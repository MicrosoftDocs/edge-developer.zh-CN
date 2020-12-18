---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: 了解 Web 身份验证 API 如何允许 Web 应用程序使用 Windows Hello 和 FIDO2 进行用户身份验证。
title: Web 身份验证 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 07f1de47156f43ff4726e8907a123c2cb1afc337
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232288"
---
# Web 身份验证和 Windows Hello  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge 中的 Web 身份验证 [API](https://w3c.github.io/webauthn) 使 Web 应用程序可以使用 [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) 和外部 [FIDO2](https://fidoalliance.org/fido2) 设备进行用户身份验证，以便你和用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和密钥日志记录攻击。  当前的 Microsoft Edge 实现基于 Web 身份验证规范的候选建议。  

> [!IMPORTANT]
> 本主题将向你展示如何使用 Microsoft Edge 试用 Windows Hello 和 FIDO2 身份验证。  

使用 Web 身份验证，服务器向下向浏览器发送纯文本质询。  一旦 Microsoft Edge 能够通过 Windows Hello 或外部 FIDO2 设备验证用户，系统将使用先前为此用户预配的私钥对质询进行签名，并将签名发送回服务器。  如果服务器可以使用其为该用户使用的公钥验证签名并验证质询是否正确，则它可以对用户进行安全身份验证。  对于 [此类非](https://en.wikipedia.org/wiki/Public-key_cryptography) 对称加密，公钥本身没有任何意义，并且私钥永远不会共享。  此外，私钥永远不能从安全元素或具有启用 TPM 的硬件的新式系统中移动。  

使用 Web 身份验证 API 有两个基本步骤：  

1.  向用户注册 `create`  
1.  向用户进行身份验证 `get`  

下面的开发指南将指导你使用 [WebAuthn 示例应用完成此流](https://github.com/MicrosoftEdge/webauthnsample)。  

## 注册用户  

作为标识提供程序，您首先需要通过该方法为用户创建 Web 身份验证 `navigator.credentials.create` 凭据。  在服务器上向用户注册该凭据之前，需要确认用户的身份。  这可以通过向用户发送电子邮件确认或要求他们使用其传统的登录方法完成。  

`create`该方法采用以下参数：  

:::row:::
   :::column span="1":::
      **信赖方信息**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      rp: {
          name: "WebAuthn Sample App",
          icon: "https://example.com/rpIcon.png"
      },
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **用户帐户信息**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      user: {
          id: stringToArrayBuffer("some.user.id"),
          name: "bob.smith@contoso.com",
          displayName: "Bob Smith",
          icon: "https://example.com/userIcon.png"
      },
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **加密参数**  
   :::column-end:::
   :::column span="3":::
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
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **验证器选择参数**  
   :::column-end:::
   :::column span="3":::
      ```javascript
      authenticatorSelection: {
          //Select authenticators that support username-less flows
          requireResidentKey: true,
          //Select authenticators that have a second factor (such as PIN, Bio)
          userVerification: "required",
          //Selects between bound or detachable authenticators
          authenticatorAttachment: "platform"
      },
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **其他选项**  
   :::column-end:::
   :::column span="3":::
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
   :::column-end:::
:::row-end:::  

可以使用 [凭据创建参数](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) 来配置要创建的凭据。  特别是，你可以选择通过设置为创建 Windows Hello 凭据，或者选择通过设置为外部 `authenticatorAttachment` `platform` FIDO2 设备的漫游 `authenticatorAttachment` 凭据 `cross-platform` 。  

使用此方法时，Microsoft Edge 将首先要求用户通过扫描其面部或指纹、输入 PIN 或在外部 FIDO2 设备上采取措施来验证其 `create` 状态。  完成此步骤后，验证器将生成公钥对并存储私钥。  这些凭据是每个源、每个帐户创建的，无法提取，因为它们安全地存储在身份验证设备中。  

生成的承诺返回一 [个表示新](https://w3c.github.io/webauthn#sctn-attestation) 凭据的证明对象。  证明对象包含凭据的公钥。  您将此对象发送到服务器以验证将来的身份验证。  在发送回服务器之前，你需要对原始数据进行 base64 编码。  

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

然后，服务器应解码证明对象、执行验证步骤、提取此凭据的公钥并存储它供将来身份验证。  可以在 WebAuthn 规范的凭据注册 [算法](https://w3c.github.io/webauthn#registering-a-new-credential) 中找到详细步骤列表。  

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

## 对用户进行身份验证  

在客户端上创建凭据后，用户下次尝试登录网站时，可以使用其 Web 身份验证凭据（而不是调用密码）提供登录 `navigator.credentials.get` 。  

该方法 `get` 将质询作为它的唯一必需参数。  这一挑战是一个不透明的字节序列，服务器将向下发送到客户端以使用用户的私钥进行签名。  例如：  

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

从服务器检索质询后，你将调用获取 API 以及 [凭据请求选项](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。  Microsoft Edge 将显示一个提示，该提示将验证使用 Windows Hello 或外部 FIDO2 设备的用户身份。  验证用户后，将在 TPM 或 FIDO2 设备中对质询进行签名，承诺将返回包含签名和其他[](https://w3c.github.io/webauthn#authenticatorassertionresponse)元数据的断言对象，供你发送到服务器。  

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

在服务器上收到断言后，您需要验证签名以对用户进行身份验证。  下面是一些示例代码。  可以在 WebAuthn 规范的断言 [验证算法](https://w3c.github.io/webauthn#verifying-assertion) 中找到详细步骤列表。  

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

## 实施说明  

### 支持的平台  

*   Web 身份验证 API 的候选建议版本可以从 Microsoft Edge 从 EdgeHTML 18 \ (Windows Insider Preview 版本 17713 或更高版本\) 。  
*   前缀 [的预览版](https://blogs.windows.com/msedgedev/2016/04/12) Web 身份验证 API 已删除且不再可用。  
*   Web 身份验证 API 尚不可用于 UWP 应用和 PWA。  
*   Internet Explorer不支持 Web 身份验证 API。  

### 支持的验证器  

通过 Microsoft Edge 中的 Web 身份验证 API，可以使用以下技术对用户进行身份验证：  

*   **Windows Hello**  使用人脸、指纹或 PIN 启用无密码的设备内身份验证  
*   **FIDO2**  使用可移动设备和指纹或 PIN 启用无密码漫游身份验证  
*   **U2F**  为未准备好移动到无密码模型的网站启用强大的第二重身份验证  

### Windows Hello 的特殊注意事项  

使用 Windows Hello 验证器时要注意的一些注意事项：  

*   可以通过调用 API 检测电脑上是否提供 `isUserVerifyingPlatformAuthenticatorAvailable` Windows Hello。  在此处了解有关此 API [的更多信息](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。  
*   为 Windows Hello 创建凭据时，应 `authenticatorAttachment` 设置为 `platform` 提供最佳用户体验。
*   Windows Hello 仅支持 RS256 \ (alg -257\) 用作其公钥算法。  请确保在创建凭据时指定此算法。  
*   若要接收 [TPM 证明语句](https://w3c.github.io/webauthn#tpm-attestation)，在调用 API 时将证明设置为 `create` "direct"。  TPM 证明是一项最佳选择。  只有具有 TPM 2.0 的 PC 将返回 TPM 证明语句，证明过程可能会由于各种原因失败。  
*   Windows Hello 采用多种方法来保护用户凭据。  您可以通过使用凭据创建时返回的证明对象中的 [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) 字段来检查用于保护凭据的方法。  以下是 Windows Hello 可能返回的 AAGUID 的列表：   
    *   软件支持的验证器  
        *   Windows Hello 软件验证器：  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   Windows Hello VBS 软件验证器：  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   受信任的平台模块 \ (TPM\) 验证器  
        *   Windows Hello 硬件验证器：  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   Windows Hello VBS 硬件验证器：  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### API 平面  

*   Microsoft Edge 具有核心 Web 身份验证规范的候选建议版本的完整实现。  
*   [支持 AppID](https://w3c.github.io/webauthn#sctn-appid-extension)扩展。  
*   不支持其他扩展。  

## 演示  

[客户端和服务器代码示例](https://github.com/MicrosoftEdge/webauthnsample)  

[Windows Hello 测试驱动器演示](https://webauthnsample.azurewebsites.net)  

## 规范  

[Web 身份验证：用于访问公钥凭据的 API](http://w3c.github.io/webauthn)  
