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
# <span data-ttu-id="40ad0-104">Microsoft Edge 中跟踪 (Chromium) </span><span class="sxs-lookup"><span data-stu-id="40ad0-104">Tracking Prevention in Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="40ad0-105">Microsoft Edge 中的跟踪防护功能通过限制跟踪器访问基于浏览器的存储和网络的能力，防止用户进行联机跟踪。</span><span class="sxs-lookup"><span data-stu-id="40ad0-105">The tracking prevention feature in Microsoft Edge protects users from online tracking by restricting the ability of trackers to access browser-based storage as well as the network.</span></span>  <span data-ttu-id="40ad0-106">它专为实现 Microsoft [Edge][MicrosoftEdgeBrowserPrivacyPromise] 浏览器隐私承诺而构建，同时还确保默认情况下不会影响网站兼容性或 Web 经济适用性。</span><span class="sxs-lookup"><span data-stu-id="40ad0-106">It is built to uphold the Microsoft Edge [browser privacy promise][MicrosoftEdgeBrowserPrivacyPromise] while also ensuring that there is no impact by default to website compatibility or the economic viability of the web.</span></span>  

<span data-ttu-id="40ad0-107">Microsoft Edge 目前为用户提供三个级别的跟踪防护，这些跟踪防护通过导航到进行选择 `edge://settings/privacy` 。</span><span class="sxs-lookup"><span data-stu-id="40ad0-107">Microsoft Edge currently offers users three levels of tracking prevention, which are selected by navigating to `edge://settings/privacy`.</span></span>  

![跟踪防护的三个设置][ImageThreeSettingsTrackingPrevention]  

1.  <span data-ttu-id="40ad0-109">**基本** - 最不严格的跟踪防护级别，专为喜欢个性化广告的用户和不介意在 Web 上跟踪的用户设计。</span><span class="sxs-lookup"><span data-stu-id="40ad0-109">**Basic** - The least restrictive level of tracking prevention that is designed for users who enjoy personalized advertisements and who do not mind being tracked on the web.</span></span>  <span data-ttu-id="40ad0-110">基本仅保护用户免受恶意跟踪器（如指纹器和加密器）的攻击。</span><span class="sxs-lookup"><span data-stu-id="40ad0-110">Basic only protects users against malicious trackers such as fingerprinters and cryptominers.</span></span>  
1.  <span data-ttu-id="40ad0-111">\*\*平衡 (默认 \*\*) - 默认级别的跟踪防护，专为想要在浏览时在 Web 上看到不太令人关注的广告的用户设计。</span><span class="sxs-lookup"><span data-stu-id="40ad0-111">**Balanced (Default)** - The default level of tracking prevention that is designed for users who want to see less creepy advertisements that follow them around the web while they browse.</span></span>  <span data-ttu-id="40ad0-112">平衡旨在阻止来自用户从不参与的网站的跟踪器，同时最大程度地降低 Web 上的兼容性问题的风险。</span><span class="sxs-lookup"><span data-stu-id="40ad0-112">Balanced aims to block trackers from sites that users never engage with while minimizing the risk of compatibility issues on the web.</span></span>  
1.  <span data-ttu-id="40ad0-113">**严格** - 最严格的跟踪防护级别，专为能够实现最大隐私的交易网站兼容性的用户设计。</span><span class="sxs-lookup"><span data-stu-id="40ad0-113">**Strict** - The most restrictive level of tracking prevention that is designed for users who are okay trading website compatibility for maximum privacy.</span></span>  

<span data-ttu-id="40ad0-114">Microsoft Edge 中的跟踪防护功能由三个主要组件组成，它们协同工作以确定网站中的特定资源是否应该分类为跟踪器并阻止。</span><span class="sxs-lookup"><span data-stu-id="40ad0-114">The tracking prevention feature in Microsoft Edge is made up of three main components that work together to determine whether a specific resource from a website should be classified as a tracker and blocked.</span></span>  <span data-ttu-id="40ad0-115">组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="40ad0-115">The components are as follows:</span></span>  

1.  <span data-ttu-id="40ad0-116">**分类** - Microsoft Edge 确定 URL 是否属于跟踪器的方式。</span><span class="sxs-lookup"><span data-stu-id="40ad0-116">**Classification** - The way Microsoft Edge determines whether a URL belongs to a tracker.</span></span>  
1.  <span data-ttu-id="40ad0-117">**强制** - 保护 Microsoft Edge 用户免受分类为跟踪器 URL 的操作。</span><span class="sxs-lookup"><span data-stu-id="40ad0-117">**Enforcement** - The actions taken to protect Microsoft Edge users from URLs classified as trackers.</span></span>  
1.  <span data-ttu-id="40ad0-118">**缓解** - 提供的机制可确保用户指定的收藏夹网站仍可运行，同时提供强大的默认保护。</span><span class="sxs-lookup"><span data-stu-id="40ad0-118">**Mitigations** - The mechanisms provided to ensure user-specified favorite sites still work, while offering strong default protection.</span></span>  

<span data-ttu-id="40ad0-119">将对此页面上的每个组件进行浏览和详细介绍。</span><span class="sxs-lookup"><span data-stu-id="40ad0-119">Each of the components are explored and explained in detail on this page.</span></span>  

