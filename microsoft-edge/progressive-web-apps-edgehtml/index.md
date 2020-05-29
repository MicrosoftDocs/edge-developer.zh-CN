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
# Windows 上的渐进式 Web 应用（EdgeHTML）  

通过[渐进式 Web 应用][MDNApps]\ （或只是 PWAs \），你无需在使用开放 Web 技术实现跨平台互操作性和为用户提供针对其设备自定义的本机应用体验之间做出决定。  这是因为 PWAs 只是一种网站，可在支持平台上[逐渐增强][AListApartUnderstandingProgressiveEnhancement]到类似本机应用之类的功能。  PWA 的特性结合了最好的 Web 和本机应用。  

:::row:::
    :::column:::
        ![可发现图标][ImageISearch]
        ### [Dsgetdcname][MDNPwaAdvantagesDiscoverable]
        从 web 搜索结果和支持应用商店
    :::column-end:::
    :::column:::
        ![可安装图标][ImageIPackage]
        ### [可安装][MDNPwaAdvantagesInstallable]
        从主屏幕固定和启动  
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
        体验通过设备功能放大 \ （向上或向下）  
    :::column-end:::
    :::column:::
        ![安全图标][ImageISecurity]
        ### [安全][MDNPwaAdvantagesSafe]
        提供安全 HTTPS 终结点和其他用户保护  
    :::column-end:::
    :::column:::
        ![响应图标][ImageIResponsive]
        ### [响应][MDNPwaAdvantagesResponsive]
        适应用户的屏幕大小/方向和输入法  
    :::column-end:::
    :::column:::
        ![Linkable 图标][ImageILink]
        ### [Linkable][MDNPwaAdvantagesLinkable]
        从标准超链接共享和启动  
    :::column-end:::
:::row-end:::

通过构建现有网站或将其转换为 PWA，你可以通过推送通知和脱机支持更好地与你的现有受众接洽。  同时，你可以继续在打开的网站上构建受众，因为用户通过搜索和链接共享发现你的 PWA。  

## Windows 10 上的 PWAs （EdgeHTML）  

> [!NOTE]
> 通过 EdgeHTML 中的 "移动到 Microsoft Edge" （Chromium），PWAs 使用的基础 web 平台是不同的。  从浏览器中安装和运行 Edge （Chromium） PWAs。  Edge （EdgeHTML） PWAs 作为通用 Windows 平台（UWP）应用程序运行，并使用较早的 EdgeHTML web 平台。  如果你需要 PWA 的 Windows 10 API 访问，此 EdgeHTML 文档适用于你。  如果你的目标是不带 Windows 特定 API 访问的交叉平台支持，请转到[Microsoft Edge （Chromium） PWA 文档][PwaChromiumIndex]。  

当你构建渐进式 Web 应用以利用 Windows 10 时，你可以通过[Microsoft Store][MicrosoftDeveloperStore]分发 PWA，每月100万个活动的每月100万个活动的整个 Windows 10 安装群是你的潜在应用受众！  以这种方式开发的应用程序以[通用 Windows 平台][WindowsUWPGetStartedGuide]应用的形式运行，并具有对 WinRT api 的本机类似访问权限。  请注意，在使用 WinRT Api 时，你的代码的 web 平台呈现是 EdgeHTML 的，因此请确保在调用任何特定于 Windows 的 Api 之前使用功能检测，以确保你的 PWA 能够在 Microsoft Edge \ （Chromium \） PWAs 可用的平台上保持运行。  

[下面介绍如何开始][PwaEdgehtmlGetStarted]将 web 应用转换为 PWA \ （EdgeHTML \），在 Windows 10 上对其进行测试，并将其分发到 Microsoft Store 中。  

## 要求  

若要以 PWA 的形式运行，您的服务器托管的 web 应用至少需要：  

*   [X] [HTTPS][WikiHttps]。  通过为服务器/应用通信提供安全连接来保护你的用户。  服务工作者和其他 PWA 技术仅适用于通过安全连接提供的 web 资源 \ （或来自 `localhost` 于调试目的 \）。  
  
