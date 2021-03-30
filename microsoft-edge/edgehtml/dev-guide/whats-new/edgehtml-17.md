---
title: EdgeHTML 17 中的新功能和 API
description: 本指南概述了 EdgeHTML 17 中包含的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: edge， Web 开发， html， css， javascript， 开发人员
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 75429528fd814963a8c78e27f85564223fb2d3c8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232169"
---
# <span data-ttu-id="8c624-104">EdgeHTML 17 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="8c624-104">What's new in EdgeHTML 17</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="8c624-105">下面是 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) Web 平台中新增和更新的功能列表，作为 [Windows 10 2018](https://blogs.windows.com/windowsexperience/2018/04/27) 年 4 月更新 \(04/2018 内部版本 17134\) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c624-105">Here's a list of the new and updated features shipped in [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web platform, as part of the [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, Build 17134\).</span></span>  <span data-ttu-id="8c624-106">有关特定 [Windows Insider](https://insider.windows.com) Preview 内部版本的变化，请参阅 Microsoft [Edge 更改日志](https://developer.microsoft.com/microsoft-edge/platform/changelog) 和 [EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="8c624-106">For changes in specific [Windows Insider](https://insider.windows.com) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="8c624-107">下面是以下更改列表的 permalink： [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md)</span><span class="sxs-lookup"><span data-stu-id="8c624-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md).</span></span>  

## <span data-ttu-id="8c624-108">新增和更新的功能</span><span class="sxs-lookup"><span data-stu-id="8c624-108">New and updated features</span></span>  

### <span data-ttu-id="8c624-109">ARIA 1.1 角色、状态和事件</span><span class="sxs-lookup"><span data-stu-id="8c624-109">ARIA 1.1 Roles, States, and Events</span></span>  

