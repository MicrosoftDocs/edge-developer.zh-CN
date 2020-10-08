---
title: EdgeHTML 17 中的新功能和 Api
description: 本指南概述了 EdgeHTML 17 中包含的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘、web 开发、html、css、javascript、开发人员
ms.openlocfilehash: 0fc7dda532866e8970003bce2febb7e46fbbc459
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941943"
---
# <span data-ttu-id="ed8ef-104">EdgeHTML 17 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="ed8ef-104">What's new in EdgeHTML 17</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="ed8ef-105">下面是 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web 平台中随附的新增和更新功能的列表，作为 [Windows 10 2018 年4月的更新](https://blogs.windows.com/windowsexperience/2018/04/27) \ (04/2018，内部版本 17134 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-105">Here's a list of the new and updated features shipped in [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web platform, as part of the [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, Build 17134\).</span></span>  <span data-ttu-id="ed8ef-106">有关特定 Windows 预览 [体验计划](https://insider.windows.com) 预览版中的更改，请参阅 [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-106">For changes in specific [Windows Insider](https://insider.windows.com) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="ed8ef-107">下面是以下更改列表的固定链接： [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md).</span></span>  

## <span data-ttu-id="ed8ef-108">新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="ed8ef-108">New and updated features</span></span>  

### <span data-ttu-id="ed8ef-109">ARIA 1.1 角色、状态和事件</span><span class="sxs-lookup"><span data-stu-id="ed8ef-109">ARIA 1.1 Roles, States, and Events</span></span>  

