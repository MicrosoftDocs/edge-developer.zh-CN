---
description: 渐进式 Web (Chromium) 在本机运行Windows 10。  下面是作为 Web 开发人员需要知道的所有内容。
title: Windows 上的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 Web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: f1f5370af0710927f66c8231274fe307cb3ee2a4
ms.sourcegitcommit: 7f7922dbb6af87ecac1378d18359125770c5b8e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11536807"
---
# <a name="progressive-web-apps-on-windows-overview"></a><span data-ttu-id="e6d47-105">渐进式 Web 应用Windows概述</span><span class="sxs-lookup"><span data-stu-id="e6d47-105">Progressive Web Apps on Windows overview</span></span>  

<span data-ttu-id="e6d47-106">[渐进式 Web 应用][MDNApps] \ (PWA\) 提供对开放 Web 技术的访问权限，实现跨平台互操作性，并为用户提供为设备自定义的本机、类似应用的体验。</span><span class="sxs-lookup"><span data-stu-id="e6d47-106">[Progressive Web Apps][MDNApps] \(PWAs\) provide access to open web technologies for cross-platform interoperability and provide your users with a native, app-like experience customized for their devices.</span></span>  <span data-ttu-id="e6d47-107">PWA 是逐步增强的网站[][AListApartUnderstandingProgressiveEnhancement]，其功能与支持平台上的本机应用类似。</span><span class="sxs-lookup"><span data-stu-id="e6d47-107">PWAs are websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="e6d47-108">PWA 的特性结合了最好的 Web 和本机应用。</span><span class="sxs-lookup"><span data-stu-id="e6d47-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification-small.png":::  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ### <a name="discoverablemdnpwaadvantagesdiscoverable"></a><span data-ttu-id="e6d47-109">[可发现][MDNPwaAdvantagesDiscoverable]</span><span class="sxs-lookup"><span data-stu-id="e6d47-109">[Discoverable][MDNPwaAdvantagesDiscoverable]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="installablemdnpwaadvantagesinstallable"></a><span data-ttu-id="e6d47-110">[可安装][MDNPwaAdvantagesInstallable]</span><span class="sxs-lookup"><span data-stu-id="e6d47-110">[Installable][MDNPwaAdvantagesInstallable]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="re-engageablemdnpwaadvantagesreengageable"></a><span data-ttu-id="e6d47-111">[重新参与][MDNPwaAdvantagesReEngageable]</span><span class="sxs-lookup"><span data-stu-id="e6d47-111">[Re-engageable][MDNPwaAdvantagesReEngageable]</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        <span data-ttu-id="e6d47-112">从 Web 搜索结果和支持的应用商店</span><span class="sxs-lookup"><span data-stu-id="e6d47-112">From web search results and supporting app stores</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="e6d47-113">从主屏幕、"开始"菜单、任务栏等固定和启动</span><span class="sxs-lookup"><span data-stu-id="e6d47-113">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="e6d47-114">发送推送通知，即使应用不处于活动状态</span><span class="sxs-lookup"><span data-stu-id="e6d47-114">Send push notifications, even when the app is not active</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security-small.png":::  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ### <a name="network-independentmdnpwaadvantagesnetworkindependent"></a><span data-ttu-id="e6d47-115">[与网络无关][MDNPwaAdvantagesNetworkIndependent]</span><span class="sxs-lookup"><span data-stu-id="e6d47-115">[Network Independent][MDNPwaAdvantagesNetworkIndependent]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="progressivemdnpwaadvantagesprogressive"></a><span data-ttu-id="e6d47-116">[渐进][MDNPwaAdvantagesProgressive]</span><span class="sxs-lookup"><span data-stu-id="e6d47-116">[Progressive][MDNPwaAdvantagesProgressive]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="safemdnpwaadvantagessafe"></a><span data-ttu-id="e6d47-117">[保险箱][MDNPwaAdvantagesSafe]</span><span class="sxs-lookup"><span data-stu-id="e6d47-117">[Safe][MDNPwaAdvantagesSafe]</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        <span data-ttu-id="e6d47-118">在脱机和低网络条件下工作</span><span class="sxs-lookup"><span data-stu-id="e6d47-118">Works offline and in low-network conditions</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="e6d47-119">体验通过 (功能) 向上或向下扩展</span><span class="sxs-lookup"><span data-stu-id="e6d47-119">Experience scales up (or down) with device capabilities</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="e6d47-120">提供安全的 HTTPS 终结点和其他用户安全措施</span><span class="sxs-lookup"><span data-stu-id="e6d47-120">Provides a secure HTTPS endpoint and other user safeguards</span></span>  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive-small.png":::  
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link-small.png":::  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        ### <a name="responsivemdnpwaadvantagesresponsive"></a><span data-ttu-id="e6d47-121">[响应][MDNPwaAdvantagesResponsive]</span><span class="sxs-lookup"><span data-stu-id="e6d47-121">[Responsive][MDNPwaAdvantagesResponsive]</span></span>  
    :::column-end:::
    :::column:::
        ### <a name="linkablemdnpwaadvantageslinkable"></a><span data-ttu-id="e6d47-122">[可链接][MDNPwaAdvantagesLinkable]</span><span class="sxs-lookup"><span data-stu-id="e6d47-122">[Linkable][MDNPwaAdvantagesLinkable]</span></span>  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        <span data-ttu-id="e6d47-123">适应用户的屏幕大小或方向和输入方法</span><span class="sxs-lookup"><span data-stu-id="e6d47-123">Adapts to the user's screen size or orientation and input method</span></span>  
    :::column-end:::
    :::column:::
        <span data-ttu-id="e6d47-124">从标准超链接共享和启动</span><span class="sxs-lookup"><span data-stu-id="e6d47-124">Share and launch from a standard hyperlink</span></span>  
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  

