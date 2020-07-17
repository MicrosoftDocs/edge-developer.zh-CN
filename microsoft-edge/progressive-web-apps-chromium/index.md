---
description: 累进 Web 应用在 Windows 10 上以本机方式运行。  下面是 web 开发人员需要了解的所有内容。
title: Windows 上的渐进式 Web 应用
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/17/2020
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 web 应用、PWA、Edge、JavaScript、Windows、UWP、Microsoft Store
ms.openlocfilehash: 90740bac07ebfd74f89e2524e6955621e1b09b05
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882805"
---
# <span data-ttu-id="2c5dd-105">Windows 上的渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="2c5dd-105">Progressive Web Apps on Windows</span></span>  

<span data-ttu-id="2c5dd-106">使用[渐进式 Web 应用][MDNApps]\ （或只是 PWAs \），无需在使用开放 Web 技术实现跨平台互操作性和为用户提供针对其设备自定义的本机应用体验之间做出决定。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-106">With [Progressive Web Apps][MDNApps] \(or simply PWAs\), you do not have to decide between using open web technologies for cross-platform interoperability and providing your users with a native app-like experience customized for their devices.</span></span>  <span data-ttu-id="2c5dd-107">PWAs 是在支持平台上以本机应用的形式[逐渐增强][AListApartUnderstandingProgressiveEnhancement]到功能的网站。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-107">PWAs are just websites that are [progressively enhanced][AListApartUnderstandingProgressiveEnhancement] to function like native apps on supporting platforms.</span></span>  <span data-ttu-id="2c5dd-108">PWA 的特性结合了最好的 Web 和本机应用。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-108">The qualities of a PWA combine the best of the web and native apps.</span></span>  

:::row:::
    :::column:::
        ![可发现图标][ImageISearch]
        ### [<span data-ttu-id="2c5dd-110">Dsgetdcname</span><span class="sxs-lookup"><span data-stu-id="2c5dd-110">Discoverable</span></span>][MDNPwaAdvantagesDiscoverable]
        <span data-ttu-id="2c5dd-111">从 web 搜索结果和支持应用商店</span><span class="sxs-lookup"><span data-stu-id="2c5dd-111">From web search results and supporting app stores</span></span>
    :::column-end:::
    :::column:::
        ![可安装图标][ImageIPackage]
        ### [<span data-ttu-id="2c5dd-113">可安装</span><span class="sxs-lookup"><span data-stu-id="2c5dd-113">Installable</span></span>][MDNPwaAdvantagesInstallable]
        <span data-ttu-id="2c5dd-114">通过主屏幕、"开始" 菜单、任务栏等固定和启动</span><span class="sxs-lookup"><span data-stu-id="2c5dd-114">Pin and launch from the home screen, Start Menu, Taskbar, and so on</span></span>
    :::column-end:::
    :::column:::
        ![重新 engageable 图标][ImageIPushNotification]
        ### [<span data-ttu-id="2c5dd-116">重新 engageable</span><span class="sxs-lookup"><span data-stu-id="2c5dd-116">Re-engageable</span></span>][MDNPwaAdvantagesReEngageable]
        <span data-ttu-id="2c5dd-117">发送推送通知，即使应用未处于活动状态</span><span class="sxs-lookup"><span data-stu-id="2c5dd-117">Send push notifications, even when the app is not active</span></span>
    :::column-end:::
    :::column:::
        ![网络独立图标][ImageIOffline]
        ### [<span data-ttu-id="2c5dd-119">独立于网络</span><span class="sxs-lookup"><span data-stu-id="2c5dd-119">Network Independent</span></span>][MDNPwaAdvantagesNetworkIndependent]
        <span data-ttu-id="2c5dd-120">在低网络条件下脱机工作</span><span class="sxs-lookup"><span data-stu-id="2c5dd-120">Works offline and in low-network conditions</span></span>
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        !["渐进" 图标][ImageIProgressive]
        ### [<span data-ttu-id="2c5dd-122">累进</span><span class="sxs-lookup"><span data-stu-id="2c5dd-122">Progressive</span></span>][MDNPwaAdvantagesProgressive]
        <span data-ttu-id="2c5dd-123">体验通过设备功能放大（或缩小）</span><span class="sxs-lookup"><span data-stu-id="2c5dd-123">Experience scales up (or down) with device capabilities</span></span>
    :::column-end:::
    :::column:::
        ![安全图标][ImageISecurity]
        ### [<span data-ttu-id="2c5dd-125">安全</span><span class="sxs-lookup"><span data-stu-id="2c5dd-125">Safe</span></span>][MDNPwaAdvantagesSafe]
        <span data-ttu-id="2c5dd-126">提供安全 HTTPS 终结点和其他用户保护</span><span class="sxs-lookup"><span data-stu-id="2c5dd-126">Provides a secure HTTPS endpoint and other user safeguards</span></span>
    :::column-end:::
    :::column:::
        ![响应图标][ImageIResponsive]
        ### [<span data-ttu-id="2c5dd-128">响应</span><span class="sxs-lookup"><span data-stu-id="2c5dd-128">Responsive</span></span>][MDNPwaAdvantagesResponsive]
        <span data-ttu-id="2c5dd-129">适应用户的屏幕大小或方向和输入法</span><span class="sxs-lookup"><span data-stu-id="2c5dd-129">Adapts to the user's screen size or orientation and input method</span></span>
    :::column-end:::
    :::column:::
        ![Linkable 图标][ImageILink]
        ### [<span data-ttu-id="2c5dd-131">Linkable</span><span class="sxs-lookup"><span data-stu-id="2c5dd-131">Linkable</span></span>][MDNPwaAdvantagesLinkable]
        <span data-ttu-id="2c5dd-132">从标准超链接共享和启动</span><span class="sxs-lookup"><span data-stu-id="2c5dd-132">Share and launch from a standard hyperlink</span></span>
    :::column-end:::
