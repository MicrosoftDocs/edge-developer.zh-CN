---
description: 本指南概述了 EdgeHTML 15 中包括的开发人员功能和标准。
title: EdgeHTML 15 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.custom: seodec18
ms.openlocfilehash: 4febe4be1fce29207de7a57b61d96eae0a5c02ab
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941922"
---
# <span data-ttu-id="aa4c7-104">EdgeHTML 15 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="aa4c7-104">What's new in EdgeHTML 15</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="aa4c7-105">截止到下面，截止到 [Windows 10 创意者](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) 更新 \ (04/2017（内部版本 15063\) ），当前发布的 Microsoft Edge 平台随即发布的更改。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-105">Here are the changes shipped with the current release of the Microsoft Edge platform, as of the [Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, Build 15063\).</span></span>  <span data-ttu-id="aa4c7-106">有关 Microsoft Edge 浏览器的整体更改的概述，请参阅 [Windows 10 创意者更新中 Microsoft Edge 中的新增功能](https://blogs.windows.com/msedgedev/2017/04/11)。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-106">For an overview of changes to the overall Microsoft Edge browser, see [What's new in Microsoft Edge in the Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11).</span></span>  

<span data-ttu-id="aa4c7-107">有关随后的 Windows Insider Preview 版本中的更改，请参阅 [EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-107">For changes in subsequent Windows Insider Preview builds, see [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="aa4c7-108">下面是下列更改列表的句号  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md) ：。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-108">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md).</span></span>  

## <span data-ttu-id="aa4c7-109">新增功能</span><span class="sxs-lookup"><span data-stu-id="aa4c7-109">New features</span></span>  

### <span data-ttu-id="aa4c7-110">CSS 自定义属性</span><span class="sxs-lookup"><span data-stu-id="aa4c7-110">CSS Custom Properties</span></span>  

