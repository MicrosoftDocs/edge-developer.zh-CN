---
description: 渐进式 Web 应用在 Windows 10 上本地运行。  下面是作为 Web 开发人员需要知道的一切内容。
title: Windows 上的渐进式 Web 应用 (EdgeHTML)
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
ms.technology: pwa
keywords: 渐进式 Web 应用， PWA， Edge， JavaScript， Windows， UWP， Microsoft Store
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 87996f6be7c1963c01a476b307a31e689e3880d4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232392"
---
# Windows 上的渐进式 Web 应用 (EdgeHTML)  

使用 [渐进式 Web][MDNApps] 应用 \ (或简单的 PWA\) 则不需要决定使用开放 Web 技术实现跨平台互操作性，还是为用户提供为设备自定义的本机类似应用的体验。  这是因为 PWA 只是逐步增强的网站，可以[][AListApartUnderstandingProgressiveEnhancement]像支持平台上的本机应用一样运行。  PWA 的特性结合了最好的 Web 和本机应用。  

:::row:::
    :::column:::
        ![可发现图标][ImageISearch]
        ### [可发现][MDNPwaAdvantagesDiscoverable]
        从 Web 搜索结果和支持的应用商店
    :::column-end:::
    :::column:::
        ![可安装图标][ImageIPackage]
        ### [可安装][MDNPwaAdvantagesInstallable]
        从主屏幕固定和启动  
    :::column-end:::
    :::column:::
        ![可重新参与的图标][ImageIPushNotification]
        ### [重新参与][MDNPwaAdvantagesReEngageable]
        发送推送通知，即使应用不处于活动状态  
    :::column-end:::
    :::column:::
        !["网络独立"图标][ImageIOffline]
        ### [独立于网络][MDNPwaAdvantagesNetworkIndependent]
        在低网络条件下脱机工作  
    :::column-end:::
:::row-end:::
:::row:::
    :::column:::
        ![渐进图标][ImageIProgressive]
        ### [渐进][MDNPwaAdvantagesProgressive]
        体验使用设备 (向上或向下\) \缩放\  
    :::column-end:::
    :::column:::
        ![安全图标][ImageISecurity]
        ### [安全][MDNPwaAdvantagesSafe]
        提供安全的 HTTPS 终结点和其他用户安全措施  
    :::column-end:::
    :::column:::
        ![响应图标][ImageIResponsive]
        ### [响应][MDNPwaAdvantagesResponsive]
        适应用户的屏幕大小/方向和输入方法  
    :::column-end:::
    :::column:::
        ![可链接图标][ImageILink]
        ### [可链接][MDNPwaAdvantagesLinkable]
        从标准超链接共享和启动  
    :::column-end:::
:::row-end:::

通过构建现有网站或将其转换为 PWA，您可以使用推送通知和脱机支持更好地吸引现有受众。  同时，当用户通过搜索和链接共享发现 PWA 时，您可以继续在开放 Web 上构建受众。  

## Windows 10 上的 PWA (EdgeHTML)   

> [!NOTE]
> 随着从 EdgeHTML (Microsoft Edge) Chromium，PWA 使用的基础 Web 平台并不相同。  Edge (Chromium) 在浏览器中安装并运行 PBA。  Edge (EDGEHTML) PWA 作为通用 Windows 平台运行 (UWP) 应用程序并使用旧版 EdgeHTML Web 平台。  如果需要 PWA 的 Windows 10 API 访问权限，此 EdgeHTML 文档适合你。  如果你的目标是在没有 Windows 特定 API 访问权限的情况下实现跨平台支持，请前往 Microsoft Edge ([Chromium) PWA 文档][PwaChromiumIndex]。  

构建渐进式 Web 应用以利用 Windows 10 时，可以通过 [Microsoft Store][MicrosoftDeveloperStore]分发 PWA，整个 Windows 10 安装库（每月活动用户数超过 6 亿）是潜在应用受众！  这样开发的应用程序作为通用 [Windows 平台][WindowsUWPGetStartedGuide] 应用运行，并且具有对 WinRT API 的本机访问权限。  请注意，在使用 WinRT API 时，呈现代码的 Web 平台是 EdgeHTML，因此请确保在调用任何 Windows 特定 API 之前使用功能检测，以确保 PWA 仍可在 Microsoft Edge \ (Chromium\) PWA 可用的平台上运行。  

