---
title: 网络问题指南
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/30/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 018a6ef89242d55cefaa974641be456f4501c557
ms.sourcegitcommit: 33663cd7838dddee86228dde469a5e9551bddb02
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611803"
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





# <span data-ttu-id="3bd4e-103">网络问题指南</span><span class="sxs-lookup"><span data-stu-id="3bd4e-103">Network Issues Guide</span></span>   




<span data-ttu-id="3bd4e-104">本指南介绍如何在 Microsoft Edge DevTools 的 "网络" 面板中检测网络问题或优化机会。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-104">This guide shows you how to detect network issues or optimization opportunities in the Network panel of Microsoft Edge DevTools.</span></span>  

<span data-ttu-id="3bd4e-105">请参阅[入门][NetworkPerformance]了解网络面板的基础知识。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-105">See [Get Started][NetworkPerformance] to learn the basics of the Network panel.</span></span>  

## <span data-ttu-id="3bd4e-106">已排队或已停止的请求</span><span class="sxs-lookup"><span data-stu-id="3bd4e-106">Queued or stalled requests</span></span>   

### <span data-ttu-id="3bd4e-107">症状</span><span class="sxs-lookup"><span data-stu-id="3bd4e-107">Symptoms</span></span>  

<span data-ttu-id="3bd4e-108">同时下载六个请求。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-108">Six requests are downloading simultaneously.</span></span>  <span data-ttu-id="3bd4e-109">之后，一系列请求将排队或停止。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-109">After that, a series of requests are queued or stalled.</span></span>  <span data-ttu-id="3bd4e-110">当前六个请求中的一个完成时，队列中的请求之一将开始。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-110">Once one of the first six requests finishes, one of the requests in the queue starts.</span></span>  

