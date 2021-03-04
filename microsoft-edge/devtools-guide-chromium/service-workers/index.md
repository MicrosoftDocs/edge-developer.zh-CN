---
description: 所有关于服务工作者改进以及如何使用每个改进。
title: 服务工作者改进
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/19/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 服务工作者， PWA
ms.openlocfilehash: 2f32155d1d28d1e65ad29abfe58a414f3e3c6ed7
ms.sourcegitcommit: 661e8def3f27cea381c59ac38954789e736c18f4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "11387279"
---
# <a name="service-worker-improvements"></a><span data-ttu-id="d83a4-104">服务工作者改进</span><span class="sxs-lookup"><span data-stu-id="d83a4-104">Service Worker improvements</span></span>  

<span data-ttu-id="d83a4-105">本文将指导你改进开发人员工具，以使用服务工作者，以及[][MdnServiceWorkerApi]通过每个服务工作者传递的网络请求。</span><span class="sxs-lookup"><span data-stu-id="d83a4-105">This article teaches you about improvements to developer tools for working with [service workers][MdnServiceWorkerApi] and the network requests that pass through each one.</span></span>  <span data-ttu-id="d83a4-106">服务**工作者改进**包括**网络、\*\*\*\*应用程序和\*\*\*\*源**工具。</span><span class="sxs-lookup"><span data-stu-id="d83a4-106">The **service worker improvements** are in the **Network**, **Application**, and **Sources** tools.</span></span>  <span data-ttu-id="d83a4-107">改进可简化以下任务。</span><span class="sxs-lookup"><span data-stu-id="d83a4-107">The improvements simplify the following tasks.</span></span>  

*   <span data-ttu-id="d83a4-108">基于服务工作线程时间线进行调试。</span><span class="sxs-lookup"><span data-stu-id="d83a4-108">Debug based on Service Worker timelines.</span></span>  
    *   <span data-ttu-id="d83a4-109">请求开示和启动持续时间。</span><span class="sxs-lookup"><span data-stu-id="d83a4-109">The start of a request and duration of the bootstrap.</span></span>  
    *   <span data-ttu-id="d83a4-110">更新到服务工作线程注册。</span><span class="sxs-lookup"><span data-stu-id="d83a4-110">Update to Service worker registration.</span></span>  
    *   <span data-ttu-id="d83a4-111">使用提取事件处理程序 [的请求的][MdnFetchEvent] 运行时。</span><span class="sxs-lookup"><span data-stu-id="d83a4-111">The runtime of a request using the [fetch event][MdnFetchEvent] handler.</span></span>  
    *   <span data-ttu-id="d83a4-112">用于加载客户端的所有提取事件的运行时。</span><span class="sxs-lookup"><span data-stu-id="d83a4-112">The runtime of all fetch events for loading a client.</span></span>  