<span data-ttu-id="aa4c7-111">Microsoft Edge 现在支持 [CSS 自定义属性，即](https://drafts.csswg.org/css-variables)一个.k.a CSS 变量。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-111">Microsoft Edge now supports [CSS Custom Properties](https://drafts.csswg.org/css-variables), a.k.a CSS Variables.</span></span>  <span data-ttu-id="aa4c7-112">CSS 变量允许您创建自定义 CSS 属性，这些属性可在整个样式表中重复使用，以帮助减少重复数据量，如重复颜色。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-112">CSS Variables allow you to create custom CSS properties that can be reused throughout stylesheets to help reduce the amount of duplicate data, like repeated colors.</span></span>  <span data-ttu-id="aa4c7-113">使用 CSS 变量非常简单：</span><span class="sxs-lookup"><span data-stu-id="aa4c7-113">Using CSS Variables is simple:</span></span>  

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

### <span data-ttu-id="aa4c7-114">交section Ob服务器</span><span class="sxs-lookup"><span data-stu-id="aa4c7-114">Intersection Observer</span></span>  

<span data-ttu-id="aa4c7-115">EdgeHTML 15 引入了 [交集 Ob 服务器 API](https://w3c.github.io/IntersectionObserver) 规范。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-115">EdgeHTML 15 introduces the [Intersection Observer API](https://w3c.github.io/IntersectionObserver) specification.</span></span>  <span data-ttu-id="aa4c7-116">利用交集 Observer API，你可以异步查询相对其他元素或全局视区的 DOM 元素的位置和可见性。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-116">The Intersection Observer API allows you to asynchronously query the position and visibility of DOM elements relative to other elements or the global viewport.</span></span>  <span data-ttu-id="aa4c7-117">此 API 不需要通过创建一个高效地在视图中通知元素的方法，从而消除了自定义很高代码的需要。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-117">This API eliminates the need for custom expensive code by creating a method to efficiently notify elements when they are in view.</span></span>  

### <span data-ttu-id="aa4c7-118">JavaScript</span><span class="sxs-lookup"><span data-stu-id="aa4c7-118">JavaScript</span></span>  

<span data-ttu-id="aa4c7-119">性能优化将使 EdgeHTML 15 复习 JavaScript 引子具有大概括视。这将使其占用大概括状态。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-119">Performance optimizations take center stage with the EdgeHTML 15 rev of the Chakra JavaScript engine.</span></span>  <span data-ttu-id="aa4c7-120">通过 Windows 10 创意者更新，Chakra 通过重新演示函数并优化堆参数来节省内存，并提高缩小代码的性能。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-120">With the Windows 10 Creators Update, Chakra saves memory by re-deferring functions and optimizing away heap arguments and improves performance for minified code.</span></span>  

<span data-ttu-id="aa4c7-121">此外，EdgeHTML 15 引入了以下功能预览：</span><span class="sxs-lookup"><span data-stu-id="aa4c7-121">Additionally, EdgeHTML 15 introduces the following feature previews:</span></span>  

#### <span data-ttu-id="aa4c7-122">实质 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="aa4c7-122">Experimental JavaScript features</span></span>  

<span data-ttu-id="aa4c7-123">与</span><span class="sxs-lookup"><span data-stu-id="aa4c7-123">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="aa4c7-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \ ([demo](https://webassembly.org/demo)\) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="aa4c7-125">共享内存和原子</span><span class="sxs-lookup"><span data-stu-id="aa4c7-125">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

<span data-ttu-id="aa4c7-126">若要 [进一步细节，请参阅 Microsoft Edge 中改进的 JavaScript 性能、WebAssembly](https://blogs.windows.com/msedgedev/2017/04/20) 和共享内存。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-126">See [Improved JavaScript performance, WebAssembly, and Shared Memory in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/04/20) for further details.</span></span>  

### <span data-ttu-id="aa4c7-127">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="aa4c7-127">Payment Request API</span></span>  

<span data-ttu-id="aa4c7-128">[现支持付款请求 API，](https://w3.org/TR/payment-request)从而在 Windows 10 电脑和手机上的 Web 上支持更加简单的结账和付款。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-128">The [Payment Request API](https://w3.org/TR/payment-request) is now supported, enabling simpler checkout and payments on the web on Windows 10 PCs and Phones.</span></span>  <span data-ttu-id="aa4c7-129">此 API 使 Microsoft Edge 能够成为商业、消费者和支付方式 \ (的用户存储在云中的中介方式。<) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-129">This API enables Microsoft Edge to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="aa4c7-130">有关付款请求 API 的详细信息，请查明较为简单的 [Web 付款：](https://blogs.windows.com/msedgedev/2016/12/15) 付款请求 API 和付 [款请求 API 开发](/microsoft-edge/dev-guide/device/payment-request-api) 人员指南。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-130">For more information on the Payment Request API, check out [Simpler web payments: Introducing the Payment Request API](https://blogs.windows.com/msedgedev/2016/12/15) and the [Payment Request API](/microsoft-edge/dev-guide/device/payment-request-api) developer guide.</span></span>  

### <span data-ttu-id="aa4c7-131">TCP 快速打开 TCP (TFO) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-131">TCP Fast Open (TFO)</span></span>  
<span data-ttu-id="aa4c7-132">TCP 快速打开功能可减少打开 TCP 连接和提高浏览器网络性能所需的跨口行程的功能。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-132">TCP Fast Open is a feature that reduces the number of round trips required to open a TCP connection, improving browser networking performance.</span></span>  <span data-ttu-id="aa4c7-133">有关详细信息，请参阅"使用 [TCP](https://blogs.windows.com/msedgedev/2016/06/15)快速打开"更快、更安全的 Web。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-133">For more details, see [Building a faster and more secure web with TCP Fast Open](https://blogs.windows.com/msedgedev/2016/06/15).</span></span>  <span data-ttu-id="aa4c7-134">由于各种网络拓扑的互操作性差异，Microsoft Edge 默认未启用此功能。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-134">Due to interoperability differences in various network topologies, this features is not enabled by default in Microsoft Edge.</span></span>  <span data-ttu-id="aa4c7-135">要启用此功能， `about:flags` 请在地址栏中键入，然后选中"启用 **TCP 快捷方式"的复选框，在"** 网络"部分下选择"启用 TCP 快速 **打开** "。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-135">To enable it, type `about:flags` in your address bar, and select the checkbox for **Enable TCP Fast Open** under the **Networking** section.</span></span>  

### <span data-ttu-id="aa4c7-136">WebRTC 和可互操作的 RTC 视频编解码器支持</span><span class="sxs-lookup"><span data-stu-id="aa4c7-136">WebRTC and interoperable RTC video codec support</span></span>  

<span data-ttu-id="aa4c7-137">EdgeHTML 15 支持 WebRTC 1.0 API 的子集，用于与使用早期版本 W3C WebRTC-PC API 线 2015 较早版本生成的应用程序进行互操作性。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-137">EdgeHTML 15 supports a subset of the WebRTC 1.0 API for interoperability with applications built with earlier versions of the W3C WebRTC-PC API circa 2015.</span></span>  <span data-ttu-id="aa4c7-138">有关详细信息， [请参阅 WebRTC API](/previous-versions//mt806139(v=vs.85)) 参考。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-138">See the [WebRTC API reference](/previous-versions//mt806139(v=vs.85)) for details.</span></span>  

<span data-ttu-id="aa4c7-139">为了利用对等音频和视频通信中最高级的功能，我们建议使用[API 实时通) API。](https://ortc.org)</span><span class="sxs-lookup"><span data-stu-id="aa4c7-139">To take advantage of our most advanced features in peer-to-peer audio and video communication, we recommend using the [Object Real-Time Communication) API](https://ortc.org).</span></span>  <span data-ttu-id="aa4c7-140">ORTC API 更适合需要设置组音频和视频调用，或者直接控制各个传输、发送方和接收器对象。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-140">The ORTC API is better suited for situations where you want to set up group audio and video calls, or directly control individual transport, sender, and receiver objects.</span></span>  

<span data-ttu-id="aa4c7-141">Microsoft Edge 支持具有 ORTC 和 WebRTC 1.0 的 H.264/AVC 和 VP8 视频，同时也支持以下两种支持以下功能[：abs-发送时](https://webrtc.org/experiments/rtp-hdrext/abs-send-time)[、Goog-Remb、Picture](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03) [Loss 指示和一套 NACK 反转](https://tools.ietf.org/html/rfc4585)[;RTP 回转](https://tools.ietf.org/html/rfc4588)。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-141">The Microsoft Edge supports both H.264/AVC and VP8 video with ORTC and WebRTC 1.0, and provides the following features in support of both codec types: [abs-send-time](https://webrtc.org/experiments/rtp-hdrext/abs-send-time), [goog-remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03), [Picture Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [RTP Retransmission](https://tools.ietf.org/html/rfc4588).</span></span>  

<span data-ttu-id="aa4c7-142">有关详细信息，请参阅介绍 [Microsoft Edge 中的 WebRTC 1.0](https://blogs.windows.com/msedgedev/2017/01/31)和可互操作实时通信。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-142">For more info, see [Introducing WebRTC 1.0 and interoperable real-time communications in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31).</span></span>  

### <span data-ttu-id="aa4c7-143">WebVR</span><span class="sxs-lookup"><span data-stu-id="aa4c7-143">WebVR</span></span>  

<span data-ttu-id="aa4c7-144">Microsoft Edge 现在支持 [WebVR，它](https://immersive-web.github.io/webxr)是一种可将 Windows Mixed Reality 头像建广的实例 API 连接到 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-144">Microsoft Edge now has support for [WebVR](https://immersive-web.github.io/webxr), an experimental API that connects Windows Mixed Reality head mounted displays and Microsoft Edge.</span></span>  <span data-ttu-id="aa4c7-145">此连接使 VR 内容能够在网站中体验，这意味着沉缩 VR 体验不再限于桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-145">This connection enables VR content to be experienced within a website, meaning immersive VR experiences are no longer limited to desktop applications.</span></span>  

<span data-ttu-id="aa4c7-146">Microsoft Edge 中的虚拟现实由 WebGL 提供支持，这是一种用于呈现 3D 和 2D 图形的 JavaScript API。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-146">Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.</span></span>  <span data-ttu-id="aa4c7-147">支持使用 WebGL 库（如 BabylonJS）构建的 WebGL 应用程序和应用程序。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-147">WebGL applications and applications built with WebGL libraries like BabylonJS are supported.</span></span>  <span data-ttu-id="aa4c7-148">连接后，WebVR 将在耳机前发送与位置和传感器信息相对应的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-148">Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.</span></span>  <span data-ttu-id="aa4c7-149">与游戏板 API 的扩展，WebVR API 还支持单 [位控制器](../dom/gamepad-api.md)。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-149">The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).</span></span>  <span data-ttu-id="aa4c7-150">此 API 默认处于开机状态，因此无需切换标志。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-150">This API is on by default, so no need to toggle a flag.</span></span>  

<span data-ttu-id="aa4c7-151">有关详细信息， [请参阅 WebVR API](/previous-versions//mt806281(v=vs.85)) [参考和游戏](https://developer.mozilla.org/docs/Web/API/Gamepad_API) 板 API 参考。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-151">See the [WebVR API reference](/previous-versions//mt806281(v=vs.85)) and [Gamepad API reference](https://developer.mozilla.org/docs/Web/API/Gamepad_API) for details.</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="aa4c7-152">由于 WebVR 规范仍在开发中，所以 Microsoft Edge 的实现可能会在以后更改。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-152">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="aa4c7-153">更新的功能</span><span class="sxs-lookup"><span data-stu-id="aa4c7-153">Updated features</span></span>  

### <span data-ttu-id="aa4c7-154">内容安全策略 (2 级) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-154">Content Security Policy (Level 2)</span></span>  

<span data-ttu-id="aa4c7-155">已在使用 CSP 1 使用的网站可继续使用 CSP 2 的 Microsoft Edge 支持，但是最好将负载工作词转化为 `frame-src` 新的 `child-src` 指令，再以后校对您的网站校对。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-155">Sites already using CSP 1 should continue to work with Microsoft Edge support for CSP 2, however it's best to switch any `frame-src` directives that load worker scripts to the new `child-src` directive to future-proof your site.</span></span>  <span data-ttu-id="aa4c7-156">\ (In CSP 3 `frame-src` 中，将不再适用于工作者.\) CSP 2 也添加以下内容：</span><span class="sxs-lookup"><span data-stu-id="aa4c7-156">\(In CSP 3, `frame-src` will no longer apply to workers.\) CSP 2 also adds the following:</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="aa4c7-157">新的指令</span><span class="sxs-lookup"><span data-stu-id="aa4c7-157">New directives</span></span>  
   :::column-end:::
   :::column span="2":::
      `base-uri`<span data-ttu-id="aa4c7-158">、、 `child-src` `form-action` 和 `frame-ancestors` `plugin-types` .</span><span class="sxs-lookup"><span data-stu-id="aa4c7-158">, `child-src`, `form-action`, `frame-ancestors` and `plugin-types`.</span></span>  <span data-ttu-id="aa4c7-159">有关详细信息 [，请参阅 Microsoft Edge 支持的 CSP 指](../security/content-security-policy.md) 令。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-159">See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="aa4c7-160">Workers 支持</span><span class="sxs-lookup"><span data-stu-id="aa4c7-160">Workers support</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="aa4c7-161">后台工作者脚本受其自己的策略保护，独立于文档加载它们的策略。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-161">Background worker scripts are governed by their own policy, separate from the policy of the document loading them.</span></span>  <span data-ttu-id="aa4c7-162">与主机文档一然，你可以在响应头中为工作者设置 CSP。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-162">As with host documents, you can set the CSP for a worker in the response header.</span></span>  <span data-ttu-id="aa4c7-163">此外，在 CSP 2 中新增了这一新增内容，指令的标志  `allow-scripts` `allow-same-origin` `sandbox` 现在会影响创建工作线程。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-163">Also new in CSP 2 is that  `allow-scripts` and `allow-same-origin` flags of the `sandbox` directive now affect worker thread creation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="aa4c7-164">嵌入脚本和样式</span><span class="sxs-lookup"><span data-stu-id="aa4c7-164">Inline scripts and styles</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="aa4c7-165">CSP 2 允许通过将 nonce 和哈希作为白名机制提供来允许执行内联脚本和样式块。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-165">CSP 2 allows for the execution of inline scripts and style blocks by providing nonces and hashes as a whitelisting mechanism.</span></span>  <span data-ttu-id="aa4c7-166">Nonce 是在每个页面加载上生成的随机 base-64 值，该值同时出现在 CSP 策略和页面的脚本标记中。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-166">Nonces are random base-64 values generated on each page load that appears in both the CSP policy and in the script tags in the page.</span></span>  <span data-ttu-id="aa4c7-167">当在加载时以动态方式生成页面时，服务器将生成一个 nonce 值，将其插入到页面的 NonceToken 中，并在内容安全策略 HTTP 标头中声明了该页面。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-167">When the page is dynamically generated on load, the server generates a nonce value, inserts it into the NonceToken in the page and also declares it in the Content Security Policy HTTP header.</span></span>  <span data-ttu-id="aa4c7-168">哈希 (是通过 sha256、sha384 或 sha512 算法\) 在 CSP 策略中通过 `<script>` `<style>` 或指令\) 指定 \ (指定的静态 `script-src` `style-src` 值。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-168">Hashes are static values generated \(via sha256, sha384 or sha512 algorithms\) from the content of a `<script>` or `<style>` element that are then specified \(via `script-src` or `style-src` directives\) in the CSP policy.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="aa4c7-169">CSP 协议报告</span><span class="sxs-lookup"><span data-stu-id="aa4c7-169">CSP violation reporting</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="aa4c7-170">现在，在 `SecurityPolicyViolationEvent` CSP 值分音时引发新事件。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-170">A new event, `SecurityPolicyViolationEvent` is now fired upon CSP violations.</span></span>  <span data-ttu-id="aa4c7-171">继续支持上述 CSP 报告的 `report-uri` 更早机制。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-171">The earlier mechanism for CSP reporting, `report-uri`, continues to be supported.</span></span>  <span data-ttu-id="aa4c7-172">几个新字段已添加到两者通用报告中， `effectiveDirective` 包括 \ (的分布情况 ) 报告 \、\ (`statusCode` THE HTTP response code\) 、\ (`sourceFile` the offending resource\) ， `lineNumber` and `columnNumber` .</span><span class="sxs-lookup"><span data-stu-id="aa4c7-172">Several new fields have been added to the violation reports common to both, including `effectiveDirective` \(the policy that was violated\), `statusCode` \(the HTTP response code\), `sourceFile` \(the URL of the offending resource\), `lineNumber`, and `columnNumber`.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="aa4c7-173">Web 身份验证</span><span class="sxs-lookup"><span data-stu-id="aa4c7-173">Web Authentication</span></span>  

<span data-ttu-id="aa4c7-174">已使用[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生物识别扩展[Web 身份验证 API](../device/web-authentication.md)的 Microsoft Edge 支持已进行了如下更改：</span><span class="sxs-lookup"><span data-stu-id="aa4c7-174">Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:</span></span>  

*   <span data-ttu-id="aa4c7-175">在 EdgeHTML 14 \ (Windows 10 周年更新（版本 10240、7/2016\) 公开了 MS - 前缀 API \ ([MSCredentials](/previous-versions//mt697639(v=vs.85))接口\) 中引入的实际实现。 [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04)</span><span class="sxs-lookup"><span data-stu-id="aa4c7-175">The initial implementation of the experimental Web Authentication API introduced in [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update, build 10240, 7/2016\) was exposed through MS- prefixed APIs \(the [MSCredentials](/previous-versions//mt697639(v=vs.85)) interface\).</span></span>  <span data-ttu-id="aa4c7-176">虽然这些 API 仍在 EdgeHTML 15 中可用，但这些 API 现已不支持以标准前缀的、基于标准的 API 和行为（ [以更加](https://w3.org/TR/2016/WD-webauthn-20160928) 高的规范的规范的形式定义）来弃用，并且可能随着标准化的规范的规格不断变化而继续更改。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-176">While these APIs are still available in EdgeHTML 15, they are now deprecated in favor of the non-prefixed, standards-based APIs and behaviors defined in a more [recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928) of the specification, and are likely to continue changing as the spec matures toward standardization.</span></span>  

*   <span data-ttu-id="aa4c7-177">默认，最新的 Microsoft Edge 实现处于关闭状态，并以开启该功能\ (`about:flags` ) 。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-177">The latest Microsoft Edge implementation is turned off by default and ships behind a flag \(type `about:flags` in your address bar to turn on the feature\).</span></span>  

*   <span data-ttu-id="aa4c7-178">Microsoft Edge 尚不支持 USB 密钥或移动设备等外部 Bluetooth凭据。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-178">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span>  <span data-ttu-id="aa4c7-179">当前 API 仅限于嵌入存储在 TPM 中的凭据。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-179">The current API is limited to embedded credentials stored in the TPM.</span></span>  <span data-ttu-id="aa4c7-180">如果 TPM 在设备上不可用，则使用软件回退。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-180">A software fallback is used if TPM is not available on the device.</span></span>  

*   <span data-ttu-id="aa4c7-181">Windows 用户帐户必须配置为至少支持 PIN，最好是正面或指纹生物识别。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-181">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span>  <span data-ttu-id="aa4c7-182">这是为了确保 Windows 可以对 TPM 的访问进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-182">This is to ensure that Windows can authenticate the access to the TPM.</span></span>  

*   <span data-ttu-id="aa4c7-183">在 [本机中描述的预](https://w3.org/TR/webauthn/#extension-predef) 定义扩展中，Microsoft Edge 此时仅支持 [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (`webauthn_txAuthSimple` \) 。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-183">Of the [predefined extensions](https://w3.org/TR/webauthn/#extension-predef) described in the spec, Microsoft Edge only supports the [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(`webauthn_txAuthSimple`\) at this time.</span></span>  

*  <span data-ttu-id="aa4c7-184">`timeoutSeconds`该选项当前未进行求值</span><span class="sxs-lookup"><span data-stu-id="aa4c7-184">The `timeoutSeconds` option is not currently evaluated</span></span>  

### <span data-ttu-id="aa4c7-185">WebDriver</span><span class="sxs-lookup"><span data-stu-id="aa4c7-185">WebDriver</span></span>  

<span data-ttu-id="aa4c7-186">EdgeHTML 15 带来了少量 WebDriver 更新，包括对静色命令行标志和新命令终结点的支持：</span><span class="sxs-lookup"><span data-stu-id="aa4c7-186">EdgeHTML 15 brings a handful of WebDriver updates including support for the silent command line flag and new command endpoints:</span></span>  

| <span data-ttu-id="aa4c7-187">方法</span><span class="sxs-lookup"><span data-stu-id="aa4c7-187">Method</span></span> | <span data-ttu-id="aa4c7-188">URI 模板</span><span class="sxs-lookup"><span data-stu-id="aa4c7-188">URI Template</span></span> | <span data-ttu-id="aa4c7-189">命令</span><span class="sxs-lookup"><span data-stu-id="aa4c7-189">Command</span></span> |  
|:--- |:---  |:--- |    
| <span data-ttu-id="aa4c7-190">POST</span><span class="sxs-lookup"><span data-stu-id="aa4c7-190">POST</span></span> | <span data-ttu-id="aa4c7-191">/session/{session id}/alert/accept</span><span class="sxs-lookup"><span data-stu-id="aa4c7-191">/session/{session id}/alert/accept</span></span> | [<span data-ttu-id="aa4c7-192">接受"接受的"</span><span class="sxs-lookup"><span data-stu-id="aa4c7-192">Accept Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| <span data-ttu-id="aa4c7-193">POST</span><span class="sxs-lookup"><span data-stu-id="aa4c7-193">POST</span></span> | <span data-ttu-id="aa4c7-194">/session/{session id}/alert/dismiss</span><span class="sxs-lookup"><span data-stu-id="aa4c7-194">/session/{session id}/alert/dismiss</span></span> | [<span data-ttu-id="aa4c7-195">消除通知</span><span class="sxs-lookup"><span data-stu-id="aa4c7-195">Dismiss Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| <span data-ttu-id="aa4c7-196">GET</span><span class="sxs-lookup"><span data-stu-id="aa4c7-196">GET</span></span> | <span data-ttu-id="aa4c7-197">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="aa4c7-197">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="aa4c7-198">获取发件人文本</span><span class="sxs-lookup"><span data-stu-id="aa4c7-198">Get Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| <span data-ttu-id="aa4c7-199">POST</span><span class="sxs-lookup"><span data-stu-id="aa4c7-199">POST</span></span> | <span data-ttu-id="aa4c7-200">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="aa4c7-200">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="aa4c7-201">发送提示文本</span><span class="sxs-lookup"><span data-stu-id="aa4c7-201">Send Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| <span data-ttu-id="aa4c7-202">POST</span><span class="sxs-lookup"><span data-stu-id="aa4c7-202">POST</span></span> | <span data-ttu-id="aa4c7-203">/session/{session id}/execute/async</span><span class="sxs-lookup"><span data-stu-id="aa4c7-203">/session/{session id}/execute/async</span></span> | [<span data-ttu-id="aa4c7-204">执行异步脚本</span><span class="sxs-lookup"><span data-stu-id="aa4c7-204">Execute Async Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| <span data-ttu-id="aa4c7-205">POST</span><span class="sxs-lookup"><span data-stu-id="aa4c7-205">POST</span></span> | <span data-ttu-id="aa4c7-206">/session/{session id}/execute/sync</span><span class="sxs-lookup"><span data-stu-id="aa4c7-206">/session/{session id}/execute/sync</span></span> | [<span data-ttu-id="aa4c7-207">执行脚本</span><span class="sxs-lookup"><span data-stu-id="aa4c7-207">Execute Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| <span data-ttu-id="aa4c7-208">GET</span><span class="sxs-lookup"><span data-stu-id="aa4c7-208">GET</span></span> | <span data-ttu-id="aa4c7-209">/session/{session id}/window</span><span class="sxs-lookup"><span data-stu-id="aa4c7-209">/session/{session id}/window</span></span> | [<span data-ttu-id="aa4c7-210">获取窗口句柄</span><span class="sxs-lookup"><span data-stu-id="aa4c7-210">Get Window Handle</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| <span data-ttu-id="aa4c7-211">GET</span><span class="sxs-lookup"><span data-stu-id="aa4c7-211">GET</span></span> | <span data-ttu-id="aa4c7-212">/session/{session id}/window/handles</span><span class="sxs-lookup"><span data-stu-id="aa4c7-212">/session/{session id}/window/handles</span></span> | [<span data-ttu-id="aa4c7-213">获取 Window 句柄</span><span class="sxs-lookup"><span data-stu-id="aa4c7-213">Get Window Handles</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

<span data-ttu-id="aa4c7-214">有关详细信息和其他 WebDriver 功能的状态，请查看[WebDriver。](../../webdriver.md)</span><span class="sxs-lookup"><span data-stu-id="aa4c7-214">For more info and the status of other WebDriver features, check out [WebDriver](../../webdriver.md).</span></span>  

## <span data-ttu-id="aa4c7-215">EdgeHTML 15 中的新 API</span><span class="sxs-lookup"><span data-stu-id="aa4c7-215">New APIs in EdgeHTML 15</span></span>  

<span data-ttu-id="aa4c7-216">下面是 EdgeHTML 15 中的新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-216">Here's the full list of new APIs in EdgeHTML 15.</span></span>  <span data-ttu-id="aa4c7-217">它们以格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-217">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='582' scrolling='no' title='<span data-ttu-id="aa4c7-218">新版 EdgeHTML15 API</span><span class="sxs-lookup"><span data-stu-id="aa4c7-218">New EdgeHTML15 APIs</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="aa4c7-219">有关 <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> 在 CodePen 上使用 Microsoft Edge 的文档和 </a> Microsoft Edge <a href='http://codepen.io/MicrosoftEdgeDocumentation'> (@MicrosoftEdgeDocumentation) 笔新 EdgeHTML15 </a> <a href='http://codepen.io'> </a> API。</span><span class="sxs-lookup"><span data-stu-id="aa4c7-219">See the Pen <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'>New EdgeHTML15 APIs</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="aa4c7-220">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="aa4c7-220">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="aa4c7-221">EdgeHTML 12 / Windows 内部版本 10240 (7/2015) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-221">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="aa4c7-222">EdgeHTML 13 / Windows 版本 10586 (11/2015 版) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-222">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="aa4c7-223">EdgeHTML 14/Windows 内部版本 14393 (，8) </span><span class="sxs-lookup"><span data-stu-id="aa4c7-223">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  
