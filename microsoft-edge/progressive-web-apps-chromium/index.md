---
description: 渐进式 Web 应用 (Chromium) 在 Windows 10 上本地运行。  下面是作为 Web 开发人员需要知道的一切信息。
title: Windows 上的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/17/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 Web 应用， PWA， Edge， JavaScript， Windows， UWP， Microsoft Store
ms.openlocfilehash: a13f39dc3b3e0d47ad07b0e447556dc14093e71b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231214"
---
# <span data-ttu-id="19ff9-105">Windows 上的渐进式 Web 应用概述</span><span class="sxs-lookup"><span data-stu-id="19ff9-105">Progressive Web Apps on Windows overview</span></span>  

<span data-ttu-id="19ff9-106">[渐进式 Web][MDNApps] 应用 \ (PWA\) 提供对开放 Web 技术的访问权限，实现跨平台互操作性，并为用户提供为设备自定义的本机、类似应用的体验。</span><span class="sxs-lookup"><span data-stu-id="19ff9-106">[Progressive Web Apps][MDNApps] \(PWAs\) provide access to open web technologies for cross-platform interoperability and provide your users with a native, app-like experience customized for their devices.</span></span>  <span data-ttu-id="19ff9-107">PWA 是逐步增强的网站 [，其功能][AListApartUnderstandingProgressiveEnhancement] 与支持平台上的本机应用类似。</span><span class="sxs-lookup"><span data-stu-id="19ff9-107">PWAs are websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="19ff9-108">PWA 的特性结合了最好的 Web 和本机应用。</span><span class="sxs-lookup"><span data-stu-id="19ff9-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [<span data-ttu-id="19ff9-109">可发现</span><span class="sxs-lookup"><span data-stu-id="19ff9-109">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="19ff9-110">从 Web 搜索结果和支持的应用商店</span><span class="sxs-lookup"><span data-stu-id="19ff9-110">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [<span data-ttu-id="19ff9-111">可安装</span><span class="sxs-lookup"><span data-stu-id="19ff9-111">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="19ff9-112">从主屏幕、"开始"菜单、任务栏等固定和启动</span><span class="sxs-lookup"><span data-stu-id="19ff9-112">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [<span data-ttu-id="19ff9-113">可重新参与</span><span class="sxs-lookup"><span data-stu-id="19ff9-113">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="19ff9-114">发送推送通知，即使应用不处于活动状态</span><span class="sxs-lookup"><span data-stu-id="19ff9-114">Send push notifications, even when the app is not active</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [<span data-ttu-id="19ff9-115">独立于网络</span><span class="sxs-lookup"><span data-stu-id="19ff9-115">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="19ff9-116">在低网络条件下脱机工作</span><span class="sxs-lookup"><span data-stu-id="19ff9-116">Works offline and in low-network conditions</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [<span data-ttu-id="19ff9-117">渐进</span><span class="sxs-lookup"><span data-stu-id="19ff9-117">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="19ff9-118">体验通过 (功能) 向上或向下扩展</span><span class="sxs-lookup"><span data-stu-id="19ff9-118">Experience scales up (or down) with device capabilities</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [<span data-ttu-id="19ff9-119">安全</span><span class="sxs-lookup"><span data-stu-id="19ff9-119">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="19ff9-120">提供安全的 HTTPS 终结点和其他用户安全措施</span><span class="sxs-lookup"><span data-stu-id="19ff9-120">Provides a secure HTTPS endpoint and other user safeguards</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [<span data-ttu-id="19ff9-121">响应</span><span class="sxs-lookup"><span data-stu-id="19ff9-121">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="19ff9-122">适应用户的屏幕大小或方向和输入方法</span><span class="sxs-lookup"><span data-stu-id="19ff9-122">Adapts to the user's screen size or orientation and input method</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [<span data-ttu-id="19ff9-123">可链接</span><span class="sxs-lookup"><span data-stu-id="19ff9-123">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="19ff9-124">从标准超链接共享和启动</span><span class="sxs-lookup"><span data-stu-id="19ff9-124">Share and launch from a standard hyperlink</span></span>
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


