---
description: 在 Microsoft Edge DevTools 中模拟 Authenticators 和调试 WebAuthn。
title: 在 Microsoft Edge 中模拟 authenticators 和调试 WebAuthn DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/22/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6727e9aeea1a51689a80570a2f1c9df880a8c9db
ms.sourcegitcommit: 6e2b26d41a0aa56ac34e6edc7dddd852ddb415b1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2020
ms.locfileid: "11133999"
---
# <span data-ttu-id="94986-104">在 Microsoft Edge 中模拟 authenticators 和调试 WebAuthn DevTools</span><span class="sxs-lookup"><span data-stu-id="94986-104">Emulate authenticators and debug WebAuthn in Microsoft Edge DevTools</span></span>  

<span data-ttu-id="94986-105">不要在你的网站或应用中使用物理 authenticators 调试 Web 身份验证，请使用 Microsoft Edge DevTools 中的 " **WebAuthn** " 工具创建基于软件的虚拟 authenticators 并与之交互。</span><span class="sxs-lookup"><span data-stu-id="94986-105">Instead of debugging Web Authentication in your website or app with physical authenticators, use the **WebAuthn** tool in Microsoft Edge DevTools to create and interact with software-based virtual authenticators.</span></span>  

## <span data-ttu-id="94986-106">开始之前</span><span class="sxs-lookup"><span data-stu-id="94986-106">Before you begin</span></span>  

<span data-ttu-id="94986-107">Web 身份验证入门的一个绝佳位置是 [Web 身份验证 API 规范][GithubW3cWebauthn]。</span><span class="sxs-lookup"><span data-stu-id="94986-107">A great place to get started with Web Authentication is the [Web Authentication API specification][GithubW3cWebauthn].</span></span>  

## <span data-ttu-id="94986-108">设置 "WebAuthn" 工具</span><span class="sxs-lookup"><span data-stu-id="94986-108">Set up the WebAuthn tool</span></span>  

1.  <span data-ttu-id="94986-109">导航到使用 WebAuthn 的网页，例如以下演示网站。</span><span class="sxs-lookup"><span data-stu-id="94986-109">Navigate to a webpage that uses WebAuthn, such as the following demo website.</span></span>  
    
    [<span data-ttu-id="94986-110">webauthndemo.appspot.com</span><span class="sxs-lookup"><span data-stu-id="94986-110">webauthndemo.appspot.com</span></span>][AppspotWebauthndemo]  
    
1.  <span data-ttu-id="94986-111">登录到网站。</span><span class="sxs-lookup"><span data-stu-id="94986-111">Sign into the website.</span></span>  
1.  <span data-ttu-id="94986-112">[打开 DevTools][DevtoolsGuideChromiumOpen]。</span><span class="sxs-lookup"><span data-stu-id="94986-112">[Open DevTools][DevtoolsGuideChromiumOpen].</span></span>  
1.  <span data-ttu-id="94986-113">若要打开 " **WebAuthn** " 工具，请选择 "**自定义和控制 DevTools** \ (`...` \ ) " 图标 > "**更多工具" 工具**  >  **WebAuthn**。</span><span class="sxs-lookup"><span data-stu-id="94986-113">To open the **WebAuthn** tool, choose the **Customize and control DevTools** \(`...`\) icon > **More tools** > **WebAuthn**.</span></span>  
    
    :::image type="complex" source="../media/webauthn-webauthn-tab.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-webauthn-tab.msft.png":::
       <span data-ttu-id="94986-115">**WebAuthn** 工具</span><span class="sxs-lookup"><span data-stu-id="94986-115">**WebAuthn** tool</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="94986-116">在 " **WebAuthn** 工具" 中，选择 " **启用虚拟身份验证器环境**" 旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="94986-116">In the **WebAuthn** tool, choose the checkbox next to **Enable virtual authenticator environment**.</span></span>  