<span data-ttu-id="3bd4e-111">在[图 1](#figure-1)的**瀑布**图中，资源的前六个请求 `edge-iconx1024.msft.png` 同时开始。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-111">In the **Waterfall** in [Figure 1](#figure-1), the first six requests for the `edge-iconx1024.msft.png` asset start simultaneously.</span></span>  <span data-ttu-id="3bd4e-112">后续请求将停止，直到一个初始六个完成。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-112">The subsequent requests are stalled until one of the original six finishes.</span></span>  

> ##### <span data-ttu-id="3bd4e-113">图 1</span><span class="sxs-lookup"><span data-stu-id="3bd4e-113">Figure 1</span></span>  
> <span data-ttu-id="3bd4e-114">网络面板中排队或停止的系列的示例</span><span class="sxs-lookup"><span data-stu-id="3bd4e-114">An example of a queued or stalled series in the Network panel</span></span>  
> ![网络面板中排队或停止的系列的示例][ImageStalled]  

### <span data-ttu-id="3bd4e-116">原因</span><span class="sxs-lookup"><span data-stu-id="3bd4e-116">Causes</span></span>  

<span data-ttu-id="3bd4e-117">在单个域上发出的请求过多。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-117">Too many requests are being made on a single domain.</span></span>  <span data-ttu-id="3bd4e-118">在 HTTP/1.0 或 HTTP/1.1 连接上，Microsoft Edge 允许每个主机最多同时有6个 TCP 连接。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-118">On HTTP/1.0 or HTTP/1.1 connections, Microsoft Edge allows a maximum of six simultaneous TCP connections per host.</span></span>  

### <span data-ttu-id="3bd4e-119">固定</span><span class="sxs-lookup"><span data-stu-id="3bd4e-119">Fixes</span></span>  

*   <span data-ttu-id="3bd4e-120">如果必须使用 HTTP/1.0 或 HTTP/1.1，则实现域 sharding。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-120">Implement domain sharding if you must use HTTP/1.0 or HTTP/1.1.</span></span>  
*   <span data-ttu-id="3bd4e-121">使用 HTTP/2。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-121">Use HTTP/2.</span></span>  <span data-ttu-id="3bd4e-122">请勿将域 sharding 与 HTTP/2 配合使用。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-122">Do not use domain sharding with HTTP/2.</span></span>  
*   <span data-ttu-id="3bd4e-123">删除或推迟不必要的请求，以便提前下载关键请求。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-123">Remove or defer unnecessary requests so that critical requests download earlier.</span></span>  

## <span data-ttu-id="3bd4e-124">将时间降低到第一个字节（TTFB）</span><span class="sxs-lookup"><span data-stu-id="3bd4e-124">Slow Time To First Byte (TTFB)</span></span>   

### <span data-ttu-id="3bd4e-125">症状</span><span class="sxs-lookup"><span data-stu-id="3bd4e-125">Symptoms</span></span>  

<span data-ttu-id="3bd4e-126">一个请求花费了很长时间等待接收来自服务器的第一个字节。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-126">A request spends a long time waiting to receive the first byte from the server.</span></span>  

<span data-ttu-id="3bd4e-127">在[图 2](#figure-2)中，**瀑布**图中的长绿条指示请求已等待很长时间。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-127">In [Figure 2](#figure-2), the long, green bar in the **Waterfall** indicates that the request was waiting a long time.</span></span>  <span data-ttu-id="3bd4e-128">这是通过使用配置文件来限制网络速度和增加延迟而进行模拟的。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-128">This was simulated using a profile to restrict network speed and add a delay.</span></span>  

> ##### <span data-ttu-id="3bd4e-129">图 2</span><span class="sxs-lookup"><span data-stu-id="3bd4e-129">Figure 2</span></span>  
> <span data-ttu-id="3bd4e-130">在第一个字节时间较慢的请求示例</span><span class="sxs-lookup"><span data-stu-id="3bd4e-130">An example of a request with a slow Time To First Byte</span></span>  
> ![在第一个字节时间较慢的请求示例][ImageSlowTimeToFirstByte]  

### <span data-ttu-id="3bd4e-132">原因</span><span class="sxs-lookup"><span data-stu-id="3bd4e-132">Causes</span></span>  

*   <span data-ttu-id="3bd4e-133">客户端和服务器之间的连接速度较慢。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-133">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="3bd4e-134">服务器响应速度较慢。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-134">The server is slow to respond.</span></span>  <span data-ttu-id="3bd4e-135">在本地托管服务器，以确定它是较慢的连接还是服务器。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-135">Host the server locally to determine if it is the connection or server that is slow.</span></span>  <span data-ttu-id="3bd4e-136">如果您在访问本地服务器时仍遇到较慢的第一个字节 \ （TTFB \），则服务器速度较慢。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-136">If you still get a slow Time To First Byte \(TTFB\) when accessing a local server, then the server is slow.</span></span>  

### <span data-ttu-id="3bd4e-137">固定</span><span class="sxs-lookup"><span data-stu-id="3bd4e-137">Fixes</span></span>  

*   <span data-ttu-id="3bd4e-138">如果连接速度较慢，请考虑在 CDN 上托管你的内容或更改托管提供商。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-138">If the connection is slow, consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="3bd4e-139">如果服务器速度较慢，请考虑优化数据库查询、实现缓存或修改服务器配置。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-139">If the server is slow, consider optimizing database queries, implementing a cache, or modifying your server configuration.</span></span>  

## <span data-ttu-id="3bd4e-140">缓慢的内容下载</span><span class="sxs-lookup"><span data-stu-id="3bd4e-140">Slow content download</span></span>   

### <span data-ttu-id="3bd4e-141">症状</span><span class="sxs-lookup"><span data-stu-id="3bd4e-141">Symptoms</span></span>  

<span data-ttu-id="3bd4e-142">下载请求需要较长时间。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-142">A request takes a long time to download.</span></span>  

<span data-ttu-id="3bd4e-143">在[图 3](#figure-3)中，在 "瀑布" 旁边的 "**瀑布**图" 中，屏幕上的长蓝条表示下载时间较长。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-143">In [Figure 3](#figure-3), the long, blue bar in the **Waterfall** next to the png means it took a long time to download.</span></span>  

> ##### <span data-ttu-id="3bd4e-144">图 3</span><span class="sxs-lookup"><span data-stu-id="3bd4e-144">Figure 3</span></span>  
> <span data-ttu-id="3bd4e-145">需要很长时间才能下载的请求的示例</span><span class="sxs-lookup"><span data-stu-id="3bd4e-145">An example of a request that takes a long time to download</span></span>  
> ![需要很长时间才能下载的请求的示例][ImageSlowContentDownload]  

### <span data-ttu-id="3bd4e-147">原因</span><span class="sxs-lookup"><span data-stu-id="3bd4e-147">Causes</span></span>  

*   <span data-ttu-id="3bd4e-148">客户端和服务器之间的连接速度较慢。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-148">The connection between the client and server is slow.</span></span>  
*   <span data-ttu-id="3bd4e-149">正在下载大量内容。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-149">A lot of content is being downloaded.</span></span>  

### <span data-ttu-id="3bd4e-150">固定</span><span class="sxs-lookup"><span data-stu-id="3bd4e-150">Fixes</span></span>  

*   <span data-ttu-id="3bd4e-151">请考虑在 CDN 上托管你的内容或更改托管提供商。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-151">Consider hosting your content on a CDN or changing hosting providers.</span></span>  
*   <span data-ttu-id="3bd4e-152">通过优化您的请求发送更少的字节。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-152">Send fewer bytes by optimizing your requests.</span></span>  

## <span data-ttu-id="3bd4e-153">参与知识</span><span class="sxs-lookup"><span data-stu-id="3bd4e-153">Contribute knowledge</span></span>  

<span data-ttu-id="3bd4e-154">是否有网络问题应添加到本指南？</span><span class="sxs-lookup"><span data-stu-id="3bd4e-154">Do you have a network issue that should be added to this guide?</span></span>  

*   <span data-ttu-id="3bd4e-155">向[@EdgeDevTools][MicrosoftEdgeTweet]发送 tweet。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-155">Send a tweet to [@EdgeDevTools][MicrosoftEdgeTweet].</span></span>  
*   <span data-ttu-id="3bd4e-156">选择 "**发送反馈** ![ ][ImageSendFeedbackIcon] " 在 DevTools 中发送反馈，或按 `Alt` + `Shift` + `I` \ （Windows \）或 `Option` + `Shift` + `I` \ （macOS \）提供反馈或功能请求。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-156">Select **Send Feedback** ![Send Feedback][ImageSendFeedbackIcon] in the DevTools or press `Alt`+`Shift`+`I` \(Windows\) or `Option`+`Shift`+`I` \(macOS\) to provide feedback or feature requests.</span></span>  
*   <span data-ttu-id="3bd4e-157">在 "文档" 存储库中[打开一个问题][WebFundamentalsIssue]。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-157">[Open an issue][WebFundamentalsIssue] on the docs repo.</span></span>  

<!--   -->  



<!-- image links -->  

[ImageSendFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/smile-icon.msft.png  

[ImageStalled]: /microsoft-edge/devtools-guide-chromium/media/network-network-disabled-cache-resources-queue.msft.png "图1：网络面板中已排队或停止使用的系列的示例"  
[ImageSlowTimeToFirstByte]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-using-dial-up-profile.msft.png "图2：较慢时间到第一个字节的请求示例"  
[ImageSlowContentDownload]: /microsoft-edge/devtools-guide-chromium/media/network-network-resources-edge-devtools.msft.png "图3：下载需要很长时间的请求的示例"  

<!-- links -->  

[NetworkPerformance]: /microsoft-edge/devtools-guide-chromium/network/index "检查 Microsoft Edge DevTools 中的网络活动"  

[MicrosoftEdgeTweet]: https://twitter.com/intent/tweet?text=@EdgeDevTools%20[Network%20Issues%20Guide%20Suggestion]  

[WebFundamentalsIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Network%20Issues%20Guide%20Suggestion%5D "新问题-MicrosoftDocs/edge-开发人员"  

> [!NOTE]
> <span data-ttu-id="3bd4e-163">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-163">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="3bd4e-164">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/network/issues)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）和[Jonathan Garbee][JonathanGarbee] \ （Google Developer for Web 技术）创作。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-164">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/network/issues) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Jonathan Garbee][JonathanGarbee] \(Google Developer Expert for Web Technology\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="3bd4e-166">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="3bd4e-166">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[JonathanGarbee]: https://developers.google.com/web/resources/contributors/jonathangarbee
