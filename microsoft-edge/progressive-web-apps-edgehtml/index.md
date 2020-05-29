---
description: 累进 Web 应用在 Windows 10 上以本机方式运行。  下面是 web 开发人员需要了解的所有内容。
title: Windows 上的渐进式 Web 应用（EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/28/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 778502f6db9a89da810b4fb59b10e8fb889fa4b5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562580"
---
# <span data-ttu-id="bc10b-105">Windows 上的渐进式 Web 应用（EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="bc10b-105">Progressive Web Apps (EdgeHTML) on Windows</span></span>  

<span data-ttu-id="bc10b-106">通过[渐进式 Web 应用][MDNApps]\ （或只是 PWAs \），你无需在使用开放 Web 技术实现跨平台互操作性和为用户提供针对其设备自定义的本机应用体验之间做出决定。</span><span class="sxs-lookup"><span data-stu-id="bc10b-106">With [Progressive Web Apps][MDNApps] \(or simply PWAs\) you do not have to decide between using open web technologies for cross-platform interoperability and providing your users with a native app-like experience customized for their device.</span></span>  <span data-ttu-id="bc10b-107">这是因为 PWAs 只是一种网站，可在支持平台上[逐渐增强][AListApartUnderstandingProgressiveEnhancement]到类似本机应用之类的功能。</span><span class="sxs-lookup"><span data-stu-id="bc10b-107">That is because PWAs are just websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="bc10b-108">PWA 的特性结合了最好的 Web 和本机应用。</span><span class="sxs-lookup"><span data-stu-id="bc10b-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        ![可发现图标][ImageISearch]
        ### [<span data-ttu-id="bc10b-110">Dsgetdcname</span><span class="sxs-lookup"><span data-stu-id="bc10b-110">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="bc10b-111">从 web 搜索结果和支持应用商店</span><span class="sxs-lookup"><span data-stu-id="bc10b-111">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        ![可安装图标][ImageIPackage]
        ### [<span data-ttu-id="bc10b-113">可安装</span><span class="sxs-lookup"><span data-stu-id="bc10b-113">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="bc10b-114">从主屏幕固定和启动</span><span class="sxs-lookup"><span data-stu-id="bc10b-114">Pin and launch from the home screen</span></span>  
    :::column-end:::
    :::column:::
        ![重新 engageable 图标][ImageIPushNotification]
        ### [<span data-ttu-id="bc10b-116">重新 engageable</span><span class="sxs-lookup"><span data-stu-id="bc10b-116">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="bc10b-117">发送推送通知，即使应用未处于活动状态</span><span class="sxs-lookup"><span data-stu-id="bc10b-117">Send push notifications, even when the app is not active</span></span>  
    :::column-end:::
    :::column:::
        ![网络独立图标][ImageIOffline]
        ### [<span data-ttu-id="bc10b-119">独立于网络</span><span class="sxs-lookup"><span data-stu-id="bc10b-119">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="bc10b-120">在低网络条件下脱机工作</span><span class="sxs-lookup"><span data-stu-id="bc10b-120">Works offline and in low-network conditions</span></span>  
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        !["渐进" 图标][ImageIProgressive]
        ### [<span data-ttu-id="bc10b-122">累进</span><span class="sxs-lookup"><span data-stu-id="bc10b-122">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="bc10b-123">体验通过设备功能放大 \ （向上或向下）</span><span class="sxs-lookup"><span data-stu-id="bc10b-123">Experience scales \(up or down\) with device capabilities</span></span>  
    :::column-end:::
    :::column:::
        ![安全图标][ImageISecurity]
        ### [<span data-ttu-id="bc10b-125">安全</span><span class="sxs-lookup"><span data-stu-id="bc10b-125">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="bc10b-126">提供安全 HTTPS 终结点和其他用户保护</span><span class="sxs-lookup"><span data-stu-id="bc10b-126">Provides a secure HTTPS endpoint and other user safeguards</span></span>  
    :::column-end:::
    :::column:::
        ![响应图标][ImageIResponsive]
        ### [<span data-ttu-id="bc10b-128">响应</span><span class="sxs-lookup"><span data-stu-id="bc10b-128">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="bc10b-129">适应用户的屏幕大小/方向和输入法</span><span class="sxs-lookup"><span data-stu-id="bc10b-129">Adapts to the user's screen size / orientation and input method</span></span>  
    :::column-end:::
    :::column:::
        ![Linkable 图标][ImageILink]
        ### [<span data-ttu-id="bc10b-131">Linkable</span><span class="sxs-lookup"><span data-stu-id="bc10b-131">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="bc10b-132">从标准超链接共享和启动</span><span class="sxs-lookup"><span data-stu-id="bc10b-132">Share and launch from a standard hyperlink</span></span>  
    :::column-end:::