:::row-end:::

<span data-ttu-id="2c5dd-133">通过构建现有网站或将其转换为 PWA，你可以更好地使用推送通知、类似于应用的集成和脱机支持与你的现有受众取得联系。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-133">By building or converting your existing site to a PWA, you engage better with your existing audience using push notifications, app-like integration, and offline support.</span></span>  <span data-ttu-id="2c5dd-134">同时，你应该在打开的网站上继续构建受众，因为用户通过搜索和链接共享发现你的 PWA。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-134">At the same time, you should continue to build your audience on the open web, as users discover your PWA through search and link-sharing.</span></span>  <span data-ttu-id="2c5dd-135">最重要的是，你只需更新 web 服务器代码即可更新你的应用。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-135">Best of all, you may update your app by simply updating your web server code.</span></span>  

## <span data-ttu-id="2c5dd-136">Microsoft Edge 上的 PWAs （Chromium）</span><span class="sxs-lookup"><span data-stu-id="2c5dd-136">PWAs on Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="2c5dd-137">当你生成针对 web 标准 Api 的渐进式 Web 应用时，你的应用程序可能会跨平台和设备部署，并充分利用特定于设备的功能。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-137">When you build a Progressive Web App targeting web standard APIs, your application may be deployed across platforms and devices and take advantage of the device specific capabilities as available.</span></span>  <span data-ttu-id="2c5dd-138">Microsoft Edge \ （Chromium \）中的 PWAs 是完全基于 web 平台角度的标准，可让用户直接在浏览器中安装应用，而无需基于应用商店的部署或注册。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-138">PWAs in Microsoft Edge \(Chromium\) are completely standards-based from a web platform perspective and enable users to install the app directly from within the browser without the need for Store-based deployment or registration.</span></span>  <span data-ttu-id="2c5dd-139">Microsoft Edge \ （Chromium \）可用的任何平台上都支持桌面 PWAs，包括 Windows 7、Windows 10 和 macOS。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-139">Desktop PWAs are supported on any of the platforms Microsoft Edge \(Chromium\) is available, including Windows 7, Windows 10, and macOS.</span></span>  <span data-ttu-id="2c5dd-140">其他好处包括：</span><span class="sxs-lookup"><span data-stu-id="2c5dd-140">Other benefits include:</span></span>  

