---
description: 本指南概述了 EdgeHTML 15 中包含的开发人员功能和标准。
title: EdgeHTML 15 中的新功能和 Api
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/02/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.custom: seodec18
ms.openlocfilehash: 4fd0bbc06d27bace424ea99cfe9941aabc737fee
ms.sourcegitcommit: 204a284e21bf2da5cdc862c5e8b5839245abbbbc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2020
ms.locfileid: "11094359"
---
# <span data-ttu-id="82592-104">EdgeHTML 15 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="82592-104">What's new in EdgeHTML 15</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="82592-105">以下是当前版本的 Microsoft Edge 平台（从 [Windows 10 创意者更新](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \ (04/2017，内部版本 15063 \ ) ）随附的更改。</span><span class="sxs-lookup"><span data-stu-id="82592-105">Here are the changes shipped with the current release of the Microsoft Edge platform, as of the [Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, Build 15063\).</span></span>  <span data-ttu-id="82592-106">有关 Microsoft Edge 整体浏览器更改的概述，请参阅 [Windows 10 创意者更新中 Microsoft Edge 中的新增功能](https://blogs.windows.com/msedgedev/2017/04/11)。</span><span class="sxs-lookup"><span data-stu-id="82592-106">For an overview of changes to the overall Microsoft Edge browser, see [What's new in Microsoft Edge in the Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11).</span></span>  

<span data-ttu-id="82592-107">有关后续 Windows 预览体验计划预览版本中的更改，请参阅 [EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="82592-107">For changes in subsequent Windows Insider Preview builds, see [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="82592-108">下面是以下更改列表的固定链接：  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) 。</span><span class="sxs-lookup"><span data-stu-id="82592-108">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md).</span></span>  

## <span data-ttu-id="82592-109">新增功能</span><span class="sxs-lookup"><span data-stu-id="82592-109">New features</span></span>  

### <span data-ttu-id="82592-110">CSS 自定义属性</span><span class="sxs-lookup"><span data-stu-id="82592-110">CSS Custom Properties</span></span>  

