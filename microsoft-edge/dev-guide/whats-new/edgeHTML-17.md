---
title: EdgeHTML 17 中的新功能和 API
description: 本指南概述了 EdgeHTML 17 中包括的开发人员功能和标准。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: 边缘， Web 开发， html， css， javascript， developer
ms.openlocfilehash: 0fc7dda532866e8970003bce2febb7e46fbbc459
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10941943"
---
# <span data-ttu-id="dc0ef-104">EdgeHTML 17 中的新增功能</span><span class="sxs-lookup"><span data-stu-id="dc0ef-104">What's new in EdgeHTML 17</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="dc0ef-105">下面是 [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) Web 平台中随之外出现的新功能和更新功能列表，作为 [Windows 10 2018 年 4 月更新](https://blogs.windows.com/windowsexperience/2018/04/27) \ (04/2018（内部版本 17134\) 的一部分）。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-105">Here's a list of the new and updated features shipped in [EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/04/30) web platform, as part of the [Windows 10 April 2018 Update](https://blogs.windows.com/windowsexperience/2018/04/27) \(04/2018, Build 17134\).</span></span>  <span data-ttu-id="dc0ef-106">有关特定 [Windows Insider](https://insider.windows.com) Preview 版本中的更改，请参阅 [Microsoft Edge 更改日](https://developer.microsoft.com/microsoft-edge/platform/changelog) 志 [和 EdgeHTML 中的新增功能](../whats-new.md)。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-106">For changes in specific [Windows Insider](https://insider.windows.com) Preview builds, see the [Microsoft Edge Changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog) and [What's New in EdgeHTML](../whats-new.md).</span></span>  

<span data-ttu-id="dc0ef-107">下面是下列更改列表的句号 [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md) ：。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-107">Here's the permalink for the following list of changes: [https://aka.ms/devguide_edgehtml_17](./edgehtml-17.md).</span></span>  

## <span data-ttu-id="dc0ef-108">新增功能和更新功能</span><span class="sxs-lookup"><span data-stu-id="dc0ef-108">New and updated features</span></span>  

### <span data-ttu-id="dc0ef-109">ARIA 1.1 角色、州和活动</span><span class="sxs-lookup"><span data-stu-id="dc0ef-109">ARIA 1.1 Roles, States, and Events</span></span>  