## <span data-ttu-id="40ad0-120">分类</span><span class="sxs-lookup"><span data-stu-id="40ad0-120">Classification</span></span>  

<span data-ttu-id="40ad0-121">Microsoft Edge 中的跟踪防护功能的第一个组件是分类。</span><span class="sxs-lookup"><span data-stu-id="40ad0-121">The first component of the tracking prevention feature in Microsoft Edge is classification.</span></span>  <span data-ttu-id="40ad0-122">若要对联机跟踪器进行分类并将它们分组为类别，Microsoft Edge 使用 [断开连接][|::ref1::|Main] 开放源代码 [跟踪保护列表][GitHubDisconnectMeTrackingProtection]。</span><span class="sxs-lookup"><span data-stu-id="40ad0-122">To classify online trackers and group them into categories, Microsoft Edge uses the [Disconnect][|::ref1::|Main] open source [tracking protection lists][GitHubDisconnectMeTrackingProtection].</span></span>  <span data-ttu-id="40ad0-123">列表通过"信任保护列表"组件传递，可查看该组件 `edge://components` 。</span><span class="sxs-lookup"><span data-stu-id="40ad0-123">The lists are delivered via the "Trust Protection Lists" component, which is viewable at `edge://components`.</span></span>  <span data-ttu-id="40ad0-124">下载后，列表存储在磁盘上，您可以使用它们确定是否/如何对特定 URL 进行分类。</span><span class="sxs-lookup"><span data-stu-id="40ad0-124">After being downloaded, the lists are stored on disk where you may use them to determine whether/how a particular URL is classified.</span></span>  

<span data-ttu-id="40ad0-125">若要确定 MICROSOFT Edge 中的分类系统是否将 URL 视为跟踪程序，将检查一系列主机名，从完全匹配开始，然后继续检查顶级域之外最多四个标签的部分匹配项。</span><span class="sxs-lookup"><span data-stu-id="40ad0-125">To determine if a URL is considered a tracker by the classification system in Microsoft Edge, a series of host names are checked, starting with an exact match and then proceeding to check for partial matches for up to four labels beyond the top-level domain.</span></span>  

> <span data-ttu-id="40ad0-126">**示例**：</span><span class="sxs-lookup"><span data-stu-id="40ad0-126">**Example**:</span></span>  
> 
> <span data-ttu-id="40ad0-127">URL：</span><span class="sxs-lookup"><span data-stu-id="40ad0-127">URL:</span></span> `https://a.subdomain.of.a.known.tracker.test/some/path`  
> 
> <span data-ttu-id="40ad0-128">测试的主机名：</span><span class="sxs-lookup"><span data-stu-id="40ad0-128">Tested host names:</span></span>  
> 
> *   `a.subdomain.of.a.known.tracker.test`  
> *   `of.a.known.tracker.test`  
> *   `a.known.tracker.test`  
> *   `known.tracker.test`  
> *   `tracker.test`  

<span data-ttu-id="40ad0-129">如果其中任何主机名与断开连接列表上的主机名匹配，Microsoft Edge 将继续评估强制操作，以防止跟踪用户。 [][|::ref2::|Main] [][GitHubDisconnectMeTrackingProtection]</span><span class="sxs-lookup"><span data-stu-id="40ad0-129">If any of those host names match with a host name on the [Disconnect][|::ref2::|Main] [lists][GitHubDisconnectMeTrackingProtection], Microsoft Edge proceeds with evaluating enforcement actions to prevent users from being tracked.</span></span>  

## <span data-ttu-id="40ad0-130">强制</span><span class="sxs-lookup"><span data-stu-id="40ad0-130">Enforcement</span></span>  

<span data-ttu-id="40ad0-131">为了防止跟踪 Web 上的操作，Microsoft Edge 对分类跟踪程序采取两种强制操作：</span><span class="sxs-lookup"><span data-stu-id="40ad0-131">To provide protection from tracking actions on the web, Microsoft Edge takes two enforcement actions against classified trackers:</span></span>

*   <span data-ttu-id="40ad0-132">**限制存储** 访问 - 如果已知跟踪资源尝试访问可能尝试保留有关用户的数据的任何 Web 存储，Microsoft Edge 将阻止该访问。</span><span class="sxs-lookup"><span data-stu-id="40ad0-132">**Restrict storage access** - If a known tracking resource tries to access any web storage where it may try to persist data about the user, Microsoft Edge blocks that access.</span></span>  <span data-ttu-id="40ad0-133">这包括限制该跟踪器获取或设置 Cookie 以及访问存储 API（如 `IndexedDB` 和 `localStorage` ）的能力。</span><span class="sxs-lookup"><span data-stu-id="40ad0-133">This includes restricting the ability for that tracker to get or set cookies as well as access storage APIs such as `IndexedDB` and `localStorage`.</span></span>  
*   <span data-ttu-id="40ad0-134">**阻止资源** 加载 - 如果在网站上加载了已知的跟踪资源，Microsoft Edge 可能会阻止该负载，直到请求到达网络，具体取决于负载的兼容性影响以及用户设置的跟踪防护设置。</span><span class="sxs-lookup"><span data-stu-id="40ad0-134">**Block resource loads** - If a known tracking resource is being loaded on a website, Microsoft Edge may block that load before the request reaches the network depending on compatibility impact of the load and the tracking prevention setting a user has set.</span></span>  <span data-ttu-id="40ad0-135">阻止的负载可能包括跟踪脚本、像素、iframe 等。</span><span class="sxs-lookup"><span data-stu-id="40ad0-135">Blocked loads may include tracking scripts, pixels, iframes, and more.</span></span>  <span data-ttu-id="40ad0-136">这可以防止任何数据被发送到跟踪域，甚至可能会提高加载次数和页面性能作为副作用。</span><span class="sxs-lookup"><span data-stu-id="40ad0-136">This prevents any data potentially being sent to the tracking domain and may even improve load times and page performance as a side effect.</span></span>  

