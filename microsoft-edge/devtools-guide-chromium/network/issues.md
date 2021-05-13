---
description: 了解如何使用 Microsoft Edge DevTools 的网络面板检测网络问题。
title: 网络问题指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge，web 开发，f12 工具，devtools
ms.openlocfilehash: c99f43872abe04800880c63ee4126bfcdd633edb
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564978"
---
<!-- Copyright Kayce Basques and Jonathan Garbee

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="network-issues-guide"></a><span data-ttu-id="abae9-104">网络问题指南</span><span class="sxs-lookup"><span data-stu-id="abae9-104">Network issues guide</span></span>  

<span data-ttu-id="abae9-105">本指南将演示如何使用 Microsoft Edge DevTools 的网络面板检测网络问题或优化机会。</span><span class="sxs-lookup"><span data-stu-id="abae9-105">This guide shows you how to detect network issues or optimization opportunities in the Network panel of Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="abae9-106">若要了解**网络**工具的基础知识，请导航到[入门][NetworkPerformance]。</span><span class="sxs-lookup"><span data-stu-id="abae9-106">To learn the basics of the **Network** tool, navigate to [Get Started][NetworkPerformance].</span></span>  

## <a name="queued-or-stalled-requests"></a><span data-ttu-id="abae9-107">请求排队或暂停</span><span class="sxs-lookup"><span data-stu-id="abae9-107">Queued or stalled requests</span></span>  

**<span data-ttu-id="abae9-108">症状</span><span class="sxs-lookup"><span data-stu-id="abae9-108">Symptoms</span></span>**  

<span data-ttu-id="abae9-109">六个请求正在同时下载。</span><span class="sxs-lookup"><span data-stu-id="abae9-109">Six requests are downloading simultaneously.</span></span>  <span data-ttu-id="abae9-110">之后，一系列的请求处于排队或暂停状态。</span><span class="sxs-lookup"><span data-stu-id="abae9-110">After that, a series of requests are queued or stalled.</span></span>  <span data-ttu-id="abae9-111">一旦前六个请求中完成一个，队列中的一个请求开始下载。</span><span class="sxs-lookup"><span data-stu-id="abae9-111">Once one of the first six requests finishes, one of the requests in the queue starts.</span></span>  

<span data-ttu-id="abae9-112">在下图的**瀑布图**中，`edge-iconx1024.msft.png` 资产的前六个请求同时开始。</span><span class="sxs-lookup"><span data-stu-id="abae9-112">In the **Waterfall** in the following figure, the first six requests for the `edge-iconx1024.msft.png` asset start simultaneously.</span></span>  <span data-ttu-id="abae9-113">后续请求将保持暂停，直到原来的六个请求中的一个完成。</span><span class="sxs-lookup"><span data-stu-id="abae9-113">The subsequent requests are stalled until one of the original six finishes.</span></span>  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="网络面板中排队或暂停系列的示例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   <span data-ttu-id="abae9-115">**Network** 工具中排队或暂停系列的示例</span><span class="sxs-lookup"><span data-stu-id="abae9-115">An example of a queued or stalled series in the **Network** tool</span></span>  
:::image-end:::  

**<span data-ttu-id="abae9-116">原因</span><span class="sxs-lookup"><span data-stu-id="abae9-116">Causes</span></span>**  

<span data-ttu-id="abae9-117">对单个域提出的请求过多。</span><span class="sxs-lookup"><span data-stu-id="abae9-117">Too many requests are being made on a single domain.</span></span>  <span data-ttu-id="abae9-118">在 HTTP/1.0 或 HTTP/1.1 连接上，Microsoft Edge 允许每个主机最多同步六个 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="abae9-118">On HTTP/1.0 or HTTP/1.1 connections, Microsoft Edge allows a maximum of six simultaneous TCP connections per host.</span></span>  

