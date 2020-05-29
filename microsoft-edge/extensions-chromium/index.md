---
description: Microsoft Edge （Chromium）扩展的概述以及基本构建和发布浏览器扩展。
title: Microsoft Edge （Chromium）扩展
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/28/2020
ms.topic: conceptual
ms.prod: microsoft-edge
keywords: 边缘、扩展开发、浏览器扩展、addons、合作伙伴中心、开发人员、chromium 扩展
ms.openlocfilehash: 2c4c34805e93bf6fbae57f1d0230cc821d1f3f65
ms.sourcegitcommit: a5392ab44133d742c0e1fa500ad9a872989b7c3f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2020
ms.locfileid: "10684697"
---
# <span data-ttu-id="5f170-104">Microsoft Edge （Chromium）扩展</span><span class="sxs-lookup"><span data-stu-id="5f170-104">Microsoft Edge (Chromium) Extensions</span></span>  

<span data-ttu-id="5f170-105">扩展是一个小程序，您可以使用该程序（开发人员 \）将新功能添加到 Microsoft Edge \ （Chromium \）或修改现有功能。</span><span class="sxs-lookup"><span data-stu-id="5f170-105">An extension is a small program that you \(the developer\) may use to add new features to Microsoft Edge \(Chromium\) or modify the existing functionality.</span></span>  <span data-ttu-id="5f170-106">扩展旨在通过提供对目标受众非常重要的小功能来改善用户的日常浏览体验。</span><span class="sxs-lookup"><span data-stu-id="5f170-106">An extension is intended to improve a user's day-to-day browsing experience by providing niche functionality that is important to targeted audiences.</span></span>  

<span data-ttu-id="5f170-107">如果你的想法或产品依赖于特定的 web 浏览器的可用性，或者补充你希望提供的功能扩展现有网站的浏览体验，则可以创建扩展。</span><span class="sxs-lookup"><span data-stu-id="5f170-107">You may create extensions if your idea or product depends on the availability of a specific web browser or augments the browsing experience where the functionality that you want to provide extends existing websites.</span></span>  <span data-ttu-id="5f170-108">附带体验的示例包括 adblockers 和密码管理器。</span><span class="sxs-lookup"><span data-stu-id="5f170-108">Examples of companion experiences include adblockers and password managers.</span></span>  

<span data-ttu-id="5f170-109">扩展的结构类似于常规 web 应用。</span><span class="sxs-lookup"><span data-stu-id="5f170-109">An extension is structured similar to a regular web app.</span></span>  <span data-ttu-id="5f170-110">它至少包括一个应用清单 JSON 文件，该文件包含基本平台信息、用于定义功能的 JavaScript 文件，以及用于确定用户界面外观的 HTML 和 CSS 文件 \ （根据需要 \）。</span><span class="sxs-lookup"><span data-stu-id="5f170-110">At a minimum, it includes an app manifest JSON file that contains basic platform information, a JavaScript file to define functionality, and a HTML and CSS file to determine the look of the user interface \(as required\).</span></span>  <span data-ttu-id="5f170-111">若要直接处理部分浏览器（如窗口或选项卡），必须发送 API 请求，并且通常按名称引用浏览器。</span><span class="sxs-lookup"><span data-stu-id="5f170-111">To work directly with part of the browser, such as a window or tab, you must send API requests and often reference the browser by name.</span></span>  

:::image type="complex" source="./media/example-extension-screenshot.png" alt-text="Microsoft Edge （Chromium）扩展":::
  <span data-ttu-id="5f170-113">Microsoft Edge \ （Chromium \）扩展</span><span class="sxs-lookup"><span data-stu-id="5f170-113">A Microsoft Edge \(Chromium\) extension</span></span>  
:::image-end:::  

## <span data-ttu-id="5f170-114">基本指南</span><span class="sxs-lookup"><span data-stu-id="5f170-114">Basic guidance</span></span>  