<span data-ttu-id="19ff9-125">生成 \ (或转换\) 现有网站转换为 PWA，以增强用户参与度。</span><span class="sxs-lookup"><span data-stu-id="19ff9-125">Build \(or convert\) your existing website to a PWA to enhance your engagement with your users.</span></span>  <span data-ttu-id="19ff9-126">增强功能包括推送通知、类似应用的集成和脱机支持。</span><span class="sxs-lookup"><span data-stu-id="19ff9-126">Enhancements include push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="19ff9-127">继续构建开放 Web 上的受众，以便用户通过搜索和链接共享发现 PWA。</span><span class="sxs-lookup"><span data-stu-id="19ff9-127">Continue to build your audience on the open web for users to discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="19ff9-128">最好使用 Web 服务器代码更新应用。</span><span class="sxs-lookup"><span data-stu-id="19ff9-128">Best of all, your app is updated in using your web server code.</span></span>  

## <span data-ttu-id="19ff9-129">Microsoft Edge 上的 PWA (Chromium) </span><span class="sxs-lookup"><span data-stu-id="19ff9-129">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="19ff9-130">构建面向 Web 标准 API 的渐进式 Web 应用时，应用程序可能会跨平台和设备部署，并尽可能利用特定于设备的功能。</span><span class="sxs-lookup"><span data-stu-id="19ff9-130">When you build a Progressive Web App targeting web standard APIs, your application may be deployed across platforms and devices and take advantage of the device-specific capabilities as available.</span></span>  <span data-ttu-id="19ff9-131">Microsoft Edge \ (Chromium\) 中的 PWA 为您的网站添加了以下优势。</span><span class="sxs-lookup"><span data-stu-id="19ff9-131">PWAs in Microsoft Edge \(Chromium\) add the following advantages to your website.</span></span>  

*   <span data-ttu-id="19ff9-132">你的应用基于基于标准的 Web 平台构建。</span><span class="sxs-lookup"><span data-stu-id="19ff9-132">Your app is built on a standards-based web platform.</span></span>  
*   <span data-ttu-id="19ff9-133">使用户可以直接从浏览器安装应用。</span><span class="sxs-lookup"><span data-stu-id="19ff9-133">Enables your users to install your app directly from the browser.</span></span>  
*   <span data-ttu-id="19ff9-134">使用户无需基于应用商店的部署或注册即可安装应用。</span><span class="sxs-lookup"><span data-stu-id="19ff9-134">Enables your users to install your app without a Store-based deployment or registration.</span></span>  
    
<span data-ttu-id="19ff9-135">桌面 PWA 在任何 Microsoft Edge \ (Chromium\) 都受支持。</span><span class="sxs-lookup"><span data-stu-id="19ff9-135">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available.</span></span> <span data-ttu-id="19ff9-136">Microsoft Edge \ (Chromium\) 在 Windows 7、Windows 10 和 macOS 上可用。</span><span class="sxs-lookup"><span data-stu-id="19ff9-136">Microsoft Edge \(Chromium\) is available on Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="19ff9-137">其中包括以下好处。</span><span class="sxs-lookup"><span data-stu-id="19ff9-137">The following benefits are included.</span></span>  

*   <span data-ttu-id="19ff9-138">可以直接在浏览器中使用导航栏中的 **"** 安装"图标安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="19ff9-138">Applications may be installed directly from within the browser using the **Install** icon in the navigation bar.</span></span>  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="安装应用程序飞出和图标" lightbox="./media/install_pwa_icon.png":::
       <span data-ttu-id="19ff9-140">安装应用程序飞出和图标</span><span class="sxs-lookup"><span data-stu-id="19ff9-140">Install application flyout and icon</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="19ff9-141">也可以从"设置应用"菜单安装、运行**和管理**  >  \*\*\*\* 应用程序</span><span class="sxs-lookup"><span data-stu-id="19ff9-141">Applications may also be installed, run, and managed from the **Settings** > **Apps** menu</span></span>  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="设置下的应用程序菜单项" lightbox="./media/app_menus.png":::
       <span data-ttu-id="19ff9-143">设置下的应用程序菜单项</span><span class="sxs-lookup"><span data-stu-id="19ff9-143">Application menu items under settings</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="19ff9-144">Web 通知已集成到 Windows 通知系统中</span><span class="sxs-lookup"><span data-stu-id="19ff9-144">Web Notifications are integrated into the Windows notification system</span></span>  