<span data-ttu-id="e6d47-125">生成 \ (或将) 网站转换为PWA，以增强用户参与度。</span><span class="sxs-lookup"><span data-stu-id="e6d47-125">Build \(or convert\) your existing website to a PWA to enhance your engagement with your users.</span></span>  <span data-ttu-id="e6d47-126">增强功能包括推送通知、类似应用的集成和脱机支持。</span><span class="sxs-lookup"><span data-stu-id="e6d47-126">Enhancements include push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="e6d47-127">继续构建开放 Web 上的受众，以便用户通过搜索和链接PWA发现你的网站。</span><span class="sxs-lookup"><span data-stu-id="e6d47-127">Continue to build your audience on the open web for users to discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="e6d47-128">最好使用 Web 服务器代码更新应用。</span><span class="sxs-lookup"><span data-stu-id="e6d47-128">Best of all, your app is updated in using your web server code.</span></span>  

## <a name="pwas-on-microsoft-edge-chromium"></a><span data-ttu-id="e6d47-129">PA on Microsoft Edge (Chromium) </span><span class="sxs-lookup"><span data-stu-id="e6d47-129">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="e6d47-130">构建面向 Web 标准 API 的渐进式 Web 应用时，应用可能会跨平台和设备进行部署，并尽可能利用特定于设备的功能。</span><span class="sxs-lookup"><span data-stu-id="e6d47-130">When you build a Progressive Web App targeting web standard APIs, your app may be deployed across platforms and devices and take advantage of the device-specific capabilities as available.</span></span>  <span data-ttu-id="e6d47-131">Microsoft Edge \ (Chromium\) 中的 PA 将以下优势添加到您的网站。</span><span class="sxs-lookup"><span data-stu-id="e6d47-131">PWAs in Microsoft Edge \(Chromium\) add the following advantages to your website.</span></span>  

*   <span data-ttu-id="e6d47-132">你的应用基于基于标准的 Web 平台构建。</span><span class="sxs-lookup"><span data-stu-id="e6d47-132">Your app is built on a standards-based web platform.</span></span>  
*   <span data-ttu-id="e6d47-133">允许用户直接从浏览器安装应用。</span><span class="sxs-lookup"><span data-stu-id="e6d47-133">Allows your users to install your app directly from the browser.</span></span>  
*   <span data-ttu-id="e6d47-134">允许用户在没有基于应用商店的部署或注册的情况下安装应用。</span><span class="sxs-lookup"><span data-stu-id="e6d47-134">Allows your users to install your app without a Store-based deployment or registration.</span></span>  
    