<span data-ttu-id="ed8ef-110">EdgeHTML 17 为可访问的富 Internet 应用程序中的各种角色、状态和属性添加支持 [ (wai-aria-aria) 1.1 规范](https://w3.org/TR/wai-aria-1.1)，包括 [源](https://www.w3.org/TR/wai-aria-1.1#feed)、 [表单](https://www.w3.org/TR/wai-aria-1.1#form)、 [ARIA haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup)、 [ARIA 占位符](https://w3.org/TR/wai-aria-1.1#aria-placeholder)等; [在 changelog 中查找 ARIA 更新的完整列表](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-110">EdgeHTML 17 adds support for various roles, states, and properties from the [Accessible Rich Internet Applications (WAI-ARIA) 1.1 specification](https://w3.org/TR/wai-aria-1.1), including [feed](https://www.w3.org/TR/wai-aria-1.1#feed), [form](https://www.w3.org/TR/wai-aria-1.1#form), [aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup), [aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder), and many more; find a [full list of ARIA updates in the changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299).</span></span>  <span data-ttu-id="ed8ef-111">通过此更新，EdgeHTML 17 现在支持 WAI-ARIA-ARIA 1.1 中定义的所有角色和属性。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-111">With this update, EdgeHTML 17 now supports all roles and attributes defined in WAI-ARIA 1.1.</span></span>  <span data-ttu-id="ed8ef-112">有关 Microsoft Edge 中的辅助功能的详细信息，请查看 [辅助功能](../../accessibility.md) 文档。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-112">Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.</span></span>  

### <span data-ttu-id="ed8ef-113">CSS 蒙版</span><span class="sxs-lookup"><span data-stu-id="ed8ef-113">CSS masking</span></span>  

<span data-ttu-id="ed8ef-114">EdgeHTML 17 包含对 [CSS 掩蔽](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)的实验性支持。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-114">EdgeHTML 17 includes experimental support for [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking).</span></span>  <span data-ttu-id="ed8ef-115">部分实现引入了 CSS [掩码-图像](https://developer.mozilla.org/docs/Web/CSS/mask-image) 和 [掩码大小](https://developer.mozilla.org/docs/Web/CSS/mask-size) 属性。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-115">The partial implementation introduces the CSS [mask-image](https://developer.mozilla.org/docs/Web/CSS/mask-image) and [mask-size](https://developer.mozilla.org/docs/Web/CSS/mask-size) properties.</span></span>  <span data-ttu-id="ed8ef-116">检查 "启用 CSS 掩蔽" 标志：要试验的标志！</span><span class="sxs-lookup"><span data-stu-id="ed8ef-116">Check the "Enable CSS Masking" flag in about:flags to being experimenting!</span></span>  

### <span data-ttu-id="ed8ef-117">SVG 元素上的 CSS 转换</span><span class="sxs-lookup"><span data-stu-id="ed8ef-117">CSS transforms on SVG elements</span></span>  

<span data-ttu-id="ed8ef-118">EdgeHTML 17 现在支持 SVG 元素和演示属性上的 CSS 转换。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-118">EdgeHTML 17 now supports CSS transforms on SVG elements and presentation attributes.</span></span>  <span data-ttu-id="ed8ef-119">这使 SVG 元素能够以可视方式进行操作，包括旋转、缩放、移动、倾斜或平移。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-119">This allows SVG elements to be visually manipulated, including rotating, scaling, moving, skewing, or translating.</span></span>  

### <span data-ttu-id="ed8ef-120">Extensions</span><span class="sxs-lookup"><span data-stu-id="ed8ef-120">Extensions</span></span>  

<span data-ttu-id="ed8ef-121">Microsoft Edge 现在支持显示来自扩展的通知的 [通知 API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-121">Microsoft Edge now supports the [Notification API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) which displays notifications from extensions.</span></span>  <span data-ttu-id="ed8ef-122">现在，扩展开发人员可以创建不同类型的通知 \ (基本、列表、图像等 \ ) 支持完全用户交互的。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-122">Extension developers can now create different types of notifications \(basic, list, image  and so on\) which support full user interaction.</span></span>  <span data-ttu-id="ed8ef-123">通知也会自动登录到操作中心。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-123">The notifications are also automatically logged into the Action Center.</span></span>  <span data-ttu-id="ed8ef-124">请访问 [通知示例](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) ，了解如何在扩展中使用此 API。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-124">Visit the [notifications sample](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) on how to use this API in your extension.</span></span>  

<span data-ttu-id="ed8ef-125">EdgeHTML 17 现在还支持 `Tabs.reload()` 作为标准选项卡 API 类的一部分的方法。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-125">EdgeHTML 17 now also supports the `Tabs.reload()` method as part of the standard tabs API class.</span></span>  <span data-ttu-id="ed8ef-126">在 Windows 10 2018 年4月更新中也是新增的，用户现在可以选择允许扩展在 inPrivate 浏览期间运行。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-126">Also new in the Windows 10 April 2018 Update, users can now choose to allow extensions to run during inPrivate browsing.</span></span>  

<span data-ttu-id="ed8ef-127">有关此版本中的扩展更新的更多详细信息，请转到博客文章 [2018 年4月更新的 Windows 10 年4月扩展的新增功能](https://blogs.windows.com/msedgedev/2018/05/24)。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-127">For more details on extensions updates in this release, head over to the blog post [New features for extensions in the Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24).</span></span>  

### <span data-ttu-id="ed8ef-128">DevTools</span><span class="sxs-lookup"><span data-stu-id="ed8ef-128">DevTools</span></span>  

<span data-ttu-id="ed8ef-129">此版本的 DevTools 随附两种方式：作为传统的 in 浏览器 (`F12` \ ) Microsoft Edge 的工具，以及从 Microsoft Store 中预览为独立的 [Windows 10 应用](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) ！</span><span class="sxs-lookup"><span data-stu-id="ed8ef-129">This release of the DevTools ships in two ways: as the traditional in-browser \(`F12`\) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools 应用" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   <span data-ttu-id="ed8ef-131">Microsoft Edge DevTools 应用</span><span class="sxs-lookup"><span data-stu-id="ed8ef-131">Microsoft Edge DevTools app</span></span>  
:::image-end:::  

<span data-ttu-id="ed8ef-132">这些工具还更新了许多主要功能，包括对 [远程调试](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \ (的基本支持，包括通过新的 [DevTools 协议](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\ ) 、 [PWA 调试功能](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)、 [IndexedDB 缓存管理](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)、 [垂直停靠](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) 等！</span><span class="sxs-lookup"><span data-stu-id="ed8ef-132">The tools have also been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(via our new [DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\), [PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging), [IndexedDB cache management](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection), [vertical docking](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="ed8ef-133">我们还继续在性能和可靠性方面作为日常投资的一部分，开始上次发布的整体 [重构工作](./edgehtml-16.md) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-133">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>  

<span data-ttu-id="ed8ef-134">有关详细信息，请访问 [最新 Windows 10 更新 (EdgeHTML 17) 中的 DevTools ](../../devtools-guide/whats-new/edgehtml-17.md) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-134">Visit [DevTools in the latest Windows 10 update (EdgeHTML 17)](../../devtools-guide/whats-new/edgehtml-17.md) for more details.</span></span>  

### <span data-ttu-id="ed8ef-135">JavaScript</span><span class="sxs-lookup"><span data-stu-id="ed8ef-135">JavaScript</span></span>  

<span data-ttu-id="ed8ef-136">有了 EdgeHTML 17，Chakra JavaScript 引擎带来了许多关键领域的性能改进：</span><span class="sxs-lookup"><span data-stu-id="ed8ef-136">With EdgeHTML 17 the Chakra JavaScript engine introduces performance improvements in a number of key areas:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="ed8ef-137">更简洁内存占用</span><span class="sxs-lookup"><span data-stu-id="ed8ef-137">Leaner memory footprint</span></span>**  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="ed8ef-138">\ (重新 ) 对[对象文本](https://github.com/Microsoft/ChakraCore/pull/4136)的[箭头函数](https://github.com/Microsoft/ChakraCore/pull/4105)和方法的延迟分析</span><span class="sxs-lookup"><span data-stu-id="ed8ef-138">\(Re-\)defer parsing for [arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105) and [methods on object literals](https://github.com/Microsoft/ChakraCore/pull/4136)</span></span>  
      *   [<span data-ttu-id="ed8ef-139">RegExp 字节码重构</span><span class="sxs-lookup"><span data-stu-id="ed8ef-139">RegExp bytecode refactoring</span></span>](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="ed8ef-140">更快的 JavaScript 内置</span><span class="sxs-lookup"><span data-stu-id="ed8ef-140">Faster JavaScript built-ins</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="ed8ef-141">为对象键入共享。创建</span><span class="sxs-lookup"><span data-stu-id="ed8ef-141">Type sharing for Object.create</span></span>](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [<span data-ttu-id="ed8ef-142">对象的多态内联缓存。 assign</span><span class="sxs-lookup"><span data-stu-id="ed8ef-142">Polymorphic inline cache for Object.assign</span></span>](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [<span data-ttu-id="ed8ef-143">JSON. parse/stringify 优化</span><span class="sxs-lookup"><span data-stu-id="ed8ef-143">JSON.parse/stringify optimizations</span></span>](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [<span data-ttu-id="ed8ef-144">在 JavaScript 中重写数组迭代器，更快地为 .。。多种</span><span class="sxs-lookup"><span data-stu-id="ed8ef-144">Rewriting Array Iterators in JavaScript and faster for...of</span></span>](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="ed8ef-145">Web 程序集</span><span class="sxs-lookup"><span data-stu-id="ed8ef-145">Web Assembly</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="ed8ef-146">Inling 支持</span><span class="sxs-lookup"><span data-stu-id="ed8ef-146">Inling support</span></span>](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="ed8ef-147">查看有关所有详细信息，请参阅 [EdgeHTML 17 中的增强 JavaScript 和 WebAssembly 性能](https://blogs.windows.com/msedgedev/2018/06/19) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-147">Check out [Improved JavaScript and WebAssembly performance in EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) for all the details.</span></span>  

### <span data-ttu-id="ed8ef-148">媒体元素</span><span class="sxs-lookup"><span data-stu-id="ed8ef-148">Media element</span></span>

<span data-ttu-id="ed8ef-149">EdgeHTML 17 包括对 [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 的更新，包括：</span><span class="sxs-lookup"><span data-stu-id="ed8ef-149">EdgeHTML 17 includes updates to [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) including:</span></span>  

*   <span data-ttu-id="ed8ef-150">`preload`元素上的新属性 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 指示应预加载的数据。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-150">The new `preload` attribute on the [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) element indicates what data should be preloaded.</span></span>
*   <span data-ttu-id="ed8ef-151">添加 [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) 方法和 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) 属性使开发人员可以选择音频输出设备。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-151">The addition of the [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) method and [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) property allow developers to select the audio output device.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="ed8ef-152">此功能在 RTC 中尚不可用。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-152">This is not yet available in RTC.</span></span>  
    
### <span data-ttu-id="ed8ef-153">媒体捕获 API</span><span class="sxs-lookup"><span data-stu-id="ed8ef-153">Media Capture API</span></span>  

<span data-ttu-id="ed8ef-154">Microsoft Edge 现在通过 [媒体捕获 API](https://w3c.github.io/mediacapture-screen-share)在 RTC 中支持屏幕捕获。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-154">Microsoft Edge now supports Screen Capture in RTC via the [Media Capture API](https://w3c.github.io/mediacapture-screen-share).</span></span>  <span data-ttu-id="ed8ef-155">此功能允许网页捕获用户的显示设备的输出，通常用于广播桌面，用于插件免费的虚拟会议或演示文稿。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-155">This feature lets web pages capture output of a user's display device, commonly used to broadcast a desktop for plugin-free virtual meetings or presentation.</span></span>  

### <span data-ttu-id="ed8ef-156">渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="ed8ef-156">Progressive Web Apps</span></span>  

<span data-ttu-id="ed8ef-157">从 EdgeHTML 17 开始，"服务工作人员" 和 "推送通知" 默认情况下处于启用状态 \ (在博客文章服务工作人员中了解有关这些功能的详细信息：在) [之外转到页面](https://blogs.windows.com/msedgedev/2017/12/19) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-157">Starting in EdgeHTML 17, Service Workers and push notifications are enabled by default \(learn more about these features in the blog post [Service Worker: Going beyond the page](https://blogs.windows.com/msedgedev/2017/12/19)).</span></span>  <span data-ttu-id="ed8ef-158">这将完成一套技术 (，包括获取网络和推送和缓存 Api \ ) ，用于在 Windows 10 上为累进 Web Apps (PWAs \ ) 布局技术基础。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-158">This completes the suite of technologies \(including Fetch networking and the Push and Cache APIs\) that lays the technical foundation for progressive Web Apps \(PWAs\) on Windows 10.</span></span>  

<span data-ttu-id="ed8ef-159">PWAs 是一种 web 应用，可在支持平台和浏览器引擎（如安装/主屏幕启动、脱机支持和推送通知）的情况下 [逐渐增强](https://en.wikipedia.org/wiki/Progressive_enhancement) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-159">PWAs are simply web apps that are [progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement) with native app-like features on supporting platforms and browser engines, such as installation / home screen launch, offline support, and push notifications.</span></span>  <span data-ttu-id="ed8ef-160">在使用 Microsoft Edge \ (EdgeHTML \ ) 引擎的 Windows 10 上，PWAs 将独立于浏览器窗口运行的额外优势视为 [通用 Windows 平台](/windows/uwp/get-started/whats-a-uwp) 应用。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-160">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform](/windows/uwp/get-started/whats-a-uwp) apps.</span></span>  

<span data-ttu-id="ed8ef-161">除了 PWAs，服务工作者和缓存 API 使开发人员能够从缓存中截获网络请求和响应。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-161">Beyond PWAs, Service Workers and the Cache API allow developers the ability to intercept network requests and respond from the cache.</span></span>  <span data-ttu-id="ed8ef-162">网站甚至不需要是完整的 web 应用，即可利用服务工作人员缓存实现 tined 页面加载性能和可靠性，以及在没有 internet 或质量连接期间提供脱机体验的功能。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-162">A website need not even been a full-blow web app to take advantage of the Service Worker cache for fine-tined page load performance and reliability, as well as the ability to provide an offline experience during periods of no internet or poor-quality connection.</span></span>  

<span data-ttu-id="ed8ef-163">转到我们 [的 windows 文档上的渐进式 Web 应用](../../progressive-web-apps-edgehtml/index.md) ，了解有关服务工作者的更多信息以及有关 Windows 10 上的 PWAs 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-163">Head over to our [Progressive Web Apps on Windows](../../progressive-web-apps-edgehtml/index.md) docs to learn more about Service Workers and details about PWAs on Windows 10.</span></span>  

### <span data-ttu-id="ed8ef-164">Web 安全</span><span class="sxs-lookup"><span data-stu-id="ed8ef-164">Web Security</span></span>  

<span data-ttu-id="ed8ef-165">EdgeHTML 17 引入了对子资源完整性 \ (斯里兰卡的支持 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-165">EdgeHTML 17 introduces support for Subresource Integrity \(SRI\).</span></span>  <span data-ttu-id="ed8ef-166">[子资源完整性](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 是一种安全功能，允许浏览器验证提取的资源 \ (（如图像、脚本、字体等）是否在未进行意外操作的情况下传递 ) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-166">[Subresource Integrity](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) is a security feature that allows browsers to verify that fetched resources \(such as images, scripts, fonts, and so on\) are delivered without unexpected manipulation.</span></span>  

<span data-ttu-id="ed8ef-167">添加一个 `integrity` 属性，其中包含你希望在网页上加载的资源的加密哈希表示形式 `<script>` `<link>` ，如下面的示例所示。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-167">Add an `integrity` attribute containing a cryptographic hash representation of the resource that you expect to load on your webpage to a `<script>` or `<link>` element, like the example below.</span></span>  <span data-ttu-id="ed8ef-168">然后，Microsoft Edge 会将所请求的资源与属性中定义的哈希进行比较 `integrity` 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-168">Then, Microsoft Edge will compare the requested resource to the hash defined in the `integrity` attribute.</span></span>  <span data-ttu-id="ed8ef-169">如果它们不匹配，Microsoft Edge 将不会执行资源，并向网络返回一个错误。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-169">If they do not match, Microsoft Edge will not execute the resource and returns an error to the network.</span></span>  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

<span data-ttu-id="ed8ef-170">另外，EdgeHTML 17 中的新增功能是不 [安全的请求](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) 请求标头，允许浏览器请求安全浏览体验。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-170">Also new in EdgeHTML 17, the [Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) request header allows browsers to request a secure browsing experience.</span></span>  <span data-ttu-id="ed8ef-171">此标题指示服务器浏览器支持升级任何不安全的请求，并且用户应被重定向到网站的安全版本（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-171">This header tells the server that the browser supports upgrading any insecure requests and the user should be redirected to a secure version of the site if available.</span></span>  

### <span data-ttu-id="ed8ef-172">可变字体</span><span class="sxs-lookup"><span data-stu-id="ed8ef-172">Variable Fonts</span></span>
<span data-ttu-id="ed8ef-173">对可变字体的完全支持 \ (包括 CSS [字体、变体设置](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) 和 [字体光大小](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\ ) 在 EdgeHTML 17 中可用。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-173">Full support for Variable Fonts \(including CSS [font-variation-settings](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) and [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) is available in EdgeHTML 17.</span></span>  <span data-ttu-id="ed8ef-174">利用可变字体，开发人员可以通过调整各种坐标轴来实现外观不同的字体外观，从而减少对多个字体文件和 bettering 性能的需求。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-174">Variable fonts enable developers to achieve the look of seemingly different typefaces with a single font by adjusting various axes – reducing the need for multiple font files and bettering performance.</span></span>  

<span data-ttu-id="ed8ef-175">加入我们的 [expedition，了解哪些可变字体提供 web 开发人员和设计器](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)，以及如何在您的网站上使用它们。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-175">Join us on [an expedition to learn about what variable fonts provide web developers and designers](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts), and how to use them on your site.</span></span>  <span data-ttu-id="ed8ef-176">在博客文章中阅读有关可变字体的详细信息， [使具有可变字体的 Microsoft Edge 具有富于表现力和性能的版式](https://blogs.windows.com/msedgedev/2018/03/13)。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-176">And read more about Variable Fonts in the blog post, [Bringing expressive, performant typography to Microsoft Edge with Variable Fonts](https://blogs.windows.com/msedgedev/2018/03/13).</span></span>  

<iframe height='456' scrolling='no' title='<span data-ttu-id="ed8ef-177">可变 Tides 票证示例</span><span class="sxs-lookup"><span data-stu-id="ed8ef-177">Variable Tides ticket examples</span></span>' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="ed8ef-178">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> CodePen 上的 MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'> @MSEdgeDev </a>) 中的 <a href='https://codepen.io'> 笔变量 Tides 票证示例 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-178">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'>Variable Tides ticket examples</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="ed8ef-179">EdgeHTML 17 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="ed8ef-179">New APIs in EdgeHTML 17</span></span>  

<span data-ttu-id="ed8ef-180">下面是 EdgeHTML 17 中新 Api 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-180">Here's the full list of new APIs in EdgeHTML 17.</span></span>  <span data-ttu-id="ed8ef-181">它们以的格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-181">They are listed in the format of `[interface name].[api name]`.</span></span>  

> [!NOTE] 
> <span data-ttu-id="ed8ef-182">虽然在 DOM 中公开以下 Api，但某些 Api 的端到端行为可能仍在开发中。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-182">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="ed8ef-183">请参阅  [Microsoft Edge 平台状态](https://developer.microsoft.com/microsoft-edge/platform/status) ，了解有关功能支持的官方 word 功能。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-183">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

<iframe height='580' scrolling='no' title='<span data-ttu-id="ed8ef-184">EdgeHTML 17 中的新 Api</span><span class="sxs-lookup"><span data-stu-id="ed8ef-184">New APIs in EdgeHTML 17</span></span>' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="ed8ef-185">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> EdgeHTML 17 MSEdgeDev (中的笔新 api，请参阅 </a> <a href='https://codepen.io/MSEdgeDev'> CodePen 上的 @MSEdgeDev </a>) <a href='https://codepen.io'> </a> 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-185">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>New APIs in EdgeHTML 17</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

> [!TIP]
> <span data-ttu-id="ed8ef-186">我们已与其他浏览器和 web 社区 [合作](https://blogs.windows.com/msedgedev/2017/10/18) ，采用 [MDN web 文档](https://developer.mozilla.org) 作为针对当前和新兴的基于标准的 web 技术的有用、无偏差、不限浏览器的文档。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-186">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span>  <span data-ttu-id="ed8ef-187">你可以直接在 [MDN web 引用库](https://developer.mozilla.org/docs/Web)的每个页面中找到有关 EdgeHTML API 支持的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-187">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span>  <span data-ttu-id="ed8ef-188">有关 Microsoft Edge 中支持的最新功能，请访问 Microsoft Edge 的 [平台状态](https://developer.microsoft.com/microsoft-edge/status) 。</span><span class="sxs-lookup"><span data-stu-id="ed8ef-188">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/status) for the latest features supported in Microsoft Edge.</span></span>  

## <span data-ttu-id="ed8ef-189">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="ed8ef-189">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="ed8ef-190">EdgeHTML 13/Windows 内部版本 10586 (11/2015) </span><span class="sxs-lookup"><span data-stu-id="ed8ef-190">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)  

[<span data-ttu-id="ed8ef-191">EdgeHTML 14/Windows 内部版本 14393 (8/2016) </span><span class="sxs-lookup"><span data-stu-id="ed8ef-191">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)  

[<span data-ttu-id="ed8ef-192">EdgeHTML 15/Windows 内部版本 15063 (4/2017) </span><span class="sxs-lookup"><span data-stu-id="ed8ef-192">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)  

[<span data-ttu-id="ed8ef-193">EdgeHTML 16/Windows 内部版本 16299 (10/2017) </span><span class="sxs-lookup"><span data-stu-id="ed8ef-193">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](https://aka.ms/devguide_edgehtml_16)  
