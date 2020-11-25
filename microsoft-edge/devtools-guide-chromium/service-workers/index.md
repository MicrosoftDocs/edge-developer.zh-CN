---
description: 所有关于服务工作人员的改进以及如何使用每一个。
title: 服务工作人员改进
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、服务工作人员、PWA
ms.openlocfilehash: 4e1b43235ccd7b108d2aadd1c803aa3276fa1265
ms.sourcegitcommit: 080759f68a0a158f10dc20d20c14e222ace1be84
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2020
ms.locfileid: "11190024"
---
# <span data-ttu-id="95c73-104">服务工作人员改进</span><span class="sxs-lookup"><span data-stu-id="95c73-104">Service Worker improvements</span></span>  

<span data-ttu-id="95c73-105">本文介绍对 [服务工作人员][MdnServiceWorkerApi] 的改进，以及传递每个服务工作请求的网络请求。</span><span class="sxs-lookup"><span data-stu-id="95c73-105">This article teaches you about improvements to [service workers][MdnServiceWorkerApi] and the network requests that pass through each one.</span></span>  <span data-ttu-id="95c73-106">**服务工作人员改进**位于 "**网络**"、"**应用程序**" 和 "**源**" 工具中。</span><span class="sxs-lookup"><span data-stu-id="95c73-106">The **service worker improvements** are in the **Network**, **Application**, and **Sources** tools.</span></span>  <span data-ttu-id="95c73-107">改进包括以下任务。</span><span class="sxs-lookup"><span data-stu-id="95c73-107">The improvements include the following tasks.</span></span>  

*   <span data-ttu-id="95c73-108">基于服务工作时间日程表进行调试。</span><span class="sxs-lookup"><span data-stu-id="95c73-108">Debug based on Service Worker timelines.</span></span>  
    *   <span data-ttu-id="95c73-109">请求的开始时间和引导的持续时间。</span><span class="sxs-lookup"><span data-stu-id="95c73-109">The start of a request and duration of the bootstrap.</span></span>  
    *   <span data-ttu-id="95c73-110">更新到服务工作人员注册。</span><span class="sxs-lookup"><span data-stu-id="95c73-110">Update to Service worker registration.</span></span>  
    *   <span data-ttu-id="95c73-111">使用 [fetch 事件][MdnFetchEvent] 处理程序的请求的运行时。</span><span class="sxs-lookup"><span data-stu-id="95c73-111">The runtime of a request using the [fetch event][MdnFetchEvent] handler.</span></span>  
    *   <span data-ttu-id="95c73-112">用于加载客户端的所有获取事件的运行时。</span><span class="sxs-lookup"><span data-stu-id="95c73-112">The runtime of all fetch events for loading a client.</span></span>  
