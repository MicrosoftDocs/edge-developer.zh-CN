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
ms.openlocfilehash: 482f498e246ee265424f7b80ff3cd67f78501ee2
ms.sourcegitcommit: 9169d784485e3cb0b1987a8f395c4bb688bd9b2e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "10583033"
---
# Windows 上的渐进式 Web 应用  

使用[渐进式 Web 应用][MDNApps]\ （或只是 PWAs \），无需在使用开放 Web 技术实现跨平台互操作性和为用户提供针对其设备自定义的本机应用体验之间做出决定。  PWAs 是在支持平台上以本机应用的形式[逐渐增强][AListApartUnderstandingProgressiveEnhancement]到功能的网站。  PWA 的特性结合了最好的 Web 和本机应用。  

:::row:::
    :::column:::
        ![可发现图标][ImageISearch]
        ### [Dsgetdcname][MDNPwaAdvantagesDiscoverable]
        从 web 搜索结果和支持应用商店
    :::column-end:::
    :::column:::
        ![可安装图标][ImageIPackage]
        ### [可安装][MDNPwaAdvantagesInstallable]
        通过主屏幕、"开始" 菜单、任务栏等固定和启动
    :::column-end:::
    :::column:::
        ![重新 engageable 图标][ImageIPushNotification]
        ### [重新 engageable][MDNPwaAdvantagesReEngageable]
        发送推送通知，即使应用未处于活动状态
    :::column-end:::
    :::column:::
        ![网络独立图标][ImageIOffline]
        ### [独立于网络][MDNPwaAdvantagesNetworkIndependent]
        在低网络条件下脱机工作
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        !["渐进" 图标][ImageIProgressive]
        ### [累进][MDNPwaAdvantagesProgressive]
        体验通过设备功能放大（或缩小）
    :::column-end:::
    :::column:::
        ![安全图标][ImageISecurity]
        ### [安全][MDNPwaAdvantagesSafe]
        提供安全 HTTPS 终结点和其他用户保护
    :::column-end:::
    :::column:::
        ![响应图标][ImageIResponsive]
        ### [响应][MDNPwaAdvantagesResponsive]
        适应用户的屏幕大小或方向和输入法
    :::column-end:::
    :::column:::
        ![Linkable 图标][ImageILink]
        ### [Linkable][MDNPwaAdvantagesLinkable]
        从标准超链接共享和启动
    :::column-end:::
:::row-end:::

通过构建现有网站或将其转换为 PWA，你可以更好地使用推送通知、类似于应用的集成和脱机支持与你的现有受众取得联系。  同时，你应该在打开的网站上继续构建受众，因为用户通过搜索和链接共享发现你的 PWA。  最重要的是，你只需更新 web 服务器代码即可更新你的应用。  

## Microsoft Edge 上的 PWAs （Chromium）  

当你生成针对 web 标准 Api 的渐进式 Web 应用时，你的应用程序可能会跨平台和设备部署，并充分利用特定于设备的功能。  Microsoft Edge \ （Chromium \）中的 PWAs 是完全基于 web 平台角度的标准，可让用户直接在浏览器中安装应用，而无需基于应用商店的部署或注册。  Microsoft Edge \ （Chromium \）可用的任何平台上都支持桌面 PWAs，包括 Windows 7、Windows 10 和 macOS。  其他好处包括：  

*   通过导航栏中的 "**安装**" 图标，可以直接从浏览器内部安装应用程序。  
    
    ![安装应用程序浮出控件和图标][ImageInstallPwa]  
    
*   也可以从 "**设置**  >  **应用**" 菜单安装、运行和管理应用程序  
    
    !["设置" 下的 "应用程序" 菜单项][ImageAppMenus]  

*   Web 通知集成到 Windows 通知系统中
*   与安装了该应用的浏览器配置文件共享的 cookie 存储
*   通过 `...` 菜单（包括证书验证、网站权限、跟踪保护和浏览器扩展）访问其他浏览器功能
*   对[Microsoft Edge DevTools][DevtoolsProgressiveWebApps]的完全访问权限调试你的应用  

