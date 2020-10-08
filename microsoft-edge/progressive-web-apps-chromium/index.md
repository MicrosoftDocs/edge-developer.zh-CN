---
description: " (Chromium 中的渐进式 Web 应用) 在 Windows 10 上以本机方式运行。  下面是 web 开发人员需要了解的所有内容。"
title: Windows 上的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/01/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: a9fa08a9c84ee5da8eab3c9c3edeea34439b6557
ms.sourcegitcommit: be76feed0d616a96c77ea2748a9f0d6c0c06284b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/07/2020
ms.locfileid: "11103932"
---
# <span data-ttu-id="1ace3-105">Windows 上的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="1ace3-105">Progressive Web Apps on Windows</span></span>  

<span data-ttu-id="1ace3-106">[渐进式 Web 应用][MDNApps] \ (PWAs \ ) 提供对开放 Web 技术以实现跨平台互操作性的访问权限，并为用户提供针对其设备自定义的与应用类似的本机体验。</span><span class="sxs-lookup"><span data-stu-id="1ace3-106">[Progressive Web Apps][MDNApps] \(PWAs\) provide access to open web technologies for cross-platform interoperability and provide your users with a native, app-like experience customized for their devices.</span></span>  <span data-ttu-id="1ace3-107">PWAs 是在支持平台上以本机应用的形式 [逐渐增强][AListApartUnderstandingProgressiveEnhancement] 到功能的网站。</span><span class="sxs-lookup"><span data-stu-id="1ace3-107">PWAs are websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="1ace3-108">PWA 的特性结合了最好的 Web 和本机应用。</span><span class="sxs-lookup"><span data-stu-id="1ace3-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [<span data-ttu-id="1ace3-109">Dsgetdcname</span><span class="sxs-lookup"><span data-stu-id="1ace3-109">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="1ace3-110">从 web 搜索结果和支持应用商店</span><span class="sxs-lookup"><span data-stu-id="1ace3-110">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [<span data-ttu-id="1ace3-111">可安装</span><span class="sxs-lookup"><span data-stu-id="1ace3-111">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="1ace3-112">通过主屏幕、"开始" 菜单、任务栏等固定和启动</span><span class="sxs-lookup"><span data-stu-id="1ace3-112">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [<span data-ttu-id="1ace3-113">重新 engageable</span><span class="sxs-lookup"><span data-stu-id="1ace3-113">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="1ace3-114">发送推送通知，即使应用未处于活动状态</span><span class="sxs-lookup"><span data-stu-id="1ace3-114">Send push notifications, even when the app is not active</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [<span data-ttu-id="1ace3-115">独立于网络</span><span class="sxs-lookup"><span data-stu-id="1ace3-115">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="1ace3-116">在低网络条件下脱机工作</span><span class="sxs-lookup"><span data-stu-id="1ace3-116">Works offline and in low-network conditions</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [<span data-ttu-id="1ace3-117">累进</span><span class="sxs-lookup"><span data-stu-id="1ace3-117">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="1ace3-118">体验通过设备功能放大 (或下降) </span><span class="sxs-lookup"><span data-stu-id="1ace3-118">Experience scales up (or down) with device capabilities</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [<span data-ttu-id="1ace3-119">安全</span><span class="sxs-lookup"><span data-stu-id="1ace3-119">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="1ace3-120">提供安全 HTTPS 终结点和其他用户保护</span><span class="sxs-lookup"><span data-stu-id="1ace3-120">Provides a secure HTTPS endpoint and other user safeguards</span></span>
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [<span data-ttu-id="1ace3-121">响应</span><span class="sxs-lookup"><span data-stu-id="1ace3-121">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="1ace3-122">适应用户的屏幕大小或方向和输入法</span><span class="sxs-lookup"><span data-stu-id="1ace3-122">Adapts to the user's screen size or orientation and input method</span></span>
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [<span data-ttu-id="1ace3-123">Linkable</span><span class="sxs-lookup"><span data-stu-id="1ace3-123">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="1ace3-124">从标准超链接共享和启动</span><span class="sxs-lookup"><span data-stu-id="1ace3-124">Share and launch from a standard hyperlink</span></span>
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


<span data-ttu-id="1ace3-125">内部版本 \ (或将 \ ) 现有网站转换为 PWA，以增强您与用户的合作。</span><span class="sxs-lookup"><span data-stu-id="1ace3-125">Build \(or convert\) your existing website to a PWA to enhance your engagement with your users.</span></span>  <span data-ttu-id="1ace3-126">增强功能包括推送通知、类似应用的集成和脱机支持。</span><span class="sxs-lookup"><span data-stu-id="1ace3-126">Enhancements include push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="1ace3-127">继续在打开的 web 上构建受众，让用户通过 "搜索" 和 "链接共享" 发现你的 PWA。</span><span class="sxs-lookup"><span data-stu-id="1ace3-127">Continue to build your audience on the open web for users to discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="1ace3-128">最重要的是，你的应用会使用你的 web 服务器代码进行更新。</span><span class="sxs-lookup"><span data-stu-id="1ace3-128">Best of all, your app is updated in using your web server code.</span></span>  

## <span data-ttu-id="1ace3-129">Microsoft Edge (Chromium) PWAs</span><span class="sxs-lookup"><span data-stu-id="1ace3-129">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="1ace3-130">当你生成针对 web 标准 Api 的渐进式 Web 应用时，你的应用程序可能会跨平台和设备部署，并充分利用特定于设备的功能。</span><span class="sxs-lookup"><span data-stu-id="1ace3-130">When you build a Progressive Web App targeting web standard APIs, your application may be deployed across platforms and devices and take advantage of the device-specific capabilities as available.</span></span>  <span data-ttu-id="1ace3-131">Microsoft Edge 中的 PWAs \ (Chromium \ ) 将以下优势添加到您的网站。</span><span class="sxs-lookup"><span data-stu-id="1ace3-131">PWAs in Microsoft Edge \(Chromium\) add the following advantages to your website.</span></span>  

*   <span data-ttu-id="1ace3-132">你的应用基于基于标准的 web 平台构建。</span><span class="sxs-lookup"><span data-stu-id="1ace3-132">Your app is built on a standards-based web platform.</span></span>  
*   <span data-ttu-id="1ace3-133">使你的用户能够直接从浏览器安装你的应用。</span><span class="sxs-lookup"><span data-stu-id="1ace3-133">Enables your users to install your app directly from the browser.</span></span>  
*   <span data-ttu-id="1ace3-134">使你的用户能够在不使用基于应用商店的部署或注册的情况下安装你的应用。</span><span class="sxs-lookup"><span data-stu-id="1ace3-134">Enables your users to install your app without a Store-based deployment or registration.</span></span>  
    
<span data-ttu-id="1ace3-135">Microsoft Edge \ (Chromium \ ) 可用的任何平台都支持桌面 PWAs。</span><span class="sxs-lookup"><span data-stu-id="1ace3-135">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available.</span></span> <span data-ttu-id="1ace3-136">Microsoft Edge \ (Chromium \ ) 在 Windows 7、Windows 10 和 macOS 上可用。</span><span class="sxs-lookup"><span data-stu-id="1ace3-136">Microsoft Edge \(Chromium\) is available on Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="1ace3-137">包括以下优点。</span><span class="sxs-lookup"><span data-stu-id="1ace3-137">The following benefits are included.</span></span>  

*   <span data-ttu-id="1ace3-138">可以使用导航栏中的 " **安装** " 图标直接从浏览器内部安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="1ace3-138">Applications may be installed directly from within the browser using the **Install** icon in the navigation bar.</span></span>  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="安装应用程序浮出控件和图标" lightbox="./media/install_pwa_icon.png":::
       <span data-ttu-id="1ace3-140">安装应用程序浮出控件和图标</span><span class="sxs-lookup"><span data-stu-id="1ace3-140">Install application flyout and icon</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="1ace3-141">也可以从 "**设置**  >  **应用**" 菜单中安装、运行和管理应用程序</span><span class="sxs-lookup"><span data-stu-id="1ace3-141">Applications may also be installed, run, and managed from the **Settings** > **Apps** menu</span></span>  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="安装应用程序浮出控件和图标" lightbox="./media/app_menus.png":::
       <span data-ttu-id="1ace3-143">"设置" 下的 "应用程序" 菜单项</span><span class="sxs-lookup"><span data-stu-id="1ace3-143">Application menu items under settings</span></span>  
    :::image-end:::  
    
*   <span data-ttu-id="1ace3-144">Web 通知集成到 Windows 通知系统中</span><span class="sxs-lookup"><span data-stu-id="1ace3-144">Web Notifications are integrated into the Windows notification system</span></span>  
*   <span data-ttu-id="1ace3-145">与安装了该应用的浏览器配置文件共享的 cookie 存储</span><span class="sxs-lookup"><span data-stu-id="1ace3-145">Shared cookie store with the browser profile that installed the app</span></span>  
*   <span data-ttu-id="1ace3-146">使用 " **设置" 和 "更多** \ (`...` \ ) " 菜单（包括证书验证、网站权限、跟踪保护和浏览器扩展）访问其他浏览器功能</span><span class="sxs-lookup"><span data-stu-id="1ace3-146">Access to other browser features using the **Setting and more** \(`...`\) menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>  
*   <span data-ttu-id="1ace3-147">对 [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] 的完全访问权限调试你的应用</span><span class="sxs-lookup"><span data-stu-id="1ace3-147">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  
    
> [!IMPORTANT]
> <span data-ttu-id="1ace3-148">若要针对使用 JavaScript 进行 WinRT API 请求的 Windows 10 专门定制 PWAs，请导航到 [特定于 EDGEHTML PWA 功能的文档][PwaEdgehtmlIndex]。</span><span class="sxs-lookup"><span data-stu-id="1ace3-148">To tailor PWAs specifically for Windows 10 that make WinRT API requests using JavaScript, navigate to [documentation specific to the EdgeHTML PWA features][PwaEdgehtmlIndex].</span></span>  <span data-ttu-id="1ace3-149">了解有关在 Windows 10 上测试 PWA 并将其分发到 Microsoft Store 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="1ace3-149">Learn more about testing your PWA on Windows 10 and distributing it in the Microsoft Store.</span></span>  

> [!NOTE]
> <span data-ttu-id="1ace3-150">有关 PWA 优势、即将推出的功能和简短演示的详细信息，请导航到 [内部版本 2020 PWA 会话][BuildVideo]。</span><span class="sxs-lookup"><span data-stu-id="1ace3-150">For more information about PWA benefits, upcoming features, and short demos, navigate to [Build 2020 PWA session][BuildVideo].</span></span> 

## <span data-ttu-id="1ace3-151">要求</span><span class="sxs-lookup"><span data-stu-id="1ace3-151">Requirements</span></span>  

<span data-ttu-id="1ace3-152">若要作为 PWA 运行，服务器托管的 web 应用应包括以下最低要求。</span><span class="sxs-lookup"><span data-stu-id="1ace3-152">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-153">HTTPS</span><span class="sxs-lookup"><span data-stu-id="1ace3-153">HTTPS</span></span>][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-154">通过为服务器或应用通信提供安全连接来保护你的用户。</span><span class="sxs-lookup"><span data-stu-id="1ace3-154">Protects your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="1ace3-155">服务工作者和其他 PWA 技术仅适用于通过安全连接进行服务的 web 资源 (或 `localhost` 用于调试目的 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="1ace3-155">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-156">服务工作进程</span><span class="sxs-lookup"><span data-stu-id="1ace3-156">Service Workers</span></span>][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-157">使用服务工作线程充当服务器和客户端应用之间的网络代理。</span><span class="sxs-lookup"><span data-stu-id="1ace3-157">Uses Service Worker threads to act as network proxies between your server and client app.</span></span>  <span data-ttu-id="1ace3-158">服务工作线程提供离线支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。</span><span class="sxs-lookup"><span data-stu-id="1ace3-158">Service Worker threads provide offline support, resource caching, push notifications, background data sync, and  page-load performance optimizations.</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-159">Web App 清单</span><span class="sxs-lookup"><span data-stu-id="1ace3-159">Web App Manifest</span></span>][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-160">提供一个基于 JSON 的元数据文件，该文件描述有关你的 web 应用的关键信息，因此 Windows 10 和其他主机平台为你的 PWA 用户提供了可安装的、类似于应用的内置体验。</span><span class="sxs-lookup"><span data-stu-id="1ace3-160">Provides a JSON-based metadata file that describes key information about your web app, so that Windows 10 and other host platforms provide your PWA users with an installable, native app-like experience.</span></span>  <span data-ttu-id="1ace3-161">关键信息包括图标、语言和 URL 入口点。</span><span class="sxs-lookup"><span data-stu-id="1ace3-161">Key information includes icons, language, and URL entry point.</span></span> 
   :::column-end:::
:::row-end:::  

<span data-ttu-id="1ace3-162">若要成为绝佳的 PWA，你的应用还必须满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="1ace3-162">To be a great PWA, your app must also meet the following requirements.</span></span>  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-163">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="1ace3-163">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-164">通过在不同的浏览器和环境中进行 [测试][MicrosoftDeveloperEdgeToolsRemote] ，确保你的 PWA 正常工作。</span><span class="sxs-lookup"><span data-stu-id="1ace3-164">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-165">响应式设计</span><span class="sxs-lookup"><span data-stu-id="1ace3-165">Responsive design</span></span>][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-166">采用流畅的布局和灵活的图像。</span><span class="sxs-lookup"><span data-stu-id="1ace3-166">Employs fluid layouts and flexible images.</span></span>  <span data-ttu-id="1ace3-167">响应式设计包括以下元素，这些元素可将你的 UX 调整为你的用户设备。</span><span class="sxs-lookup"><span data-stu-id="1ace3-167">Responsive design includes the following elements that adapt your UX to your user's device.</span></span>  
      
      *   <span data-ttu-id="1ace3-168">CSS [网格][MDNCssGridLayout]</span><span class="sxs-lookup"><span data-stu-id="1ace3-168">CSS [grid][MDNCssGridLayout]</span></span>  
      *   [<span data-ttu-id="1ace3-169">flexbox</span><span class="sxs-lookup"><span data-stu-id="1ace3-169">flexbox</span></span>][MDNCssFlexibleBoxLayout]  
      *   <span data-ttu-id="1ace3-170">CSS [网格][MDNCssGridLayout] 和 [flexbox][MDNCssFlexibleBoxLayout]</span><span class="sxs-lookup"><span data-stu-id="1ace3-170">CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout]</span></span>  
      *   [<span data-ttu-id="1ace3-171">媒体查询</span><span class="sxs-lookup"><span data-stu-id="1ace3-171">media queries</span></span>][MDNMediaQueries]  
      *   [<span data-ttu-id="1ace3-172">响应图像</span><span class="sxs-lookup"><span data-stu-id="1ace3-172">responsive images</span></span>][MDNResponsiveImages]  
      
      <span data-ttu-id="1ace3-173">使用浏览器中的 [设备仿真工具][DevToolsGuide|::ref1::|] 进行本地测试，或创建 [远程调试会话][DevToolsProtocolClientsEdgeDevToolsPreview] 以直接在目标设备上进行测试。</span><span class="sxs-lookup"><span data-stu-id="1ace3-173">Uses [device emulation tools][DevToolsGuide|::ref1::|] from your browser to locally test, or create a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-174">深层链接</span><span class="sxs-lookup"><span data-stu-id="1ace3-174">Deep linking</span></span>][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-175">将网站的每个页面路由到唯一的 URL，以便现有用户可以通过社交媒体共享帮助您更多的受众参与。</span><span class="sxs-lookup"><span data-stu-id="1ace3-175">Routes each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-176">验证和测试实践</span><span class="sxs-lookup"><span data-stu-id="1ace3-176">Validation and testing practices</span></span>][Webhint]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-177">使用 [Webhint][Webhint] linter 之类的代码质量工具来优化应用的效率、可靠性、安全性和辅助功能。</span><span class="sxs-lookup"><span data-stu-id="1ace3-177">Uses code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="1ace3-178">Chromium PWA 清单</span><span class="sxs-lookup"><span data-stu-id="1ace3-178">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="1ace3-179">针对 Google 基线 PWA 清单验证你的 PWA。</span><span class="sxs-lookup"><span data-stu-id="1ace3-179">Verifies your PWA against the Google baseline PWA checklist.</span></span>  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> <span data-ttu-id="1ace3-180">若要将 PWA 转换为 [Microsoft store][MicrosoftDeveloperStore] 应用程序，请导航到 [microsoft Store 中 (EdgeHTML) 的渐进式 Web 应用][PwaEdgehtmlMicrosoftStore]。</span><span class="sxs-lookup"><span data-stu-id="1ace3-180">To turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] application, navigate to [Progressive Web Apps (EdgeHTML) in the Microsoft Store][PwaEdgehtmlMicrosoftStore].</span></span>  
  
## <span data-ttu-id="1ace3-181">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ace3-181">See also</span></span>  

*   [<span data-ttu-id="1ace3-182">Myth Busting PWAs</span><span class="sxs-lookup"><span data-stu-id="1ace3-182">Myth Busting PWAs</span></span>][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [<span data-ttu-id="1ace3-183">渐进式 Web 应用的渐进式路线图</span><span class="sxs-lookup"><span data-stu-id="1ace3-183">A Progressive Roadmap for your Progressive Web App</span></span>][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [<span data-ttu-id="1ace3-184">具有渐进的 Web 应用的脱机文章</span><span class="sxs-lookup"><span data-stu-id="1ace3-184">Offline POSTs with Progressive Web Apps</span></span>][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [<span data-ttu-id="1ace3-185">PWA 问答&</span><span class="sxs-lookup"><span data-stu-id="1ace3-185">PWA Q&A</span></span>][AaronGustafsonNotebookPwaQa]  
*   [<span data-ttu-id="1ace3-186">在网上打赌</span><span class="sxs-lookup"><span data-stu-id="1ace3-186">Betting on the Web</span></span>][JoretegBlogBettingWeb]  
*   [<span data-ttu-id="1ace3-187">命名渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="1ace3-187">Naming Progressive Web Apps</span></span>][Fberriman20170626NamingProgressiveWebApps]  
*   [<span data-ttu-id="1ace3-188">设计和构建不带框架 (第1部分) 的渐进式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1ace3-188">Designing And Building A Progressive Web Application Without A Framework (Part 1)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [<span data-ttu-id="1ace3-189">设计和构建不带框架 (第2部分) 的渐进式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1ace3-189">Designing And Building A Progressive Web Application Without A Framework (Part 2)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [<span data-ttu-id="1ace3-190">设计和构建不带框架 (第3部分) 的渐进式 Web 应用程序</span><span class="sxs-lookup"><span data-stu-id="1ace3-190">Designing And Building A Progressive Web Application Without A Framework (Part 3)</span></span>][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- links -->  

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "枚举"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps.md "调试渐进式 Web 应用"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 中的新增功能"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 中的新增功能"  
[PwaEdgehtmlIndex]: ../progressive-web-apps-edgehtml/index.md "在 Windows 上 (EdgeHTML) 的渐进式 Web 应用"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store 中的渐进式 Web 应用"
<!--PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps-edgehtml/microsoft-store.md#criteria-for-automatic-submission "Criteria for automatic submission - Progressive Web Apps in the Microsoft Store"  -->  

[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows 推送通知服务 \ (WNS \ ) 概述"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "针对 Xbox 和电视进行设计"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP 设备的 UI 注意事项"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "什么是 (UWP) 应用的通用 Windows 平台？"  
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
[MicrosoftEdge]: https://www.microsoft.com/edge "下载新的 Microsoft Edge 浏览器"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "在 Windows 10 中打开或关闭 "聚焦助手""  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "在 Windows 10 中更改通知设置"  

[AaronGustafsonNotebookPwaQa]: https://www.aaron-gustafson.com/notebook/pwa-qa "PWA 问答&"  

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
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "快速响应图像 |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA 视频"  

[CloudfourThinksProgressiveRoadmapYourWebApp]: https://cloudfour.com/thinks/a-progressive-roadmap-for-your-progressive-web-app "渐进式 Web 应用的渐进式路线图"  

[Davrous20191018MythBustingPwasNewEdgeEdition]: https://www.davrous.com/2019/10/18/myth-busting-pwas-the-new-edge-edition "Myth Busting PWAs-新的边缘版本"  

[Fberriman20170626NamingProgressiveWebApps]: https://fberriman.com/2017/06/26/naming-progressive-web-apps "命名渐进式 Web 应用"  

[JoretegBlogBettingWeb]: https://joreteg.com/blog/betting-on-the-web "在网上打赌"  

[MediumWebEdgeOfflinePostsProgressiveWebApps]: https://medium.com/web-on-the-edge/offline-posts-with-progressive-web-apps-fc2dc4ad895 "具有渐进的 Web 应用的脱机文章"  

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-1 "设计和构建不带框架 (第1部分) 的渐进式 Web 应用程序 "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-2 "设计和构建不带框架 (第2部分) 的渐进式 Web 应用程序 "  

[Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]: https://www.smashingmagazine.com/2019/07/progressive-web-application-pwa-framework-part-3 "设计和构建不带框架 (第3部分) 的渐进式 Web 应用程序 "  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "什么使 Web 应用成为一个好的渐进？ |web 开发"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接-维基百科"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-维基百科"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 web 设计-维基百科"  
