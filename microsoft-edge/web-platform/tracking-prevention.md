---
description: 此页面提供有关 Microsoft Edge (Chromium) 跟踪功能的文档
title: 'Microsoft Edge 中跟踪 (Chromium) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/27/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， 兼容性， Web 平台， 跟踪防护， 跟踪程序， Cookie， 存储， 广告阻止， 跟踪程序阻止， 跟踪保护
ms.openlocfilehash: a767e55a44c4d416b6d40ca12eb49f2c3a722010
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11231146"
---
# Microsoft Edge 中跟踪 (Chromium)   

Microsoft Edge 中的跟踪防护功能通过限制跟踪器访问基于浏览器的存储和网络的能力，防止用户进行联机跟踪。  它专为实现 Microsoft [Edge][MicrosoftEdgeBrowserPrivacyPromise] 浏览器隐私承诺而构建，同时还确保默认情况下不会影响网站兼容性或 Web 经济适用性。  

Microsoft Edge 目前为用户提供三个级别的跟踪防护，这些跟踪防护通过导航到进行选择 `edge://settings/privacy` 。  

![跟踪防护的三个设置][ImageThreeSettingsTrackingPrevention]  

1.  **基本** - 最不严格的跟踪防护级别，专为喜欢个性化广告的用户和不介意在 Web 上跟踪的用户设计。  基本仅保护用户免受恶意跟踪器（如指纹器和加密器）的攻击。  
1.  **平衡 (默认 **) - 默认级别的跟踪防护，专为想要在浏览时在 Web 上看到不太令人关注的广告的用户设计。  平衡旨在阻止来自用户从不参与的网站的跟踪器，同时最大程度地降低 Web 上的兼容性问题的风险。  
1.  **严格** - 最严格的跟踪防护级别，专为能够实现最大隐私的交易网站兼容性的用户设计。  

Microsoft Edge 中的跟踪防护功能由三个主要组件组成，它们协同工作以确定网站中的特定资源是否应该分类为跟踪器并阻止。  组件如下所示：  

1.  **分类** - Microsoft Edge 确定 URL 是否属于跟踪器的方式。  
1.  **强制** - 保护 Microsoft Edge 用户免受分类为跟踪器 URL 的操作。  
1.  **缓解** - 提供的机制可确保用户指定的收藏夹网站仍可运行，同时提供强大的默认保护。  

将对此页面上的每个组件进行浏览和详细介绍。  

## 分类  

Microsoft Edge 中的跟踪防护功能的第一个组件是分类。  若要对联机跟踪器进行分类并将它们分组为类别，Microsoft Edge 使用 [断开连接][|::ref1::|Main] 开放源代码 [跟踪保护列表][GitHubDisconnectMeTrackingProtection]。  列表通过"信任保护列表"组件传递，可查看该组件 `edge://components` 。  下载后，列表存储在磁盘上，您可以使用它们确定是否/如何对特定 URL 进行分类。  

若要确定 MICROSOFT Edge 中的分类系统是否将 URL 视为跟踪程序，将检查一系列主机名，从完全匹配开始，然后继续检查顶级域之外最多四个标签的部分匹配项。  

> **示例**：  
> 
> URL： `https://a.subdomain.of.a.known.tracker.test/some/path`  
> 
> 测试的主机名：  
> 
> *   `a.subdomain.of.a.known.tracker.test`  
> *   `of.a.known.tracker.test`  
> *   `a.known.tracker.test`  
> *   `known.tracker.test`  
> *   `tracker.test`  

如果其中任何主机名与断开连接列表上的主机名匹配，Microsoft Edge 将继续评估强制操作，以防止跟踪用户。 [][|::ref2::|Main] [][GitHubDisconnectMeTrackingProtection]  

## 强制  

为了防止跟踪 Web 上的操作，Microsoft Edge 对分类跟踪程序采取两种强制操作：

*   **限制存储** 访问 - 如果已知跟踪资源尝试访问可能尝试保留有关用户的数据的任何 Web 存储，Microsoft Edge 将阻止该访问。  这包括限制该跟踪器获取或设置 Cookie 以及访问存储 API（如 `IndexedDB` 和 `localStorage` ）的能力。  
*   **阻止资源** 加载 - 如果在网站上加载了已知的跟踪资源，Microsoft Edge 可能会阻止该负载，直到请求到达网络，具体取决于负载的兼容性影响以及用户设置的跟踪防护设置。  阻止的负载可能包括跟踪脚本、像素、iframe 等。  这可以防止任何数据被发送到跟踪域，甚至可能会提高加载次数和页面性能作为副作用。  

用户可以单击地址栏左侧的页面信息飞出图标，以找出特定页面上阻止的跟踪器： 

![页面信息飞出中阻止的跟踪程序][ImageBlockedTrackersPageInfoFlyout]  

应用强制的方式取决于用户选择的跟踪防护级别以及可能应用的缓解。  

## 缓解  

