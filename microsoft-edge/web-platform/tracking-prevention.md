---
description: 此页面提供有关 Microsoft Edge （Chromium）跟踪保护功能的文档
title: Microsoft Edge 中的跟踪保护（Chromium）
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
# <span data-ttu-id="fc1dd-104">Microsoft Edge 中的跟踪保护（Chromium）</span><span class="sxs-lookup"><span data-stu-id="fc1dd-104">Tracking Prevention in Microsoft Edge (Chromium)</span></span>  

<span data-ttu-id="fc1dd-105">Microsoft Edge 中的跟踪防护功能通过限制跟踪器访问基于浏览器的存储和网络的能力来保护联机跟踪用户。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-105">The tracking prevention feature in Microsoft Edge protects users from online tracking by restricting the ability of trackers to access browser-based storage as well as the network.</span></span>  <span data-ttu-id="fc1dd-106">它旨在保持 Microsoft Edge[浏览器的隐私承诺][MicrosoftEdgeBrowserPrivacyPromise]，同时确保默认情况下不会对网站兼容性或 web 的经济生存能力产生任何影响。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-106">It is built to uphold the Microsoft Edge [browser privacy promise][MicrosoftEdgeBrowserPrivacyPromise] while also ensuring that there is no impact by default to website compatibility or the economic viability of the web.</span></span>  

<span data-ttu-id="fc1dd-107">Microsoft Edge 当前向用户提供三个级别的跟踪防护，这些级别通过导航到来选择 `edge://settings/privacy` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-107">Microsoft Edge currently offers users three levels of tracking prevention, which are selected by navigating to `edge://settings/privacy`.</span></span>  

![跟踪防护的三个设置][ImageThreeSettingsTrackingPrevention]  

1.  <span data-ttu-id="fc1dd-109">**基本**-跟踪保护的最低限制级别，适用于欣赏个性化广告的用户和不介意在 web 上跟踪的用户。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-109">**Basic** - The least restrictive level of tracking prevention that is designed for users who enjoy personalized advertisements and who do not mind being tracked on the web.</span></span>  <span data-ttu-id="fc1dd-110">基本仅针对恶意跟踪用户（如 fingerprinters 和 cryptominers）保护用户。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-110">Basic only protects users against malicious trackers such as fingerprinters and cryptominers.</span></span>  
1.  <span data-ttu-id="fc1dd-111">已**平衡（默认）** -跟踪防护的默认级别，适用于希望在浏览时看到在 web 周围关注更少 creepy 广告的用户。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-111">**Balanced (Default)** - The default level of tracking prevention that is designed for users who want to see less creepy advertisements that follow them around the web while they browse.</span></span>  <span data-ttu-id="fc1dd-112">平衡旨在阻止来自用户永不参与的网站的跟踪程序，同时将 web 上的兼容性问题的风险降到最低。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-112">Balanced aims to block trackers from sites that users never engage with while minimizing the risk of compatibility issues on the web.</span></span>  
1.  <span data-ttu-id="fc1dd-113">**严格**-跟踪防护的最高限制级别，适用于不确定最高隐私的网站兼容性的用户。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-113">**Strict** - The most restrictive level of tracking prevention that is designed for users who are okay trading website compatibility for maximum privacy.</span></span>  

<span data-ttu-id="fc1dd-114">Microsoft Edge 中的跟踪防护功能由三个主要组件组成，这些组件协同工作以确定网站中的特定资源是否应归类为跟踪者和已阻止。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-114">The tracking prevention feature in Microsoft Edge is made up of three main components that work together to determine whether a specific resource from a website should be classified as a tracker and blocked.</span></span>  <span data-ttu-id="fc1dd-115">这些组件如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-115">The components are as follows:</span></span>  

1.  <span data-ttu-id="fc1dd-116">**分类**-Microsoft EDGE 确定 URL 是否属于跟踪器的方式。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-116">**Classification** - The way Microsoft Edge determines whether a URL belongs to a tracker.</span></span>  
1.  <span data-ttu-id="fc1dd-117">**强制执行**-保护 Microsoft Edge 用户免受分类为跟踪程序的 url 的操作。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-117">**Enforcement** - The actions taken to protect Microsoft Edge users from URLs classified as trackers.</span></span>  
1.  <span data-ttu-id="fc1dd-118">**缓解**-为确保用户指定的常用网站而提供的机制在提供强默认保护时仍然有效。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-118">**Mitigations** - The mechanisms provided to ensure user-specified favorite sites still work, while offering strong default protection.</span></span>  

<span data-ttu-id="fc1dd-119">本页面详细讨论并详细介绍每个组件。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-119">Each of the components are explored and explained in detail on this page.</span></span>  

## <span data-ttu-id="fc1dd-120">分类</span><span class="sxs-lookup"><span data-stu-id="fc1dd-120">Classification</span></span>  