*   <span data-ttu-id="d83a4-113">浏览提取事件处理程序、安装事件处理程序和激活事件处理程序的运行时详细信息。</span><span class="sxs-lookup"><span data-stu-id="d83a4-113">Explore the runtime details of fetch event handlers, install event handlers, and activate event handlers.</span></span>  
*   <span data-ttu-id="d83a4-114">使用页面脚本信息进入和退出提取 [事件处理程序](#sources)。</span><span class="sxs-lookup"><span data-stu-id="d83a4-114">Step into and out of fetch event handler with [page script information](#sources).</span></span>  
    
<span data-ttu-id="d83a4-115">这些体验跨越三个不同的开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="d83a4-115">The experiences span three different developer tools.</span></span>  

1.  <span data-ttu-id="d83a4-116">网络 [工具](#network) 。</span><span class="sxs-lookup"><span data-stu-id="d83a4-116">The [Network](#network) tool.</span></span>  <span data-ttu-id="d83a4-117">选择通过服务工作者运行的网络请求，并访问计时工具中服务 **工作者的相应时间线** 。</span><span class="sxs-lookup"><span data-stu-id="d83a4-117">Choose a network request that runs through a service worker and access the corresponding timeline of the service worker in the **Timing** tool.</span></span>  
1.  <span data-ttu-id="d83a4-118">应用程序 [工具](#application) 。</span><span class="sxs-lookup"><span data-stu-id="d83a4-118">The [Application](#application) tool.</span></span>  <span data-ttu-id="d83a4-119">若要调试服务工作者，请导航到 **"服务工作者"** 工具。</span><span class="sxs-lookup"><span data-stu-id="d83a4-119">To debug the service workers, navigate to the **Service Workers** tool.</span></span>  
1.  <span data-ttu-id="d83a4-120">源 [工具](#sources) 。</span><span class="sxs-lookup"><span data-stu-id="d83a4-120">The [Sources](#sources) tool.</span></span>  <span data-ttu-id="d83a4-121">单步获取事件处理程序时访问页面脚本信息。</span><span class="sxs-lookup"><span data-stu-id="d83a4-121">Access page script information when stepping into fetch event handlers.</span></span>  
    
## <a name="network"></a><span data-ttu-id="d83a4-122">网络</span><span class="sxs-lookup"><span data-stu-id="d83a4-122">Network</span></span>  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="网络工具中的服务工作者时间线" lightbox="../media/sw-network-timeline.msft.png":::
   <span data-ttu-id="d83a4-124">网络视图</span><span class="sxs-lookup"><span data-stu-id="d83a4-124">Network view</span></span>  
:::image-end:::  

<span data-ttu-id="d83a4-125">若要访问网络工具中的服务工作者 **调试功能，** 请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="d83a4-125">To access the service worker debugging features in the **Network** tool, complete one of the following actions.</span></span>  

*   <span data-ttu-id="d83a4-126">直接访问**网络工具。**</span><span class="sxs-lookup"><span data-stu-id="d83a4-126">Access directly in the **Network** tool.</span></span>  
*   <span data-ttu-id="d83a4-127">在应用程序 **工具中** 启动。</span><span class="sxs-lookup"><span data-stu-id="d83a4-127">Started in the **Application** tool.</span></span>  
    
### <a name="request-routing"></a><span data-ttu-id="d83a4-128">请求传送</span><span class="sxs-lookup"><span data-stu-id="d83a4-128">Request routing</span></span>  

<span data-ttu-id="d83a4-129">为了便于可视化请求传送，日程表现在显示服务工作者启动和 `respondWith` 提取事件。</span><span class="sxs-lookup"><span data-stu-id="d83a4-129">To make request routing easier to visualize, timelines now display the service worker start-up and the `respondWith` fetch events.</span></span>  <span data-ttu-id="d83a4-130">若要调试并可视化通过服务工作者传递的网络请求，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="d83a4-130">To debug and visualize a network request that passed through a service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="d83a4-131">选择通过服务工作者发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="d83a4-131">Choose the network request that went through a service worker.</span></span>  
1.  <span data-ttu-id="d83a4-132">打开 **计时** 工具。</span><span class="sxs-lookup"><span data-stu-id="d83a4-132">Open the **Timing** tool.</span></span>  
    
### <a name="fetch-events"></a><span data-ttu-id="d83a4-133">提取事件</span><span class="sxs-lookup"><span data-stu-id="d83a4-133">Fetch events</span></span>  

<span data-ttu-id="d83a4-134">若要了解有关提取事件 `respondWith` More about， choose the dropdown arrow to the left of the `respondWith` .</span><span class="sxs-lookup"><span data-stu-id="d83a4-134">To learn more about the `respondWith` fetch events, choose the dropdown arrow to the left of the `respondWith`.</span></span>  <span data-ttu-id="d83a4-135">若要查找有关原始请求和\*\*\*\* 收到的**响应**的更多详细信息，请使用相应的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="d83a4-135">To find more details about the **Original Request** and **Response Received**, use the corresponding dropdown arrows.</span></span>  

## <a name="application"></a><span data-ttu-id="d83a4-136">应用程序</span><span class="sxs-lookup"><span data-stu-id="d83a4-136">Application</span></span>  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="应用程序视图" lightbox="../media/sw-application-timeline.msft.png":::
   <span data-ttu-id="d83a4-138">应用程序视图</span><span class="sxs-lookup"><span data-stu-id="d83a4-138">Application view</span></span>  
:::image-end:::  

### <a name="service-worker-update-timeline"></a><span data-ttu-id="d83a4-139">服务工作者更新时间线</span><span class="sxs-lookup"><span data-stu-id="d83a4-139">Service worker update timeline</span></span>  

<span data-ttu-id="d83a4-140">Microsoft Edge DevTools 团队在应用程序工具\*\*\*\* 中添加了时间线，以反映服务工作者的更新生命周期。</span><span class="sxs-lookup"><span data-stu-id="d83a4-140">The Microsoft Edge DevTools team added a timeline in the **Application** tool to reflect the update lifecycle of the service worker.</span></span>  <span data-ttu-id="d83a4-141">它显示安装和激活事件。</span><span class="sxs-lookup"><span data-stu-id="d83a4-141">It displays the installation and activation events.</span></span>  <span data-ttu-id="d83a4-142">每个事件都有相应的下拉箭头，可为您提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="d83a4-142">Each of the events has a corresponding dropdown arrow to give you more details.</span></span>  

### <a name="request-routing-and-fetch-events"></a><span data-ttu-id="d83a4-143">请求传送和提取事件</span><span class="sxs-lookup"><span data-stu-id="d83a4-143">Request routing and fetch events</span></span>  

<span data-ttu-id="d83a4-144">现在，可以通过控制台箱中的 **"** 网络"工具访问服务工作者日程表。</span><span class="sxs-lookup"><span data-stu-id="d83a4-144">You may now access the service worker timelines through the **Network** tool in the console drawer.</span></span>  <span data-ttu-id="d83a4-145">该功能可提高性能、最大程度地减少 UI 重复，并创建更全面的调试体验。</span><span class="sxs-lookup"><span data-stu-id="d83a4-145">The feature benefits performance, minimizes UI duplication, and creates a more comprehensive debugging experience.</span></span>  

1.  <span data-ttu-id="d83a4-146">打开正在调试的服务工作者。</span><span class="sxs-lookup"><span data-stu-id="d83a4-146">Open the service worker you are debugging.</span></span>  
1.  <span data-ttu-id="d83a4-147">选择 **"网络** "按钮以打开 [请求路由体验](#network)。</span><span class="sxs-lookup"><span data-stu-id="d83a4-147">Choose the **Network** button to open up the [request routing experience](#network).</span></span>  
1.  <span data-ttu-id="d83a4-148">使用 **respondWith** 下拉列表获取事件请求和响应信息。</span><span class="sxs-lookup"><span data-stu-id="d83a4-148">Use the **respondWith** dropdowns for fetch event request and response information.</span></span>  

<span data-ttu-id="d83a4-149">**网络**工具显示通过正在调试的服务工作者发送的网络请求。</span><span class="sxs-lookup"><span data-stu-id="d83a4-149">The **Network** tool displays the network requests that went through the service worker you are debugging.</span></span>  <span data-ttu-id="d83a4-150">自动筛选器是缩小浏览范围的方法。</span><span class="sxs-lookup"><span data-stu-id="d83a4-150">The automatic filter is a way to narrow down your exploration.</span></span>

## <a name="sources"></a><span data-ttu-id="d83a4-151">源</span><span class="sxs-lookup"><span data-stu-id="d83a4-151">Sources</span></span>  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM 视图" lightbox="../media/sw-sources.msft.png":::
   <span data-ttu-id="d83a4-153">DOM 视图</span><span class="sxs-lookup"><span data-stu-id="d83a4-153">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="d83a4-154">若要查找更多堆栈信息，在提取处理程序中设置一个断点。</span><span class="sxs-lookup"><span data-stu-id="d83a4-154">To find more stack information, set a break point in the fetch handler.</span></span>  <span data-ttu-id="d83a4-155">详细信息将导致在页面脚本中请求资源。</span><span class="sxs-lookup"><span data-stu-id="d83a4-155">The details lead to where the resource is requested in the page script.</span></span>  <span data-ttu-id="d83a4-156">当调试器在提取处理程序内暂停时，组合的堆栈信息将显示在面板右侧。</span><span class="sxs-lookup"><span data-stu-id="d83a4-156">When the debugger pauses inside a fetch handler, a combined stack information is displayed in the panel to the right.</span></span>  <span data-ttu-id="d83a4-157">之后，您可以在堆栈帧中四处移动。</span><span class="sxs-lookup"><span data-stu-id="d83a4-157">After that, you may move around in the stack frames.</span></span>  

### <a name="future-work"></a><span data-ttu-id="d83a4-158">未来工作</span><span class="sxs-lookup"><span data-stu-id="d83a4-158">Future work</span></span>  

<span data-ttu-id="d83a4-159">Microsoft Edge DevTools 团队计划进一步开发缓存详细信息，并正在研究更多方法改善渐进 [式 Web][MdnProgressiveWebApps] 应用程序开发人员的服务工作者调试体验。</span><span class="sxs-lookup"><span data-stu-id="d83a4-159">The Microsoft Edge DevTools team plans to further develop the cache detail and are investigating more ways to improve the service worker debugging experience for [Progressive Web Application][MdnProgressiveWebApps] developers.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="d83a4-160">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="d83a4-160">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps "渐进式 Web (PWA) |MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作 API |MDN"  