[下面是如何开始][PwaEdgehtmlGetStarted] 将 Web 应用转换为 PWA \ (EdgeHTML\) 、在 Windows 10 上测试它，以及如何在 Microsoft Store 中分发它。  

## 要求  

若要作为 PWA 运行，服务器托管的 Web 应用至少需要：  

*   [HTTPS][WikiHttps]。  通过为服务器/应用通信提供安全连接来保护用户。  服务工作人员和其他 PWA 技术仅处理通过安全连接 \ (或用于调试 `localhost` 目的\) 。  
  
*   [服务工作者][MDNServiceWorkerApi]。  使用服务工作线程充当服务器和客户端应用之间的网络代理，以提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载优化。  

*   [Web 应用清单][MDNWebAppManifest]。  提供一个基于 JSON 的元数据文件，用于描述有关 Web 应用 \ (（如图标、语言和 URL 入口点\) ）的关键信息，以便 Windows 10 和其他主机平台能够为 PWA 用户提供可安装的本机类似应用的体验。  将网站与 Web 应用清单相关联，使其可以通过必应索引服务自动包含在 [Microsoft Store][PwaEdgehtmlMicrosoftStoreImportingBing] 中。  

若要成为出色的 PWA，你的应用还需要：  

*   [跨浏览器兼容性][MDNCrossBrowserTesting]。  通过在不同浏览器和环境 [中进行测试][MicrosoftDeveloperEdgeToolsRemote] ，确保 PWA 正常工作。  在 Windows 10 上，请务必在 Microsoft Edge 浏览器和完整的 PWA 体验中测试你的应用：作为由 EdgeHTML 引擎\ (支持的独立 Windows 10 应用\) 。  
  