*   <span data-ttu-id="19ff9-145">具有安装应用程序的浏览器配置文件的共享 Cookie 存储</span><span class="sxs-lookup"><span data-stu-id="19ff9-145">Shared cookie store with the browser profile that installed the app</span></span>  
*   <span data-ttu-id="19ff9-146">使用"设置"和更多 **\ (** \) 菜单访问其他浏览器功能，包括证书验证、网站权限、跟踪保护和 `...` 浏览器扩展</span><span class="sxs-lookup"><span data-stu-id="19ff9-146">Access to other browser features using the **Setting and more** \(`...`\) menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>  
*   <span data-ttu-id="19ff9-147">对 [用于调试应用的 Microsoft Edge DevTools][DevtoolsProgressiveWebApps] 的完全访问权限</span><span class="sxs-lookup"><span data-stu-id="19ff9-147">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="19ff9-148">若要专门为使用 JavaScript 提出 WinRT API 请求的 Windows 10 定制 PWA，请导航到[特定于 EdgeHTML PWA 功能的文档][PwaEdgehtmlIndex]。</span><span class="sxs-lookup"><span data-stu-id="19ff9-148">To tailor PWAs specifically for Windows 10 that make WinRT API requests using JavaScript, navigate to [documentation specific to the EdgeHTML PWA features][PwaEdgehtmlIndex].</span></span>  <span data-ttu-id="19ff9-149">了解有关在 Windows 10 上测试 PWA 和在 Microsoft Store 中分发 PWA 的信息。</span><span class="sxs-lookup"><span data-stu-id="19ff9-149">Learn more about testing your PWA on Windows 10 and distributing it in the Microsoft Store.</span></span>  

> [!NOTE]
> <span data-ttu-id="19ff9-150">有关 PWA 权益、即将推出的功能和简短演示的信息，请导航到 Build [2020 PWA 会话][BuildVideo]。</span><span class="sxs-lookup"><span data-stu-id="19ff9-150">For more information about PWA benefits, upcoming features, and short demos, navigate to [Build 2020 PWA session][BuildVideo].</span></span> 

## <span data-ttu-id="19ff9-151">要求</span><span class="sxs-lookup"><span data-stu-id="19ff9-151">Requirements</span></span>  

<span data-ttu-id="19ff9-152">若要作为 PWA 运行，服务器托管的 Web 应用应包含以下最低要求。</span><span class="sxs-lookup"><span data-stu-id="19ff9-152">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-153">HTTPS</span><span class="sxs-lookup"><span data-stu-id="19ff9-153">HTTPS</span></span>][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-154">通过为服务器或应用通信提供安全连接来保护用户。</span><span class="sxs-lookup"><span data-stu-id="19ff9-154">Protects your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="19ff9-155">服务工作人员和其他 PWA 技术仅适用于通过安全连接 \ (或用于调试 `localhost` 目的\) 。</span><span class="sxs-lookup"><span data-stu-id="19ff9-155">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-156">服务工作者</span><span class="sxs-lookup"><span data-stu-id="19ff9-156">Service Workers</span></span>][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-157">使用服务工作线程充当服务器和客户端应用之间的网络代理。</span><span class="sxs-lookup"><span data-stu-id="19ff9-157">Uses Service Worker threads to act as network proxies between your server and client app.</span></span>  <span data-ttu-id="19ff9-158">服务工作线程提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。</span><span class="sxs-lookup"><span data-stu-id="19ff9-158">Service Worker threads provide offline support, resource caching, push notifications, background data sync, and  page-load performance optimizations.</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-159">Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="19ff9-159">Web App Manifest</span></span>][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-160">提供一个基于 JSON 的元数据文件，该文件描述有关 Web 应用的关键信息，以便 Windows 10 和其他主机平台为 PWA 用户提供可安装的本机类似应用的体验。</span><span class="sxs-lookup"><span data-stu-id="19ff9-160">Provides a JSON-based metadata file that describes key information about your web app, so that Windows 10 and other host platforms provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="19ff9-161">关键信息包括图标、语言和 URL 入口点。</span><span class="sxs-lookup"><span data-stu-id="19ff9-161">Key information includes icons, language, and URL entry point.</span></span> 
   :::column-end:::
:::row-end:::  

