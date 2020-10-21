---
description: 了解如何在 Microsoft Edge DevTools 的网络面板中检测网络问题。
title: 网络问题指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 4713dc252d428abbf5b60ee5f74a7316a102dab6
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125375"
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

# <span data-ttu-id="fc03c-104">网络问题指南</span><span class="sxs-lookup"><span data-stu-id="fc03c-104">Network issues guide</span></span>  

<span data-ttu-id="fc03c-105">本指南介绍如何在 Microsoft Edge DevTools 的 "网络" 面板中检测网络问题或优化机会。</span><span class="sxs-lookup"><span data-stu-id="fc03c-105">This guide shows you how to detect network issues or optimization opportunities in the Network panel of Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="fc03c-106">请参阅 [入门][NetworkPerformance] 了解 **网络** 面板的基础知识。</span><span class="sxs-lookup"><span data-stu-id="fc03c-106">See [Get Started][NetworkPerformance] to learn the basics of the **Network** panel.</span></span>  

## <span data-ttu-id="fc03c-107">已排队或已停止的请求</span><span class="sxs-lookup"><span data-stu-id="fc03c-107">Queued or stalled requests</span></span>  

**<span data-ttu-id="fc03c-108">症状</span><span class="sxs-lookup"><span data-stu-id="fc03c-108">Symptoms</span></span>**  

<span data-ttu-id="fc03c-109">同时下载六个请求。</span><span class="sxs-lookup"><span data-stu-id="fc03c-109">Six requests are downloading simultaneously.</span></span>  <span data-ttu-id="fc03c-110">之后，一系列请求将排队或停止。</span><span class="sxs-lookup"><span data-stu-id="fc03c-110">After that, a series of requests are queued or stalled.</span></span>  <span data-ttu-id="fc03c-111">当前六个请求中的一个完成时，队列中的请求之一将开始。</span><span class="sxs-lookup"><span data-stu-id="fc03c-111">Once one of the first six requests finishes, one of the requests in the queue starts.</span></span>  

<span data-ttu-id="fc03c-112">在下图中的 **瀑布** 图中，资源的前六个请求 `edge-iconx1024.msft.png` 同时开始。</span><span class="sxs-lookup"><span data-stu-id="fc03c-112">In the **Waterfall** in the following figure, the first six requests for the `edge-iconx1024.msft.png` asset start simultaneously.</span></span>  <span data-ttu-id="fc03c-113">后续请求将停止，直到一个初始六个完成。</span><span class="sxs-lookup"><span data-stu-id="fc03c-113">The subsequent requests are stalled until one of the original six finishes.</span></span>  

:::image type="complex" source="../media/network-network-disabled-cache-resources-queue.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-disabled-cache-resources-queue.msft.png":::
   <span data-ttu-id="fc03c-115">**网络**面板中排队或停止的系列的示例</span><span class="sxs-lookup"><span data-stu-id="fc03c-115">An example of a queued or stalled series in the **Network** panel</span></span>  
:::image-end:::  

**<span data-ttu-id="fc03c-116">原因</span><span class="sxs-lookup"><span data-stu-id="fc03c-116">Causes</span></span>**  

<span data-ttu-id="fc03c-117">在单个域上发出的请求过多。</span><span class="sxs-lookup"><span data-stu-id="fc03c-117">Too many requests are being made on a single domain.</span></span>  <span data-ttu-id="fc03c-118">在 HTTP/1.0 或 HTTP/1.1 连接上，Microsoft Edge 允许每个主机最多同时有6个 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="fc03c-118">On HTTP/1.0 or HTTP/1.1 connections, Microsoft Edge allows a maximum of six simultaneous TCP connections per host.</span></span>  

**<span data-ttu-id="fc03c-119">固定</span><span class="sxs-lookup"><span data-stu-id="fc03c-119">Fixes</span></span>**  

*   <span data-ttu-id="fc03c-120">如果必须使用 HTTP/1.0 或 HTTP/1.1，则实现域 sharding。</span><span class="sxs-lookup"><span data-stu-id="fc03c-120">Implement domain sharding if you must use HTTP/1.0 or HTTP/1.1.</span></span>  
*   <span data-ttu-id="fc03c-121">使用 HTTP/2。</span><span class="sxs-lookup"><span data-stu-id="fc03c-121">Use HTTP/2.</span></span>  <span data-ttu-id="fc03c-122">请勿将域 sharding 与 HTTP/2 配合使用。</span><span class="sxs-lookup"><span data-stu-id="fc03c-122">Do not use domain sharding with HTTP/2.</span></span>  
*   <span data-ttu-id="fc03c-123">删除或推迟不必要的请求，以便提前下载关键请求。</span><span class="sxs-lookup"><span data-stu-id="fc03c-123">Remove or defer unnecessary requests so that critical requests download earlier.</span></span>  
    
## <span data-ttu-id="fc03c-124">在 TTFB) 的第一字节 (时间较慢</span><span class="sxs-lookup"><span data-stu-id="fc03c-124">Slow Time To First Byte (TTFB)</span></span>  

**<span data-ttu-id="fc03c-125">症状</span><span class="sxs-lookup"><span data-stu-id="fc03c-125">Symptoms</span></span>**  

<span data-ttu-id="fc03c-126">一个请求花费了很长时间等待接收来自服务器的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="fc03c-126">A request spends a long time waiting to receive the first byte from the server.</span></span>  

<span data-ttu-id="fc03c-127">在下图中， **瀑布** 图中的长绿条指示请求已等待很长时间。</span><span class="sxs-lookup"><span data-stu-id="fc03c-127">In the following figure, the long, green bar in the **Waterfall** indicates that the request was waiting a long time.</span></span>  <span data-ttu-id="fc03c-128">这是通过使用配置文件来限制网络速度和增加延迟而进行模拟的。</span><span class="sxs-lookup"><span data-stu-id="fc03c-128">This was simulated using a profile to restrict network speed and add a delay.</span></span>  