:::row-end:::

<span data-ttu-id="bc10b-133">通过构建现有网站或将其转换为 PWA，你可以通过推送通知和脱机支持更好地与你的现有受众接洽。</span><span class="sxs-lookup"><span data-stu-id="bc10b-133">By building or converting your existing site to a PWA, you are able to better engage your existing audience with push notifications and offline support.</span></span>  <span data-ttu-id="bc10b-134">同时，你可以继续在打开的网站上构建受众，因为用户通过搜索和链接共享发现你的 PWA。</span><span class="sxs-lookup"><span data-stu-id="bc10b-134">At the same time, you are able to continue building your audience on the open web, as users discover your PWA through search and link-sharing.</span></span>  

## <span data-ttu-id="bc10b-135">Windows 10 上的 PWAs （EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="bc10b-135">PWAs on Windows 10 (EdgeHTML)</span></span>  

> [!NOTE]
> <span data-ttu-id="bc10b-136">通过 EdgeHTML 中的 "移动到 Microsoft Edge" （Chromium），PWAs 使用的基础 web 平台是不同的。</span><span class="sxs-lookup"><span data-stu-id="bc10b-136">With the move to Microsoft Edge (Chromium) from EdgeHTML, the underlying web platforms used by PWAs are not the same.</span></span>  <span data-ttu-id="bc10b-137">从浏览器中安装和运行 Edge （Chromium） PWAs。</span><span class="sxs-lookup"><span data-stu-id="bc10b-137">Edge (Chromium) PWAs are installed from and run within the browser.</span></span>  <span data-ttu-id="bc10b-138">Edge （EdgeHTML） PWAs 作为通用 Windows 平台（UWP）应用程序运行，并使用较早的 EdgeHTML web 平台。</span><span class="sxs-lookup"><span data-stu-id="bc10b-138">Edge (EdgeHTML) PWAs run as Universal Windows Platform (UWP) applications and use the older EdgeHTML web platform.</span></span>  <span data-ttu-id="bc10b-139">如果你需要 PWA 的 Windows 10 API 访问，此 EdgeHTML 文档适用于你。</span><span class="sxs-lookup"><span data-stu-id="bc10b-139">If you require Windows 10 API access for your PWA, this EdgeHTML documentation is for you.</span></span>  <span data-ttu-id="bc10b-140">如果你的目标是不带 Windows 特定 API 访问的交叉平台支持，请转到[Microsoft Edge （Chromium） PWA 文档][PwaChromiumIndex]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-140">If your goal is cross platform support without Windows specific API access, please head over to the [Microsoft Edge (Chromium) PWA documentation][PwaChromiumIndex].</span></span>  

<span data-ttu-id="bc10b-141">当你构建渐进式 Web 应用以利用 Windows 10 时，你可以通过[Microsoft Store][MicrosoftDeveloperStore]分发 PWA，每月100万个活动的每月100万个活动的整个 Windows 10 安装群是你的潜在应用受众！</span><span class="sxs-lookup"><span data-stu-id="bc10b-141">When you build a Progressive Web App to take advantage of Windows 10, you are able to distribute your PWA through the [Microsoft Store][MicrosoftDeveloperStore], the entire Windows 10 install base of 600+ million active monthly users is your potential app audience!</span></span>  <span data-ttu-id="bc10b-142">以这种方式开发的应用程序以[通用 Windows 平台][WindowsUWPGetStartedGuide]应用的形式运行，并具有对 WinRT api 的本机类似访问权限。</span><span class="sxs-lookup"><span data-stu-id="bc10b-142">Applications developed this way run as [Universal Windows Platform][WindowsUWPGetStartedGuide] apps and have native like access to the WinRT APIs.</span></span>  <span data-ttu-id="bc10b-143">请注意，在使用 WinRT Api 时，你的代码的 web 平台呈现是 EdgeHTML 的，因此请确保在调用任何特定于 Windows 的 Api 之前使用功能检测，以确保你的 PWA 能够在 Microsoft Edge \ （Chromium \） PWAs 可用的平台上保持运行。</span><span class="sxs-lookup"><span data-stu-id="bc10b-143">Note that the web platform rendering your code is EdgeHTML when using the WinRT APIs so be sure to use feature detection before calling any Windows specific APIs to ensure your PWA is able to still run across platforms where Microsoft Edge \(Chromium\) PWAs are available.</span></span>  

