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
# <span data-ttu-id="2a968-104">Web 身份验证和 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="2a968-104">Web Authentication and Windows Hello</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="2a968-105">Microsoft Edge [中的 Web 身份验证 API](https://w3c.github.io/webauthn) 允许 Web 应用程序使用 Windows [Hello 和](https://www.microsoft.com/windows/comprehensive-security) 外部 [FIDO2 设备](https://fidoalliance.org/fido2) 进行用户身份验证，以便你和你的用户可以避免密码管理的所有各种问题，包括密码来宾、网络网络处理和密钥日志记录的问题。</span><span class="sxs-lookup"><span data-stu-id="2a968-105">The [Web Authentication API](https://w3c.github.io/webauthn) in Microsoft Edge enables web applications to use [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) and [external FIDO2 devices](https://fidoalliance.org/fido2) for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and key-logging attacks.</span></span>  <span data-ttu-id="2a968-106">当前 Microsoft Edge 实现基于 Web 身份验证规范的待选建议。</span><span class="sxs-lookup"><span data-stu-id="2a968-106">The current Microsoft Edge implementation is based on the Candidate Recommendation of the Web Authentication specification.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2a968-107">本主题将介绍如何尝试使用 Microsoft Edge 的 Windows Hello 和 FIDO2 身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a968-107">This topic will show you how to try out Windows Hello and FIDO2 authentication with Microsoft Edge.</span></span>  

<span data-ttu-id="2a968-108">通过使用 Web 身份验证，服务器会将纯文本内容发送到浏览器。</span><span class="sxs-lookup"><span data-stu-id="2a968-108">Using Web Authentication, the server sends down a plain text challenge to the browser.</span></span>  <span data-ttu-id="2a968-109">一次 Microsoft Edge 能够通过 Windows Hello 或外部 FIDO2 设备验证用户，系统将使用之前为此用户预配置的私钥来签名该挑选，然后将签名重新发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="2a968-109">Once Microsoft Edge is able to verify the user through Windows Hello or an external FIDO2 device, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span>  <span data-ttu-id="2a968-110">如果服务器可以使用它对该用户所具有的公钥验证签名，并验证挑测是否正确，它可以安全地对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a968-110">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span>  <span data-ttu-id="2a968-111">使用 [非对称加](https://en.wikipedia.org/wiki/Public-key_cryptography) 密，公钥本身是无意义的，私钥不会共享。</span><span class="sxs-lookup"><span data-stu-id="2a968-111">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span>  <span data-ttu-id="2a968-112">而且，在启用了 TPM 的硬件的情况下，私钥永远无法从任何支持 TPM 的安全元素或现代系统中进行移动。</span><span class="sxs-lookup"><span data-stu-id="2a968-112">Furthermore, the private key can never be moved from secure elements or modern systems with TPM-enabled hardware.</span></span>  

<span data-ttu-id="2a968-113">可以使用 Web 身份验证 API 的基本步骤：</span><span class="sxs-lookup"><span data-stu-id="2a968-113">There are two basic steps to using the Web Authentication API:</span></span>  

1.  <span data-ttu-id="2a968-114">向用户注册</span><span class="sxs-lookup"><span data-stu-id="2a968-114">Register your user with</span></span> `create`  
1.  <span data-ttu-id="2a968-115">通过</span><span class="sxs-lookup"><span data-stu-id="2a968-115">Authenticate your user with</span></span> `get`  

