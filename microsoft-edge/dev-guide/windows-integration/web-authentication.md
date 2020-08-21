---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: 了解 Web 身份验证 API 如何启用 Web 应用程序以使用 Windows Hello 和 FIDO2 进行用户身份验证。
title: Web 身份验证 - 开发人员指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: windows-integration
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: b8ff3769434c17b5508978c64b5d9c14e7e3bdaa
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941815"
---
# Web 身份验证和 Windows Hello  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

Microsoft Edge [中的 Web 身份验证 API](https://w3c.github.io/webauthn) 允许 Web 应用程序使用 Windows [Hello 和](https://www.microsoft.com/windows/comprehensive-security) 外部 [FIDO2 设备](https://fidoalliance.org/fido2) 进行用户身份验证，以便你和你的用户可以避免密码管理的所有各种问题，包括密码来宾、网络网络处理和密钥日志记录的问题。  当前 Microsoft Edge 实现基于 Web 身份验证规范的待选建议。  

> [!IMPORTANT]
> 本主题将介绍如何尝试使用 Microsoft Edge 的 Windows Hello 和 FIDO2 身份验证。  

通过使用 Web 身份验证，服务器会将纯文本内容发送到浏览器。  一次 Microsoft Edge 能够通过 Windows Hello 或外部 FIDO2 设备验证用户，系统将使用之前为此用户预配置的私钥来签名该挑选，然后将签名重新发送到服务器。  如果服务器可以使用它对该用户所具有的公钥验证签名，并验证挑测是否正确，它可以安全地对用户进行身份验证。  使用 [非对称加](https://en.wikipedia.org/wiki/Public-key_cryptography) 密，公钥本身是无意义的，私钥不会共享。  而且，在启用了 TPM 的硬件的情况下，私钥永远无法从任何支持 TPM 的安全元素或现代系统中进行移动。  

可以使用 Web 身份验证 API 的基本步骤：  

1.  向用户注册 `create`  
1.  通过 `get`  

下面的开发指南将引导你使用 [WebAuthn](https://github.com/MicrosoftEdge/webauthnsample)示例应用来完成此流程。  

## 注册用户  

作为标识提供程序，首先需要使用该方法为用户创建 Web 身份验证 `navigator.credentials.create` 凭据。  在向服务器上的用户注册该凭据之前，您需要确认用户的身份。  这可以通过向用户发送电子邮件确认，或要求用户使用其传统登录方法来完成。  

`create`该方法使用以下参数：  

:::row:::
   :::column span="1":::
      **保留方信息**  
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
      **其他选项：**  
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

您可以 [使用凭据创建参数](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) 来配置要创建的凭据。  特别要在外部 FIDO2 设备上，你可以选择通过将设置设置为或 `authenticatorAttachment` `platform` 通过将外部 FIDO2 设备上的漫游凭据设置为来创建 Windows Hello 凭据 `authenticatorAttachment` `cross-platform` 。  

当你使用该方法时，Microsoft Edge 将先让用户验证其状态：扫描他们的面部或指 `create` 纹、进入 PIN 或在外部 FIDO2 设备上执行操作。  完成此步骤后，验证器将生成公钥对并存储私钥。  这些凭据按原源、每个帐户安全创建，并且无法提取，因为它们安全地存储到身份验证设备。  

生成的 promise 返回 [表示新](https://w3c.github.io/webauthn#sctn-attestation) 凭据的证明对象。  证明对象包含凭据的公钥。  您将将该对象发送到服务器以验证将来的身份验证。  在返回服务器之前，你需要对原始数据进行编码。  

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

然后，服务器应解码证明对象，执行验证步骤，为此凭据提取公钥，并将密钥存储在未来身份验证中。  有关步骤的详细列表，可以在 WebAuthn [规](https://w3c.github.io/webauthn#registering-a-new-credential) 范的凭据注册算法中找到。  

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

## 验证你的用户  

在客户端上创建凭据后，用户下次尝试登录到该站点时，你可以提供 Web 身份验证凭据登录，而非通过调用密码来登录 `navigator.credentials.get` 。  

`get`该方法将这些挑包作为它的仅必需的参数。  挑质问题是服务器将向下发送到客户端以便使用用户的私钥进行登录的不理确结果。  例如：  

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

从服务器检索挑质后，你将调用 GET API 以及 [凭据请求选项](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。  Microsoft Edge 将显示一条提示，这将验证使用 Windows Hello 或外部 FIDO2 设备的用户的身份。  在用户经过验证后，问题将在 TPM 或 FIDO2 设备上进行登录，承诺将返回 [包含](https://w3c.github.io/webauthn#authenticatorassertionresponse) 签名及其他元数据的断言对象供您发送给服务器。  

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

在服务器上收到断断后，你将需要验证该签名以对用户进行身份验证。  下面是一些示例代码。  有关步骤的详细列表可以在 WebAuthn [规](https://w3c.github.io/webauthn#verifying-assertion) 范中的断包验证算法中找到。  

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

*   从 Microsoft Edge 开始使用 Candidate 建议版本的 Web 身份验证 API，此版本从 Microsoft Edge 开始使用，该版本号为 18 \ (Windows Insider Preview 版本 17713 或更高版本\) 。  
*   已 [删除前缀、Web](https://blogs.windows.com/msedgedev/2016/04/12) 身份验证 API 预览版本，且不再可用。  
*   Web 身份验证 API 尚不适用于 UWP 应用和 PWA。  
*   Internet Explorer验证 API 不支持 Web 身份验证 API。  

### 支持的身份验证器  

使用 Microsoft Edge 中的 Web 身份验证 API，你可使用以下技术来对用户进行身份验证：  

*   **Windows Hello**  通过面板、指纹或 PIN 启用无密码身份验证  
*   **FIDO2**  启用使用可移动设备以及指纹或 PIN 进行无密码漫游身份验证  
*   **U2F**  为尚未准备移至密码模型的网站启用强第二个因素身份验证  

### Windows Hello 的特殊注意事项  

使用 Windows Hello 验证器时需要注意的一些事项：  

*   你可以通过调用 API 检测电脑是否支持 Windows `isUserVerifyingPlatformAuthenticatorAvailable` Hello。  请在此处了解有关此 API [的详细信息](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。  
*   在为 Windows Hello 创建凭据时，你应设置为 `authenticatorAttachment` `platform` 提供最佳的用户体验。
*   Windows Hello 仅支持 RS256 \ (alg -257\) 作为其公钥算法。  在创建凭据时，请务必指定此算法。  
*   若要接收 [TPM 证明语句，请在](https://w3c.github.io/webauthn#tpm-attestation)调用 API 时将证明设置为"直接 `create` "。  TPM 证明最好是实现最佳工作。  仅具有 TPM 2.0 的电脑将返回 TPM 证明，因此证明过程可能由于多种原因而失败。  
*   Windows Hello 使用多种方法来保护用户凭据。  你可以通过在凭据创建时返回的同步对象中使用 [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) 字段来检查是否使用了哪种方法来保护凭据。  下面是 Windows Hello 可能返回的 AAGUID 列表：   
    *   软件支持的身份验证器  
        *   Windows Hello 软件验证器：  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   Windows Hello VBS 软件验证器：  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   受信任的平台模块 \ (TPM\支持) 验证器  
        *   Windows Hello 硬件验证器：  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   Windows Hello VBS 硬件身份验证器：  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### API 平面  

*   Microsoft Edge 已完全实现内采用的内部 Web 身份验证规范的全部推荐版本。  
*   支持 [AppID 扩展](https://w3c.github.io/webauthn#sctn-appid-extension) 。  
*   不支持其他扩展名。  

## 演示  

[客户端和服务器代码示例](https://github.com/MicrosoftEdge/webauthnsample)  

[Windows Hello 测试驱动器演示](https://webauthnsample.azurewebsites.net)  

## 规范  

[Web 身份验证：用于访问公钥凭据的 API](http://w3c.github.io/webauthn)  