<span data-ttu-id="e6d47-135">桌面 PBA 在任何支持 \Microsoft Edge\ (Chromium\) 平台上均受支持。</span><span class="sxs-lookup"><span data-stu-id="e6d47-135">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available.</span></span> <span data-ttu-id="e6d47-136">Microsoft Edge \ (Chromium\) 7、Windows 和 macOS 上Windows 10 \Windows 10\macOS。</span><span class="sxs-lookup"><span data-stu-id="e6d47-136">Microsoft Edge \(Chromium\) is available on Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="e6d47-137">其中包括以下好处。</span><span class="sxs-lookup"><span data-stu-id="e6d47-137">The following benefits are included.</span></span>  

*   <span data-ttu-id="e6d47-138">可以直接在浏览器中使用导航栏中的 **"安装** "图标安装应用。</span><span class="sxs-lookup"><span data-stu-id="e6d47-138">Apps may be installed directly from within the browser using the **Install** icon in the navigation bar.</span></span>  
    
    :::image type="complex" source="./media/install-progressive-web-app-icon.png" alt-text="安装应用飞出和图标" lightbox="./media/install-progressive-web-app-icon.png":::
       <span data-ttu-id="e6d47-140">安装应用飞出和图标</span><span class="sxs-lookup"><span data-stu-id="e6d47-140">Install app flyout and icon</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="e6d47-141">也可以从"应用"菜单安装、运行和管理设置\*\*\*\*  >  **应用程序**</span><span class="sxs-lookup"><span data-stu-id="e6d47-141">Apps may also be installed, run, and managed from the **Settings** > **Apps** menu</span></span>  
    
    :::image type="complex" source="./media/app-menus.png" alt-text="设置下的应用菜单项" lightbox="./media/app-menus.png":::
       <span data-ttu-id="e6d47-143">设置下的应用菜单项</span><span class="sxs-lookup"><span data-stu-id="e6d47-143">App menu items under settings</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="e6d47-144">Web 通知已集成到 Windows通知系统</span><span class="sxs-lookup"><span data-stu-id="e6d47-144">Web Notifications are integrated into the Windows notification system</span></span>  
*   <span data-ttu-id="e6d47-145">具有安装应用程序的浏览器配置文件的共享 Cookie 存储</span><span class="sxs-lookup"><span data-stu-id="e6d47-145">Shared cookie store with the browser profile that installed the app</span></span>  
*   <span data-ttu-id="e6d47-146">使用"设置"和 **更多** \ (\) 菜单访问其他浏览器功能，包括证书验证、网站权限、跟踪保护和 `...` 浏览器扩展</span><span class="sxs-lookup"><span data-stu-id="e6d47-146">Access to other browser features using the **Setting and more** \(`...`\) menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>  
*   <span data-ttu-id="e6d47-147">对调试[Microsoft Edge开发人员][DevtoolsProgressiveWebApps]工具的完全访问权限</span><span class="sxs-lookup"><span data-stu-id="e6d47-147">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  
    
> [!NOTE]
> <span data-ttu-id="e6d47-148">有关版本PWA、即将推出的功能和简短演示的信息，请导航到"内部版本[2020 PWA会话"。][BuildVideo]</span><span class="sxs-lookup"><span data-stu-id="e6d47-148">For more information about PWA benefits, upcoming features, and short demos, navigate to [Build 2020 PWA session][BuildVideo].</span></span> 

## <a name="requirements"></a><span data-ttu-id="e6d47-149">要求</span><span class="sxs-lookup"><span data-stu-id="e6d47-149">Requirements</span></span>  