**<span data-ttu-id="abae9-119">修补程序</span><span class="sxs-lookup"><span data-stu-id="abae9-119">Fixes</span></span>**  

*   <span data-ttu-id="abae9-120">如果必须使用 HTTP/1.0 或 HTTP/1.1，则实施域分片。</span><span class="sxs-lookup"><span data-stu-id="abae9-120">Implement domain sharding if you must use HTTP/1.0 or HTTP/1.1.</span></span>  
*   <span data-ttu-id="abae9-121">使用 HTTP/2。</span><span class="sxs-lookup"><span data-stu-id="abae9-121">Use HTTP/2.</span></span>  <span data-ttu-id="abae9-122">不要将域分片用于 HTTP/2。</span><span class="sxs-lookup"><span data-stu-id="abae9-122">Do not use domain sharding with HTTP/2.</span></span>  
*   <span data-ttu-id="abae9-123">删除或延迟不必要的请求，以便提前下载关键请求。</span><span class="sxs-lookup"><span data-stu-id="abae9-123">Remove or defer unnecessary requests so that critical requests download earlier.</span></span>  
    
## <a name="slow-time-to-first-byte-ttfb"></a><span data-ttu-id="abae9-124">第一字节时间 (TTFB) 缓慢</span><span class="sxs-lookup"><span data-stu-id="abae9-124">Slow Time To First Byte (TTFB)</span></span>  

**<span data-ttu-id="abae9-125">症状</span><span class="sxs-lookup"><span data-stu-id="abae9-125">Symptoms</span></span>**  

<span data-ttu-id="abae9-126">请求等待接收服务器的第一个字节的时间过长。</span><span class="sxs-lookup"><span data-stu-id="abae9-126">A request spends a long time waiting to receive the first byte from the server.</span></span>  

<span data-ttu-id="abae9-127">下图中，**瀑布图**中的绿色条形图表示请求等待了很长时间。</span><span class="sxs-lookup"><span data-stu-id="abae9-127">In the following figure, the long, green bar in the **Waterfall** indicates that the request was waiting a long time.</span></span>  <span data-ttu-id="abae9-128">这是使用限制网速并添加延迟的配置文件进行的模拟。</span><span class="sxs-lookup"><span data-stu-id="abae9-128">This was simulated using a profile to restrict network speed and add a delay.</span></span>  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="第一字节时间缓慢的请求示例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   <span data-ttu-id="abae9-130">第一字节时间缓慢的请求示例</span><span class="sxs-lookup"><span data-stu-id="abae9-130">An example of a request with a slow Time To First Byte</span></span>  
:::image-end:::  

**<span data-ttu-id="abae9-131">原因</span><span class="sxs-lookup"><span data-stu-id="abae9-131">Causes</span></span>**  

*   <span data-ttu-id="abae9-132">客户端和服务器之间的连接速度很慢。</span><span class="sxs-lookup"><span data-stu-id="abae9-132">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="abae9-133">服务器响应缓慢。</span><span class="sxs-lookup"><span data-stu-id="abae9-133">The server is slow to respond.</span></span>  <span data-ttu-id="abae9-134">在本地托管服务器，以确定是连接速度慢还是服务器速度慢。</span><span class="sxs-lookup"><span data-stu-id="abae9-134">Host the server locally to determine if it is the connection or server that is slow.</span></span>  <span data-ttu-id="abae9-135">如果访问本地服务器时，第一字节时间\(TTFB\) 仍然缓慢，则表示是服务器速度慢。</span><span class="sxs-lookup"><span data-stu-id="abae9-135">If you still get a slow Time To First Byte \(TTFB\) when accessing a local server, then the server is slow.</span></span>  
    
**<span data-ttu-id="abae9-136">修补程序</span><span class="sxs-lookup"><span data-stu-id="abae9-136">Fixes</span></span>**  