<span data-ttu-id="fc1dd-121">Microsoft Edge 中的跟踪防护功能的第一个组件是分类。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-121">The first component of the tracking prevention feature in Microsoft Edge is classification.</span></span>  <span data-ttu-id="fc1dd-122">若要对联机跟踪跟踪人员进行分类并将其分组为类别，Microsoft Edge 使用[断开][|::ref1::|Main]的打开源[跟踪保护列表][GitHubDisconnectMeTrackingProtection]。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-122">To classify online trackers and group them into categories, Microsoft Edge uses the [Disconnect][|::ref1::|Main] open source [tracking protection lists][GitHubDisconnectMeTrackingProtection].</span></span>  <span data-ttu-id="fc1dd-123">这些列表通过可查看的 "信任保护列表" 组件提供 `edge://components` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-123">The lists are delivered via the "Trust Protection Lists" component, which is viewable at `edge://components`.</span></span>  <span data-ttu-id="fc1dd-124">下载列表后，这些列表将存储在磁盘上，您可以使用它们来确定是否对特定的 URL 进行分类。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-124">After being downloaded, the lists are stored on disk where you may use them to determine whether/how a particular URL is classified.</span></span>  

<span data-ttu-id="fc1dd-125">若要确定某个 URL 是否由 Microsoft Edge 中的分类系统视为跟踪器，请检查一系列主机名，从完全匹配项开始，然后继续检查部分匹配项，以查找最多四个标签（超过顶级域）。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-125">To determine if a URL is considered a tracker by the classification system in Microsoft Edge, a series of host names are checked, starting with an exact match and then proceeding to check for partial matches for up to four labels beyond the top-level domain.</span></span>  

> <span data-ttu-id="fc1dd-126">**示例**：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-126">**Example**:</span></span>  
> 
> <span data-ttu-id="fc1dd-127">URL</span><span class="sxs-lookup"><span data-stu-id="fc1dd-127">URL:</span></span> `https://a.subdomain.of.a.known.tracker.test/some/path`  
> 
> <span data-ttu-id="fc1dd-128">已测试主机名：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-128">Tested host names:</span></span>  
> 
> *   `a.subdomain.of.a.known.tracker.test`  
> *   `of.a.known.tracker.test`  
> *   `a.known.tracker.test`  
> *   `known.tracker.test`  
> *   `tracker.test`  

<span data-ttu-id="fc1dd-129">如果这些主机名称中的任何一个与[断开连接][|::ref2::|Main][列表][GitHubDisconnectMeTrackingProtection]上的主机名相匹配，Microsoft Edge 将继续评估强制操作以防止跟踪用户。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-129">If any of those host names match with a host name on the [Disconnect][|::ref2::|Main] [lists][GitHubDisconnectMeTrackingProtection], Microsoft Edge proceeds with evaluating enforcement actions to prevent users from being tracked.</span></span>  

## <span data-ttu-id="fc1dd-130">强制</span><span class="sxs-lookup"><span data-stu-id="fc1dd-130">Enforcement</span></span>  

<span data-ttu-id="fc1dd-131">为了对 web 上的跟踪操作提供保护，Microsoft Edge 针对分类跟踪跟踪执行两个强制操作：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-131">To provide protection from tracking actions on the web, Microsoft Edge takes two enforcement actions against classified trackers:</span></span>

*   <span data-ttu-id="fc1dd-132">**限制存储访问**-如果已知的跟踪资源尝试访问任何可能尝试保留有关用户的数据的 web 存储，则访问的 Microsoft Edge 块。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-132">**Restrict storage access** - If a known tracking resource tries to access any web storage where it may try to persist data about the user, Microsoft Edge blocks that access.</span></span>  <span data-ttu-id="fc1dd-133">这包括限制该跟踪器获取或设置 cookie 以及访问存储 Api （如和）的能力 `IndexedDB` `localStorage` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-133">This includes restricting the ability for that tracker to get or set cookies as well as access storage APIs such as `IndexedDB` and `localStorage`.</span></span>  
*   <span data-ttu-id="fc1dd-134">**阻止资源加载**-如果在网站上加载了已知的跟踪资源，Microsoft Edge 可能会在请求到达网络之前阻止该加载，具体取决于负载的兼容性影响和用户设置的跟踪保护设置。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-134">**Block resource loads** - If a known tracking resource is being loaded on a website, Microsoft Edge may block that load before the request reaches the network depending on compatibility impact of the load and the tracking prevention setting a user has set.</span></span>  <span data-ttu-id="fc1dd-135">已阻止的加载可能包括跟踪脚本、像素、iframe 等。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-135">Blocked loads may include tracking scripts, pixels, iframes, and more.</span></span>  <span data-ttu-id="fc1dd-136">这可以防止任何可能发送到跟踪域的数据，甚至还可以提高加载时间和页面性能，作为副作用。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-136">This prevents any data potentially being sent to the tracking domain and may even improve load times and page performance as a side effect.</span></span>  