<span data-ttu-id="5f170-115">一些最热门的浏览器可用于包含 Safari、Firefox、Chrome、Opera、Brave 和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="5f170-115">Some of the most popular browsers to build for include Safari, Firefox, Chrome, Opera, Brave, and Microsoft Edge.</span></span>  <span data-ttu-id="5f170-116">开始扩展开发教程和文档检索的好地方是由浏览器组织托管的网站。</span><span class="sxs-lookup"><span data-stu-id="5f170-116">Great places to begin your extension development tutorials and documentation research are sites hosted by the browser organizations.</span></span>  <span data-ttu-id="5f170-117">下表不是明确的，请将其用作有用的起始点。</span><span class="sxs-lookup"><span data-stu-id="5f170-117">The following table is not definitive, please use it as a helpful starting point.</span></span>  

| <span data-ttu-id="5f170-118">Web 浏览器</span><span class="sxs-lookup"><span data-stu-id="5f170-118">Web browser</span></span> | <span data-ttu-id="5f170-119">基于 Chromium？</span><span class="sxs-lookup"><span data-stu-id="5f170-119">Chromium-based?</span></span> | <span data-ttu-id="5f170-120">扩展开发主页</span><span class="sxs-lookup"><span data-stu-id="5f170-120">Extension development homepage</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="5f170-121">Safari</span><span class="sxs-lookup"><span data-stu-id="5f170-121">Safari</span></span> | <span data-ttu-id="5f170-122">否</span><span class="sxs-lookup"><span data-stu-id="5f170-122">No</span></span> | [<span data-ttu-id="5f170-123">developer.apple.com/documentation/safariservices/safari_app_extensions</span><span class="sxs-lookup"><span data-stu-id="5f170-123">developer.apple.com/documentation/safariservices/safari_app_extensions</span></span>][AppleDeveloperSafariservicesAppExtensions] |  
| <span data-ttu-id="5f170-124">Firefox</span><span class="sxs-lookup"><span data-stu-id="5f170-124">Firefox</span></span> | <span data-ttu-id="5f170-125">否</span><span class="sxs-lookup"><span data-stu-id="5f170-125">No</span></span> | [<span data-ttu-id="5f170-126">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span><span class="sxs-lookup"><span data-stu-id="5f170-126">developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions</span></span>][MDNWebextensions] |  
| <span data-ttu-id="5f170-127">镶边</span><span class="sxs-lookup"><span data-stu-id="5f170-127">Chrome</span></span> | <span data-ttu-id="5f170-128">是</span><span class="sxs-lookup"><span data-stu-id="5f170-128">Yes</span></span> | [<span data-ttu-id="5f170-129">developer.chrome.com/extensions</span><span class="sxs-lookup"><span data-stu-id="5f170-129">developer.chrome.com/extensions</span></span>][ChromeDeveloperExtensions] |  
| <span data-ttu-id="5f170-130">Opera</span><span class="sxs-lookup"><span data-stu-id="5f170-130">Opera</span></span> | <span data-ttu-id="5f170-131">是</span><span class="sxs-lookup"><span data-stu-id="5f170-131">Yes</span></span> | [<span data-ttu-id="5f170-132">dev.opera.com/extensions</span><span class="sxs-lookup"><span data-stu-id="5f170-132">dev.opera.com/extensions</span></span>][OperaDevExtensions] |  
| <span data-ttu-id="5f170-133">Brave</span><span class="sxs-lookup"><span data-stu-id="5f170-133">Brave</span></span> | <span data-ttu-id="5f170-134">是</span><span class="sxs-lookup"><span data-stu-id="5f170-134">Yes</span></span> | <span data-ttu-id="5f170-135">使用[Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span><span class="sxs-lookup"><span data-stu-id="5f170-135">Uses [Chrome Web Store][GoogleChromeWebstoreCategoryExtensions]</span></span> |  
| <span data-ttu-id="5f170-136">新的 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5f170-136">new Microsoft Edge</span></span> | <span data-ttu-id="5f170-137">是</span><span class="sxs-lookup"><span data-stu-id="5f170-137">Yes</span></span> | [<span data-ttu-id="5f170-138">developer.microsoft.com/microsoft-edge/extensions</span><span class="sxs-lookup"><span data-stu-id="5f170-138">developer.microsoft.com/microsoft-edge/extensions</span></span>][MicrosoftDeveloperEdgeExtensions] |  

> [!IMPORTANT]
> <span data-ttu-id="5f170-139">网站的许多教程都使用特定于浏览器的 Api，这些 Api 可能与你要开发的浏览器不匹配。</span><span class="sxs-lookup"><span data-stu-id="5f170-139">Many of the tutorials of the sites use browser-specific APIs that may not match the browser for which you are developing.</span></span>  <span data-ttu-id="5f170-140">在大多数情况下，Chromium 扩展在不同的 Chromium 浏览器中工作，并且 Api 按预期工作。</span><span class="sxs-lookup"><span data-stu-id="5f170-140">In most cases, a Chromium extension works as-is in different Chromium browsers and the APIs work as expected.</span></span>  <span data-ttu-id="5f170-141">只有一些较少的常见 Api 才能严格地特定于浏览器。</span><span class="sxs-lookup"><span data-stu-id="5f170-141">Only some less common APIs may be strictly browser-specific.</span></span>  <span data-ttu-id="5f170-142">有关教程的链接，请参阅另[请参阅](#see-also)。</span><span class="sxs-lookup"><span data-stu-id="5f170-142">For links to the tutorials, see [See also](#see-also).</span></span>  

## <span data-ttu-id="5f170-143">为什么 Chromium</span><span class="sxs-lookup"><span data-stu-id="5f170-143">Why Chromium</span></span>  

<span data-ttu-id="5f170-144">如果你的目标是将扩展发布到尽可能多的浏览器扩展存储，则必须针对多个版本对其进行修改，以便在每个不同的浏览器环境中进行目标和运行。</span><span class="sxs-lookup"><span data-stu-id="5f170-144">If your goal is to publish your extension to as many browser extensions stores as possible, it must be modified for multiple versions in order to target and run in each distinct browser environment.</span></span>  <span data-ttu-id="5f170-145">与其他扩展类型不同， [Safari 扩展][AppleDeveloperSafariservicesAppExtensions]可以利用 web 和本机代码与对应的本机应用程序进行通信。</span><span class="sxs-lookup"><span data-stu-id="5f170-145">[Safari extensions][AppleDeveloperSafariservicesAppExtensions], unlike other extension types, may leverage both web and native code to communicate with counterpart native applications.</span></span>  <span data-ttu-id="5f170-146">[Firefox 扩展][MDNWebextensions]与其他扩展类型共享更多的内容，但也有一些[差异][ExtensionworkshopPorting]需要考虑。</span><span class="sxs-lookup"><span data-stu-id="5f170-146">[Firefox extensions][MDNWebextensions] share more in common with the other extension types but there are also some [differences][ExtensionworkshopPorting] to consider.</span></span>  <span data-ttu-id="5f170-147">但有一些好消息，上面的图表中的最后四个浏览器能够利用相同的代码程序包，并最大程度地减少更改和维护并行版本的要求。</span><span class="sxs-lookup"><span data-stu-id="5f170-147">However, there is some good news; the last four browsers in the chart above are able to leverage the same code package and minimize the requirement to alter and maintain parallel versions.</span></span>  <span data-ttu-id="5f170-148">这是因为浏览器基于[Chromium 开放源代码项目][|::ref1::|Home]。</span><span class="sxs-lookup"><span data-stu-id="5f170-148">That is because the browsers are based on the [Chromium open-source project][|::ref1::|Home].</span></span>  

<span data-ttu-id="5f170-149">通过创建 Chromium 扩展，你可以写入最少的代码，以最大程度地增加目标扩展存储的数量，并且最终可以找到并获取你的扩展的用户数。</span><span class="sxs-lookup"><span data-stu-id="5f170-149">Creating a Chromium extension enables you to write the least amount of code to maximize both the number of extension stores you are targeting and ultimately the number of users that are able to find and acquire your extension.</span></span>  

<span data-ttu-id="5f170-150">以下内容主要关注 Chromium 扩展。</span><span class="sxs-lookup"><span data-stu-id="5f170-150">The following content focuses mostly on Chromium extensions.</span></span>  

## <span data-ttu-id="5f170-151">浏览器兼容性和扩展测试</span><span class="sxs-lookup"><span data-stu-id="5f170-151">Browser compatibility and extension testing</span></span>  

<span data-ttu-id="5f170-152">有时，Chromium 浏览器之间不存在 API 奇偶校验。</span><span class="sxs-lookup"><span data-stu-id="5f170-152">Occasionally, API parity does not exist between Chromium browsers.</span></span>  <span data-ttu-id="5f170-153">例如，标识和支付 Api 之间存在差异。</span><span class="sxs-lookup"><span data-stu-id="5f170-153">For example, there are differences in the identity and payment APIs.</span></span>  <span data-ttu-id="5f170-154">为确保您的扩展满足客户期望值，请通过官方浏览器文档（如[Chrome api][ChromeDeveloperExtensionsApiIndex]、 [Opera 支持的扩展 api][OperaDevExtensionsApis]和[Microsoft （Chromium） Edge 的端口 Chrome 扩展][ExtensionsChromiumDeveloperGuidePortChrome]）查看 API 状态。</span><span class="sxs-lookup"><span data-stu-id="5f170-154">To ensure your extension meets customer expectations, review API statuses through official browser documentation such as [Chrome APIs][ChromeDeveloperExtensionsApiIndex], [Extension APIs Supported in Opera][OperaDevExtensionsApis], and [Port Chrome Extension To Microsoft (Chromium) Edge][ExtensionsChromiumDeveloperGuidePortChrome].</span></span>  

<span data-ttu-id="5f170-155">根据你所需的 Api，这些差异可能意味着你必须在每个应用商店的代码中创建稍有不同的代码包。</span><span class="sxs-lookup"><span data-stu-id="5f170-155">Depending on the APIs that you require, these differences may mean that you must create slightly different code packages with small differences in the code for each store.</span></span>  

<span data-ttu-id="5f170-156">开发扩展时，在将扩展提交到浏览器存储之前，你可以在浏览器中旁加载，以在不同的环境中对其进行测试。</span><span class="sxs-lookup"><span data-stu-id="5f170-156">When developing your extension, you may sideload it in your browser to test it in different environments before submitting your extension to browser stores.</span></span>  

## <span data-ttu-id="5f170-157">将扩展发布到浏览器存储</span><span class="sxs-lookup"><span data-stu-id="5f170-157">Publish your extension to browser stores</span></span>  

<span data-ttu-id="5f170-158">你可以在以下浏览器存储中提交和查找浏览器扩展。</span><span class="sxs-lookup"><span data-stu-id="5f170-158">You may submit and seek browser extensions in the following browser stores.</span></span>  

*   [<span data-ttu-id="5f170-159">Firefox 浏览器加载项</span><span class="sxs-lookup"><span data-stu-id="5f170-159">Firefox Browser Add-ons</span></span>][MozillaAddonsFirefoxExtensions]  
*   [<span data-ttu-id="5f170-160">Chrome Web Store</span><span class="sxs-lookup"><span data-stu-id="5f170-160">Chrome Web Store</span></span>][GoogleChromeWebstoreCategoryExtensions]  
*   [<span data-ttu-id="5f170-161">Opera addons</span><span class="sxs-lookup"><span data-stu-id="5f170-161">Opera addons</span></span>][OperaAddonsExtensions]  
*   [<span data-ttu-id="5f170-162">Microsoft Edge 加载项</span><span class="sxs-lookup"><span data-stu-id="5f170-162">Microsoft Edge Add-ons</span></span>][MicrosoftEdgeAddonsCategoryExtensions]  

<span data-ttu-id="5f170-163">某些商店允许您从其他浏览器下载列出的扩展。</span><span class="sxs-lookup"><span data-stu-id="5f170-163">Some stores allow you to download listed extensions from other browsers.</span></span>  <span data-ttu-id="5f170-164">从另一个浏览器下载时，如果用户能够导航到不同浏览器中的现有应用商店列表，则可能会提前保存您的 "（开发人员 \）" 工作，并删除向其他商店提交的要求。</span><span class="sxs-lookup"><span data-stu-id="5f170-164">Downloading from from another browser may save you \(the developer\) effort upfront and remove the requirement to submit to additional stores if users are able to navigate to the existing store listings across different browsers.</span></span>  <span data-ttu-id="5f170-165">但是，浏览器存储不保证跨浏览器访问。</span><span class="sxs-lookup"><span data-stu-id="5f170-165">However, cross-browser access is not guaranteed by browser stores.</span></span>  <span data-ttu-id="5f170-166">为了确保你的用户能够在不同的浏览器中找到你的扩展，你应该在每个浏览器扩展存储中维护一个列表。</span><span class="sxs-lookup"><span data-stu-id="5f170-166">To ensure your users are able to find your extension in different browsers, you should maintain a listing on each browser extension store.</span></span>  

<span data-ttu-id="5f170-167">扩展可能具有重叠的访问群体，这些受众经常使用多个浏览器，或者你可能会发现它应该面向的读者不是以前的浏览器。</span><span class="sxs-lookup"><span data-stu-id="5f170-167">An extension may have overlapping audiences that often use multiple browsers, or you may discover that it should be targeting an audience that it has not before.</span></span>  <span data-ttu-id="5f170-168">若要实现此目的，现有的 Chromium 扩展可能会从一个浏览器迁移到另一个浏览器。</span><span class="sxs-lookup"><span data-stu-id="5f170-168">To make this happen, existing Chromium extensions may be migrated from one browser to another.</span></span>  

### <span data-ttu-id="5f170-169">将现有扩展迁移到 Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5f170-169">Migrate an existing extension to Microsoft Edge</span></span>  

<span data-ttu-id="5f170-170">如果你已为另一个 Chromium 浏览器开发了扩展，并且想要提供它并确保它通过 Microsoft Edge 工作，则不必重写你的扩展。</span><span class="sxs-lookup"><span data-stu-id="5f170-170">If you already developed an extension for another Chromium browser and want to offer it and ensure it works through Microsoft Edge, you do not have to rewrite your extension.</span></span>  <span data-ttu-id="5f170-171">只要你使用的 Api 在不同的浏览器上可用，或者存在提供所需功能的其他 Api，将现有的 Chromium 扩展迁移到其他 Chromium 浏览器就非常简单。</span><span class="sxs-lookup"><span data-stu-id="5f170-171">Migrating existing Chromium extensions to other Chromium browsers is straightforward as long as the APIs you use are available on different browsers or there are other APIs that provide the required functionality.</span></span>  

<span data-ttu-id="5f170-172">有关移植 Chrome 扩展的详细信息，请参阅移植[到 Microsoft （Chromium）边缘的 chrome 扩展][ExtensionsChromiumDeveloperGuidePortChrome]。</span><span class="sxs-lookup"><span data-stu-id="5f170-172">For more information on porting your Chrome extension, see [Port Chrome extensions to Microsoft (Chromium) Edge][ExtensionsChromiumDeveloperGuidePortChrome].</span></span>  <span data-ttu-id="5f170-173">将扩展移植到目标浏览器后，下一步是发布它。</span><span class="sxs-lookup"><span data-stu-id="5f170-173">Once you have ported your extension to the target browser, the next step is to publish it.</span></span>  

### <span data-ttu-id="5f170-174">发布到 Microsoft Edge 加载项网站</span><span class="sxs-lookup"><span data-stu-id="5f170-174">Publishing to the Microsoft Edge add-ons website</span></span>  

<span data-ttu-id="5f170-175">若要开始将您的扩展发布到 Microsoft Edge，您必须注册一个具有 MSA 电子邮件帐户的[开发者帐户][MicrosoftDeveloperRegistration]\ （@outlook .com，@live .com，依此类推 \），以便在应用商店中提交您的扩展列表。</span><span class="sxs-lookup"><span data-stu-id="5f170-175">To get started publishing your extension to Microsoft Edge, you must [register for a developer account][MicrosoftDeveloperRegistration] with a MSA email account \(@outlook.com, @live.com, and so on\) to submit your extension listing in the store.</span></span>  <span data-ttu-id="5f170-176">选择要注册的电子邮件地址时，请考虑是否必须与组织中的其他人一起转移或共享该扩展名的所有权。</span><span class="sxs-lookup"><span data-stu-id="5f170-176">When choosing an email address to register, consider if you must transfer or share ownership of the extension with others in your organization.</span></span>  <span data-ttu-id="5f170-177">注册完成后，您可以创建一个新的向应用商店提交的扩展。</span><span class="sxs-lookup"><span data-stu-id="5f170-177">After registration is complete, you may create a new extension submission to the store.</span></span>  

<span data-ttu-id="5f170-178">若要将扩展提交到应用商店，必须满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="5f170-178">To submit your extension to the store, you must meet the following requirements.</span></span>  

*   <span data-ttu-id="5f170-179">包含代码文件的存档 \ （.zip）文件。</span><span class="sxs-lookup"><span data-stu-id="5f170-179">An archive \(.zip\) file that contains your code files.</span></span>  
*   <span data-ttu-id="5f170-180">所有所需的视觉资源，包括徽标和小型促销图块。</span><span class="sxs-lookup"><span data-stu-id="5f170-180">All required visual assets, which includes a logo and small promotional tile.</span></span>  
*   <span data-ttu-id="5f170-181">可选促销媒体，如屏幕截图、较大的促销图块、URL 或与您的分机的视频相结合的任意组合。</span><span class="sxs-lookup"><span data-stu-id="5f170-181">Optional promotional media, such as screenshots, larger promotional tiles, a URL, or any combination to videos of your extension.</span></span>  
*   <span data-ttu-id="5f170-182">描述你的扩展的信息，如名称、简短说明、详细说明和指向隐私策略的链接。</span><span class="sxs-lookup"><span data-stu-id="5f170-182">Information that describes your extension such as the name, short description, long description, and a link to your privacy policy.</span></span>  

> [!NOTE]
> <span data-ttu-id="5f170-183">不同的存储可能具有不同的提交要求。</span><span class="sxs-lookup"><span data-stu-id="5f170-183">Different stores may have different submission requirements.</span></span>  <span data-ttu-id="5f170-184">上面的列表总结了将扩展发布到 Microsoft Edge 的[要求][ExtensionsChromiumPublish]。</span><span class="sxs-lookup"><span data-stu-id="5f170-184">The above list summarizes the [requirements][ExtensionsChromiumPublish] for publishing an extension to Microsoft Edge.</span></span>  

<span data-ttu-id="5f170-185">完成提交过程后，将审阅您的扩展，并通过或失败认证过程。</span><span class="sxs-lookup"><span data-stu-id="5f170-185">After you complete the submission process, your extension is reviewed and either passes or fails the certification process.</span></span>  <span data-ttu-id="5f170-186">将通知所有者，并根据需要执行后续步骤。</span><span class="sxs-lookup"><span data-stu-id="5f170-186">Owners are notified of the outcome and given next steps as required.</span></span>  <span data-ttu-id="5f170-187">如果你向应用商店提交更新的扩展名（包括对扩展列表详细信息的更新），则会启动新的审阅过程。</span><span class="sxs-lookup"><span data-stu-id="5f170-187">If you submit an updated extension to the store, including updates to the extension listing details, a new review process is started.</span></span>  

## <span data-ttu-id="5f170-188">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5f170-188">See also</span></span>  

*   [<span data-ttu-id="5f170-189">移植 Google Chrome 扩展</span><span class="sxs-lookup"><span data-stu-id="5f170-189">Porting a Google Chrome extension</span></span>][ExtensionworkshopPorting]  
*   [<span data-ttu-id="5f170-190">构建 Safari 应用扩展</span><span class="sxs-lookup"><span data-stu-id="5f170-190">Building a Safari App Extension</span></span>][AppleDeveloperSafariservicesAppExtensionsBuilding]  
*   [<span data-ttu-id="5f170-191">您的第一个扩展（Firefox）</span><span class="sxs-lookup"><span data-stu-id="5f170-191">Your first extension (Firefox)</span></span>][MDNWebextensionsYourFirst]  
*   [<span data-ttu-id="5f170-192">入门教程（Chrome）</span><span class="sxs-lookup"><span data-stu-id="5f170-192">Getting Started Tutorial (Chrome)</span></span>][ChromeDeveloperExtensionsGetstarted]  
*   [<span data-ttu-id="5f170-193">入门（Opera）</span><span class="sxs-lookup"><span data-stu-id="5f170-193">Getting Started (Opera)</span></span>][OperaDevExtensionsGettingStarted]  
*   [<span data-ttu-id="5f170-194">Microsoft Edge （Chromium）扩展入门</span><span class="sxs-lookup"><span data-stu-id="5f170-194">Getting Started With Microsoft Edge (Chromium) Extensions</span></span>][ExtensionsChromiumGettingStartedIndex]  

<!-- image links -->  

<!-- links -->  

[ExtensionsChromiumDeveloperGuidePortChrome]: ./developer-guide/port-chrome-extension.md "将端口 Chrome 扩展到 Microsoft （Chromium） Edge |Microsoft 文档"  
[ExtensionsChromiumGettingStartedIndex]: ./getting-started/index.md "Microsoft Edge 入门（Chromium）扩展 |Microsoft 文档"  
[ExtensionsChromiumPublish]: ./publish/publish-extension.md "发布扩展 |Microsoft 文档"  

[MicrosoftDeveloperEdgeExtensions]: https://developer.microsoft.com/microsoft-edge/extensions "开发 Microsoft Edge 的扩展 |Microsoft 开发人员"  
[MicrosoftDeveloperRegistration]: https://developer.microsoft.com/registration "合作伙伴中心 |Microsoft 开发人员"  

[MicrosoftEdgeAddonsCategoryExtensions]: https://microsoftedge.microsoft.com/addons/category/Edge-Extensions "Microsoft Edge 的扩展 |Microsoft Edge"  

[AppleDeveloperSafariservicesAppExtensions]: https://developer.apple.com/documentation/safariservices/safari_app_extensions "Safari 应用扩展 |Apple 开发人员"  
[AppleDeveloperSafariservicesAppExtensionsBuilding]: https://developer.apple.com/documentation/safariservices/safari_app_extensions/building_a_safari_app_extension "构建 Safari 应用扩展 |Apple 开发人员"  

[ChromeDeveloperExtensions]: https://developer.chrome.com/extensions "什么是扩展？ |Chrome 开发人员"  
[ChromeDeveloperExtensionsApiIndex]: https://developer.chrome.com/extensions/api_index "Chrome Api |Chrome 开发人员"  
[ChromeDeveloperExtensionsGetstarted]: https://developer.chrome.com/extensions/getstarted "入门教程 |Chrome 开发人员"  

[ChromiumHome]: https://www.chromium.org/Home "Chromium"  

[ExtensionworkshopPorting]: https://extensionworkshop.com/documentation/develop/porting-a-google-chrome-extension "移植 Google Chrome 扩展 |延长研讨会"  

[GoogleChromeWebstoreCategoryExtensions]: https://chrome.google.com/webstore/category/extensions "扩展名 |Chrome Web Store"  

[MDNWebextensions]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions "浏览器扩展 |MDN"  
[MDNWebextensionsYourFirst]: https://developer.mozilla.org/docs/Mozilla/Add-ons/WebExtensions/Your_first_WebExtension "您的第一个扩展 |MDN"  

[MozillaAddonsFirefoxExtensions]: https://addons.mozilla.org/firefox/extensions "扩展名 |Firefox 的加载项"  

[OperaAddonsExtensions]: https://addons.opera.com/extensions "扩展名 |Opera Addons"  

[OperaDevExtensions]: https://dev.opera.com/extensions "扩展文档 |开发人员的 Opera"  
[OperaDevExtensionsApis]: https://dev.opera.com/extensions/apis "Opera 中支持的扩展 Api |开发人员的 Opera"  
[OperaDevExtensionsGettingStarted]: https://dev.opera.com/extensions/getting-started "入门 |开发人员的 Opera"  