<span data-ttu-id="19ff9-162">若要成为出色的 PWA，您的应用程序还必须满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="19ff9-162">To be a great PWA, your app must also meet the following requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-163">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="19ff9-163">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-164">通过在不同浏览器和环境 [中进行测试][MicrosoftDeveloperEdgeToolsRemote] ，确保 PWA 正常工作。</span><span class="sxs-lookup"><span data-stu-id="19ff9-164">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-165">响应式设计</span><span class="sxs-lookup"><span data-stu-id="19ff9-165">Responsive design</span></span>][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-166">采用流畅的布局和灵活的图像。</span><span class="sxs-lookup"><span data-stu-id="19ff9-166">Employs fluid layouts and flexible images.</span></span>  <span data-ttu-id="19ff9-167">响应式设计包括以下使用户体验适应用户设备的元素。</span><span class="sxs-lookup"><span data-stu-id="19ff9-167">Responsive design includes the following elements that adapt your UX to your user's device.</span></span>  
      
      *   <span data-ttu-id="19ff9-168">CSS [网格][MDNCssGridLayout]</span><span class="sxs-lookup"><span data-stu-id="19ff9-168">CSS [grid][MDNCssGridLayout]</span></span>  
      *   [<span data-ttu-id="19ff9-169">flexbox</span><span class="sxs-lookup"><span data-stu-id="19ff9-169">flexbox</span></span>][MDNCssFlexibleBoxLayout]  
      *   <span data-ttu-id="19ff9-170">CSS [网格][MDNCssGridLayout] 和 [弹性框][MDNCssFlexibleBoxLayout]</span><span class="sxs-lookup"><span data-stu-id="19ff9-170">CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout]</span></span>  
      *   [<span data-ttu-id="19ff9-171">媒体查询</span><span class="sxs-lookup"><span data-stu-id="19ff9-171">media queries</span></span>][MDNMediaQueries]  
      *   [<span data-ttu-id="19ff9-172">响应式图像</span><span class="sxs-lookup"><span data-stu-id="19ff9-172">responsive images</span></span>][MDNResponsiveImages]  
      
      <span data-ttu-id="19ff9-173">使用 [浏览器的设备仿真][DevToolsGuideDeviceModeTestingOtherBrowsers] 工具在本地测试，或在 [Windows][DevtoolsRemoteDebuggingWindows] 或 [Android][DevtoolsRemoteDebuggingIndex] 上创建远程调试会话以直接在目标设备上进行测试。</span><span class="sxs-lookup"><span data-stu-id="19ff9-173">Uses [device emulation tools][DevToolsGuideDeviceModeTestingOtherBrowsers] from your browser to locally test, or create a remote debugging session on [Windows][DevtoolsRemoteDebuggingWindows] or [Android][DevtoolsRemoteDebuggingIndex] to test directly on a target device.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-174">深层链接</span><span class="sxs-lookup"><span data-stu-id="19ff9-174">Deep linking</span></span>][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-175">将网站的每个页面路由到唯一 URL，以便现有用户可以通过社交媒体共享来吸引更广泛的受众。</span><span class="sxs-lookup"><span data-stu-id="19ff9-175">Routes each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-176">验证和测试做法</span><span class="sxs-lookup"><span data-stu-id="19ff9-176">Validation and testing practices</span></span>][Webhint]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-177">使用 [Webhint][Webhint] linter 等代码质量工具优化应用的效率、稳定性、安全性和辅助功能。</span><span class="sxs-lookup"><span data-stu-id="19ff9-177">Uses code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="19ff9-178">Chromium PWA 清单</span><span class="sxs-lookup"><span data-stu-id="19ff9-178">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="19ff9-179">根据 Google 基线 PWA 清单验证 PWA。</span><span class="sxs-lookup"><span data-stu-id="19ff9-179">Verifies your PWA against the Google baseline PWA checklist.</span></span>  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> <span data-ttu-id="19ff9-180">若要将 PWA 转换为 [Microsoft Store][MicrosoftDeveloperStore] 应用程序，请导航到[Microsoft Store (的渐进式 Web 应用) EdgeHTML 应用程序][PwaEdgehtmlMicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="19ff9-180">To turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] application, navigate to [Progressive Web Apps (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  
  
## <span data-ttu-id="19ff9-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19ff9-181">See also</span></span>  

*   [<span data-ttu-id="19ff9-182">实现 PBA 的百万亿元</span><span class="sxs-lookup"><span data-stu-id="19ff9-182">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="19ff9-183">渐进式 Web 应用的渐进路线图</span><span class="sxs-lookup"><span data-stu-id="19ff9-183">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="19ff9-184">具有渐进式 Web 应用的脱机 POST</span><span class="sxs-lookup"><span data-stu-id="19ff9-184">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="19ff9-185">PWA 问答&A</span><span class="sxs-lookup"><span data-stu-id="19ff9-185">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="19ff9-186">Web 上的百元</span><span class="sxs-lookup"><span data-stu-id="19ff9-186">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="19ff9-187">命名渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="19ff9-187">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="19ff9-188">设计和生成不带框架的渐进式 Web (第 1 部分) </span><span class="sxs-lookup"><span data-stu-id="19ff9-188">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="19ff9-189">设计和生成不带框架的渐进式 Web (第 2 部分) </span><span class="sxs-lookup"><span data-stu-id="19ff9-189">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="19ff9-190">设计和生成不带框架的渐进式 Web (第 3 部分) </span><span class="sxs-lookup"><span data-stu-id="19ff9-190">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- links -->  

[DevtoolsRemoteDebuggingIndex]: ../devtools-guide-chromium/remote-debugging/index.md "远程调试 Android 设备入门 |Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "远程调试 Windows 10 设备入门 |Microsoft Docs"  
[DevToolsGuideDeviceModeTestingOtherBrowsers]: ../devtools-guide-chromium/device-mode/testing-other-browsers.md "模拟和测试其他浏览器 |Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps/index.md "调试渐进式 Web 应用 |Microsoft Docs"  
<!--[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "What's new in EdgeHTML 17 | Microsoft Docs"  -->  
<!--[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "What's New in EdgeHTML 14 | Microsoft Docs"  -->  
<span data-ttu-id="19ff9-195">[PwaEdgehtmlIndex]： ../edgehtml/progressive-web-apps/index.md "Windows 上的渐进式 Web (EdgeHTML) |Microsoft Docs"</span><span class="sxs-lookup"><span data-stu-id="19ff9-195">[PwaEdgehtmlIndex]: ../edgehtml/progressive-web-apps/index.md "Progressive Web Apps (EdgeHTML) on Windows | Microsoft Docs"</span></span>  
<span data-ttu-id="19ff9-196">[PwaEdgehtmlMicrosoftStore]： ../edgehtml/progressive-web-apps/microsoft-store.md "Microsoft Store 中的渐进 Web 应用 |Microsoft Docs"</span><span class="sxs-lookup"><span data-stu-id="19ff9-196">[PwaEdgehtmlMicrosoftStore]: ../edgehtml/progressive-web-apps/microsoft-store.md "Progressive Web Apps in the Microsoft Store | Microsoft Docs"</span></span>
<!--PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps/microsoft-store.md#criteria-for-automatic-submission "Criteria for automatic submission - Progressive Web Apps in the Microsoft Store"  -->  

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows 推送通知服务 (WNS) 概述 |Microsoft Docs"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "针对 Xbox 和电视进行设计 |Microsoft Docs"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP 设备的 UI 注意事项 |Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "什么是通用 Windows 平台 (UWP) 应用？ |Microsoft Docs"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "使用后台任务支持你的应用 |Microsoft Docs"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "发布 Windows 应用和游戏 |Microsoft Docs"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "打开开发人员帐户 |Microsoft Docs"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "将渐进式 Web 应用用于 Microsoft Edge 和 Windows 10 - Windows 博客"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "后台同步 API - Microsoft Edge 平台状态"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web 应用程序清单 - Microsoft Edge 平台状态"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "即时测试"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "适用于开发人员的混合现实"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftEdge]: https://www.microsoft.com/edge "下载新的 Microsoft Edge 浏览器"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "在 Windows 10 中打开或关闭焦点辅助"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "更改 Windows 10 中的通知设置"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA 问答&A"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "了解渐进式增强 - 列表分开"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "apps |MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存 |MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "跨浏览器测试 |MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS 弹性框布局 |MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 |MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "Fetch API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "媒体查询 |MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API |MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API |MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "可发现 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "可安装 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "可链接 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "独立于网络 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "渐进 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "重新参与 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "响应 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "安全 - 渐进式 Web 应用优势"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "响应式图像 |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单 |MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA 视频"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "实现 PBA - 新边缘版本"  

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上的百元"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "具有渐进式 Web 应用的脱机 POST"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和构建不带框架的渐进式 Web (第 1 部分) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和生成不带框架的渐进式 Web (第 2 部分) "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和生成不带框架的渐进式 Web 应用程序 (第 3 部分) "  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "什么是良好的渐进式 Web 应用？ |web.dev"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接 - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 Web 设计 - Wikipedia"  
