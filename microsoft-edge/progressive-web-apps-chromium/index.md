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
# Windows 上的渐进式 Web 应用概述  

[渐进式 Web][MDNApps] 应用 \ (PWA\) 提供对开放 Web 技术的访问权限，实现跨平台互操作性，并为用户提供为设备自定义的本机、类似应用的体验。  PWA 是逐步增强的网站 [，其功能][AListApartUnderstandingProgressiveEnhancement] 与支持平台上的本机应用类似。  PWA 的特性结合了最好的 Web 和本机应用。  

:::row:::
    :::column:::
        :::image type="icon" source="./media/i_search.png":::
        ### [可发现][MDNPwaAdvantagesDiscoverable]
        从 Web 搜索结果和支持的应用商店
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_package.png":::
        ### [可安装][MDNPwaAdvantagesInstallable]
        从主屏幕、"开始"菜单、任务栏等固定和启动
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_push-notification.png":::
        ### [可重新参与][MDNPwaAdvantagesReEngageable]
        发送推送通知，即使应用不处于活动状态
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
        ### [渐进][MDNPwaAdvantagesProgressive]
        体验通过 (功能) 向上或向下扩展
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_security.png":::
        ### [安全][MDNPwaAdvantagesSafe]
        提供安全的 HTTPS 终结点和其他用户安全措施
    :::column-end:::
:::row-end:::  
:::row:::
    :::column:::
        :::image type="icon" source="./media/i_responsive.png":::
        ### [响应][MDNPwaAdvantagesResponsive]
        适应用户的屏幕大小或方向和输入方法
    :::column-end:::
    :::column:::
        :::image type="icon" source="./media/i_link.png":::
        ### [可链接][MDNPwaAdvantagesLinkable]
        从标准超链接共享和启动
    :::column-end:::
    :::column:::
        &nbsp;  
    :::column-end:::
:::row-end:::  


生成 \ (或转换\) 现有网站转换为 PWA，以增强用户参与度。  增强功能包括推送通知、类似应用的集成和脱机支持。  继续构建开放 Web 上的受众，以便用户通过搜索和链接共享发现 PWA。  最好使用 Web 服务器代码更新应用。  

## Microsoft Edge 上的 PWA (Chromium)   

构建面向 Web 标准 API 的渐进式 Web 应用时，应用程序可能会跨平台和设备部署，并尽可能利用特定于设备的功能。  Microsoft Edge \ (Chromium\) 中的 PWA 为您的网站添加了以下优势。  

*   你的应用基于基于标准的 Web 平台构建。  
*   使用户可以直接从浏览器安装应用。  
*   使用户无需基于应用商店的部署或注册即可安装应用。  
    
桌面 PWA 在任何 Microsoft Edge \ (Chromium\) 都受支持。 Microsoft Edge \ (Chromium\) 在 Windows 7、Windows 10 和 macOS 上可用。  其中包括以下好处。  

*   可以直接在浏览器中使用导航栏中的 **"** 安装"图标安装应用程序。  
    
    :::image type="complex" source="./media/install_pwa_icon.png" alt-text="安装应用程序飞出和图标" lightbox="./media/install_pwa_icon.png":::
       安装应用程序飞出和图标  
    :::image-end:::  
    
*   也可以从"设置应用"菜单安装、运行**和管理**  >  **** 应用程序  
    
    :::image type="complex" source="./media/app_menus.png" alt-text="设置下的应用程序菜单项" lightbox="./media/app_menus.png":::
       设置下的应用程序菜单项  
    :::image-end:::  
    
*   Web 通知已集成到 Windows 通知系统中  
*   具有安装应用程序的浏览器配置文件的共享 Cookie 存储  
*   使用"设置"和更多 **\ (** \) 菜单访问其他浏览器功能，包括证书验证、网站权限、跟踪保护和 `...` 浏览器扩展  
*   对 [用于调试应用的 Microsoft Edge DevTools][DevtoolsProgressiveWebApps] 的完全访问权限  
    
> [!IMPORTANT]
> 若要专门为使用 JavaScript 提出 WinRT API 请求的 Windows 10 定制 PWA，请导航到[特定于 EdgeHTML PWA 功能的文档][PwaEdgehtmlIndex]。  了解有关在 Windows 10 上测试 PWA 和在 Microsoft Store 中分发 PWA 的信息。  

> [!NOTE]
> 有关 PWA 权益、即将推出的功能和简短演示的信息，请导航到 Build [2020 PWA 会话][BuildVideo]。 

## 要求  

若要作为 PWA 运行，服务器托管的 Web 应用应包含以下最低要求。  