<span data-ttu-id="e6d47-150">若要作为PWA运行，服务器托管的 Web 应用应包含以下最低要求。</span><span class="sxs-lookup"><span data-stu-id="e6d47-150">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-151">HTTPS</span><span class="sxs-lookup"><span data-stu-id="e6d47-151">HTTPS</span></span>][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-152">通过为服务器或应用通信提供安全连接来保护用户。</span><span class="sxs-lookup"><span data-stu-id="e6d47-152">Protects your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="e6d47-153">服务工作人员和其他PWA技术仅适用于通过安全连接 \ (或用于调试目的 `localhost` \) 。</span><span class="sxs-lookup"><span data-stu-id="e6d47-153">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-154">服务工作者</span><span class="sxs-lookup"><span data-stu-id="e6d47-154">Service Workers</span></span>][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-155">使用服务工作线程充当服务器和客户端应用之间的网络代理。</span><span class="sxs-lookup"><span data-stu-id="e6d47-155">Uses Service Worker threads to act as network proxies between your server and client app.</span></span>  <span data-ttu-id="e6d47-156">服务工作线程提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。</span><span class="sxs-lookup"><span data-stu-id="e6d47-156">Service Worker threads provide offline support, resource caching, push notifications, background data sync, and  page-load performance optimizations.</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-157">Web 应用清单</span><span class="sxs-lookup"><span data-stu-id="e6d47-157">Web App Manifest</span></span>][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-158">提供一个基于 JSON 的元数据文件，该文件描述有关 Web 应用的关键信息，以便 Windows 10 和其他主机平台为 PWA 用户提供可安装的本机类似应用的体验。</span><span class="sxs-lookup"><span data-stu-id="e6d47-158">Provides a JSON-based metadata file that describes key information about your web app, so that Windows 10 and other host platforms provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="e6d47-159">关键信息包括图标、语言和 URL 入口点。</span><span class="sxs-lookup"><span data-stu-id="e6d47-159">Key information includes icons, language, and URL entry point.</span></span> 
   :::column-end:::
:::row-end:::  