<span data-ttu-id="dc0ef-110">Microsoft EdgeHTML 17 增加了对可访问富 Internet 应用程序中各种角色[、状态和属性的支持 (WAI-ARIA) 1.1 规](https://w3.org/TR/wai-aria-1.1)范，包括[订阅源](https://www.w3.org/TR/wai-aria-1.1#feed)、[form](https://www.w3.org/TR/wai-aria-1.1#form)表单[aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup)、名单里网页[、aria-占位符](https://w3.org/TR/wai-aria-1.1#aria-placeholder)等;在[更改日程中查找 ARIA 更新的完整列表](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299)。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-110">EdgeHTML 17 adds support for various roles, states, and properties from the [Accessible Rich Internet Applications (WAI-ARIA) 1.1 specification](https://w3.org/TR/wai-aria-1.1), including [feed](https://www.w3.org/TR/wai-aria-1.1#feed), [form](https://www.w3.org/TR/wai-aria-1.1#form), [aria-haspopup](https://w3.org/TR/wai-aria-1.1#aria-haspopup), [aria-placeholder](https://w3.org/TR/wai-aria-1.1#aria-placeholder), and many more; find a [full list of ARIA updates in the changelog](https://developer.microsoft.com/microsoft-edge/platform/changelog/desktop/17134/?compareWith=16299).</span></span>  <span data-ttu-id="dc0ef-111">通过此更新，EdgeHTML 17 现在支持在 WAI-ARIA 1.1 中定义的所有角色和属性。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-111">With this update, EdgeHTML 17 now supports all roles and attributes defined in WAI-ARIA 1.1.</span></span>  <span data-ttu-id="dc0ef-112">查看有关 Microsoft [Edge 辅](../../accessibility.md) 助功能的详细信息，请参阅辅助功能文档。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-112">Check out the [Accessibility](../../accessibility.md) docs for more information about accessibility in Microsoft Edge.</span></span>  

### <span data-ttu-id="dc0ef-113">CSS 掩码</span><span class="sxs-lookup"><span data-stu-id="dc0ef-113">CSS masking</span></span>  

<span data-ttu-id="dc0ef-114">EdgeHTML 17 包含对 [CSS 发表的实际支持](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking)。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-114">EdgeHTML 17 includes experimental support for [CSS Masking](https://developer.mozilla.org/docs/Web/CSS/CSS_Masking).</span></span>  <span data-ttu-id="dc0ef-115">部分实现引入了 CSS [mask 图像](https://developer.mozilla.org/docs/Web/CSS/mask-image)[和屏码大小](https://developer.mozilla.org/docs/Web/CSS/mask-size)属性。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-115">The partial implementation introduces the CSS [mask-image](https://developer.mozilla.org/docs/Web/CSS/mask-image) and [mask-size](https://developer.mozilla.org/docs/Web/CSS/mask-size) properties.</span></span>  <span data-ttu-id="dc0ef-116">请选中有关：标志的：标志的"启用 CSS 掩码"标志以试用！</span><span class="sxs-lookup"><span data-stu-id="dc0ef-116">Check the "Enable CSS Masking" flag in about:flags to being experimenting!</span></span>  

### <span data-ttu-id="dc0ef-117">SVG 元素上的 CSS 转换</span><span class="sxs-lookup"><span data-stu-id="dc0ef-117">CSS transforms on SVG elements</span></span>  

<span data-ttu-id="dc0ef-118">Microsoft EdgeHTML 17 现在支持 SVG 元素和演示属性上的 CSS 转换。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-118">EdgeHTML 17 now supports CSS transforms on SVG elements and presentation attributes.</span></span>  <span data-ttu-id="dc0ef-119">这允许以视觉方式操作 SVG 元素，包括旋转、缩放、移动、换行或翻译。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-119">This allows SVG elements to be visually manipulated, including rotating, scaling, moving, skewing, or translating.</span></span>  

### <span data-ttu-id="dc0ef-120">Extensions</span><span class="sxs-lookup"><span data-stu-id="dc0ef-120">Extensions</span></span>  

<span data-ttu-id="dc0ef-121">Microsoft Edge 现在支持 [通知 API，](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) 该 API 显示扩展中的通知。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-121">Microsoft Edge now supports the [Notification API](https://developer.mozilla.org/Add-ons/WebExtensions/API/notifications) which displays notifications from extensions.</span></span>  <span data-ttu-id="dc0ef-122">扩展开发人员现在可以创建不同类型的通知 \ (基本、列表、图像等（支持 ) 完整用户交互）。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-122">Extension developers can now create different types of notifications \(basic, list, image  and so on\) which support full user interaction.</span></span>  <span data-ttu-id="dc0ef-123">这些通知还会自动登录到操作中心。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-123">The notifications are also automatically logged into the Action Center.</span></span>  <span data-ttu-id="dc0ef-124">访问关 [于如何在](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) 扩展中使用此 API 的通知示例。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-124">Visit the [notifications sample](https://github.com/MicrosoftEdge/MicrosoftEdge-Extensions-Demos/tree/notifications/notifications) on how to use this API in your extension.</span></span>  

<span data-ttu-id="dc0ef-125">EdgeHTML 17 现在还支持作为 `Tabs.reload()` 标准选项卡 API 类的一部分的方法。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-125">EdgeHTML 17 now also supports the `Tabs.reload()` method as part of the standard tabs API class.</span></span>  <span data-ttu-id="dc0ef-126">此外，Windows 10 2018 年 4 月更新中新的版订阅现在用户可以选择允许扩展在 inPrivate 浏览过程中运行。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-126">Also new in the Windows 10 April 2018 Update, users can now choose to allow extensions to run during inPrivate browsing.</span></span>  

<span data-ttu-id="dc0ef-127">有关此版本中的扩展更新的更多详细信息，请转到 [Windows 10 2018 年 4](https://blogs.windows.com/msedgedev/2018/05/24)月更新中的博客文章新功能。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-127">For more details on extensions updates in this release, head over to the blog post [New features for extensions in the Windows 10 April 2018 Update](https://blogs.windows.com/msedgedev/2018/05/24).</span></span>  

### <span data-ttu-id="dc0ef-128">DevTools</span><span class="sxs-lookup"><span data-stu-id="dc0ef-128">DevTools</span></span>  

<span data-ttu-id="dc0ef-129">这个版本的 DevTools 以两种方式交付：作为 Microsoft Edge 的传统浏览器 \ (`F12` \) 工具，然后作为 Microsoft Store 中的随 [机 Windows 10](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) 应用进行预览！</span><span class="sxs-lookup"><span data-stu-id="dc0ef-129">This release of the DevTools ships in two ways: as the traditional in-browser \(`F12`\) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](../../devtools-guide/whats-new/edgehtml-17.md#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>  

:::image type="complex" source="../../devtools-protocol/media/microsoft-edge-devtools.png" alt-text="Microsoft Edge 开发工具应用" lightbox="../../devtools-protocol/media/microsoft-edge-devtools.png":::
   <span data-ttu-id="dc0ef-131">Microsoft Edge 开发工具应用</span><span class="sxs-lookup"><span data-stu-id="dc0ef-131">Microsoft Edge DevTools app</span></span>  
:::image-end:::  

<span data-ttu-id="dc0ef-132">该工具也会使用许多主要功能进行了更新，其中[包括通过新的](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) [DevTools 协](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)议 \) 、PWA 调试功能[、IndexedDB 缓存管理](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection)、垂直[PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging)停运来管理等[对远](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge)程调试 \ (的基本支持！</span><span class="sxs-lookup"><span data-stu-id="dc0ef-132">The tools have also been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol) \(via our new [DevTools Protocol](../../devtools-guide/whats-new/edgehtml-17.md#devtools-protocol)\), [PWA debugging features](../../devtools-guide/whats-new/edgehtml-17.md#pwa-debugging), [IndexedDB cache management](../../devtools-guide/whats-new/edgehtml-17.md#indexeddb-inspection), [vertical docking](../../devtools-guide/whats-new/edgehtml-17.md#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="dc0ef-133">我们还在持续的性能 [和](./edgehtml-16.md) 可靠性的同时，我们还将延续整体重构工作。我们还在持续改进性能和可靠性方面继续了整体重身协作。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-133">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>  

<span data-ttu-id="dc0ef-134">有关详细信息，[请访问最新 Windows 10 更新 (的 Windows 10 开发工具) 中的 DevTools。](../../devtools-guide/whats-new/edgehtml-17.md)</span><span class="sxs-lookup"><span data-stu-id="dc0ef-134">Visit [DevTools in the latest Windows 10 update (EdgeHTML 17)](../../devtools-guide/whats-new/edgehtml-17.md) for more details.</span></span>  

### <span data-ttu-id="dc0ef-135">JavaScript</span><span class="sxs-lookup"><span data-stu-id="dc0ef-135">JavaScript</span></span>  

<span data-ttu-id="dc0ef-136">借助 Microsoft EdgeHTML 17，Chakra JavaScript 引文在许多关键方面引入了性能改进：</span><span class="sxs-lookup"><span data-stu-id="dc0ef-136">With EdgeHTML 17 the Chakra JavaScript engine introduces performance improvements in a number of key areas:</span></span>  

:::row:::
   :::column span="1":::
      **<span data-ttu-id="dc0ef-137">更简单的内存量足</span><span class="sxs-lookup"><span data-stu-id="dc0ef-137">Leaner memory footprint</span></span>**  
   :::column-end:::
   :::column span="2":::
      *   <span data-ttu-id="dc0ef-138">\ (Re-\) ，针对对象[文本上箭头函数](https://github.com/Microsoft/ChakraCore/pull/4105)[和方法进行延迟分析](https://github.com/Microsoft/ChakraCore/pull/4136)</span><span class="sxs-lookup"><span data-stu-id="dc0ef-138">\(Re-\)defer parsing for [arrow functions](https://github.com/Microsoft/ChakraCore/pull/4105) and [methods on object literals](https://github.com/Microsoft/ChakraCore/pull/4136)</span></span>  
      *   [<span data-ttu-id="dc0ef-139">RegExp 字节码重造</span><span class="sxs-lookup"><span data-stu-id="dc0ef-139">RegExp bytecode refactoring</span></span>](https://github.com/Microsoft/ChakraCore/pull/3915)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="dc0ef-140">速度更快的 JavaScript</span><span class="sxs-lookup"><span data-stu-id="dc0ef-140">Faster JavaScript built-ins</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="dc0ef-141">类型共享对象.create</span><span class="sxs-lookup"><span data-stu-id="dc0ef-141">Type sharing for Object.create</span></span>](https://github.com/Microsoft/ChakraCore/pull/3901)  
      *   [<span data-ttu-id="dc0ef-142">Object.assign 的 Polymorphic 以嵌入式缓存</span><span class="sxs-lookup"><span data-stu-id="dc0ef-142">Polymorphic inline cache for Object.assign</span></span>](https://github.com/Microsoft/ChakraCore/pull/3792)  
      *   [<span data-ttu-id="dc0ef-143">JSON.parse/stringify 优化</span><span class="sxs-lookup"><span data-stu-id="dc0ef-143">JSON.parse/stringify optimizations</span></span>](https://github.com/Microsoft/ChakraCore/pull/4077)  
      *   [<span data-ttu-id="dc0ef-144">在 JavaScript 中重写数组接标，更快...的</span><span class="sxs-lookup"><span data-stu-id="dc0ef-144">Rewriting Array Iterators in JavaScript and faster for...of</span></span>](https://github.com/Microsoft/ChakraCore/pull/4095)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      **<span data-ttu-id="dc0ef-145">Web 组编程</span><span class="sxs-lookup"><span data-stu-id="dc0ef-145">Web Assembly</span></span>**
   :::column-end:::
   :::column span="2":::
      *   [<span data-ttu-id="dc0ef-146">Inling 支持</span><span class="sxs-lookup"><span data-stu-id="dc0ef-146">Inling support</span></span>](https://github.com/Microsoft/ChakraCore/pull/3681)  
   :::column-end:::
:::row-end:::  

<span data-ttu-id="dc0ef-147">查看改 [进的 JavaScript 和 EdgeHTML 17 中改进的 JavaScript 和 WebAssembly 性能](https://blogs.windows.com/msedgedev/2018/06/19) ，了解所有详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-147">Check out [Improved JavaScript and WebAssembly performance in EdgeHTML 17](https://blogs.windows.com/msedgedev/2018/06/19) for all the details.</span></span>  

### <span data-ttu-id="dc0ef-148">媒体元素</span><span class="sxs-lookup"><span data-stu-id="dc0ef-148">Media element</span></span>

<span data-ttu-id="dc0ef-149">Microsoft EdgeHTML 17 包括 [对 HTMLMediaElement 的更新，](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 包括：</span><span class="sxs-lookup"><span data-stu-id="dc0ef-149">EdgeHTML 17 includes updates to [HTMLMediaElement](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) including:</span></span>  

*   <span data-ttu-id="dc0ef-150">元素 `preload` 上的新 [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) 属性指示应该预加载哪些数据。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-150">The new `preload` attribute on the [`<media>`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement) element indicates what data should be preloaded.</span></span>
*   <span data-ttu-id="dc0ef-151">添加方法和属性 [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) 将 [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) 允许开发人员选择音频输出设备。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-151">The addition of the [`setSinkId()`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/setSinkId) method and [`sinkId`](https://developer.mozilla.org/docs/Web/API/HTMLMediaElement/sinkId) property allow developers to select the audio output device.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="dc0ef-152">尚未在 RTC 中提供。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-152">This is not yet available in RTC.</span></span>  
    
### <span data-ttu-id="dc0ef-153">媒体捕获 API</span><span class="sxs-lookup"><span data-stu-id="dc0ef-153">Media Capture API</span></span>  

<span data-ttu-id="dc0ef-154">Microsoft Edge 现在通过媒体捕获 API 支持 RTC [的屏幕截图屏幕截图](https://w3c.github.io/mediacapture-screen-share)。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-154">Microsoft Edge now supports Screen Capture in RTC via the [Media Capture API](https://w3c.github.io/mediacapture-screen-share).</span></span>  <span data-ttu-id="dc0ef-155">此功能允许网页捕获用户的显示设备输出，通常用于针对无触传的虚拟会议或演示广播桌面。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-155">This feature lets web pages capture output of a user's display device, commonly used to broadcast a desktop for plugin-free virtual meetings or presentation.</span></span>  

### <span data-ttu-id="dc0ef-156">渐进式 Web 应用</span><span class="sxs-lookup"><span data-stu-id="dc0ef-156">Progressive Web Apps</span></span>  

<span data-ttu-id="dc0ef-157">从 EdgeHTML 17 开始，默认启用服务工作者和推送通知，模板将默认启用 \ (了解有关博客文章服务工作者中的以下功能 [的更多信息：除了页面](https://blogs.windows.com/msedgedev/2017/12/19)) 。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-157">Starting in EdgeHTML 17, Service Workers and push notifications are enabled by default \(learn more about these features in the blog post [Service Worker: Going beyond the page](https://blogs.windows.com/msedgedev/2017/12/19)).</span></span>  <span data-ttu-id="dc0ef-158">这将完成一套技术 \ (，包括获取网络以及 Push 和 Cache API\) （它依循 Windows 10 上的渐进式 Web 应用 \ (PWA\) ）进行技术基付。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-158">This completes the suite of technologies \(including Fetch networking and the Push and Cache APIs\) that lays the technical foundation for progressive Web Apps \(PWAs\) on Windows 10.</span></span>  

<span data-ttu-id="dc0ef-159">PWA 是仅通过支持平台和浏览器[progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement)引引器上的本机应用（如安装/主屏幕启动、脱机支持和推送通知）上的本机应用功能进行逐步增进的 Web 应用。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-159">PWAs are simply web apps that are [progressively enhanced](https://en.wikipedia.org/wiki/Progressive_enhancement) with native app-like features on supporting platforms and browser engines, such as installation / home screen launch, offline support, and push notifications.</span></span>  <span data-ttu-id="dc0ef-160">在带有 Microsoft Edge \ (EdgeHTML\) 引荐的 Windows 10 上，PWA 享受以通用 Windows 平台应用单独运行浏览器窗口 [的优](/windows/uwp/get-started/whats-a-uwp) 势。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-160">On Windows 10 with the Microsoft Edge \(EdgeHTML\) engine, PWAs enjoy the added advantage of running independently of the browser window as [Universal Windows Platform](/windows/uwp/get-started/whats-a-uwp) apps.</span></span>  

<span data-ttu-id="dc0ef-161">除 PWA、服务工作者和缓存 API 外，开发人员还可以从缓存中捕获网络请求和从缓存中进行响应。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-161">Beyond PWAs, Service Workers and the Cache API allow developers the ability to intercept network requests and respond from the cache.</span></span>  <span data-ttu-id="dc0ef-162">网站甚至不需要充分利用服务 Worker 缓存进行细化页面加载性能和可靠性，网站在没有 Internet 连接或质量较差的连接期内提供脱机体验的能力。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-162">A website need not even been a full-blow web app to take advantage of the Service Worker cache for fine-tined page load performance and reliability, as well as the ability to provide an offline experience during periods of no internet or poor-quality connection.</span></span>  

<span data-ttu-id="dc0ef-163">访问 Windows 上的渐进 [式 Web 应用，](../../progressive-web-apps-edgehtml/index.md) 了解有关在 Windows 10 中服务工作者和有关 PWA 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-163">Head over to our [Progressive Web Apps on Windows](../../progressive-web-apps-edgehtml/index.md) docs to learn more about Service Workers and details about PWAs on Windows 10.</span></span>  

### <span data-ttu-id="dc0ef-164">Web 安全性</span><span class="sxs-lookup"><span data-stu-id="dc0ef-164">Web Security</span></span>  

<span data-ttu-id="dc0ef-165">EdgeHTML 17 引入了对子资源完整性 \ (SRI\) 。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-165">EdgeHTML 17 introduces support for Subresource Integrity \(SRI\).</span></span>  <span data-ttu-id="dc0ef-166">[子资源完整性是](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) 一项安全功能，允许浏览器验证是否提供了资源 \ (如图像、脚本、字体等\) ，但不预期的操作。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-166">[Subresource Integrity](https://developer.mozilla.org/docs/Web/Security/Subresource_Integrity) is a security feature that allows browsers to verify that fetched resources \(such as images, scripts, fonts, and so on\) are delivered without unexpected manipulation.</span></span>  

<span data-ttu-id="dc0ef-167">添加一种包含预期将在网页上加载到或元素的资源 `integrity` 加密哈代表示的 `<script>` `<link>` 属性，如下例所示。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-167">Add an `integrity` attribute containing a cryptographic hash representation of the resource that you expect to load on your webpage to a `<script>` or `<link>` element, like the example below.</span></span>  <span data-ttu-id="dc0ef-168">然后，Microsoft Edge 会将请求的资源与该属性中定义的 `integrity` 哈值进行比较。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-168">Then, Microsoft Edge will compare the requested resource to the hash defined in the `integrity` attribute.</span></span>  <span data-ttu-id="dc0ef-169">如果它们不匹配，Microsoft Edge 将不执行该资源，并向网络返回错误。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-169">If they do not match, Microsoft Edge will not execute the resource and returns an error to the network.</span></span>  

```html
<script src="https://example.com/example-framework.js" 
        integrity="sha384-Li9vy3DqF8tnTXuiaAJuML3ky+er10rcgNR/VqsVpcw+ThHmYcwiB1pbOxEbzJr7" 
        crossorigin="anonymous"></script>
```  

<span data-ttu-id="dc0ef-170">同样在 EdgeHTML 17 中加新增功能， [使用升级-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) 请求标头请求笔记本请求安全浏览体验。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-170">Also new in EdgeHTML 17, the [Upgrade-Insecure-Requests](https://developer.mozilla.org/docs/Web/HTTP/Headers/Upgrade-Insecure-Requests) request header allows browsers to request a secure browsing experience.</span></span>  <span data-ttu-id="dc0ef-171">此头注重指示浏览器支持升级任何不安全的请求，应将用户重定向到安全版本的网站（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-171">This header tells the server that the browser supports upgrading any insecure requests and the user should be redirected to a secure version of the site if available.</span></span>  

### <span data-ttu-id="dc0ef-172">可变字体</span><span class="sxs-lookup"><span data-stu-id="dc0ef-172">Variable Fonts</span></span>
<span data-ttu-id="dc0ef-173">对可变字体的完整支持 \ (包括 CSS [字体变体设置](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) 和 [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) 在 EdgeHTML 17 中可用。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-173">Full support for Variable Fonts \(including CSS [font-variation-settings](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings) and [font-optical-sizing](https://developer.mozilla.org/docs/Web/CSS/font-variation-settings)\) is available in EdgeHTML 17.</span></span>  <span data-ttu-id="dc0ef-174">可变字体使开发人员能够通过调整各种语言来实现通过单个字体看起来有所不同字样的外观 - 减少了对多个字体文件的需求并更好地实现性能。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-174">Variable fonts enable developers to achieve the look of seemingly different typefaces with a single font by adjusting various axes – reducing the need for multiple font files and bettering performance.</span></span>  

<span data-ttu-id="dc0ef-175">通过将 [可变字体与我们进行合作，了解哪些](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts)字体为 Web 开发人员和设计者提供，以及如何在您的网站上使用这些变量。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-175">Join us on [an expedition to learn about what variable fonts provide web developers and designers](https://developer.microsoft.com/microsoft-edge/testdrive/demos/variable-fonts), and how to use them on your site.</span></span>  <span data-ttu-id="dc0ef-176">阅读有关博客文章中的变量字体的详细信息，将明确 [的版](https://blogs.windows.com/msedgedev/2018/03/13)式呈现给 Microsoft Edge 使用变量字体。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-176">And read more about Variable Fonts in the blog post, [Bringing expressive, performant typography to Microsoft Edge with Variable Fonts](https://blogs.windows.com/msedgedev/2018/03/13).</span></span>  

<iframe height='456' scrolling='no' title='<span data-ttu-id="dc0ef-177">变量 Tides 票面示例</span><span class="sxs-lookup"><span data-stu-id="dc0ef-177">Variable Tides ticket examples</span></span>' src='//codepen.io/MSEdgeDev/embed/dmYvWg/?height=456&theme-id=23761&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="dc0ef-178">请参阅 <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'> MSEdgeDev 在 CodePen 上按 </a> MSEdgeDev 设置 <a href='https://codepen.io/MSEdgeDev'> 的 </a> (@MSEdgeDev) <a href='https://codepen.io'> 笔描述信息 </a> 。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-178">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/dmYvWg/'>Variable Tides ticket examples</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

## <span data-ttu-id="dc0ef-179">EdgeHTML 17 中的新 API</span><span class="sxs-lookup"><span data-stu-id="dc0ef-179">New APIs in EdgeHTML 17</span></span>  

<span data-ttu-id="dc0ef-180">下面是 EdgeHTML 17 中的新 API 的完整列表。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-180">Here's the full list of new APIs in EdgeHTML 17.</span></span>  <span data-ttu-id="dc0ef-181">它们以格式列出 `[interface name].[api name]` 。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-181">They are listed in the format of `[interface name].[api name]`.</span></span>  

> [!NOTE] 
> <span data-ttu-id="dc0ef-182">尽管以下 API 在 DOM 中公开，但某些 API 的端到端行为可能仍在开发中。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-182">Although the following APIs are exposed in the DOM, the end-to-end behavior of some might still be in development.</span></span>  <span data-ttu-id="dc0ef-183">若要了解  [功能支持的正](https://developer.microsoft.com/microsoft-edge/platform/status) 式字词，请参考 Microsoft Edge 平台状态。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-183">Refer to  [Microsoft Edge platform status](https://developer.microsoft.com/microsoft-edge/platform/status) for the official word on feature support.</span></span>  

<iframe height='580' scrolling='no' title='<span data-ttu-id="dc0ef-184">EdgeHTML 17 中的新 API</span><span class="sxs-lookup"><span data-stu-id="dc0ef-184">New APIs in EdgeHTML 17</span></span>' src='//codepen.io/MSEdgeDev/embed/pLxgdj/?height=608&theme-id=23401&default-tab=result&embed-version=2' frameborder='no' allowtransparency='true' allowfullscreen='true' style='width: 100%;'><span data-ttu-id="dc0ef-185">在 <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'> CodePen 上查看 </a> MicrosoftEdgeDev 代码的 MsEdgeDev 函数 <a href='https://codepen.io/MSEdgeDev'> </a> (@MSEdgeDev) <a href='https://codepen.io'> 笔新 </a> API。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-185">See the Pen <a href='https://codepen.io/MSEdgeDev/pen/pLxgdj/'>New APIs in EdgeHTML 17</a> by MSEdgeDev (<a href='https://codepen.io/MSEdgeDev'>@MSEdgeDev</a>) on <a href='https://codepen.io'>CodePen</a>.</span></span></iframe>  

> [!TIP]
> <span data-ttu-id="dc0ef-186">我们已 [与](https://blogs.windows.com/msedgedev/2017/10/18) 其他浏览器和 Web 社区合作，是关于当前和新兴基于 [标准](https://developer.mozilla.org) 的 Web 技术的有用不当安全的、不依自浏览器的常用文档。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-186">We've [partnered](https://blogs.windows.com/msedgedev/2017/10/18) with other browsers and the web community in adopting [MDN Web Docs](https://developer.mozilla.org) as the definitive place for useful, unbiased, browser-agnostic documentation for current and emerging standards-based web technologies.</span></span>  <span data-ttu-id="dc0ef-187">可以在 MDN Web 参考库的每个页面中直接找到有关 [EdgeHTML API 支持的详细信息](https://developer.mozilla.org/docs/Web)。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-187">You can find details about EdgeHTML API support directly in each page of the [MDN web reference library](https://developer.mozilla.org/docs/Web).</span></span>  <span data-ttu-id="dc0ef-188">访问 Microsoft Edge 中支持 [的最新](https://developer.microsoft.com/microsoft-edge/status) 功能的 Microsoft Edge 平台状态。</span><span class="sxs-lookup"><span data-stu-id="dc0ef-188">Visit Microsoft Edge's [Platform status](https://developer.microsoft.com/microsoft-edge/status) for the latest features supported in Microsoft Edge.</span></span>  

## <span data-ttu-id="dc0ef-189">以前的 EdgeHTML 版本</span><span class="sxs-lookup"><span data-stu-id="dc0ef-189">Previous EdgeHTML releases</span></span>  

[<span data-ttu-id="dc0ef-190">EdgeHTML 13 / Windows 版本 10586 (11/2015 版) </span><span class="sxs-lookup"><span data-stu-id="dc0ef-190">EdgeHTML 13 / Windows build 10586 (11/2015)</span></span>](https://aka.ms/devguide_edgehtml_13)  

[<span data-ttu-id="dc0ef-191">EdgeHTML 14/Windows 内部版本 14393 (，8) </span><span class="sxs-lookup"><span data-stu-id="dc0ef-191">EdgeHTML 14 / Windows build 14393 (8/2016)</span></span>](https://aka.ms/devguide_edgehtml_14)  

[<span data-ttu-id="dc0ef-192">EdgeHTML 15 /Windows 内部版本 15063 (4/2017) </span><span class="sxs-lookup"><span data-stu-id="dc0ef-192">EdgeHTML 15 / Windows build 15063 (4/2017)</span></span>](https://aka.ms/devguide_edgehtml_15)  

[<span data-ttu-id="dc0ef-193">EdgeHTML 16 /Windows 版本 16299 (10/2017 年 10 月 10 日) </span><span class="sxs-lookup"><span data-stu-id="dc0ef-193">EdgeHTML 16 / Windows build 16299 (10/2017)</span></span>](https://aka.ms/devguide_edgehtml_16)  
