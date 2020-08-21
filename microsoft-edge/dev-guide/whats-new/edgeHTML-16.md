---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: 本指南概述 Microsoft Edge 中包括的开发人员功能和标准。
title: EdgeHTML 16 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: a15888bc8c1314d61d436759e5d63be942174ea4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941938"
---
# <span data-ttu-id="93c98-104">EdgeHTML 16 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="93c98-104">What's new in EdgeHTML 16</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="93c98-105">下面是 [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) Web 平台中随之外出现的新功能和更新功能的列表， [作为 Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \ (10/2017（内部版本 16299\) 的一部分）。</span><span class="sxs-lookup"><span data-stu-id="93c98-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, Build 16299\).</span></span>  <span data-ttu-id="93c98-106">有关特定 Windows Insider Preview 版本中的更改，请参阅 [Microsoft Edge 更改日](https://developer.microsoft.com/microsoft-edge/platform/changelog) 志 [和 EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="93c98-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="93c98-107">下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md) ：。</span><span class="sxs-lookup"><span data-stu-id="93c98-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md).</span></span>  

## <span data-ttu-id="93c98-108">新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="93c98-108">New and updated features</span></span>  

### <span data-ttu-id="93c98-109">CSS 网格布局</span><span class="sxs-lookup"><span data-stu-id="93c98-109">CSS Grid Layout</span></span>  

