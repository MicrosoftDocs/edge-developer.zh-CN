---
ms.assetid: 476c4b7a-be24-434b-a051-83f19d741aaf
description: This guide provides an overview of the developer features and standards included in Microsoft Edge.
title: New features and APIs in EdgeHTML 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: edge, web development, html, css, javascript, developer
ms.openlocfilehash: a15888bc8c1314d61d436759e5d63be942174ea4
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941938"
---
# <span data-ttu-id="0f47e-104">What's new in EdgeHTML 16</span><span class="sxs-lookup"><span data-stu-id="0f47e-104">What's new in EdgeHTML 16</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="0f47e-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, Build 16299\).</span><span class="sxs-lookup"><span data-stu-id="0f47e-105">Here's a list of the new and updated features shipped in [EdgeHTML 16](https://blogs.windows.com/msedgedev/2017/10/17) web platform, as part of the [Windows 10 Fall Creators Update](https://blogs.windows.com/windowsexperience/2017/10/17/whats-new-windows-10-fall-creators-update) \(10/2017, Build 16299\).</span></span>  <span data-ttu-id="0f47e-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span><span class="sxs-lookup"><span data-stu-id="0f47e-106">For changes in specific Windows Insider Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="0f47e-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md).</span><span class="sxs-lookup"><span data-stu-id="0f47e-107">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_16](./edgehtml-16.md).</span></span>  

## <span data-ttu-id="0f47e-108">New and updated features</span><span class="sxs-lookup"><span data-stu-id="0f47e-108">New and updated features</span></span>  

### <span data-ttu-id="0f47e-109">CSS Grid Layout</span><span class="sxs-lookup"><span data-stu-id="0f47e-109">CSS Grid Layout</span></span>  