<span data-ttu-id="40ad0-137">用户可以单击地址栏左侧的页面信息飞出图标，以找出特定页面上阻止的跟踪器：</span><span class="sxs-lookup"><span data-stu-id="40ad0-137">A user may click the page info flyout icon on the left side of the address bar to find out which trackers were blocked on a specific page:</span></span> 

![页面信息飞出中阻止的跟踪程序][ImageBlockedTrackersPageInfoFlyout]  

<span data-ttu-id="40ad0-139">应用强制的方式取决于用户选择的跟踪防护级别以及可能应用的缓解。</span><span class="sxs-lookup"><span data-stu-id="40ad0-139">How the enforcements are applied depends on what level of tracking prevention the user selected and the mitigations that may apply.</span></span>  

## <span data-ttu-id="40ad0-140">缓解</span><span class="sxs-lookup"><span data-stu-id="40ad0-140">Mitigations</span></span>  

<span data-ttu-id="40ad0-141">为确保尽可能保持 Web 兼容性，Microsoft Edge 具有三种缓解措施，以帮助平衡特定情况下的强制。</span><span class="sxs-lookup"><span data-stu-id="40ad0-141">To ensure that web compatibility is preserved as much as possible, Microsoft Edge has three mitigations to help balance enforcements in specific situations.</span></span>  <span data-ttu-id="40ad0-142">这些是组织[关系缓解、](#org-relationship-mitigation)[组织参与缓解](#org-engagement-mitigation)和[CompatExceptions 列表](#the-compatexceptions-list)。</span><span class="sxs-lookup"><span data-stu-id="40ad0-142">These are the [Org Relationship mitigation](#org-relationship-mitigation), the [Org Engagement mitigation](#org-engagement-mitigation), and the [CompatExceptions List](#the-compatexceptions-list).</span></span>  

<span data-ttu-id="40ad0-143">在深入分析缓解之前，需要先定义"组织"或"组织"这一概念。</span><span class="sxs-lookup"><span data-stu-id="40ad0-143">Before diving into the mitigations, it is worth defining the concept of an "Organization" or "Org" for short.</span></span>  <span data-ttu-id="40ad0-144">[Disconnect][|::ref3::|Main]还维护一entities.js列表[][GitHubDisconnectMeTrackingProtectionEntitiesJson]，该列表定义由同一父组织/公司拥有的 URL 组。</span><span class="sxs-lookup"><span data-stu-id="40ad0-144">[Disconnect][|::ref3::|Main] also maintains a list called [entities.json][GitHubDisconnectMeTrackingProtectionEntitiesJson] that defines groups of URLs that are owned by the same parent organization/company.</span></span>  <span data-ttu-id="40ad0-145">Microsoft Edge 中的跟踪防护功能在"组织关系"[](#org-relationship-mitigation)缓解和"组织参与[](#org-engagement-mitigation)"缓解中都使用此列表，以最大程度地减少因跟踪影响跨组织请求的预防导致的兼容性问题的发生。</span><span class="sxs-lookup"><span data-stu-id="40ad0-145">The tracking prevention feature in Microsoft Edge uses this list in both the [Org Relationship mitigation](#org-relationship-mitigation) and the [Org Engagement mitigation](#org-engagement-mitigation) to minimize the occurrence of compatibility issues caused by tracking prevention affecting cross-organizational requests.</span></span>  

### <span data-ttu-id="40ad0-146">组织关系缓解</span><span class="sxs-lookup"><span data-stu-id="40ad0-146">Org Relationship Mitigation</span></span>  

<span data-ttu-id="40ad0-147">多个热门网站同时维护网站和内容交付网络 \ (CDN\) ，以向这些网站提供静态资源和内容。</span><span class="sxs-lookup"><span data-stu-id="40ad0-147">Several popular websites maintain both websites and Content Delivery Networks \(CDNs\) to serve static resources and content to those sites.</span></span>  <span data-ttu-id="40ad0-148">为了确保这些类型的方案不受跟踪防护的影响，当站点向同一父组织拥有的其他站点提出第三方请求时，Microsoft Edge 会免除网站跟踪防护 (如列表 \) 上的 Disconnect [entities.js][GitHubDisconnectMeTrackingProtectionEntitiesJson]中的定义。</span><span class="sxs-lookup"><span data-stu-id="40ad0-148">To ensure that these types of scenarios are not affected by tracking prevention, Microsoft Edge exempts a site from tracking prevention when the site is making third-party requests to other sites owned by the same parent organization \(as defined in the [Disconnect entities.json list][GitHubDisconnectMeTrackingProtectionEntitiesJson]\).</span></span>  <span data-ttu-id="40ad0-149">最好通过示例来说明这一点。</span><span class="sxs-lookup"><span data-stu-id="40ad0-149">This is best illustrated by an example.</span></span>  

> **<span data-ttu-id="40ad0-150">示例：</span><span class="sxs-lookup"><span data-stu-id="40ad0-150">Example:</span></span>**
> 
> <span data-ttu-id="40ad0-151">名为 Org1 的组织拥有域和，如列表上的断开连接entities.js`org1.test` `org1-cdn.test` [定义][GitHubDisconnectMeTrackingProtectionEntitiesJson]。</span><span class="sxs-lookup"><span data-stu-id="40ad0-151">An organization named Org1 owns the domains `org1.test` and `org1-cdn.test`, as defined in the [Disconnect entities.json list][GitHubDisconnectMeTrackingProtectionEntitiesJson].</span></span>  <span data-ttu-id="40ad0-152">假设 `org1-cdn.test` 它被分类为跟踪器，并且通常会应用跟踪防护强制。</span><span class="sxs-lookup"><span data-stu-id="40ad0-152">Imagine that `org1-cdn.test` is classified as a tracker and would normally have tracking prevention enforcements applied to it.</span></span>  <span data-ttu-id="40ad0-153">如果用户访问和网站尝试从中加载资源，Microsoft Edge 不会对请求执行任何强制操作，即使这不是第一方 `https://org1.test` `https://org1-cdn.test` `org1-cdn.test` URL。</span><span class="sxs-lookup"><span data-stu-id="40ad0-153">If a user visits `https://org1.test` and the site tries to load a resource from `https://org1-cdn.test`, Microsoft Edge does not take any enforcement actions against requests made to `org1-cdn.test` even though it is not a first-party URL.</span></span>  <span data-ttu-id="40ad0-154">但是，如果另一个不是 Org1 组织的一部分的 URL 尝试加载同一资源，则请求将强制执行，因为它不是同一组织的一部分。</span><span class="sxs-lookup"><span data-stu-id="40ad0-154">If another URL that is not part of the Org1 organization tries to load that same resource, however, then the request would be subject to enforcements because it is not part of the same organization.</span></span>  
> 
> <span data-ttu-id="40ad0-155">即使这可放松对属于同一组织的网站的跟踪防护强制执行，这不太可能带来很高的隐私风险，因为此类组织能够确定您访问过的网站/资源以及使用内部后端数据。 `https://org1.test` `https://org1-cdn.test`</span><span class="sxs-lookup"><span data-stu-id="40ad0-155">Even though this relaxes tracking prevention enforcements for sites that belong to the same organization, it is unlikely that this introduces a high amount of privacy risk since such organizations are able to determine which sites/resources you have accessed on `https://org1.test` as well `https://org1-cdn.test` using internal back-end data.</span></span>  

### <span data-ttu-id="40ad0-156">组织参与缓解</span><span class="sxs-lookup"><span data-stu-id="40ad0-156">Org Engagement Mitigation</span></span>  

<span data-ttu-id="40ad0-157">创建组织参与缓解是为了确保用户充分参与的组织所拥有的网站继续按预期在 Web 中工作，从而最大限度地降低通过跟踪防护引入的兼容性风险。</span><span class="sxs-lookup"><span data-stu-id="40ad0-157">The org engagement mitigation was created to minimize compatibility risks introduced by tracking prevention by ensuring that sites owned by organizations that users sufficiently engage with continue to work as expected across the web.</span></span>  <span data-ttu-id="40ad0-158">每当用户与给定[][ChromiumDesignDocsSiteEngagement]网站建立持续关系 \ (当前由网站参与评分为 4.1 或更高\) 定义时，它就会利用网站参与来轻松实施。</span><span class="sxs-lookup"><span data-stu-id="40ad0-158">It makes use of [site engagement][ChromiumDesignDocsSiteEngagement] to relax enforcements whenever a user has established an ongoing relationship \(currently defined by a site engagement score of 4.1 or greater\) with a given site.</span></span>  <span data-ttu-id="40ad0-159">示例再次说明了这一点：</span><span class="sxs-lookup"><span data-stu-id="40ad0-159">This again is best illustrated by an example:</span></span>

> **<span data-ttu-id="40ad0-160">示例：</span><span class="sxs-lookup"><span data-stu-id="40ad0-160">Example:</span></span>**
> 
> <span data-ttu-id="40ad0-161">名为 Social Org 的组织拥有域 `social.example` 和 `social-videos.example` 。</span><span class="sxs-lookup"><span data-stu-id="40ad0-161">An organization named Social Org owns the domains `social.example` and `social-videos.example`.</span></span>
> 
> <span data-ttu-id="40ad0-162">如果用户已与 Social Org 拥有的任何域建立网站参与度分数 4.1 或更高，则认为他们与 Social Org 有关系。</span><span class="sxs-lookup"><span data-stu-id="40ad0-162">Users are considered to have a relationship with Social Org if they have established a site engagement score of 4.1 or greater with any one of domains owned by Social Org.</span></span>
> 
> <span data-ttu-id="40ad0-163">如果另一个网站包含第三方内容 \ (则假设来自 Social Org 拥有的任何域的嵌入视频来自 `https://content-embedder.example` \) ，这些域通常受跟踪防护强制执行的限制，只要用户具有 Social Org 拥有域的网站参与度分数维持在阈值之上，该网站就无需跟踪防护强制。 `social-videos.example`</span><span class="sxs-lookup"><span data-stu-id="40ad0-163">If another site, `https://content-embedder.example`, includes third-party content \(say an embedded video from `social-videos.example`\) from any of the domains owned by Social Org that would normally be restricted by tracking prevention enforcements, the site is exempt from tracking prevention enforcements as long as the user's site engagement score with domains owned by Social Org is maintained above the threshold.</span></span>
> 
> <span data-ttu-id="40ad0-164">如果网站不属于组织，用户必须直接使用网站参与度分数 4.1 或更高，然后才能轻松使用跟踪防护施加的任何存储访问/资源负载块。</span><span class="sxs-lookup"><span data-stu-id="40ad0-164">If a site does not belong to an organization, a user must establish a site engagement score of 4.1 or greater with it directly before any storage access/resource load blocks imposed by tracking prevention are relaxed.</span></span>

<span data-ttu-id="40ad0-165">目前仅在平衡模式下应用组织参与缓解，以便 Microsoft Edge 为已选择"严格"的用户提供可能的最高保护。</span><span class="sxs-lookup"><span data-stu-id="40ad0-165">The org engagement mitigation is currently only applied in Balanced mode so that Microsoft Edge is offering the highest possible protections for users who have opted into Strict.</span></span>

### <span data-ttu-id="40ad0-166">CompatExceptions 列表</span><span class="sxs-lookup"><span data-stu-id="40ad0-166">The CompatExceptions List</span></span>  

<span data-ttu-id="40ad0-167">根据 Microsoft 最近收到的用户反馈，Microsoft Edge 维护一个小型站点列表 \ (其中大多数站点位于断开连接内容类别\) 尽管已执行上述两项缓解措施，但由于跟踪防护而中断。</span><span class="sxs-lookup"><span data-stu-id="40ad0-167">Based on recent user feedback Microsoft received, Microsoft Edge maintains a small list of sites \(most of which are in the Disconnect Content category\) that were breaking due to tracking prevention despite having the above two mitigations in place.</span></span> <span data-ttu-id="40ad0-168">此列表上的网站无需跟踪防护实施。</span><span class="sxs-lookup"><span data-stu-id="40ad0-168">Sites on this list are exempt from tracking prevention enforcements.</span></span>  <span data-ttu-id="40ad0-169">可以在磁盘上找到以下描述 [的位置](#determining-whetherhow-a-particular-url-is-classified) 的列表。</span><span class="sxs-lookup"><span data-stu-id="40ad0-169">The list can be found on disk at the [locations](#determining-whetherhow-a-particular-url-is-classified) described below.</span></span>  <span data-ttu-id="40ad0-170">用户可以使用中的"阻止"选项 **覆盖其** 上的条目 `edge://settings/content/cookies` 。</span><span class="sxs-lookup"><span data-stu-id="40ad0-170">Users may override entries on it using the **Block** option in `edge://settings/content/cookies`.</span></span>

<span data-ttu-id="40ad0-171">为了避免继续维护此列表，Microsoft 目前正在使用 Chromium 代码库中的存储访问[API。][GitHubMsExplainersStorageAccessApi]</span><span class="sxs-lookup"><span data-stu-id="40ad0-171">To avoid maintaining this list moving forwards, Microsoft is currently working on the [Storage Access API][GitHubMsExplainersStorageAccessApi] in the Chromium codebase.</span></span>  <span data-ttu-id="40ad0-172">存储访问 [API][GitHubMsExplainersStorageAccessApi] 为网站开发人员提供了直接从用户请求存储访问权限的方法，为用户提供了有关其隐私设置如何影响其浏览体验的透明度，并给予网站开发人员控件快速直观地取消阻止。</span><span class="sxs-lookup"><span data-stu-id="40ad0-172">The [Storage Access API][GitHubMsExplainersStorageAccessApi] gives site developers a way to request storage access from users directly, providing users with more transparency into how their privacy settings are affecting their browsing experience, and giving site developers controls to quickly and intuitively unblock themselves.</span></span>

<span data-ttu-id="40ad0-173">实现存储访问[API][GitHubMsExplainersStorageAccessApi]后，Microsoft 将弃用 CompatExceptions 列表并联系受影响的站点，以使它们了解问题，并请求他们使用存储[访问 API。][GitHubMsExplainersStorageAccessApi]</span><span class="sxs-lookup"><span data-stu-id="40ad0-173">After the [Storage Access API][GitHubMsExplainersStorageAccessApi] is implemented, Microsoft will deprecate the CompatExceptions list and reach out to the affected sites both to make them aware of the issues, and to request that they use the [Storage Access API][GitHubMsExplainersStorageAccessApi] moving forward.</span></span>  

## <span data-ttu-id="40ad0-174">当前跟踪防护行为</span><span class="sxs-lookup"><span data-stu-id="40ad0-174">Current tracking prevention behavior</span></span>  

<span data-ttu-id="40ad0-175">下表显示了应用于 Microsoft Edge 中每个分类跟踪器类别的强制操作和缓解。</span><span class="sxs-lookup"><span data-stu-id="40ad0-175">The following table shows the enforcement actions and mitigations that are applied to each category of classified tracker in Microsoft Edge.</span></span>  

*   <span data-ttu-id="40ad0-176">顶部是断开连接跟踪保护列表类别定义的跟踪 [程序类别][GitHubDisconnectTrackingProtectionCategories]。</span><span class="sxs-lookup"><span data-stu-id="40ad0-176">Along the top are the categories of trackers as defined by [Disconnect tracking protection list categories][GitHubDisconnectTrackingProtectionCategories].</span></span>  
*   <span data-ttu-id="40ad0-177">左侧是 Microsoft Edge \ (Basic、Balanced 和 Strict\) 中的三个级别的跟踪) 。</span><span class="sxs-lookup"><span data-stu-id="40ad0-177">Along the left side are the three levels of tracking prevention in Microsoft Edge \(Basic, Balanced, and Strict\).</span></span>  
*   <span data-ttu-id="40ad0-178">该 `S` 字母指示阻止存储访问。</span><span class="sxs-lookup"><span data-stu-id="40ad0-178">The letter `S` indicates that storage access is blocked.</span></span>  
*   <span data-ttu-id="40ad0-179">该字母指示存储访问和资源负载 `B` \ (如网络请求\) 被阻止。</span><span class="sxs-lookup"><span data-stu-id="40ad0-179">The letter `B` indicates that both storage access and resource loads \(such as network requests\) are blocked.</span></span>  
*   <span data-ttu-id="40ad0-180">连字符 \ (\) 表示未对存储访问或资源负载 `-` 应用块。</span><span class="sxs-lookup"><span data-stu-id="40ad0-180">A hyphen \(`-`\) indicates that no block is applied to either storage access or resource loads.</span></span>  

| | <span data-ttu-id="40ad0-181">放大</span><span class="sxs-lookup"><span data-stu-id="40ad0-181">Advertizing</span></span> | <span data-ttu-id="40ad0-182">分析</span><span class="sxs-lookup"><span data-stu-id="40ad0-182">Analytics</span></span> | <span data-ttu-id="40ad0-183">内容</span><span class="sxs-lookup"><span data-stu-id="40ad0-183">Content</span></span> | <span data-ttu-id="40ad0-184">加密</span><span class="sxs-lookup"><span data-stu-id="40ad0-184">Cryptomining</span></span> | <span data-ttu-id="40ad0-185">指纹</span><span class="sxs-lookup"><span data-stu-id="40ad0-185">Fingerprinting</span></span> | <span data-ttu-id="40ad0-186">社交</span><span class="sxs-lookup"><span data-stu-id="40ad0-186">Social</span></span> | <span data-ttu-id="40ad0-187">Other</span><span class="sxs-lookup"><span data-stu-id="40ad0-187">Other</span></span> | <span data-ttu-id="40ad0-188">同一组织缓解</span><span class="sxs-lookup"><span data-stu-id="40ad0-188">Same Org Mitigation</span></span> | <span data-ttu-id="40ad0-189">组织参与缓解</span><span class="sxs-lookup"><span data-stu-id="40ad0-189">Org Engagement Mitigation</span></span> |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **<span data-ttu-id="40ad0-190">基本</span><span class="sxs-lookup"><span data-stu-id="40ad0-190">Basic</span></span>** | - | - | - | <span data-ttu-id="40ad0-191">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-191">B</span></span> | <span data-ttu-id="40ad0-192">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-192">B</span></span> | - | - | <span data-ttu-id="40ad0-193">启用</span><span class="sxs-lookup"><span data-stu-id="40ad0-193">Enabled</span></span> | <span data-ttu-id="40ad0-194">不适用</span><span class="sxs-lookup"><span data-stu-id="40ad0-194">N/A</span></span> |  
| **<span data-ttu-id="40ad0-195">平衡</span><span class="sxs-lookup"><span data-stu-id="40ad0-195">Balanced</span></span>** | <span data-ttu-id="40ad0-196">S</span><span class="sxs-lookup"><span data-stu-id="40ad0-196">S</span></span> | - | <span data-ttu-id="40ad0-197">S</span><span class="sxs-lookup"><span data-stu-id="40ad0-197">S</span></span> | <span data-ttu-id="40ad0-198">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-198">B</span></span> | <span data-ttu-id="40ad0-199">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-199">B</span></span> | <span data-ttu-id="40ad0-200">S</span><span class="sxs-lookup"><span data-stu-id="40ad0-200">S</span></span> | <span data-ttu-id="40ad0-201">S</span><span class="sxs-lookup"><span data-stu-id="40ad0-201">S</span></span> | <span data-ttu-id="40ad0-202">已启用</span><span class="sxs-lookup"><span data-stu-id="40ad0-202">Enabled</span></span> | <span data-ttu-id="40ad0-203">已启用</span><span class="sxs-lookup"><span data-stu-id="40ad0-203">Enabled</span></span> |  
| **<span data-ttu-id="40ad0-204">“严格”</span><span class="sxs-lookup"><span data-stu-id="40ad0-204">Strict</span></span>** | <span data-ttu-id="40ad0-205">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-205">B</span></span> | <span data-ttu-id="40ad0-206">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-206">B</span></span> | <span data-ttu-id="40ad0-207">S</span><span class="sxs-lookup"><span data-stu-id="40ad0-207">S</span></span> | <span data-ttu-id="40ad0-208">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-208">B</span></span> | <span data-ttu-id="40ad0-209">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-209">B</span></span> | <span data-ttu-id="40ad0-210">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-210">B</span></span> | <span data-ttu-id="40ad0-211">B</span><span class="sxs-lookup"><span data-stu-id="40ad0-211">B</span></span> | <span data-ttu-id="40ad0-212">已启用</span><span class="sxs-lookup"><span data-stu-id="40ad0-212">Enabled</span></span> | <span data-ttu-id="40ad0-213">禁用</span><span class="sxs-lookup"><span data-stu-id="40ad0-213">Disabled</span></span> |  

> [!NOTE]
> <span data-ttu-id="40ad0-214">组织参与缓解不适用于加密或指纹类别。</span><span class="sxs-lookup"><span data-stu-id="40ad0-214">The org engagement mitigation does not apply to the Cryptomining or Fingerprinting categories.</span></span>  

> [!TIP]
> <span data-ttu-id="40ad0-215">严格模式会阻止比平衡更多的资源负载。</span><span class="sxs-lookup"><span data-stu-id="40ad0-215">Strict mode blocks more resource loads than Balanced.</span></span>  <span data-ttu-id="40ad0-216">阻止更多资源负载可能会导致出现严格模式，以阻止比 Balanced 更少的跟踪请求，因为从不加载提出请求的跟踪程序。</span><span class="sxs-lookup"><span data-stu-id="40ad0-216">The blocking of more resource loads may result in Strict mode appearing to block less tracking requests than Balanced since the trackers making the requests are never loaded.</span></span>  

> [!NOTE]
> <span data-ttu-id="40ad0-217">当前跟踪防护行为中的[](#current-tracking-prevention-behavior)指纹列是指除其他列表外，位于指纹列表上的跟踪器。</span><span class="sxs-lookup"><span data-stu-id="40ad0-217">The Fingerprinting column in [Current tracking prevention behavior](#current-tracking-prevention-behavior) refers to trackers that are on the Fingerprinting list in addition to another list.</span></span>  <span data-ttu-id="40ad0-218">仅出现在指纹列表上的跟踪器被视为非恶意指纹，并且不会被阻止。</span><span class="sxs-lookup"><span data-stu-id="40ad0-218">Trackers that appear on solely on the Fingerprinting list are considered non-malicious fingerprinters and are not blocked.</span></span>

### <span data-ttu-id="40ad0-219">InPrivate 行为</span><span class="sxs-lookup"><span data-stu-id="40ad0-219">InPrivate behavior</span></span>  

<span data-ttu-id="40ad0-220">在 Microsoft Edge 79 中，默认行为是在 InPrivate 中应用严格模式保护。</span><span class="sxs-lookup"><span data-stu-id="40ad0-220">In Microsoft Edge 79, the default behavior was to apply Strict mode protections in InPrivate.</span></span>  <span data-ttu-id="40ad0-221">在 Microsoft Edge 80 中，此行为已替换为允许用户决定是应用严格模式保护还是保留其常规设置（在浏览 `edge://settings/privacy` InPrivate 时）的开关。</span><span class="sxs-lookup"><span data-stu-id="40ad0-221">In Microsoft Edge 80, this behavior was replaced by a switch in `edge://settings/privacy` that allows users to decide whether to apply Strict mode protections or to keep their regular settings while browsing InPrivate.</span></span>  

## <span data-ttu-id="40ad0-222">确定是否/如何对特定 URL 进行分类</span><span class="sxs-lookup"><span data-stu-id="40ad0-222">Determining whether/how a particular URL is classified</span></span>  

<span data-ttu-id="40ad0-223">确定是否将特定 URL 分类为已知跟踪程序的最简单方法是执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="40ad0-223">The easiest way to determine whether a specific URL is classified as a known tracker is to perform the following steps.</span></span>  

1.  <span data-ttu-id="40ad0-224">打开 DevTools 并导航到控制台选项卡。</span><span class="sxs-lookup"><span data-stu-id="40ad0-224">Open DevTools and navigate to the Console tab.</span></span>  
1.  <span data-ttu-id="40ad0-225">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="40ad0-225">Reload the page.</span></span>  
    1.  <span data-ttu-id="40ad0-226">你可能希望首先清除 **Cookie** 和其他网站数据，以重置网站参与度分数并确保完全干净。</span><span class="sxs-lookup"><span data-stu-id="40ad0-226">You may want to clear **Cookies and other site data** first to reset site engagement scores and ensure a completely clean slate.</span></span>  
1.  <span data-ttu-id="40ad0-227">查找读取的任何邮件 `Tracking Prevention blocked access to storage for <URL>` 。</span><span class="sxs-lookup"><span data-stu-id="40ad0-227">Look for any messages that read `Tracking Prevention blocked access to storage for <URL>`.</span></span>  
    1.  <span data-ttu-id="40ad0-228">您可以展开消息以查看被阻止的单个 URL。</span><span class="sxs-lookup"><span data-stu-id="40ad0-228">You may expand the messages to see the individual URLs that were blocked.</span></span>  
1.  <span data-ttu-id="40ad0-229">如果需要确定特定被阻止网站属于哪个类别，最简单的方法是在列表上的断开连接services.js[搜索][GitHubDisconnectTrackingProtectionCategories]。</span><span class="sxs-lookup"><span data-stu-id="40ad0-229">If you need to determine which category a specific blocked site is in, the easiest way to do this is to search for it on the [Disconnect services.json list][GitHubDisconnectTrackingProtectionCategories].</span></span>  <span data-ttu-id="40ad0-230">条目按字母顺序排序，因此滚动到网站条目块的顶部使您能够查找特定网站的特定类别。</span><span class="sxs-lookup"><span data-stu-id="40ad0-230">The entries are alphabetized, so scrolling to the top of a block of site entries enables you to find the specific category for a particular site.</span></span>  

> [!TIP]
> <span data-ttu-id="40ad0-231">如果需要访问存储在磁盘上的跟踪防护列表，可以在两个位置之一找到每个跟踪防护列表。</span><span class="sxs-lookup"><span data-stu-id="40ad0-231">If you need to access the tracking prevention lists that are stored on disk, each may be found in one of two locations.</span></span>  
>
> <span data-ttu-id="40ad0-232">**基于组件的更新** - 从"信任保护列表"组件下载的列表</span><span class="sxs-lookup"><span data-stu-id="40ad0-232">**Component-based updates** - The lists that are downloaded from the "Trust Protection Lists" component</span></span>  
>
> <span data-ttu-id="40ad0-233">窗口：</span><span class="sxs-lookup"><span data-stu-id="40ad0-233">Windows:</span></span> `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> <span data-ttu-id="40ad0-234">macOS：</span><span class="sxs-lookup"><span data-stu-id="40ad0-234">macOS:</span></span> `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> <span data-ttu-id="40ad0-235">**安装目录** - 与 Microsoft Edge 安装程序捆绑的列表。</span><span class="sxs-lookup"><span data-stu-id="40ad0-235">**Installation directory** - The lists that are bundled with the Microsoft Edge Installer.</span></span>  <span data-ttu-id="40ad0-236">如果选择了不同的安装目录，则具体路径可能不同。</span><span class="sxs-lookup"><span data-stu-id="40ad0-236">If you selected a different installation directory, your exact paths may be different.</span></span>  
>
> <span data-ttu-id="40ad0-237">窗口：</span><span class="sxs-lookup"><span data-stu-id="40ad0-237">Windows:</span></span> `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> <span data-ttu-id="40ad0-238">macOS：</span><span class="sxs-lookup"><span data-stu-id="40ad0-238">macOS:</span></span> `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## <span data-ttu-id="40ad0-239">常见问题</span><span class="sxs-lookup"><span data-stu-id="40ad0-239">Frequently Asked Questions</span></span>  

<span data-ttu-id="40ad0-240">以下部分包含有关 Microsoft Edge 中跟踪防护功能常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="40ad0-240">The following section contains answers to frequently asked questions about the tracking prevention feature in Microsoft Edge.</span></span>  

**<span data-ttu-id="40ad0-241">是否有一种方法可以阻止或允许特定跟踪器进行调试？</span><span class="sxs-lookup"><span data-stu-id="40ad0-241">Is there a way to block or allow specific trackers for debugging purposes?</span></span>**  

<span data-ttu-id="40ad0-242">目前，Microsoft Edge 仅公开了一个选项，用于禁止跟踪防护强制功能在指定的站点上运行。</span><span class="sxs-lookup"><span data-stu-id="40ad0-242">Currently, Microsoft Edge only exposes an option to disable tracking prevention enforcements from running on a specified site.</span></span>  <span data-ttu-id="40ad0-243">可通过页面信息飞出或通过页面访问 `edge://settings/privacy/trackingPreventionExceptions` 此选项。</span><span class="sxs-lookup"><span data-stu-id="40ad0-243">This option is accessed via the page info flyout or through the `edge://settings/privacy/trackingPreventionExceptions` page.</span></span>  

<span data-ttu-id="40ad0-244">也就是说，页面上的"\*\*\*\* 阻止"\*\*\*\* 和"允许"选项可用于允许或拒绝特定域访问存储，如 Cookie 和其他 `edge://settings/content/cookies` 浏览器存储机制。</span><span class="sxs-lookup"><span data-stu-id="40ad0-244">That being said, the **Block** and **Allow** options on the `edge://settings/content/cookies` page may be used to allow or deny specific domains access to storage such as cookies and other browser storage mechanisms.</span></span>  <span data-ttu-id="40ad0-245">这适用于调试因跟踪阻止访问特定网站的存储的防护实施导致的站点问题。</span><span class="sxs-lookup"><span data-stu-id="40ad0-245">This is useful for debugging site issues that are caused by tracking prevention enforcements blocking access to storage for a specific site.</span></span>  

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