<span data-ttu-id="bc10b-144">[下面介绍如何开始][PwaEdgehtmlGetStarted]将 web 应用转换为 PWA \ （EdgeHTML \），在 Windows 10 上对其进行测试，并将其分发到 Microsoft Store 中。</span><span class="sxs-lookup"><span data-stu-id="bc10b-144">[Here is how to get started][PwaEdgehtmlGetStarted] converting your web app to a PWA \(EdgeHTML\), testing it on Windows 10, and distributing it in the Microsoft Store.</span></span>  

## <span data-ttu-id="bc10b-145">要求</span><span class="sxs-lookup"><span data-stu-id="bc10b-145">Requirements</span></span>  

<span data-ttu-id="bc10b-146">若要以 PWA 的形式运行，您的服务器托管的 web 应用至少需要：</span><span class="sxs-lookup"><span data-stu-id="bc10b-146">To run as a PWA, your server-hosted web app at minimum requires:</span></span>  

*   <span data-ttu-id="bc10b-147">[X] [HTTPS][WikiHttps]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-147">[X] [HTTPS][WikiHttps].</span></span>  <span data-ttu-id="bc10b-148">通过为服务器/应用通信提供安全连接来保护你的用户。</span><span class="sxs-lookup"><span data-stu-id="bc10b-148">Protect your users by providing a secure connection for server/app communication.</span></span>  <span data-ttu-id="bc10b-149">服务工作者和其他 PWA 技术仅适用于通过安全连接提供的 web 资源 \ （或来自 `localhost` 于调试目的 \）。</span><span class="sxs-lookup"><span data-stu-id="bc10b-149">Service workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
  
*   <span data-ttu-id="bc10b-150">[X][服务工作者][MDNServiceWorkerApi]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-150">[X] [Service workers][MDNServiceWorkerApi].</span></span>  <span data-ttu-id="bc10b-151">使用服务工作线程在服务器和客户端应用之间充当网络代理，以便提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。</span><span class="sxs-lookup"><span data-stu-id="bc10b-151">Use service worker threads to act as network proxies between your server and client app in order to provide offline support, resource caching, push notifications, background data sync, and page load perf optimizations.</span></span>  

*   <span data-ttu-id="bc10b-152">[X] [Web app 清单][MDNWebAppManifest]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-152">[X] [Web app manifest][MDNWebAppManifest].</span></span>  <span data-ttu-id="bc10b-153">提供基于 JSON 的元数据文件，描述有关你的 web 应用的关键信息 \ （如图标、语言和 URL 入口点 \），以便 Windows 10 和其他主机平台能够为你的 PWA 用户提供可安装的、具有类似应用的体验。</span><span class="sxs-lookup"><span data-stu-id="bc10b-153">Provide a JSON-based metadata file describing key information about your web app \(such as icons, language, and URL entry point\) so that Windows 10 and other host platforms are able to provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="bc10b-154">将您的网站与 web 应用清单相关联使其能够通过必应索引服务[自动包含在 Microsoft Store 中][PwaEdgehtmlMicrosoftStoreImportingBing]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-154">Associating your site with a web app manifest makes it eligible for [automatic inclusion in the Microsoft Store][PwaEdgehtmlMicrosoftStoreImportingBing] through the Bing indexing service.</span></span>  

<span data-ttu-id="bc10b-155">若要成为绝佳的 PWA，你的应用还需要：</span><span class="sxs-lookup"><span data-stu-id="bc10b-155">To be a great PWA, your app also needs:</span></span>  

*   <span data-ttu-id="bc10b-156">[X][跨浏览器的兼容性][MDNCrossBrowserTesting]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-156">[X] [Cross-browser compatibility][MDNCrossBrowserTesting].</span></span>  <span data-ttu-id="bc10b-157">通过在不同的浏览器和环境中进行[测试][MicrosoftDeveloperEdgeToolsRemote]，确保你的 PWA 正常工作。</span><span class="sxs-lookup"><span data-stu-id="bc10b-157">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  <span data-ttu-id="bc10b-158">在 Windows 10 上，确保在 Microsoft Edge 浏览器中以及在完整的 PWA 体验中同时测试你的应用：作为已安装的独立 Windows 10 应用 \ （由 EdgeHTML 引擎 \ 提供支持）。</span><span class="sxs-lookup"><span data-stu-id="bc10b-158">On Windows 10, be sure to test your app both in the Microsoft Edge browser and also in the full PWA experience: as an installed, standalone Windows 10 app \(powered by the EdgeHTML engine\).</span></span>  
  