:::image type="complex" source="../media/network-network-resources-using-dial-up-profile.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-resources-using-dial-up-profile.msft.png":::
   <span data-ttu-id="fc03c-130">在第一个字节时间较慢的请求示例</span><span class="sxs-lookup"><span data-stu-id="fc03c-130">An example of a request with a slow Time To First Byte</span></span>  
:::image-end:::  

**<span data-ttu-id="fc03c-131">原因</span><span class="sxs-lookup"><span data-stu-id="fc03c-131">Causes</span></span>**  

*   <span data-ttu-id="fc03c-132">客户端和服务器之间的连接速度较慢。</span><span class="sxs-lookup"><span data-stu-id="fc03c-132">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="fc03c-133">服务器响应速度较慢。</span><span class="sxs-lookup"><span data-stu-id="fc03c-133">The server is slow to respond.</span></span>  <span data-ttu-id="fc03c-134">在本地托管服务器，以确定它是较慢的连接还是服务器。</span><span class="sxs-lookup"><span data-stu-id="fc03c-134">Host the server locally to determine if it is the connection or server that is slow.</span></span>  <span data-ttu-id="fc03c-135">如果您在访问本地服务器时仍有较慢的第一个字节 \ (TTFB \ ) ，则服务器速度较慢。</span><span class="sxs-lookup"><span data-stu-id="fc03c-135">If you still get a slow Time To First Byte \(TTFB\) when accessing a local server, then the server is slow.</span></span>  
    
**<span data-ttu-id="fc03c-136">固定</span><span class="sxs-lookup"><span data-stu-id="fc03c-136">Fixes</span></span>**  

*   <span data-ttu-id="fc03c-137">如果连接速度较慢，请考虑在 CDN 上托管你的内容或更改托管提供商。</span><span class="sxs-lookup"><span data-stu-id="fc03c-137">If the connection is slow, consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="fc03c-138">如果服务器速度较慢，请考虑优化数据库查询、实现缓存或修改服务器配置。</span><span class="sxs-lookup"><span data-stu-id="fc03c-138">If the server is slow, consider optimizing database queries, implementing a cache, or modifying your server configuration.</span></span>  
    
## <span data-ttu-id="fc03c-139">缓慢的内容下载</span><span class="sxs-lookup"><span data-stu-id="fc03c-139">Slow content download</span></span>  

**<span data-ttu-id="fc03c-140">症状</span><span class="sxs-lookup"><span data-stu-id="fc03c-140">Symptoms</span></span>**  

<span data-ttu-id="fc03c-141">下载请求需要较长时间。</span><span class="sxs-lookup"><span data-stu-id="fc03c-141">A request takes a long time to download.</span></span>  

<span data-ttu-id="fc03c-142">在下图中，在 "瀑布" 旁边的 " **瀑布** 图" 中，长的蓝条表示下载时间较长。</span><span class="sxs-lookup"><span data-stu-id="fc03c-142">In the following figure, the long, blue bar in the **Waterfall** next to the png means it took a long time to download.</span></span>  

:::image type="complex" source="../media/network-network-resources-edge-devtools.msft.png" alt-text="网络面板中排队或停止的系列的示例" lightbox="../media/network-network-resources-edge-devtools.msft.png":::
   <span data-ttu-id="fc03c-144">需要很长时间才能下载的请求的示例</span><span class="sxs-lookup"><span data-stu-id="fc03c-144">An example of a request that takes a long time to download</span></span>  
:::image-end:::  

**<span data-ttu-id="fc03c-145">原因</span><span class="sxs-lookup"><span data-stu-id="fc03c-145">Causes</span></span>**  

*   <span data-ttu-id="fc03c-146">客户端和服务器之间的连接速度较慢。</span><span class="sxs-lookup"><span data-stu-id="fc03c-146">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="fc03c-147">正在下载大量内容。</span><span class="sxs-lookup"><span data-stu-id="fc03c-147">A lot of content is being downloaded.</span></span>  
    
**<span data-ttu-id="fc03c-148">固定</span><span class="sxs-lookup"><span data-stu-id="fc03c-148">Fixes</span></span>**  

*   <span data-ttu-id="fc03c-149">请考虑在 CDN 上托管你的内容或更改托管提供商。</span><span class="sxs-lookup"><span data-stu-id="fc03c-149">Consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="fc03c-150">通过优化您的请求发送更少的字节。</span><span class="sxs-lookup"><span data-stu-id="fc03c-150">Send fewer bytes by optimizing your requests.</span></span>  
    
<!--   ## Contribute knowledge  

Do you have a network issue that should be added to this guide?  

*   Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].  
*   Choose **Send Feedback** \(![Send Feedback][ImageSendFeedbackIcon]\) in the DevTools or select `Alt`+`Shift`+`I` \(Windows, Linux\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.  
*   [Open an issue][WebFundamentalsIssue] on the docs repo.  -->  
    
## <span data-ttu-id="fc03c-151">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="fc03c-151">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageSendFeedbackIcon]: ../media/smile-icon.msft.png  

<!-- links -->  

[NetworkPerformance]: ./index.md "检查 Microsoft Edge DevTools 中的网络活动 |Microsoft 文档"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新问题 - MicrosoftDocs/edge-developer"  

> [!NOTE]
> <span data-ttu-id="fc03c-154">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="fc03c-154">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="fc03c-155">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/network/issues) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Jonathan Garbee][JonathanGarbee] \ (Google Developer for Web ) 技术。</span><span class="sxs-lookup"><span data-stu-id="fc03c-155">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/issues) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="fc03c-157">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="fc03c-157">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
