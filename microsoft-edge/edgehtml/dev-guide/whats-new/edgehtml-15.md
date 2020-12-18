---
description: 本指南概述了 EdgeHTML 15 中包含的开发人员功能和标准。
title: EdgeHTML 15 中的新功能和 API
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 126fbc5f2a077052654063237c669089a3376ab0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232679"
---
# <span data-ttu-id="c5293-104">EdgeHTML 15 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="c5293-104">What's new in EdgeHTML 15</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="c5293-105">下面是 Microsoft Edge 平台当前版本附带的更改，自 [Windows 10](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) 创意者更新 \ (04/2017 内部版本 15063\) 起。</span><span class="sxs-lookup"><span data-stu-id="c5293-105">Here are the changes shipped with the current release of the Microsoft Edge platform, as of the [Windows 10 Creators Update](https://blogs.windows.com/buildingapps/2017/04/05/windows-10-creators-update-creators-update-sdk-released/#MMhK2OdcrR12Vi6u.97) \(04/2017, Build 15063\).</span></span>  <span data-ttu-id="c5293-106">有关整个 Microsoft Edge 浏览器更改的概述，请参阅 [Windows 10](https://blogs.windows.com/msedgedev/2017/04/11)创意者更新中的 Microsoft Edge 的新增功能。</span><span class="sxs-lookup"><span data-stu-id="c5293-106">For an overview of changes to the overall Microsoft Edge browser, see [What's new in Microsoft Edge in the Windows 10 Creators Update](https://blogs.windows.com/msedgedev/2017/04/11).</span></span>  

