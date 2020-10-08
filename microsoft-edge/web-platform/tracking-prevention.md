---
description: 此页面提供有关 Microsoft Edge (Chromium) 跟踪防护功能的文档
title: " (Chromium) 的 Microsoft Edge 中的跟踪防护"
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，兼容性，web 平台，跟踪防护，跟踪器，cookie，存储，广告阻止，跟踪器阻止，跟踪保护
ms.openlocfilehash: 2648f05c112a00e66eae85ed44adf22632a0524a
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564602"
---
#  (Chromium) 的 Microsoft Edge 中的跟踪防护  

Microsoft Edge 中的跟踪防护功能通过限制跟踪器访问基于浏览器的存储和网络的能力来保护联机跟踪用户。  它旨在保持 Microsoft Edge [浏览器的隐私承诺][MicrosoftEdgeBrowserPrivacyPromise] ，同时确保默认情况下不会对网站兼容性或 web 的经济生存能力产生任何影响。  

Microsoft Edge 当前向用户提供三个级别的跟踪防护，这些级别通过导航到来选择 `edge://settings/privacy` 。  

![跟踪防护的三个设置][ImageThreeSettingsTrackingPrevention]  

1.  **基本** -跟踪保护的最低限制级别，适用于欣赏个性化广告的用户和不介意在 web 上跟踪的用户。  基本仅针对恶意跟踪用户（如 fingerprinters 和 cryptominers）保护用户。  
1.  已**平衡 (默认) ** -为希望在浏览时查看更少 creepy 广告的用户设计的默认跟踪防护级别。  平衡旨在阻止来自用户永不参与的网站的跟踪程序，同时将 web 上的兼容性问题的风险降到最低。  
1.  **严格** -跟踪防护的最高限制级别，适用于不确定最高隐私的网站兼容性的用户。  

Microsoft Edge 中的跟踪防护功能由三个主要组件组成，这些组件协同工作以确定网站中的特定资源是否应归类为跟踪者和已阻止。  这些组件如下所示：  

1.  **分类** -Microsoft EDGE 确定 URL 是否属于跟踪器的方式。  
1.  **强制执行** -保护 Microsoft Edge 用户免受分类为跟踪程序的 url 的操作。  
1.  **缓解** -为确保用户指定的常用网站而提供的机制在提供强默认保护时仍然有效。  

本页面详细讨论并详细介绍每个组件。  

## 分类  

Microsoft Edge 中的跟踪防护功能的第一个组件是分类。  若要对联机跟踪跟踪人员进行分类并将其分组为类别，Microsoft Edge 使用 [断开][|::ref1::|Main] 的打开源 [跟踪保护列表][GitHubDisconnectMeTrackingProtection]。  这些列表通过可查看的 "信任保护列表" 组件提供 `edge://components` 。  下载列表后，这些列表将存储在磁盘上，您可以使用它们来确定是否对特定的 URL 进行分类。  

若要确定某个 URL 是否由 Microsoft Edge 中的分类系统视为跟踪器，请检查一系列主机名，从完全匹配项开始，然后继续检查部分匹配项，以查找最多四个标签（超过顶级域）。  

> **示例**：  
> 
> URL `https://a.subdomain.of.a.known.tracker.test/some/path`  
> 
> 已测试主机名：  
> 
> *   `a.subdomain.of.a.known.tracker.test`  
> *   `of.a.known.tracker.test`  
> *   `a.known.tracker.test`  
> *   `known.tracker.test`  
> *   `tracker.test`  

如果这些主机名称中的任何一个与[断开连接][|::ref2::|Main][列表][GitHubDisconnectMeTrackingProtection]上的主机名相匹配，Microsoft Edge 将继续评估强制操作以防止跟踪用户。  

## 强制  

为了对 web 上的跟踪操作提供保护，Microsoft Edge 针对分类跟踪跟踪执行两个强制操作：

