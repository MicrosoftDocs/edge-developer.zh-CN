---
description: Microsoft Edge (Chromium) 扩展以及生成和发布浏览器扩展的概述。
title: Microsoft Edge (Chromium) 扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: edge， 扩展开发， 浏览器扩展， 加载项， 合作伙伴中心， 开发人员， chromium 扩展
ms.openlocfilehash: 04b9ffb7ec175bad4f980310819ea6d3551ef9f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230941"
---
# <span data-ttu-id="0be82-104">Microsoft Edge (Chromium) 扩展概述</span><span class="sxs-lookup"><span data-stu-id="0be82-104">Microsoft Edge (Chromium) Extensions overview</span></span> 

<span data-ttu-id="0be82-105">扩展是开发人员 \ (\) 可能用于将新功能添加到 Microsoft Edge \ (Chromium\) 或修改现有功能的一个小程序。</span><span class="sxs-lookup"><span data-stu-id="0be82-105">An extension is a small program that you \(the developer\) may use to add new features to Microsoft Edge \(Chromium\) or modify the existing functionality.</span></span>  <span data-ttu-id="0be82-106">扩展旨在通过提供对目标受众非常重要的小范围功能来改进用户日常浏览体验。</span><span class="sxs-lookup"><span data-stu-id="0be82-106">An extension is intended to improve a user's day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>  

<span data-ttu-id="0be82-107">如果您的想法或产品依赖于特定 Web 浏览器的可用性，您可以创建扩展，也可以增强要提供的功能扩展现有网站的浏览体验。</span><span class="sxs-lookup"><span data-stu-id="0be82-107">You may create extensions if your idea or product depends on the availability of a specific web browser or augments the browsing experience where the functionality that you want to provide extends existing websites.</span></span>  <span data-ttu-id="0be82-108">配套体验的示例包括 adblockers 和密码管理器。</span><span class="sxs-lookup"><span data-stu-id="0be82-108">Examples of companion experiences include adblockers and password managers.</span></span>  

<span data-ttu-id="0be82-109">扩展的结构类似于常规 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="0be82-109">An extension is structured similar to a regular web app.</span></span>  <span data-ttu-id="0be82-110">它至少包括一个包含基本平台信息的应用清单 JSON 文件、一个定义功能的 JavaScript 文件，以及一个 HTML 和 CSS 文件，用于确定用户界面 \ (的外观（如果需要\) ）。</span><span class="sxs-lookup"><span data-stu-id="0be82-110">At a minimum, it includes an app manifest JSON file that contains basic platform information, a JavaScript file to define functionality, and a HTML and CSS file to determine the look of the user interface \(as required\).</span></span>  <span data-ttu-id="0be82-111">若要直接使用部分浏览器（如窗口或选项卡），必须发送 API 请求并经常按名称引用浏览器。</span><span class="sxs-lookup"><span data-stu-id="0be82-111">To work directly with part of the browser, such as a window or tab, you must send API requests and often reference the browser by name.</span></span>  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge (Chromium) 扩展":::
  <span data-ttu-id="0be82-113">Microsoft Edge \ (Chromium\) 扩展</span><span class="sxs-lookup"><span data-stu-id="0be82-113">A Microsoft Edge \(Chromium\) extension</span></span>  
:::image-end:::  

## <span data-ttu-id="0be82-114">基本指南</span><span class="sxs-lookup"><span data-stu-id="0be82-114">Basic guidance</span></span>  

<span data-ttu-id="0be82-115">要构建的一些最受欢迎的浏览器包括 Safari、Firefox、Chrome、Opera、Opera 和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="0be82-115">Some of the most popular browsers to build for include Safari, Firefox, Chrome, Opera, Brave, and Microsoft Edge.</span></span>  <span data-ttu-id="0be82-116">浏览器组织托管的网站是开始扩展开发教程和文档研究的地方。</span><span class="sxs-lookup"><span data-stu-id="0be82-116">Great places to begin your extension development tutorials and documentation research are sites hosted by the browser organizations.</span></span>  <span data-ttu-id="0be82-117">下表并不明确，请使用它作为一个有用的起点。</span><span class="sxs-lookup"><span data-stu-id="0be82-117">The following table is not definitive, please use it as a helpful starting point.</span></span>  