1.  <span data-ttu-id="94986-117">启用后，将显示名为 " **新建身份验证** 器" 的新分区。</span><span class="sxs-lookup"><span data-stu-id="94986-117">After it is enabled, a new section named **New authenticator** is displayed.</span></span>  
    
    :::image type="complex" source="../media/webauthn-enable-virtual-auth.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-enable-virtual-auth.msft.png":::
        **<span data-ttu-id="94986-119">启用虚拟身份验证器环境</span><span class="sxs-lookup"><span data-stu-id="94986-119">Enable virtual authenticator environment</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="94986-120">在 " **新建身份验证** 器" 部分中，配置以下选项。</span><span class="sxs-lookup"><span data-stu-id="94986-120">In the **New authenticator** section, configure the following options.</span></span>  
    
    | <span data-ttu-id="94986-121">选项</span><span class="sxs-lookup"><span data-stu-id="94986-121">Option</span></span> | <span data-ttu-id="94986-122">Value</span><span class="sxs-lookup"><span data-stu-id="94986-122">Value</span></span> | <span data-ttu-id="94986-123">详细信息</span><span class="sxs-lookup"><span data-stu-id="94986-123">Details</span></span> |  
    |:--- |:--- |:--- |  
    | `Protocol` | <span data-ttu-id="94986-124">[ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] 或 [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml]</span><span class="sxs-lookup"><span data-stu-id="94986-124">[ctap2][FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml] or [u2f][FidoallianceSpecsU2fV12Ps20170411OverviewHtml]</span></span> | <span data-ttu-id="94986-125">虚拟身份验证器用于编码和解码的协议</span><span class="sxs-lookup"><span data-stu-id="94986-125">The protocol the virtual authenticator uses for encoding and decoding</span></span> |  
    | `Transport` |   `usb`<span data-ttu-id="94986-126">、 `nfc` 、 `ble` 或</span><span class="sxs-lookup"><span data-stu-id="94986-126">, `nfc`, `ble`, or</span></span> `internal` | <span data-ttu-id="94986-127">虚拟身份验证器模拟所选传输，以便为特定凭据获取断言。</span><span class="sxs-lookup"><span data-stu-id="94986-127">The virtual authenticator simulates the selected transport for communicating with clients in order to obtain an assertion for a specific credential.</span></span>  <span data-ttu-id="94986-128">有关详细信息，请导航到 [身份验证器传输枚举][GithubW3cWebauthnEnumTransport]</span><span class="sxs-lookup"><span data-stu-id="94986-128">For more information, navigate to [Authenticator Transport Enumeration][GithubW3cWebauthnEnumTransport]</span></span> |  
    |  `Supports resident keys` | <span data-ttu-id="94986-129">使用复选框打开 \ (或关闭 \ ) </span><span class="sxs-lookup"><span data-stu-id="94986-129">Turn on \(or off\) using the checkbox</span></span> | <span data-ttu-id="94986-130">如果你的 web 应用依赖于常驻密钥 \ (也称为客户端可发现凭据 \ ) ，则打开。</span><span class="sxs-lookup"><span data-stu-id="94986-130">Turn on if your web app relies on resident keys \(also known as client-side discoverable credentials\).</span></span>  <span data-ttu-id="94986-131">有关详细信息，请导航到 " [常驻密钥需求枚举][GithubW3cWebauthnEnumResidentkeyrequirement]"。</span><span class="sxs-lookup"><span data-stu-id="94986-131">For more information, navigate to [Resident Key Requirement Enumeration][GithubW3cWebauthnEnumResidentkeyrequirement].</span></span> |  
    | `Supports user verification` | <span data-ttu-id="94986-132">使用复选框打开 \ (或关闭 \ ) </span><span class="sxs-lookup"><span data-stu-id="94986-132">Turn on \(or off\) using the checkbox</span></span> | <span data-ttu-id="94986-133">如果你的 web 应用依赖于使用手势形式的本地授权（如触控 + pin 码、密码输入或生物识别识别），则打开。</span><span class="sxs-lookup"><span data-stu-id="94986-133">Turn on if your web app relies on local authorization using gesture modalities like touch plus pin code, password entry, or biometric recognition.</span></span>  <span data-ttu-id="94986-134">有关详细信息，请导航到 [用户验证][GithubW3cWebauthnEnumUserverification]</span><span class="sxs-lookup"><span data-stu-id="94986-134">For more information, navigate to [User Verification][GithubW3cWebauthnEnumUserverification]</span></span> |  
    
1.  <span data-ttu-id="94986-135">选择“添加”按钮\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="94986-135">Choose the **Add** button.</span></span>  
1.  <span data-ttu-id="94986-136">将显示新创建的身份验证器的新分区。</span><span class="sxs-lookup"><span data-stu-id="94986-136">A new section of your newly created authenticator is displayed.</span></span>  
    
    :::image type="complex" source="../media/webauthn-authenticator.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-authenticator.msft.png":::
       <span data-ttu-id="94986-138">鉴别</span><span class="sxs-lookup"><span data-stu-id="94986-138">Authenticator</span></span>  
    :::image-end:::  
    
<span data-ttu-id="94986-139">**身份验证**器部分包括一个**凭据**表。</span><span class="sxs-lookup"><span data-stu-id="94986-139">The **Authenticator** section includes a **Credentials** table.</span></span>  <span data-ttu-id="94986-140">在将凭据注册到身份验证器之前，该表为空。</span><span class="sxs-lookup"><span data-stu-id="94986-140">The table is empty until a credential is registered to the authenticator.</span></span>  