*   **限制存储访问** -如果已知的跟踪资源尝试访问任何可能尝试保留有关用户的数据的 web 存储，则访问的 Microsoft Edge 块。  这包括限制该跟踪器获取或设置 cookie 以及访问存储 Api （如和）的能力 `IndexedDB` `localStorage` 。  
*   **阻止资源加载** -如果在网站上加载了已知的跟踪资源，Microsoft Edge 可能会在请求到达网络之前阻止该加载，具体取决于负载的兼容性影响和用户设置的跟踪保护设置。  已阻止的加载可能包括跟踪脚本、像素、iframe 等。  这可以防止任何可能发送到跟踪域的数据，甚至还可以提高加载时间和页面性能，作为副作用。  

用户可以单击地址栏左侧的 "页面信息" 飞出图标，了解特定页面上被阻止的跟踪器： 

![页面信息浮出控件中的被阻止的跟踪跟踪][ImageBlockedTrackersPageInfoFlyout]  

Enforcements 的应用方式取决于用户选择的跟踪保护级别和可能适用的缓解。  

## 缓解  

为了确保尽可能多地保留 web 兼容性，Microsoft Edge 有三个缓解措施，可帮助在特定情况下平衡 enforcements。  这些是组织间的 [关系缓解](#org-relationship-mitigation)、 [组织参与缓解](#org-engagement-mitigation)和 [CompatExceptions 列表](#the-compatexceptions-list)。  

在深入研究缓解之前，有必要定义简短的 "组织" 或 "组织" 概念。  [断开连接][|::ref3::|Main] 还会保留一个名为 [entities.js][GitHubDisconnectMeTrackingProtectionEntitiesJson] 的列表，该列表定义由同一父组织/公司拥有的 url 组。  Microsoft Edge 中的跟踪防护功能在 [组织关系缓解](#org-relationship-mitigation) 和 [组织参与缓解](#org-engagement-mitigation) 中使用此列表，最大程度地减少由于跟踪阻止影响跨组织请求而导致的兼容性问题。  

### 组织间的关系缓解  

有几个常用网站既维护网站和内容交付网络 \ (Cdn \ ) 将静态资源和内容提供给这些网站。  若要确保这些类型的方案不受 "跟踪防护" 的影响，Microsoft Edge exempts 网站在将第三方请求发送到由列表 \ ) 上的 " [断开连接" entities.js][GitHubDisconnectMeTrackingProtectionEntitiesJson]中定义的其他网站时，从 ("跟踪防护" 中创建网站。  这是一个示例的最佳说明。  

> **示例：**
> 
> 名为 Org1 的组织拥有域 `org1.test` 和 " `org1-cdn.test` [断开连接 entities.js" 列表][GitHubDisconnectMeTrackingProtectionEntitiesJson]中定义的域。  假设 `org1-cdn.test` 已归类为跟踪器，并且通常会对其应用跟踪防护 enforcements。  如果用户访问 `https://org1.test` 和网站尝试加载资源 `https://org1-cdn.test` ，Microsoft Edge 不会对所做的请求执行任何强制操作， `org1-cdn.test` 即使它不是第一方 URL 也是如此。  但是，如果另一个不属于 Org1 组织的 URL 尝试加载同一资源，则该请求将受到 enforcements，因为它不是同一组织的一部分。  
> 
> 即使此 relaxes 跟踪保护 enforcements 对于属于同一组织的网站，这种情况不太可能带来大量隐私风险，因为这样的组织能够确定您访问的网站/资源以及 `https://org1.test` `https://org1-cdn.test` 使用内部后端数据。  

### 组织参与缓解  

已创建组织参与缓解，以通过确保由用户充分参与的组织所拥有的兼容性风险来最大程度地减少跟踪保护带来的兼容性风险，并在 web 上继续按预期工作。  当用户建立了当前的关系 \ (当前由4.1 或更高版本的 ) 与给定的网站进行定义时，它利用 [网站预订][ChromiumDesignDocsSiteEngagement] 来放松 enforcements。  这种情况下，最好的例子如下所示：