*   <span data-ttu-id="2c5dd-141">通过导航栏中的 "**安装**" 图标，可以直接从浏览器内部安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-141">Applications may be installed directly from within the browser via the **Install** icon in the navigation bar.</span></span>  
    
    ![安装应用程序浮出控件和图标][ImageInstallPwa]  
    
*   <span data-ttu-id="2c5dd-143">也可以从 "**设置**  >  **应用**" 菜单安装、运行和管理应用程序</span><span class="sxs-lookup"><span data-stu-id="2c5dd-143">Applications may also be installed, run and managed from the **Settings** > **Apps** menu</span></span>  
    
    !["设置" 下的 "应用程序" 菜单项][ImageAppMenus]  

*   <span data-ttu-id="2c5dd-145">Web 通知集成到 Windows 通知系统中</span><span class="sxs-lookup"><span data-stu-id="2c5dd-145">Web Notifications are integrated into the Windows notification system</span></span>
*   <span data-ttu-id="2c5dd-146">与安装了该应用的浏览器配置文件共享的 cookie 存储</span><span class="sxs-lookup"><span data-stu-id="2c5dd-146">Shared cookie store with the browser profile that installed the app</span></span>
*   <span data-ttu-id="2c5dd-147">通过 `...` 菜单（包括证书验证、网站权限、跟踪保护和浏览器扩展）访问其他浏览器功能</span><span class="sxs-lookup"><span data-stu-id="2c5dd-147">Access to other browser features via the `...` menu including certificate validation, site permissions, tracking protection, and browser extensions</span></span>
*   <span data-ttu-id="2c5dd-148">对[Microsoft Edge DevTools][DevtoolsProgressiveWebApps]的完全访问权限调试你的应用</span><span class="sxs-lookup"><span data-stu-id="2c5dd-148">Full access to [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] for debugging your app</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="2c5dd-149">若要针对使用 JavaScript 进行 WinRT API 请求的 Windows 10 专门定制 PWAs，请参阅[特定于 EDGEHTML PWA 功能的文档][PwaEdgehtmlIndex]。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-149">To tailor PWAs specifically for Windows 10 that make WinRT API requests using JavaScript, see the [documentation specific to the EdgeHTML PWA features][PwaEdgehtmlIndex].</span></span>  <span data-ttu-id="2c5dd-150">了解有关在 Windows 10 上测试 PWA 并将其分发到 Microsoft Store 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-150">Learn more about testing your PWA on Windows 10 and distributing it in the Microsoft Store.</span></span>  

> [!NOTE]
> <span data-ttu-id="2c5dd-151">有关 PWA 好处、即将推出的功能和简短演示的概述，请查看[内部版本 2020 pwa 会话][BuildVideo]。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-151">Check out the [Build 2020 PWA session][BuildVideo] for an overview of PWA benefits, upcoming features and short demos.</span></span> 

## <span data-ttu-id="2c5dd-152">要求</span><span class="sxs-lookup"><span data-stu-id="2c5dd-152">Requirements</span></span>  

<span data-ttu-id="2c5dd-153">若要作为 PWA 运行，服务器托管的 web 应用应包括以下最低要求。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-153">To run as a PWA, your server-hosted web app should include following minimum requirements.</span></span>  