<span data-ttu-id="2a968-116">下面的开发指南将引导你使用 [WebAuthn](https://github.com/MicrosoftEdge/webauthnsample)示例应用来完成此流程。</span><span class="sxs-lookup"><span data-stu-id="2a968-116">The following dev guide will walk you through this flow using the [WebAuthn Sample App](https://github.com/MicrosoftEdge/webauthnsample).</span></span>  

## <span data-ttu-id="2a968-117">注册用户</span><span class="sxs-lookup"><span data-stu-id="2a968-117">Register your user</span></span>  

<span data-ttu-id="2a968-118">作为标识提供程序，首先需要使用该方法为用户创建 Web 身份验证 `navigator.credentials.create` 凭据。</span><span class="sxs-lookup"><span data-stu-id="2a968-118">Acting as an identity provider, you will first need to create a Web Authentication credential for your user with the `navigator.credentials.create` method.</span></span>  <span data-ttu-id="2a968-119">在向服务器上的用户注册该凭据之前，您需要确认用户的身份。</span><span class="sxs-lookup"><span data-stu-id="2a968-119">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span>  <span data-ttu-id="2a968-120">这可以通过向用户发送电子邮件确认，或要求用户使用其传统登录方法来完成。</span><span class="sxs-lookup"><span data-stu-id="2a968-120">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>  

<span data-ttu-id="2a968-121">`create`该方法使用以下参数：</span><span class="sxs-lookup"><span data-stu-id="2a968-121">The `create` method takes the following parameters:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="2a968-122">保留方信息</span><span class="sxs-lookup"><span data-stu-id="2a968-122">relying party information</span></span>**  
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
      **<span data-ttu-id="2a968-123">用户帐户信息</span><span class="sxs-lookup"><span data-stu-id="2a968-123">user account information</span></span>**  
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
      **<span data-ttu-id="2a968-124">加密参数</span><span class="sxs-lookup"><span data-stu-id="2a968-124">crypto parameters</span></span>**  
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
      **<span data-ttu-id="2a968-125">验证器选择参数</span><span class="sxs-lookup"><span data-stu-id="2a968-125">authenticator selection parameters</span></span>**  
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
      **<span data-ttu-id="2a968-126">其他选项：</span><span class="sxs-lookup"><span data-stu-id="2a968-126">other options</span></span>**  
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

<span data-ttu-id="2a968-127">您可以 [使用凭据创建参数](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) 来配置要创建的凭据。</span><span class="sxs-lookup"><span data-stu-id="2a968-127">You can use [credential creation parameters](https://w3c.github.io/webauthn#dictdef-publickeycredentialcreationoptions) to configure the credential you want to create.</span></span>  <span data-ttu-id="2a968-128">特别要在外部 FIDO2 设备上，你可以选择通过将设置设置为或 `authenticatorAttachment` `platform` 通过将外部 FIDO2 设备上的漫游凭据设置为来创建 Windows Hello 凭据 `authenticatorAttachment` `cross-platform` 。</span><span class="sxs-lookup"><span data-stu-id="2a968-128">In particular, you can choose to create a Windows Hello credential by setting `authenticatorAttachment` to `platform`, or a roaming credential on an external FIDO2 device by setting `authenticatorAttachment` to `cross-platform`.</span></span>  

<span data-ttu-id="2a968-129">当你使用该方法时，Microsoft Edge 将先让用户验证其状态：扫描他们的面部或指 `create` 纹、进入 PIN 或在外部 FIDO2 设备上执行操作。</span><span class="sxs-lookup"><span data-stu-id="2a968-129">When you use the `create` method, Microsoft Edge will first ask the user to verify their presence by scanning their face or fingerprint, entering a PIN, or taking action on an external FIDO2 device.</span></span>  <span data-ttu-id="2a968-130">完成此步骤后，验证器将生成公钥对并存储私钥。</span><span class="sxs-lookup"><span data-stu-id="2a968-130">Once this step is completed the authenticator will generate a publicprivate key pair and store the private key.</span></span>  <span data-ttu-id="2a968-131">这些凭据按原源、每个帐户安全创建，并且无法提取，因为它们安全地存储到身份验证设备。</span><span class="sxs-lookup"><span data-stu-id="2a968-131">These credentials are created per origin, per account, and cannot be extracted because they are stored securely to the authentication device.</span></span>  

<span data-ttu-id="2a968-132">生成的 promise 返回 [表示新](https://w3c.github.io/webauthn#sctn-attestation) 凭据的证明对象。</span><span class="sxs-lookup"><span data-stu-id="2a968-132">The resulting promise returns an [attestation object](https://w3c.github.io/webauthn#sctn-attestation) representing the new credential.</span></span>  <span data-ttu-id="2a968-133">证明对象包含凭据的公钥。</span><span class="sxs-lookup"><span data-stu-id="2a968-133">The attestation object contains the public key for the credential.</span></span>  <span data-ttu-id="2a968-134">您将将该对象发送到服务器以验证将来的身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a968-134">You'll send this object to the server for validating future authentications.</span></span>  <span data-ttu-id="2a968-135">在返回服务器之前，你需要对原始数据进行编码。</span><span class="sxs-lookup"><span data-stu-id="2a968-135">Before sending back to the server, you'll need to base64-encode the raw data.</span></span>  

**<span data-ttu-id="2a968-136">客户端</span><span class="sxs-lookup"><span data-stu-id="2a968-136">Client</span></span>**  

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

<span data-ttu-id="2a968-137">然后，服务器应解码证明对象，执行验证步骤，为此凭据提取公钥，并将密钥存储在未来身份验证中。</span><span class="sxs-lookup"><span data-stu-id="2a968-137">The server should then decode the attestation object, perform verification steps, extract the public key for this credential, and store it for future authentications.</span></span>  <span data-ttu-id="2a968-138">有关步骤的详细列表，可以在 WebAuthn [规](https://w3c.github.io/webauthn#registering-a-new-credential) 范的凭据注册算法中找到。</span><span class="sxs-lookup"><span data-stu-id="2a968-138">A detailed list of steps can be found in the [credential registration algorithm](https://w3c.github.io/webauthn#registering-a-new-credential) in the WebAuthn specification.</span></span>  

**<span data-ttu-id="2a968-139">Server</span><span class="sxs-lookup"><span data-stu-id="2a968-139">Server</span></span>**  

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```  

## <span data-ttu-id="2a968-140">验证你的用户</span><span class="sxs-lookup"><span data-stu-id="2a968-140">Authenticate your user</span></span>  

<span data-ttu-id="2a968-141">在客户端上创建凭据后，用户下次尝试登录到该站点时，你可以提供 Web 身份验证凭据登录，而非通过调用密码来登录 `navigator.credentials.get` 。</span><span class="sxs-lookup"><span data-stu-id="2a968-141">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using their Web Authentication credential instead of a password with a call to `navigator.credentials.get`.</span></span>  

<span data-ttu-id="2a968-142">`get`该方法将这些挑包作为它的仅必需的参数。</span><span class="sxs-lookup"><span data-stu-id="2a968-142">The `get` method takes the challenge as its only required parameter.</span></span>  <span data-ttu-id="2a968-143">挑质问题是服务器将向下发送到客户端以便使用用户的私钥进行登录的不理确结果。</span><span class="sxs-lookup"><span data-stu-id="2a968-143">The challenge is an opaque sequence of bytes that the server will send down to a client to sign with the user's private key.</span></span>  <span data-ttu-id="2a968-144">例如：</span><span class="sxs-lookup"><span data-stu-id="2a968-144">For example:</span></span>  

**<span data-ttu-id="2a968-145">Server</span><span class="sxs-lookup"><span data-stu-id="2a968-145">Server</span></span>**  

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```  

<span data-ttu-id="2a968-146">从服务器检索挑质后，你将调用 GET API 以及 [凭据请求选项](https://w3c.github.io/webauthn#credentialrequestoptions-extension)。</span><span class="sxs-lookup"><span data-stu-id="2a968-146">After retrieving a challenge from the server, you'll call the get API along with [credential request options](https://w3c.github.io/webauthn#credentialrequestoptions-extension).</span></span>  <span data-ttu-id="2a968-147">Microsoft Edge 将显示一条提示，这将验证使用 Windows Hello 或外部 FIDO2 设备的用户的身份。</span><span class="sxs-lookup"><span data-stu-id="2a968-147">Microsoft Edge will show a prompt, which will verify the identity of the user using Windows Hello or an external FIDO2 device.</span></span>  <span data-ttu-id="2a968-148">在用户经过验证后，问题将在 TPM 或 FIDO2 设备上进行登录，承诺将返回 [包含](https://w3c.github.io/webauthn#authenticatorassertionresponse) 签名及其他元数据的断言对象供您发送给服务器。</span><span class="sxs-lookup"><span data-stu-id="2a968-148">After the user is verified, the challenge will be signed within the TPM or FIDO2 device and the promise will return with an [assertion object](https://w3c.github.io/webauthn#authenticatorassertionresponse) that contains the signature and other metadata for you to send to the server.</span></span>  

**<span data-ttu-id="2a968-149">客户端</span><span class="sxs-lookup"><span data-stu-id="2a968-149">Client</span></span>**  

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

<span data-ttu-id="2a968-150">在服务器上收到断断后，你将需要验证该签名以对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="2a968-150">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span>  <span data-ttu-id="2a968-151">下面是一些示例代码。</span><span class="sxs-lookup"><span data-stu-id="2a968-151">The following is some sample code.</span></span>  <span data-ttu-id="2a968-152">有关步骤的详细列表可以在 WebAuthn [规](https://w3c.github.io/webauthn#verifying-assertion) 范中的断包验证算法中找到。</span><span class="sxs-lookup"><span data-stu-id="2a968-152">A detailed list of steps can be found in the [assertion verification algorithm](https://w3c.github.io/webauthn#verifying-assertion) in the WebAuthn specification.</span></span>  

**<span data-ttu-id="2a968-153">Server</span><span class="sxs-lookup"><span data-stu-id="2a968-153">Server</span></span>**  

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

## <span data-ttu-id="2a968-154">实现说明</span><span class="sxs-lookup"><span data-stu-id="2a968-154">Implementation notes</span></span>  

### <span data-ttu-id="2a968-155">支持的平台</span><span class="sxs-lookup"><span data-stu-id="2a968-155">Supported platforms</span></span>  

*   <span data-ttu-id="2a968-156">从 Microsoft Edge 开始使用 Candidate 建议版本的 Web 身份验证 API，此版本从 Microsoft Edge 开始使用，该版本号为 18 \ (Windows Insider Preview 版本 17713 或更高版本\) 。</span><span class="sxs-lookup"><span data-stu-id="2a968-156">The Candidate Recommendation version of the Web Authentication API can be used from Microsoft Edge beginning with EdgeHTML 18 \(Windows Insider Preview version 17713 or newer\).</span></span>  
*   <span data-ttu-id="2a968-157">已 [删除前缀、Web](https://blogs.windows.com/msedgedev/2016/04/12) 身份验证 API 预览版本，且不再可用。</span><span class="sxs-lookup"><span data-stu-id="2a968-157">The [prefixed, preview version](https://blogs.windows.com/msedgedev/2016/04/12) of the Web Authentication API has been removed and is no longer available.</span></span>  
*   <span data-ttu-id="2a968-158">Web 身份验证 API 尚不适用于 UWP 应用和 PWA。</span><span class="sxs-lookup"><span data-stu-id="2a968-158">The Web Authentication API is not yet available to UWP apps and PWAs.</span></span>  
*   <span data-ttu-id="2a968-159">Internet Explorer验证 API 不支持 Web 身份验证 API。</span><span class="sxs-lookup"><span data-stu-id="2a968-159">Internet Explorer does not support the Web Authentication API.</span></span>  

### <span data-ttu-id="2a968-160">支持的身份验证器</span><span class="sxs-lookup"><span data-stu-id="2a968-160">Supported authenticators</span></span>  

<span data-ttu-id="2a968-161">使用 Microsoft Edge 中的 Web 身份验证 API，你可使用以下技术来对用户进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="2a968-161">With the Web Authentication API in Microsoft Edge, you can authenticate users with the following technologies:</span></span>  

*   <span data-ttu-id="2a968-162">**Windows Hello**  通过面板、指纹或 PIN 启用无密码身份验证</span><span class="sxs-lookup"><span data-stu-id="2a968-162">**Windows Hello**  Enables passwordless on-device authentication with  face, fingerprint, or PIN</span></span>  
*   <span data-ttu-id="2a968-163">**FIDO2**  启用使用可移动设备以及指纹或 PIN 进行无密码漫游身份验证</span><span class="sxs-lookup"><span data-stu-id="2a968-163">**FIDO2**  Enables passwordless roaming authentication with a removable device and a fingerprint or PIN</span></span>  
*   <span data-ttu-id="2a968-164">**U2F**  为尚未准备移至密码模型的网站启用强第二个因素身份验证</span><span class="sxs-lookup"><span data-stu-id="2a968-164">**U2F**  Enables strong second factor authentication for websites that are not ready to move to a passwordless model</span></span>  

### <span data-ttu-id="2a968-165">Windows Hello 的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="2a968-165">Special considerations for Windows Hello</span></span>  

<span data-ttu-id="2a968-166">使用 Windows Hello 验证器时需要注意的一些事项：</span><span class="sxs-lookup"><span data-stu-id="2a968-166">A few things to note when using the Windows Hello authenticator:</span></span>  

*   <span data-ttu-id="2a968-167">你可以通过调用 API 检测电脑是否支持 Windows `isUserVerifyingPlatformAuthenticatorAvailable` Hello。</span><span class="sxs-lookup"><span data-stu-id="2a968-167">You can detect if Windows Hello is available on a PC by calling the `isUserVerifyingPlatformAuthenticatorAvailable` API.</span></span>  <span data-ttu-id="2a968-168">请在此处了解有关此 API [的详细信息](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable)。</span><span class="sxs-lookup"><span data-stu-id="2a968-168">Learn more about this API [here](https://www.w3.org/TR/webauthn#isUserVerifyingPlatformAuthenticatorAvailable).</span></span>  
*   <span data-ttu-id="2a968-169">在为 Windows Hello 创建凭据时，你应设置为 `authenticatorAttachment` `platform` 提供最佳的用户体验。</span><span class="sxs-lookup"><span data-stu-id="2a968-169">When creating a credential for Windows Hello, you should set `authenticatorAttachment` to `platform` for the best user experience.</span></span>
*   <span data-ttu-id="2a968-170">Windows Hello 仅支持 RS256 \ (alg -257\) 作为其公钥算法。</span><span class="sxs-lookup"><span data-stu-id="2a968-170">Windows Hello only supports RS256 \(alg -257\) as its public key algorithm.</span></span>  <span data-ttu-id="2a968-171">在创建凭据时，请务必指定此算法。</span><span class="sxs-lookup"><span data-stu-id="2a968-171">Be sure to specify this algorithm when creating a credential.</span></span>  
*   <span data-ttu-id="2a968-172">若要接收 [TPM 证明语句，请在](https://w3c.github.io/webauthn#tpm-attestation)调用 API 时将证明设置为"直接 `create` "。</span><span class="sxs-lookup"><span data-stu-id="2a968-172">To receive a [TPM attestation statement](https://w3c.github.io/webauthn#tpm-attestation), set attestation to "direct" when calling the `create` API.</span></span>  <span data-ttu-id="2a968-173">TPM 证明最好是实现最佳工作。</span><span class="sxs-lookup"><span data-stu-id="2a968-173">TPM attestation is a best effort.</span></span>  <span data-ttu-id="2a968-174">仅具有 TPM 2.0 的电脑将返回 TPM 证明，因此证明过程可能由于多种原因而失败。</span><span class="sxs-lookup"><span data-stu-id="2a968-174">Only PCs with TPM 2.0 will return a TPM attestation statement, and the attestation process could fail for a variety of reasons.</span></span>  
*   <span data-ttu-id="2a968-175">Windows Hello 使用多种方法来保护用户凭据。</span><span class="sxs-lookup"><span data-stu-id="2a968-175">Windows Hello employs a variety of ways to protect user credentials.</span></span>  <span data-ttu-id="2a968-176">你可以通过在凭据创建时返回的同步对象中使用 [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) 字段来检查是否使用了哪种方法来保护凭据。</span><span class="sxs-lookup"><span data-stu-id="2a968-176">You can check which method has been used to protect a credential by consuming the [AAGUID](https://w3c.github.io/webauthn#sec-attested-credential-data) field in the attestation object returned at credential creation.</span></span>  <span data-ttu-id="2a968-177">下面是 Windows Hello 可能返回的 AAGUID 列表：</span><span class="sxs-lookup"><span data-stu-id="2a968-177">The following is the list of AAGUIDs that Windows Hello may return:</span></span>   
    *   <span data-ttu-id="2a968-178">软件支持的身份验证器</span><span class="sxs-lookup"><span data-stu-id="2a968-178">Software backed authenticators</span></span>  
        *   <span data-ttu-id="2a968-179">Windows Hello 软件验证器：</span><span class="sxs-lookup"><span data-stu-id="2a968-179">Windows Hello software authenticator:</span></span>  `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`  
        *   <span data-ttu-id="2a968-180">Windows Hello VBS 软件验证器：</span><span class="sxs-lookup"><span data-stu-id="2a968-180">Windows Hello VBS software authenticator:</span></span>  `6E96969E-A5CF-4AAD-9B56-305FE6C82795`  
    *   <span data-ttu-id="2a968-181">受信任的平台模块 \ (TPM\支持) 验证器</span><span class="sxs-lookup"><span data-stu-id="2a968-181">Trusted Platform Module \(TPM\) backed authenticators</span></span>  
        *   <span data-ttu-id="2a968-182">Windows Hello 硬件验证器：</span><span class="sxs-lookup"><span data-stu-id="2a968-182">Windows Hello hardware authenticator:</span></span>  `08987058-CADC-4B81-B6E1-30DE50DCBE96`  
        *   <span data-ttu-id="2a968-183">Windows Hello VBS 硬件身份验证器：</span><span class="sxs-lookup"><span data-stu-id="2a968-183">Windows Hello VBS hardware authenticator:</span></span>  `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`  

### <span data-ttu-id="2a968-184">API 平面</span><span class="sxs-lookup"><span data-stu-id="2a968-184">API surface</span></span>  

*   <span data-ttu-id="2a968-185">Microsoft Edge 已完全实现内采用的内部 Web 身份验证规范的全部推荐版本。</span><span class="sxs-lookup"><span data-stu-id="2a968-185">Microsoft Edge has a complete implementation of the Candidate Recommendation version of the core Web Authentication specification.</span></span>  
*   <span data-ttu-id="2a968-186">支持 [AppID 扩展](https://w3c.github.io/webauthn#sctn-appid-extension) 。</span><span class="sxs-lookup"><span data-stu-id="2a968-186">The [AppID extension](https://w3c.github.io/webauthn#sctn-appid-extension) is supported.</span></span>  
*   <span data-ttu-id="2a968-187">不支持其他扩展名。</span><span class="sxs-lookup"><span data-stu-id="2a968-187">No other extensions are supported.</span></span>  

## <span data-ttu-id="2a968-188">演示</span><span class="sxs-lookup"><span data-stu-id="2a968-188">Demos</span></span>  

[<span data-ttu-id="2a968-189">客户端和服务器代码示例</span><span class="sxs-lookup"><span data-stu-id="2a968-189">Client and server code sample</span></span>](https://github.com/MicrosoftEdge/webauthnsample)  

[<span data-ttu-id="2a968-190">Windows Hello 测试驱动器演示</span><span class="sxs-lookup"><span data-stu-id="2a968-190">Windows Hello Test Drive demo</span></span>](https://webauthnsample.azurewebsites.net)  

## <span data-ttu-id="2a968-191">规范</span><span class="sxs-lookup"><span data-stu-id="2a968-191">Specification</span></span>  

[<span data-ttu-id="2a968-192">Web 身份验证：用于访问公钥凭据的 API</span><span class="sxs-lookup"><span data-stu-id="2a968-192">Web Authentication: An API for accessing Public Key Credentials</span></span>](http://w3c.github.io/webauthn)  