*   <span data-ttu-id="bc10b-159">[X][响应式设计][WikiResponsiveWebDesign]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-159">[X] [Responsive design][WikiResponsiveWebDesign].</span></span>  <span data-ttu-id="bc10b-160">使用具有 CSS[网格][MDNCssGridLayout]和/或[flexbox][MDNCssFlexibleBoxLayout]、[媒体查询][MDNMediaQueries]和 [响应式图像[MDNResponsiveImages]的流畅布局和灵活的图像，以将你的 UX 调整到你的用户设备。</span><span class="sxs-lookup"><span data-stu-id="bc10b-160">Employ fluid layouts and flexible images with CSS [grid][MDNCssGridLayout] and/or [flexbox][MDNCssFlexibleBoxLayout], [media queries][MDNMediaQueries], and [responsive images[MDNResponsiveImages] to adapt your UX to your user's device.</span></span>  <span data-ttu-id="bc10b-161">使用浏览器中的设备[仿真工具][DevToolsGuide|::ref1::|]进行本地测试，或设置[远程调试会话][DevToolsProtocolClientsEdgeDevToolsPreview]以在目标设备上直接测试。</span><span class="sxs-lookup"><span data-stu-id="bc10b-161">Use device [emulation tools][DevToolsGuide|::ref1::|] from your browser to test locally, or set up a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>  <span data-ttu-id="bc10b-162">在 Windows 10 上，PWAs \ （EdgeHTML \）还可以针对桌面、手机和平板电脑之外[的外形][WindowsUWPDesignDevicesIndex]规格进行定制，包括[： Xbox 和电视][WindowsUWPDesignDevicesDesigningTv]、 [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub]和[Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality]设备。</span><span class="sxs-lookup"><span data-stu-id="bc10b-162">On Windows 10, PWAs \(EdgeHTML\) are able to also be [tailored for form factors][WindowsUWPDesignDevicesIndex] beyond desktop, phone and tablet, including: [Xbox and TV][WindowsUWPDesignDevicesDesigningTv], [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub], and [Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality] devices.</span></span>  
  
*   <span data-ttu-id="bc10b-163">[X][深层链接][WikiDeepLinking]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-163">[X] [Deep linking][WikiDeepLinking].</span></span>  <span data-ttu-id="bc10b-164">将网站的每个页面路由到唯一的 URL，以便现有用户可以通过社交媒体共享帮助您更多的受众参与。</span><span class="sxs-lookup"><span data-stu-id="bc10b-164">Route each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  

*   <span data-ttu-id="bc10b-165">[X][最佳做法][Webhint]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-165">[X] [Best practices][Webhint].</span></span>  <span data-ttu-id="bc10b-166">使用[webhint][Webhint] linter 之类的代码质量工具来优化应用的效率、可靠性、安全性和辅助功能。</span><span class="sxs-lookup"><span data-stu-id="bc10b-166">Use code quality tools like the [webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  

<span data-ttu-id="bc10b-167">若要将渐进式 Web 应用提交到[Microsoft Store][MicrosoftDeveloperStore]，您必须具有：</span><span class="sxs-lookup"><span data-stu-id="bc10b-167">To submit your Progressive Web App to the [Microsoft Store][MicrosoftDeveloperStore], you must have:</span></span>  

*   <span data-ttu-id="bc10b-168">[X] [Microsoft 开发者帐户][WindowsUWPPublishDeveloperAccount]</span><span class="sxs-lookup"><span data-stu-id="bc10b-168">[X] A [Microsoft developer account][WindowsUWPPublishDeveloperAccount]</span></span>  
*   <span data-ttu-id="bc10b-169">[X] 已完成[发布 Windows 应用的步骤][WindowsUWPPublishIndex]</span><span class="sxs-lookup"><span data-stu-id="bc10b-169">[X] Completed [steps for publishing a Windows app][WindowsUWPPublishIndex]</span></span>  

<span data-ttu-id="bc10b-170">在未来的几个月内，web 会议[特定条件][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]的现有 PWAs 将由必应搜索引擎自动索引为 Microsoft Store \ （在这里，开发人员可以为其 Windows 10 受众直接管理它们）。</span><span class="sxs-lookup"><span data-stu-id="bc10b-170">In the coming months, existing PWAs on the web meeting [specific criteria][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] are auto-indexed by the Bing search engine into the Microsoft Store \(where developers are able to directly manage them for their Windows 10 audience\).</span></span>  