> **示例：**
> 
> 名为 "社交组织" 的组织拥有域 `social.example` 和 `social-videos.example` 。
> 
> 如果用户已建立了4.1 或更高的网站参与分数或更高的与社交组织拥有的任何一个域的关系，则认为用户与社交组织有关系。
> 
> 如果另一个网站 `https://content-embedder.example` 包含第三方内容 \ (从 `social-videos.example` \ ) 中的任何域（通常由 enforcements 的 "跟踪防护" 限制）发出的嵌入视频，则只要用户的网站参与分数的 enforcements 超过了阈值，该网站就会免于跟踪保护。
> 
> 如果网站不属于某个组织，则用户必须在 "跟踪防护" 所强加的任何存储访问/资源负载块之前直接建立4.1 或更高的网站参与分数。

组织参与缓解目前仅在平衡模式下应用，因此 Microsoft Edge 为选择严格的用户提供了最高可能的保护。

### CompatExceptions 列表  

根据 Microsoft 已收到的最新用户反馈，Microsoft Edge 维护了一个较小的网站列表，其中大多数 (网站是 "断开连接内容" 类别的 "断开连接内容" ) 类别，因为在有上述两个缓解措施的情况下，由于进行了这两个缓解。 此列表中的网站不受跟踪保护 enforcements。  可以在磁盘上的如下所述 [位置](#determining-whetherhow-a-particular-url-is-classified) 找到该列表。  用户可以使用中的 " **阻止** " 选项替代其上的条目 `edge://settings/content/cookies` 。

为避免保留此列表向前移动，Microsoft 当前正在 Chromium 基本代码中处理 [存储访问 API][GitHubMsExplainersStorageAccessApi] 。  [存储访问 API][GitHubMsExplainersStorageAccessApi]为网站开发人员提供了一种直接向用户请求存储访问权限的方法，让用户可以更轻松地了解其隐私设置对其浏览体验有何影响，以及让网站开发人员控件快速、直观地取消阻止他们的浏览体验。

实现 [存储访问 api][GitHubMsExplainersStorageAccessApi] 后，Microsoft 将弃用 CompatExceptions 列表并访问受影响的网站，以使他们注意这些问题，并请求他们使用 [存储访问 API][GitHubMsExplainersStorageAccessApi] 前进。  

## 当前跟踪防护行为  

下表显示了应用于 Microsoft Edge 中的每个分类跟踪器类别的强制操作和缓解。  

*   顶部是由 " [断开连接跟踪保护列表类别][GitHubDisconnectTrackingProtectionCategories]" 定义的跟踪器类别。  
*   在 Microsoft Edge \ (基本、已平衡和严格 \ ) 中，左侧有三个级别的跟踪保护。  
*   字母 `S` 表示存储访问被阻止。  
*   字母 `B` 表示存储访问和资源加载 \ (（如网络请求 \ ) ）被阻止。  
*   连字符 \ (`-` \ ) 表示没有对存储访问或资源负载应用任何块。  

| | Advertizing | 分析 | 内容 | Cryptomining | 识别 | 社交 | Other | 相同的组织缓解措施 | 组织参与缓解 |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **基本** | - | - | - | B | B | - | - | 启用 | 不适用 |  
| **平衡** | S | - | S | B | B | S | S | 已启用 | 已启用 |  
| **“严格”** | B | B | S | B | B | B | B | 已启用 | 禁用 |  

> [!NOTE]
> 组织参与缓解不适用于 Cryptomining 或指纹类别。  

> [!TIP]
> 严格模式会阻止比平衡更多的资源负载。  阻止更多资源加载可能会导致严格模式的阻止跟踪请求数比已平衡的跟踪请求的阻止程度少，因为从不加载跟踪请求的跟踪请求。  

> [!NOTE]
> [当前跟踪防护行为](#current-tracking-prevention-behavior)中的指纹栏指的是指纹列表中除另一个列表之外的跟踪程序。  仅在指纹列表上显示的跟踪程序被视为非恶意 fingerprinters，并且不会被阻止。

### InPrivate 行为  

在 Microsoft Edge 79 中，默认行为是在 InPrivate 中应用严格模式保护。  在 Microsoft Edge 80 中，此行为被替换为一个开关， `edge://settings/privacy` 用户可在浏览 InPrivate 时决定是应用严格模式保护还是保留常规设置。  

## 确定特定 URL 是否已分类  

确定特定 URL 是否属于已知跟踪器的最简单方法是执行以下步骤。  

1.  打开 DevTools 并导航到 "控制台" 选项卡。  
1.  重新加载页面。  
    1.  您可能希望首先清除 **cookie 和其他网站数据** 以重置网站预订分数并确保完全干净的平板。  
1.  查找任何阅读的邮件 `Tracking Prevention blocked access to storage for <URL>` 。  
    1.  您可以展开邮件以查看被阻止的单个 Url。  
1.  如果需要确定特定的被阻止网站所在的类别，最简单的方法是在 " [断开连接 services.js" 列表][GitHubDisconnectTrackingProtectionCategories]中搜索。  这些条目按字母顺序排列，因此滚动到网站条目块的顶部可让你找到特定网站的特定类别。  

> [!TIP]
> 如果需要访问存储在磁盘上的跟踪保护列表，可以在两个位置之一中找到每个列表。  
>
> **基于组件的更新** -从 "信任保护列表" 组件下载的列表  
>
> 窗口： `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> MacOS `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> **安装目录** -与 Microsoft Edge 安装程序捆绑的列表。  如果你选择了其他安装目录，你的确切路径可能会有所不同。  
>
> 窗口： `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> MacOS `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## 常见问题  

以下部分包含有关 Microsoft Edge 中的跟踪保护功能的常见问题的解答。  

**是否有办法阻止或允许特定的跟踪程序用于调试用途？**  

目前，Microsoft Edge 仅公开一个选项，可禁用在指定网站上运行的跟踪保护 enforcements。  通过页面信息弹出窗口或页面访问此选项 `edge://settings/privacy/trackingPreventionExceptions` 。  

也就是说，页面上的 " **阻止** " 和 " **允许** " 选项可 `edge://settings/content/cookies` 用于允许或拒绝特定域访问存储，如 cookie 和其他浏览器存储机制。  这对于通过阻止 enforcements 阻止访问特定网站的存储导致的网站问题非常有用。  

<!-- image links -->  

[ImageThreeSettingsTrackingPrevention]: ../media/web-platform/tracking-prevention/tracking-prevention-settings.png  
[ImageBlockedTrackersPageInfoFlyout]: ../media/web-platform/tracking-prevention/page-info-flyout.png  

<!-- links -->  

[MicrosoftEdgeBrowserPrivacyPromise]: https://microsoftedgewelcome.microsoft.com/privacy "隐私-Microsoft Edge"  

[ChromiumDesignDocsSiteEngagement]: https://www.chromium.org/developers/design-documents/site-engagement "网站预订-Chromium 项目"  

[DisconnectMain]: https://disconnect.me "中断"  

[GitHubDisconnectMeTrackingProtection]: https://github.com/disconnectme/disconnect-tracking-protection "disconnectme/断开连接-跟踪-保护 |Github"  
[GitHubDisconnectTrackingProtectionCategories]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/services.json "services.jsdisconnectme/断开连接-跟踪-保护 |Github"  
[GitHubDisconnectMeTrackingProtectionEntitiesJson]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/entities.json "entities.jsdisconnectme/断开连接-跟踪-保护 |Github"  

[GitHubMsExplainersStorageAccessApi]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/StorageAccessAPI/explainer.md "存储访问 API Explainer-MSEdgeExplainers/StorageAccessAPI |GitHub"
