---
description: 构建和发布 Microsoft Edge (Chromium) 扩展的概述。
title: Microsoft Edge (Chromium) 扩展概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/10/2021
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员， chromium 扩展
ms.openlocfilehash: 3ed0871883acfb7c3cf08c2da9f47d18ae3465f0
ms.sourcegitcommit: fe7301d0f62493e42e6a1a81cdbda3457f0343b8
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/13/2021
ms.locfileid: "11327524"
---
# <span data-ttu-id="a494f-104">Microsoft Edge (Chromium) 扩展概述</span><span class="sxs-lookup"><span data-stu-id="a494f-104">Overview of Microsoft Edge (Chromium) Extensions</span></span>  

<span data-ttu-id="a494f-105">扩展是你\（开发人员\）使用它来添加或修改 Microsoft Edge \(Chromium\) 功能的小程序。</span><span class="sxs-lookup"><span data-stu-id="a494f-105">An extension is a small program that you \(a developer\) use to add or modify features for Microsoft Edge \(Chromium\).</span></span>  <span data-ttu-id="a494f-106">扩展旨在改善用户的日常浏览体验。</span><span class="sxs-lookup"><span data-stu-id="a494f-106">An extension is intended to improve a user's day-to-day browsing experience.</span></span>  <span data-ttu-id="a494f-107">它提供了对目标受众很重要的功能。</span><span class="sxs-lookup"><span data-stu-id="a494f-107">It provides niche functionality that is important to a target audience.</span></span>  

<span data-ttu-id="a494f-108">如果有基于以下任一条件的想法或产品，则可以创建扩展。</span><span class="sxs-lookup"><span data-stu-id="a494f-108">You may create an extension if you have an idea or product that is based upon either of the following conditions.</span></span>  

*   <span data-ttu-id="a494f-109">特定的 web 浏览器。</span><span class="sxs-lookup"><span data-stu-id="a494f-109">A specific web browser.</span></span>  
*   <span data-ttu-id="a494f-110">对特定网页功能的改进。</span><span class="sxs-lookup"><span data-stu-id="a494f-110">Improvements to features of specific webpages.</span></span>  
    
<span data-ttu-id="a494f-111">配套体验的示例包括广告拦截器和密码管理器。</span><span class="sxs-lookup"><span data-stu-id="a494f-111">Examples of companion experiences include ad blockers and password managers.</span></span>  

<span data-ttu-id="a494f-112">扩展的结构类似于常规 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="a494f-112">An extension is structured similar to a regular web app.</span></span>  <span data-ttu-id="a494f-113">它至少应该包括以下功能。</span><span class="sxs-lookup"><span data-stu-id="a494f-113">At a minimum, it should include the following features.</span></span>

*   <span data-ttu-id="a494f-114">包含基本平台信息的应用程序清单 JSON 文件。</span><span class="sxs-lookup"><span data-stu-id="a494f-114">An app manifest JSON file that contains basic platform information.</span></span>  
*   <span data-ttu-id="a494f-115">定义功能的 JavaScript 文件。</span><span class="sxs-lookup"><span data-stu-id="a494f-115">A JavaScript file that define functionality.</span></span>  
*   <span data-ttu-id="a494f-116">定义用户界面的 HTML 和 CSS 文件。</span><span class="sxs-lookup"><span data-stu-id="a494f-116">HTML and CSS files that define the user interface.</span></span>  

<span data-ttu-id="a494f-117">若要直接使用部分浏览器（如窗口或选项卡），必须发送 API 请求，并通常按名称引用浏览器。</span><span class="sxs-lookup"><span data-stu-id="a494f-117">To work directly with part of the browser, such as a window or tab, you must send API requests and often reference the browser by name.</span></span>  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 扩展" lightbox="./media/example-extension-screenshot.png":::
  <span data-ttu-id="a494f-119">Microsoft Edge \(Chromium\) 扩展</span><span class="sxs-lookup"><span data-stu-id="a494f-119">A Microsoft Edge \(Chromium\) extension</span></span>  
:::image-end:::  

## <span data-ttu-id="a494f-120">基本指南</span><span class="sxs-lookup"><span data-stu-id="a494f-120">Basic guidance</span></span>  