<span data-ttu-id="82592-111">Microsoft Edge 现在支持 [Css 自定义属性](https://drafts.csswg.org/css-variables)，即 css 变量。</span><span class="sxs-lookup"><span data-stu-id="82592-111">Microsoft Edge now supports [CSS Custom Properties](https://drafts.csswg.org/css-variables), a.k.a CSS Variables.</span></span>  <span data-ttu-id="82592-112">CSS 变量允许你创建可在整个样式表中重复使用的自定义 CSS 属性，以帮助减少重复数据量（如重复的颜色）。</span><span class="sxs-lookup"><span data-stu-id="82592-112">CSS Variables allow you to create custom CSS properties that can be reused throughout stylesheets to help reduce the amount of duplicate data, like repeated colors.</span></span>  <span data-ttu-id="82592-113">使用 CSS 变量非常简单：</span><span class="sxs-lookup"><span data-stu-id="82592-113">Using CSS Variables is simple:</span></span>  

```css
/* define a custom property by using two dashes and assign it a value */
body {   
   --default-color: #3390b1
}

/* reference it in your stylesheet with the "var()" function */
h1 {
   color: var(--default-color);
}
```  

### <span data-ttu-id="82592-114">交集观察器</span><span class="sxs-lookup"><span data-stu-id="82592-114">Intersection Observer</span></span>  

<span data-ttu-id="82592-115">EdgeHTML 15 引入了 [交集观察程序 API](https://w3c.github.io/IntersectionObserver) 规范。</span><span class="sxs-lookup"><span data-stu-id="82592-115">EdgeHTML 15 introduces the [Intersection Observer API](https://w3c.github.io/IntersectionObserver) specification.</span></span>  <span data-ttu-id="82592-116">"交集观察程序" API 允许你异步查询 DOM 元素相对于其他元素或全局视区的位置和可见性。</span><span class="sxs-lookup"><span data-stu-id="82592-116">The Intersection Observer API allows you to asynchronously query the position and visibility of DOM elements relative to other elements or the global viewport.</span></span>  <span data-ttu-id="82592-117">此 API 通过创建一种在视图中高效通知元素的方法，消除了自定义昂贵的代码的需要。</span><span class="sxs-lookup"><span data-stu-id="82592-117">This API eliminates the need for custom expensive code by creating a method to efficiently notify elements when they are in view.</span></span>  

### <span data-ttu-id="82592-118">JavaScript</span><span class="sxs-lookup"><span data-stu-id="82592-118">JavaScript</span></span>  

<span data-ttu-id="82592-119">性能优化采用 Chakra JavaScript 引擎的 EdgeHTML 15 次阶段。</span><span class="sxs-lookup"><span data-stu-id="82592-119">Performance optimizations take center stage with the EdgeHTML 15 rev of the Chakra JavaScript engine.</span></span>  <span data-ttu-id="82592-120">通过 Windows 10 创意者更新，Chakra 可通过重新延迟函数和优化堆参数来节省内存，并提高 minified 代码的性能。</span><span class="sxs-lookup"><span data-stu-id="82592-120">With the Windows 10 Creators Update, Chakra saves memory by re-deferring functions and optimizing away heap arguments and improves performance for minified code.</span></span>  

<span data-ttu-id="82592-121">此外，EdgeHTML 15 引入了以下功能预览：</span><span class="sxs-lookup"><span data-stu-id="82592-121">Additionally, EdgeHTML 15 introduces the following feature previews:</span></span>  

#### <span data-ttu-id="82592-122">实验性 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="82592-122">Experimental JavaScript features</span></span>  

<span data-ttu-id="82592-123">已启用</span><span class="sxs-lookup"><span data-stu-id="82592-123">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="82592-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \ ([演示](https://webassembly.org/demo)\ ) </span><span class="sxs-lookup"><span data-stu-id="82592-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="82592-125">共享内存和 Atomics</span><span class="sxs-lookup"><span data-stu-id="82592-125">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

<span data-ttu-id="82592-126">有关进一步的详细信息，请参阅 [Microsoft Edge 中改进的 JavaScript 性能、WebAssembly 和共享内存](https://blogs.windows.com/msedgedev/2017/04/20) 。</span><span class="sxs-lookup"><span data-stu-id="82592-126">See [Improved JavaScript performance, WebAssembly, and Shared Memory in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/04/20) for further details.</span></span>  

### <span data-ttu-id="82592-127">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="82592-127">Payment Request API</span></span>  

<span data-ttu-id="82592-128">[付款请求 API](https://w3.org/TR/payment-request)现在受支持，在 Windows 10 电脑和手机上的 web 上支持更简单的结帐和付款。</span><span class="sxs-lookup"><span data-stu-id="82592-128">The [Payment Request API](https://w3.org/TR/payment-request) is now supported, enabling simpler checkout and payments on the web on Windows 10 PCs and Phones.</span></span>  <span data-ttu-id="82592-129">此 API 使 Microsoft Edge 能够充当商家、消费者和付款方式 \ (（如信用卡）之间的媒介，如消费者已存储在云中的 ) 。</span><span class="sxs-lookup"><span data-stu-id="82592-129">This API enables Microsoft Edge to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="82592-130">有关付款请求 API 的详细信息，请查看 [更简单的 web 付款：介绍付款请求 api](https://blogs.windows.com/msedgedev/2016/12/15) 和 [付款请求 api](/microsoft-edge/dev-guide/device/payment-request-api) 开发人员指南。</span><span class="sxs-lookup"><span data-stu-id="82592-130">For more information on the Payment Request API, check out [Simpler web payments: Introducing the Payment Request API](https://blogs.windows.com/msedgedev/2016/12/15) and the [Payment Request API](/microsoft-edge/dev-guide/device/payment-request-api) developer guide.</span></span>  

### <span data-ttu-id="82592-131">TCP 快速打开 (TFO) </span><span class="sxs-lookup"><span data-stu-id="82592-131">TCP Fast Open (TFO)</span></span>  
<span data-ttu-id="82592-132">TCP Fast Open 功能可减少打开 TCP 连接所需的往返次数，从而提高浏览器网络性能。</span><span class="sxs-lookup"><span data-stu-id="82592-132">TCP Fast Open is a feature that reduces the number of round trips required to open a TCP connection, improving browser networking performance.</span></span>  <span data-ttu-id="82592-133">有关更多详细信息，请参阅 [使用 TCP 快速打开构建更快、更安全的 web](https://blogs.windows.com/msedgedev/2016/06/15)。</span><span class="sxs-lookup"><span data-stu-id="82592-133">For more details, see [Building a faster and more secure web with TCP Fast Open](https://blogs.windows.com/msedgedev/2016/06/15).</span></span>  <span data-ttu-id="82592-134">由于各种网络拓扑中的互操作性差异，默认情况下，Microsoft Edge 中不支持此功能。</span><span class="sxs-lookup"><span data-stu-id="82592-134">Due to interoperability differences in various network topologies, this features is not enabled by default in Microsoft Edge.</span></span>  <span data-ttu-id="82592-135">若要启用它，请 `about:flags` 在地址栏中键入，然后选中 "启用**网络**" 部分下的 "**启用 TCP 快速打开**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="82592-135">To enable it, type `about:flags` in your address bar, and select the checkbox for **Enable TCP Fast Open** under the **Networking** section.</span></span>  

### <span data-ttu-id="82592-136">WebRTC 和互操作的 RTC 视频编解码器支持</span><span class="sxs-lookup"><span data-stu-id="82592-136">WebRTC and interoperable RTC video codec support</span></span>  

<span data-ttu-id="82592-137">EdgeHTML 15 支持 WebRTC 1.0 API 的子集，与使用 W3C WebRTC-PC API 2015 circa 的早期版本一起构建的应用程序的互操作性。</span><span class="sxs-lookup"><span data-stu-id="82592-137">EdgeHTML 15 supports a subset of the WebRTC 1.0 API for interoperability with applications built with earlier versions of the W3C WebRTC-PC API circa 2015.</span></span>  <span data-ttu-id="82592-138">有关详细信息，请参阅 [WEBRTC API 参考](/previous-versions//mt806139(v=vs.85)) 。</span><span class="sxs-lookup"><span data-stu-id="82592-138">See the [WebRTC API reference](/previous-versions//mt806139(v=vs.85)) for details.</span></span>  

<span data-ttu-id="82592-139">若要充分利用对等音频和视频通信中的最高级功能，建议使用 [对象实时通信) API](https://ortc.org)。</span><span class="sxs-lookup"><span data-stu-id="82592-139">To take advantage of our most advanced features in peer-to-peer audio and video communication, we recommend using the [Object Real-Time Communication) API](https://ortc.org).</span></span>  <span data-ttu-id="82592-140">对于你希望设置群组音频和视频呼叫或直接控制单个传输、发送方和接收方对象的情况，ORTC API 更适合。</span><span class="sxs-lookup"><span data-stu-id="82592-140">The ORTC API is better suited for situations where you want to set up group audio and video calls, or directly control individual transport, sender, and receiver objects.</span></span>  

<span data-ttu-id="82592-141">Microsoft Edge 支持1.0 和 WebRTC 的 AVC 和 VP8 视频，并提供以下功能来支持两种编解码器类型： [abs-发送时间](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)、 [goog-Remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)、 [图片损失指示和常规 NACK 反馈](https://tools.ietf.org/html/rfc4585)， [RTP 重新传输](https://tools.ietf.org/html/rfc4588)。</span><span class="sxs-lookup"><span data-stu-id="82592-141">The Microsoft Edge supports both H.264/AVC and VP8 video with ORTC and WebRTC 1.0, and provides the following features in support of both codec types: [abs-send-time](https://webrtc.org/experiments/rtp-hdrext/abs-send-time), [goog-remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03), [Picture Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [RTP Retransmission](https://tools.ietf.org/html/rfc4588).</span></span>  

<span data-ttu-id="82592-142">有关详细信息，请参阅 [在 Microsoft Edge 中介绍 WebRTC 1.0 和互操作实时通信](https://blogs.windows.com/msedgedev/2017/01/31)。</span><span class="sxs-lookup"><span data-stu-id="82592-142">For more info, see [Introducing WebRTC 1.0 and interoperable real-time communications in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31).</span></span>  

### <span data-ttu-id="82592-143">WebVR</span><span class="sxs-lookup"><span data-stu-id="82592-143">WebVR</span></span>  

<span data-ttu-id="82592-144">Microsoft Edge 现在支持 [WebVR](https://immersive-web.github.io/webxr)，即连接 Windows Mixed Reality head 挂载显示器和 Microsoft Edge 的实验 API。</span><span class="sxs-lookup"><span data-stu-id="82592-144">Microsoft Edge now has support for [WebVR](https://immersive-web.github.io/webxr), an experimental API that connects Windows Mixed Reality head mounted displays and Microsoft Edge.</span></span>  <span data-ttu-id="82592-145">此连接允许在网站中体验 VR 内容，这意味着沉浸式 VR 体验不再局限于桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="82592-145">This connection enables VR content to be experienced within a website, meaning immersive VR experiences are no longer limited to desktop applications.</span></span>  

<span data-ttu-id="82592-146">Microsoft Edge 中的虚拟现实由 WebGL （用于呈现3D 和2D 图形的 JavaScript API）提供支持。</span><span class="sxs-lookup"><span data-stu-id="82592-146">Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.</span></span>  <span data-ttu-id="82592-147">WebGL 支持 WebGL 库（如 BabylonJS）生成的应用程序和应用程序。</span><span class="sxs-lookup"><span data-stu-id="82592-147">WebGL applications and applications built with WebGL libraries like BabylonJS are supported.</span></span>  <span data-ttu-id="82592-148">连接后，WebVR 将发送与耳机周围的位置和传感器信息相对应的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="82592-148">Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.</span></span>  <span data-ttu-id="82592-149">WebVR API 还支持空间控制器，感谢使用 [游戏板 API](../dom/gamepad-api.md)的扩展。</span><span class="sxs-lookup"><span data-stu-id="82592-149">The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).</span></span>  <span data-ttu-id="82592-150">此 API 在默认情况下处于打开状态，因此无需切换标志。</span><span class="sxs-lookup"><span data-stu-id="82592-150">This API is on by default, so no need to toggle a flag.</span></span>  

<span data-ttu-id="82592-151">有关详细信息，请参阅 [WEBVR api 参考](/previous-versions//mt806281(v=vs.85)) 和 [游戏板 api 参考](https://developer.mozilla.org/docs/Web/API/Gamepad_API) 。</span><span class="sxs-lookup"><span data-stu-id="82592-151">See the [WebVR API reference](/previous-versions//mt806281(v=vs.85)) and [Gamepad API reference](https://developer.mozilla.org/docs/Web/API/Gamepad_API) for details.</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="82592-152">由于 WebVR 规范仍在开发中，Microsoft Edge 的实现可能会在行的后面更改。</span><span class="sxs-lookup"><span data-stu-id="82592-152">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="82592-153">更新的功能</span><span class="sxs-lookup"><span data-stu-id="82592-153">Updated features</span></span>  

### <span data-ttu-id="82592-154">内容安全策略 (级别 2) </span><span class="sxs-lookup"><span data-stu-id="82592-154">Content Security Policy (Level 2)</span></span>  

<span data-ttu-id="82592-155">已使用 CSP 1 的网站应继续与对 CSP 2 的 Microsoft Edge 支持配合使用，但最好切换 `frame-src` 将工作脚本加载到新指令的任何指令，以便 `child-src` 在以后对您的网站进行校对。</span><span class="sxs-lookup"><span data-stu-id="82592-155">Sites already using CSP 1 should continue to work with Microsoft Edge support for CSP 2, however it's best to switch any `frame-src` directives that load worker scripts to the new `child-src` directive to future-proof your site.</span></span>  <span data-ttu-id="82592-156">\ (在 CSP 3 中， `frame-src` 将不再适用于工作人员。 \n ) CSP 2 也会添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="82592-156">\(In CSP 3, `frame-src` will no longer apply to workers.\) CSP 2 also adds the following:</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="82592-157">新指令</span><span class="sxs-lookup"><span data-stu-id="82592-157">New directives</span></span>  
   :::column-end:::
   :::column span="2":::
      `base-uri`<span data-ttu-id="82592-158">、 `child-src` 、 `form-action` `frame-ancestors` 和 `plugin-types` 。</span><span class="sxs-lookup"><span data-stu-id="82592-158">, `child-src`, `form-action`, `frame-ancestors` and `plugin-types`.</span></span>  <span data-ttu-id="82592-159">有关详细信息，请参阅 [Microsoft Edge 支持的 CSP 指令](../security/content-security-policy.md) 。</span><span class="sxs-lookup"><span data-stu-id="82592-159">See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="82592-160">工作人员支持</span><span class="sxs-lookup"><span data-stu-id="82592-160">Workers support</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="82592-161">后台辅助脚本由其自己的策略控制，与加载它们的文档的策略不同。</span><span class="sxs-lookup"><span data-stu-id="82592-161">Background worker scripts are governed by their own policy, separate from the policy of the document loading them.</span></span>  <span data-ttu-id="82592-162">对于主文档，您可以在响应标题中为工作人员设置 CSP。</span><span class="sxs-lookup"><span data-stu-id="82592-162">As with host documents, you can set the CSP for a worker in the response header.</span></span>  <span data-ttu-id="82592-163">CSP 2 中的新增功能也是该  `allow-scripts` `allow-same-origin` 指令的标志 `sandbox` 现在会影响工作线程创建。</span><span class="sxs-lookup"><span data-stu-id="82592-163">Also new in CSP 2 is that  `allow-scripts` and `allow-same-origin` flags of the `sandbox` directive now affect worker thread creation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="82592-164">内联脚本和样式</span><span class="sxs-lookup"><span data-stu-id="82592-164">Inline scripts and styles</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="82592-165">CSP 2 允许通过提供 nonces 和哈希作为允许列表机制来执行内联脚本和样式块。</span><span class="sxs-lookup"><span data-stu-id="82592-165">CSP 2 allows for the execution of inline scripts and style blocks by providing nonces and hashes as a allow-listing mechanism.</span></span>  <span data-ttu-id="82592-166">Nonces 是在 CSP 策略和页面的脚本标记中出现的每个页面加载上生成的随机 base 64 值。</span><span class="sxs-lookup"><span data-stu-id="82592-166">Nonces are random base-64 values generated on each page load that appears in both the CSP policy and in the script tags in the page.</span></span>  <span data-ttu-id="82592-167">当页面在加载时动态生成时，服务器将生成 nonce 值，将其插入到页面中的 NonceToken，并在内容安全策略 HTTP 标头中声明它。</span><span class="sxs-lookup"><span data-stu-id="82592-167">When the page is dynamically generated on load, the server generates a nonce value, inserts it into the NonceToken in the page and also declares it in the Content Security Policy HTTP header.</span></span>  <span data-ttu-id="82592-168">哈希是使用 sha384 或 sha512 算法 \ ) 从在 `<script>` `<style>` `script-src` `style-src` CSP 策略中使用或指令 \ ) 指定 \ (或元素的内容 (生成的静态值。</span><span class="sxs-lookup"><span data-stu-id="82592-168">Hashes are static values generated \(using sha256, sha384 or sha512 algorithms\) from the content of a `<script>` or `<style>` element that are then specified \(using `script-src` or `style-src` directives\) in the CSP policy.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="82592-169">CSP 违反报告</span><span class="sxs-lookup"><span data-stu-id="82592-169">CSP violation reporting</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="82592-170">新事件 `SecurityPolicyViolationEvent` 现将在 CSP 违规时触发。</span><span class="sxs-lookup"><span data-stu-id="82592-170">A new event, `SecurityPolicyViolationEvent` is now fired upon CSP violations.</span></span>  <span data-ttu-id="82592-171">CSP 报告的早期机制 `report-uri` 继续受支持。</span><span class="sxs-lookup"><span data-stu-id="82592-171">The earlier mechanism for CSP reporting, `report-uri`, continues to be supported.</span></span>  <span data-ttu-id="82592-172">已向冲突报告添加了多个新字段，其中包含 `effectiveDirective` 违反 ) 的策略 \ (， `statusCode` \ (HTTP 响应代码 \ ) ，\ (了有问题的 `sourceFile` 资源的 URL \ ) 、 `lineNumber` 和 `columnNumber` 。</span><span class="sxs-lookup"><span data-stu-id="82592-172">Several new fields have been added to the violation reports common to both, including `effectiveDirective` \(the policy that was violated\), `statusCode` \(the HTTP response code\), `sourceFile` \(the URL of the offending resource\), `lineNumber`, and `columnNumber`.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="82592-173">Web 身份验证</span><span class="sxs-lookup"><span data-stu-id="82592-173">Web Authentication</span></span>  

<span data-ttu-id="82592-174">使用[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生物识别的新兴[WEB 身份验证 API](../device/web-authentication.md)的 Microsoft Edge 支持已更新，但具有以下更改：</span><span class="sxs-lookup"><span data-stu-id="82592-174">Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:</span></span>  

*   <span data-ttu-id="82592-175">[EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) (Windows 10 周年更新、内部版本10240、7/2016 \ )  (通过 MSCredentials 接口 \ ) 公开了[MSCredentials](/previous-versions//mt697639(v=vs.85))接口 \ 中引入的实验性 Web 身份验证 API 的初始实现。</span><span class="sxs-lookup"><span data-stu-id="82592-175">The initial implementation of the experimental Web Authentication API introduced in [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update, build 10240, 7/2016\) was exposed through MS- prefixed APIs \(the [MSCredentials](/previous-versions//mt697639(v=vs.85)) interface\).</span></span>  <span data-ttu-id="82592-176">虽然这些 Api 在 EdgeHTML 15 中仍然可用，但它们现在已被弃用，取而代之的是在规范的 [更新快照](https://w3.org/TR/2016/WD-webauthn-20160928) 中定义的非前缀、基于标准的 api 和行为，并且可能会在规范逐渐提高标准化时继续进行更改。</span><span class="sxs-lookup"><span data-stu-id="82592-176">While these APIs are still available in EdgeHTML 15, they are now deprecated in favor of the non-prefixed, standards-based APIs and behaviors defined in a more [recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928) of the specification, and are likely to continue changing as the spec matures toward standardization.</span></span>  

*   <span data-ttu-id="82592-177">默认情况下，最新的 Microsoft Edge 实现处于关闭状态，并在您的地址栏中输入 "标志 \ (" `about:flags` 以打开功能 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="82592-177">The latest Microsoft Edge implementation is turned off by default and ships behind a flag \(type `about:flags` in your address bar to turn on the feature\).</span></span>  

*   <span data-ttu-id="82592-178">Microsoft Edge 尚不支持诸如 USB 密钥或蓝牙设备之类的外部凭据。</span><span class="sxs-lookup"><span data-stu-id="82592-178">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span>  <span data-ttu-id="82592-179">当前 API 仅限于 TPM 中存储的嵌入凭据。</span><span class="sxs-lookup"><span data-stu-id="82592-179">The current API is limited to embedded credentials stored in the TPM.</span></span>  <span data-ttu-id="82592-180">如果 TPM 在设备上不可用，则使用软件回退。</span><span class="sxs-lookup"><span data-stu-id="82592-180">A software fallback is used if TPM is not available on the device.</span></span>  

*   <span data-ttu-id="82592-181">当前登录的 Windows 用户帐户必须配置为至少支持 PIN，并且最好是指纹或指纹生物识别。</span><span class="sxs-lookup"><span data-stu-id="82592-181">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span>  <span data-ttu-id="82592-182">这是为了确保 Windows 可以对 TPM 的访问进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="82592-182">This is to ensure that Windows can authenticate the access to the TPM.</span></span>  

*   <span data-ttu-id="82592-183">在规范中介绍的 [预定义扩展](https://w3.org/TR/webauthn/#extension-predef) ，Microsoft Edge 仅支持 [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (`webauthn_txAuthSimple` \ ) 。</span><span class="sxs-lookup"><span data-stu-id="82592-183">Of the [predefined extensions](https://w3.org/TR/webauthn/#extension-predef) described in the spec, Microsoft Edge only supports the [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(`webauthn_txAuthSimple`\) at this time.</span></span>  

*  <span data-ttu-id="82592-184">该 `timeoutSeconds` 选项当前未评估</span><span class="sxs-lookup"><span data-stu-id="82592-184">The `timeoutSeconds` option is not currently evaluated</span></span>  

### <span data-ttu-id="82592-185">WebDriver</span><span class="sxs-lookup"><span data-stu-id="82592-185">WebDriver</span></span>  

<span data-ttu-id="82592-186">EdgeHTML 15 提供少量的 WebDriver 更新，包括对无声命令行标志和新命令终结点的支持：</span><span class="sxs-lookup"><span data-stu-id="82592-186">EdgeHTML 15 brings a handful of WebDriver updates including support for the silent command line flag and new command endpoints:</span></span>  

| <span data-ttu-id="82592-187">方法</span><span class="sxs-lookup"><span data-stu-id="82592-187">Method</span></span> | <span data-ttu-id="82592-188">URI 模板</span><span class="sxs-lookup"><span data-stu-id="82592-188">URI Template</span></span> | <span data-ttu-id="82592-189">命令</span><span class="sxs-lookup"><span data-stu-id="82592-189">Command</span></span> |  
|:--- |:---  |:--- |    
| <span data-ttu-id="82592-190">POST</span><span class="sxs-lookup"><span data-stu-id="82592-190">POST</span></span> | <span data-ttu-id="82592-191">/session/{session id}/alert/accept</span><span class="sxs-lookup"><span data-stu-id="82592-191">/session/{session id}/alert/accept</span></span> | [<span data-ttu-id="82592-192">接受通知</span><span class="sxs-lookup"><span data-stu-id="82592-192">Accept Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| <span data-ttu-id="82592-193">POST</span><span class="sxs-lookup"><span data-stu-id="82592-193">POST</span></span> | <span data-ttu-id="82592-194">/session/{session id}/alert/dismiss</span><span class="sxs-lookup"><span data-stu-id="82592-194">/session/{session id}/alert/dismiss</span></span> | [<span data-ttu-id="82592-195">消除警告</span><span class="sxs-lookup"><span data-stu-id="82592-195">Dismiss Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| <span data-ttu-id="82592-196">GET</span><span class="sxs-lookup"><span data-stu-id="82592-196">GET</span></span> | <span data-ttu-id="82592-197">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="82592-197">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="82592-198">获取通知文本</span><span class="sxs-lookup"><span data-stu-id="82592-198">Get Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| <span data-ttu-id="82592-199">POST</span><span class="sxs-lookup"><span data-stu-id="82592-199">POST</span></span> | <span data-ttu-id="82592-200">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="82592-200">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="82592-201">发送提醒文本</span><span class="sxs-lookup"><span data-stu-id="82592-201">Send Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| <span data-ttu-id="82592-202">POST</span><span class="sxs-lookup"><span data-stu-id="82592-202">POST</span></span> | <span data-ttu-id="82592-203">/session/{session id}/execute/async</span><span class="sxs-lookup"><span data-stu-id="82592-203">/session/{session id}/execute/async</span></span> | [<span data-ttu-id="82592-204">执行异步脚本</span><span class="sxs-lookup"><span data-stu-id="82592-204">Execute Async Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| <span data-ttu-id="82592-205">POST</span><span class="sxs-lookup"><span data-stu-id="82592-205">POST</span></span> | <span data-ttu-id="82592-206">/session/{session id}/execute/sync</span><span class="sxs-lookup"><span data-stu-id="82592-206">/session/{session id}/execute/sync</span></span> | [<span data-ttu-id="82592-207">执行脚本</span><span class="sxs-lookup"><span data-stu-id="82592-207">Execute Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| <span data-ttu-id="82592-208">GET</span><span class="sxs-lookup"><span data-stu-id="82592-208">GET</span></span> | <span data-ttu-id="82592-209">/session/{session id}/window</span><span class="sxs-lookup"><span data-stu-id="82592-209">/session/{session id}/window</span></span> | [<span data-ttu-id="82592-210">获取窗口句柄</span><span class="sxs-lookup"><span data-stu-id="82592-210">Get Window Handle</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| <span data-ttu-id="82592-211">GET</span><span class="sxs-lookup"><span data-stu-id="82592-211">GET</span></span> | <span data-ttu-id="82592-212">/session/{session id}/window/handles</span><span class="sxs-lookup"><span data-stu-id="82592-212">/session/{session id}/window/handles</span></span> | [<span data-ttu-id="82592-213">获取窗口句柄</span><span class="sxs-lookup"><span data-stu-id="82592-213">Get Window Handles</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

<span data-ttu-id="82592-214">有关详细信息以及其他 WebDriver 功能的状态，请参阅 [WebDriver](../../webdriver.md)。</span><span class="sxs-lookup"><span data-stu-id="82592-214">For more info and the status of other WebDriver features, check out [WebDriver](../../webdriver.md).</span></span>  

## <span data-ttu-id="82592-215">EdgeHTML 15 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="82592-215">New APIs in EdgeHTML 15</span></span>  

<span data-ttu-id="82592-216">下面是 EdgeHTML 15 中新 Api 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="82592-216">Here's the full list of new APIs in EdgeHTML 15.</span></span>  <span data-ttu-id="82592-217">它们以的格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="82592-217">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='582' scrolling='no' title='<span data-ttu-id="82592-218">新的 EdgeHTML15 Api</span><span class="sxs-lookup"><span data-stu-id="82592-218">New EdgeHTML15 APIs</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="82592-219">请参阅 <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> </a> Microsoft Edge 文档 (<a href='http://codepen.io/MicrosoftEdgeDocumentation'> @MicrosoftEdgeDocumentation </a>) 上的 "CodePen" 中 <a href='http://codepen.io'> </a> 的 "新 EdgeHTML15 api"。</span><span class="sxs-lookup"><span data-stu-id="82592-219">See the Pen <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'>New EdgeHTML15 APIs</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="82592-220">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="82592-220">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="82592-221">EdgeHTML 12/Windows 内部版本 10240 (7/2015) </span><span class="sxs-lookup"><span data-stu-id="82592-221">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="82592-222">EdgeHTML 13/Windows 内部版本 10586 (11/2015) </span><span class="sxs-lookup"><span data-stu-id="82592-222">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="82592-223">EdgeHTML 14/Windows 内部版本 14393 (8/2016) </span><span class="sxs-lookup"><span data-stu-id="82592-223">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  
