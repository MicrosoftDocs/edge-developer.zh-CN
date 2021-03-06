---
description: 本指南概述了 EdgeHTML 16 中包含的开发人员功能和标准。
title: EdgeHTML 16 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: article
ms.prod: microsoft-edge
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.openlocfilehash: e6ec2ec4a3152e9dfe73938784968fe3403d99cf
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11399195"
---
# <a name="whats-new-in-edgehtml-16"></a><span data-ttu-id="8f3a1-104">EdgeHTML 16 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="8f3a1-104">What's new in EdgeHTML 16</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="8f3a1-105">下面是 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web 平台中作为 [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \ (10/2017 内部版本 16299\) 的一部分提供的新功能和更新功能的列表。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, Build 16299\).</span></span>  <span data-ttu-id="8f3a1-106">有关特定 Windows Insider Preview 内部版本的变化，请参阅 [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="8f3a1-107">下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md)</span><span class="sxs-lookup"><span data-stu-id="8f3a1-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md).</span></span>  

## <a name="new-and-updated-features"></a><span data-ttu-id="8f3a1-108">新增和更新的功能</span><span class="sxs-lookup"><span data-stu-id="8f3a1-108">New and updated features</span></span>  

### <a name="css-grid-layout"></a><span data-ttu-id="8f3a1-109">CSS 网格布局</span><span class="sxs-lookup"><span data-stu-id="8f3a1-109">CSS Grid Layout</span></span>  

<span data-ttu-id="8f3a1-110">Microsoft Edge 现在支持 CSS 网格布局的无 [前缀实现](https://www.w3.org/TR/css-grid-1)。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-110">Microsoft Edge now supports the un-prefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1).</span></span>  <span data-ttu-id="8f3a1-111">[网格布局](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 定义基于网格的二维布局系统，与使用浮点或脚本定位时所实现的布局更流畅。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span></span>  <span data-ttu-id="8f3a1-112">下面的示例使用 CSS 网格布局为基本网页创建结构。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span></span>  

<iframe height='303' scrolling='no' title='<span data-ttu-id="8f3a1-113">CSS 网格布局</span><span class="sxs-lookup"><span data-stu-id="8f3a1-113">CSS Grid Layout</span></span>' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="8f3a1-114">请参阅 CodePen 上的 <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> </a> MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) </a> <a href='https://codepen.io'> 的笔 CSS 网格布局 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

### <a name="css-object-fit-and-object-position"></a><span data-ttu-id="8f3a1-115">CSS 对象适合和对象位置</span><span class="sxs-lookup"><span data-stu-id="8f3a1-115">CSS object-fit and object-position</span></span>  

<span data-ttu-id="8f3a1-116">EdgeHTML 16 引入了对 CSS 属性和 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 的支持。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span></span>  <span data-ttu-id="8f3a1-117">这些属性控制替换内容在内容框中的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-117">These properties control the position and size of replaced content within the content box.</span></span>  

### <a name="developer-tools"></a><span data-ttu-id="8f3a1-118">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="8f3a1-118">Developer Tools</span></span>  

