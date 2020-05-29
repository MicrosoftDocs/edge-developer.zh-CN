---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: 了解 Web 应用程序如何能够使 web 应用程序使用 Windows Hello 和 FIDO2 进行用户身份验证。
title: 开发人员指南-Web 身份验证
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: cb561ae4147a24489138263a83dd37bd6f599074
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562975"
---
# Web 身份验证和 Windows Hello

Microsoft Edge 中的[Web 身份验证 API](https://w3c.github.io/webauthn)使 web 应用程序可以使用[Windows HELLO](https://go.microsoft.com/fwlink/p/?LinkID=624961)和[外部 FIDO2 设备](https://fidoalliance.org/fido2)进行用户身份验证，以便你和你的用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和按键日志记录攻击。 当前 Microsoft Edge 实现基于 Web 身份验证规范的候选建议。 **本主题将介绍如何通过 Microsoft Edge 试用 Windows Hello 和 FIDO2 身份验证。**

使用 Web 身份验证，服务器将纯文本质询发送到浏览器。 一旦 Microsoft Edge 能够通过 Windows Hello 或外部 FIDO2 设备验证用户，系统将使用以前为此用户预配的私钥对质询进行签名，并将签名重新发送到服务器。 如果服务器可以使用其针对该用户的公钥验证签名并验证质询是否正确，则可以安全地验证用户身份。 利用[非对称加密](https://en.wikipedia.org/wiki/Public-key_cryptography)（如这样），公钥本身毫无意义，私钥永远不会共享。 此外，私钥永远不能通过启用 TPM 的硬件从安全元素或新式系统中进行移动。

使用 Web 身份验证 API 有两个基本步骤：

**1. 向注册用户 `create`**

**2. 通过验证您的用户 `get`**

下面的开发人员指南将通过使用[WebAuthn 示例应用](https://github.com/MicrosoftEdge/webauthnsample)指导你完成此流程。

## 注册您的用户

作为*标识提供者*，你首先需要使用导航器为你的用户创建 Web 身份验证凭据。**create**方法。 将该凭据注册到服务器上的用户之前，您需要确认用户的身份。 可通过向用户发送电子邮件确认或要求他们使用传统的登录方法来完成此操作。


该 `create` 方法采用以下参数：

 - **信赖方信息**

```javascript
    rp: {
        name: "WebAuthn Sample App",
        icon: "https://example.com/rpIcon.png"
    },
```

 - **用户帐户信息**

```javascript
    user: {
        id: stringToArrayBuffer("some.user.id"),
        name: "bob.smith@contoso.com",
        displayName: "Bob Smith",
        icon: "https://example.com/userIcon.png"
    },
```

 - **加密参数**

```javascript
    pubKeyCredParams: [
        {
            //External authenticators support the ES256 algorithm
            type: "public-key",
            alg: -7                 
        }, 
        {
            //Windows Hello supports the RS256 algorithm
            type: "public-key",
            alg: -257
        }
    ],
```

 - **身份验证器选择参数**

```javascript
    authenticatorSelection: {
        //Select authenticators that support username-less flows
        requireResidentKey: true,
        //Select authenticators that have a second factor (e.g. PIN, Bio)
        userVerification: "required",
        //Selects between bound or detachable authenticators
        authenticatorAttachment: "platform"
    },
```

- **其他选项**

```javascript
    //Select larger timeout values, as Microsoft Edge shows UI
    timeout: 50000,
    //an opaque challenge that the authenticator signs over
    challenge: challenge,
    //prevent re-registration by specifying existing credentials here
    excludeCredentials: [],
    //specifies whether you need an attestation statement
    attestation: "none" 
```

你可以使用[凭据创建参数](https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions)配置要创建的凭据。 特别是，你可以 `authenticatorAttachment` `platform` 通过设置为来选择在外部 FIDO2 设备上通过设置 to 或漫游凭据创建 Windows Hello 凭据 `authenticatorAttachment` `cross-platform` 。 

使用此方法时 `create` ，Microsoft Edge 将首先要求用户通过扫描其面孔或指纹、输入 PIN 或在外部 FIDO2 设备上执行操作来验证其状态。 完成此步骤后，身份验证器将生成一个公用/专用密钥对并存储私钥。 这些凭据根据每个帐户创建，并且无法提取，因为它们被安全地存储到身份验证设备。 

结果承诺返回表示新凭据的[证明对象](https://w3c.github.io/webauthn/#sctn-attestation)。 证明对象包含凭据的公钥。 将此对象发送到服务器，以便验证未来身份验证。 将原始数据发送回服务器之前，需要对原始数据进行 base64 编码。

**客户端**

```javascript
<script>
    navigator.credentials.create({
        publicKey: createCredentialOptions
    }).then(rawAttestation => {
        var attestation = {
            id: base64encode(rawAttestation.rawId),
            clientDataJSON: arrayBufferToString(rawAttestation.response.clientDataJSON),
            attestationObject: base64encode(rawAttestation.response.attestationObject)
        };
        return rest_put("/credentials", attestation);
    })
</script>
```

然后，服务器应解码证明对象，执行验证步骤，提取此凭据的公钥，然后将其存储下来以供将来身份验证。 可在 WebAuthn 规范的[凭据注册算法](https://w3c.github.io/webauthn/#registering-a-new-credential)中找到详细步骤列表。

**Server**

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```

## 验证用户身份

在客户端上创建凭据后，下次用户尝试登录到该网站时，您可以使用其 Web 身份验证凭据（而不是使用 "导航器" 调用的密码）对其进行签名。**获取**。

该 `get` 方法将*质询*视为唯一的必需参数。 质询是一种不透明的字节序列，服务器将向客户端发送该字节序列，以使用用户的私钥进行签名。 例如：

**Server**

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```

从服务器检索质询后，将调用 get API 以及[凭据请求选项](https://w3c.github.io/webauthn/#credentialrequestoptions-extension)。 Microsoft Edge 将显示一个提示，它将验证使用 Windows Hello 或外部 FIDO2 设备的用户的身份。 验证用户后，质询将在 TPM 或 FIDO2 设备中签名，并且承诺将返回一个[断言对象](https://w3c.github.io/webauthn/#authenticatorassertionresponse)，该对象包含用于发送到服务器的签名和其他元数据。

**客户端**

```javascript
    var credentialRequestOptions = {
        //specifies which credential IDs are allowed to authenticate the user
        //if empty, any credential can authenticate the users
        allowCredentials: allowCredentials,
        //an opaque challenge that the authenticator signs over
        challenge: challenge,
        //Select larger timeout values, as Microsoft Edge shows UI
        timeout: 50000
    };

    navigator.credentials.get({
        publicKey: credentialRequestOptions
    }).then(rawAssertion => {
        var assertion = {
            id: base64encode(rawAssertion.rawId),
            clientDataJSON: arrayBufferToString(rawAssertion.response.clientDataJSON),
            userHandle: base64encode(rawAssertion.response.userHandle),
            signature: base64encode(rawAssertion.response.signature),
            authenticatorData: base64encode(rawAssertion.response.authenticatorData)
        };
        return rest_put("/assertion", assertion);
    })
```

在服务器上收到断言后，你将需要验证签名以对用户进行身份验证。 下面是一些示例代码。  可在 WebAuthn 规范的[断言验证算法](https://w3c.github.io/webauthn/#verifying-assertion)中找到详细步骤列表。

**Server**

```javascript
    var jwkToPem = require('jwk-to-pem')
    var crypto = require('crypto');

    ...

    // Using credential’s id attribute, look up the corresponding 
    // credential public key.
    var credential = await storage.Credentials.findOne({
        id: assertion.id
    });

    //Refer to sample to see how to verify client data and authenticator data

    ...

    //Using the credential public key from lookup, verify that sig is a valid
    //signature over the binary concatenation of authData and hash.
    var publicKey = credential.publicKeyJwk;
    var verify = (publicKey.kty === "RSA") ? crypto.createVerify('RSA-SHA256') : crypto.createVerify('sha256');
    verify.update(authData);
    verify.update(hash);
    if (!verify.verify(jwkToPem(publicKey), sig))
        throw new Error("Could not verify signature");

    //Verify signCount has increased or is zero 
    if (authenticatorData.signCount != 0 &&
        authenticatorData.signCount < credential.signCount) {
        throw new Error("Received signCount of " + authenticatorData.signCount +
            " expected signCount > " + credential.signCount);
    }
```

## 实现说明

### 支持的平台
- Web 身份验证 API 的候选推荐版本可从 Microsoft Edge 中使用 EdgeHTML 18 （Windows 预览体验计划预览版17713及更高版本）。
- "已删除" 和 "Web 身份验证 API" 的[前缀版本](https://blogs.windows.com/msedgedev/2016/04/12/a-world-without-passwords-windows-hello-in-microsoft-edge/)已被删除，不再可用。
- Web 身份验证 API 尚不可用于 UWP 应用和 PWAs。
- Internet Explorer 不支持 Web 身份验证 API。 

### 支持的 authenticators
通过 Microsoft Edge 中的 Web 身份验证 API，你可以通过以下技术对用户进行身份验证：
- **Windows Hello**，通过面孔、指纹或 PIN 启用 passwordless 设备身份验证
- **FIDO2**，通过可移动设备和指纹或 PIN 启用 passwordless 漫游身份验证
- **U2F**，为尚未准备好移动到 passwordless 模型的网站启用强烈的第二因素身份验证

### Windows Hello 的特殊注意事项 
使用 Windows Hello 身份验证器时需要注意的一些事项：
- 你可以通过调用 API 来检测电脑上是否可以使用 Windows Hello `isUserVerifyingPlatformAuthenticatorAvailable` 。 [在此处](https://www.w3.org/TR/webauthn/#isUserVerifyingPlatformAuthenticatorAvailable)了解有关此 API 的详细信息。
- 创建适用于 Windows Hello 的凭据时，应将设置 `authenticatorAttachment` 为以 `platform` 获得最佳用户体验。
- Windows Hello 仅支持 RS256 （alg-257）作为其公钥算法。 请确保在创建凭据时指定此算法。
- 若要接收[TPM 证明语句](https://w3c.github.io/webauthn/#tpm-attestation)，请在调用 API 时将证明设置为 "direct" `create` 。 TPM 证明是一种最大努力。 只有使用 TPM 2.0 的电脑才会返回 TPM 证明声明，并且证明过程可能会因各种原因而失败。
- Windows Hello 采用多种方法来保护用户凭据。 你可以通过在凭据创建时使用证明对象中的[AAGUID](https://w3c.github.io/webauthn/#sec-attested-credential-data)字段来检查用于保护凭据的方法。 以下是 Windows Hello 可能返回的 AAGUIDs 的列表： 
  - 软件支持的 authenticators
    - Windows Hello 软件身份验证器： `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`
    - Windows Hello VBS 软件身份验证器： `6E96969E-A5CF-4AAD-9B56-305FE6C82795`
  - 受信任的平台模块（TPM）受支持的 authenticators
    - Windows Hello 硬件身份验证器： `08987058-CADC-4B81-B6E1-30DE50DCBE96`
    - Windows Hello VBS 硬件身份验证器： `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`


### API 平面
- Microsoft Edge 已完全实现了核心 Web 身份验证规范的候选推荐版本。
- 支持[AppID 扩展](https://w3c.github.io/webauthn/#sctn-appid-extension)。 
- 不支持其他扩展。


## 演示

[客户端和服务器代码示例](https://github.com/MicrosoftEdge/webauthnsample)

[Windows Hello 测试驱动器演示](https://webauthnsample.azurewebsites.net/)

## 书

[Web 身份验证：用于访问公钥凭据的 API](http://w3c.github.io/webauthn/)