*   [X][服务工作者][MDNServiceWorkerApi]。  使用服务工作线程在服务器和客户端应用之间充当网络代理，以便提供脱机支持、资源缓存、推送通知、后台数据同步和页面加载性能优化。  

*   [X] [Web app 清单][MDNWebAppManifest]。  提供基于 JSON 的元数据文件，描述有关你的 web 应用的关键信息 \ （如图标、语言和 URL 入口点 \），以便 Windows 10 和其他主机平台能够为你的 PWA 用户提供可安装的、具有类似应用的体验。  将您的网站与 web 应用清单相关联使其能够通过必应索引服务[自动包含在 Microsoft Store 中][PwaEdgehtmlMicrosoftStoreImportingBing]。  

若要成为绝佳的 PWA，你的应用还需要：  

*   [X][跨浏览器的兼容性][MDNCrossBrowserTesting]。  通过在不同的浏览器和环境中进行[测试][MicrosoftDeveloperEdgeToolsRemote]，确保你的 PWA 正常工作。  在 Windows 10 上，确保在 Microsoft Edge 浏览器中以及在完整的 PWA 体验中同时测试你的应用：作为已安装的独立 Windows 10 应用 \ （由 EdgeHTML 引擎 \ 提供支持）。  
  
*   [X][响应式设计][WikiResponsiveWebDesign]。  使用具有 CSS[网格][MDNCssGridLayout]和/或[flexbox][MDNCssFlexibleBoxLayout]、[媒体查询][MDNMediaQueries]和 [响应式图像[MDNResponsiveImages]的流畅布局和灵活的图像，以将你的 UX 调整到你的用户设备。  使用浏览器中的设备[仿真工具][DevToolsGuide|::ref1::|]进行本地测试，或设置[远程调试会话][DevToolsProtocolClientsEdgeDevToolsPreview]以在目标设备上直接测试。  在 Windows 10 上，PWAs \ （EdgeHTML \）还可以针对桌面、手机和平板电脑之外[的外形][WindowsUWPDesignDevicesIndex]规格进行定制，包括[： Xbox 和电视][WindowsUWPDesignDevicesDesigningTv]、 [Surface Hub][MicrosoftDeveloperWindowsSurfaceHub]和[Windows Mixed Reality][MicrosoftDeveloperWindowsMixedReality]设备。  
  
*   [X][深层链接][WikiDeepLinking]。  将网站的每个页面路由到唯一的 URL，以便现有用户可以通过社交媒体共享帮助您更多的受众参与。  

*   [X][最佳做法][Webhint]。  使用[webhint][Webhint] linter 之类的代码质量工具来优化应用的效率、可靠性、安全性和辅助功能。  

若要将渐进式 Web 应用提交到[Microsoft Store][MicrosoftDeveloperStore]，您必须具有：  

*   [X] [Microsoft 开发者帐户][WindowsUWPPublishDeveloperAccount]  
*   [X] 已完成[发布 Windows 应用的步骤][WindowsUWPPublishIndex]  

在未来的几个月内，web 会议[特定条件][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]的现有 PWAs 将由必应搜索引擎自动索引为 Microsoft Store \ （在这里，开发人员可以为其 Windows 10 受众直接管理它们）。  

有关更多详细信息，请查看[Microsoft Store 中的 PWAs （EdgeHTML）][PwaEdgehtmlMicrosoftStore] 。  

## 当前可用性  

浏览器引擎支持针对多个体系结构组件的渐进 Web 应用调用，最重要的是[获取 API][MDNFetchApi]基础的网络基础结构。  EdgeHTML 引擎中的 PWA 支持在 Windows 10 1809 版本中完成。  对 web 标准的进一步改进，因为该时间不会合并到 EdgeHTML 引擎中，因此请务必运行兼容性测试并使用功能检测，以确保在 EdgeHTML 平台上不支持 PWA 所需的功能。  

对于即将推出的 Microsoft Edge \ （Chromium）版本2020，浏览器平台对这些功能的完全支持，这些功能可在支持 Chromium 浏览器的设备上运行。  

对于 EdgeHTML 和 Windows，此处是基于标准的 PWA 技术的当前状态：  

| 技术 | 用途 | 可用性 | 使用说明 |  
|:--- |:--- |:--- |:--- |  
| [Web 应用程序清单][MDNWebAppManifest] | 向主机操作系统提供应用元数据以支持安装和应用商店提升。  Microsoft Store 中的 PWAs 所需。  | [在开发中][MicrosoftDeveloperEdgePlatformStatusWebApplicationManifest] | 现在，你可以使用[PWA 生成器][|::ref2::|]生成符合 W3C 的 JSON 清单，并将你的应用打包到各种操作系统平台。  对于 Windows，PWA 生成器会将你的 JSON 清单转换为 `.appxmanifest` Windows 10 应用所需的 \ （XML \）格式。  |  
| [获取 API][MDNFetchApi] | 为页面资源提供异步网络 \ （请求，响应 \） |[EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /内部版本 14393 + | [服务工作者 API][MDNServiceWorkerApi]语法基于基于 Fetch 的网络 api。  你还可以更常见地使用[FETCH API][MDNFetchApi]作为一种新式替代方法 `XMLHttpRequest` 。  |  
| [服务工作者 API][MDNServiceWorkerApi] | 提供支持脱机的 web 应用模型/网络代理，其中事件驱动的脚本独立于网页运行  | [EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /内部版本 17133 + | EdgeHTML 16 中发运的实验性支持 \ （落后 `Enable Service Workers` 于标志 \）。  默认情况下，在 EdgeHTML 17 + 版本中打开。  |  
| [缓存 API][MDNCache] | 为网络请求/响应对提供存储机制 | [EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /内部版本 17133 + | 请参阅上面的[服务工作程序 API][MDNServiceWorkerApi]注释。  |  
| [推送 API][MDNPushApi] | 使服务工作人员能够订阅推送通知 |[EdgeHTML17][DevGuideWhatsNewEdgeHtml17] /内部版本 17133 +| 请参阅上面的[服务工作程序 API][MDNServiceWorkerApi]注释。  Windows 10 应用 \ （包括 PWAs \）需要[Windows 推送通知服务 \ （WNS \）][WindowsUWPControlsPatternTilesNotificationsWns]提供推送通知，该服务支持 W3C [Push API][MDNPushApi]。  |  
| [通知 API][MDNNotificationsApi] | 允许服务工作人员在推送消息时向用户显示系统通知 | [EdgeHTML 14 +][DevGuideWhatsNewEdgeHtml14] /内部版本 14393 + | EdgeHTML 中的 Web 通知与 Windows 10[操作中心][MicrosoftSupportWindowsNotificationSettings]完全集成，用户可以在其中管理应用通知和设置[静音时间][MicrosoftSupportWindowsFocusAssist]。  |  
| [后台同步 API][MDNSyncManager] | 提供用于通知服务工作人员的 API，用户已重新联机并安排定期事件以将本地数据与服务器同步 | [在开发中][MicrosoftDeveloperEdgePlatformStatusBackgroundSync] | 现在，你可以使用本机[WinRT BACKGROUNDTASK API][WindowsUWPLaunchResumeBackgroundTasks]在作为 Windows 10 应用运行时实现 PWA 的后台任务。  |  

以下是 Microsoft Store 对 Windows 10 上的 PWAs 支持的当前状态：  

| 应用商店提交方法 | 状态 | 详细信息 |  
|:--- |:--- |:--- |  
| 手动 \ （开发人员已启动 \） | 可用 | 查看[Microsoft Store 中的 PWAs （EdgeHTML）][PwaEdgehtmlMicrosoftStore]以开始使用。  |  
| 自动 \ （自动索引为必应 \） | 即将推出 | 我们[当前正在试验][WindowsBlogsWelcomingPWAsEdgeWindows]PWA 的应用合作伙伴子集的 PWA 加入过程。  在未来的几个月里，Microsoft 在主流 web 上 PWAs 的欢迎。  [通过 Bing 查看自动 PWA 导入][PwaEdgehtmlMicrosoftStoreCriteriaAutomaticSubmission]，了解有关 Microsoft Store 自动生成的 PWA 列表要求的详细信息。  |  

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