<span data-ttu-id="8f3a1-119">此版本我们启动了一项重要的 Microsoft Edge DevTools 重构工作，以提高稳定性和性能，还添加了一组你现在可以在 [Windows](https://insider.windows.com) 预览体验成员版本上开始使用的新功能。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com) builds.</span></span>  <span data-ttu-id="8f3a1-120">查看 [Microsoft Edge DevTools 指南](../whats-new.md) ，详细了解更改了哪些功能！</span><span class="sxs-lookup"><span data-stu-id="8f3a1-120">Check out the [Microsoft Edge DevTools guide](../whats-new.md) for more on what's changed!</span></span>  

### <a name="javascript"></a><span data-ttu-id="8f3a1-121">JavaScript</span><span class="sxs-lookup"><span data-stu-id="8f3a1-121">JavaScript</span></span>  

<span data-ttu-id="8f3a1-122">[EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/31)通过扩展 Chakra 引擎延迟/重新延迟函数、使用多态内嵌缓存以及使用块优化函数的功能，在早期版本的 Javascript 性能优化的基础上构建。 `try` / `finally`</span><span class="sxs-lookup"><span data-stu-id="8f3a1-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with `try`/`finally` blocks.</span></span>  

<span data-ttu-id="8f3a1-123">此外，EdgeHTML 15 中首次预览的功能现在稳定且默认启用：</span><span class="sxs-lookup"><span data-stu-id="8f3a1-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span></span>  

#### <a name="new-features"></a><span data-ttu-id="8f3a1-124">新功能</span><span class="sxs-lookup"><span data-stu-id="8f3a1-124">New features</span></span>  

<span data-ttu-id="8f3a1-125">默认启用</span><span class="sxs-lookup"><span data-stu-id="8f3a1-125">On by default</span></span>  

*   <span data-ttu-id="8f3a1-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \ ([演示](https://webassembly.org/demo)\) </span><span class="sxs-lookup"><span data-stu-id="8f3a1-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="8f3a1-127">共享内存和原子</span><span class="sxs-lookup"><span data-stu-id="8f3a1-127">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### <a name="payment-request-api"></a><span data-ttu-id="8f3a1-128">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="8f3a1-128">Payment Request API</span></span>  

<span data-ttu-id="8f3a1-129">付款请求 [API](../windows-integration/payment-request-api.md) 是一个开放的跨浏览器标准，它使浏览器能够充当商家、消费者和付款方式 \ (（如消费者存储在云中的信用卡\) ）之间的中介。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-129">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="8f3a1-130">EdgeHTML 16 中的 API 已更新，以匹配最新的 W3C [付款请求 API](https://w3c.github.io/payment-request) 规范。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-130">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request) specification.</span></span>  <span data-ttu-id="8f3a1-131">这包括：</span><span class="sxs-lookup"><span data-stu-id="8f3a1-131">This includes:</span></span>  

*   <span data-ttu-id="8f3a1-132">对方法 `canMakePayment()` 的支持</span><span class="sxs-lookup"><span data-stu-id="8f3a1-132">Support for the `canMakePayment()` method</span></span>  
*   <span data-ttu-id="8f3a1-133">对属性 `requestId` 的支持</span><span class="sxs-lookup"><span data-stu-id="8f3a1-133">Support for the `requestId` property</span></span>  
*   <span data-ttu-id="8f3a1-134">对属性 `id` 的支持</span><span class="sxs-lookup"><span data-stu-id="8f3a1-134">Support for the `id` property</span></span>  
*   <span data-ttu-id="8f3a1-135">方法参数的默认值 `complete()` 从 `result` ""更改为"未知"</span><span class="sxs-lookup"><span data-stu-id="8f3a1-135">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span></span>  

### <a name="service-workers"></a><span data-ttu-id="8f3a1-136">服务工作者</span><span class="sxs-lookup"><span data-stu-id="8f3a1-136">Service Workers</span></span>  