| <span data-ttu-id="2c5dd-154">要求</span><span class="sxs-lookup"><span data-stu-id="2c5dd-154">Requirement</span></span> | <span data-ttu-id="2c5dd-155">详细信息</span><span class="sxs-lookup"><span data-stu-id="2c5dd-155">Details</span></span> | 
|:--- |:--- |  
| [<span data-ttu-id="2c5dd-156">HTTPS</span><span class="sxs-lookup"><span data-stu-id="2c5dd-156">HTTPS</span></span>][WikiHttps] | <span data-ttu-id="2c5dd-157">通过为服务器或应用通信提供安全连接来保护你的用户。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-157">Protect your users by providing a secure connection for server or app communication.</span></span>  <span data-ttu-id="2c5dd-158">服务工作者和其他 PWA 技术仅适用于通过安全连接提供的 web 资源 \ （或来自 `localhost` 于调试目的 \）。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-158">Service Workers and other PWA technologies only work with web resources served over a secure connection \(or from `localhost` for debugging purposes\).</span></span>  |  
| [<span data-ttu-id="2c5dd-159">服务工作进程</span><span class="sxs-lookup"><span data-stu-id="2c5dd-159">Service Workers</span></span>][MDNServiceWorkerApi] | <span data-ttu-id="2c5dd-160">使用服务工作线程在服务器和客户端应用之间充当网络代理，以便提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-160">Use Service Worker threads to act as network proxies between your server and client app in order to provide offline support, resource caching, push notifications, background data sync, and  page load perf optimizations.</span></span>  |  
| [<span data-ttu-id="2c5dd-161">Web App 清单</span><span class="sxs-lookup"><span data-stu-id="2c5dd-161">Web App Manifest</span></span>][MDNWebAppManifest] | <span data-ttu-id="2c5dd-162">提供基于 JSON 的元数据文件，描述有关你的 web 应用的关键信息 \ （如图标、语言和 URL 入口点 \），以便 Windows 10 和其他主机平台能够为你的 PWA 用户提供可安装的、具有类似应用的体验。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-162">Provide a JSON-based metadata file describing key information about your web app \(such as icons, language, and URL entry point\), so that Windows 10 and other host platforms are able to provide your PWA users with an installable, native app-like experience.</span></span>  |  

<span data-ttu-id="2c5dd-163">若要成为绝佳的 PWA，你的应用还必须满足以下要求。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-163">To be a great PWA, your app must also meet the following requirements.</span></span>  

| <span data-ttu-id="2c5dd-164">要求</span><span class="sxs-lookup"><span data-stu-id="2c5dd-164">Requirement</span></span> | <span data-ttu-id="2c5dd-165">详细信息</span><span class="sxs-lookup"><span data-stu-id="2c5dd-165">Details</span></span> | 
|:--- |:--- |  
| [<span data-ttu-id="2c5dd-166">跨浏览器兼容性</span><span class="sxs-lookup"><span data-stu-id="2c5dd-166">Cross-browser compatibility</span></span>][MDNCrossBrowserTesting] | <span data-ttu-id="2c5dd-167">通过在不同的浏览器和环境中进行[测试][MicrosoftDeveloperEdgeToolsRemote]，确保你的 PWA 正常工作。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-167">Ensure your PWA works by [testing][MicrosoftDeveloperEdgeToolsRemote] in different browsers and environments.</span></span>  |  
| [<span data-ttu-id="2c5dd-168">响应式设计</span><span class="sxs-lookup"><span data-stu-id="2c5dd-168">Responsive design</span></span>][WikiResponsiveWebDesign] | <span data-ttu-id="2c5dd-169">使用具有 CSS[网格][MDNCssGridLayout]、 [flexbox][MDNCssFlexibleBoxLayout]、CSS[网格][MDNCssGridLayout]和[flexbox][MDNCssFlexibleBoxLayout] 、[媒体查询][MDNMediaQueries]和[响应图像][MDNResponsiveImages]的流畅布局和灵活的图像，将你的 UX 调整到你的用户设备。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-169">Employ fluid layouts and flexible images with CSS [grid][MDNCssGridLayout], [flexbox][MDNCssFlexibleBoxLayout], CSS [grid][MDNCssGridLayout] and [flexbox][MDNCssFlexibleBoxLayout] , [media queries][MDNMediaQueries], and [responsive images][MDNResponsiveImages] to adapt your UX to your user's device.</span></span>  <span data-ttu-id="2c5dd-170">使用浏览器中的[设备仿真工具][DevToolsGuide|::ref1::|]进行本地测试，或设置[远程调试会话][DevToolsProtocolClientsEdgeDevToolsPreview]以在目标设备上直接测试。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-170">Use [device emulation tools][DevToolsGuide|::ref1::|] from your browser to test locally, or set up a [remote debugging session][DevToolsProtocolClientsEdgeDevToolsPreview] to test directly on a target device.</span></span>  |  
| [<span data-ttu-id="2c5dd-171">深层链接</span><span class="sxs-lookup"><span data-stu-id="2c5dd-171">Deep linking</span></span>][WikiDeepLinking] | <span data-ttu-id="2c5dd-172">将网站的每个页面路由到唯一的 URL，以便现有用户可以通过社交媒体共享帮助您更多的受众参与。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-172">Route each page of your site to a unique URL so existing users may help you engage an even broader audience through social media sharing.</span></span>  |  
| [<span data-ttu-id="2c5dd-173">最佳实践</span><span class="sxs-lookup"><span data-stu-id="2c5dd-173">Best practices</span></span>][Webhint] | <span data-ttu-id="2c5dd-174">使用[Webhint][Webhint] linter 之类的代码质量工具来优化应用的效率、可靠性、安全性和辅助功能。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-174">Use code quality tools like the [Webhint][Webhint] linter to optimize the efficiency, robustness, safety, and accessibility of your app.</span></span>  |  
| [<span data-ttu-id="2c5dd-175">Chromium PWA 清单</span><span class="sxs-lookup"><span data-stu-id="2c5dd-175">Chromium PWA Checklist</span></span>][WebDevGoodPwaChecklist] | <span data-ttu-id="2c5dd-176">对照 Google 基线 PWA 清单检查 PWA。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-176">Check your PWA against the Google baseline PWA checklist.</span></span>  |  