| <span data-ttu-id="0be82-118">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="0be82-118">Web browser</span></span> | <span data-ttu-id="0be82-119">基于 Chromium？</span><span class="sxs-lookup"><span data-stu-id="0be82-119">Chromium-based?</span></span> | <span data-ttu-id="0be82-120">扩展开发主页</span><span class="sxs-lookup"><span data-stu-id="0be82-120">Extension development homepage</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="0be82-121">Safari</span><span class="sxs-lookup"><span data-stu-id="0be82-121">Safari</span></span> | <span data-ttu-id="0be82-122">否</span><span class="sxs-lookup"><span data-stu-id="0be82-122">No</span></span> | [<span data-ttu-id="0be82-123">developer.apple.com/documentation/safariservices/safari_app_extensions</span><span class="sxs-lookup"><span data-stu-id="0be82-123">developer.apple.com/documentation/safariservices/safari_app_extensions</span></span>][AppleDeveloperSafariservicesAppExtensions] |  
| <span data-ttu-id="0be82-124">Firefox</span><span class="sxs-lookup"><span data-stu-id="0be82-124">Firefox</span></span> | <span data-ttu-id="0be82-125">否</span><span class="sxs-lookup"><span data-stu-id="0be82-125">No</span></span> | [<span data-ttu-id="0be82-126">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span><span class="sxs-lookup"><span data-stu-id="0be82-126">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span></span>][MDNWebextensions] |  
| <span data-ttu-id="0be82-127">镶边</span><span class="sxs-lookup"><span data-stu-id="0be82-127">Chrome</span></span> | <span data-ttu-id="0be82-128">是</span><span class="sxs-lookup"><span data-stu-id="0be82-128">Yes</span></span> | [<span data-ttu-id="0be82-129">developer.chrome.com/extensions</span><span class="sxs-lookup"><span data-stu-id="0be82-129">developer.chrome.com/extensions</span></span>][ChromeDeveloperExtensions] |  
| <span data-ttu-id="0be82-130">Opera</span><span class="sxs-lookup"><span data-stu-id="0be82-130">Opera</span></span> | <span data-ttu-id="0be82-131">是</span><span class="sxs-lookup"><span data-stu-id="0be82-131">Yes</span></span> | [<span data-ttu-id="0be82-132">dev.opera.com/extensions</span><span class="sxs-lookup"><span data-stu-id="0be82-132">dev.opera.com/extensions</span></span>][OperaDevExtensions] |  
| <span data-ttu-id="0be82-133">百万</span><span class="sxs-lookup"><span data-stu-id="0be82-133">Brave</span></span> | <span data-ttu-id="0be82-134">是</span><span class="sxs-lookup"><span data-stu-id="0be82-134">Yes</span></span> | <span data-ttu-id="0be82-135">使用 [Chrome Web 应用商店][GoogleChromeWebstoreCategoryExtensions]</span><span class="sxs-lookup"><span data-stu-id="0be82-135">Uses [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span></span> |  
| <span data-ttu-id="0be82-136">新 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0be82-136">new Microsoft Edge</span></span> | <span data-ttu-id="0be82-137">是</span><span class="sxs-lookup"><span data-stu-id="0be82-137">Yes</span></span> | [<span data-ttu-id="0be82-138">developer.microsoft.com/microsoft-edge/extensions</span><span class="sxs-lookup"><span data-stu-id="0be82-138">developer.microsoft.com/microsoft-edge/extensions</span></span>][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> <span data-ttu-id="0be82-139">许多网站教程使用与要开发浏览器不匹配的特定于浏览器的 API。</span><span class="sxs-lookup"><span data-stu-id="0be82-139">Many of the tutorials of the sites use browser-specific APIs that may not match the browser for which you are developing.</span></span>  <span data-ttu-id="0be82-140">在大多数情况下，Chromium 扩展的工作方式与不同 Chromium 浏览器相同，API 按预期工作。</span><span class="sxs-lookup"><span data-stu-id="0be82-140">In most cases, a Chromium extension works as-is in different Chromium browsers and the APIs work as expected.</span></span>  <span data-ttu-id="0be82-141">只有一些不太常见的 API 可能完全特定于浏览器。</span><span class="sxs-lookup"><span data-stu-id="0be82-141">Only some less common APIs may be strictly browser-specific.</span></span>  <span data-ttu-id="0be82-142">有关指向教程的链接，请参阅 [另请参阅](#see-also)。</span><span class="sxs-lookup"><span data-stu-id="0be82-142">For links to the tutorials, see [See also](#see-also).</span></span>  

## <span data-ttu-id="0be82-143">为什么使用 Chromium？</span><span class="sxs-lookup"><span data-stu-id="0be82-143">Why Chromium?</span></span>

<span data-ttu-id="0be82-144">如果您的目标是将扩展发布到尽可能多的浏览器扩展存储，则必须针对多个版本对其进行修改，以便定位并在每个不同的浏览器环境中运行。</span><span class="sxs-lookup"><span data-stu-id="0be82-144">If your goal is to publish your extension to as many browser extensions stores as possible, it must be modified for multiple versions in order to target and run in each distinct browser environment.</span></span>  <span data-ttu-id="0be82-145">[与其他扩展][AppleDeveloperSafariservicesAppExtensions]类型不同，Safari 扩展可能利用 Web 和本机代码与对应的本机应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="0be82-145">[Safari extensions][AppleDeveloperSafariservicesAppExtensions], unlike other extension types, may leverage both web and native code to communicate with counterpart native applications.</span></span>  <span data-ttu-id="0be82-146">[Firefox 扩展][MDNWebextensions] 与其他扩展类型共享得更为常见，但还需要考虑 [一些][ExtensionworkshopPorting] 差异。</span><span class="sxs-lookup"><span data-stu-id="0be82-146">[Firefox extensions][MDNWebextensions] share more in common with the other extension types but there are also some [differences][ExtensionworkshopPorting] to consider.</span></span>  <span data-ttu-id="0be82-147">但是，有一些好消息;上图中的最后四个浏览器能够利用同一代码包，并最大限度地减少更改和维护并行版本的需求。</span><span class="sxs-lookup"><span data-stu-id="0be82-147">However, there is some good news; the last four browsers in the chart above are able to leverage the same code package and minimize the requirement to alter and maintain parallel versions.</span></span>  <span data-ttu-id="0be82-148">这是因为浏览器基于 [Chromium 开放源代码项目][|::ref1::|Home]。</span><span class="sxs-lookup"><span data-stu-id="0be82-148">That is because the browsers are based on the [Chromium open-source project][|::ref1::|Home].</span></span>  

<span data-ttu-id="0be82-149">通过创建 Chromium 扩展，您可以编写最少的代码，以最大程度地增加目标扩展存储的数量，并最终增加能够查找和获取扩展的用户数。</span><span class="sxs-lookup"><span data-stu-id="0be82-149">Creating a Chromium extension enables you to write the least amount of code to maximize both the number of extension stores you are targeting and ultimately the number of users that are able to find and acquire your extension.</span></span>  

<span data-ttu-id="0be82-150">以下内容主要侧重于 Chromium 扩展。</span><span class="sxs-lookup"><span data-stu-id="0be82-150">The following content focuses mostly on Chromium extensions.</span></span>  

## <span data-ttu-id="0be82-151">浏览器兼容性和扩展测试</span><span class="sxs-lookup"><span data-stu-id="0be82-151">Browser compatibility and extension testing</span></span>  

<span data-ttu-id="0be82-152">有时，Chromium 浏览器之间不存在 API 奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="0be82-152">Occasionally, API parity does not exist between Chromium browsers.</span></span>  <span data-ttu-id="0be82-153">例如，标识和付款 API 存在差异。</span><span class="sxs-lookup"><span data-stu-id="0be82-153">For example, there are differences in the identity and payment APIs.</span></span>  <span data-ttu-id="0be82-154">若要确保扩展符合客户期望，请通过官方浏览器文档（如[Chrome API、Opera][ChromeDeveloperExtensionsApiIndex]中支持的[][OperaDevExtensionsApis]扩展 API 和 Microsoft [ (Chromium][ExtensionsChromiumDeveloperGuidePortChrome]) Edge 的端口 Chrome 扩展）查看 API 状态。</span><span class="sxs-lookup"><span data-stu-id="0be82-154">To ensure your extension meets customer expectations, review API statuses through official browser documentation such as [Chrome APIs][ChromeDeveloperExtensionsApiIndex], [Extension APIs Supported in Opera][OperaDevExtensionsApis], and [Port Chrome Extension To Microsoft (Chromium) Edge][ExtensionsChromiumDeveloperGuidePortChrome].</span></span>  

<span data-ttu-id="0be82-155">根据你需要的 API，这些差异可能意味着你必须创建略有不同的代码包，每个存储的代码差异很小。</span><span class="sxs-lookup"><span data-stu-id="0be82-155">Depending on the APIs that you require, these differences may mean that you must create slightly different code packages with small differences in the code for each store.</span></span>  

<span data-ttu-id="0be82-156">开发扩展时，你可以先在浏览器中旁加载它，以在不同环境中测试它，然后再将扩展提交到浏览器存储。</span><span class="sxs-lookup"><span data-stu-id="0be82-156">When developing your extension, you may sideload it in your browser to test it in different environments before submitting your extension to browser stores.</span></span>  

## <span data-ttu-id="0be82-157">将扩展发布到浏览器存储</span><span class="sxs-lookup"><span data-stu-id="0be82-157">Publish your extension to browser stores</span></span>  

<span data-ttu-id="0be82-158">你可以提交并查找以下浏览器存储中的浏览器扩展。</span><span class="sxs-lookup"><span data-stu-id="0be82-158">You may submit and seek browser extensions in the following browser stores.</span></span>  

*   [<span data-ttu-id="0be82-159">Firefox 浏览器加载项</span><span class="sxs-lookup"><span data-stu-id="0be82-159">Firefox Browser Add-ons</span></span>][MozillaAddonsFirefoxExtensions]  
*   [<span data-ttu-id="0be82-160">Chrome Web Store</span><span class="sxs-lookup"><span data-stu-id="0be82-160">Chrome Web Store</span></span>][GoogleChromeWebstoreCategoryExtensions]  
*   [<span data-ttu-id="0be82-161">操作加载项</span><span class="sxs-lookup"><span data-stu-id="0be82-161">Opera addons</span></span>][OperaAddonsExtensions]  
*   [<span data-ttu-id="0be82-162">Microsoft Edge 加载项</span><span class="sxs-lookup"><span data-stu-id="0be82-162">Microsoft Edge Add-ons</span></span>][MicrosoftEdgeAddonsCategoryExtensions]  

<span data-ttu-id="0be82-163">某些应用商店允许你从其他浏览器下载列出的扩展。</span><span class="sxs-lookup"><span data-stu-id="0be82-163">Some stores allow you to download listed extensions from other browsers.</span></span>  <span data-ttu-id="0be82-164">从另一个浏览器下载可以提前节省开发人员 \ (\) 工作量，并删除在用户能够跨不同浏览器导航到现有应用商店一览时提交到其他应用商店的要求。</span><span class="sxs-lookup"><span data-stu-id="0be82-164">Downloading from from another browser may save you \(the developer\) effort upfront and remove the requirement to submit to additional stores if users are able to navigate to the existing store listings across different browsers.</span></span>  <span data-ttu-id="0be82-165">但是，浏览器存储无法保证跨浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="0be82-165">However, cross-browser access is not guaranteed by browser stores.</span></span>  <span data-ttu-id="0be82-166">若要确保用户能够在不同的浏览器中查找扩展，应维护每个浏览器扩展存储上的一览。</span><span class="sxs-lookup"><span data-stu-id="0be82-166">To ensure your users are able to find your extension in different browsers, you should maintain a listing on each browser extension store.</span></span>  

<span data-ttu-id="0be82-167">扩展可能具有经常使用多个浏览器的重叠访问群体，或者你可能会发现它应面向之前没有访问群体。</span><span class="sxs-lookup"><span data-stu-id="0be82-167">An extension may have overlapping audiences that often use multiple browsers, or you may discover that it should be targeting an audience that it has not before.</span></span>  <span data-ttu-id="0be82-168">为此，现有 Chromium 扩展可能从一个浏览器迁移到另一个浏览器。</span><span class="sxs-lookup"><span data-stu-id="0be82-168">To make this happen, existing Chromium extensions may be migrated from one browser to another.</span></span>  

### <span data-ttu-id="0be82-169">将现有扩展迁移到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0be82-169">Migrate an existing extension to Microsoft Edge</span></span>  

<span data-ttu-id="0be82-170">如果你已针对另一个 Chromium 浏览器开发了扩展，并且想要提供它并确保它通过 Microsoft Edge 运行，则不需要重写扩展。</span><span class="sxs-lookup"><span data-stu-id="0be82-170">If you already developed an extension for another Chromium browser and want to offer it and ensure it works through Microsoft Edge, you do not have to rewrite your extension.</span></span>  <span data-ttu-id="0be82-171">将现有 Chromium 扩展迁移到其他 Chromium 浏览器非常简单，只要你使用的 API 在不同浏览器上可用，或者存在提供所需功能的其他 API。</span><span class="sxs-lookup"><span data-stu-id="0be82-171">Migrating existing Chromium extensions to other Chromium browsers is straightforward as long as the APIs you use are available on different browsers or there are other APIs that provide the required functionality.</span></span>  

<span data-ttu-id="0be82-172">有关移植 Chrome 扩展详细信息，请参阅将 Chrome 扩展移植到 Microsoft ([Chromium) Edge。][ExtensionsChromiumDeveloperGuidePortChrome]</span><span class="sxs-lookup"><span data-stu-id="0be82-172">For more information on porting your Chrome extension, see [Port Chrome extensions to Microsoft (Chromium) Edge][ExtensionsChromiumDeveloperGuidePortChrome].</span></span>  <span data-ttu-id="0be82-173">将扩展移植到目标浏览器后，下一步是发布它。</span><span class="sxs-lookup"><span data-stu-id="0be82-173">Once you have ported your extension to the target browser, the next step is to publish it.</span></span>  

### <span data-ttu-id="0be82-174">发布到 Microsoft Edge 加载项网站</span><span class="sxs-lookup"><span data-stu-id="0be82-174">Publishing to the Microsoft Edge add-ons website</span></span>  

<span data-ttu-id="0be82-175">若要开始将扩展发布到 Microsoft Edge，必须使用[][MicrosoftDeveloperRegistration]MSA 电子邮件帐户 \ (@outlook.com、@live.com 等注册开发人员帐户\) 才能在应用商店中提交扩展列表。</span><span class="sxs-lookup"><span data-stu-id="0be82-175">To get started publishing your extension to Microsoft Edge, you must [register for a developer account][MicrosoftDeveloperRegistration] with a MSA email account \(@outlook.com, @live.com, and so on\) to submit your extension listing in the store.</span></span>  <span data-ttu-id="0be82-176">选择要注册的电子邮件地址时，请考虑是否必须与组织其他人转移或共享扩展的所有权。</span><span class="sxs-lookup"><span data-stu-id="0be82-176">When choosing an email address to register, consider if you must transfer or share ownership of the extension with others in your organization.</span></span>  <span data-ttu-id="0be82-177">注册完成后，你可以创建新的到应用商店的扩展提交。</span><span class="sxs-lookup"><span data-stu-id="0be82-177">After registration is complete, you may create a new extension submission to the store.</span></span>  

<span data-ttu-id="0be82-178">若要将扩展提交到应用商店，必须满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="0be82-178">To submit your extension to the store, you must meet the following requirements.</span></span>  

*   <span data-ttu-id="0be82-179">包含代码文件的存档 \ (.zip\) 文件。</span><span class="sxs-lookup"><span data-stu-id="0be82-179">An archive \(.zip\) file that contains your code files.</span></span>  
*   <span data-ttu-id="0be82-180">所有必需的视觉资源，包括徽标和小型促销磁贴。</span><span class="sxs-lookup"><span data-stu-id="0be82-180">All required visual assets, which includes a logo and small promotional tile.</span></span>  
*   <span data-ttu-id="0be82-181">可选促销媒体，如屏幕截图、较大的促销磁贴、URL 或你的扩展视频的任意组合。</span><span class="sxs-lookup"><span data-stu-id="0be82-181">Optional promotional media, such as screenshots, larger promotional tiles, a URL, or any combination to videos of your extension.</span></span>  
*   <span data-ttu-id="0be82-182">描述扩展的信息，例如名称、简短说明、长描述和隐私策略链接。</span><span class="sxs-lookup"><span data-stu-id="0be82-182">Information that describes your extension such as the name, short description, long description, and a link to your privacy policy.</span></span>  

> [!NOTE]
> <span data-ttu-id="0be82-183">不同的应用商店可能有不同的提交要求。</span><span class="sxs-lookup"><span data-stu-id="0be82-183">Different stores may have different submission requirements.</span></span>  <span data-ttu-id="0be82-184">上述列表 [总结了向][ExtensionsChromiumPublish] Microsoft Edge 发布扩展的要求。</span><span class="sxs-lookup"><span data-stu-id="0be82-184">The above list summarizes the [requirements][ExtensionsChromiumPublish] for publishing an extension to Microsoft Edge.</span></span>  

<span data-ttu-id="0be82-185">完成提交过程后，你的扩展将经过审查，并且通过或未能通过认证过程。</span><span class="sxs-lookup"><span data-stu-id="0be82-185">After you complete the submission process, your extension is reviewed and either passes or fails the certification process.</span></span>  <span data-ttu-id="0be82-186">将通知所有者结果，并按需要提供下一步。</span><span class="sxs-lookup"><span data-stu-id="0be82-186">Owners are notified of the outcome and given next steps as required.</span></span>  <span data-ttu-id="0be82-187">如果向应用商店提交更新的扩展，包括扩展一览详细信息的更新，将启动新的审阅过程。</span><span class="sxs-lookup"><span data-stu-id="0be82-187">If you submit an updated extension to the store, including updates to the extension listing details, a new review process is started.</span></span>  

## <span data-ttu-id="0be82-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0be82-188">See also</span></span>  

*   [<span data-ttu-id="0be82-189">移植 Google Chrome 扩展</span><span class="sxs-lookup"><span data-stu-id="0be82-189">Porting a Google Chrome extension</span></span>][ExtensionworkshopPorting]  
*   [<span data-ttu-id="0be82-190">生成 Safari 应用扩展</span><span class="sxs-lookup"><span data-stu-id="0be82-190">Building a Safari App Extension</span></span>][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [<span data-ttu-id="0be82-191">Firefox (的第一个) </span><span class="sxs-lookup"><span data-stu-id="0be82-191">Your first extension (Firefox)</span></span>][MDNWebextensionsYourFirst]  
*   [<span data-ttu-id="0be82-192">Chrome (入门) </span><span class="sxs-lookup"><span data-stu-id="0be82-192">Getting Started Tutorial (Chrome)</span></span>][ChromeDeveloperExtensionsGetstarted]  
*   [<span data-ttu-id="0be82-193">操作 (入门) </span><span class="sxs-lookup"><span data-stu-id="0be82-193">Getting Started (Opera)</span></span>][OperaDevExtensionsGettingStarted]  
*   [<span data-ttu-id="0be82-194">Microsoft Edge (Chromium) 扩展入门</span><span class="sxs-lookup"><span data-stu-id="0be82-194">Getting Started With Microsoft Edge (Chromium) Extensions</span></span>][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "将 Chrome 扩展移植到 Microsoft (Chromium) Edge |Microsoft Docs"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge (Chromium) 扩展入门 |Microsoft Docs"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "发布扩展 |Microsoft Docs"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "开发 Microsoft Edge 扩展 |Microsoft 开发人员"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "合作伙伴中心 |Microsoft 开发人员"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 的扩展 |Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari 应用扩展 |Apple 开发人员"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "生成 Safari 应用扩展 |Apple 开发人员"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "什么是扩展？ |Chrome 开发人员"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome API |Chrome 开发人员"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "入门教程 |Chrome 开发人员"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "移植 Google Chrome 扩展 |扩展研讨会"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "扩展 |Chrome Web Store"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "浏览器扩展 |MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "你的第一个扩展 |MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "扩展 |Firefox 加载项"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "扩展 |Opera Addons"  

[OperaDevExtensions]: https://dev.opera.com/extensions "扩展文档 |Dev.Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "操作中支持的扩展 API |Dev.Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "入门 |Dev.Opera"  