<span data-ttu-id="fc1dd-137">用户可以单击地址栏左侧的 "页面信息" 飞出图标，了解特定页面上被阻止的跟踪器：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-137">A user may click the page info flyout icon on the left side of the address bar to find out which trackers were blocked on a specific page:</span></span> 

![页面信息浮出控件中的被阻止的跟踪跟踪][ImageBlockedTrackersPageInfoFlyout]  

<span data-ttu-id="fc1dd-139">Enforcements 的应用方式取决于用户选择的跟踪保护级别和可能适用的缓解。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-139">How the enforcements are applied depends on what level of tracking prevention the user selected and the mitigations that may apply.</span></span>  

## <span data-ttu-id="fc1dd-140">缓解</span><span class="sxs-lookup"><span data-stu-id="fc1dd-140">Mitigations</span></span>  

<span data-ttu-id="fc1dd-141">为了确保尽可能多地保留 web 兼容性，Microsoft Edge 有三个缓解措施，可帮助在特定情况下平衡 enforcements。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-141">To ensure that web compatibility is preserved as much as possible, Microsoft Edge has three mitigations to help balance enforcements in specific situations.</span></span>  <span data-ttu-id="fc1dd-142">这些是组织间的[关系缓解](#org-relationship-mitigation)、[组织参与缓解](#org-engagement-mitigation)和[CompatExceptions 列表](#the-compatexceptions-list)。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-142">These are the [Org Relationship mitigation](#org-relationship-mitigation), the [Org Engagement mitigation](#org-engagement-mitigation), and the [CompatExceptions List](#the-compatexceptions-list).</span></span>  

<span data-ttu-id="fc1dd-143">在深入研究缓解之前，有必要定义简短的 "组织" 或 "组织" 概念。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-143">Before diving into the mitigations, it is worth defining the concept of an "Organization" or "Org" for short.</span></span>  <span data-ttu-id="fc1dd-144">"[断开连接][|::ref3::|Main]" 还会保留名为[实体][GitHubDisconnectMeTrackingProtectionEntitiesJson]的列表，该列表定义由同一父组织/公司拥有的 url 组。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-144">[Disconnect][|::ref3::|Main] also maintains a list called [entities.json][GitHubDisconnectMeTrackingProtectionEntitiesJson] that defines groups of URLs that are owned by the same parent organization/company.</span></span>  <span data-ttu-id="fc1dd-145">Microsoft Edge 中的跟踪防护功能在[组织关系缓解](#org-relationship-mitigation)和[组织参与缓解](#org-engagement-mitigation)中使用此列表，最大程度地减少由于跟踪阻止影响跨组织请求而导致的兼容性问题。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-145">The tracking prevention feature in Microsoft Edge uses this list in both the [Org Relationship mitigation](#org-relationship-mitigation) and the [Org Engagement mitigation](#org-engagement-mitigation) to minimize the occurrence of compatibility issues caused by tracking prevention affecting cross-organizational requests.</span></span>  

### <span data-ttu-id="fc1dd-146">组织间的关系缓解</span><span class="sxs-lookup"><span data-stu-id="fc1dd-146">Org Relationship Mitigation</span></span>  

<span data-ttu-id="fc1dd-147">几个热门网站可维护网站和内容交付网络 \ （Cdn \），以便为这些网站提供静态资源和内容。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-147">Several popular websites maintain both websites and Content Delivery Networks \(CDNs\) to serve static resources and content to those sites.</span></span>  <span data-ttu-id="fc1dd-148">若要确保这些类型的方案不受 "跟踪保护" 的影响，Microsoft Edge exempts 网站在向同一父组织（在[断开连接的实体][GitHubDisconnectMeTrackingProtectionEntitiesJson]中定义）所拥有的其他网站发出第三方请求时，从 "跟踪防护" 中创建网站。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-148">To ensure that these types of scenarios are not affected by tracking prevention, Microsoft Edge exempts a site from tracking prevention when the site is making third-party requests to other sites owned by the same parent organization \(as defined in the [Disconnect entities.json list][GitHubDisconnectMeTrackingProtectionEntitiesJson]\).</span></span>  <span data-ttu-id="fc1dd-149">这是一个示例的最佳说明。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-149">This is best illustrated by an example.</span></span>  

> **<span data-ttu-id="fc1dd-150">示例：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-150">Example:</span></span>**
> 
> <span data-ttu-id="fc1dd-151">名为 Org1 的组织拥有域 `org1.test` 以及 `org1-cdn.test` [断开连接的实体][GitHubDisconnectMeTrackingProtectionEntitiesJson]中定义的域。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-151">An organization named Org1 owns the domains `org1.test` and `org1-cdn.test`, as defined in the [Disconnect entities.json list][GitHubDisconnectMeTrackingProtectionEntitiesJson].</span></span>  <span data-ttu-id="fc1dd-152">假设 `org1-cdn.test` 已归类为跟踪器，并且通常会对其应用跟踪防护 enforcements。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-152">Imagine that `org1-cdn.test` is classified as a tracker and would normally have tracking prevention enforcements applied to it.</span></span>  <span data-ttu-id="fc1dd-153">如果用户访问 `https://org1.test` 和网站尝试加载资源 `https://org1-cdn.test` ，Microsoft Edge 不会对所做的请求执行任何强制操作， `org1-cdn.test` 即使它不是第一方 URL 也是如此。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-153">If a user visits `https://org1.test` and the site tries to load a resource from `https://org1-cdn.test`, Microsoft Edge does not take any enforcement actions against requests made to `org1-cdn.test` even though it is not a first-party URL.</span></span>  <span data-ttu-id="fc1dd-154">但是，如果另一个不属于 Org1 组织的 URL 尝试加载同一资源，则该请求将受到 enforcements，因为它不是同一组织的一部分。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-154">If another URL that is not part of the Org1 organization tries to load that same resource, however, then the request would be subject to enforcements because it is not part of the same organization.</span></span>  
> 
> <span data-ttu-id="fc1dd-155">即使此 relaxes 跟踪保护 enforcements 对于属于同一组织的网站，这种情况不太可能带来大量隐私风险，因为这样的组织能够确定您访问的网站/资源以及 `https://org1.test` `https://org1-cdn.test` 使用内部后端数据。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-155">Even though this relaxes tracking prevention enforcements for sites that belong to the same organization, it is unlikely that this introduces a high amount of privacy risk since such organizations are able to determine which sites/resources you have accessed on `https://org1.test` as well `https://org1-cdn.test` using internal back-end data.</span></span>  

### <span data-ttu-id="fc1dd-156">组织参与缓解</span><span class="sxs-lookup"><span data-stu-id="fc1dd-156">Org Engagement Mitigation</span></span>  

<span data-ttu-id="fc1dd-157">已创建组织参与缓解，以通过确保由用户充分参与的组织所拥有的兼容性风险来最大程度地减少跟踪保护带来的兼容性风险，并在 web 上继续按预期工作。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-157">The org engagement mitigation was created to minimize compatibility risks introduced by tracking prevention by ensuring that sites owned by organizations that users sufficiently engage with continue to work as expected across the web.</span></span>  <span data-ttu-id="fc1dd-158">只要用户建立了一个持续的关系 \ （当前由使用4.1 或更高版本的网站实施分数为或更高版本的 enforcements 定义），它就可以让[网站的参与][ChromiumDesignDocsSiteEngagement]放松</span><span class="sxs-lookup"><span data-stu-id="fc1dd-158">It makes use of [site engagement][ChromiumDesignDocsSiteEngagement] to relax enforcements whenever a user has established an ongoing relationship \(currently defined by a site engagement score of 4.1 or greater\) with a given site.</span></span>  <span data-ttu-id="fc1dd-159">这种情况下，最好的例子如下所示：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-159">This again is best illustrated by an example:</span></span>

> **<span data-ttu-id="fc1dd-160">示例：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-160">Example:</span></span>**
> 
> <span data-ttu-id="fc1dd-161">名为 "社交组织" 的组织拥有域 `social.example` 和 `social-videos.example` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-161">An organization named Social Org owns the domains `social.example` and `social-videos.example`.</span></span>
> 
> <span data-ttu-id="fc1dd-162">如果用户已建立了4.1 或更高的网站参与分数或更高的与社交组织拥有的任何一个域的关系，则认为用户与社交组织有关系。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-162">Users are considered to have a relationship with Social Org if they have established a site engagement score of 4.1 or greater with any one of domains owned by Social Org.</span></span>
> 
> <span data-ttu-id="fc1dd-163">如果另一个网站 `https://content-embedder.example` 包含第三方内容 \ （从 `social-videos.example` \ 组织所拥有的来自社交组织的任何域的嵌入视频，通常受 "跟踪防护 enforcements" 限制），则只要用户的网站参与分数与社会组织拥有的域保持在阈值之上，则该网站不受跟踪保护 enforcements。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-163">If another site, `https://content-embedder.example`, includes third-party content \(say an embedded video from `social-videos.example`\) from any of the domains owned by Social Org that would normally be restricted by tracking prevention enforcements, the site is exempt from tracking prevention enforcements as long as the user's site engagement score with domains owned by Social Org is maintained above the threshold.</span></span>
> 
> <span data-ttu-id="fc1dd-164">如果网站不属于某个组织，则用户必须在 "跟踪防护" 所强加的任何存储访问/资源负载块之前直接建立4.1 或更高的网站参与分数。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-164">If a site does not belong to an organization, a user must establish a site engagement score of 4.1 or greater with it directly before any storage access/resource load blocks imposed by tracking prevention are relaxed.</span></span>

<span data-ttu-id="fc1dd-165">组织参与缓解目前仅在平衡模式下应用，因此 Microsoft Edge 为选择严格的用户提供了最高可能的保护。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-165">The org engagement mitigation is currently only applied in Balanced mode so that Microsoft Edge is offering the highest possible protections for users who have opted into Strict.</span></span>

### <span data-ttu-id="fc1dd-166">CompatExceptions 列表</span><span class="sxs-lookup"><span data-stu-id="fc1dd-166">The CompatExceptions List</span></span>  

<span data-ttu-id="fc1dd-167">根据 Microsoft 已收到的最新用户反馈，Microsoft Edge 维护一个较小的网站列表（其中大多数是在断开连接的内容类别 \）中中断的，因为即使有上述两个缓解措施，仍可进行跟踪保护。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-167">Based on recent user feedback Microsoft received, Microsoft Edge maintains a small list of sites \(most of which are in the Disconnect Content category\) that were breaking due to tracking prevention despite having the above two mitigations in place.</span></span> <span data-ttu-id="fc1dd-168">此列表中的网站不受跟踪保护 enforcements。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-168">Sites on this list are exempt from tracking prevention enforcements.</span></span>  <span data-ttu-id="fc1dd-169">可以在磁盘上的如下所述[位置](#determining-whetherhow-a-particular-url-is-classified)找到该列表。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-169">The list can be found on disk at the [locations](#determining-whetherhow-a-particular-url-is-classified) described below.</span></span>  <span data-ttu-id="fc1dd-170">用户可以使用中的 "**阻止**" 选项替代其上的条目 `edge://settings/content/cookies` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-170">Users may override entries on it using the **Block** option in `edge://settings/content/cookies`.</span></span>

<span data-ttu-id="fc1dd-171">为避免保留此列表向前移动，Microsoft 当前正在 Chromium 基本代码中处理[存储访问 API][GitHubMsExplainersStorageAccessApi] 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-171">To avoid maintaining this list moving forwards, Microsoft is currently working on the [Storage Access API][GitHubMsExplainersStorageAccessApi] in the Chromium codebase.</span></span>  <span data-ttu-id="fc1dd-172">[存储访问 API][GitHubMsExplainersStorageAccessApi]为网站开发人员提供了一种直接向用户请求存储访问权限的方法，让用户可以更轻松地了解其隐私设置对其浏览体验有何影响，以及让网站开发人员控件快速、直观地取消阻止他们的浏览体验。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-172">The [Storage Access API][GitHubMsExplainersStorageAccessApi] gives site developers a way to request storage access from users directly, providing users with more transparency into how their privacy settings are affecting their browsing experience, and giving site developers controls to quickly and intuitively unblock themselves.</span></span>

<span data-ttu-id="fc1dd-173">实现[存储访问 api][GitHubMsExplainersStorageAccessApi]后，Microsoft 将弃用 CompatExceptions 列表并访问受影响的网站，以使他们注意这些问题，并请求他们使用[存储访问 API][GitHubMsExplainersStorageAccessApi]前进。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-173">After the [Storage Access API][GitHubMsExplainersStorageAccessApi] is implemented, Microsoft will deprecate the CompatExceptions list and reach out to the affected sites both to make them aware of the issues, and to request that they use the [Storage Access API][GitHubMsExplainersStorageAccessApi] moving forward.</span></span>  

## <span data-ttu-id="fc1dd-174">当前跟踪防护行为</span><span class="sxs-lookup"><span data-stu-id="fc1dd-174">Current tracking prevention behavior</span></span>  

<span data-ttu-id="fc1dd-175">下表显示了应用于 Microsoft Edge 中的每个分类跟踪器类别的强制操作和缓解。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-175">The following table shows the enforcement actions and mitigations that are applied to each category of classified tracker in Microsoft Edge.</span></span>  

*   <span data-ttu-id="fc1dd-176">顶部是由 "[断开连接跟踪保护列表类别][GitHubDisconnectTrackingProtectionCategories]" 定义的跟踪器类别。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-176">Along the top are the categories of trackers as defined by [Disconnect tracking protection list categories][GitHubDisconnectTrackingProtectionCategories].</span></span>  
*   <span data-ttu-id="fc1dd-177">在 Microsoft Edge \ （基本、已平衡和严格 \）中，左侧是跟踪防护的三个级别。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-177">Along the left side are the three levels of tracking prevention in Microsoft Edge \(Basic, Balanced, and Strict\).</span></span>  
*   <span data-ttu-id="fc1dd-178">字母 `S` 表示存储访问被阻止。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-178">The letter `S` indicates that storage access is blocked.</span></span>  
*   <span data-ttu-id="fc1dd-179">字母 `B` 表示存储访问和资源加载 \ （如网络请求 \）被阻止。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-179">The letter `B` indicates that both storage access and resource loads \(such as network requests\) are blocked.</span></span>  
*   <span data-ttu-id="fc1dd-180">连字符 \ （ `-` \）表示没有对存储访问或资源负载应用任何块。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-180">A hyphen \(`-`\) indicates that no block is applied to either storage access or resource loads.</span></span>  

| | <span data-ttu-id="fc1dd-181">Advertizing</span><span class="sxs-lookup"><span data-stu-id="fc1dd-181">Advertizing</span></span> | <span data-ttu-id="fc1dd-182">分析</span><span class="sxs-lookup"><span data-stu-id="fc1dd-182">Analytics</span></span> | <span data-ttu-id="fc1dd-183">内容</span><span class="sxs-lookup"><span data-stu-id="fc1dd-183">Content</span></span> | <span data-ttu-id="fc1dd-184">Cryptomining</span><span class="sxs-lookup"><span data-stu-id="fc1dd-184">Cryptomining</span></span> | <span data-ttu-id="fc1dd-185">识别</span><span class="sxs-lookup"><span data-stu-id="fc1dd-185">Fingerprinting</span></span> | <span data-ttu-id="fc1dd-186">社交</span><span class="sxs-lookup"><span data-stu-id="fc1dd-186">Social</span></span> | <span data-ttu-id="fc1dd-187">Other</span><span class="sxs-lookup"><span data-stu-id="fc1dd-187">Other</span></span> | <span data-ttu-id="fc1dd-188">相同的组织缓解措施</span><span class="sxs-lookup"><span data-stu-id="fc1dd-188">Same Org Mitigation</span></span> | <span data-ttu-id="fc1dd-189">组织参与缓解</span><span class="sxs-lookup"><span data-stu-id="fc1dd-189">Org Engagement Mitigation</span></span> |  
| - | - | - | - | - | - | - | - | - | - | - |  
| **<span data-ttu-id="fc1dd-190">基本</span><span class="sxs-lookup"><span data-stu-id="fc1dd-190">Basic</span></span>** | - | - | - | <span data-ttu-id="fc1dd-191">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-191">B</span></span> | <span data-ttu-id="fc1dd-192">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-192">B</span></span> | - | - | <span data-ttu-id="fc1dd-193">启用</span><span class="sxs-lookup"><span data-stu-id="fc1dd-193">Enabled</span></span> | <span data-ttu-id="fc1dd-194">不适用</span><span class="sxs-lookup"><span data-stu-id="fc1dd-194">N/A</span></span> |  
| **<span data-ttu-id="fc1dd-195">平衡</span><span class="sxs-lookup"><span data-stu-id="fc1dd-195">Balanced</span></span>** | <span data-ttu-id="fc1dd-196">S</span><span class="sxs-lookup"><span data-stu-id="fc1dd-196">S</span></span> | - | <span data-ttu-id="fc1dd-197">S</span><span class="sxs-lookup"><span data-stu-id="fc1dd-197">S</span></span> | <span data-ttu-id="fc1dd-198">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-198">B</span></span> | <span data-ttu-id="fc1dd-199">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-199">B</span></span> | <span data-ttu-id="fc1dd-200">S</span><span class="sxs-lookup"><span data-stu-id="fc1dd-200">S</span></span> | <span data-ttu-id="fc1dd-201">S</span><span class="sxs-lookup"><span data-stu-id="fc1dd-201">S</span></span> | <span data-ttu-id="fc1dd-202">启用</span><span class="sxs-lookup"><span data-stu-id="fc1dd-202">Enabled</span></span> | <span data-ttu-id="fc1dd-203">已启用</span><span class="sxs-lookup"><span data-stu-id="fc1dd-203">Enabled</span></span> |  
| **<span data-ttu-id="fc1dd-204">“严格”</span><span class="sxs-lookup"><span data-stu-id="fc1dd-204">Strict</span></span>** | <span data-ttu-id="fc1dd-205">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-205">B</span></span> | <span data-ttu-id="fc1dd-206">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-206">B</span></span> | <span data-ttu-id="fc1dd-207">S</span><span class="sxs-lookup"><span data-stu-id="fc1dd-207">S</span></span> | <span data-ttu-id="fc1dd-208">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-208">B</span></span> | <span data-ttu-id="fc1dd-209">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-209">B</span></span> | <span data-ttu-id="fc1dd-210">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-210">B</span></span> | <span data-ttu-id="fc1dd-211">B</span><span class="sxs-lookup"><span data-stu-id="fc1dd-211">B</span></span> | <span data-ttu-id="fc1dd-212">已启用</span><span class="sxs-lookup"><span data-stu-id="fc1dd-212">Enabled</span></span> | <span data-ttu-id="fc1dd-213">禁用</span><span class="sxs-lookup"><span data-stu-id="fc1dd-213">Disabled</span></span> |  

> [!NOTE]
> <span data-ttu-id="fc1dd-214">组织参与缓解不适用于 Cryptomining 或指纹类别。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-214">The org engagement mitigation does not apply to the Cryptomining or Fingerprinting categories.</span></span>  

> [!TIP]
> <span data-ttu-id="fc1dd-215">严格模式会阻止比平衡更多的资源负载。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-215">Strict mode blocks more resource loads than Balanced.</span></span>  <span data-ttu-id="fc1dd-216">阻止更多资源加载可能会导致严格模式的阻止跟踪请求数比已平衡的跟踪请求的阻止程度少，因为从不加载跟踪请求的跟踪请求。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-216">The blocking of more resource loads may result in Strict mode appearing to block less tracking requests than Balanced since the trackers making the requests are never loaded.</span></span>  

> [!NOTE]
> <span data-ttu-id="fc1dd-217">[当前跟踪防护行为](#current-tracking-prevention-behavior)中的指纹栏指的是指纹列表中除另一个列表之外的跟踪程序。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-217">The Fingerprinting column in [Current tracking prevention behavior](#current-tracking-prevention-behavior) refers to trackers that are on the Fingerprinting list in addition to another list.</span></span>  <span data-ttu-id="fc1dd-218">仅在指纹列表上显示的跟踪程序被视为非恶意 fingerprinters，并且不会被阻止。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-218">Trackers that appear on solely on the Fingerprinting list are considered non-malicious fingerprinters and are not blocked.</span></span>

### <span data-ttu-id="fc1dd-219">InPrivate 行为</span><span class="sxs-lookup"><span data-stu-id="fc1dd-219">InPrivate behavior</span></span>  

<span data-ttu-id="fc1dd-220">在 Microsoft Edge 79 中，默认行为是在 InPrivate 中应用严格模式保护。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-220">In Microsoft Edge 79, the default behavior was to apply Strict mode protections in InPrivate.</span></span>  <span data-ttu-id="fc1dd-221">在 Microsoft Edge 80 中，此行为被替换为一个开关， `edge://settings/privacy` 用户可在浏览 InPrivate 时决定是应用严格模式保护还是保留常规设置。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-221">In Microsoft Edge 80, this behavior was replaced by a switch in `edge://settings/privacy` that allows users to decide whether to apply Strict mode protections or to keep their regular settings while browsing InPrivate.</span></span>  

## <span data-ttu-id="fc1dd-222">确定特定 URL 是否已分类</span><span class="sxs-lookup"><span data-stu-id="fc1dd-222">Determining whether/how a particular URL is classified</span></span>  

<span data-ttu-id="fc1dd-223">确定特定 URL 是否属于已知跟踪器的最简单方法是执行以下步骤。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-223">The easiest way to determine whether a specific URL is classified as a known tracker is to perform the following steps.</span></span>  

1.  <span data-ttu-id="fc1dd-224">打开 DevTools 并导航到 "控制台" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-224">Open DevTools and navigate to the Console tab.</span></span>  
1.  <span data-ttu-id="fc1dd-225">重新加载页面。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-225">Reload the page.</span></span>  
    1.  <span data-ttu-id="fc1dd-226">您可能希望首先清除**cookie 和其他网站数据**以重置网站预订分数并确保完全干净的平板。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-226">You may want to clear **Cookies and other site data** first to reset site engagement scores and ensure a completely clean slate.</span></span>  
1.  <span data-ttu-id="fc1dd-227">查找任何阅读的邮件 `Tracking Prevention blocked access to storage for <URL>` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-227">Look for any messages that read `Tracking Prevention blocked access to storage for <URL>`.</span></span>  
    1.  <span data-ttu-id="fc1dd-228">您可以展开邮件以查看被阻止的单个 Url。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-228">You may expand the messages to see the individual URLs that were blocked.</span></span>  
1.  <span data-ttu-id="fc1dd-229">如果需要确定特定的被阻止网站所在的类别，最简单的方法是在[断开连接服务. json 列表][GitHubDisconnectTrackingProtectionCategories]中搜索。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-229">If you need to determine which category a specific blocked site is in, the easiest way to do this is to search for it on the [Disconnect services.json list][GitHubDisconnectTrackingProtectionCategories].</span></span>  <span data-ttu-id="fc1dd-230">这些条目按字母顺序排列，因此滚动到网站条目块的顶部可让你找到特定网站的特定类别。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-230">The entries are alphabetized, so scrolling to the top of a block of site entries enables you to find the specific category for a particular site.</span></span>  

> [!TIP]
> <span data-ttu-id="fc1dd-231">如果需要访问存储在磁盘上的跟踪保护列表，可以在两个位置之一中找到每个列表。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-231">If you need to access the tracking prevention lists that are stored on disk, each may be found in one of two locations.</span></span>  
>
> <span data-ttu-id="fc1dd-232">**基于组件的更新**-从 "信任保护列表" 组件下载的列表</span><span class="sxs-lookup"><span data-stu-id="fc1dd-232">**Component-based updates** - The lists that are downloaded from the "Trust Protection Lists" component</span></span>  
>
> <span data-ttu-id="fc1dd-233">窗口：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-233">Windows:</span></span> `%LOCALAPPDATA%\Microsoft\Edge <OptionalChannelName>\User Data\Trust Protection Lists`  
>
> <span data-ttu-id="fc1dd-234">MacOS</span><span class="sxs-lookup"><span data-stu-id="fc1dd-234">macOS:</span></span> `~/Library/Application Support/Microsoft Edge <OptionalChannelName>/Trust Protection Lists`  
>
> <span data-ttu-id="fc1dd-235">**安装目录**-与 Microsoft Edge 安装程序捆绑的列表。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-235">**Installation directory** - The lists that are bundled with the Microsoft Edge Installer.</span></span>  <span data-ttu-id="fc1dd-236">如果你选择了其他安装目录，你的确切路径可能会有所不同。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-236">If you selected a different installation directory, your exact paths may be different.</span></span>  
>
> <span data-ttu-id="fc1dd-237">窗口：</span><span class="sxs-lookup"><span data-stu-id="fc1dd-237">Windows:</span></span> `%PROGRAMFILES(x86)%\Microsoft\ Edge <OptionalChannelName>\Application<Version>\Trust Protection Lists`  
>
> <span data-ttu-id="fc1dd-238">MacOS</span><span class="sxs-lookup"><span data-stu-id="fc1dd-238">macOS:</span></span> `/Applications/Microsoft Edge.app/Contents/Frameworks/Microsoft Edge Framework.framework/Libraries/Trust Protection Lists`  

## <span data-ttu-id="fc1dd-239">常见问题</span><span class="sxs-lookup"><span data-stu-id="fc1dd-239">Frequently Asked Questions</span></span>  

<span data-ttu-id="fc1dd-240">以下部分包含有关 Microsoft Edge 中的跟踪保护功能的常见问题的解答。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-240">The following section contains answers to frequently asked questions about the tracking prevention feature in Microsoft Edge.</span></span>  

**<span data-ttu-id="fc1dd-241">是否有办法阻止或允许特定的跟踪程序用于调试用途？</span><span class="sxs-lookup"><span data-stu-id="fc1dd-241">Is there a way to block or allow specific trackers for debugging purposes?</span></span>**  

<span data-ttu-id="fc1dd-242">目前，Microsoft Edge 仅公开一个选项，可禁用在指定网站上运行的跟踪保护 enforcements。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-242">Currently, Microsoft Edge only exposes an option to disable tracking prevention enforcements from running on a specified site.</span></span>  <span data-ttu-id="fc1dd-243">通过页面信息弹出窗口或页面访问此选项 `edge://settings/privacy/trackingPreventionExceptions` 。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-243">This option is accessed via the page info flyout or through the `edge://settings/privacy/trackingPreventionExceptions` page.</span></span>  

<span data-ttu-id="fc1dd-244">也就是说，页面上的 "**阻止**" 和 "**允许**" 选项可 `edge://settings/content/cookies` 用于允许或拒绝特定域访问存储，如 cookie 和其他浏览器存储机制。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-244">That being said, the **Block** and **Allow** options on the `edge://settings/content/cookies` page may be used to allow or deny specific domains access to storage such as cookies and other browser storage mechanisms.</span></span>  <span data-ttu-id="fc1dd-245">这对于通过阻止 enforcements 阻止访问特定网站的存储导致的网站问题非常有用。</span><span class="sxs-lookup"><span data-stu-id="fc1dd-245">This is useful for debugging site issues that are caused by tracking prevention enforcements blocking access to storage for a specific site.</span></span>  

<!-- image links -->  

[ImageThreeSettingsTrackingPrevention]: ../media/web-platform/tracking-prevention/tracking-prevention-settings.png  
[ImageBlockedTrackersPageInfoFlyout]: ../media/web-platform/tracking-prevention/page-info-flyout.png  

<!-- links -->  

[MicrosoftEdgeBrowserPrivacyPromise]: https://microsoftedgewelcome.microsoft.com/privacy "隐私-Microsoft Edge"  

[ChromiumDesignDocsSiteEngagement]: https://www.chromium.org/developers/design-documents/site-engagement "网站预订-Chromium 项目"  

[DisconnectMain]: https://disconnect.me "中断"  

[GitHubDisconnectMeTrackingProtection]: https://github.com/disconnectme/disconnect-tracking-protection "disconnectme/断开连接-跟踪-保护 |Github"  
[GitHubDisconnectTrackingProtectionCategories]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/services.json "disconnectme/断开连接-跟踪-保护 |Github"  
[GitHubDisconnectMeTrackingProtectionEntitiesJson]: https://github.com/disconnectme/disconnect-tracking-protection/blob/master/entities.json "实体. json-disconnectme/断开连接-跟踪-保护 |Github"  

[GitHubMsExplainersStorageAccessApi]: https://github.com/MicrosoftEdge/MSEdgeExplainers/blob/master/StorageAccessAPI/explainer.md "存储访问 API Explainer-MSEdgeExplainers/StorageAccessAPI |GitHub"