> [!IMPORTANT]
> 若要针对使用 JavaScript 进行 WinRT API 请求的 Windows 10 专门定制 PWAs，请参阅[特定于 EDGEHTML PWA 功能的文档][PwaEdgehtmlIndex]。  了解有关在 Windows 10 上测试 PWA 并将其分发到 Microsoft Store 的详细信息。  

## 要求  

若要作为 PWA 运行，服务器托管的 web 应用应包括以下最低要求。  

|  | 要求 | 详细信息 | 
|:--- |:--- |:--- |  
| X | [HTTPS][WikiHttps] | 通过为服务器或应用通信提供安全连接来保护你的用户。  服务工作者和其他 PWA 技术仅适用于通过安全连接提供的 web 资源 \ （或来自 `localhost` 于调试目的 \）。  |  
| X | [服务工作人员][MDNServiceWorkerApi] | 使用服务工作线程在服务器和客户端应用之间充当网络代理，以便提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。  |  
| X | [Web App 清单][MDNWebAppManifest] | 提供基于 JSON 的元数据文件，描述有关你的 web 应用的关键信息 \ （如图标、语言和 URL 入口点 \），以便 Windows 10 和其他主机平台能够为你的 PWA 用户提供可安装的、具有类似应用的体验。  |  

若要成为绝佳的 PWA，你的应用还必须满足以下要求。  

|  | 要求 | 详细信息 | 
|:--- |:--- |:--- |  
| X | [跨浏览器兼容性][MDNCrossBrowserTesting] | 通过在不同的浏览器和环境中进行[测试][MicrosoftDeveloperEdgeToolsRemote]，确保你的 PWA 正常工作。  |  
| X | [响应式设计][WikiResponsiveWebDesign] | 使用具有 CSS[网格][MDNCssGridLayout]、 [flexbox][MDNCssFlexibleBoxLayout]、CSS[网格][MDNCssGridLayout]和[flexbox][MDNCssFlexibleBoxLayout] 、[媒体查询][MDNMediaQueries]和[响应图像][MDNResponsiveImages]的流畅布局和灵活的图像，将你的 UX 调整到你的用户设备。  使用浏览器中的[设备仿真工具][DevToolsGuide|::ref1::|]进行本地测试，或设置[远程调试会话][DevToolsProtocolClientsEdgeDevToolsPreview]以在目标设备上直接测试。  |  
| X | [深层链接][WikiDeepLinking] | 将网站的每个页面路由到唯一的 URL，以便现有用户可以通过社交媒体共享帮助您更多的受众参与。  |  
| X | [最佳实践][Webhint] | 使用[Webhint][Webhint] linter 之类的代码质量工具来优化应用的效率、可靠性、安全性和辅助功能。  |  
| X | [Chromium PWA 清单][WebDevGoodPwaChecklist] | 对照 Google 基线 PWA 清单检查 PWA。  |  

如果要将 PWA 转换为[Microsoft Store][MicrosoftDeveloperStore]应用程序，请转到 "[渐进 Web 应用（EdgeHTML）][PwaEdgehtmlMicrosoftStore] " 文档。  

## 当前可用性  

浏览器引擎支持针对多个体系结构组件的渐进 Web 应用请求，最重要的是[获取 API][MDNFetchApi]基础的网络基础结构。  

对于 Microsoft Edge \ （Chromium \），浏览器平台包括对在支持 Microsoft Edge \ （Chromium \）的设备上工作的这些功能的完全支持。  

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
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "仿真"  
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

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[WebDevGoodPwaChecklist]: https://web.dev/pwa-checklist "什么使 Web 应用成为一个好的渐进？ |web 开发"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接-维基百科"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS-维基百科"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 web 设计-维基百科"  
