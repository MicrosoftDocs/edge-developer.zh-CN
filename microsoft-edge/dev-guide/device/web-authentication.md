---
ms.assetid: 88825563-5f5d-421d-861b-7cec01277dec
description: 了解如何使用 Web 身份验证 API 使 web 应用程序可以使用 Windows Hello 生物识别进行用户身份验证。
title: 开发人员指南-Web 身份验证
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 01/15/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: c49d181633ae1b2b35aa0f88287841d28e806f44
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562630"
---
# Web 身份验证和 Windows Hello

Microsoft Edge 中的 Web 身份验证（以前称为*FIDO 2.0* ） API 使 Web 应用程序可以使用[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)生物识别进行用户身份验证，以便你和你的用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和 keylogging 攻击。 当前 Microsoft Edge （以*毫秒为*前缀）实现基于 Web 身份验证规范的早期草案，将来可能会发生更改。 **本主题将介绍如何试用 Microsoft Edge 的 Windows Hello 身份验证，还将针对浏览器更新进一步校对你的代码。**

Web 身份验证 API 是[FIDO 联盟](https://fidoalliance.org/)的新兴标准，其目的在于提供一种可互操作的方法，使用 Windows Hello 和跨浏览器的其他生物识别设备进行 Web 身份验证。 Web 身份验证规范定义了两种身份验证方案：密码不足和两个因素。 在不带密码的情况下，用户无需使用用户名或密码登录到网页-他们可以使用 Windows Hello 进行单独登录。 在这两种情况下，用户通常使用用户名和密码登录，但 Windows Hello 将用作第二个因素检查，以使整体身份验证更强。

使用与 Windows Hello 结合使用的 Web 身份验证，服务器将纯文本质询发送到浏览器。 一旦 Microsoft Edge 能够通过 Windows Hello 验证用户，系统将使用以前为此用户预配的私钥对质询进行签名，并将签名重新发送到服务器。 如果服务器可以使用其针对该用户的公钥验证签名并验证质询是否正确，则可以安全地验证用户身份。 利用[非对称加密](https://en.wikipedia.org/wiki/Public-key_cryptography)（如这样），公钥本身毫无意义，私钥永远不会共享。 此外，私钥永远不能从新式系统中通过启用 TPM 的硬件进行移动。

使用 Web 身份验证 API 有两个基本步骤：

**1. 向注册用户 `makeCredential`**

**2. 通过验证您的用户 `getAssertion`**

以下将使用推荐的[Webauthn polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)引导你完成此流程。 [完整代码](https://github.com/adrianba/fido-snippets/)可用于此服务器和客户端演示。 [C #](https://github.com/adrianba/fido-snippets/tree/master/csharp)、 [PHP](https://github.com/adrianba/fido-snippets/tree/master/php)和[node.js](https://github.com/adrianba/fido-snippets/tree/master/nodejs)服务器端版本可用。

## 注册您的用户

作为*标识提供者*，你首先需要使用 window for 用户创建 Web 身份验证凭据。**makeCredential**方法。 将该凭据注册到服务器上的用户之前，您需要确认用户的身份。 可通过向用户发送电子邮件确认或要求他们使用传统的登录方法来完成此操作。

MakeCredential 方法采用以下参数：
 - **用户帐户信息**

```
    var userAccountInformation = {
        rpDisplayName: "fido-demo",
        displayName: email
    };
```

 - **加密参数**

```
    var cryptoParams = [
        {
            type: "ScopedCred",
            algorithm: "RSASSA-PKCS1-v1_5",
        }
    ];
```

结果承诺返回一个对象，该对象表示您随后发送回服务器以验证未来身份验证的凭据：

**客户端**

```
<script src="webauthn.js"><!-- polyfill to map Microsoft Edge experimental implementation to current W3C spec --></script>
<script>
    var email = '<%=user.email%>';
    var name = '<%=user.name%>';

    webauthn.makeCredential(userAccountInformation, cryptoParams)
        .then(function (creds) {
            document.getElementById('form-id').value = creds.credential.id;
            document.getElementById('form-pk').value = JSON.stringify(creds.publicKey);
            document.getElementById('form-email').value = email;
            document.getElementById('form-name').value = name;
            document.getElementById('theform').submit();
        }).catch(function (err) {
            // No acceptable authenticator or user refused consent. Handle appropriately.
            alert(err);
        });
</script>
```

使用 makeCredential 方法时，Microsoft Edge 将首先要求 Windows Hello 使用面孔标识或指纹标识，以验证用户是否与登录到 Windows 帐户的用户相同。 完成此步骤后，Microsoft Passport 将生成一个公共/专用密钥对，并将私钥存储在受信任的平台模块（TPM）中，该专用加密处理器硬件用于存储凭据。 如果用户没有启用 TPM 的设备，这些密钥将存储在软件中。 这些凭据按照每个 Windows 帐户创建，不会被漫游，因为它们与设备相关联。 这意味着，你需要确保用户注册对其使用的每个设备使用 Windows Hello。

## 验证用户身份

在客户端上创建凭据后，下次用户尝试登录到该网站时，你可以使用 Windows Hello （而不是通过调用 window. webauthn）对其进行签名。**getAssertion**。

GetAssertion 方法将*质询*视为唯一的必需参数。 质询是随机生成的数量，服务器将向客户端发送该数量，以使用用户的私钥进行签名。 例如：

**Server**

```
var crypto = require('crypto');

Strategy.prototype.generateChallenge = function() {
    return this.generateVerifiableString(crypto.randomBytes(32));
};

Strategy.prototype.generateVerifiableString = function(data) {
    // Create cipher using secret
    var d = new Buffer(data);
    var c = crypto.createCipher('aes192',new Buffer(this._secret));

    // Encrypt data
    c.update(d);

    // Hash results of encrypting data
    var hash = crypto.createHash('sha256');
    hash.update(c.final());

    // Combine original data with hash
    return d.toString('hex') + string_separator + hash.digest('hex');
};
```

一旦进行 getAssertion 呼叫，Microsoft Edge 将显示 Windows Hello 提示，该提示将验证使用生物识别的用户的身份。 验证用户后，该质询将在 TPM 中签名，并且承诺将返回一个断言对象，该对象包含用于发送到服务器的签名和其他元数据：

**客户端**

```
<script src="webauthn.js"><!-- polyfill to map Microsoft Edge experimental implementation to current W3C spec --></script>
<script>
    var challenge = '<%=challenge%>';

    webauthn.getAssertion(challenge)
    .then(function(assertion) {
      document.getElementById("form-id").value = assertion.credential.id;
      document.getElementById("form-type").value = assertion.credential.type;
      document.getElementById("form-data").value = assertion.clientData;
      document.getElementById("form-sig").value = assertion.signature;
      document.getElementById("form-authnr").value = assertion.authenticatorData;
      document.getElementById("form-challenge").value = challenge;
      document.getElementById("theform").submit();
    })
    .catch(function(err) {
      if(err && err.name) {
        document.getElementById("form-err").value = err.name;
      } else {
        document.getElementById("form-err").value = "unknown";
      }
      document.getElementById("theform").submit();
    });

</script>
```

在服务器上收到断言后，你将需要验证签名以对用户进行身份验证。 例如（在 NODE.JS 中）：

**Server**

```
var jwkToPem = require('jwk-to-pem')
var crypto = require('crypto');

var fidoAuthenticator = {
     validateSignature: function (publicKey, clientData, authnrData, signature, challenge) {
         // Make sure the challenge in the client data
         // matches the expected challenge
         var c = new Buffer(clientData, 'base64');
         var cc = JSON.parse(c.toString().replace(/\0/g,''));
         if(cc.challenge != challenge) return false;

         // Hash data with sha256
         const hash = crypto.createHash('sha256');
         hash.update(c);
         var h = hash.digest();

         // Verify signature is correct for authnrData + hash
         var verify = crypto.createVerify('RSA-SHA256');
         verify.update(new Buffer(authnrData,'base64'));
         verify.update(h);
         return verify.verify(jwkToPem(JSON.parse(publicKey)), signature, 'base64');
     }
};   
```

## Microsoft Edge 与规范之间的区别

> [!NOTE]
> 在 Microsoft Edge 中尝试使用 Windows Hello 的 Web 身份验证 API 时，我们建议使用 polyfill 中所示的 "Webauthn"，以避免必须考虑此处列出的差异。 我们将为该规范的每个主要发布版本更新此 polyfill。


当前 Microsoft Edge 实现基于 Web 身份验证规范的早期草案，并且可能会在将来的内部版本中更改，并且在规范演变时也可能会发生更改。 当前差异包括：

- Microsoft Edge Api 为 MS 前缀。
- Microsoft Edge 尚不支持诸如 USB 密钥或蓝牙设备之类的外部凭据。 当前 API 仅限于 TPM 中存储的嵌入凭据。
- 当前登录的 Windows 用户帐户必须配置为至少支持 PIN，并且最好是指纹或指纹生物识别。 这是为了确保 Windows 可以对 TPM 的访问进行身份验证。
- Microsoft Edge 实现尚不支持帐户选取器体验。
- 调用 msCredentials 的第二个*筛选器*参数当前需要指定凭据 id。[getAssertion](https://msdn.microsoft.com/library/mt697640)。 因此，你需要在客户端上的本地存储中存储凭据 ID 信息（在 indexDB 或 localStorage 中进行凭据时）。 如果用户删除其浏览历史记录（包括本地存储），他们将需要重新注册才能在下次登录时使用 Windows Hello。
- Microsoft Edge 不支持当前 Web 身份验证规范草稿中的所有选项，如 "延长" 或 "超时"。

最后一点，以下 Web 身份验证规范定义中注明了特定的 Microsoft Edge 差异：

### W3C 规范

```
partial interface Window {
    readonly attribute WebAuthentication webauthn; // msCredentials
};

interface WebAuthentication { // MSCredentials
    Promise <ScopedCredentialInfo> makeCredential (
        Account                                 accountInformation,
        sequence <ScopedCredentialParameters>   cryptoParameters,
        DOMString                               attestationChallenge, // Optional in Microsoft Edge
        optional unsigned long                  credentialTimeoutSeconds, // Not yet supported
        optional sequence <Credential>          blacklist, // Not yet supported
        optional WebAuthnExtensions             credentialExtensions // Not yet supported
    );

    Promise <WebAuthnAssertion> getAssertion (
        DOMString                        assertionChallenge,
        optional unsigned long           assertionTimeoutSeconds, // Not yet supported
        optional sequence <Credential>   whitelist, // Not yet supported
        optional WebAuthnExtensions      assertionExtensions // Not yet supported
    );
};

interface ScopedCredentialInfo { // MSAssertion
    readonly attribute Credential           credential;
    readonly attribute any                  publicKey;
    readonly attribute AttestationStatement attestation;
};

dictionary Account { // MSAccountInfo
    required DOMString rpDisplayName;
    required DOMString displayName;
    DOMString          name; // Not yet supported
    DOMString          id; // Not yet supported
    DOMString          imageUri; // Not yet supported
};

dictionary ScopedCredentialParameters { // MSCredentialParameters
    required CredentialType        type;
    required AlgorithmIdentifier   algorithm;
};

enum CredentialType { // MSCredentialType
    "ScopedCred" // Must be "FIDO_2_0" in Microsoft Edge
};

interface Credential { // MSCredentialSpec
    readonly attribute CredentialType type;
    readonly attribute DOMString      id;
};

dictionary WebAuthnExtensions { // Not supported
};
```



## API 参考

[MSCredentials](https://msdn.microsoft.com/library/mt697639)

[makeCredential](https://msdn.microsoft.com/library/mt697641)

[getAssertion](https://msdn.microsoft.com/library/mt697640)

## 演示

[客户端和服务器代码示例](https://github.com/adrianba/fido-snippets/)

[Webauthn .js polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)

[Windows Hello 测试驱动器演示](https://testdrive-fido.azurewebsites.net/)

## 书

[Web 身份验证：用于访问范围内凭据的 Web API 1](http://w3c.github.io/webauthn/)  