<span data-ttu-id="bc10b-171">有关更多详细信息，请查看[Microsoft Store 中的 PWAs （EdgeHTML）][PwaEdgehtmlMicrosoftStore] 。</span><span class="sxs-lookup"><span data-stu-id="bc10b-171">Check out [PWAs (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore] for further details.</span></span>  

## <span data-ttu-id="bc10b-172">当前可用性</span><span class="sxs-lookup"><span data-stu-id="bc10b-172">Current availability</span></span>  

<span data-ttu-id="bc10b-173">浏览器引擎支持针对多个体系结构组件的渐进 Web 应用调用，最重要的是[获取 API][MDNFetchApi]基础的网络基础结构。</span><span class="sxs-lookup"><span data-stu-id="bc10b-173">Browser engine support for Progressive Web Apps calls for a number of architectural components, the most significant being the networking infrastructure underlying the [Fetch API][MDNFetchApi].</span></span>  <span data-ttu-id="bc10b-174">EdgeHTML 引擎中的 PWA 支持在 Windows 10 1809 版本中完成。</span><span class="sxs-lookup"><span data-stu-id="bc10b-174">PWA support in the EdgeHTML engine was completed in the Windows 10 1809 release.</span></span>  <span data-ttu-id="bc10b-175">对 web 标准的进一步改进，因为该时间不会合并到 EdgeHTML 引擎中，因此请务必运行兼容性测试并使用功能检测，以确保在 EdgeHTML 平台上不支持 PWA 所需的功能。</span><span class="sxs-lookup"><span data-stu-id="bc10b-175">Further improvements to web standards since that time will not be incorporated into the EdgeHTML engine so be sure to run compatibility tests and use feature detection to gracefully fallback should the feature your PWA needs be unsupported on the EdgeHTML platform.</span></span>  

<span data-ttu-id="bc10b-176">对于即将推出的 Microsoft Edge \ （Chromium）版本2020，浏览器平台对这些功能的完全支持，这些功能可在支持 Chromium 浏览器的设备上运行。</span><span class="sxs-lookup"><span data-stu-id="bc10b-176">For the upcoming Microsoft Edge \(Chromium\) release in 2020, the browser platform has full support for these features that work across devices where the Chromium browser is supported.</span></span>  

<span data-ttu-id="bc10b-177">对于 EdgeHTML 和 Windows，此处是基于标准的 PWA 技术的当前状态：</span><span class="sxs-lookup"><span data-stu-id="bc10b-177">For EdgeHTML and Windows, here is the current status of standards-based PWA technologies:</span></span>  

| <span data-ttu-id="bc10b-178">技术</span><span class="sxs-lookup"><span data-stu-id="bc10b-178">Technology</span></span> | <span data-ttu-id="bc10b-179">用途</span><span class="sxs-lookup"><span data-stu-id="bc10b-179">Purpose</span></span> | <span data-ttu-id="bc10b-180">可用性</span><span class="sxs-lookup"><span data-stu-id="bc10b-180">Availability</span></span> | <span data-ttu-id="bc10b-181">使用说明</span><span class="sxs-lookup"><span data-stu-id="bc10b-181">Usage notes</span></span> |  
|:--- |:--- |:--- |:--- |  
| [<span data-ttu-id="bc10b-182">Web 应用程序清单</span><span class="sxs-lookup"><span data-stu-id="bc10b-182">Web Application Manifest</span></span>][MDNWebAppManifest] | <span data-ttu-id="bc10b-183">向主机操作系统提供应用元数据以支持安装和应用商店提升。</span><span class="sxs-lookup"><span data-stu-id="bc10b-183">Provides app metadata to the host OS for enabling installation and app store promotion.</span></span>  <span data-ttu-id="bc10b-184">Microsoft Store 中的 PWAs 所需。</span><span class="sxs-lookup"><span data-stu-id="bc10b-184">Required for PWAs in the Microsoft Store.</span></span>  | [<span data-ttu-id="bc10b-185">在开发中</span><span class="sxs-lookup"><span data-stu-id="bc10b-185">In development</span></span>][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | <span data-ttu-id="bc10b-186">现在，你可以使用[PWA 生成器][|::ref2::|]生成符合 W3C 的 JSON 清单，并将你的应用打包到各种操作系统平台。</span><span class="sxs-lookup"><span data-stu-id="bc10b-186">For now, you are able to use [PWA Builder][|::ref2::|] to generate a W3C-compliant JSON manifest and package your app for various OS platforms.</span></span>  <span data-ttu-id="bc10b-187">对于 Windows，PWA 生成器会将你的 JSON 清单转换为 `.appxmanifest` Windows 10 应用所需的 \ （XML \）格式。</span><span class="sxs-lookup"><span data-stu-id="bc10b-187">For Windows, PWA Builder translates your JSON manifest into the `.appxmanifest` \(XML\) format required by Windows 10 apps.</span></span>  |  
| [<span data-ttu-id="bc10b-188">获取 API</span><span class="sxs-lookup"><span data-stu-id="bc10b-188">Fetch API</span></span>][MDNFetchApi] | <span data-ttu-id="bc10b-189">为页面资源提供异步网络 \ （请求，响应 \）</span><span class="sxs-lookup"><span data-stu-id="bc10b-189">Provides asynchronous networking \(requests, responses\) for page resources</span></span> |<span data-ttu-id="bc10b-190">[EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /内部版本 14393 +</span><span class="sxs-lookup"><span data-stu-id="bc10b-190">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / Build 14393+</span></span> | <span data-ttu-id="bc10b-191">[服务工作者 API][MDNServiceWorkerApi]语法基于基于 Fetch 的网络 api。</span><span class="sxs-lookup"><span data-stu-id="bc10b-191">The [Service Worker API][MDNServiceWorkerApi] syntax is based on Fetch-based networking APIs.</span></span>  <span data-ttu-id="bc10b-192">你还可以更常见地使用[FETCH API][MDNFetchApi]作为一种新式替代方法 `XMLHttpRequest` 。</span><span class="sxs-lookup"><span data-stu-id="bc10b-192">You are able to also use [Fetch API][MDNFetchApi] more generally as a modern alternative to `XMLHttpRequest`.</span></span>  |  
| [<span data-ttu-id="bc10b-193">服务工作者 API</span><span class="sxs-lookup"><span data-stu-id="bc10b-193">Service Worker API</span></span>][MDNServiceWorkerApi] | <span data-ttu-id="bc10b-194">提供支持脱机的 web 应用模型/网络代理，其中事件驱动的脚本独立于网页运行</span><span class="sxs-lookup"><span data-stu-id="bc10b-194">Provides an offline-capable web app model / network proxy, where event-driven scripts run independent of web pages</span></span>  | <span data-ttu-id="bc10b-195">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /内部版本 17133 +</span><span class="sxs-lookup"><span data-stu-id="bc10b-195">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span> | <span data-ttu-id="bc10b-196">EdgeHTML 16 中发运的实验性支持 \ （落后 `Enable Service Workers` 于标志 \）。</span><span class="sxs-lookup"><span data-stu-id="bc10b-196">Experimental support \(behind `Enable Service Workers` flag\) shipped in EdgeHTML 16.</span></span>  <span data-ttu-id="bc10b-197">默认情况下，在 EdgeHTML 17 + 版本中打开。</span><span class="sxs-lookup"><span data-stu-id="bc10b-197">On by default in EdgeHTML 17+ builds.</span></span>  |  
| [<span data-ttu-id="bc10b-198">缓存 API</span><span class="sxs-lookup"><span data-stu-id="bc10b-198">Cache API</span></span>][MDNCache] | <span data-ttu-id="bc10b-199">为网络请求/响应对提供存储机制</span><span class="sxs-lookup"><span data-stu-id="bc10b-199">Provides a storage mechanism for network request/response pairs</span></span> | <span data-ttu-id="bc10b-200">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /内部版本 17133 +</span><span class="sxs-lookup"><span data-stu-id="bc10b-200">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span> | <span data-ttu-id="bc10b-201">请参阅上面的[服务工作程序 API][MDNServiceWorkerApi]注释。</span><span class="sxs-lookup"><span data-stu-id="bc10b-201">See [Service Worker API][MDNServiceWorkerApi] note above.</span></span>  |  
| [<span data-ttu-id="bc10b-202">推送 API</span><span class="sxs-lookup"><span data-stu-id="bc10b-202">Push API</span></span>][MDNPushApi] | <span data-ttu-id="bc10b-203">使服务工作人员能够订阅推送通知</span><span class="sxs-lookup"><span data-stu-id="bc10b-203">Enables a service worker to subscribe to push notifications</span></span> |<span data-ttu-id="bc10b-204">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /内部版本 17133 +</span><span class="sxs-lookup"><span data-stu-id="bc10b-204">[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] / Build 17133+</span></span>| <span data-ttu-id="bc10b-205">请参阅上面的[服务工作程序 API][MDNServiceWorkerApi]注释。</span><span class="sxs-lookup"><span data-stu-id="bc10b-205">See [Service Worker API][MDNServiceWorkerApi] note above.</span></span>  <span data-ttu-id="bc10b-206">Windows 10 应用 \ （包括 PWAs \）需要[Windows 推送通知服务 \ （WNS \）][WindowsUWPControlsPatternTilesNotificationsWns]提供推送通知，该服务支持 W3C [Push API][MDNPushApi]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-206">Windows 10 apps \(including PWAs\) require the [Windows Push Notification Service \(WNS\)][WindowsUWPControlsPatternTilesNotificationsWns] to deliver push notifications, which supports the W3C [Push API][MDNPushApi].</span></span>  |  
| [<span data-ttu-id="bc10b-207">通知 API</span><span class="sxs-lookup"><span data-stu-id="bc10b-207">Notifications API</span></span>][MDNNotificationsApi] | <span data-ttu-id="bc10b-208">允许服务工作人员在推送消息时向用户显示系统通知</span><span class="sxs-lookup"><span data-stu-id="bc10b-208">Enables a service worker to display a system notification to the user upon push message</span></span> | <span data-ttu-id="bc10b-209">[EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /内部版本 14393 +</span><span class="sxs-lookup"><span data-stu-id="bc10b-209">[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] / Build 14393+</span></span> | <span data-ttu-id="bc10b-210">EdgeHTML 中的 Web 通知与 Windows 10[操作中心][MicrosoftSupportWindowsNotificationSettings]完全集成，用户可以在其中管理应用通知和设置[静音时间][MicrosoftSupportWindowsFocusAssist]。</span><span class="sxs-lookup"><span data-stu-id="bc10b-210">Web Notifications in EdgeHTML are fully integrated with the Windows 10 [Action Center][MicrosoftSupportWindowsNotificationSettings], where users are able to manage app notifications and set [Quiet Hours][MicrosoftSupportWindowsFocusAssist].</span></span>  |  
| [<span data-ttu-id="bc10b-211">后台同步 API</span><span class="sxs-lookup"><span data-stu-id="bc10b-211">Background Sync API</span></span>][MDNSyncManager] | <span data-ttu-id="bc10b-212">提供用于通知服务工作人员的 API，用户已重新联机并安排定期事件以将本地数据与服务器同步</span><span class="sxs-lookup"><span data-stu-id="bc10b-212">Provides an API for notifying a service worker that the user has come back online and for scheduling periodic events to synchronize local data with the server</span></span> | [<span data-ttu-id="bc10b-213">在开发中</span><span class="sxs-lookup"><span data-stu-id="bc10b-213">In development</span></span>][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | <span data-ttu-id="bc10b-214">现在，你可以使用本机[WinRT BACKGROUNDTASK API][WindowsUWPLaunchResumeBackgroundTasks]在作为 Windows 10 应用运行时实现 PWA 的后台任务。</span><span class="sxs-lookup"><span data-stu-id="bc10b-214">For now, you are able to use the native [WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks] to implement background tasks for your PWA when it runs as a Windows 10 app.</span></span>  |  

<span data-ttu-id="bc10b-215">以下是 Microsoft Store 对 Windows 10 上的 PWAs 支持的当前状态：</span><span class="sxs-lookup"><span data-stu-id="bc10b-215">Here is the current status of Microsoft Store support for PWAs on Windows 10:</span></span>  

| <span data-ttu-id="bc10b-216">应用商店提交方法</span><span class="sxs-lookup"><span data-stu-id="bc10b-216">Store submission method</span></span> | <span data-ttu-id="bc10b-217">状态</span><span class="sxs-lookup"><span data-stu-id="bc10b-217">Status</span></span> | <span data-ttu-id="bc10b-218">详细信息</span><span class="sxs-lookup"><span data-stu-id="bc10b-218">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="bc10b-219">手动 \ （开发人员已启动 \）</span><span class="sxs-lookup"><span data-stu-id="bc10b-219">Manual \(developer initiated\)</span></span> | <span data-ttu-id="bc10b-220">可用</span><span class="sxs-lookup"><span data-stu-id="bc10b-220">Available</span></span> | <span data-ttu-id="bc10b-221">查看[Microsoft Store 中的 PWAs （EdgeHTML）][PwaEdgehtmlMicrosoftStore]以开始使用。</span><span class="sxs-lookup"><span data-stu-id="bc10b-221">Check out [PWAs (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore] to get started.</span></span>  |  
| <span data-ttu-id="bc10b-222">自动 \ （自动索引为必应 \）</span><span class="sxs-lookup"><span data-stu-id="bc10b-222">Automatic \(auto-indexed with Bing\)</span></span> | <span data-ttu-id="bc10b-223">即将推出</span><span class="sxs-lookup"><span data-stu-id="bc10b-223">Coming soon</span></span> | <span data-ttu-id="bc10b-224">我们[当前正在试验][WindowsBlogsWelcomingPWAsEdgeWindows]PWA 的应用合作伙伴子集的 PWA 加入过程。</span><span class="sxs-lookup"><span data-stu-id="bc10b-224">We are [currently piloting][WindowsBlogsWelcomingPWAsEdgeWindows] the PWA onboarding process with a limited subset of app partners.</span></span>  <span data-ttu-id="bc10b-225">在未来的几个月里，Microsoft 在主流 web 上 PWAs 的欢迎。</span><span class="sxs-lookup"><span data-stu-id="bc10b-225">In the coming months Microsoft welcomes PWAs across the mainstream web to the Microsoft Store.</span></span>  <span data-ttu-id="bc10b-226">[通过 Bing 查看自动 PWA 导入][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]，了解有关 Microsoft Store 自动生成的 PWA 列表要求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="bc10b-226">Check out [Automatic PWA importing with Bing][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] to learn more about Microsoft Store requirements for auto-generated PWA listings.</span></span>  |  

<!-- image links -->  

[ImageISearch]: media/i_search.png  
[ImageIPackage]: media/i_package.png  
[ImageIPushNotification]: media/i_push-notification.png  
[ImageIOffline]: media/i_offline.png  
[ImageIProgressive]: media/i_progressive.png  
[ImageISecurity]: media/i_security.png  
[ImageIResponsive]: media/i_responsive.png  
[ImageILink]: media/i_link.png  

<!-- links -->  

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "仿真"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 中的新增功能"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 中的新增功能"  
[PwaChromiumIndex]: ../progressive-web-apps-chromium/index.md "Windows 上的渐进式 Web 应用（Chromium）"  
[PwaEdgehtmlGetStarted]: ../progressive-web-apps-edgehtml/get-started.md "渐进式 Web 应用（EdgeHTML）入门"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store 中的渐进式 Web 应用"
[PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps-edgehtml/microsoft-store.md#criteria-for-automatic-submission "Microsoft Store 中自动提交-渐进 Web 应用的标准"  
[PwaEdgehtmlMicrosoftStoreImportingBing]: microsoft-store.md#automatic-pwa-importing-with-bing "在 Microsoft Store 中通过 Bing-累进 Web 应用（EdgeHTML）自动导入 PWA"  


[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows 推送通知服务 \ （WNS \）概述"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "针对 Xbox 和电视进行设计"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP 设备的 UI 注意事项"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "什么是通用 Windows 平台（UWP）应用？"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "支持带有后台任务的应用"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "发布 Windows 应用和游戏"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "打开开发者帐户"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "欢迎向 Microsoft Edge 和 Windows 10 进行渐进式 Web 应用-Windows 博客"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "后台同步 API-Microsoft Edge 平台状态"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web 应用程序清单-Microsoft Edge 平台状态"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "即时测试"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "开发人员的混合现实"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft 开发人员应用商店"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "在 Windows 10 中打开或关闭 "聚焦助手""  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "在 Windows 10 中更改通知设置"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "了解渐进式增强-列表分离"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "应用 |MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "跨浏览器测试 |MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS 弹性框布局 |MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 |MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "获取 API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "媒体查询 |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "可发现-渐进 web app 的优势"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "可安装-渐进式 web 应用的优势"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "Linkable-渐进式 web 应用的优势"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "网络独立-渐进式 web 应用的优势"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "渐进渐进的 web 应用优势"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "Engageable-渐进式 web 应用的优势"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "响应性-渐进式 web 应用的优势"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "安全-渐进式 web 应用的优势"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "响应图像 |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接-维基百科"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-维基百科"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 web 设计-维基百科"  
