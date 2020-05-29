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
# <span data-ttu-id="5e7d9-104">Web 身份验证和 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="5e7d9-104">Web authentication and Windows Hello</span></span>

<span data-ttu-id="5e7d9-105">Microsoft Edge 中的 Web 身份验证（以前称为*FIDO 2.0* ） API 使 Web 应用程序可以使用[Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961)生物识别进行用户身份验证，以便你和你的用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和 keylogging 攻击。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-105">The Web Authentication (formerly *FIDO 2.0* ) API in Microsoft Edge enables web applications to use [Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961) biometrics for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and keylogging attacks.</span></span> <span data-ttu-id="5e7d9-106">当前 Microsoft Edge （以*毫秒为*前缀）实现基于 Web 身份验证规范的早期草案，将来可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-106">The current Microsoft Edge (*ms-* prefixed) implementation is based on an earlier draft of the Web Authentication specification and is likely to change in the future.</span></span> **<span data-ttu-id="5e7d9-107">本主题将介绍如何试用 Microsoft Edge 的 Windows Hello 身份验证，还将针对浏览器更新进一步校对你的代码。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-107">This topic will show you how to try out Windows Hello authentication with Microsoft Edge while also future-proofing your code against browser updates.</span></span>**

<span data-ttu-id="5e7d9-108">Web 身份验证 API 是[FIDO 联盟](https://fidoalliance.org/)的新兴标准，其目的在于提供一种可互操作的方法，使用 Windows Hello 和跨浏览器的其他生物识别设备进行 Web 身份验证。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-108">The Web Authentication API is an emerging standard put forth by the [FIDO Alliance](https://fidoalliance.org/) with the aim of providing an interoperable way of doing web authentication using Windows Hello and other biometric devices across browsers.</span></span> <span data-ttu-id="5e7d9-109">Web 身份验证规范定义了两种身份验证方案：密码不足和两个因素。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-109">The Web Authentication specification defines two authentication scenarios: password-less and two factor.</span></span> <span data-ttu-id="5e7d9-110">在不带密码的情况下，用户无需使用用户名或密码登录到网页-他们可以使用 Windows Hello 进行单独登录。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-110">In the password-less case, the user does not need to log into the web page using a user name or password – they can login solely using Windows Hello.</span></span> <span data-ttu-id="5e7d9-111">在这两种情况下，用户通常使用用户名和密码登录，但 Windows Hello 将用作第二个因素检查，以使整体身份验证更强。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-111">In the two factor case, the user logs in normally using a username and password, but Windows Hello is used as a second factor check to make the overall authentication stronger.</span></span>

<span data-ttu-id="5e7d9-112">使用与 Windows Hello 结合使用的 Web 身份验证，服务器将纯文本质询发送到浏览器。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-112">Using Web Authentication combined with Windows Hello, the server sends down a plain text challenge to the browser.</span></span> <span data-ttu-id="5e7d9-113">一旦 Microsoft Edge 能够通过 Windows Hello 验证用户，系统将使用以前为此用户预配的私钥对质询进行签名，并将签名重新发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-113">Once Microsoft Edge is able to verify the user through Windows Hello, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span> <span data-ttu-id="5e7d9-114">如果服务器可以使用其针对该用户的公钥验证签名并验证质询是否正确，则可以安全地验证用户身份。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-114">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span> <span data-ttu-id="5e7d9-115">利用[非对称加密](https://en.wikipedia.org/wiki/Public-key_cryptography)（如这样），公钥本身毫无意义，私钥永远不会共享。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-115">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span> <span data-ttu-id="5e7d9-116">此外，私钥永远不能从新式系统中通过启用 TPM 的硬件进行移动。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-116">Furthermore, the private key can never be moved from modern systems with TPM-enabled hardware.</span></span>

<span data-ttu-id="5e7d9-117">使用 Web 身份验证 API 有两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-117">There are two basic steps to using the Web Authentication API:</span></span>

**<span data-ttu-id="5e7d9-118">1. 向注册用户</span><span class="sxs-lookup"><span data-stu-id="5e7d9-118">1. Register your user with</span></span> `makeCredential`**

**<span data-ttu-id="5e7d9-119">2. 通过验证您的用户</span><span class="sxs-lookup"><span data-stu-id="5e7d9-119">2. Authenticate your user with</span></span> `getAssertion`**

<span data-ttu-id="5e7d9-120">以下将使用推荐的[Webauthn polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)引导你完成此流程。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-120">The following will walk you through this flow using the recommended [Webauthn.js polyfill](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js).</span></span> <span data-ttu-id="5e7d9-121">[完整代码](https://github.com/adrianba/fido-snippets/)可用于此服务器和客户端演示。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-121">The [complete code](https://github.com/adrianba/fido-snippets/) is available for this server and client side demo.</span></span> <span data-ttu-id="5e7d9-122">[C #](https://github.com/adrianba/fido-snippets/tree/master/csharp)、 [PHP](https://github.com/adrianba/fido-snippets/tree/master/php)和[node.js](https://github.com/adrianba/fido-snippets/tree/master/nodejs)服务器端版本可用。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-122">[C#](https://github.com/adrianba/fido-snippets/tree/master/csharp), [PHP](https://github.com/adrianba/fido-snippets/tree/master/php), and [Node.JS](https://github.com/adrianba/fido-snippets/tree/master/nodejs) server side versions are available.</span></span>

## <span data-ttu-id="5e7d9-123">注册您的用户</span><span class="sxs-lookup"><span data-stu-id="5e7d9-123">Register your user</span></span>

<span data-ttu-id="5e7d9-124">作为*标识提供者*，你首先需要使用 window for 用户创建 Web 身份验证凭据。**makeCredential**方法。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-124">Acting as an *identity provider*, you will first need to create a Web Authentication credential for your user with the window.webauthn.**makeCredential** method.</span></span> <span data-ttu-id="5e7d9-125">将该凭据注册到服务器上的用户之前，您需要确认用户的身份。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-125">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span> <span data-ttu-id="5e7d9-126">可通过向用户发送电子邮件确认或要求他们使用传统的登录方法来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-126">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>

<span data-ttu-id="5e7d9-127">MakeCredential 方法采用以下参数：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-127">The makeCredential method takes the following parameters:</span></span>
 - **<span data-ttu-id="5e7d9-128">用户帐户信息</span><span class="sxs-lookup"><span data-stu-id="5e7d9-128">user account information</span></span>**

```
    var userAccountInformation = {
        rpDisplayName: "fido-demo",
        displayName: email
    };
```

 - **<span data-ttu-id="5e7d9-129">加密参数</span><span class="sxs-lookup"><span data-stu-id="5e7d9-129">crypto parameters</span></span>**

```
    var cryptoParams = [
        {
            type: "ScopedCred",
            algorithm: "RSASSA-PKCS1-v1_5",
        }
    ];
```

<span data-ttu-id="5e7d9-130">结果承诺返回一个对象，该对象表示您随后发送回服务器以验证未来身份验证的凭据：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-130">The resulting promise returns an object representing the credential that you then send back to the server for validating future authentications:</span></span>

**<span data-ttu-id="5e7d9-131">客户端</span><span class="sxs-lookup"><span data-stu-id="5e7d9-131">Client</span></span>**

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

<span data-ttu-id="5e7d9-132">使用 makeCredential 方法时，Microsoft Edge 将首先要求 Windows Hello 使用面孔标识或指纹标识，以验证用户是否与登录到 Windows 帐户的用户相同。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-132">When you use the makeCredential method, Microsoft Edge will first ask Windows Hello to use face or fingerprint identification to verify that the user is the same user as the one logged into the Windows account.</span></span> <span data-ttu-id="5e7d9-133">完成此步骤后，Microsoft Passport 将生成一个公共/专用密钥对，并将私钥存储在受信任的平台模块（TPM）中，该专用加密处理器硬件用于存储凭据。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-133">Once this step is completed, Microsoft Passport will generate a public/private key pair and store the private key in the Trusted Platform Module (TPM), the dedicated crypto processor hardware used to store credentials.</span></span> <span data-ttu-id="5e7d9-134">如果用户没有启用 TPM 的设备，这些密钥将存储在软件中。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-134">If the user doesn’t have a TPM enabled device, these keys will be stored in software.</span></span> <span data-ttu-id="5e7d9-135">这些凭据按照每个 Windows 帐户创建，不会被漫游，因为它们与设备相关联。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-135">These credentials are created per origin, per Windows account, and will not be roamed because they are tied to the device.</span></span> <span data-ttu-id="5e7d9-136">这意味着，你需要确保用户注册对其使用的每个设备使用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-136">This means that you’ll need to make sure the user registers to use Windows Hello for every device they use.</span></span>

## <span data-ttu-id="5e7d9-137">验证用户身份</span><span class="sxs-lookup"><span data-stu-id="5e7d9-137">Authenticate your user</span></span>

<span data-ttu-id="5e7d9-138">在客户端上创建凭据后，下次用户尝试登录到该网站时，你可以使用 Windows Hello （而不是通过调用 window. webauthn）对其进行签名。**getAssertion**。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-138">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using Windows Hello instead of a password with a call to window.webauthn.**getAssertion**.</span></span>

<span data-ttu-id="5e7d9-139">GetAssertion 方法将*质询*视为唯一的必需参数。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-139">The getAssertion method takes the *challenge* as its only required parameter.</span></span> <span data-ttu-id="5e7d9-140">质询是随机生成的数量，服务器将向客户端发送该数量，以使用用户的私钥进行签名。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-140">The challenge is the randomly generated quantity that the server will send down to a client to sign with the user's private key.</span></span> <span data-ttu-id="5e7d9-141">例如：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-141">For example:</span></span>

**<span data-ttu-id="5e7d9-142">Server</span><span class="sxs-lookup"><span data-stu-id="5e7d9-142">Server</span></span>**

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

<span data-ttu-id="5e7d9-143">一旦进行 getAssertion 呼叫，Microsoft Edge 将显示 Windows Hello 提示，该提示将验证使用生物识别的用户的身份。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-143">Once the getAssertion call is made, Microsoft Edge will show the Windows Hello prompt, which will verify the identity of the user using biometrics.</span></span> <span data-ttu-id="5e7d9-144">验证用户后，该质询将在 TPM 中签名，并且承诺将返回一个断言对象，该对象包含用于发送到服务器的签名和其他元数据：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-144">After the user is verified, the challenge will be signed within the TPM and the promise will return with an assertion object that contains the signature and other metadata for you to send to the server:</span></span>

**<span data-ttu-id="5e7d9-145">客户端</span><span class="sxs-lookup"><span data-stu-id="5e7d9-145">Client</span></span>**

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

<span data-ttu-id="5e7d9-146">在服务器上收到断言后，你将需要验证签名以对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-146">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span> <span data-ttu-id="5e7d9-147">例如（在 NODE.JS 中）：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-147">For example (in Node.JS):</span></span>

**<span data-ttu-id="5e7d9-148">Server</span><span class="sxs-lookup"><span data-stu-id="5e7d9-148">Server</span></span>**

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

## <span data-ttu-id="5e7d9-149">Microsoft Edge 与规范之间的区别</span><span class="sxs-lookup"><span data-stu-id="5e7d9-149">Differences between Microsoft Edge and the spec</span></span>

> [!NOTE]
> <span data-ttu-id="5e7d9-150">在 Microsoft Edge 中尝试使用 Windows Hello 的 Web 身份验证 API 时，我们建议使用 polyfill 中所示的 "Webauthn"，以避免必须考虑此处列出的差异。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-150">When trying out the Web Authentication API with Windows Hello in Microsoft Edge, we recommend using the Webauthn.js polyfill as shown above to avoid having to account for the discrepancies listed here.</span></span> <span data-ttu-id="5e7d9-151">我们将为该规范的每个主要发布版本更新此 polyfill。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-151">We'll update this polyfill for every major published version of the specification.</span></span>


<span data-ttu-id="5e7d9-152">当前 Microsoft Edge 实现基于 Web 身份验证规范的早期草案，并且可能会在将来的内部版本中更改，并且在规范演变时也可能会发生更改。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-152">The current Microsoft Edge implementation is based on an earlier draft of the Web Authentication specification and is likely to change in future builds and as the spec evolves.</span></span> <span data-ttu-id="5e7d9-153">当前差异包括：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-153">The current differences include:</span></span>

- <span data-ttu-id="5e7d9-154">Microsoft Edge Api 为 MS 前缀。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-154">Microsoft Edge APIs are MS- prefixed.</span></span>
- <span data-ttu-id="5e7d9-155">Microsoft Edge 尚不支持诸如 USB 密钥或蓝牙设备之类的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-155">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span> <span data-ttu-id="5e7d9-156">当前 API 仅限于 TPM 中存储的嵌入凭据。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-156">The current API is limited to embedded credentials stored in the TPM.</span></span>
- <span data-ttu-id="5e7d9-157">当前登录的 Windows 用户帐户必须配置为至少支持 PIN，并且最好是指纹或指纹生物识别。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-157">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span> <span data-ttu-id="5e7d9-158">这是为了确保 Windows 可以对 TPM 的访问进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-158">This is to ensure that Windows can authenticate the access to the TPM.</span></span>
- <span data-ttu-id="5e7d9-159">Microsoft Edge 实现尚不支持帐户选取器体验。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-159">The Microsoft Edge implementation does not yet support the account picker experience.</span></span>
- <span data-ttu-id="5e7d9-160">调用 msCredentials 的第二个*筛选器*参数当前需要指定凭据 id。[getAssertion](https://msdn.microsoft.com/library/mt697640)。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-160">A second *filters* parameter specifying the credential id is currently required for calls to msCredentials.[getAssertion](https://msdn.microsoft.com/library/mt697640).</span></span> <span data-ttu-id="5e7d9-161">因此，你需要在客户端上的本地存储中存储凭据 ID 信息（在 indexDB 或 localStorage 中进行凭据时）。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-161">As such, you’ll need to store your credential ID information in local storage on the client, either in indexDB or localStorage when making your credential.</span></span> <span data-ttu-id="5e7d9-162">如果用户删除其浏览历史记录（包括本地存储），他们将需要重新注册才能在下次登录时使用 Windows Hello。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-162">If a user deletes their browsing history, including local storage, they will need to re-register to use Windows Hello the next time they log in.</span></span>
- <span data-ttu-id="5e7d9-163">Microsoft Edge 不支持当前 Web 身份验证规范草稿中的所有选项，如 "延长" 或 "超时"。</span><span class="sxs-lookup"><span data-stu-id="5e7d9-163">Microsoft Edge does not support all of the options in the current Web Authentication specification draft, such as extensions or timeouts.</span></span>

<span data-ttu-id="5e7d9-164">最后一点，以下 Web 身份验证规范定义中注明了特定的 Microsoft Edge 差异：</span><span class="sxs-lookup"><span data-stu-id="5e7d9-164">On that last point, the specific Microsoft Edge differences are noted in the following Web Authentication spec definitions:</span></span>

### <span data-ttu-id="5e7d9-165">W3C 规范</span><span class="sxs-lookup"><span data-stu-id="5e7d9-165">W3C spec</span></span>

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



## <span data-ttu-id="5e7d9-166">API 参考</span><span class="sxs-lookup"><span data-stu-id="5e7d9-166">API Reference</span></span>

[<span data-ttu-id="5e7d9-167">MSCredentials</span><span class="sxs-lookup"><span data-stu-id="5e7d9-167">MSCredentials</span></span>](https://msdn.microsoft.com/library/mt697639)

[<span data-ttu-id="5e7d9-168">makeCredential</span><span class="sxs-lookup"><span data-stu-id="5e7d9-168">makeCredential</span></span>](https://msdn.microsoft.com/library/mt697641)

[<span data-ttu-id="5e7d9-169">getAssertion</span><span class="sxs-lookup"><span data-stu-id="5e7d9-169">getAssertion</span></span>](https://msdn.microsoft.com/library/mt697640)

## <span data-ttu-id="5e7d9-170">演示</span><span class="sxs-lookup"><span data-stu-id="5e7d9-170">Demos</span></span>

[<span data-ttu-id="5e7d9-171">客户端和服务器代码示例</span><span class="sxs-lookup"><span data-stu-id="5e7d9-171">Client and server code samples</span></span>](https://github.com/adrianba/fido-snippets/)

[<span data-ttu-id="5e7d9-172">Webauthn .js polyfill</span><span class="sxs-lookup"><span data-stu-id="5e7d9-172">Webauthn.js polyfill</span></span>](https://github.com/adrianba/fido-snippets/blob/master/polyfill/webauthn.js)

[<span data-ttu-id="5e7d9-173">Windows Hello 测试驱动器演示</span><span class="sxs-lookup"><span data-stu-id="5e7d9-173">Windows Hello Test Drive demo</span></span>](https://testdrive-fido.azurewebsites.net/)

## <span data-ttu-id="5e7d9-174">书</span><span class="sxs-lookup"><span data-stu-id="5e7d9-174">Specification</span></span>

[<span data-ttu-id="5e7d9-175">Web 身份验证：用于访问范围内凭据的 Web API 1</span><span class="sxs-lookup"><span data-stu-id="5e7d9-175">Web Authentication: A Web API for accessing scoped credentials 1</span></span>](http://w3c.github.io/webauthn/)  