<span data-ttu-id="93c98-110">Microsoft Edge 现在支持对 CSS 网格 [布局的未前缀实现](https://www.w3.org/TR/css-grid-1)。</span><span class="sxs-lookup"><span data-stu-id="93c98-110">Microsoft Edge now supports the un-prefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1).</span></span>  <span data-ttu-id="93c98-111">[网格布局](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) 定义了基于二维网格的布局系统，它比使用浮点或脚本进行定位相比，该系统支持更流畅的布局。</span><span class="sxs-lookup"><span data-stu-id="93c98-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span></span>  <span data-ttu-id="93c98-112">以下示例使用 CSS 网格布局为基本网页创建结构。</span><span class="sxs-lookup"><span data-stu-id="93c98-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span></span>  

<iframe height='303' scrolling='no' title='<span data-ttu-id="93c98-113">CSS 网格布局</span><span class="sxs-lookup"><span data-stu-id="93c98-113">CSS Grid Layout</span></span>' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="93c98-114">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'> MSEdgeDev 代码库 (@MSEdgeDev) 笔的 Pen CSS </a> <a href='https://codepen.io/MSEdgeDev'> </a> <a href='https://codepen.io'> 网格布局 </a> 。</span><span class="sxs-lookup"><span data-stu-id="93c98-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

### <span data-ttu-id="93c98-115">CSS 对象适合和 object-position</span><span class="sxs-lookup"><span data-stu-id="93c98-115">CSS object-fit and object-position</span></span>  

<span data-ttu-id="93c98-116">EdgeHTML 16 引入了对 CSS 属性和的 [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) 支持 [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position) 。</span><span class="sxs-lookup"><span data-stu-id="93c98-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span></span>  <span data-ttu-id="93c98-117">这些属性控制替换内容在内容框中的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="93c98-117">These properties control the position and size of replaced content within the content box.</span></span>  

### <span data-ttu-id="93c98-118">开发人员工具</span><span class="sxs-lookup"><span data-stu-id="93c98-118">Developer Tools</span></span>  

<span data-ttu-id="93c98-119">此版本已经为提升的可靠性和性能重构，我们已经为提升的强大功能和性能重构，并添加了一大段新功能，你可以现在开始在 [Windows 预览](https://insider.windows.com) 体验成员版本上使用。</span><span class="sxs-lookup"><span data-stu-id="93c98-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com) builds.</span></span>  <span data-ttu-id="93c98-120">查看 [Microsoft Edge 开发人员指南，了解](../whats-new.md) 发生变化情况的详细信息！</span><span class="sxs-lookup"><span data-stu-id="93c98-120">Check out the [Microsoft Edge DevTools guide](../whats-new.md) for more on what's changed!</span></span>  

### <span data-ttu-id="93c98-121">JavaScript</span><span class="sxs-lookup"><span data-stu-id="93c98-121">JavaScript</span></span>  

<span data-ttu-id="93c98-122">[EdgeHTML 16 基于以](https://blogs.windows.com/msedgedev/2017/10/31)前版本的性能优化的 Javascript 性能优化的基率，方法是扩展 Chakra 引联程序可延期/re-defer 函数、使用多形式缓存，并使用块 `try` / `finally` 优化函数。</span><span class="sxs-lookup"><span data-stu-id="93c98-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with `try`/`finally` blocks.</span></span>  

<span data-ttu-id="93c98-123">另外，在 EdgeHTML 15 中预览的功能现在更可排序，默认情况下处于启用状态：</span><span class="sxs-lookup"><span data-stu-id="93c98-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span></span>  

#### <span data-ttu-id="93c98-124">新增功能</span><span class="sxs-lookup"><span data-stu-id="93c98-124">New features</span></span>  

<span data-ttu-id="93c98-125">默认启用</span><span class="sxs-lookup"><span data-stu-id="93c98-125">On by default</span></span>  

*   <span data-ttu-id="93c98-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \ ([demo](https://webassembly.org/demo)\) </span><span class="sxs-lookup"><span data-stu-id="93c98-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="93c98-127">共享内存和原子</span><span class="sxs-lookup"><span data-stu-id="93c98-127">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### <span data-ttu-id="93c98-128">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="93c98-128">Payment Request API</span></span>  

<span data-ttu-id="93c98-129">[付款请求 API 是](../windows-integration/payment-request-api.md)一种开放的跨浏览器标准，允许浏览器在商业、使用者和付款方式 \ (如信用卡\) 客户存储在云中，采用的中介。</span><span class="sxs-lookup"><span data-stu-id="93c98-129">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="93c98-130">已更新 EdgeHTML 16 中的 API，以匹配最新的 W3C [付款请求 API](https://w3c.github.io/payment-request) 规范。</span><span class="sxs-lookup"><span data-stu-id="93c98-130">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request) specification.</span></span>  <span data-ttu-id="93c98-131">这包括：</span><span class="sxs-lookup"><span data-stu-id="93c98-131">This includes:</span></span>  

*   <span data-ttu-id="93c98-132">对方法 `canMakePayment()` 的支持</span><span class="sxs-lookup"><span data-stu-id="93c98-132">Support for the `canMakePayment()` method</span></span>  
*   <span data-ttu-id="93c98-133">对属性 `requestId` 的支持</span><span class="sxs-lookup"><span data-stu-id="93c98-133">Support for the `requestId` property</span></span>  
*   <span data-ttu-id="93c98-134">对属性 `id` 的支持</span><span class="sxs-lookup"><span data-stu-id="93c98-134">Support for the `id` property</span></span>  
*   <span data-ttu-id="93c98-135">该方法参数的 `complete()` 默认值从"" `result` 更改为"未知"</span><span class="sxs-lookup"><span data-stu-id="93c98-135">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span></span>  

### <span data-ttu-id="93c98-136">服务工作进程</span><span class="sxs-lookup"><span data-stu-id="93c98-136">Service Workers</span></span>  

<span data-ttu-id="93c98-137">[服务工作者](https://www.w3.org/TR/service-workers-1) 是在网页后台运行的事件驱动的脚本。</span><span class="sxs-lookup"><span data-stu-id="93c98-137">[Service Workers](https://www.w3.org/TR/service-workers-1) are event-driven scripts that run in the background of a web page.</span></span>  <span data-ttu-id="93c98-138">服务工作者现在只能通过本机应用使用功能，如从网络中部起状态、管理和处理后台同步、本地存储以及推送通知等本机应用的请求。</span><span class="sxs-lookup"><span data-stu-id="93c98-138">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span></span>  <span data-ttu-id="93c98-139">服务工作者的支持仍在开发中，但你可以通过在技术服务工作者支持中启用服务工作者功能，在 Microsoft Edge 中通过实验性服务工作者支持测试你的 `about:flags` PWA。</span><span class="sxs-lookup"><span data-stu-id="93c98-139">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in `about:flags`.</span></span>  

### <span data-ttu-id="93c98-140">WebVR</span><span class="sxs-lookup"><span data-stu-id="93c98-140">WebVR</span></span>  

<span data-ttu-id="93c98-141">适用于 Microsoft Edge 的 WebVR 已添加 [对运动控制器的支持](https://developer.microsoft.com/windows/mixed-reality/motion_controllers)。</span><span class="sxs-lookup"><span data-stu-id="93c98-141">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span></span>  <span data-ttu-id="93c98-142">这些控制器在空间中具有精确的位置，可让你精细交互虚拟现实。</span><span class="sxs-lookup"><span data-stu-id="93c98-142">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span></span>  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="运动控制器" lightbox="../media/MotionControllers.jpg":::
   <span data-ttu-id="93c98-144">运动控制器</span><span class="sxs-lookup"><span data-stu-id="93c98-144">Motion controllers</span></span>  
:::image-end:::  

<span data-ttu-id="93c98-145">WebVR 也经过优化，以支持两种不同类型的体验。</span><span class="sxs-lookup"><span data-stu-id="93c98-145">WebVR has also been optimized to support two different types of experiences.</span></span>  

<span data-ttu-id="93c98-146">**Windows 混合现实电脑** - 一台包含集成图形的台式机和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="93c98-146">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span></span>  <span data-ttu-id="93c98-147">插入这些设备后，沉送耳机将以 60 帧每秒的速度运行。</span><span class="sxs-lookup"><span data-stu-id="93c98-147">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span></span>  
<span data-ttu-id="93c98-148">**Windows 混合现实 Ultra 电脑** - 具有自由图形的台式机和笔记本电脑。</span><span class="sxs-lookup"><span data-stu-id="93c98-148">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span></span>  <span data-ttu-id="93c98-149">插入这些设备后，沉送耳机将以 90 帧每秒的速度运行。</span><span class="sxs-lookup"><span data-stu-id="93c98-149">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span></span>  

<span data-ttu-id="93c98-150">这两个设置都支持相同的沉静视频和游戏体验。</span><span class="sxs-lookup"><span data-stu-id="93c98-150">Both setups will support the same immersive video and gaming experiences.</span></span>  

<span data-ttu-id="93c98-151">有关即将推出的 Windows Mixed Reality 更新的详细信息，请查看 [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) 更新博客文章。</span><span class="sxs-lookup"><span data-stu-id="93c98-151">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) holiday update blog post.</span></span>  

<span data-ttu-id="93c98-152">有关指南和演示，请转到 [WebVR 开发人员指南](/microsoft-edge/webvr)。</span><span class="sxs-lookup"><span data-stu-id="93c98-152">For guides and demos, head over to the [WebVR Developer Guide](/microsoft-edge/webvr).</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="93c98-153">由于 WebVR 规范仍在开发中，所以 Microsoft Edge 的实现可能会在以后更改。</span><span class="sxs-lookup"><span data-stu-id="93c98-153">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="93c98-154">EdgeHTML 16 中的新 API</span><span class="sxs-lookup"><span data-stu-id="93c98-154">New APIs in EdgeHTML 16</span></span>  

<span data-ttu-id="93c98-155">下面是 EdgeHTML 16 中的新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="93c98-155">Here's the full list of new APIs in EdgeHTML 16.</span></span>  <span data-ttu-id="93c98-156">它们以格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="93c98-156">They are listed in the format of `[interface name].[api name]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="93c98-157">尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍在开发中。</span><span class="sxs-lookup"><span data-stu-id="93c98-157">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="93c98-158">若要了解  [功能支持的正](https://developer.microsoft.com/microsoft-edge/platform/status) 式字词，请参考 Microsoft Edge 平台状态。</span><span class="sxs-lookup"><span data-stu-id="93c98-158">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

---  

<iframe height='559' scrolling='no' title='<span data-ttu-id="93c98-159">EdgeHTML 16 中的新 API</span><span class="sxs-lookup"><span data-stu-id="93c98-159">New APIs in EdgeHTML 16</span></span>' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="93c98-160">在 <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'> CodePen 上查看 </a> MSEdgeDev 中由 MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> </a> (@MSEdgeDev@MSEdgeDev) <a href='https://codepen.io'> 笔新 </a> API。</span><span class="sxs-lookup"><span data-stu-id="93c98-160">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

---  

## <span data-ttu-id="93c98-161">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="93c98-161">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="93c98-162">EdgeHTML 12 / Windows 内部版本 10240 (7/2015) </span><span class="sxs-lookup"><span data-stu-id="93c98-162">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="93c98-163">EdgeHTML 13 / Windows 版本 10586 (11/2015 版) </span><span class="sxs-lookup"><span data-stu-id="93c98-163">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="93c98-164">EdgeHTML 14/Windows 内部版本 14393 (，8) </span><span class="sxs-lookup"><span data-stu-id="93c98-164">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  

[<span data-ttu-id="93c98-165">EdgeHTML 15 /Windows 内部版本 15063 (4/2017) </span><span class="sxs-lookup"><span data-stu-id="93c98-165">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](./edgehtml-15.md)  