:::image type="complex" source="../media/webauthn-no-cred.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-no-cred.msft.png":::
   <span data-ttu-id="94986-142">无凭据</span><span class="sxs-lookup"><span data-stu-id="94986-142">No credentials</span></span>  
:::image-end:::  

## <span data-ttu-id="94986-143">注册新凭据</span><span class="sxs-lookup"><span data-stu-id="94986-143">Register a new credential</span></span>  

<span data-ttu-id="94986-144">若要注册新凭据，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="94986-144">To register a new credential, complete the following steps.</span></span>  <span data-ttu-id="94986-145">有关注册新凭据时 [Web 身份验证 API][GithubW3cWebauthn] 正在执行的操作的详细信息，请导航以 [创建新凭据][GithubW3cWebauthnSctnCreatecredential]。</span><span class="sxs-lookup"><span data-stu-id="94986-145">For more information about what the [Web Authentication API][GithubW3cWebauthn] is doing when registering a new credential, navigate to [Create a New Credential][GithubW3cWebauthnSctnCreatecredential].</span></span>  

1.  <span data-ttu-id="94986-146">在演示网站上，选择 " **注册新凭据**"。</span><span class="sxs-lookup"><span data-stu-id="94986-146">On the demo website, choose **Register new credential**.</span></span>  
1.  <span data-ttu-id="94986-147">新凭据现在已添加到 "WebAuthn 工具" 的 " **凭据** " 表中。</span><span class="sxs-lookup"><span data-stu-id="94986-147">A new credential is now added to the **Credentials** table in the WebAuthn tool.</span></span>  
    
    :::image type="complex" source="../media/webauthn-view-cred.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-view-cred.msft.png":::
       <span data-ttu-id="94986-149">查看凭据</span><span class="sxs-lookup"><span data-stu-id="94986-149">View credentials</span></span>  
    :::image-end:::  
    
<span data-ttu-id="94986-150">在演示网站上，选择 " **身份验证** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="94986-150">On the demo website, choose the **Authenticate** button.</span></span>  <span data-ttu-id="94986-151">验证**凭据**表中凭据的[签名计数][GithubW3cWebauthnSctnSignCounter]是否增加1，它标记成功的[authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion]操作。</span><span class="sxs-lookup"><span data-stu-id="94986-151">Verify that the [Sign Count][GithubW3cWebauthnSctnSignCounter] of the credential in the **Credentials** table increased by 1, which marks a successful [authenticatorGetAssertion][GithubW3cWebauthnAuthenticatorgetassertion] operation.</span></span>  

## <span data-ttu-id="94986-152">导出和删除凭据</span><span class="sxs-lookup"><span data-stu-id="94986-152">Export and remove credentials</span></span>  

<span data-ttu-id="94986-153">若要导出或删除凭据，请选择 " **导出** " 或 " **删除** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="94986-153">To export or remove a credential, choose the **Export** or **Remove** button.</span></span>  

:::image type="complex" source="../media/webauthn-export-remove.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-export-remove.msft.png":::
   <span data-ttu-id="94986-155">导出或删除凭据</span><span class="sxs-lookup"><span data-stu-id="94986-155">Export or remove a credential</span></span>  
:::image-end:::  

## <span data-ttu-id="94986-156">重命名身份验证器</span><span class="sxs-lookup"><span data-stu-id="94986-156">Rename an authenticator</span></span>  

<span data-ttu-id="94986-157">若要重命名身份验证器，请完成以下步骤。</span><span class="sxs-lookup"><span data-stu-id="94986-157">To rename an authenticator, complete the following steps.</span></span>  

1.  <span data-ttu-id="94986-158">在身份验证器名称旁边，选择 " **编辑** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="94986-158">Next to the authenticator name, choose the **Edit** button.</span></span>  
1.  <span data-ttu-id="94986-159">编辑名称，然后选择 " **输入** " 以保存更改。</span><span class="sxs-lookup"><span data-stu-id="94986-159">Edit the name, then choose **Enter** to save the changes.</span></span>  

:::image type="complex" source="../media/webauthn-rename.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-rename.msft.png":::
   <span data-ttu-id="94986-161">重命名身份验证器</span><span class="sxs-lookup"><span data-stu-id="94986-161">Rename an authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="94986-162">设置活动身份验证器</span><span class="sxs-lookup"><span data-stu-id="94986-162">Set the active authenticator</span></span>  

<span data-ttu-id="94986-163">新创建的身份验证器将自动激活。</span><span class="sxs-lookup"><span data-stu-id="94986-163">A newly created authenticator is automatically activated.</span></span>  <span data-ttu-id="94986-164">若要使用其他虚拟身份验证器，请选择身份验证器旁边的 **活动** 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="94986-164">To use another virtual authenticator, choose the **Active** radio button next to the authenticator.</span></span>  

