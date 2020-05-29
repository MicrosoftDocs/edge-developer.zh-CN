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
# <span data-ttu-id="9cadc-104">Web 身份验证和 Windows Hello</span><span class="sxs-lookup"><span data-stu-id="9cadc-104">Web Authentication and Windows Hello</span></span>

<span data-ttu-id="9cadc-105">Microsoft Edge 中的[Web 身份验证 API](https://w3c.github.io/webauthn)使 web 应用程序可以使用[Windows HELLO](https://go.microsoft.com/fwlink/p/?LinkID=624961)和[外部 FIDO2 设备](https://fidoalliance.org/fido2)进行用户身份验证，以便你和你的用户可以避免密码管理的所有麻烦和风险，包括密码猜测、网络钓鱼和按键日志记录攻击。</span><span class="sxs-lookup"><span data-stu-id="9cadc-105">The [Web Authentication API](https://w3c.github.io/webauthn) in Microsoft Edge enables web applications to use [Windows Hello](https://go.microsoft.com/fwlink/p/?LinkID=624961) and [external FIDO2 devices](https://fidoalliance.org/fido2) for user authentication so that you and your users can avoid all the hassles and risks of password management, including password guessing, phishing, and key-logging attacks.</span></span> <span data-ttu-id="9cadc-106">当前 Microsoft Edge 实现基于 Web 身份验证规范的候选建议。</span><span class="sxs-lookup"><span data-stu-id="9cadc-106">The current Microsoft Edge implementation is based on the Candidate Recommendation of the Web Authentication specification.</span></span> **<span data-ttu-id="9cadc-107">本主题将介绍如何通过 Microsoft Edge 试用 Windows Hello 和 FIDO2 身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cadc-107">This topic will show you how to try out Windows Hello and FIDO2 authentication with Microsoft Edge.</span></span>**

<span data-ttu-id="9cadc-108">使用 Web 身份验证，服务器将纯文本质询发送到浏览器。</span><span class="sxs-lookup"><span data-stu-id="9cadc-108">Using Web Authentication, the server sends down a plain text challenge to the browser.</span></span> <span data-ttu-id="9cadc-109">一旦 Microsoft Edge 能够通过 Windows Hello 或外部 FIDO2 设备验证用户，系统将使用以前为此用户预配的私钥对质询进行签名，并将签名重新发送到服务器。</span><span class="sxs-lookup"><span data-stu-id="9cadc-109">Once Microsoft Edge is able to verify the user through Windows Hello or an external FIDO2 device, the system will sign the challenge with a private key previously provisioned for this user and send the signature back to the server.</span></span> <span data-ttu-id="9cadc-110">如果服务器可以使用其针对该用户的公钥验证签名并验证质询是否正确，则可以安全地验证用户身份。</span><span class="sxs-lookup"><span data-stu-id="9cadc-110">If the server can validate the signature using the public key it has for that user and verify the challenge is correct, it can authenticate the user securely.</span></span> <span data-ttu-id="9cadc-111">利用[非对称加密](https://en.wikipedia.org/wiki/Public-key_cryptography)（如这样），公钥本身毫无意义，私钥永远不会共享。</span><span class="sxs-lookup"><span data-stu-id="9cadc-111">With [asymmetric cryptography](https://en.wikipedia.org/wiki/Public-key_cryptography) such as this, the public key is meaningless on its own and the private key is never shared.</span></span> <span data-ttu-id="9cadc-112">此外，私钥永远不能通过启用 TPM 的硬件从安全元素或新式系统中进行移动。</span><span class="sxs-lookup"><span data-stu-id="9cadc-112">Furthermore, the private key can never be moved from secure elements or modern systems with TPM-enabled hardware.</span></span>

<span data-ttu-id="9cadc-113">使用 Web 身份验证 API 有两个基本步骤：</span><span class="sxs-lookup"><span data-stu-id="9cadc-113">There are two basic steps to using the Web Authentication API:</span></span>

**<span data-ttu-id="9cadc-114">1. 向注册用户</span><span class="sxs-lookup"><span data-stu-id="9cadc-114">1. Register your user with</span></span> `create`**

**<span data-ttu-id="9cadc-115">2. 通过验证您的用户</span><span class="sxs-lookup"><span data-stu-id="9cadc-115">2. Authenticate your user with</span></span> `get`**

<span data-ttu-id="9cadc-116">下面的开发人员指南将通过使用[WebAuthn 示例应用](https://github.com/MicrosoftEdge/webauthnsample)指导你完成此流程。</span><span class="sxs-lookup"><span data-stu-id="9cadc-116">The following dev guide will walk you through this flow using the [WebAuthn Sample App](https://github.com/MicrosoftEdge/webauthnsample).</span></span>

## <span data-ttu-id="9cadc-117">注册您的用户</span><span class="sxs-lookup"><span data-stu-id="9cadc-117">Register your user</span></span>

<span data-ttu-id="9cadc-118">作为*标识提供者*，你首先需要使用导航器为你的用户创建 Web 身份验证凭据。**create**方法。</span><span class="sxs-lookup"><span data-stu-id="9cadc-118">Acting as an *identity provider*, you will first need to create a Web Authentication credential for your user with the navigator.credentials.**create** method.</span></span> <span data-ttu-id="9cadc-119">将该凭据注册到服务器上的用户之前，您需要确认用户的身份。</span><span class="sxs-lookup"><span data-stu-id="9cadc-119">Before you register that credential to the user on your server, you will need to confirm the identity of the user.</span></span> <span data-ttu-id="9cadc-120">可通过向用户发送电子邮件确认或要求他们使用传统的登录方法来完成此操作。</span><span class="sxs-lookup"><span data-stu-id="9cadc-120">This can be done by sending the user an email confirmation or asking them to use their traditional login method.</span></span>


<span data-ttu-id="9cadc-121">该 `create` 方法采用以下参数：</span><span class="sxs-lookup"><span data-stu-id="9cadc-121">The `create` method takes the following parameters:</span></span>

 - **<span data-ttu-id="9cadc-122">信赖方信息</span><span class="sxs-lookup"><span data-stu-id="9cadc-122">relying party information</span></span>**

```javascript
    rp: {
        name: "WebAuthn Sample App",
        icon: "https://example.com/rpIcon.png"
    },
```

 - **<span data-ttu-id="9cadc-123">用户帐户信息</span><span class="sxs-lookup"><span data-stu-id="9cadc-123">user account information</span></span>**

```javascript
    user: {
        id: stringToArrayBuffer("some.user.id"),
        name: "bob.smith@contoso.com",
        displayName: "Bob Smith",
        icon: "https://example.com/userIcon.png"
    },
```

 - **<span data-ttu-id="9cadc-124">加密参数</span><span class="sxs-lookup"><span data-stu-id="9cadc-124">crypto parameters</span></span>**

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

 - **<span data-ttu-id="9cadc-125">身份验证器选择参数</span><span class="sxs-lookup"><span data-stu-id="9cadc-125">authenticator selection parameters</span></span>**

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

- **<span data-ttu-id="9cadc-126">其他选项</span><span class="sxs-lookup"><span data-stu-id="9cadc-126">other options</span></span>**

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

<span data-ttu-id="9cadc-127">你可以使用[凭据创建参数](https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions)配置要创建的凭据。</span><span class="sxs-lookup"><span data-stu-id="9cadc-127">You can use [credential creation parameters](https://w3c.github.io/webauthn/#dictdef-publickeycredentialcreationoptions) to configure the credential you want to create.</span></span> <span data-ttu-id="9cadc-128">特别是，你可以 `authenticatorAttachment` `platform` 通过设置为来选择在外部 FIDO2 设备上通过设置 to 或漫游凭据创建 Windows Hello 凭据 `authenticatorAttachment` `cross-platform` 。</span><span class="sxs-lookup"><span data-stu-id="9cadc-128">In particular, you can choose to create a Windows Hello credential by setting `authenticatorAttachment` to `platform`, or a roaming credential on an external FIDO2 device by setting `authenticatorAttachment` to `cross-platform`.</span></span> 

<span data-ttu-id="9cadc-129">使用此方法时 `create` ，Microsoft Edge 将首先要求用户通过扫描其面孔或指纹、输入 PIN 或在外部 FIDO2 设备上执行操作来验证其状态。</span><span class="sxs-lookup"><span data-stu-id="9cadc-129">When you use the `create` method, Microsoft Edge will first ask the user to verify their presence by scanning their face or fingerprint, entering a PIN, or taking action on an external FIDO2 device.</span></span> <span data-ttu-id="9cadc-130">完成此步骤后，身份验证器将生成一个公用/专用密钥对并存储私钥。</span><span class="sxs-lookup"><span data-stu-id="9cadc-130">Once this step is completed the authenticator will generate a public/private key pair and store the private key.</span></span> <span data-ttu-id="9cadc-131">这些凭据根据每个帐户创建，并且无法提取，因为它们被安全地存储到身份验证设备。</span><span class="sxs-lookup"><span data-stu-id="9cadc-131">These credentials are created per origin, per account, and cannot be extracted because they are stored securely to the authentication device.</span></span> 

<span data-ttu-id="9cadc-132">结果承诺返回表示新凭据的[证明对象](https://w3c.github.io/webauthn/#sctn-attestation)。</span><span class="sxs-lookup"><span data-stu-id="9cadc-132">The resulting promise returns an [attestation object](https://w3c.github.io/webauthn/#sctn-attestation) representing the new credential.</span></span> <span data-ttu-id="9cadc-133">证明对象包含凭据的公钥。</span><span class="sxs-lookup"><span data-stu-id="9cadc-133">The attestation object contains the public key for the credential.</span></span> <span data-ttu-id="9cadc-134">将此对象发送到服务器，以便验证未来身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cadc-134">You'll send this object to the server for validating future authentications.</span></span> <span data-ttu-id="9cadc-135">将原始数据发送回服务器之前，需要对原始数据进行 base64 编码。</span><span class="sxs-lookup"><span data-stu-id="9cadc-135">Before sending back to the server, you'll need to base64-encode the raw data.</span></span>

**<span data-ttu-id="9cadc-136">客户端</span><span class="sxs-lookup"><span data-stu-id="9cadc-136">Client</span></span>**

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

<span data-ttu-id="9cadc-137">然后，服务器应解码证明对象，执行验证步骤，提取此凭据的公钥，然后将其存储下来以供将来身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cadc-137">The server should then decode the attestation object, perform verification steps, extract the public key for this credential, and store it for future authentications.</span></span> <span data-ttu-id="9cadc-138">可在 WebAuthn 规范的[凭据注册算法](https://w3c.github.io/webauthn/#registering-a-new-credential)中找到详细步骤列表。</span><span class="sxs-lookup"><span data-stu-id="9cadc-138">A detailed list of steps can be found in the [credential registration algorithm](https://w3c.github.io/webauthn/#registering-a-new-credential) in the WebAuthn specification.</span></span>

**<span data-ttu-id="9cadc-139">Server</span><span class="sxs-lookup"><span data-stu-id="9cadc-139">Server</span></span>**

```javascript
    attestationObject = cbor.decodeFirstSync(Buffer.from(attestation.attestationObject, 'base64'));
    authenticatorData = parseAuthenticatorData(attestationObject.authData);
    var credential = await storage.Credentials.create({
        id: authenticatorData.attestedCredentialData.credentialId.toString('base64'),
        publicKeyJwk: authenticatorData.attestedCredentialData.publicKeyJwk,
        signCount: authenticatorData.signCount
    });
```

## <span data-ttu-id="9cadc-140">验证用户身份</span><span class="sxs-lookup"><span data-stu-id="9cadc-140">Authenticate your user</span></span>

<span data-ttu-id="9cadc-141">在客户端上创建凭据后，下次用户尝试登录到该网站时，您可以使用其 Web 身份验证凭据（而不是使用 "导航器" 调用的密码）对其进行签名。**获取**。</span><span class="sxs-lookup"><span data-stu-id="9cadc-141">Once the credential is created on the client, the next time the user attempts to log into the site you can offer to sign them in using their Web Authentication credential instead of a password with a call to navigator.credentials.**get**.</span></span>

<span data-ttu-id="9cadc-142">该 `get` 方法将*质询*视为唯一的必需参数。</span><span class="sxs-lookup"><span data-stu-id="9cadc-142">The `get` method takes the *challenge* as its only required parameter.</span></span> <span data-ttu-id="9cadc-143">质询是一种不透明的字节序列，服务器将向客户端发送该字节序列，以使用用户的私钥进行签名。</span><span class="sxs-lookup"><span data-stu-id="9cadc-143">The challenge is an opaque sequence of bytes that the server will send down to a client to sign with the user's private key.</span></span> <span data-ttu-id="9cadc-144">例如：</span><span class="sxs-lookup"><span data-stu-id="9cadc-144">For example:</span></span>

**<span data-ttu-id="9cadc-145">Server</span><span class="sxs-lookup"><span data-stu-id="9cadc-145">Server</span></span>**

```javascript
    var jwt = require('jsonwebtoken');
    var jwt_secret = "defaultsecret";
    fido.getChallenge = () => {
        return jwt.sign({}, jwt_secret, {
            expiresIn: 120 * 1000
        });
    };
```

<span data-ttu-id="9cadc-146">从服务器检索质询后，将调用 get API 以及[凭据请求选项](https://w3c.github.io/webauthn/#credentialrequestoptions-extension)。</span><span class="sxs-lookup"><span data-stu-id="9cadc-146">After retrieving a challenge from the server, you'll call the get API along with [credential request options](https://w3c.github.io/webauthn/#credentialrequestoptions-extension).</span></span> <span data-ttu-id="9cadc-147">Microsoft Edge 将显示一个提示，它将验证使用 Windows Hello 或外部 FIDO2 设备的用户的身份。</span><span class="sxs-lookup"><span data-stu-id="9cadc-147">Microsoft Edge will show a prompt, which will verify the identity of the user using Windows Hello or an external FIDO2 device.</span></span> <span data-ttu-id="9cadc-148">验证用户后，质询将在 TPM 或 FIDO2 设备中签名，并且承诺将返回一个[断言对象](https://w3c.github.io/webauthn/#authenticatorassertionresponse)，该对象包含用于发送到服务器的签名和其他元数据。</span><span class="sxs-lookup"><span data-stu-id="9cadc-148">After the user is verified, the challenge will be signed within the TPM or FIDO2 device and the promise will return with an [assertion object](https://w3c.github.io/webauthn/#authenticatorassertionresponse) that contains the signature and other metadata for you to send to the server.</span></span>

**<span data-ttu-id="9cadc-149">客户端</span><span class="sxs-lookup"><span data-stu-id="9cadc-149">Client</span></span>**

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

<span data-ttu-id="9cadc-150">在服务器上收到断言后，你将需要验证签名以对用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="9cadc-150">Once you receive the assertion on the server, you will need to validate the signature to authenticate the user.</span></span> <span data-ttu-id="9cadc-151">下面是一些示例代码。</span><span class="sxs-lookup"><span data-stu-id="9cadc-151">The following is some sample code.</span></span>  <span data-ttu-id="9cadc-152">可在 WebAuthn 规范的[断言验证算法](https://w3c.github.io/webauthn/#verifying-assertion)中找到详细步骤列表。</span><span class="sxs-lookup"><span data-stu-id="9cadc-152">A detailed list of steps can be found in the [assertion verification algorithm](https://w3c.github.io/webauthn/#verifying-assertion) in the WebAuthn specification.</span></span>

**<span data-ttu-id="9cadc-153">Server</span><span class="sxs-lookup"><span data-stu-id="9cadc-153">Server</span></span>**

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

## <span data-ttu-id="9cadc-154">实现说明</span><span class="sxs-lookup"><span data-stu-id="9cadc-154">Implementation notes</span></span>

### <span data-ttu-id="9cadc-155">支持的平台</span><span class="sxs-lookup"><span data-stu-id="9cadc-155">Supported platforms</span></span>
- <span data-ttu-id="9cadc-156">Web 身份验证 API 的候选推荐版本可从 Microsoft Edge 中使用 EdgeHTML 18 （Windows 预览体验计划预览版17713及更高版本）。</span><span class="sxs-lookup"><span data-stu-id="9cadc-156">The Candidate Recommendation version of the Web Authentication API can be used from Microsoft Edge beginning with EdgeHTML 18 (Windows Insider Preview version 17713 and up).</span></span>
- <span data-ttu-id="9cadc-157">"已删除" 和 "Web 身份验证 API" 的[前缀版本](https://blogs.windows.com/msedgedev/2016/04/12/a-world-without-passwords-windows-hello-in-microsoft-edge/)已被删除，不再可用。</span><span class="sxs-lookup"><span data-stu-id="9cadc-157">The [prefixed, preview version](https://blogs.windows.com/msedgedev/2016/04/12/a-world-without-passwords-windows-hello-in-microsoft-edge/) of the Web Authentication API has been removed and is no longer available.</span></span>
- <span data-ttu-id="9cadc-158">Web 身份验证 API 尚不可用于 UWP 应用和 PWAs。</span><span class="sxs-lookup"><span data-stu-id="9cadc-158">The Web Authentication API is not yet available to UWP apps and PWAs.</span></span>
- <span data-ttu-id="9cadc-159">Internet Explorer 不支持 Web 身份验证 API。</span><span class="sxs-lookup"><span data-stu-id="9cadc-159">Internet Explorer does not support the Web Authentication API.</span></span> 

### <span data-ttu-id="9cadc-160">支持的 authenticators</span><span class="sxs-lookup"><span data-stu-id="9cadc-160">Supported authenticators</span></span>
<span data-ttu-id="9cadc-161">通过 Microsoft Edge 中的 Web 身份验证 API，你可以通过以下技术对用户进行身份验证：</span><span class="sxs-lookup"><span data-stu-id="9cadc-161">With the Web Authentication API in Microsoft Edge, you can authenticate users with the following technologies:</span></span>
- <span data-ttu-id="9cadc-162">**Windows Hello**，通过面孔、指纹或 PIN 启用 passwordless 设备身份验证</span><span class="sxs-lookup"><span data-stu-id="9cadc-162">**Windows Hello**, enabling passwordless on-device authentication with  face, fingerprint, or PIN</span></span>
- <span data-ttu-id="9cadc-163">**FIDO2**，通过可移动设备和指纹或 PIN 启用 passwordless 漫游身份验证</span><span class="sxs-lookup"><span data-stu-id="9cadc-163">**FIDO2**, enabling passwordless roaming authentication with a removable device and a fingerprint or PIN</span></span>
- <span data-ttu-id="9cadc-164">**U2F**，为尚未准备好移动到 passwordless 模型的网站启用强烈的第二因素身份验证</span><span class="sxs-lookup"><span data-stu-id="9cadc-164">**U2F**, enabling strong second factor authentication for websites that are not ready to move to a passwordless model</span></span>

### <span data-ttu-id="9cadc-165">Windows Hello 的特殊注意事项</span><span class="sxs-lookup"><span data-stu-id="9cadc-165">Special considerations for Windows Hello</span></span> 
<span data-ttu-id="9cadc-166">使用 Windows Hello 身份验证器时需要注意的一些事项：</span><span class="sxs-lookup"><span data-stu-id="9cadc-166">A few things to note when using the Windows Hello authenticator:</span></span>
- <span data-ttu-id="9cadc-167">你可以通过调用 API 来检测电脑上是否可以使用 Windows Hello `isUserVerifyingPlatformAuthenticatorAvailable` 。</span><span class="sxs-lookup"><span data-stu-id="9cadc-167">You can detect if Windows Hello is available on a PC by calling the `isUserVerifyingPlatformAuthenticatorAvailable` API.</span></span> <span data-ttu-id="9cadc-168">[在此处](https://www.w3.org/TR/webauthn/#isUserVerifyingPlatformAuthenticatorAvailable)了解有关此 API 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9cadc-168">Learn more about this API [here](https://www.w3.org/TR/webauthn/#isUserVerifyingPlatformAuthenticatorAvailable).</span></span>
- <span data-ttu-id="9cadc-169">创建适用于 Windows Hello 的凭据时，应将设置 `authenticatorAttachment` 为以 `platform` 获得最佳用户体验。</span><span class="sxs-lookup"><span data-stu-id="9cadc-169">When creating a credential for Windows Hello, you should set `authenticatorAttachment` to `platform` for the best user experience.</span></span>
- <span data-ttu-id="9cadc-170">Windows Hello 仅支持 RS256 （alg-257）作为其公钥算法。</span><span class="sxs-lookup"><span data-stu-id="9cadc-170">Windows Hello only supports RS256 (alg -257) as its public key algorithm.</span></span> <span data-ttu-id="9cadc-171">请确保在创建凭据时指定此算法。</span><span class="sxs-lookup"><span data-stu-id="9cadc-171">Be sure to specify this algorithm when creating a credential.</span></span>
- <span data-ttu-id="9cadc-172">若要接收[TPM 证明语句](https://w3c.github.io/webauthn/#tpm-attestation)，请在调用 API 时将证明设置为 "direct" `create` 。</span><span class="sxs-lookup"><span data-stu-id="9cadc-172">To receive a [TPM attestation statement](https://w3c.github.io/webauthn/#tpm-attestation), set attestation to "direct" when calling the `create` API.</span></span> <span data-ttu-id="9cadc-173">TPM 证明是一种最大努力。</span><span class="sxs-lookup"><span data-stu-id="9cadc-173">TPM attestation is a best effort.</span></span> <span data-ttu-id="9cadc-174">只有使用 TPM 2.0 的电脑才会返回 TPM 证明声明，并且证明过程可能会因各种原因而失败。</span><span class="sxs-lookup"><span data-stu-id="9cadc-174">Only PCs with TPM 2.0 will return a TPM attestation statement, and the attestation process could fail for a variety of reasons.</span></span>
- <span data-ttu-id="9cadc-175">Windows Hello 采用多种方法来保护用户凭据。</span><span class="sxs-lookup"><span data-stu-id="9cadc-175">Windows Hello employs a variety of ways to protect user credentials.</span></span> <span data-ttu-id="9cadc-176">你可以通过在凭据创建时使用证明对象中的[AAGUID](https://w3c.github.io/webauthn/#sec-attested-credential-data)字段来检查用于保护凭据的方法。</span><span class="sxs-lookup"><span data-stu-id="9cadc-176">You can check which method has been used to protect a credential by consuming the [AAGUID](https://w3c.github.io/webauthn/#sec-attested-credential-data) field in the attestation object returned at credential creation.</span></span> <span data-ttu-id="9cadc-177">以下是 Windows Hello 可能返回的 AAGUIDs 的列表：</span><span class="sxs-lookup"><span data-stu-id="9cadc-177">The following is the list of AAGUIDs that Windows Hello may return:</span></span> 
  - <span data-ttu-id="9cadc-178">软件支持的 authenticators</span><span class="sxs-lookup"><span data-stu-id="9cadc-178">Software backed authenticators</span></span>
    - <span data-ttu-id="9cadc-179">Windows Hello 软件身份验证器：</span><span class="sxs-lookup"><span data-stu-id="9cadc-179">Windows Hello software authenticator:</span></span> `6028B017-B1D4-4C02-B4B3-AFCDAFC96BB2`
    - <span data-ttu-id="9cadc-180">Windows Hello VBS 软件身份验证器：</span><span class="sxs-lookup"><span data-stu-id="9cadc-180">Windows Hello VBS software authenticator:</span></span> `6E96969E-A5CF-4AAD-9B56-305FE6C82795`
  - <span data-ttu-id="9cadc-181">受信任的平台模块（TPM）受支持的 authenticators</span><span class="sxs-lookup"><span data-stu-id="9cadc-181">Trusted Platform Module (TPM) backed authenticators</span></span>
    - <span data-ttu-id="9cadc-182">Windows Hello 硬件身份验证器：</span><span class="sxs-lookup"><span data-stu-id="9cadc-182">Windows Hello hardware authenticator:</span></span> `08987058-CADC-4B81-B6E1-30DE50DCBE96`
    - <span data-ttu-id="9cadc-183">Windows Hello VBS 硬件身份验证器：</span><span class="sxs-lookup"><span data-stu-id="9cadc-183">Windows Hello VBS hardware authenticator:</span></span> `9DDD1817-AF5A-4672-A2B9-3E3DD95000A9`


### <span data-ttu-id="9cadc-184">API 平面</span><span class="sxs-lookup"><span data-stu-id="9cadc-184">API surface</span></span>
- <span data-ttu-id="9cadc-185">Microsoft Edge 已完全实现了核心 Web 身份验证规范的候选推荐版本。</span><span class="sxs-lookup"><span data-stu-id="9cadc-185">Microsoft Edge has a complete implementation of the Candidate Recommendation version of the core Web Authentication specification.</span></span>
- <span data-ttu-id="9cadc-186">支持[AppID 扩展](https://w3c.github.io/webauthn/#sctn-appid-extension)。</span><span class="sxs-lookup"><span data-stu-id="9cadc-186">The [AppID extension](https://w3c.github.io/webauthn/#sctn-appid-extension) is supported.</span></span> 
- <span data-ttu-id="9cadc-187">不支持其他扩展。</span><span class="sxs-lookup"><span data-stu-id="9cadc-187">No other extensions are supported.</span></span>


## <span data-ttu-id="9cadc-188">演示</span><span class="sxs-lookup"><span data-stu-id="9cadc-188">Demos</span></span>

[<span data-ttu-id="9cadc-189">客户端和服务器代码示例</span><span class="sxs-lookup"><span data-stu-id="9cadc-189">Client and server code sample</span></span>](https://github.com/MicrosoftEdge/webauthnsample)

[<span data-ttu-id="9cadc-190">Windows Hello 测试驱动器演示</span><span class="sxs-lookup"><span data-stu-id="9cadc-190">Windows Hello Test Drive demo</span></span>](https://webauthnsample.azurewebsites.net/)

## <span data-ttu-id="9cadc-191">书</span><span class="sxs-lookup"><span data-stu-id="9cadc-191">Specification</span></span>

[<span data-ttu-id="9cadc-192">Web 身份验证：用于访问公钥凭据的 API</span><span class="sxs-lookup"><span data-stu-id="9cadc-192">Web Authentication: An API for accessing Public Key Credentials</span></span>](http://w3c.github.io/webauthn/)