为确保尽可能保持 Web 兼容性，Microsoft Edge 具有三种缓解措施，以帮助平衡特定情况下的强制。  这些是组织[关系缓解、](#org-relationship-mitigation)[组织参与缓解](#org-engagement-mitigation)和[CompatExceptions 列表](#the-compatexceptions-list)。  

在深入分析缓解之前，需要先定义"组织"或"组织"这一概念。  [Disconnect][|::ref3::|Main]还维护一entities.js列表[][GitHubDisconnectMeTrackingProtectionEntitiesJson]，该列表定义由同一父组织/公司拥有的 URL 组。  Microsoft Edge 中的跟踪防护功能在"组织关系"[](#org-relationship-mitigation)缓解和"组织参与[](#org-engagement-mitigation)"缓解中都使用此列表，以最大程度地减少因跟踪影响跨组织请求的预防导致的兼容性问题的发生。  

### 组织关系缓解  

多个热门网站同时维护网站和内容交付网络 \ (CDN\) ，以向这些网站提供静态资源和内容。  为了确保这些类型的方案不受跟踪防护的影响，当站点向同一父组织拥有的其他站点提出第三方请求时，Microsoft Edge 会免除网站跟踪防护 (如列表 \) 上的 Disconnect [entities.js][GitHubDisconnectMeTrackingProtectionEntitiesJson]中的定义。  最好通过示例来说明这一点。  

> **示例：**
> 
> 名为 Org1 的组织拥有域和，如列表上的断开连接entities.js`org1.test` `org1-cdn.test` [定义][GitHubDisconnectMeTrackingProtectionEntitiesJson]。  假设 `org1-cdn.test` 它被分类为跟踪器，并且通常会应用跟踪防护强制。  如果用户访问和网站尝试从中加载资源，Microsoft Edge 不会对请求执行任何强制操作，即使这不是第一方 `https://org1.test` `https://org1-cdn.test` `org1-cdn.test` URL。  但是，如果另一个不是 Org1 组织的一部分的 URL 尝试加载同一资源，则请求将强制执行，因为它不是同一组织的一部分。  
> 
> 即使这可放松对属于同一组织的网站的跟踪防护强制执行，这不太可能带来很高的隐私风险，因为此类组织能够确定您访问过的网站/资源以及使用内部后端数据。 `https://org1.test` `https://org1-cdn.test`  

### 组织参与缓解  

创建组织参与缓解是为了确保用户充分参与的组织所拥有的网站继续按预期在 Web 中工作，从而最大限度地降低通过跟踪防护引入的兼容性风险。  每当用户与给定[][ChromiumDesignDocsSiteEngagement]网站建立持续关系 \ (当前由网站参与评分为 4.1 或更高\) 定义时，它就会利用网站参与来轻松实施。  示例再次说明了这一点：

> **示例：**
> 
> 名为 Social Org 的组织拥有域 `social.example` 和 `social-videos.example` 。
> 
> 如果用户已与 Social Org 拥有的任何域建立网站参与度分数 4.1 或更高，则认为他们与 Social Org 有关系。
> 
> 如果另一个网站包含第三方内容 \ (则假设来自 Social Org 拥有的任何域的嵌入视频来自 `https://content-embedder.example` \) ，这些域通常受跟踪防护强制执行的限制，只要用户具有 Social Org 拥有域的网站参与度分数维持在阈值之上，该网站就无需跟踪防护强制。 `social-videos.example`
> 
> 如果网站不属于组织，用户必须直接使用网站参与度分数 4.1 或更高，然后才能轻松使用跟踪防护施加的任何存储访问/资源负载块。

目前仅在平衡模式下应用组织参与缓解，以便 Microsoft Edge 为已选择"严格"的用户提供可能的最高保护。

### CompatExceptions 列表  

根据 Microsoft 最近收到的用户反馈，Microsoft Edge 维护一个小型站点列表 \ (其中大多数站点位于断开连接内容类别\) 尽管已执行上述两项缓解措施，但由于跟踪防护而中断。 此列表上的网站无需跟踪防护实施。  可以在磁盘上找到以下描述 [的位置](#determining-whetherhow-a-particular-url-is-classified) 的列表。  用户可以使用中的"阻止"选项 **覆盖其** 上的条目 `edge://settings/content/cookies` 。

为了避免继续维护此列表，Microsoft 目前正在使用 Chromium 代码库中的存储访问[API。][GitHubMsExplainersStorageAccessApi]  存储访问 [API][GitHubMsExplainersStorageAccessApi] 为网站开发人员提供了直接从用户请求存储访问权限的方法，为用户提供了有关其隐私设置如何影响其浏览体验的透明度，并给予网站开发人员控件快速直观地取消阻止。

实现存储访问[API][GitHubMsExplainersStorageAccessApi]后，Microsoft 将弃用 CompatExceptions 列表并联系受影响的站点，以使它们了解问题，并请求他们使用存储[访问 API。][GitHubMsExplainersStorageAccessApi]  

## 当前跟踪防护行为  

下表显示了应用于 Microsoft Edge 中每个分类跟踪器类别的强制操作和缓解。  

*   顶部是断开连接跟踪保护列表类别定义的跟踪 [程序类别][GitHubDisconnectTrackingProtectionCategories]。  
*   左侧是 Microsoft Edge \ (Basic、Balanced 和 Strict\) 中的三个级别的跟踪) 。  
*   该 `S` 字母指示阻止存储访问。  
*   该字母指示存储访问和资源负载 `B` \ (如网络请求\) 被阻止。  
*   连字符 \ (\) 表示未对存储访问或资源负载 `-` 应用块。  

| | 放大 | 分析 | 内容 | 加密 | 指纹 | 社交 | Other | 同一组织缓解 | 组织参与缓解 |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **基本** | - | - | - | B | B | - | - | 启用 | 不适用 |  
| **平衡** | S | - | S | B | B | S | S | 已启用 | 已启用 |  
| **“严格”** | B | B | S | B | B | B | B | 已启用 | 禁用 |  

> [!NOTE]
> 组织参与缓解不适用于加密或指纹类别。  

> [!TIP]
> 严格模式会阻止比平衡更多的资源负载。  阻止更多资源负载可能会导致出现严格模式，以阻止比 Balanced 更少的跟踪请求，因为从不加载提出请求的跟踪程序。  

> [!NOTE]
> 当前跟踪防护行为中的[](#current-tracking-prevention-behavior)指纹列是指除其他列表外，位于指纹列表上的跟踪器。  仅出现在指纹列表上的跟踪器被视为非恶意指纹，并且不会被阻止。

### InPrivate 行为  

在 Microsoft Edge 79 中，默认行为是在 InPrivate 中应用严格模式保护。  在 Microsoft Edge 80 中，此行为已替换为允许用户决定是应用严格模式保护还是保留其常规设置（在浏览 `edge://settings/privacy` InPrivate 时）的开关。  

## 确定是否/如何对特定 URL 进行分类  

确定是否将特定 URL 分类为已知跟踪程序的最简单方法是执行以下步骤。  

1.  打开 DevTools 并导航到控制台选项卡。  
1.  重新加载页面。  
    1.  你可能希望首先清除 **Cookie** 和其他网站数据，以重置网站参与度分数并确保完全干净。  
1.  查找读取的任何邮件 `Tracking Prevention blocked access to storage for <URL>` 。  
    1.  您可以展开消息以查看被阻止的单个 URL。  
1.  如果需要确定特定被阻止网站属于哪个类别，最简单的方法是在列表上的断开连接services.js[搜索][GitHubDisconnectTrackingProtectionCategories]。  条目按字母顺序排序，因此滚动到网站条目块的顶部使您能够查找特定网站的特定类别。  

> [!TIP]
> 如果需要访问存储在磁盘上的跟踪防护列表，可以在两个位置之一找到每个跟踪防护列表。  
>
> **基于组件的更新** - 从"信任保护列表"组件下载的列表  
>
> 窗口： `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> macOS： `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> **安装目录** - 与 Microsoft Edge 安装程序捆绑的列表。  如果选择了不同的安装目录，则具体路径可能不同。  
>
> 窗口： `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> macOS： `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## 常见问题  

以下部分包含有关 Microsoft Edge 中跟踪防护功能常见问题的解答。  

**是否有一种方法可以阻止或允许特定跟踪器进行调试？**  

目前，Microsoft Edge 仅公开了一个选项，用于禁止跟踪防护强制功能在指定的站点上运行。  可通过页面信息飞出或通过页面访问 `edge://settings/privacy/trackingPreventionExceptions` 此选项。  

也就是说，页面上的"**** 阻止"**** 和"允许"选项可用于允许或拒绝特定域访问存储，如 Cookie 和其他 `edge://settings/content/cookies` 浏览器存储机制。  这适用于调试因跟踪阻止访问特定网站的存储的防护实施导致的站点问题。  

<!-- image links -->  

[ImageThreeSettingsTrackingPrevention]: ./media/tracking-prevention-settings.png  
[ImageBlockedTrackersPageInfoFlyout]: ./media/page-info-flyout.png  

<!-- links -->  

[MicrosoftEdgeBrowserPrivacyPromise]: https://microsoftedgewelcome.microsoft.com/privacy "隐私 - Microsoft Edge"  

[ChromiumDesignDocsSiteEngagement]: https://www.chromium.org/developers/design-documents/site-engagement "网站参与 - Chromium 项目"  

[DisconnectMain]: https://disconnect.me "断开连接"  

[GitHubDisconnectMeTrackingProtection]: https://github.com/disconnectme/disconnect-tracking-protection "disconnectme/disconnect-tracking-protection |Github"  
[GitHubDisconnectTrackingProtectionCategories]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/services.json "services.js- disconnectme/disconnect-tracking-protection |Github"  
[GitHubDisconnectMeTrackingProtectionEntitiesJson]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/entities.json "entities.js- disconnectme/disconnect-tracking-protection |Github"  

[GitHubMsExplainersStorageAccessApi]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/StorageAccessAPI/explainer.md "存储访问 API 说明程序 - MSEdgeExplainers/StorageAccessAPI |GitHub"