<span data-ttu-id="a494f-121">为一些最受欢迎的浏览器包括 Safari、Firefox、Chrome、Opera、Cookie 和 Microsoft Edge 构建扩展。</span><span class="sxs-lookup"><span data-stu-id="a494f-121">Some of the most popular browsers to build extensions for include Safari, Firefox, Chrome, Opera, Brave, and Microsoft Edge.</span></span>  <span data-ttu-id="a494f-122">浏览器组织托管的网站是开始扩展开发教程和文档研究很好的位置。</span><span class="sxs-lookup"><span data-stu-id="a494f-122">Great places to begin your extension development tutorials and documentation research are sites hosted by the browser organizations.</span></span>  <span data-ttu-id="a494f-123">下表不确定的，可以作为起点。</span><span class="sxs-lookup"><span data-stu-id="a494f-123">The following table isn't definitive, and may be used as a starting point.</span></span>  

| <span data-ttu-id="a494f-124">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="a494f-124">Web browser</span></span> | <span data-ttu-id="a494f-125">基于 Chromium？</span><span class="sxs-lookup"><span data-stu-id="a494f-125">Chromium-based?</span></span> | <span data-ttu-id="a494f-126">扩展开发网页</span><span class="sxs-lookup"><span data-stu-id="a494f-126">Extension development webpage</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="a494f-127">Safari</span><span class="sxs-lookup"><span data-stu-id="a494f-127">Safari</span></span> | <span data-ttu-id="a494f-128">否</span><span class="sxs-lookup"><span data-stu-id="a494f-128">No</span></span> | [<span data-ttu-id="a494f-129">developer.apple.com/documentation/safariservices/safari_app_extensions</span><span class="sxs-lookup"><span data-stu-id="a494f-129">developer.apple.com/documentation/safariservices/safari_app_extensions</span></span>][AppleDeveloperSafariservicesAppExtensions] |  
| <span data-ttu-id="a494f-130">Firefox</span><span class="sxs-lookup"><span data-stu-id="a494f-130">Firefox</span></span> | <span data-ttu-id="a494f-131">否</span><span class="sxs-lookup"><span data-stu-id="a494f-131">No</span></span> | [<span data-ttu-id="a494f-132">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span><span class="sxs-lookup"><span data-stu-id="a494f-132">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span></span>][MDNWebextensions] |  
| <span data-ttu-id="a494f-133">镶边</span><span class="sxs-lookup"><span data-stu-id="a494f-133">Chrome</span></span> | <span data-ttu-id="a494f-134">是</span><span class="sxs-lookup"><span data-stu-id="a494f-134">Yes</span></span> | [<span data-ttu-id="a494f-135">developer.chrome.com/extensions</span><span class="sxs-lookup"><span data-stu-id="a494f-135">developer.chrome.com/extensions</span></span>][ChromeDeveloperExtensions] |  
| <span data-ttu-id="a494f-136">Opera</span><span class="sxs-lookup"><span data-stu-id="a494f-136">Opera</span></span> | <span data-ttu-id="a494f-137">是</span><span class="sxs-lookup"><span data-stu-id="a494f-137">Yes</span></span> | [<span data-ttu-id="a494f-138">dev.opera.com/extensions</span><span class="sxs-lookup"><span data-stu-id="a494f-138">dev.opera.com/extensions</span></span>][OperaDevExtensions] |  
| <span data-ttu-id="a494f-139">勇敢</span><span class="sxs-lookup"><span data-stu-id="a494f-139">Brave</span></span> | <span data-ttu-id="a494f-140">是</span><span class="sxs-lookup"><span data-stu-id="a494f-140">Yes</span></span> | <span data-ttu-id="a494f-141">使用 [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span><span class="sxs-lookup"><span data-stu-id="a494f-141">Uses [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span></span> |  
| <span data-ttu-id="a494f-142">新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a494f-142">new Microsoft Edge</span></span> | <span data-ttu-id="a494f-143">是</span><span class="sxs-lookup"><span data-stu-id="a494f-143">Yes</span></span> | [<span data-ttu-id="a494f-144">developer.microsoft.com/microsoft-edge/extensions</span><span class="sxs-lookup"><span data-stu-id="a494f-144">developer.microsoft.com/microsoft-edge/extensions</span></span>][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> <span data-ttu-id="a494f-145">许多网站教程使用的浏览器特定的 API 可能与为其开发的浏览器不匹配。</span><span class="sxs-lookup"><span data-stu-id="a494f-145">Many of the tutorials of the sites use browser-specific APIs that may not match the browser for which you develop.</span></span>  <span data-ttu-id="a494f-146">在大多数情况下，Chromium 扩展在不同 Chromium 浏览器中工作，且 API 按预期工作。</span><span class="sxs-lookup"><span data-stu-id="a494f-146">In most cases, a Chromium extension works as-is in different Chromium browsers and the APIs work as expected.</span></span>  <span data-ttu-id="a494f-147">只有一些不太常见的 API 可能会严格特定于浏览器。</span><span class="sxs-lookup"><span data-stu-id="a494f-147">Only some less common APIs may be strictly browser-specific.</span></span>  <span data-ttu-id="a494f-148">有关教程的链接，请导航至“[另请参见](#see-also)”。</span><span class="sxs-lookup"><span data-stu-id="a494f-148">For links to the tutorials, navigate to [See also](#see-also).</span></span>  

## <span data-ttu-id="a494f-149">为什么使用 Chromium？</span><span class="sxs-lookup"><span data-stu-id="a494f-149">Why Chromium?</span></span>  

<span data-ttu-id="a494f-150">如果目标是在每个浏览器扩展应用商店中发布扩展，则必须为每个版本对其进行修改，以便在不同浏览器环境中运行。</span><span class="sxs-lookup"><span data-stu-id="a494f-150">If your goal is to publish your extension in the extensions store for each browser, it must be modified for each version to target and run in each distinct browser environment.</span></span>  <span data-ttu-id="a494f-151">例如，[Safari 扩展][AppleDeveloperSafariservicesAppExtensions]可以同时使用 web 和本机代码与对应的本机应用通信。</span><span class="sxs-lookup"><span data-stu-id="a494f-151">For example, [Safari extensions][AppleDeveloperSafariservicesAppExtensions] may use both web and native code to communicate with counterpart native applications.</span></span>  <span data-ttu-id="a494f-152">上表中的最后四个浏览器使用相同的代码包，并将维护并行版本的要求降到最低。</span><span class="sxs-lookup"><span data-stu-id="a494f-152">The last four browsers in the previous table use the same code package, and minimizes the requirement to maintain parallel versions.</span></span>  <span data-ttu-id="a494f-153">这些浏览器基于 [Chromium 开源项目][|::ref1::|Home]。</span><span class="sxs-lookup"><span data-stu-id="a494f-153">These browsers are based on the [Chromium open-source project][|::ref1::|Home].</span></span>  

<span data-ttu-id="a494f-154">创建 Chromium 扩展以编写最少的代码。</span><span class="sxs-lookup"><span data-stu-id="a494f-154">Create a Chromium extension to write the least amount of code.</span></span>  <span data-ttu-id="a494f-155">它还以扩展应用商店的最大数量以及最终以找到和获取扩展的最大用户数为目标。</span><span class="sxs-lookup"><span data-stu-id="a494f-155">It also targets the maximum number of extension stores and ultimately the maximum number of users who find and acquire your extension.</span></span>  

<span data-ttu-id="a494f-156">以下内容主要侧重于 Chromium 扩展。</span><span class="sxs-lookup"><span data-stu-id="a494f-156">The following content focuses mostly on Chromium extensions.</span></span>  

## <span data-ttu-id="a494f-157">浏览器兼容性和扩展测试</span><span class="sxs-lookup"><span data-stu-id="a494f-157">Browser compatibility and extension testing</span></span>  

<span data-ttu-id="a494f-158">有时，Chromium 浏览器之间不存在 API 奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="a494f-158">Occasionally, API parity doesn't exist between Chromium browsers.</span></span>  <span data-ttu-id="a494f-159">例如，标识和付款 API 存在差异。</span><span class="sxs-lookup"><span data-stu-id="a494f-159">For example, there are differences in the identity and payment APIs.</span></span>  <span data-ttu-id="a494f-160">为了确保扩展满足客户的期望，请通过以下官方浏览器文档查看 API 状态。</span><span class="sxs-lookup"><span data-stu-id="a494f-160">To ensure your extension meets customer expectations, review API status through the following official browser docs.</span></span>  

*   [<span data-ttu-id="a494f-161">Chrome API</span><span class="sxs-lookup"><span data-stu-id="a494f-161">Chrome APIs</span></span>][ChromeDeveloperExtensionsApiIndex]  
*   [<span data-ttu-id="a494f-162">Opera 支持的扩展 API</span><span class="sxs-lookup"><span data-stu-id="a494f-162">Extension APIs supported in Opera</span></span>][OperaDevExtensionsApis]  
*   [<span data-ttu-id="a494f-163">将 Chrome 扩展移植到 Microsoft Edge (Chromium)</span><span class="sxs-lookup"><span data-stu-id="a494f-163">Port Chrome extension to Microsoft Edge (Chromium)</span></span>][ExtensionsChromiumDeveloperGuidePortChrome]  
    
<span data-ttu-id="a494f-164">所需 API 定义了为解决各浏览器之间差异而必须进行的更改。</span><span class="sxs-lookup"><span data-stu-id="a494f-164">The APIs you require define the changes you must make to address the differences between each browser.</span></span>  <span data-ttu-id="a494f-165">这可能意味着必须为每个应用商店创建略有差异的不同代码包。</span><span class="sxs-lookup"><span data-stu-id="a494f-165">It may mean that you must create slightly different code packages with small differences for each store.</span></span>  

<span data-ttu-id="a494f-166">若要在将扩展提交到浏览器应用商店之前在不同环境中进行测试，请在开发扩展时将其旁加载到浏览器中。</span><span class="sxs-lookup"><span data-stu-id="a494f-166">To test your extension in different environments before you submit it to a browser store, sideload it into your browser while you develop it.</span></span>  

## <span data-ttu-id="a494f-167">将扩展发布到浏览器应用商店</span><span class="sxs-lookup"><span data-stu-id="a494f-167">Publish your extension to browser stores</span></span>  

<span data-ttu-id="a494f-168">您可以在以下浏览器存储中提交和查找浏览器扩展。</span><span class="sxs-lookup"><span data-stu-id="a494f-168">You may submit and seek browser extensions in the following browser stores.</span></span>  

*   [<span data-ttu-id="a494f-169">Firefox 浏览器加载项</span><span class="sxs-lookup"><span data-stu-id="a494f-169">Firefox Browser Add-ons</span></span>][MozillaAddonsFirefoxExtensions]  
*   [<span data-ttu-id="a494f-170">Chrome Web Store</span><span class="sxs-lookup"><span data-stu-id="a494f-170">Chrome Web Store</span></span>][GoogleChromeWebstoreCategoryExtensions]  
*   [<span data-ttu-id="a494f-171">Opera加载项</span><span class="sxs-lookup"><span data-stu-id="a494f-171">Opera addons</span></span>][OperaAddonsExtensions]  
*   [<span data-ttu-id="a494f-172">Microsoft Edge 加载项</span><span class="sxs-lookup"><span data-stu-id="a494f-172">Microsoft Edge Add-ons</span></span>][MicrosoftEdgeAddonsCategoryExtensions]  

<span data-ttu-id="a494f-173">某些商店允许你从其他浏览器下载列出的扩展。</span><span class="sxs-lookup"><span data-stu-id="a494f-173">Some stores allow you to download listed extensions from other browsers.</span></span>  <span data-ttu-id="a494f-174">但是，浏览器商店无法保证跨浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="a494f-174">However, cross-browser access is not guaranteed by browser stores.</span></span>  <span data-ttu-id="a494f-175">为了确保你的用户可在不同的浏览器中找到扩展，应该在每个浏览器扩展商店上维护一个列表。</span><span class="sxs-lookup"><span data-stu-id="a494f-175">To ensure your users find your extension in different browsers, you should maintain a listing on each browser extension store.</span></span>  

<span data-ttu-id="a494f-176">用户可能需要在不同的浏览器中安装扩展。</span><span class="sxs-lookup"><span data-stu-id="a494f-176">Users may need to install your extension in different browsers.</span></span> <span data-ttu-id="a494f-177">在这种情况下，可以将现有的 Chromium 扩展从一个浏览器迁移到另一个浏览器。</span><span class="sxs-lookup"><span data-stu-id="a494f-177">In this scenario, you may migrate existing Chromium extensions from one browser to another.</span></span>  

### <span data-ttu-id="a494f-178">将现有扩展迁移到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="a494f-178">Migrate an existing extension to Microsoft Edge</span></span>  

<span data-ttu-id="a494f-179">如果已经为另一个 Chrome 浏览器开发了扩展，则可以将其提交到 Microsoft Edge 加载项商店。</span><span class="sxs-lookup"><span data-stu-id="a494f-179">If you've already developed an extension for another Chromium browser, you may submit it to the Microsoft Edge Add-ons store.</span></span> <span data-ttu-id="a494f-180">不需要重写扩展，并且必须验证它在 MicrosoftEdge 中是否工作。</span><span class="sxs-lookup"><span data-stu-id="a494f-180">You don't need to rewrite your extension, and must verify it works in Microsoft Edge.</span></span>  <span data-ttu-id="a494f-181">将现有的 Chromium 扩展迁移到其他 Chromium 浏览器时，请确保相同的 API 或替代方案可用于该目标浏览器。</span><span class="sxs-lookup"><span data-stu-id="a494f-181">When you migrate an existing Chromium extension to other Chromium browsers, ensure the same APIs or alternatives are available for your target browser.</span></span>  

<span data-ttu-id="a494f-182">有关将 Chrome 扩展移植到 Microsoft Edge 的更多信息，请导航到[将 Chrome 扩展移植到 Microsoft Edge (Chrome)][ExtensionsChromiumDeveloperGuidePortChrome]。</span><span class="sxs-lookup"><span data-stu-id="a494f-182">For more information on porting your Chrome extension to Microsoft Edge, navigate to [Port Chrome extensions to Microsoft Edge (Chromium)][ExtensionsChromiumDeveloperGuidePortChrome].</span></span> <span data-ttu-id="a494f-183">将扩展移植到目标浏览器后，下一步是发布它。</span><span class="sxs-lookup"><span data-stu-id="a494f-183">After you port your extension to the target browser, the next step is to publish it.</span></span>  

### <span data-ttu-id="a494f-184">发布到 Microsoft Edge 外接程序网站</span><span class="sxs-lookup"><span data-stu-id="a494f-184">Publish to the Microsoft Edge add-ons website</span></span>  

<span data-ttu-id="a494f-185">若要开始将扩展发布到 Microsoft Edge，必须[使用 MSA 电子邮件帐户注册开发人员帐户][MicrosoftDeveloperRegistration]，才能将扩展列表提交到商店。</span><span class="sxs-lookup"><span data-stu-id="a494f-185">To start publishing your extension to Microsoft Edge, you must [register for a developer account][MicrosoftDeveloperRegistration] with an MSA email account to submit your extension listing to the store.</span></span>  <span data-ttu-id="a494f-186">MSA 电子邮件帐户包括 `@outlook.com`、`@live.com` 等。</span><span class="sxs-lookup"><span data-stu-id="a494f-186">An MSA email account includes `@outlook.com`, `@live.com`, and so on.</span></span>  <span data-ttu-id="a494f-187">选择要注册的电子邮件地址时，请考虑是否必须与组织中其他人转移或共享扩展的所有权。</span><span class="sxs-lookup"><span data-stu-id="a494f-187">When you choose an email address to register, consider if you must transfer or share ownership of the extension with others in your organization.</span></span>  <span data-ttu-id="a494f-188">注册完成后，你可以向应用商店创建新的扩展提交。</span><span class="sxs-lookup"><span data-stu-id="a494f-188">After registration is complete, you may create a new extension submission to the store.</span></span>  

<span data-ttu-id="a494f-189">若要向应用商店提交扩展，请确保提供以下项目。</span><span class="sxs-lookup"><span data-stu-id="a494f-189">To submit your extension to the store, ensure you provide the following items.</span></span>  

*   <span data-ttu-id="a494f-190">包含代码文件的存档 \(`.zip`\) 文件。</span><span class="sxs-lookup"><span data-stu-id="a494f-190">An archive \(`.zip`\) file that contains your code files.</span></span>  
*   <span data-ttu-id="a494f-191">所有必需的视觉资源，包括徽标和小型促销磁贴。</span><span class="sxs-lookup"><span data-stu-id="a494f-191">All required visual assets, which include a logo and small promotional tile.</span></span>  
*   <span data-ttu-id="a494f-192">可选促销媒体，如屏幕截图、促销贴片和视频 URL。</span><span class="sxs-lookup"><span data-stu-id="a494f-192">Optional promotional media, such as screenshots, promotional tiles, and a video URL.</span></span>  
*   <span data-ttu-id="a494f-193">描述扩展名的信息，如名称、简短描述和隐私策略链接。</span><span class="sxs-lookup"><span data-stu-id="a494f-193">Information that describes your extension such as the name, short description, and a privacy policy link.</span></span>  

> [!NOTE]
> <span data-ttu-id="a494f-194">不同的应用商店可能具有不同的提交要求。</span><span class="sxs-lookup"><span data-stu-id="a494f-194">Different stores may have different submission requirements.</span></span>  <span data-ttu-id="a494f-195">上面的列表总结了发布 [Microsoft Edge][ExtensionsChromiumPublish] 扩展的要求。</span><span class="sxs-lookup"><span data-stu-id="a494f-195">The above list summarizes the [requirements][ExtensionsChromiumPublish] to publish an extension for Microsoft Edge.</span></span>  

<span data-ttu-id="a494f-196">成功提交扩展后，扩展将经历审核过程，它将通过或不通过认证过程。</span><span class="sxs-lookup"><span data-stu-id="a494f-196">After you've successfully submitted your extension, your extension undergoes a review process and either passes or fails the certification process.</span></span>  <span data-ttu-id="a494f-197">向所有者通知结果，并按需要提供下一步步骤。</span><span class="sxs-lookup"><span data-stu-id="a494f-197">Owners are notified of the outcome and given next steps as required.</span></span>  <span data-ttu-id="a494f-198">如果向应用商店提交扩展更新，则会启动新的审阅过程。</span><span class="sxs-lookup"><span data-stu-id="a494f-198">If you submit an extension update to the store, a new review process is started.</span></span>  

## <span data-ttu-id="a494f-199">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a494f-199">See also</span></span>  

*   [<span data-ttu-id="a494f-200">移植 Google Chrome 扩展</span><span class="sxs-lookup"><span data-stu-id="a494f-200">Port a Google Chrome extension</span></span>][ExtensionworkshopPorting]  
*   [<span data-ttu-id="a494f-201">构建 Safari 应用扩展</span><span class="sxs-lookup"><span data-stu-id="a494f-201">Build a Safari App extension</span></span>][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [<span data-ttu-id="a494f-202">第一个扩展 (Firefox)</span><span class="sxs-lookup"><span data-stu-id="a494f-202">Your first extension (Firefox)</span></span>][MDNWebextensionsYourFirst]  
*   [<span data-ttu-id="a494f-203">入门教程 (Opera)</span><span class="sxs-lookup"><span data-stu-id="a494f-203">Get started tutorial (Chrome)</span></span>][ChromeDeveloperExtensionsGetstarted]  
*   [<span data-ttu-id="a494f-204">入门 (Opera)</span><span class="sxs-lookup"><span data-stu-id="a494f-204">Get started (Opera)</span></span>][OperaDevExtensionsGettingStarted]  
*   [<span data-ttu-id="a494f-205">Microsoft Edge (Chromium) 扩展入门</span><span class="sxs-lookup"><span data-stu-id="a494f-205">Get started with Microsoft Edge (Chromium) extensions</span></span>][ExtensionsChromiumGettingStartedIndex]  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "将 Chrome 扩展移植到 Microsoft Edge (Chromium) |Microsoft Docs"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) 扩展 | Microsoft Docs 入门"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "发布扩展|Microsoft Docs"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "开发 Microsoft Edge |Microsoft 开发人员"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "合作伙伴中心|Microsoft 开发人员"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge |Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari 应用扩展|Apple 开发人员"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "生成 Safari 应用扩展|Apple 开发人员"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "什么是扩展？|Chrome 开发人员"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome API |Chrome 开发人员"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "入门教程|Chrome 开发人员"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "移植 Google Chrome 扩展|扩展研讨会"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "扩展|Chrome Web Store"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "浏览器扩展|MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "你的第一个|MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "扩展|Firefox 加载项"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "扩展|Opera Addons"  

[OperaDevExtensions]: https://dev.opera.com/extensions "扩展文档|Dev. Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "操作方法支持扩展|Dev. Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "入门 | Dev. Opera"  