<span data-ttu-id="0f47e-110">Microsoft Edge now supports the un-prefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1).</span><span class="sxs-lookup"><span data-stu-id="0f47e-110">Microsoft Edge now supports the un-prefixed implementation of [CSS Grid Layout](https://www.w3.org/TR/css-grid-1).</span></span>  <span data-ttu-id="0f47e-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span><span class="sxs-lookup"><span data-stu-id="0f47e-111">[Grid Layout](https://developer.mozilla.org/docs/Web/CSS/CSS_Grid_Layout) defines a two-dimensional grid-based layout system which enables more layout fluidity than possible with positioning using floats or scripts.</span></span>  <span data-ttu-id="0f47e-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span><span class="sxs-lookup"><span data-stu-id="0f47e-112">The example below uses CSS Grid Layout to create the structure for a basic web page.</span></span>  

<iframe height='303' scrolling='no' title='<span data-ttu-id="0f47e-113">CSS Grid Layout</span><span class="sxs-lookup"><span data-stu-id="0f47e-113">CSS Grid Layout</span></span>' src='//codepen.io/MSEdgeDev/embed/mMQqZX/?height=303&theme-id=23761&default-tab=css,result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="0f47e-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span><span class="sxs-lookup"><span data-stu-id="0f47e-114">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/mMQqZX/'>CSS Grid Layout</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

### <span data-ttu-id="0f47e-115">CSS object-fit and object-position</span><span class="sxs-lookup"><span data-stu-id="0f47e-115">CSS object-fit and object-position</span></span>  

<span data-ttu-id="0f47e-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span><span class="sxs-lookup"><span data-stu-id="0f47e-116">EdgeHTML 16 introduces support for CSS properties [`object-fit`](https://developer.mozilla.org/docs/Web/CSS/object-fit) and [`object-position`](https://developer.mozilla.org/docs/Web/CSS/object-position).</span></span>  <span data-ttu-id="0f47e-117">These properties control the position and size of replaced content within the content box.</span><span class="sxs-lookup"><span data-stu-id="0f47e-117">These properties control the position and size of replaced content within the content box.</span></span>  

### <span data-ttu-id="0f47e-118">Developer Tools</span><span class="sxs-lookup"><span data-stu-id="0f47e-118">Developer Tools</span></span>  

<span data-ttu-id="0f47e-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com) builds.</span><span class="sxs-lookup"><span data-stu-id="0f47e-119">This release we started a major Microsoft Edge DevTools refactoring effort for improved robustness and performance, and also added a bunch of new features you can start using today on [Windows Insider](https://insider.windows.com) builds.</span></span>  <span data-ttu-id="0f47e-120">Check out the [Microsoft Edge DevTools guide](../whats-new.md) for more on what's changed!</span><span class="sxs-lookup"><span data-stu-id="0f47e-120">Check out the [Microsoft Edge DevTools guide](../whats-new.md) for more on what's changed!</span></span>  

### <span data-ttu-id="0f47e-121">JavaScript</span><span class="sxs-lookup"><span data-stu-id="0f47e-121">JavaScript</span></span>  

<span data-ttu-id="0f47e-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with `try`/`finally` blocks.</span><span class="sxs-lookup"><span data-stu-id="0f47e-122">[EdgeHTML 16 builds on Javascript performance](https://blogs.windows.com/msedgedev/2017/10/31) optimizations of previous releases by expanding the Chakra engine's ability to defer/re-defer functions, use polymorphic inline caches, and optimize functions with `try`/`finally` blocks.</span></span>  

<span data-ttu-id="0f47e-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span><span class="sxs-lookup"><span data-stu-id="0f47e-123">Additionally, features first previewed in EdgeHTML 15 are now stable and enabled by default:</span></span>  

#### <span data-ttu-id="0f47e-124">New features</span><span class="sxs-lookup"><span data-stu-id="0f47e-124">New features</span></span>  

<span data-ttu-id="0f47e-125">On by default</span><span class="sxs-lookup"><span data-stu-id="0f47e-125">On by default</span></span>  

*   <span data-ttu-id="0f47e-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span><span class="sxs-lookup"><span data-stu-id="0f47e-126">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) MVP \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="0f47e-127">Shared Memory and Atomics</span><span class="sxs-lookup"><span data-stu-id="0f47e-127">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

### <span data-ttu-id="0f47e-128">Payment Request API</span><span class="sxs-lookup"><span data-stu-id="0f47e-128">Payment Request API</span></span>  

<span data-ttu-id="0f47e-129">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods \(such as credit cards\) that consumers have stored in the cloud.</span><span class="sxs-lookup"><span data-stu-id="0f47e-129">The [Payment Request API](../windows-integration/payment-request-api.md) is an open, cross-browser standard that enables browsers to act as an intermediary between merchants, consumers, and payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="0f47e-130">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request) specification.</span><span class="sxs-lookup"><span data-stu-id="0f47e-130">The API in EdgeHTML 16 has been updated to match the latest W3C [Payment Request API](https://w3c.github.io/payment-request) specification.</span></span>  <span data-ttu-id="0f47e-131">This includes:</span><span class="sxs-lookup"><span data-stu-id="0f47e-131">This includes:</span></span>  

*   <span data-ttu-id="0f47e-132">Support for the `canMakePayment()` method</span><span class="sxs-lookup"><span data-stu-id="0f47e-132">Support for the `canMakePayment()` method</span></span>  
*   <span data-ttu-id="0f47e-133">Support for the `requestId` property</span><span class="sxs-lookup"><span data-stu-id="0f47e-133">Support for the `requestId` property</span></span>  
*   <span data-ttu-id="0f47e-134">Support for the `id` property</span><span class="sxs-lookup"><span data-stu-id="0f47e-134">Support for the `id` property</span></span>  
*   <span data-ttu-id="0f47e-135">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span><span class="sxs-lookup"><span data-stu-id="0f47e-135">The default value for the `complete()` method's `result` parameter changed from " " to "unknown"</span></span>  

### <span data-ttu-id="0f47e-136">Service Workers</span><span class="sxs-lookup"><span data-stu-id="0f47e-136">Service Workers</span></span>  

<span data-ttu-id="0f47e-137">[Service Workers](https://www.w3.org/TR/service-workers-1) are event-driven scripts that run in the background of a web page.</span><span class="sxs-lookup"><span data-stu-id="0f47e-137">[Service Workers](https://www.w3.org/TR/service-workers-1) are event-driven scripts that run in the background of a web page.</span></span>  <span data-ttu-id="0f47e-138">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span><span class="sxs-lookup"><span data-stu-id="0f47e-138">Service workers enable functionality previously only available with native apps like intercepting and handling requests from the network, managing and handling background sync, local storage, and push notifications.</span></span>  <span data-ttu-id="0f47e-139">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in `about:flags`.</span><span class="sxs-lookup"><span data-stu-id="0f47e-139">Support for service worker is still in development, but you can test out your PWA in Microsoft Edge with our experimental service worker support by enabling the service worker feature in `about:flags`.</span></span>  

### <span data-ttu-id="0f47e-140">WebVR</span><span class="sxs-lookup"><span data-stu-id="0f47e-140">WebVR</span></span>  

<span data-ttu-id="0f47e-141">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span><span class="sxs-lookup"><span data-stu-id="0f47e-141">WebVR for Microsoft Edge has added support for [motion controllers](https://developer.microsoft.com/windows/mixed-reality/motion_controllers).</span></span>  <span data-ttu-id="0f47e-142">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span><span class="sxs-lookup"><span data-stu-id="0f47e-142">These controllers have a precise position in space, allowing for fine grained interaction with digital objects in virtual reality.</span></span>  

:::image type="complex" source="../media/MotionControllers.jpg" alt-text="Motion controllers" lightbox="../media/MotionControllers.jpg":::
   <span data-ttu-id="0f47e-144">Motion controllers</span><span class="sxs-lookup"><span data-stu-id="0f47e-144">Motion controllers</span></span>  
:::image-end:::  

<span data-ttu-id="0f47e-145">WebVR has also been optimized to support two different types of experiences.</span><span class="sxs-lookup"><span data-stu-id="0f47e-145">WebVR has also been optimized to support two different types of experiences.</span></span>  

<span data-ttu-id="0f47e-146">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span><span class="sxs-lookup"><span data-stu-id="0f47e-146">**Windows Mixed Reality PCs** - Desktops and laptops with integrated graphics.</span></span>  <span data-ttu-id="0f47e-147">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span><span class="sxs-lookup"><span data-stu-id="0f47e-147">When plugged into these devices, our immersive headsets will run at 60 frames per second.</span></span>  
<span data-ttu-id="0f47e-148">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span><span class="sxs-lookup"><span data-stu-id="0f47e-148">**Windows Mixed Reality Ultra PCs** - Desktops and laptops with discrete graphics.</span></span>  <span data-ttu-id="0f47e-149">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span><span class="sxs-lookup"><span data-stu-id="0f47e-149">When plugged into these devices, our immersive headsets will run at 90 frames per second.</span></span>  

<span data-ttu-id="0f47e-150">Both setups will support the same immersive video and gaming experiences.</span><span class="sxs-lookup"><span data-stu-id="0f47e-150">Both setups will support the same immersive video and gaming experiences.</span></span>  

<span data-ttu-id="0f47e-151">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) holiday update blog post.</span><span class="sxs-lookup"><span data-stu-id="0f47e-151">For more info about the upcoming Windows Mixed Reality updates, check out the [Windows Mixed Reality](https://blogs.windows.com/windowsexperience/2017/08/28/windows-mixed-reality-holiday-update) holiday update blog post.</span></span>  

<span data-ttu-id="0f47e-152">For guides and demos, head over to the [WebVR Developer Guide](/microsoft-edge/webvr).</span><span class="sxs-lookup"><span data-stu-id="0f47e-152">For guides and demos, head over to the [WebVR Developer Guide](/microsoft-edge/webvr).</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="0f47e-153">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span><span class="sxs-lookup"><span data-stu-id="0f47e-153">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="0f47e-154">New APIs in EdgeHTML 16</span><span class="sxs-lookup"><span data-stu-id="0f47e-154">New APIs in EdgeHTML 16</span></span>  

<span data-ttu-id="0f47e-155">Here's the full list of new APIs in EdgeHTML 16.</span><span class="sxs-lookup"><span data-stu-id="0f47e-155">Here's the full list of new APIs in EdgeHTML 16.</span></span>  <span data-ttu-id="0f47e-156">They are listed in the format of `[interface name].[api name]`.</span><span class="sxs-lookup"><span data-stu-id="0f47e-156">They are listed in the format of `[interface name].[api name]`.</span></span>

> [!NOTE] 
> <span data-ttu-id="0f47e-157">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span><span class="sxs-lookup"><span data-stu-id="0f47e-157">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="0f47e-158">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span><span class="sxs-lookup"><span data-stu-id="0f47e-158">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

---  

<iframe height='559' scrolling='no' title='<span data-ttu-id="0f47e-159">New APIs in EdgeHTML 16</span><span class="sxs-lookup"><span data-stu-id="0f47e-159">New APIs in EdgeHTML 16</span></span>' src='//codepen.io/MSEdgeDev/embed/jLGZZY/?height=559&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true'><span data-ttu-id="0f47e-160">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span><span class="sxs-lookup"><span data-stu-id="0f47e-160">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/jLGZZY/'>New APIs in EdgeHTML 16</a>by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

---  

## <span data-ttu-id="0f47e-161">Previous EdgeHTML releases</span><span class="sxs-lookup"><span data-stu-id="0f47e-161">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="0f47e-162">EdgeHTML 12 / Windows build 10240 (7/2015)</span><span class="sxs-lookup"><span data-stu-id="0f47e-162">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="0f47e-163">EdgeHTML 13 / Windows build 10586 (11/2015)</span><span class="sxs-lookup"><span data-stu-id="0f47e-163">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="0f47e-164">EdgeHTML 14 / Windows build 14393 (8/2016)</span><span class="sxs-lookup"><span data-stu-id="0f47e-164">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  

[<span data-ttu-id="0f47e-165">EdgeHTML 15 / Windows build 15063 (4/2017)</span><span class="sxs-lookup"><span data-stu-id="0f47e-165">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](./edgehtml-15.md)  