*   [响应式设计][WikiResponsiveWebDesign]。  将流畅的布局和灵活的图像与 CSS[网格][MDNCssGridLayout]和/或[弹性][MDNCssFlexibleBoxLayout]框、媒体查询和 [响应式图像[][MDNMediaQueries][MDNResponsiveImages]一起用于使用户体验适应用户设备。  使用[浏览器的设备仿真][DevToolsGuideEmulation]工具在本地进行测试，或设置远程调试会话以直接在目标[][DevToolsProtocolClientsEdgeDevToolsPreview]设备上进行测试。  在 Windows 10 上，PWA \ (EdgeHTML\) 还可以针对台式机、[][WindowsUWPDesignDevicesIndex]手机和平板电脑之外的外形设备进行定制，包括[：Xbox 和电视][WindowsUWPDesignDevicesDesigningTv][、Surface Hub][MicrosoftDeveloperWindowsSurfaceHub]和[Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality]设备。  
  
*   [深层链接][WikiDeepLinking]。  将网站的每个页面路由到唯一 URL，以便现有用户可以通过社交媒体共享来吸引更广泛的受众。  

*   [最佳做法][Webhint]。  使用 [Webhint][Webhint] linter 等代码质量工具优化应用的效率、稳定性、安全性和辅助功能。  

若要将渐进式 Web 应用提交到 [Microsoft Store，][MicrosoftDeveloperStore]你必须：  

*   [Microsoft 开发人员帐户][WindowsUWPPublishDeveloperAccount]  
*   发布 [Windows 应用已完成的步骤][WindowsUWPPublishIndex]  

未来几个月，必应搜索引擎将 Web 上的现有[][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]PA 会议特定条件自动索引到 Microsoft Store \ (开发人员可以在其中直接管理 Windows 10 受众\) 。  

有关详细信息，请参阅 Microsoft store [ (EdgeHTML) 中的 PWA。][PwaEdgehtmlMicrosoftStore]  

## 当前可用性  

对渐进式 Web 应用的浏览器引擎支持调用许多体系结构组件，最重要的是提取 API 底层 [的网络基础结构][MDNFetchApi]。  EdgeHTML 引擎中的 PWA 支持在 Windows 10 1809 版本中完成。  此后对 Web 标准的进一步改进不会合并到 EdgeHTML 引擎中，因此，请确保运行兼容性测试，并使用功能检测在 EdgeHTML 平台上不支持 PWA 需要的功能时正常回退。  

对于即将在 2020 年发布的 Microsoft Edge \ (Chromium\) ，浏览器平台完全支持这些功能，这些功能适用于支持 Chromium 浏览器的设备。  

对于 EdgeHTML 和 Windows，以下是基于标准的 PWA 技术的当前状态：  

| 技术 | 用途 | 可用性 | 使用说明 |  
|:--- |:--- |:--- |:--- |  
| [Web 应用程序清单][MDNWebAppManifest] | 向主机操作系统提供应用元数据，以启用安装和应用商店促销。  对于 Microsoft Store 中的 PWA，此为必需项。  | [在开发中][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | 目前，您可以使用 [PWA 生成器][|::ref1::|] 生成与 W3C 兼容的 JSON 清单，并针对各种操作系统平台打包应用。  对于 Windows，PWA 生成器将 JSON 清单转换为 `.appxmanifest` Windows 10 (所需的 \) XML\) 格式。  |  
| [提取 API][MDNFetchApi] | 为页面资源 (异步网络 \) 请求、响应\响应 |[EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] /内部版本 14393+ | 服务 [工作线程 API][MDNServiceWorkerApi] 语法基于基于提取的网络 API。  还可以更通常地使用 [Fetch API][MDNFetchApi] 作为新式替代 `XMLHttpRequest` 项。  |  
| [服务工作者 API][MDNServiceWorkerApi] | 提供支持脱机的 Web 应用模型/网络代理，其中事件驱动的脚本独立于网页运行  | [EdgeHTML17/][DevGuideWhatsNewEdgeHtml17] 内部版本 17133+ | EdgeHTML `Enable Service Workers` 16 中 (标记后\) 实验支持。  EdgeHTML 17+ 内部版本默认启用。  |  
| [缓存 API][MDNCache] | 为网络请求/响应对提供存储机制 | [EdgeHTML17/][DevGuideWhatsNewEdgeHtml17] 内部版本 17133+ | 请参阅 [上面的服务工作者 API][MDNServiceWorkerApi] 注释。  |  
| [推送 API][MDNPushApi] | 使服务工作者能够订阅推送通知 |[EdgeHTML17/][DevGuideWhatsNewEdgeHtml17] 内部版本 17133+| 请参阅 [上面的服务工作者 API][MDNServiceWorkerApi] 注释。  Windows 10 应用 \ (包括 PWA\) 需要[Windows 推送通知服务 \ (WNS\) ][WindowsUWPControlsPatternTilesNotificationsWns]以提供推送通知，它支持 W3C[推送 API。][MDNPushApi]  |  
| [通知 API][MDNNotificationsApi] | 使服务工作者能够在推送消息时向用户显示系统通知 | [EdgeHTML 14+][DevGuideWhatsNewEdgeHtml14] /内部版本 14393+ | EdgeHTML 中的 Web 通知与 Windows [10][MicrosoftSupportWindowsNotificationSettings]操作中心完全集成，用户可以管理应用通知并设置 [安静时间][MicrosoftSupportWindowsFocusAssist]。  |  
| [后台同步 API][MDNSyncManager] | 提供一个 API，用于通知服务工作者用户已重新联机并安排定期事件以将本地数据与服务器同步 | [在开发中][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | 目前，可以使用本机 [WinRT BackgroundTask API][WindowsUWPLaunchResumeBackgroundTasks] 在 PWA 作为 Windows 10 应用运行时实现后台任务。  |  

下面是 Windows 10 上对 PWA 的 Microsoft Store 支持的当前状态：  

| 应用商店提交方法 | 状态 | 详细信息 |  
|:--- |:--- |:--- |  
| 手动 \ (启动\)  | 可用 | 查看 [Microsoft Store (EdgeHTML) 中的 PWA][PwaEdgehtmlMicrosoftStore] 以开始使用。  |  
| 使用必应 (自动编制索引的自动 \)  | 即将推出 | 目前 [，我们正在通过][WindowsBlogsWelcomingPWAsEdgeWindows] 有限的应用合作伙伴子集试用 PWA 载入过程。  未来几个月，Microsoft 欢迎主流 Web 中的 PWA 使用 Microsoft Store。  查看使用 [必应的自动 PWA][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission] 导入，了解有关自动生成的 PWA 列表的 Microsoft Store 要求。  |  

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

[DevToolsProtocolClientsEdgeDevToolsPreview]: ../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview "Microsoft Edge DevTools Preview - DevTools 协议客户端 |Microsoft Docs"  
[DevToolsGuideEmulation]: ../devtools-guide/emulation.md "模拟 |Microsoft Docs"  
[DevGuideWhatsNewEdgeHtml17]: ../dev-guide/whats-new/edgehtml-17.md "EdgeHTML 17 中的新增功能 |Microsoft Docs"  
[DevGuideWhatsNewEdgeHtml14]: ../dev-guide/whats-new/edgehtml-14.md "EdgeHTML 14 中的新增功能 |Microsoft Docs"  
[PwaChromiumIndex]: ../../progressive-web-apps-chromium/index.md "渐进式 Web (Windows 上的 chromium) |Microsoft Docs"  
[PwaEdgehtmlGetStarted]: ../progressive-web-apps/get-started.md "使用 EdgeHTML (渐进式 Web 应用) |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStore]: ../progressive-web-apps/microsoft-store.md "Microsoft Store 中的渐进 Web 应用 |Microsoft Docs"
[PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]: ../progressive-web-apps/microsoft-store.md#criteria-for-automatic-submission "自动提交的条件 - Microsoft Store 中的渐进式 Web 应用 |Microsoft Docs"  
[PwaEdgehtmlMicrosoftStoreImportingBing]: ./microsoft-store.md#automatic-pwa-importing-with-bing "使用必应导入的自动 PWA - (Microsoft Store) EdgeHTML 应用程序 |Microsoft Docs"  


[WindowsUWPControlsPatternTilesNotificationsWns]: /windows/uwp/controls-and-patterns/tiles-and-notifications-windows-push-notification-services--wns--overview.md "Windows 推送通知服务 \ (WNS\) 概述"  
[WindowsUWPDesignDevicesDesigningTv]: /windows/uwp/design/devices/designing-for-tv.md "针对 Xbox 和电视进行设计"  
[WindowsUWPDesignDevicesIndex]: /windows/uwp/design/devices/index.md "UWP 设备的 UI 注意事项"  
[WindowsUWPGetStartedGuide]: /windows/uwp/get-started/universal-application-platform-guide.md "什么是通用 Windows 平台 (UWP) 应用？"  
[WindowsUWPLaunchResumeBackgroundTasks]: /windows/uwp/launch-resume/support-your-app-with-background-tasks.md "使用后台任务支持应用"  
[WindowsUWPPublishIndex]: /windows/uwp/publish/index.md "发布 Windows 应用和游戏"  
[WindowsUWPPublishDeveloperAccount]: /windows/uwp/publish/opening-a-developer-account.md "打开开发人员帐户"  

[WindowsBlogsWelcomingPWAsEdgeWindows]: https://blogs.windows.com/msedgedev/2018/02/06/welcoming-progressive-web-apps-edge-windows-10/#56z7mJwKsykfbR4I.97 "将渐进式 Web 应用用于 Microsoft Edge 和 Windows 10 - Windows 博客"  
[MicrosoftDeveloperEdgePlatformStatusBackgroundSync]: https://developer.microsoft.com/microsoft-edge/platform/status/backgroundsyncapi "后台同步 API - Microsoft Edge 平台状态"  
[MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest]: https://developer.microsoft.com/microsoft-edge/platform/status/webapplicationmanifest "Web 应用程序清单 - Microsoft Edge 平台状态"  
[MicrosoftDeveloperEdgeToolsRemote]: https://developer.microsoft.com/microsoft-edge/tools/remote "即时测试"  
[MicrosoftDeveloperWindowsMixedReality]: https://developer.microsoft.com/windows/mixed-reality "适用于开发人员的混合现实"  
[MicrosoftDeveloperWindowsSurfaceHub]: https://developer.microsoft.com/windows/surfacehub "Microsoft Surface Hub"  
[MicrosoftDeveloperStore]: https://developer.microsoft.com/store "Microsoft Developer Store"  
[MicrosoftSupportWindowsFocusAssist]: https://support.microsoft.com/help/4026996/windows-10-turn-focus-assist-on-or-off "在 Windows 10 中打开或关闭焦点辅助"  
[MicrosoftSupportWindowsNotificationSettings]: https://support.microsoft.com/help/4028678/windows-10-change-notification-settings "更改 Windows 10 中的通知设置"  

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

[PWABuilder]: https://www.pwabuilder.com "PWABuilder"  

[Webhint]: https://webhint.io "webhint"  

[WikiDeepLinking]: https://en.wikipedia.org/wiki/Deep_linking "深层链接 - Wikipedia"  
[WikiHttps]: https://en.wikipedia.org/wiki/HTTPS "HTTPS - Wikipedia"  
[WikiResponsiveWebDesign]: https://en.wikipedia.org/wiki/Responsive_web_design "响应式 Web 设计 - Wikipedia"  