<span data-ttu-id="c5293-107">有关后续 Windows Insider Preview 内部版本的变化，请参阅 [EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="c5293-107">For changes in subsequent Windows Insider Preview builds, see [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="c5293-108">下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md)</span><span class="sxs-lookup"><span data-stu-id="c5293-108">Here's the permalink for the following list of changes:  [https://aka.ms/devguide_edgehtml_15](./edgehtml-15.md).</span></span>  

## <span data-ttu-id="c5293-109">新功能</span><span class="sxs-lookup"><span data-stu-id="c5293-109">New features</span></span>  

### <span data-ttu-id="c5293-110">CSS 自定义属性</span><span class="sxs-lookup"><span data-stu-id="c5293-110">CSS Custom Properties</span></span>  

<span data-ttu-id="c5293-111">Microsoft Edge 现在支持 [CSS 自定义属性](https://drafts.csswg.org/css-variables)（即 CSS 变量）。</span><span class="sxs-lookup"><span data-stu-id="c5293-111">Microsoft Edge now supports [CSS Custom Properties](https://drafts.csswg.org/css-variables), a.k.a CSS Variables.</span></span>  <span data-ttu-id="c5293-112">CSS 变量允许您创建自定义 CSS 属性，这些属性可在样式表内重复使用，以帮助减少重复数据量，如重复颜色。</span><span class="sxs-lookup"><span data-stu-id="c5293-112">CSS Variables allow you to create custom CSS properties that can be reused throughout stylesheets to help reduce the amount of duplicate data, like repeated colors.</span></span>  <span data-ttu-id="c5293-113">使用 CSS 变量非常简单：</span><span class="sxs-lookup"><span data-stu-id="c5293-113">Using CSS Variables is simple:</span></span>  

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

### <span data-ttu-id="c5293-114">交集者</span><span class="sxs-lookup"><span data-stu-id="c5293-114">Intersection Observer</span></span>  

<span data-ttu-id="c5293-115">EdgeHTML 15 引入了 [交集器 API](https://w3c.github.io/IntersectionObserver) 规范。</span><span class="sxs-lookup"><span data-stu-id="c5293-115">EdgeHTML 15 introduces the [Intersection Observer API](https://w3c.github.io/IntersectionObserver) specification.</span></span>  <span data-ttu-id="c5293-116">交集 Api 允许你异步查询 DOM 元素相对于其他元素或全局视口的位置和可见性。</span><span class="sxs-lookup"><span data-stu-id="c5293-116">The Intersection Observer API allows you to asynchronously query the position and visibility of DOM elements relative to other elements or the global viewport.</span></span>  <span data-ttu-id="c5293-117">此 API 通过创建在元素查看时有效通知元素的方法，无需自定义昂贵的代码。</span><span class="sxs-lookup"><span data-stu-id="c5293-117">This API eliminates the need for custom expensive code by creating a method to efficiently notify elements when they are in view.</span></span>  

### <span data-ttu-id="c5293-118">JavaScript</span><span class="sxs-lookup"><span data-stu-id="c5293-118">JavaScript</span></span>  

<span data-ttu-id="c5293-119">性能优化在 EdgeHTML 15 修订版的 Chakra JavaScript 引擎中处于中心阶段。</span><span class="sxs-lookup"><span data-stu-id="c5293-119">Performance optimizations take center stage with the EdgeHTML 15 rev of the Chakra JavaScript engine.</span></span>  <span data-ttu-id="c5293-120">借助 Windows 10 创意者更新，Chakra 通过重新延迟函数并优化堆参数来节省内存，并改进缩小代码的性能。</span><span class="sxs-lookup"><span data-stu-id="c5293-120">With the Windows 10 Creators Update, Chakra saves memory by re-deferring functions and optimizing away heap arguments and improves performance for minified code.</span></span>  

<span data-ttu-id="c5293-121">此外，EdgeHTML 15 还引入了以下功能预览：</span><span class="sxs-lookup"><span data-stu-id="c5293-121">Additionally, EdgeHTML 15 introduces the following feature previews:</span></span>  

#### <span data-ttu-id="c5293-122">实验 JavaScript 功能</span><span class="sxs-lookup"><span data-stu-id="c5293-122">Experimental JavaScript features</span></span>  

<span data-ttu-id="c5293-123">已启用</span><span class="sxs-lookup"><span data-stu-id="c5293-123">Enabled with</span></span> `about:flags`  

*   <span data-ttu-id="c5293-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \ ([demo](https://webassembly.org/demo)\) </span><span class="sxs-lookup"><span data-stu-id="c5293-124">[WebAssembly](https://developer.microsoft.com/microsoft-edge/platform/status/webassemblymvp/?q=WebAssembly) \([demo](https://webassembly.org/demo)\)</span></span>  
*   [<span data-ttu-id="c5293-125">共享内存和原子</span><span class="sxs-lookup"><span data-stu-id="c5293-125">Shared Memory and Atomics</span></span>](https://developer.microsoft.com/microsoft-edge/platform/status/sharedmemoryandatomics/?q=Atomics)  

<span data-ttu-id="c5293-126">有关更多详细信息，请参阅 Microsoft Edge 中改进的 [JavaScript 性能、WebAssembly](https://blogs.windows.com/msedgedev/2017/04/20) 和共享内存。</span><span class="sxs-lookup"><span data-stu-id="c5293-126">See [Improved JavaScript performance, WebAssembly, and Shared Memory in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/04/20) for further details.</span></span>  

### <span data-ttu-id="c5293-127">付款请求 API</span><span class="sxs-lookup"><span data-stu-id="c5293-127">Payment Request API</span></span>  

<span data-ttu-id="c5293-128">现在 [支持付款请求 API，](https://w3.org/TR/payment-request) 从而在 Windows 10 电脑和手机上实现更简单的 Web 结帐和付款。</span><span class="sxs-lookup"><span data-stu-id="c5293-128">The [Payment Request API](https://w3.org/TR/payment-request) is now supported, enabling simpler checkout and payments on the web on Windows 10 PCs and Phones.</span></span>  <span data-ttu-id="c5293-129">此 API 使 Microsoft Edge 能够充当商家、消费者以及消费者存储在云中的付款方式 \ (（如信用卡\) ）之间的中介。</span><span class="sxs-lookup"><span data-stu-id="c5293-129">This API enables Microsoft Edge to act as an intermediary between merchants, consumers, and the payment methods \(such as credit cards\) that consumers have stored in the cloud.</span></span>  <span data-ttu-id="c5293-130">有关付款请求 API 详细信息，请查看"更简单 [的 Web](https://blogs.windows.com/msedgedev/2016/12/15) 付款：付款请求 API 介绍"和" [付款请求 API](/microsoft-edge/dev-guide/device/payment-request-api) 开发人员指南"。</span><span class="sxs-lookup"><span data-stu-id="c5293-130">For more information on the Payment Request API, check out [Simpler web payments: Introducing the Payment Request API](https://blogs.windows.com/msedgedev/2016/12/15) and the [Payment Request API](/microsoft-edge/dev-guide/device/payment-request-api) developer guide.</span></span>  

### <span data-ttu-id="c5293-131">TCP 快速打开 (TFO) </span><span class="sxs-lookup"><span data-stu-id="c5293-131">TCP Fast Open (TFO)</span></span>  
<span data-ttu-id="c5293-132">TCP 快速打开是一项功能，可以减少打开 TCP 连接所需的往返次数，从而提高浏览器网络性能。</span><span class="sxs-lookup"><span data-stu-id="c5293-132">TCP Fast Open is a feature that reduces the number of round trips required to open a TCP connection, improving browser networking performance.</span></span>  <span data-ttu-id="c5293-133">有关详细信息，请参阅使用 TCP 快速打开构建更快[、更安全的 Web。](https://blogs.windows.com/msedgedev/2016/06/15)</span><span class="sxs-lookup"><span data-stu-id="c5293-133">For more details, see [Building a faster and more secure web with TCP Fast Open](https://blogs.windows.com/msedgedev/2016/06/15).</span></span>  <span data-ttu-id="c5293-134">由于各种网络拓扑的互操作性差异，默认情况下，Microsoft Edge 中不启用此功能。</span><span class="sxs-lookup"><span data-stu-id="c5293-134">Due to interoperability differences in various network topologies, this features is not enabled by default in Microsoft Edge.</span></span>  <span data-ttu-id="c5293-135">若要启用它，请在地址栏中键入，然后选中"网络"部分下的"启用 `about:flags` **TCP 快速** 打开 **"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="c5293-135">To enable it, type `about:flags` in your address bar, and select the checkbox for **Enable TCP Fast Open** under the **Networking** section.</span></span>  

### <span data-ttu-id="c5293-136">WebRTC 和可互操作 RTC 视频编解码器支持</span><span class="sxs-lookup"><span data-stu-id="c5293-136">WebRTC and interoperable RTC video codec support</span></span>  

<span data-ttu-id="c5293-137">EdgeHTML 15 支持 WebRTC 1.0 API 的子集，用于与使用 W3C WebRTC-PC API（大约 2015 年）的早期版本构建的应用程序进行互操作。</span><span class="sxs-lookup"><span data-stu-id="c5293-137">EdgeHTML 15 supports a subset of the WebRTC 1.0 API for interoperability with applications built with earlier versions of the W3C WebRTC-PC API circa 2015.</span></span>  <span data-ttu-id="c5293-138">有关详细信息， [请参阅 WebRTC API](/previous-versions//mt806139(v=vs.85)) 参考。</span><span class="sxs-lookup"><span data-stu-id="c5293-138">See the [WebRTC API reference](/previous-versions//mt806139(v=vs.85)) for details.</span></span>  

<span data-ttu-id="c5293-139">若要利用对等音频和视频通信中的最高级功能，我们建议使用[Object Real-Time Communication) API。](https://ortc.org)</span><span class="sxs-lookup"><span data-stu-id="c5293-139">To take advantage of our most advanced features in peer-to-peer audio and video communication, we recommend using the [Object Real-Time Communication) API](https://ortc.org).</span></span>  <span data-ttu-id="c5293-140">ORTC API 更适用于要设置组音频和视频呼叫或直接控制单个传输、发件人和接收器对象的情况。</span><span class="sxs-lookup"><span data-stu-id="c5293-140">The ORTC API is better suited for situations where you want to set up group audio and video calls, or directly control individual transport, sender, and receiver objects.</span></span>  

<span data-ttu-id="c5293-141">Microsoft Edge 支持带有 ORTC 和 WebRTC 1.0 的 H.264/AVC 和 VP8 视频，并提供以下功能来支持这两种编解码器类型：abs-send-time、goog-remb、Picture [Loss Indication 和 Generic NACK feedback](https://tools.ietf.org/html/rfc4585)， [](https://webrtc.org/experiments/rtp-hdrext/abs-send-time) [RTP Retransmission。](https://tools.ietf.org/html/rfc4588) [](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03)</span><span class="sxs-lookup"><span data-stu-id="c5293-141">The Microsoft Edge supports both H.264/AVC and VP8 video with ORTC and WebRTC 1.0, and provides the following features in support of both codec types: [abs-send-time](https://webrtc.org/experiments/rtp-hdrext/abs-send-time), [goog-remb](https://tools.ietf.org/html/draft-alvestrand-rmcat-remb-03), [Picture Loss Indication and Generic NACK feedback](https://tools.ietf.org/html/rfc4585), [RTP Retransmission](https://tools.ietf.org/html/rfc4588).</span></span>  

<span data-ttu-id="c5293-142">有关详细信息，请参阅 [Microsoft Edge 中的 WebRTC 1.0](https://blogs.windows.com/msedgedev/2017/01/31)简介和可互操作实时通信。</span><span class="sxs-lookup"><span data-stu-id="c5293-142">For more info, see [Introducing WebRTC 1.0 and interoperable real-time communications in Microsoft Edge](https://blogs.windows.com/msedgedev/2017/01/31).</span></span>  

### <span data-ttu-id="c5293-143">WebVR</span><span class="sxs-lookup"><span data-stu-id="c5293-143">WebVR</span></span>  

<span data-ttu-id="c5293-144">Microsoft Edge 现在支持 [WebVR，](https://immersive-web.github.io/webxr)这是一个实验性 API，用于连接 Windows Mixed Reality 头安装显示器和 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="c5293-144">Microsoft Edge now has support for [WebVR](https://immersive-web.github.io/webxr), an experimental API that connects Windows Mixed Reality head mounted displays and Microsoft Edge.</span></span>  <span data-ttu-id="c5293-145">此连接使 WEB 内容能够在网站中体验，这意味着沉浸式VR 体验不再局限于桌面应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5293-145">This connection enables VR content to be experienced within a website, meaning immersive VR experiences are no longer limited to desktop applications.</span></span>  

<span data-ttu-id="c5293-146">Microsoft Edge 中的虚拟网络由 WebGL（用于呈现 3D 和 2D 图形的 JavaScript API）提供支持。</span><span class="sxs-lookup"><span data-stu-id="c5293-146">Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.</span></span>  <span data-ttu-id="c5293-147">支持使用 WebGL 库（如 BabylonJS）构建的 WebGL 应用程序和应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5293-147">WebGL applications and applications built with WebGL libraries like BabylonJS are supported.</span></span>  <span data-ttu-id="c5293-148">连接后，WebVR 将发送与耳机周围的位置和传感器信息相对应的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="c5293-148">Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.</span></span>  <span data-ttu-id="c5293-149">由于对游戏板 API 的扩展，WebVR API 还支持 **空间控制器**。</span><span class="sxs-lookup"><span data-stu-id="c5293-149">The WebVR API also supports spatial controllers thanks to an extension to the **Gamepad API**.</span></span>  <span data-ttu-id="c5293-150">此 API 默认处于打开状态，因此无需切换标志。</span><span class="sxs-lookup"><span data-stu-id="c5293-150">This API is on by default, so no need to toggle a flag.</span></span>  

<!--  Virtual reality in Microsoft Edge is powered by WebGL, a JavaScript API for rendering 3D and 2D graphics.  WebGL applications and applications built with WebGL libraries like BabylonJS are supported.  Once connected, WebVR sends visuals corresponding to the position and sensor information around the headset.  The WebVR API also supports spatial controllers thanks to an extension to the [Gamepad API](../dom/gamepad-api.md).  This API is on by default, so no need to toggle a flag.  -->  

<span data-ttu-id="c5293-151">有关详细信息，[请参阅 WebVR API 参考](/previous-versions/mt806281(v=vs.85))[和游戏板 API](https://developer.mozilla.org/docs/Web/API/Gamepad_API)参考。</span><span class="sxs-lookup"><span data-stu-id="c5293-151">See the [WebVR API reference](/previous-versions/mt806281(v=vs.85)) and [Gamepad API reference](https://developer.mozilla.org/docs/Web/API/Gamepad_API) for details.</span></span>  

 > [!NOTE] 
 > <span data-ttu-id="c5293-152">由于 WebVR 规范仍处于开发阶段，因此 Microsoft Edge 的实现可能会稍后发生变化。</span><span class="sxs-lookup"><span data-stu-id="c5293-152">Since the WebVR spec is still in development, Microsoft Edge's implementation may change later down the line.</span></span>  

## <span data-ttu-id="c5293-153">更新的功能</span><span class="sxs-lookup"><span data-stu-id="c5293-153">Updated features</span></span>  

### <span data-ttu-id="c5293-154">内容安全策略 (级别 2) </span><span class="sxs-lookup"><span data-stu-id="c5293-154">Content Security Policy (Level 2)</span></span>  

<span data-ttu-id="c5293-155">已使用云解决方案提供商 1 的网站应继续使用 Microsoft Edge 对 CSP 2 的支持，但最好将加载工作脚本的任何指令切换到新指令，以面向未来的 `frame-src` `child-src` 站点。</span><span class="sxs-lookup"><span data-stu-id="c5293-155">Sites already using CSP 1 should continue to work with Microsoft Edge support for CSP 2, however it's best to switch any `frame-src` directives that load worker scripts to the new `child-src` directive to future-proof your site.</span></span>  <span data-ttu-id="c5293-156">\ (在 CSP 3 中，将不再适用于工作者 `frame-src` 。\) CSP 2 还添加了以下内容：</span><span class="sxs-lookup"><span data-stu-id="c5293-156">\(In CSP 3, `frame-src` will no longer apply to workers.\) CSP 2 also adds the following:</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="c5293-157">新指令</span><span class="sxs-lookup"><span data-stu-id="c5293-157">New directives</span></span>  
   :::column-end:::
   :::column span="2":::
      `base-uri`<span data-ttu-id="c5293-158">`child-src`、、 `form-action` `frame-ancestors` 和 `plugin-types` 。</span><span class="sxs-lookup"><span data-stu-id="c5293-158">, `child-src`, `form-action`, `frame-ancestors` and `plugin-types`.</span></span>  <!--  See [Microsoft Edge supported CSP directives](../security/content-security-policy.md) for more.  -->  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="c5293-159">工作人员支持</span><span class="sxs-lookup"><span data-stu-id="c5293-159">Workers support</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c5293-160">后台工作线程脚本由其自己的策略管理，独立于加载它们的文档策略。</span><span class="sxs-lookup"><span data-stu-id="c5293-160">Background worker scripts are governed by their own policy, separate from the policy of the document loading them.</span></span>  <span data-ttu-id="c5293-161">与主机文档一样，您可以在响应标头中为工作者设置 CSP。</span><span class="sxs-lookup"><span data-stu-id="c5293-161">As with host documents, you can set the CSP for a worker in the response header.</span></span>  <span data-ttu-id="c5293-162">CSP 2 中的新增功能是，指令 `allow-scripts` `allow-same-origin` `sandbox` 的标志现在会影响工作线程创建。</span><span class="sxs-lookup"><span data-stu-id="c5293-162">Also new in CSP 2 is that `allow-scripts` and `allow-same-origin` flags of the `sandbox` directive now affect worker thread creation.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="c5293-163">内联脚本和样式</span><span class="sxs-lookup"><span data-stu-id="c5293-163">Inline scripts and styles</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c5293-164">CSP 2 通过提供非索引和哈希作为允许列表机制，允许执行内联脚本和样式块。</span><span class="sxs-lookup"><span data-stu-id="c5293-164">CSP 2 allows for the execution of inline scripts and style blocks by providing nonces and hashes as a allow-listing mechanism.</span></span>  <span data-ttu-id="c5293-165">Nonces 是在云解决方案提供商策略和页面脚本标记中显示的每个页面加载上生成的随机基 64 值。</span><span class="sxs-lookup"><span data-stu-id="c5293-165">Nonces are random base-64 values generated on each page load that appears in both the CSP policy and in the script tags in the page.</span></span>  <span data-ttu-id="c5293-166">加载时动态生成页面时，服务器将生成 nonce 值，将其插入到页面中的 NonceToken 中，并声明它在内容安全策略 HTTP 标头中。</span><span class="sxs-lookup"><span data-stu-id="c5293-166">When the page is dynamically generated on load, the server generates a nonce value, inserts it into the NonceToken in the page and also declares it in the Content Security Policy HTTP header.</span></span>  <span data-ttu-id="c5293-167">哈希是使用 sha256、sha384 或 sha512 算法\) 从随后使用 CSP 策略中的 or 指令\ (指定 \ (的内容生成的 `<script>` `<style>` 静态值 `script-src` `style-src` \) 。 (</span><span class="sxs-lookup"><span data-stu-id="c5293-167">Hashes are static values generated \(using sha256, sha384 or sha512 algorithms\) from the content of a `<script>` or `<style>` element that are then specified \(using `script-src` or `style-src` directives\) in the CSP policy.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      <span data-ttu-id="c5293-168">云解决方案提供商违反报告</span><span class="sxs-lookup"><span data-stu-id="c5293-168">CSP violation reporting</span></span>  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="c5293-169">新的事件， `SecurityPolicyViolationEvent` 现在在 CSP 冲突时触发。</span><span class="sxs-lookup"><span data-stu-id="c5293-169">A new event, `SecurityPolicyViolationEvent` is now fired upon CSP violations.</span></span>  <span data-ttu-id="c5293-170">云解决方案提供商报告早期 `report-uri` 机制继续受支持。</span><span class="sxs-lookup"><span data-stu-id="c5293-170">The earlier mechanism for CSP reporting, `report-uri`, continues to be supported.</span></span>  <span data-ttu-id="c5293-171">向这两者通用的冲突报告中添加了几个新字段，包括 `effectiveDirective` \ (违反的策略\) 、\ (HTTP 响应代码 `statusCode` \) 、\ (违反资源的 `sourceFile` URL\) `lineNumber` 和 `columnNumber` 。</span><span class="sxs-lookup"><span data-stu-id="c5293-171">Several new fields have been added to the violation reports common to both, including `effectiveDirective` \(the policy that was violated\), `statusCode` \(the HTTP response code\), `sourceFile` \(the URL of the offending resource\), `lineNumber`, and `columnNumber`.</span></span>  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="c5293-172">Web 身份验证</span><span class="sxs-lookup"><span data-stu-id="c5293-172">Web Authentication</span></span>  

<span data-ttu-id="c5293-173">通过以下更改更新了对使用[Windows Hello](https://www.microsoft.com/windows/comprehensive-security)生物识别的新兴 Web 身份验证**API**的 Microsoft Edge 支持：</span><span class="sxs-lookup"><span data-stu-id="c5293-173">Microsoft Edge support for the emerging **Web Authentication API** using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:</span></span>  

<!--  Microsoft Edge support for the emerging [Web Authentication API](../device/web-authentication.md) using [Windows Hello](https://www.microsoft.com/windows/comprehensive-security) biometrics has been updated with the following changes:  -->  

*   <span data-ttu-id="c5293-174">[EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \ (Windows 10 周年更新版本 10240，7/2016\) 中引入的实验性 Web 身份验证 API 的初始实现通过 MS 前缀 API \ ([MSCredentials](/previous-versions/mt697639(v=vs.85))接口\) 公开。</span><span class="sxs-lookup"><span data-stu-id="c5293-174">The initial implementation of the experimental Web Authentication API introduced in [EdgeHTML 14](https://blogs.windows.com/msedgedev/2016/08/04) \(Windows 10 Anniversary Update, build 10240, 7/2016\) was exposed through MS- prefixed APIs \(the [MSCredentials](/previous-versions/mt697639(v=vs.85)) interface\).</span></span>  <span data-ttu-id="c5293-175">虽然这些 API 在 EdgeHTML 15 中仍然可用，但现在已弃用它们，以支持在规范的最近快照中定义的无前缀、基于标准的 API[](https://w3.org/TR/2016/WD-webauthn-20160928)和行为，并且可能会随着规范逐渐向标准化的方向发展而继续更改。</span><span class="sxs-lookup"><span data-stu-id="c5293-175">While these APIs are still available in EdgeHTML 15, they are now deprecated in favor of the non-prefixed, standards-based APIs and behaviors defined in a more [recent snapshot](https://w3.org/TR/2016/WD-webauthn-20160928) of the specification, and are likely to continue changing as the spec matures toward standardization.</span></span>  

*   <span data-ttu-id="c5293-176">默认情况下，最新的 Microsoft Edge 实现处于关闭状态，并附带在地址栏中 (标记 `about:flags` \) 。</span><span class="sxs-lookup"><span data-stu-id="c5293-176">The latest Microsoft Edge implementation is turned off by default and ships behind a flag \(type `about:flags` in your address bar to turn on the feature\).</span></span>  

*   <span data-ttu-id="c5293-177">Microsoft Edge 尚不支持外部凭据，如 U 盘或Bluetooth设备。</span><span class="sxs-lookup"><span data-stu-id="c5293-177">Microsoft Edge does not yet support external credentials like USB keys or Bluetooth devices.</span></span>  <span data-ttu-id="c5293-178">当前 API 仅限于 TPM 中存储的嵌入凭据。</span><span class="sxs-lookup"><span data-stu-id="c5293-178">The current API is limited to embedded credentials stored in the TPM.</span></span>  <span data-ttu-id="c5293-179">如果 TPM 在设备上不可用，则使用软件回退。</span><span class="sxs-lookup"><span data-stu-id="c5293-179">A software fallback is used if TPM is not available on the device.</span></span>  

*   <span data-ttu-id="c5293-180">当前登录的 Windows 用户帐户必须配置为支持至少一个 PIN，最好是人脸或指纹生物识别。</span><span class="sxs-lookup"><span data-stu-id="c5293-180">The currently logged in Windows user account must be configured to support at least a PIN, and preferably face or fingerprint biometrics.</span></span>  <span data-ttu-id="c5293-181">这是为了确保 Windows 可以验证对 TPM 的访问。</span><span class="sxs-lookup"><span data-stu-id="c5293-181">This is to ensure that Windows can authenticate the access to the TPM.</span></span>  

*   <span data-ttu-id="c5293-182">在规范 [中描述的](https://w3.org/TR/webauthn/#extension-predef) 预定义扩展中，Microsoft Edge 目前仅支持 [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \ (`webauthn_txAuthSimple` \) 。</span><span class="sxs-lookup"><span data-stu-id="c5293-182">Of the [predefined extensions](https://w3.org/TR/webauthn/#extension-predef) described in the spec, Microsoft Edge only supports the [FIDO AppId](https://w3.org/TR/webauthn/#extension-appid) \(`webauthn_txAuthSimple`\) at this time.</span></span>  

*  <span data-ttu-id="c5293-183">`timeoutSeconds`当前未评估该选项</span><span class="sxs-lookup"><span data-stu-id="c5293-183">The `timeoutSeconds` option is not currently evaluated</span></span>  

### <span data-ttu-id="c5293-184">WebDriver</span><span class="sxs-lookup"><span data-stu-id="c5293-184">WebDriver</span></span>  

<span data-ttu-id="c5293-185">EdgeHTML 15 带来了一些 WebDriver 更新，包括对无提示命令行标志和新命令终结点的支持：</span><span class="sxs-lookup"><span data-stu-id="c5293-185">EdgeHTML 15 brings a handful of WebDriver updates including support for the silent command line flag and new command endpoints:</span></span>  

| <span data-ttu-id="c5293-186">方法</span><span class="sxs-lookup"><span data-stu-id="c5293-186">Method</span></span> | <span data-ttu-id="c5293-187">URI 模板</span><span class="sxs-lookup"><span data-stu-id="c5293-187">URI Template</span></span> | <span data-ttu-id="c5293-188">命令</span><span class="sxs-lookup"><span data-stu-id="c5293-188">Command</span></span> |  
|:--- |:---  |:--- |    
| <span data-ttu-id="c5293-189">POST</span><span class="sxs-lookup"><span data-stu-id="c5293-189">POST</span></span> | <span data-ttu-id="c5293-190">/session/{session id}/alert/accept</span><span class="sxs-lookup"><span data-stu-id="c5293-190">/session/{session id}/alert/accept</span></span> | [<span data-ttu-id="c5293-191">接受警报</span><span class="sxs-lookup"><span data-stu-id="c5293-191">Accept Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-accept-alert) |  
| <span data-ttu-id="c5293-192">POST</span><span class="sxs-lookup"><span data-stu-id="c5293-192">POST</span></span> | <span data-ttu-id="c5293-193">/session/{session id}/alert/dismiss</span><span class="sxs-lookup"><span data-stu-id="c5293-193">/session/{session id}/alert/dismiss</span></span> | [<span data-ttu-id="c5293-194">消除警报</span><span class="sxs-lookup"><span data-stu-id="c5293-194">Dismiss Alert</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-dismiss-alert) |  
| <span data-ttu-id="c5293-195">GET</span><span class="sxs-lookup"><span data-stu-id="c5293-195">GET</span></span> | <span data-ttu-id="c5293-196">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="c5293-196">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="c5293-197">获取警报文本</span><span class="sxs-lookup"><span data-stu-id="c5293-197">Get Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-alert-text) |  
| <span data-ttu-id="c5293-198">POST</span><span class="sxs-lookup"><span data-stu-id="c5293-198">POST</span></span> | <span data-ttu-id="c5293-199">/session/{session id}/alert/text</span><span class="sxs-lookup"><span data-stu-id="c5293-199">/session/{session id}/alert/text</span></span> | [<span data-ttu-id="c5293-200">发送通知文本</span><span class="sxs-lookup"><span data-stu-id="c5293-200">Send Alert Text</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-send-alert-text) |  
| <span data-ttu-id="c5293-201">POST</span><span class="sxs-lookup"><span data-stu-id="c5293-201">POST</span></span> | <span data-ttu-id="c5293-202">/session/{session id}/execute/async</span><span class="sxs-lookup"><span data-stu-id="c5293-202">/session/{session id}/execute/async</span></span> | [<span data-ttu-id="c5293-203">执行异步脚本</span><span class="sxs-lookup"><span data-stu-id="c5293-203">Execute Async Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-async-script) |  
| <span data-ttu-id="c5293-204">POST</span><span class="sxs-lookup"><span data-stu-id="c5293-204">POST</span></span> | <span data-ttu-id="c5293-205">/session/{session id}/execute/sync</span><span class="sxs-lookup"><span data-stu-id="c5293-205">/session/{session id}/execute/sync</span></span> | [<span data-ttu-id="c5293-206">执行脚本</span><span class="sxs-lookup"><span data-stu-id="c5293-206">Execute Script</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-execute-script) |  
| <span data-ttu-id="c5293-207">GET</span><span class="sxs-lookup"><span data-stu-id="c5293-207">GET</span></span> | <span data-ttu-id="c5293-208">/session/{session id}/window</span><span class="sxs-lookup"><span data-stu-id="c5293-208">/session/{session id}/window</span></span> | [<span data-ttu-id="c5293-209">获取窗口句柄</span><span class="sxs-lookup"><span data-stu-id="c5293-209">Get Window Handle</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#get-window-handle) |  
| <span data-ttu-id="c5293-210">GET</span><span class="sxs-lookup"><span data-stu-id="c5293-210">GET</span></span> | <span data-ttu-id="c5293-211">/session/{session id}/window/handles</span><span class="sxs-lookup"><span data-stu-id="c5293-211">/session/{session id}/window/handles</span></span> | [<span data-ttu-id="c5293-212">获取窗口句柄</span><span class="sxs-lookup"><span data-stu-id="c5293-212">Get Window Handles</span></span>](https://w3c.github.io/webdriver/webdriver-spec.html#dfn-get-window-handles) |  

<span data-ttu-id="c5293-213">有关详细信息和其他 WebDriver 功能的状态，请查看[WebDriver。](../../webdriver/index.md)</span><span class="sxs-lookup"><span data-stu-id="c5293-213">For more info and the status of other WebDriver features, check out [WebDriver](../../webdriver/index.md).</span></span>  

## <span data-ttu-id="c5293-214">EdgeHTML 15 中的新 API</span><span class="sxs-lookup"><span data-stu-id="c5293-214">New APIs in EdgeHTML 15</span></span>  

<span data-ttu-id="c5293-215">以下是 EdgeHTML 15 中新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="c5293-215">Here's the full list of new APIs in EdgeHTML 15.</span></span>  <span data-ttu-id="c5293-216">它们以 . `[interface name].[api name]`</span><span class="sxs-lookup"><span data-stu-id="c5293-216">They are listed in the format of `[interface name].[api name]`.</span></span>  

<iframe height='582' scrolling='no' title='<span data-ttu-id="c5293-217">新的 EdgeHTML15 API</span><span class="sxs-lookup"><span data-stu-id="c5293-217">New EdgeHTML15 APIs</span></span>' src='//codepen.io/MicrosoftEdgeDocumentation/embed/evRjjZ/?height=582&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="c5293-218">请参阅 Microsoft Edge 文档在 <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'> CodePen 上 (@MicrosoftEdgeDocumentation) </a> <a href='http://codepen.io/MicrosoftEdgeDocumentation'> </a> <a href='http://codepen.io'> EdgeHTML15 </a> API。</span><span class="sxs-lookup"><span data-stu-id="c5293-218">See the Pen <a href='http://codepen.io/MicrosoftEdgeDocumentation/pen/evRjjZ/'>New EdgeHTML15 APIs</a> by Microsoft Edge Docs (<a href='http://codepen.io/MicrosoftEdgeDocumentation'>@MicrosoftEdgeDocumentation</a>) on <a href='http://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="c5293-219">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="c5293-219">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="c5293-220">EdgeHTML 12 /Windows 版本 10240 (2015 年 7 月 7 日) </span><span class="sxs-lookup"><span data-stu-id="c5293-220">EdgeHTML 12 / Windows build 10240 (7/2015)</span></span>](./edgehtml-12.md)  

[<span data-ttu-id="c5293-221">EdgeHTML 13 /Windows 版本 10586 (2015 年 11 月 11 日) </span><span class="sxs-lookup"><span data-stu-id="c5293-221">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](./edgehtml-13.md)  

[<span data-ttu-id="c5293-222">EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) </span><span class="sxs-lookup"><span data-stu-id="c5293-222">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](./edgehtml-14.md)  