<span data-ttu-id="2c5dd-177">如果要将 PWA 转换为[Microsoft Store][MicrosoftDeveloperStore]应用程序，请转到 "[渐进 Web 应用（EdgeHTML）][PwaEdgehtmlMicrosoftStore] " 文档。</span><span class="sxs-lookup"><span data-stu-id="2c5dd-177">If you want to turn your PWA into a [Microsoft Store][MicrosoftDeveloperStore] application, head to the [Progressive Web Apps (EdgeHTML)][PwaEdgehtmlMicrosoftStore] documentation.</span></span>  
  

<!-- image links -->  

[ImageISearch]: media/i_search.png  
[ImageIPackage]: media/i_package.png  
[ImageIPushNotification]: media/i_push-notification.png  
[ImageIOffline]: media/i_offline.png  
[ImageIProgressive]: media/i_progressive.png  
[ImageISecurity]: media/i_security.png  
[ImageIResponsive]: media/i_responsive.png  
[ImageILink]: media/i_link.png  

[ImageInstallPwa]: ./media/Install_PWA.png  
[ImageAppMenus]: ./media/App_menus.png  

<!-- links -->  

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview-DevTools 协议客户端"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "枚举"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps.md "调试渐进式 Web 应用"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 中的新增功能"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 中的新增功能"  
[PwaEdgehtmlIndex]: ../progressive-web-apps-edgehtml/index.md "Windows 上的渐进式 Web 应用（EdgeHTML）"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps-edgehtml/microsoft-store.md "Microsoft Store 中的渐进式 Web 应用"
<!--PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps-edgehtml/microsoft-store.md#criteria-for-automatic-submission "Criteria for automatic submission - Progressive Web Apps in the Microsoft Store"  -->  

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
[MicrosoftEdge]: https://www.microsoft.com/edge "下载新的 Microsoft Edge 浏览器"  
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
[MDNResponsiveImages]: https://developer.mozilla.org/docs/Learn/HTML/Multimedia_and_embedding/Responsive_images "快速响应图像 |MDN"  
[MDNServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
[MDNSyncManager]: https://developer.mozilla.org/docs/Web/API/SyncManager "SyncManager |MDN"  
[MDNWebAppManifest]: https://developer.mozilla.org/docs/Web/Manifest "Web App 清单 |MDN"  

[BuildVideo]: https://www.youtube.com/watch?v=y4p_QHZtMKM "PWA 视频"

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "什么使 Web 应用成为一个好的渐进？ |web 开发"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接-维基百科"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-维基百科"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 web 设计-维基百科"  