<span data-ttu-id="e6d47-160">若要成为出色的PWA，你的应用还必须满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="e6d47-160">To be a great PWA, your app must also meet the following requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-161">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="e6d47-161">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-162">通过在不同PWA[环境中][MicrosoftDeveloperEdgeToolsRemote]进行测试，确保你的应用程序正常工作。</span><span class="sxs-lookup"><span data-stu-id="e6d47-162">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-163">响应式设计</span><span class="sxs-lookup"><span data-stu-id="e6d47-163">Responsive design</span></span>][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-164">采用流畅的布局和灵活的图像。</span><span class="sxs-lookup"><span data-stu-id="e6d47-164">Employs fluid layouts and flexible images.</span></span>  <span data-ttu-id="e6d47-165">响应式设计包括以下使用户体验适应用户设备的元素。</span><span class="sxs-lookup"><span data-stu-id="e6d47-165">Responsive design includes the following elements that adapt your UX to your user's device.</span></span>  
      
      *   <span data-ttu-id="e6d47-166">CSS [网格][MDNCssGridLayout]</span><span class="sxs-lookup"><span data-stu-id="e6d47-166">CSS [grid][MDNCssGridLayout]</span></span>  
      *   [<span data-ttu-id="e6d47-167">flexbox</span><span class="sxs-lookup"><span data-stu-id="e6d47-167">flexbox</span></span>][MDNCssFlexibleBoxLayout]  
      *   <span data-ttu-id="e6d47-168">CSS [网格][MDNCssGridLayout] 和 [弹性框][MDNCssFlexibleBoxLayout]</span><span class="sxs-lookup"><span data-stu-id="e6d47-168">CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout]</span></span>  
      *   [<span data-ttu-id="e6d47-169">媒体查询</span><span class="sxs-lookup"><span data-stu-id="e6d47-169">media queries</span></span>][MDNMediaQueries]  
      *   [<span data-ttu-id="e6d47-170">响应式图像</span><span class="sxs-lookup"><span data-stu-id="e6d47-170">responsive images</span></span>][MDNResponsiveImages]  
          
      <span data-ttu-id="e6d47-171">使用[浏览器的设备仿真][DevToolsGuideDeviceModeTestingOtherBrowsers]工具在本地测试，或在 Windows[或 Android][DevtoolsRemoteDebuggingIndex]上创建远程调试会话[][DevtoolsRemoteDebuggingWindows]，以在目标设备上直接进行测试。</span><span class="sxs-lookup"><span data-stu-id="e6d47-171">Uses [device emulation tools][DevToolsGuideDeviceModeTestingOtherBrowsers] from your browser to locally test, or create a remote debugging session on [Windows][DevtoolsRemoteDebuggingWindows] or [Android][DevtoolsRemoteDebuggingIndex] to test directly on a target device.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-172">深度链接</span><span class="sxs-lookup"><span data-stu-id="e6d47-172">Deep linking</span></span>][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-173">将网站的每个页面路由到一个唯一 URL，以便现有用户可以通过社交媒体共享帮助你吸引更广泛的受众。</span><span class="sxs-lookup"><span data-stu-id="e6d47-173">Routes each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-174">验证和测试实践</span><span class="sxs-lookup"><span data-stu-id="e6d47-174">Validation and testing practices</span></span>][Webhint]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-175">使用 [Webhint][Webhint] linter 等代码质量工具优化应用的效率、稳定性、安全性和辅助功能。</span><span class="sxs-lookup"><span data-stu-id="e6d47-175">Uses code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="e6d47-176">Chromium PWA清单</span><span class="sxs-lookup"><span data-stu-id="e6d47-176">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="e6d47-177">根据 Google PWA检查表验证PWA数据。</span><span class="sxs-lookup"><span data-stu-id="e6d47-177">Verifies your PWA against the Google baseline PWA checklist.</span></span>  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> <span data-ttu-id="e6d47-178">若要将PWA[转换为Microsoft Store应用][MicrosoftDeveloperStore]，请导航到"渐进式 Web 应用[Microsoft Store"。][PwaChromiumMicrosoftStore]</span><span class="sxs-lookup"><span data-stu-id="e6d47-178">To turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] app, navigate to [Progressive Web Apps in the Microsoft Store][PwaChromiumMicrosoftStore].</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e6d47-179">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e6d47-179">See also</span></span>  

*   [<span data-ttu-id="e6d47-180">为 PBA 提供一些支持</span><span class="sxs-lookup"><span data-stu-id="e6d47-180">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="e6d47-181">渐进式 Web 应用的渐进路线图</span><span class="sxs-lookup"><span data-stu-id="e6d47-181">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="e6d47-182">使用渐进 Web 应用的脱机 POS</span><span class="sxs-lookup"><span data-stu-id="e6d47-182">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="e6d47-183">PWA问答&</span><span class="sxs-lookup"><span data-stu-id="e6d47-183">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="e6d47-184">Web 上的百年</span><span class="sxs-lookup"><span data-stu-id="e6d47-184">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="e6d47-185">命名渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="e6d47-185">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="e6d47-186">设计和生成不带框架的渐进式 Web (第 1) </span><span class="sxs-lookup"><span data-stu-id="e6d47-186">Designing And Building A Progressive Web App Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebAppFrameworkPart1]  
*   [<span data-ttu-id="e6d47-187">设计和生成不带框架的渐进式 Web 应用 (第 2) </span><span class="sxs-lookup"><span data-stu-id="e6d47-187">Designing And Building A Progressive Web App Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebAppFrameworkPart2]  
*   [<span data-ttu-id="e6d47-188">设计和生成不带框架的渐进式 Web (第 3 部分) </span><span class="sxs-lookup"><span data-stu-id="e6d47-188">Designing And Building A Progressive Web App Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebAppFrameworkPart3]  
    
<!-- links -->  

