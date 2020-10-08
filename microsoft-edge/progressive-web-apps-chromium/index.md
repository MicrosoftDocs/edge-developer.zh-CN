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
# Windows 上的渐进式 Web 应用  

[渐进式 Web 应用][MDNApps] \ (PWAs \ ) 提供对开放 Web 技术以实现跨平台互操作性的访问权限，并为用户提供针对其设备自定义的与应用类似的本机体验。  PWAs 是在支持平台上以本机应用的形式 [逐渐增强][AListApartUnderstandingProgressiveEnhancement] 到功能的网站。  PWA 的特性结合了最好的 Web 和本机应用。  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [Dsgetdcname][MDNPwaAdvantagesDiscoverable]
        从 web 搜索结果和支持应用商店
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [可安装][MDNPwaAdvantagesInstallable]
        通过主屏幕、"开始" 菜单、任务栏等固定和启动
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [重新 engageable][MDNPwaAdvantagesReEngageable]
        发送推送通知，即使应用未处于活动状态
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_offline.png":::
        ### [独立于网络][MDNPwaAdvantagesNetworkIndependent]
        在低网络条件下脱机工作
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_progressive.png":::
        ### [累进][MDNPwaAdvantagesProgressive]
        体验通过设备功能放大 (或下降) 
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [安全][MDNPwaAdvantagesSafe]
        提供安全 HTTPS 终结点和其他用户保护
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [响应][MDNPwaAdvantagesResponsive]
        适应用户的屏幕大小或方向和输入法
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [Linkable][MDNPwaAdvantagesLinkable]
        从标准超链接共享和启动
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


内部版本 \ (或将 \ ) 现有网站转换为 PWA，以增强您与用户的合作。  增强功能包括推送通知、类似应用的集成和脱机支持。  继续在打开的 web 上构建受众，让用户通过 "搜索" 和 "链接共享" 发现你的 PWA。  最重要的是，你的应用会使用你的 web 服务器代码进行更新。  

## Microsoft Edge (Chromium) PWAs  

当你生成针对 web 标准 Api 的渐进式 Web 应用时，你的应用程序可能会跨平台和设备部署，并充分利用特定于设备的功能。  Microsoft Edge 中的 PWAs \ (Chromium \ ) 将以下优势添加到您的网站。  

*   你的应用基于基于标准的 web 平台构建。  
*   使你的用户能够直接从浏览器安装你的应用。  
*   使你的用户能够在不使用基于应用商店的部署或注册的情况下安装你的应用。  
    
Microsoft Edge \ (Chromium \ ) 可用的任何平台都支持桌面 PWAs。 Microsoft Edge \ (Chromium \ ) 在 Windows 7、Windows 10 和 macOS 上可用。  包括以下优点。  

*   可以使用导航栏中的 " **安装** " 图标直接从浏览器内部安装应用程序。  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="安装应用程序浮出控件和图标" lightbox="./media/install_pwa_icon.png":::
       安装应用程序浮出控件和图标  
    :::image-end:::  
    
*   也可以从 "**设置**  >  **应用**" 菜单中安装、运行和管理应用程序  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="安装应用程序浮出控件和图标" lightbox="./media/app_menus.png":::
       "设置" 下的 "应用程序" 菜单项  
    :::image-end:::  
    
*   Web 通知集成到 Windows 通知系统中  
*   与安装了该应用的浏览器配置文件共享的 cookie 存储  
*   使用 " **设置" 和 "更多** \ (`...` \ ) " 菜单（包括证书验证、网站权限、跟踪保护和浏览器扩展）访问其他浏览器功能  
*   对 [Microsoft Edge DevTools][DevtoolsProgressiveWebApps] 的完全访问权限调试你的应用  
    
> [!IMPORTANT]
> 若要针对使用 JavaScript 进行 WinRT API 请求的 Windows 10 专门定制 PWAs，请导航到 [特定于 EDGEHTML PWA 功能的文档][PwaEdgehtmlIndex]。  了解有关在 Windows 10 上测试 PWA 并将其分发到 Microsoft Store 的详细信息。  

> [!NOTE]
> 有关 PWA 优势、即将推出的功能和简短演示的详细信息，请导航到 [内部版本 2020 PWA 会话][BuildVideo]。 

## 要求  

若要作为 PWA 运行，服务器托管的 web 应用应包括以下最低要求。  

:::row:::
   :::column span="1":::
      [HTTPS][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      通过为服务器或应用通信提供安全连接来保护你的用户。  服务工作者和其他 PWA 技术仅适用于通过安全连接进行服务的 web 资源 (或 `localhost` 用于调试目的 \ ) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [服务工作进程][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      使用服务工作线程充当服务器和客户端应用之间的网络代理。  服务工作线程提供离线支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Web App 清单][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      提供一个基于 JSON 的元数据文件，该文件描述有关你的 web 应用的关键信息，因此 Windows 10 和其他主机平台为你的 PWA 用户提供了可安装的、类似于应用的内置体验。  关键信息包括图标、语言和 URL 入口点。 
   :::column-end:::
:::row-end:::  

若要成为绝佳的 PWA，你的应用还必须满足以下要求。  

:::row:::
   :::column span="1":::
      [跨浏览器兼容性][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      通过在不同的浏览器和环境中进行 [测试][MicrosoftDeveloperEdgeToolsRemote] ，确保你的 PWA 正常工作。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [响应式设计][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      采用流畅的布局和灵活的图像。  响应式设计包括以下元素，这些元素可将你的 UX 调整为你的用户设备。  
      
      *   CSS [网格][MDNCssGridLayout]  
      *   [flexbox][MDNCssFlexibleBoxLayout]  
      *   CSS [网格][MDNCssGridLayout] 和 [flexbox][MDNCssFlexibleBoxLayout]  
      *   [媒体查询][MDNMediaQueries]  
      *   [响应图像][MDNResponsiveImages]  
      
      使用浏览器中的 [设备仿真工具][DevToolsGuide|::ref1::|] 进行本地测试，或创建 [远程调试会话][DevToolsProtocolClientsEdgeDevToolsPreview] 以直接在目标设备上进行测试。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [深层链接][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      将网站的每个页面路由到唯一的 URL，以便现有用户可以通过社交媒体共享帮助您更多的受众参与。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [验证和测试实践][Webhint]  
   :::column-end:::
   :::column span="2":::
      使用 [Webhint][Webhint] linter 之类的代码质量工具来优化应用的效率、可靠性、安全性和辅助功能。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Chromium PWA 清单][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      针对 Google 基线 PWA 清单验证你的 PWA。  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> 若要将 PWA 转换为 [Microsoft store][MicrosoftDeveloperStore] 应用程序，请导航到 [microsoft Store 中 (EdgeHTML) 的渐进式 Web 应用][PwaEdgehtmlMicrosoftStore]。  
  
## 另请参阅  

*   [Myth Busting PWAs][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [渐进式 Web 应用的渐进式路线图][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [具有渐进的 Web 应用的脱机文章][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA 问答&][AaronGustafsonNotebookPwaQa]  
*   [在网上打赌][JoretegBlogBettingWeb]  
*   [命名渐进式 Web 应用][Fberriman20170626NamingProgressiveWebApps]  
*   [设计和构建不带框架 (第1部分) 的渐进式 Web 应用程序][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [设计和构建不带框架 (第2部分) 的渐进式 Web 应用程序][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [设计和构建不带框架 (第3部分) 的渐进式 Web 应用程序][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
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