<span data-ttu-id="8f3a1-137">[服务工作人员](https://www.w3.org/TR/service-workers-1) 是事件驱动的脚本，在网页后台运行。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-137">[Service Workers](https://www.w3.org/TR/service-workers-1) are event-driven scripts that run in the background of a web page.</span></span>  <span data-ttu-id="8f3a1-138">服务工作人员启用以前仅适用于本机应用的功能，例如截获和处理来自网络的请求、管理和处理后台同步、本地存储和推送通知。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-138">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span></span>  <span data-ttu-id="8f3a1-139">对服务工作者的支持仍在开发中，但您可以通过在 中启用服务工作者功能，在我们的实验服务工作者支持中测试 Microsoft Edge 中的 `about:flags` PWA。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-139">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in `about:flags`.</span></span>  

### <a name="webvr"></a><span data-ttu-id="8f3a1-140">WebVR</span><span class="sxs-lookup"><span data-stu-id="8f3a1-140">WebVR</span></span>  

<span data-ttu-id="8f3a1-141">Microsoft Edge 的 WebVR 增加了对运动 [控制器的支持](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-141">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span></span>  <span data-ttu-id="8f3a1-142">这些控制器在空间中具有精确位置，允许与虚拟现实中的数字对象进行精细交互。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-142">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span></span>  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="运动控制器" lightbox="../media/MotionControllers.jpg":::
   <span data-ttu-id="8f3a1-144">运动控制器</span><span class="sxs-lookup"><span data-stu-id="8f3a1-144">Motion controllers</span></span>  
:::image-end:::  

<span data-ttu-id="8f3a1-145">WebVR 还进行了优化，以支持两种不同类型的体验。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-145">WebVR has also been optimized to support two different types of experiences.</span></span>  

<span data-ttu-id="8f3a1-146">**Windows Mixed Reality 电脑** - 带集成图形的台式机和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-146">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span></span>  <span data-ttu-id="8f3a1-147">插入这些设备时，我们的沉浸式耳机将以 60 帧/秒的速度运行。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-147">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span></span>  
<span data-ttu-id="8f3a1-148">**Windows Mixed Reality 超电脑** - 具有离散图形的台式机和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-148">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span></span>  <span data-ttu-id="8f3a1-149">插入这些设备时，我们的沉浸式耳机将以 90 帧/秒的速度运行。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-149">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span></span>  

<span data-ttu-id="8f3a1-150">这两种设置将支持相同的沉浸式视频和游戏体验。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-150">Both setups will support the same immersive video and gaming experiences.</span></span>  

<span data-ttu-id="8f3a1-151">有关即将推出的 Windows Mixed Reality 更新的信息，请查看 [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) 假日更新博客文章。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-151">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) holiday update blog post.</span></span>  

<span data-ttu-id="8f3a1-152">有关指南和演示，请前往 [WebVR 开发人员指南](/microsoft-edge/webvr)。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-152">For guides and demos, head over to the [WebVR Developer Guide](/microsoft-edge/webvr).</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="8f3a1-153">由于 WebVR 规范仍处于开发阶段，因此 Microsoft Edge 的实现稍后可能会发生变化。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-153">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <a name="new-apis-in-edgehtml-16"></a><span data-ttu-id="8f3a1-154">EdgeHTML 16 中的新 API</span><span class="sxs-lookup"><span data-stu-id="8f3a1-154">New APIs in EdgeHTML 16</span></span>  

<span data-ttu-id="8f3a1-155">下面是 EdgeHTML 16 中新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-155">Here's the full list of new APIs in EdgeHTML 16.</span></span>  <span data-ttu-id="8f3a1-156">它们以 . `[interface name].[api name]`</span><span class="sxs-lookup"><span data-stu-id="8f3a1-156">They are listed in the format of `[interface name].[api name]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="8f3a1-157">尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍处于开发阶段。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-157">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="8f3a1-158">有关 [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status) 词，请参阅 Microsoft Edge 平台状态。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-158">Refer to [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

---  

<iframe height='559' scrolling='no' title='<span data-ttu-id="8f3a1-159">EdgeHTML 16 中的新 API</span><span class="sxs-lookup"><span data-stu-id="8f3a1-159">New APIs in EdgeHTML 16</span></span>' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="8f3a1-160">请参阅 EdgeHTML 16 中的笔新 <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> </a> API，由 MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) </a> <a href='https://codepen.io'> CodePen 上 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8f3a1-160">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

---  

## <a name="previous-edgehtml-releases"></a><span data-ttu-id="8f3a1-161">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="8f3a1-161">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="8f3a1-162">EdgeHTML 12 / Windows 版本 10240 (7/2015) </span><span class="sxs-lookup"><span data-stu-id="8f3a1-162">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="8f3a1-163">EdgeHTML 13 / Windows 版本 10586 (11/2015) </span><span class="sxs-lookup"><span data-stu-id="8f3a1-163">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="8f3a1-164">EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) </span><span class="sxs-lookup"><span data-stu-id="8f3a1-164">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  

[<span data-ttu-id="8f3a1-165">EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) </span><span class="sxs-lookup"><span data-stu-id="8f3a1-165">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](./edgehtml-15.md)  