> [!NOTE]
> <span data-ttu-id="94986-165">DevTools 在任意时间点仅支持一个活动的虚拟身份验证器。</span><span class="sxs-lookup"><span data-stu-id="94986-165">DevTools supports only one active virtual authenticator at any point of time.</span></span>  <span data-ttu-id="94986-166">如果删除活动身份验证器，则不会自动激活另一个身份验证器。</span><span class="sxs-lookup"><span data-stu-id="94986-166">If you remove the active authenticator, another authenticator is not automatically activated.</span></span>  

:::image type="complex" source="../media/webauthn-set-active.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-set-active.msft.png":::
   <span data-ttu-id="94986-168">设置活动身份验证器</span><span class="sxs-lookup"><span data-stu-id="94986-168">Set active authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="94986-169">删除虚拟身份验证器</span><span class="sxs-lookup"><span data-stu-id="94986-169">Remove a virtual authenticator</span></span>  

<span data-ttu-id="94986-170">若要删除虚拟身份验证器，请选择 "身份验证器" 旁边的 " **删除** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="94986-170">To remove a virtual authenticator, next to the authenticator, choose the **Remove** button.</span></span>  

:::image type="complex" source="../media/webauthn-remove-authenticator.msft.png" alt-text="WebAuthn 工具" lightbox="../media/webauthn-remove-authenticator.msft.png":::
   <span data-ttu-id="94986-172">删除身份验证器</span><span class="sxs-lookup"><span data-stu-id="94986-172">Remove authenticator</span></span>  
:::image-end:::  

## <span data-ttu-id="94986-173">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="94986-173">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsGuideChromiumOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档"  

[AppspotWebauthndemo]: https://webauthndemo.appspot.com "Webauthn 演示 |Appspot"  

[FidoallianceSpecsV20Id20180227ClientToAuthenticatorProtocolHtml]: https://fidoalliance.org/specs/fido-v2.0-id-20180227/fido-client-to-authenticator-protocol-v2.0-id-20180227.html "客户端到身份验证器协议 (CTAP) |fido 联盟"  
[FidoallianceSpecsU2fV12Ps20170411OverviewHtml]: https://fidoalliance.org/specs/fido-u2f-v1.2-ps-20170411/fido-u2f-overview-v1.2-ps-20170411.html "通用第2因素 (U2F) 概述 |fido 联盟"  

[GithubW3cWebauthn]: https://w3c.github.io/webauthn "Web 身份验证：用于访问公钥凭据级别2的 API |GitHub"  
[GithubW3cWebauthnAuthenticatorgetassertion]: https://w3c.github.io/webauthn#authenticatorgetassertion "AuthenticatorGetAssertion 操作-Web 身份验证：用于访问公钥凭据级别2的 API |GitHub"  
[GithubW3cWebauthnEnumTransport]: https://w3c.github.io/webauthn#enum-transport "身份验证器传输枚举 (枚举 AuthenticatorTransport) Web 身份验证：用于访问公钥凭据级别2的 API |W3C"  
[GithubW3cWebauthnEnumResidentkeyrequirement]: https://w3c.github.io/webauthn#enum-residentKeyRequirement "常驻密钥需求枚举 (枚举 ResidentKeyRequirement) Web 身份验证：用于访问公钥凭据的 API 级别 2 |W3C"  
[GithubW3cWebauthnEnumUserverification]: https://w3c.github.io/webauthn#user-verification "用户验证-Web 身份验证：用于访问公钥凭据级别2的 API |W3C"  
[GithubW3cWebauthnSctnCreatecredential]: https://w3c.github.io/webauthn#sctn-createCredential "创建新的凭据-PublicKeyCredential 的 [[创建]] (来源、选项、sameOriginWithAncestors) 方法 Web 身份验证：用于访问公钥凭据的 API 级别 2 |GitHub"  
[GithubW3cWebauthnSctnSignCounter]: https://w3c.github.io/webauthn/#sctn-sign-counter "签名计数器注意事项-Web 身份验证：用于访问公钥凭据级别2的 API |GitHub"  

> [!NOTE]
> <span data-ttu-id="94986-185">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="94986-185">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="94986-186">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) 找到，并由 [Jecelyn Yeen][JecelynYeen] (开发人员和 DevTools，Chrome \ ) 。</span><span class="sxs-lookup"><span data-stu-id="94986-186">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/webauthn/index) and is authored by [Jecelyn Yeen][JecelynYeen] \(Developer advocate, Chrome DevTools\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="94986-188">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="94986-188">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[JecelynYeen]: https://developers.google.com/web/resources/contributors/jecelynyeen  