*   <span data-ttu-id="95c73-113">了解提取事件处理程序、安装事件处理程序和激活事件处理程序的运行时详细信息。</span><span class="sxs-lookup"><span data-stu-id="95c73-113">Explore the runtime details of fetch event handlers, install event handlers, and activate event handlers.</span></span>  
*   <span data-ttu-id="95c73-114">通过 [页面脚本信息](#sources)单步执行和退出获取事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="95c73-114">Step into and out of fetch event handler with [page script information](#sources).</span></span>  

<span data-ttu-id="95c73-115">经验涉及三个不同的开发人员工具。</span><span class="sxs-lookup"><span data-stu-id="95c73-115">The experiences span three different developer tools.</span></span>  

1.  <span data-ttu-id="95c73-116">" [网络](#network) " 工具。</span><span class="sxs-lookup"><span data-stu-id="95c73-116">The [Network](#network) tool.</span></span>  <span data-ttu-id="95c73-117">选择通过服务工作人员运行的网络请求，并在 **计时** 工具中访问服务工作人员的相应时间线。</span><span class="sxs-lookup"><span data-stu-id="95c73-117">Choose a network request that runs through a service worker and access the corresponding timeline of the service worker in the **Timing** tool.</span></span>  
1.  <span data-ttu-id="95c73-118">[应用程序](#application)工具。</span><span class="sxs-lookup"><span data-stu-id="95c73-118">The [Application](#application) tool.</span></span>  <span data-ttu-id="95c73-119">若要调试服务工作人员，请导航到 " **服务工作人员** " 工具。</span><span class="sxs-lookup"><span data-stu-id="95c73-119">To debug the service workers, navigate to the **Service Workers** tool.</span></span>  
1.  <span data-ttu-id="95c73-120">" [源](#sources) " 工具。</span><span class="sxs-lookup"><span data-stu-id="95c73-120">The [Sources](#sources) tool.</span></span>  <span data-ttu-id="95c73-121">在单步执行提取事件处理程序时访问页面脚本信息。</span><span class="sxs-lookup"><span data-stu-id="95c73-121">Access page script information when stepping into fetch event handlers.</span></span>  

## <span data-ttu-id="95c73-122">网络</span><span class="sxs-lookup"><span data-stu-id="95c73-122">Network</span></span>  

:::image type="complex" source="../media/sw-network-timeline.msft.png" alt-text="网络工具中的服务工作时间线" lightbox="../media/sw-network-timeline.msft.png":::
   <span data-ttu-id="95c73-124">网络视图</span><span class="sxs-lookup"><span data-stu-id="95c73-124">Network view</span></span>  
:::image-end:::  

<span data-ttu-id="95c73-125">若要访问 **网络** 工具中的服务工作人员调试功能，请完成以下操作之一。</span><span class="sxs-lookup"><span data-stu-id="95c73-125">To access the service worker debugging features in the **Network** tool, complete one of the following actions.</span></span>  

*   <span data-ttu-id="95c73-126">直接在 **网络** 工具中访问。</span><span class="sxs-lookup"><span data-stu-id="95c73-126">Access directly in the **Network** tool.</span></span>  
*   <span data-ttu-id="95c73-127">在 **应用程序** 工具中启动。</span><span class="sxs-lookup"><span data-stu-id="95c73-127">Started in the **Application** tool.</span></span>  
    
### <span data-ttu-id="95c73-128">请求路由</span><span class="sxs-lookup"><span data-stu-id="95c73-128">Request routing</span></span>  

<span data-ttu-id="95c73-129">为了使请求路由更易于可视化，日程表现在显示服务工作人员启动和 `respondWith` 获取事件。</span><span class="sxs-lookup"><span data-stu-id="95c73-129">To make request routing easier to visualize, timelines now display the service worker start-up and the `respondWith` fetch events.</span></span>  <span data-ttu-id="95c73-130">若要调试和可视化通过服务工作人员传递的网络请求，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="95c73-130">To debug and visualize a network request that passed through a service worker, complete the following actions.</span></span>  

1.  <span data-ttu-id="95c73-131">选择通过服务工作人员进行的网络请求。</span><span class="sxs-lookup"><span data-stu-id="95c73-131">Choose the network request that went through a service worker.</span></span>  
1.  <span data-ttu-id="95c73-132">打开 **计时** 工具。</span><span class="sxs-lookup"><span data-stu-id="95c73-132">Open the **Timing** tool.</span></span>  
    
### <span data-ttu-id="95c73-133">获取事件</span><span class="sxs-lookup"><span data-stu-id="95c73-133">Fetch events</span></span>  

<span data-ttu-id="95c73-134">若要了解有关提取事件的详细信息 `respondWith` ，请选择左侧的下拉箭头 `respondWith` 。</span><span class="sxs-lookup"><span data-stu-id="95c73-134">To learn more about the `respondWith` fetch events, choose the dropdown arrow to the left of the `respondWith`.</span></span>  <span data-ttu-id="95c73-135">若要查找有关**已收到**的**原始请求**和响应的更多详细信息，请使用相应的下拉箭头。</span><span class="sxs-lookup"><span data-stu-id="95c73-135">To find more details about the **Original Request** and **Response Received**, use the corresponding dropdown arrows.</span></span>  

## <span data-ttu-id="95c73-136">应用程序</span><span class="sxs-lookup"><span data-stu-id="95c73-136">Application</span></span>  

:::image type="complex" source="../media/sw-application-timeline.msft.png" alt-text="应用程序视图" lightbox="../media/sw-application-timeline.msft.png":::
   <span data-ttu-id="95c73-138">应用程序视图</span><span class="sxs-lookup"><span data-stu-id="95c73-138">Application view</span></span>  
:::image-end:::  

### <span data-ttu-id="95c73-139">服务工作人员更新日程表</span><span class="sxs-lookup"><span data-stu-id="95c73-139">Service worker update timeline</span></span>  

<span data-ttu-id="95c73-140">Microsoft Edge DevTools 团队在 **应用程序** 工具中添加了一个日程表，以反映服务工作人员的更新生命周期。</span><span class="sxs-lookup"><span data-stu-id="95c73-140">The Microsoft Edge DevTools team added a timeline in the **Application** tool to reflect the update lifecycle of the service worker.</span></span>  <span data-ttu-id="95c73-141">它显示安装和激活事件。</span><span class="sxs-lookup"><span data-stu-id="95c73-141">It displays the installation and activation events.</span></span>  <span data-ttu-id="95c73-142">每个事件都有一个对应的下拉箭头，可提供更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="95c73-142">Each of the events has a corresponding dropdown arrow to give you more details.</span></span>  

### <span data-ttu-id="95c73-143">请求路由和提取事件</span><span class="sxs-lookup"><span data-stu-id="95c73-143">Request routing and fetch events</span></span>  

<span data-ttu-id="95c73-144">您现在可以通过 console 抽屉中的 " **网络** " 工具访问服务工作人员日程表。</span><span class="sxs-lookup"><span data-stu-id="95c73-144">You may now access the service worker timelines through the **Network** tool in the console drawer.</span></span>  <span data-ttu-id="95c73-145">该功能可提高性能、最小化 UI 复制，并创建更全面的调试体验。</span><span class="sxs-lookup"><span data-stu-id="95c73-145">The feature benefits performance, minimizes UI duplication, and creates a more comprehensive debugging experience.</span></span>  

1.  <span data-ttu-id="95c73-146">打开正在调试的服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="95c73-146">Open the service worker you are debugging.</span></span>  
1.  <span data-ttu-id="95c73-147">选择 " **网络** " 按钮以打开 " [请求路由体验](#network)"。</span><span class="sxs-lookup"><span data-stu-id="95c73-147">Choose the **Network** button to open up the [request routing experience](#network).</span></span>  
1.  <span data-ttu-id="95c73-148">使用 **respondWith** 下拉菜单获取获取事件请求和响应信息。</span><span class="sxs-lookup"><span data-stu-id="95c73-148">Use the **respondWith** dropdowns for fetch event request and response information.</span></span>  

<span data-ttu-id="95c73-149">**网络**工具显示通过正在调试的服务工作人员进行的网络请求。</span><span class="sxs-lookup"><span data-stu-id="95c73-149">The **Network** tool displays the network requests that went through the service worker you are debugging.</span></span>  <span data-ttu-id="95c73-150">自动筛选器是缩小您的勘探范围的一种方法。</span><span class="sxs-lookup"><span data-stu-id="95c73-150">The automatic filter is a way to narrow down your exploration.</span></span>

## <span data-ttu-id="95c73-151">源</span><span class="sxs-lookup"><span data-stu-id="95c73-151">Sources</span></span>  

:::image type="complex" source="../media/sw-sources.msft.png" alt-text="DOM 视图" lightbox="../media/sw-sources.msft.png":::
   <span data-ttu-id="95c73-153">DOM 视图</span><span class="sxs-lookup"><span data-stu-id="95c73-153">DOM view</span></span>  
:::image-end:::  

<span data-ttu-id="95c73-154">若要查找更多堆栈信息，请在 fetch 处理程序中设置断点。</span><span class="sxs-lookup"><span data-stu-id="95c73-154">To find more stack information, set a break point in the fetch handler.</span></span>  <span data-ttu-id="95c73-155">详细信息将导致在页面脚本中请求资源的位置。</span><span class="sxs-lookup"><span data-stu-id="95c73-155">The details lead to where the resource is requested in the page script.</span></span>  <span data-ttu-id="95c73-156">当调试器在提取处理程序中暂停时，将在右侧的面板中显示组合的堆栈信息。</span><span class="sxs-lookup"><span data-stu-id="95c73-156">When the debugger pauses inside a fetch handler, a combined stack information is displayed in the panel to the right.</span></span>  <span data-ttu-id="95c73-157">在此之后，你可以在堆栈帧中四处移动。</span><span class="sxs-lookup"><span data-stu-id="95c73-157">After that, you may move around in the stack frames.</span></span>  

### <span data-ttu-id="95c73-158">未来工作</span><span class="sxs-lookup"><span data-stu-id="95c73-158">Future work</span></span>  

<span data-ttu-id="95c73-159">Microsoft Edge DevTools 团队计划可进一步开发缓存详细信息，并正在研究更多提高 [Web 应用程序][MdnProgressiveWebApps] 开发人员的服务工作人员调试体验的方法。</span><span class="sxs-lookup"><span data-stu-id="95c73-159">The Microsoft Edge DevTools team plans to further develop the cache detail and are investigating more ways to improve the service worker debugging experience for [Progressive Web Application][MdnProgressiveWebApps] developers.</span></span>  

## <span data-ttu-id="95c73-160">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="95c73-160">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[MdnFetchEvent]: https://developer.mozilla.org/docs/Web/API/FetchEvent "FetchEvent |MDN"  
[MdnProgressiveWebApps]: https://developer.mozilla.org/docs/Web/Progressive_web_apps " (PWAs) | 的渐进式 web 应用MDN"  
[MdnServiceWorkerApi]: https://developer.mozilla.org/docs/Web/API/Service_Worker_API "服务工作者 API |MDN"  