<span data-ttu-id="8c624-110">EdgeHTML 17 增加了对可访问的富 Internet 应用程序[ (一) .1](https://w3.org/TR/wai-aria-1.1)规范中各种角色、状态和属性的支持，包括源、表单[、aria-haspopup、aria](https://w3.org/TR/wai-aria-1.1#aria-haspopup)[](https://www.w3.org/TR/wai-aria-1.1#feed)[占位符](https://w3.org/TR/wai-aria-1.1#aria-placeholder)等; [](https://www.w3.org/TR/wai-aria-1.1#form)在[更改日志中查找 ARIA 更新的完整列表](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。</span><span class="sxs-lookup"><span data-stu-id="8c624-110">EdgeHTML 17 adds support for various roles, states, and properties from the [Accessible Rich Internet Applications (WAI-ARIA) 1.1 specification](https://w3.org/TR/wai-aria-1.1), including [feed](https://www.w3.org/TR/wai-aria-1.1#feed), [form](https://www.w3.org/TR/wai-aria-1.1#form), [aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup), [aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder), and many more; find a [full list of ARIA updates in the changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299).</span></span>  <span data-ttu-id="8c624-111">通过此更新，EdgeHTML 17 现在支持在一个功能区 1.1 中定义的所有角色和属性。</span><span class="sxs-lookup"><span data-stu-id="8c624-111">With this update, EdgeHTML 17 now supports all roles and attributes defined in WAI-ARIA 1.1.</span></span>  <!--  Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.  -->  

### <span data-ttu-id="8c624-112">CSS 屏蔽</span><span class="sxs-lookup"><span data-stu-id="8c624-112">CSS masking</span></span>  

<span data-ttu-id="8c624-113">EdgeHTML 17 包括对 [CSS 屏蔽的实验性支持](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。</span><span class="sxs-lookup"><span data-stu-id="8c624-113">EdgeHTML 17 includes experimental support for [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking).</span></span>  <span data-ttu-id="8c624-114">部分实现引入了 CSS[掩码图像和](https://developer.mozilla.org/docs/Web/CSS/mask-image)[掩码大小](https://developer.mozilla.org/docs/Web/CSS/mask-size)属性。</span><span class="sxs-lookup"><span data-stu-id="8c624-114">The partial implementation introduces the CSS [mask-image](https://developer.mozilla.org/docs/Web/CSS/mask-image) and [mask-size](https://developer.mozilla.org/docs/Web/CSS/mask-size) properties.</span></span>  <span data-ttu-id="8c624-115">检查 about：flags 中的"启用 CSS 屏蔽"标志以进行试验！</span><span class="sxs-lookup"><span data-stu-id="8c624-115">Check the "Enable CSS Masking" flag in about:flags to being experimenting!</span></span>  

### <span data-ttu-id="8c624-116">SVG 元素上的 CSS 转换</span><span class="sxs-lookup"><span data-stu-id="8c624-116">CSS transforms on SVG elements</span></span>  

<span data-ttu-id="8c624-117">EdgeHTML 17 现在支持对 SVG 元素和演示文稿属性进行 CSS 转换。</span><span class="sxs-lookup"><span data-stu-id="8c624-117">EdgeHTML 17 now supports CSS transforms on SVG elements and presentation attributes.</span></span>  <span data-ttu-id="8c624-118">这使 SVG 元素可以直观地操作，包括旋转、缩放、移动、扭曲或转换。</span><span class="sxs-lookup"><span data-stu-id="8c624-118">This allows SVG elements to be visually manipulated, including rotating, scaling, moving, skewing, or translating.</span></span>  

### <span data-ttu-id="8c624-119">Extensions</span><span class="sxs-lookup"><span data-stu-id="8c624-119">Extensions</span></span>  

<span data-ttu-id="8c624-120">Microsoft Edge 现在支持显示来自扩展的通知[的通知 API。](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications)</span><span class="sxs-lookup"><span data-stu-id="8c624-120">Microsoft Edge now supports the [Notification API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) which displays notifications from extensions.</span></span>  <span data-ttu-id="8c624-121">扩展开发人员现在可以创建不同类型的通知\(基本、列表、图像等\) 支持完全用户交互。</span><span class="sxs-lookup"><span data-stu-id="8c624-121">Extension developers can now create different types of notifications \(basic, list, image  and so on\) which support full user interaction.</span></span>  <span data-ttu-id="8c624-122">通知还会自动登录到操作中心。</span><span class="sxs-lookup"><span data-stu-id="8c624-122">The notifications are also automatically logged into the Action Center.</span></span>  <span data-ttu-id="8c624-123">访问 [有关如何在](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) 扩展中使用此 API 的通知示例。</span><span class="sxs-lookup"><span data-stu-id="8c624-123">Visit the [notifications sample](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) on how to use this API in your extension.</span></span>  

<span data-ttu-id="8c624-124">EdgeHTML 17 现在还支持将该方法作为标准选项卡 `Tabs.reload()` API 类的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c624-124">EdgeHTML 17 now also supports the `Tabs.reload()` method as part of the standard tabs API class.</span></span>  <span data-ttu-id="8c624-125">同样是 Windows 10 2018 年 4 月更新中的新增功能，用户现在可以选择允许在 inPrivate 浏览期间运行扩展。</span><span class="sxs-lookup"><span data-stu-id="8c624-125">Also new in the Windows 10 April 2018 Update, users can now choose to allow extensions to run during inPrivate browsing.</span></span>  

<span data-ttu-id="8c624-126">有关此版本中的扩展更新的更多详细信息，请前往博客文章 [2018](https://blogs.windows.com/msedgedev/2018/05/24)年 4 月 10 日更新中扩展的新功能。</span><span class="sxs-lookup"><span data-stu-id="8c624-126">For more details on extensions updates in this release, head over to the blog post [New features for extensions in the Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24).</span></span>  

### <span data-ttu-id="8c624-127">开发工具</span><span class="sxs-lookup"><span data-stu-id="8c624-127">DevTools</span></span>  

<span data-ttu-id="8c624-128">此版本的 DevTools 以两种方式提供：作为 Microsoft Edge 的传统浏览器内 \(\) 工具，以及从 Microsoft Store 预览为独立 `F12` [Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) 应用！</span><span class="sxs-lookup"><span data-stu-id="8c624-128">This release of the DevTools ships in two ways: as the traditional in-browser \(`F12`\) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge DevTools 应用" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   <span data-ttu-id="8c624-130">Microsoft Edge DevTools 应用</span><span class="sxs-lookup"><span data-stu-id="8c624-130">Microsoft Edge DevTools app</span></span>  
:::image-end:::  

<span data-ttu-id="8c624-131">这些工具还更新了一些主要功能，包括通过我们新的[](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) [DevTools 协议](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\(、PWA 调试功能[](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)[、IndexedDB](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)缓存管理、[](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)垂直停靠等对远程调试 \)  (的基本支持！</span><span class="sxs-lookup"><span data-stu-id="8c624-131">The tools have also been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(via our new [DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\), [PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging), [IndexedDB cache management](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection), [vertical docking](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="8c624-132">作为对性能和可靠性的持续[](./edgehtml-16.md)投资一部分，我们还继续进行上一版本开始的整体重构工作。</span><span class="sxs-lookup"><span data-stu-id="8c624-132">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>  

<span data-ttu-id="8c624-133">有关详细信息[，请访问 EdgeHTML 17 (Windows 10) 中的 DevTools。](../../devtools-guide/whats-new/edgehtml-17.md)</span><span class="sxs-lookup"><span data-stu-id="8c624-133">Visit [DevTools in the latest Windows 10 update (EdgeHTML 17)](../../devtools-guide/whats-new/edgehtml-17.md) for more details.</span></span>  

### <span data-ttu-id="8c624-134">JavaScript</span><span class="sxs-lookup"><span data-stu-id="8c624-134">JavaScript</span></span>  

<span data-ttu-id="8c624-135">借助 EdgeHTML 17，Chakra JavaScript 引擎在一些关键方面引入了性能改进：</span><span class="sxs-lookup"><span data-stu-id="8c624-135">With EdgeHTML 17 the Chakra JavaScript engine introduces performance improvements in a number of key areas:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="8c624-136">更精简的内存占用</span><span class="sxs-lookup"><span data-stu-id="8c624-136">Leaner memory footprint</span></span>**  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="8c624-137">\(对象) 的 [箭头](https://github.com/Microsoft/ChakraCore/pull/4105) 函数和方法的 Re-\) [延迟分析](https://github.com/Microsoft/ChakraCore/pull/4136)</span><span class="sxs-lookup"><span data-stu-id="8c624-137">\(Re-\)defer parsing for [arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105) and [methods on object literals](https://github.com/Microsoft/ChakraCore/pull/4136)</span></span>  
      *   [<span data-ttu-id="8c624-138">RegExp 字节码重构</span><span class="sxs-lookup"><span data-stu-id="8c624-138">RegExp bytecode refactoring</span></span>](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8c624-139">更快的 JavaScript 内置</span><span class="sxs-lookup"><span data-stu-id="8c624-139">Faster JavaScript built-ins</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="8c624-140">Object.create 的类型共享</span><span class="sxs-lookup"><span data-stu-id="8c624-140">Type sharing for Object.create</span></span>](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [<span data-ttu-id="8c624-141">Object.assign 的多态内嵌缓存</span><span class="sxs-lookup"><span data-stu-id="8c624-141">Polymorphic inline cache for Object.assign</span></span>](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [<span data-ttu-id="8c624-142">JSON.parse/stringify 优化</span><span class="sxs-lookup"><span data-stu-id="8c624-142">JSON.parse/stringify optimizations</span></span>](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [<span data-ttu-id="8c624-143">在 JavaScript 中重写数组 Iterator，并更快...of</span><span class="sxs-lookup"><span data-stu-id="8c624-143">Rewriting Array Iterators in JavaScript and faster for...of</span></span>](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="8c624-144">Web 程序集</span><span class="sxs-lookup"><span data-stu-id="8c624-144">Web Assembly</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="8c624-145">Inling 支持</span><span class="sxs-lookup"><span data-stu-id="8c624-145">Inling support</span></span>](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="8c624-146">查看 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) 中改进的 JavaScript 和 WebAssembly 性能，了解所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="8c624-146">Check out [Improved JavaScript and WebAssembly performance in EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) for all the details.</span></span>  

### <span data-ttu-id="8c624-147">媒体元素</span><span class="sxs-lookup"><span data-stu-id="8c624-147">Media element</span></span>

<span data-ttu-id="8c624-148">EdgeHTML 17 包括 [HTMLMediaElement 更新](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) ，其中包括：</span><span class="sxs-lookup"><span data-stu-id="8c624-148">EdgeHTML 17 includes updates to [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) including:</span></span>  

*   <span data-ttu-id="8c624-149">元素 `preload` 上的新 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 属性指示应预加载哪些数据。</span><span class="sxs-lookup"><span data-stu-id="8c624-149">The new `preload` attribute on the [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) element indicates what data should be preloaded.</span></span>
*   <span data-ttu-id="8c624-150">添加方法和 [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) 属性后 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) ，开发人员可以选择音频输出设备。</span><span class="sxs-lookup"><span data-stu-id="8c624-150">The addition of the [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) method and [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) property allow developers to select the audio output device.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="8c624-151">这尚未在 RTC 中提供。</span><span class="sxs-lookup"><span data-stu-id="8c624-151">This is not yet available in RTC.</span></span>  
    
### <span data-ttu-id="8c624-152">媒体捕获 API</span><span class="sxs-lookup"><span data-stu-id="8c624-152">Media Capture API</span></span>  

<span data-ttu-id="8c624-153">Microsoft Edge 现在通过媒体捕获 API 支持 RTC [中的屏幕捕获](https://w3c.github.io/mediacapture-screen-share)。</span><span class="sxs-lookup"><span data-stu-id="8c624-153">Microsoft Edge now supports Screen Capture in RTC via the [Media Capture API](https://w3c.github.io/mediacapture-screen-share).</span></span>  <span data-ttu-id="8c624-154">此功能允许网页捕获用户显示设备的输出，通常用于为无插件虚拟会议或演示文稿广播桌面。</span><span class="sxs-lookup"><span data-stu-id="8c624-154">This feature lets web pages capture output of a user's display device, commonly used to broadcast a desktop for plugin-free virtual meetings or presentation.</span></span>  

### <span data-ttu-id="8c624-155">渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="8c624-155">Progressive Web Apps</span></span>  

<span data-ttu-id="8c624-156">从 EdgeHTML 17 开始，默认情况下启用服务工作者和推送通知 \(在博客文章 ["](https://blogs.windows.com/msedgedev/2017/12/19) 服务工作者：超出页面范围"中了解有关这些功能) 。</span><span class="sxs-lookup"><span data-stu-id="8c624-156">Starting in EdgeHTML 17, Service Workers and push notifications are enabled by default \(learn more about these features in the blog post [Service Worker: Going beyond the page](https://blogs.windows.com/msedgedev/2017/12/19)).</span></span>  <span data-ttu-id="8c624-157">这将完成一套技术 \(包括提取网络和推送和缓存 API\) ，这些技术为 Windows 10 上的渐进 Web 应用 \(PWA\) 提供技术基础。</span><span class="sxs-lookup"><span data-stu-id="8c624-157">This completes the suite of technologies \(including Fetch networking and the Push and Cache APIs\) that lays the technical foundation for progressive Web Apps \(PWAs\) on Windows 10.</span></span>  

<span data-ttu-id="8c624-158">PWA 只是一些 Web[](https://en.wikipedia.org/wiki/Progressive_enhancement)应用，通过支持平台和浏览器引擎上的本机类似应用功能（如安装/主屏幕启动、脱机支持和推送通知）逐步增强。</span><span class="sxs-lookup"><span data-stu-id="8c624-158">PWAs are simply web apps that are [progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement) with native app-like features on supporting platforms and browser engines, such as installation / home screen launch, offline support, and push notifications.</span></span>  <span data-ttu-id="8c624-159">在具有 Microsoft Edge \(EdgeHTML\) 引擎的 Windows 10 上，PWA 享受独立于浏览器窗口作为通用 [Windows 平台应用运行的附加](/windows/uwp/get-started/whats-a-uwp) 优势。</span><span class="sxs-lookup"><span data-stu-id="8c624-159">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform](/windows/uwp/get-started/whats-a-uwp) apps.</span></span>  

<span data-ttu-id="8c624-160">除了 PWA 之外，服务工作者和缓存 API 还允许开发人员截获网络请求和从缓存进行响应。</span><span class="sxs-lookup"><span data-stu-id="8c624-160">Beyond PWAs, Service Workers and the Cache API allow developers the ability to intercept network requests and respond from the cache.</span></span>  <span data-ttu-id="8c624-161">网站甚至不需要是一个全面的 Web 应用，以利用服务工作器缓存实现精细的页面加载性能和可靠性，以及能够在没有 Internet 或质量较差的连接期间提供脱机体验。</span><span class="sxs-lookup"><span data-stu-id="8c624-161">A website need not even been a full-blow web app to take advantage of the Service Worker cache for fine-tined page load performance and reliability, as well as the ability to provide an offline experience during periods of no internet or poor-quality connection.</span></span>  

<span data-ttu-id="8c624-162">前往 Windows 上的 [渐进式 Web 应用](../../progressive-web-apps/index.md) 文档，了解有关服务工作者的详细信息，以及 Windows 10 上的 PWA 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8c624-162">Head over to our [Progressive Web Apps on Windows](../../progressive-web-apps/index.md) docs to learn more about Service Workers and details about PWAs on Windows 10.</span></span>  

### <span data-ttu-id="8c624-163">Web 安全性</span><span class="sxs-lookup"><span data-stu-id="8c624-163">Web Security</span></span>  

<span data-ttu-id="8c624-164">EdgeHTML 17 引入了对子资源完整性 \(SRE\) 。</span><span class="sxs-lookup"><span data-stu-id="8c624-164">EdgeHTML 17 introduces support for Subresource Integrity \(SRI\).</span></span>  <span data-ttu-id="8c624-165">[子资源](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 完整性是一项安全功能，允许浏览器验证提取的资源 \(如图像、脚本、字体等\) 是否交付，而无需意外操作。</span><span class="sxs-lookup"><span data-stu-id="8c624-165">[Subresource Integrity](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) is a security feature that allows browsers to verify that fetched resources \(such as images, scripts, fonts, and so on\) are delivered without unexpected manipulation.</span></span>  

<span data-ttu-id="8c624-166">添加一个属性，其中包含您预期在网页上加载到某个或元素中的资源的加密哈希表示形式， `integrity` `<script>` `<link>` 如以下示例所示。</span><span class="sxs-lookup"><span data-stu-id="8c624-166">Add an `integrity` attribute containing a cryptographic hash representation of the resource that you expect to load on your webpage to a `<script>` or `<link>` element, like the example below.</span></span>  <span data-ttu-id="8c624-167">然后，Microsoft Edge 将请求的资源与属性中定义的哈希 `integrity` 进行比较。</span><span class="sxs-lookup"><span data-stu-id="8c624-167">Then, Microsoft Edge will compare the requested resource to the hash defined in the `integrity` attribute.</span></span>  <span data-ttu-id="8c624-168">如果不匹配，Microsoft Edge 将不会执行资源，并且会向网络返回错误。</span><span class="sxs-lookup"><span data-stu-id="8c624-168">If they do not match, Microsoft Edge will not execute the resource and returns an error to the network.</span></span>  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

<span data-ttu-id="8c624-169">也是 EdgeHTML 17 中的新增功能 [，Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) 请求标头允许浏览器请求安全浏览体验。</span><span class="sxs-lookup"><span data-stu-id="8c624-169">Also new in EdgeHTML 17, the [Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) request header allows browsers to request a secure browsing experience.</span></span>  <span data-ttu-id="8c624-170">此标头告知服务器，浏览器支持升级任何不安全的请求，并且用户应重定向到网站的安全版本（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="8c624-170">This header tells the server that the browser supports upgrading any insecure requests and the user should be redirected to a secure version of the site if available.</span></span>  

### <span data-ttu-id="8c624-171">变量字体</span><span class="sxs-lookup"><span data-stu-id="8c624-171">Variable Fonts</span></span>
<span data-ttu-id="8c624-172">EdgeHTML 17 中完全支持变量字体 \(包括 [CSS](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) 字体变体设置和字体光学 [大小调整](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) 。</span><span class="sxs-lookup"><span data-stu-id="8c624-172">Full support for Variable Fonts \(including CSS [font-variation-settings](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) and [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) is available in EdgeHTML 17.</span></span>  <span data-ttu-id="8c624-173">变量字体使开发人员通过调整各种轴来实现看起来不同的字样外观，从而通过调整各种轴实现看起来不同的字样，从而减少对多个字体文件以及提高性能的需要。</span><span class="sxs-lookup"><span data-stu-id="8c624-173">Variable fonts enable developers to achieve the look of seemingly different typefaces with a single font by adjusting various axes – reducing the need for multiple font files and bettering performance.</span></span>  

<span data-ttu-id="8c624-174">加入我们 [，了解](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)哪些变量字体为 Web 开发人员和设计人员提供，以及如何在你的网站上使用它们。</span><span class="sxs-lookup"><span data-stu-id="8c624-174">Join us on [an expedition to learn about what variable fonts provide web developers and designers](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts), and how to use them on your site.</span></span>  <span data-ttu-id="8c624-175">在博客文章阅读有关变量字体的更多内容，使用变量字体为 Microsoft Edge 带来具有表现力、性能高明 [的版式](https://blogs.windows.com/msedgedev/2018/03/13)。</span><span class="sxs-lookup"><span data-stu-id="8c624-175">And read more about Variable Fonts in the blog post, [Bringing expressive, performant typography to Microsoft Edge with Variable Fonts](https://blogs.windows.com/msedgedev/2018/03/13).</span></span>  

<iframe height='456' scrolling='no' title='<span data-ttu-id="8c624-176">变量变量票证示例</span><span class="sxs-lookup"><span data-stu-id="8c624-176">Variable Tides ticket examples</span></span>' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="8c624-177">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> </a> MsEdgeDev 在 <a href='https://codepen.io/MSEdgeDev'> CodePen 上 (@MSEdgeDev) </a> 的笔变量变量票证 <a href='https://codepen.io'> 示例 </a> 。</span><span class="sxs-lookup"><span data-stu-id="8c624-177">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'>Variable Tides ticket examples</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="8c624-178">EdgeHTML 17 中的新 API</span><span class="sxs-lookup"><span data-stu-id="8c624-178">New APIs in EdgeHTML 17</span></span>  

<span data-ttu-id="8c624-179">以下是 EdgeHTML 17 中新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="8c624-179">Here's the full list of new APIs in EdgeHTML 17.</span></span>  <span data-ttu-id="8c624-180">它们以 . `[interface name].[api name]`</span><span class="sxs-lookup"><span data-stu-id="8c624-180">They are listed in the format of `[interface name].[api name]`.</span></span>  

> [!NOTE] 
> <span data-ttu-id="8c624-181">尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍处于开发阶段。</span><span class="sxs-lookup"><span data-stu-id="8c624-181">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="8c624-182">有关  [功能支持的官方](https://developer.microsoft.com/microsoft-edge/platform/status) 词语，请参阅 Microsoft Edge 平台状态。</span><span class="sxs-lookup"><span data-stu-id="8c624-182">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

<iframe height='580' scrolling='no' title='<span data-ttu-id="8c624-183">EdgeHTML 17 中的新 API</span><span class="sxs-lookup"><span data-stu-id="8c624-183">New APIs in EdgeHTML 17</span></span>' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="8c624-184">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> New API in EdgeHTML 17 </a> by MSEdgeDev <a href='https://codepen.io/MSEdgeDev'> (@MSEdgeDev) </a> on <a href='https://codepen.io'> CodePen </a> .</span><span class="sxs-lookup"><span data-stu-id="8c624-184">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>New APIs in EdgeHTML 17</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

> [!TIP]
> <span data-ttu-id="8c624-185">我们已与其他浏览器[](https://blogs.windows.com/msedgedev/2017/10/18)和 Web 社区合作，采用[MDN Web 文档](https://developer.mozilla.org)作为针对当前和新出现的基于标准的 Web 技术的有用、无偏不的浏览器不可知文档的最终位置。</span><span class="sxs-lookup"><span data-stu-id="8c624-185">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span>  <span data-ttu-id="8c624-186">可以直接在 MDN Web 引用库的每个页面中找到有关 EdgeHTML API [支持的详细信息](https://developer.mozilla.org/docs/Web)。</span><span class="sxs-lookup"><span data-stu-id="8c624-186">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span>  <span data-ttu-id="8c624-187">访问 Microsoft Edge [的平台状态，](https://developer.microsoft.com/microsoft-edge/status) 了解 Microsoft Edge 中支持的最新功能。</span><span class="sxs-lookup"><span data-stu-id="8c624-187">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/status) for the latest features supported in Microsoft Edge.</span></span>  

## <span data-ttu-id="8c624-188">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="8c624-188">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="8c624-189">EdgeHTML 13 /Windows 版本 10586 (2015 年 11 月 11 日) </span><span class="sxs-lookup"><span data-stu-id="8c624-189">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)  

[<span data-ttu-id="8c624-190">EdgeHTML 14 /Windows 版本 14393 (2016 年 8 月 8 日) </span><span class="sxs-lookup"><span data-stu-id="8c624-190">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)  

[<span data-ttu-id="8c624-191">EdgeHTML 15 /Windows 版本 15063 (2017 年 4 月 4 日) </span><span class="sxs-lookup"><span data-stu-id="8c624-191">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)  

[<span data-ttu-id="8c624-192">EdgeHTML 16 /Windows 版本 16299 (2017 年 10 月 10 日) </span><span class="sxs-lookup"><span data-stu-id="8c624-192">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](https://aka.ms/devguide_edgehtml_16)  