:::row:::
   :::column span="1":::
      [HTTPS][WikiHttps]  
   :::column-end:::
   :::column span="2":::
      通过为服务器或应用通信提供安全连接来保护用户。  服务工作人员和其他 PWA 技术仅适用于通过安全连接 \ (或用于调试 `localhost` 目的\) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [服务工作者][MDNServiceWorkerApi]  
   :::column-end:::
   :::column span="2":::
      使用服务工作线程充当服务器和客户端应用之间的网络代理。  服务工作线程提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Web 应用清单][MDNWebAppManifest]  
   :::column-end:::
   :::column span="2":::
      提供一个基于 JSON 的元数据文件，该文件描述有关 Web 应用的关键信息，以便 Windows 10 和其他主机平台为 PWA 用户提供可安装的本机类似应用的体验。  关键信息包括图标、语言和 URL 入口点。 
   :::column-end:::
:::row-end:::  

若要成为出色的 PWA，您的应用程序还必须满足以下要求。  

:::row:::
   :::column span="1":::
      [跨浏览器兼容性][MDNCrossBrowserTesting]  
   :::column-end:::
   :::column span="2":::
      通过在不同浏览器和环境 [中进行测试][MicrosoftDeveloperEdgeToolsRemote] ，确保 PWA 正常工作。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [响应式设计][WikiResponsiveWebDesign]  
   :::column-end:::
   :::column span="2":::
      采用流畅的布局和灵活的图像。  响应式设计包括以下使用户体验适应用户设备的元素。  
      
      *   CSS [网格][MDNCssGridLayout]  
      *   [flexbox][MDNCssFlexibleBoxLayout]  
      *   CSS [网格][MDNCssGridLayout] 和 [弹性框][MDNCssFlexibleBoxLayout]  
      *   [媒体查询][MDNMediaQueries]  
      *   [响应式图像][MDNResponsiveImages]  
      
      使用 [浏览器的设备仿真][DevToolsGuideDeviceModeTestingOtherBrowsers] 工具在本地测试，或在 [Windows][DevtoolsRemoteDebuggingWindows] 或 [Android][DevtoolsRemoteDebuggingIndex] 上创建远程调试会话以直接在目标设备上进行测试。
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [深层链接][WikiDeepLinking]  
   :::column-end:::
   :::column span="2":::
      将网站的每个页面路由到唯一 URL，以便现有用户可以通过社交媒体共享来吸引更广泛的受众。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [验证和测试做法][Webhint]  
   :::column-end:::
   :::column span="2":::
      使用 [Webhint][Webhint] linter 等代码质量工具优化应用的效率、稳定性、安全性和辅助功能。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [Chromium PWA 清单][WebDevGoodPwaChecklist]  
   :::column-end:::
   :::column span="2":::
      根据 Google 基线 PWA 清单验证 PWA。  
   :::column-end:::
:::row-end:::  

> [!NOTE]
> 若要将 PWA 转换为 [Microsoft Store][MicrosoftDeveloperStore] 应用程序，请导航到[Microsoft Store (的渐进式 Web 应用) EdgeHTML 应用程序][PwaEdgehtmlMicrosoftStore]。  
  
## 另请参阅  

*   [实现 PBA 的百万亿元][Davrous20191018MythBustingPwasNewEdgeEdition]  
*   [渐进式 Web 应用的渐进路线图][CloudfourThinksProgressiveRoadmapYourWebApp]  
*   [具有渐进式 Web 应用的脱机 POST][MediumWebEdgeOfflinePostsProgressiveWebApps]  
*   [PWA 问答&A][AaronGustafsonNotebookPwaQa]  
*   [Web 上的百元][JoretegBlogBettingWeb]  
*   [命名渐进式 Web 应用][Fberriman20170626NamingProgressiveWebApps]  
*   [设计和生成不带框架的渐进式 Web (第 1 部分) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart1]  
*   [设计和生成不带框架的渐进式 Web (第 2 部分) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart2]  
*   [设计和生成不带框架的渐进式 Web (第 3 部分) ][Smashingmagazine201907ProgressiveWebApplicationFrameworkPart3]  
    
<!-- links -->  

[DevtoolsRemoteDebuggingIndex]: ../devtools-guide-chromium/remote-debugging/index.md "远程调试 Android 设备入门 |Microsoft Docs"  
[DevtoolsRemoteDebuggingWindows]: ../devtools-guide-chromium/remote-debugging/windows.md "远程调试 Windows 10 设备入门 |Microsoft Docs"  
[DevToolsGuideDeviceModeTestingOtherBrowsers]: ../devtools-guide-chromium/device-mode/testing-other-browsers.md "模拟和测试其他浏览器 |Microsoft Docs"  
[DevtoolsProgressiveWebApps]: ../devtools-guide-chromium/progressive-web-apps/index.md "调试渐进式 Web 应用 |Microsoft Docs"  
<!--[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "What's new in EdgeHTML 17 | Microsoft Docs"  -->  
<!--[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "What's New in EdgeHTML 14 | Microsoft Docs"  -->  
[PwaEdgehtmlIndex]： ../edgehtml/progressive-web-apps/index.md "Windows 上的渐进式 Web (EdgeHTML) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]： ../edgehtml/progressive-web-apps/microsoft-store.md "Microsoft Store 中的渐进 Web 应用 |Microsoft Docs"
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