[DevtoolsRemoteDebuggingIndex]: ../devtools-guide-chromium/remote-debugging/index.md "Android 设备远程调试入门 | Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "远程调试 Windows 10 设备|Microsoft Docs"  
[DevToolsGuideDeviceModeTestingOtherBrowsers]: ../devtools-guide-chromium/device-mode/testing-other-browsers.md "模拟和测试其他浏览器|Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps/index.md "调试渐进式 Web 应用|Microsoft Docs"  
[PwaChromiumMicrosoftStore]: ./microsoft-store.md "将渐进式 Web 应用发布到Microsoft Store |Microsoft Docs"

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "WindowsWNS (推送通知) 概述|Microsoft Docs"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "针对 Xbox 和电视|Microsoft Docs"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP 设备的 UI 注意事项|Microsoft Docs"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "什么是通用 Windows 平台 (UWP) 应用？|Microsoft Docs"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "使用后台任务支持|Microsoft Docs"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "发布Windows应用和游戏|Microsoft Docs"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "打开开发者帐户|Microsoft Docs"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "使渐进式 Web 应用Microsoft Edge和Windows 10 - Windows博客"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "后台同步 API - Microsoft Edge平台状态"  
[MicrosoftDeveloperEdgePlatformStatusWebAppManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web 应用清单 - Microsoft Edge平台状态"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "即时测试"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "混合现实（针对开发人员）"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft 开发人员应用商店"  
[MicrosoftEdge]: https://www.microsoft.com/edge "下载新Microsoft Edge浏览器"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "在打开或关闭焦点辅助Windows 10"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "更改通知中的Windows 10"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA问答&"  

[AListApartUnderstandingProgressiveEnhancement]: https://alistapart.com/article/understandingprogressiveenhancement "了解渐进式增强 - 列表分开"  

[MDNApps]: https://developer.mozilla.org/Apps/Progressive "应用|MDN"  
[MDNCache]: https://developer.mozilla.org/docs/Web/API/Cache "缓存|MDN"  
[MDNCrossBrowserTesting]: https://developer.mozilla.org/docs/Learn/Tools_and_testing/Cross_browser_testing "跨浏览器测试|MDN"  
[MDNCssFlexibleBoxLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Flexible_Box_Layout "CSS 弹性框布局|MDN"  
[MDNCssGridLayout]: https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout "CSS 网格布局 | MDN"  
[MDNFetchApi]: https://developer.mozilla.org/docs/Web/API/Fetch_API "提取 API |MDN"  
[MDNMediaQueries]: https://developer.mozilla.org/docs/Web/CSS/Media_Queries "媒体查询|MDN"  
[MDNNotificationsApi]: https://developer.mozilla.org/docs/Web/API/Notifications_API "通知 API | MDN"  
[MDNPushApi]: https://developer.mozilla.org/docs/Web/API/Push_API "推送 API | MDN"  
[MDNPwaAdvantagesDiscoverable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Discoverable "可发现 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesInstallable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Installable "可安装 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesLinkable]: https://developer.mozilla.org/Apps/Progressive/Advantages#Linkable "可链接 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesNetworkIndependent]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Network_independent "独立于网络 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesProgressive]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Progressive "渐进 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesReEngageable]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Re-engageable "重新参与 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesResponsive]: https://developer.mozilla.org/Apps/Progressive/Advantages#Responsive "响应式 - 渐进式 Web 应用优势"  
[MDNPwaAdvantagesSafe]: https://developer.mozilla.org/docs/Web/Apps/Progressive/Advantages#Safe "保险箱 - 渐进式 Web 应用优势"  
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "响应式图像|MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作线程 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web 应用清单|MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA视频"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "百年计划 PBA – 新边缘版本"  

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "Web 上的百年"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "使用渐进 Web 应用的脱机 POS"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Smashingmagazine201907ProgressiveWebAppFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和构建不带框架的渐进式 Web (第 1) "  

[Smashingmagazine201907ProgressiveWebAppFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和生成不带框架的渐进式 Web (第 2) "  

[Smashingmagazine201907ProgressiveWebAppFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和构建不带框架的渐进式 Web (第 3) "  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "什么是良好的渐进式 Web 应用？|web.dev"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接 - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 Web 设计 - 维基百科"  