*   <span data-ttu-id="abae9-137">如果连接速度缓慢，请考虑在 CDN 上托管内容或更改托管提供者。</span><span class="sxs-lookup"><span data-stu-id="abae9-137">If the connection is slow, consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="abae9-138">如果服务器运行缓慢，请考虑优化数据库查询，同时实现缓存或修改服务器配置。</span><span class="sxs-lookup"><span data-stu-id="abae9-138">If the server is slow, consider optimizing database queries, implementing a cache, or modifying your server configuration.</span></span>  
    
## <a name="slow-content-download"></a><span data-ttu-id="abae9-139">内容下载缓慢</span><span class="sxs-lookup"><span data-stu-id="abae9-139">Slow content download</span></span>  

**<span data-ttu-id="abae9-140">症状</span><span class="sxs-lookup"><span data-stu-id="abae9-140">Symptoms</span></span>**  

<span data-ttu-id="abae9-141">下载请求需要很长时间。</span><span class="sxs-lookup"><span data-stu-id="abae9-141">A request takes a long time to download.</span></span>  

<span data-ttu-id="abae9-142">下图中，png 旁**瀑布图**的蓝色条形图表示下载花费了很长时间。</span><span class="sxs-lookup"><span data-stu-id="abae9-142">In the following figure, the long, blue bar in the **Waterfall** next to the png means it took a long time to download.</span></span>  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="下载耗时较长的请求示例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   <span data-ttu-id="abae9-144">下载耗时较长的请求示例</span><span class="sxs-lookup"><span data-stu-id="abae9-144">An example of a request that takes a long time to download</span></span>  
:::image-end:::  

**<span data-ttu-id="abae9-145">原因</span><span class="sxs-lookup"><span data-stu-id="abae9-145">Causes</span></span>**  

*   <span data-ttu-id="abae9-146">客户端和服务器之间的连接速度很慢。</span><span class="sxs-lookup"><span data-stu-id="abae9-146">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="abae9-147">正在下载大量内容。</span><span class="sxs-lookup"><span data-stu-id="abae9-147">A lot of content is being downloaded.</span></span>  
    
**<span data-ttu-id="abae9-148">修补程序</span><span class="sxs-lookup"><span data-stu-id="abae9-148">Fixes</span></span>**  

*   <span data-ttu-id="abae9-149">请考虑在 CDN 上托管内容或更改托管提供者。</span><span class="sxs-lookup"><span data-stu-id="abae9-149">Consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="abae9-150">通过优化请求发送更少的字节。</span><span class="sxs-lookup"><span data-stu-id="abae9-150">Send fewer bytes by optimizing your requests.</span></span>  
    
<!--   ## Contribute knowledge  

Do you have a network issue that should be added to this guide?  

*   Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].  
*   Choose **Send Feedback** \(![Send Feedback](../media/smile-icon.msft.png)\) in the DevTools or select `Alt`+`Shift`+`I` \(Windows, Linux\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.  
*   [Open an issue][WebFundamentalsIssue] on the docs repo.  -->  
    
## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="abae9-151">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="abae9-151">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[NetworkPerformance]: ./index.md "使用 Microsoft Edge DevTools 检测网络活动 | Microsoft Docs"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新问题 - MicrosoftDocs/edge-developer"  

> [!NOTE]
> <span data-ttu-id="abae9-154">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="abae9-154">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="abae9-155">[此处](https://developers.google.com/web/tools/chrome-devtools/network/issues)可以找到原始页面，由 [Kayce Basques][KayceBasques] \（技术写作人员，Chrome DevTools \& Lighthouse\）和 [Jonathan Garbee][JonathanGarbee] \（Web技术的谷歌开发技术专家\）编写。</span><span class="sxs-lookup"><span data-stu-id="abae9-155">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/issues) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\).</span></span>  

[![知识共享许可协议][CCby4Image]][CCA4IL]  
<span data-ttu-id="abae9-157">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="abae9-157">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors#jonathan-garbee
