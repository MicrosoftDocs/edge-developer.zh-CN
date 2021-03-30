---
description: '在 EdgeHTML 17 中添加到 Windows 10 2018 年 4 月更新 (Microsoft Edge DevTools) '
title: EdgeHTML 17 中的 DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， edgehtml 17
ms.custom: seodec18
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 937525f349a1db650b795db1efb983f1359fcaa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232478"
---
# <span data-ttu-id="e40cb-104">EdgeHTML 17 (Windows 10 2018 年 4 月更新中的 DevTools) </span><span class="sxs-lookup"><span data-stu-id="e40cb-104">DevTools in the Windows 10 April 2018 update (EdgeHTML 17)</span></span>

<span data-ttu-id="e40cb-105">DevTools 的 EdgeHTML 17 版本以两种方式提供：作为 Microsoft Edge 的传统浏览器内 () 工具，以及从 Microsoft Store 预览为独立 `F12` [Windows 10](#microsoft-edge-devtools-app-preview) 应用！</span><span class="sxs-lookup"><span data-stu-id="e40cb-105">The EdgeHTML 17 release of the DevTools ships in two ways: as the traditional in-browser (`F12`) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>

<span data-ttu-id="e40cb-106">这些工具已使用许多主要功能进行了更新，包括[](#docking-to-the-right-in-microsoft-edge)通过我们新的[DevTools](#devtools-protocol)协议 (、PWA 调试功能[](../index.md#remote-debugging)[、IndexedDB](#indexeddb-inspection)缓存管理[](#pwa-debugging)、垂直停靠等对远程调试)  (的基本支持！</span><span class="sxs-lookup"><span data-stu-id="e40cb-106">The tools have been updated with a number of major features, including basic support for [remote debugging](../index.md#remote-debugging) (via our new [DevTools Protocol](#devtools-protocol)), [PWA debugging features](#pwa-debugging), [IndexedDB cache management](#indexeddb-inspection), [vertical docking](#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="e40cb-107">作为对性能和可靠性的持续[](./edgehtml-16.md)投资一部分，我们还继续进行上一版本开始的整体重构工作。</span><span class="sxs-lookup"><span data-stu-id="e40cb-107">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>

<span data-ttu-id="e40cb-108">以下是[EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)更新版中的 Windows [10 2018](/windows/uwp/whats-new/windows-10-build-17134)年 4 月更新中 (Microsoft Edge DevTools) 。</span><span class="sxs-lookup"><span data-stu-id="e40cb-108">Here are the latest Microsoft Edge DevTools features that shipped in the [Windows 10 April 2018 Update](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)).</span></span>

## <span data-ttu-id="e40cb-109">Microsoft Edge DevTools 应用预览</span><span class="sxs-lookup"><span data-stu-id="e40cb-109">Microsoft Edge DevTools app preview</span></span>

![Microsoft Edge DevTools 应用](../../devtools-protocol/media/microsoft-edge-devtools.png) 

<span data-ttu-id="e40cb-111">Microsoft [Edge DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) 现在可从 Microsoft Store 作为独立 Windows 10 应用进行预览。</span><span class="sxs-lookup"><span data-stu-id="e40cb-111">The [Microsoft Edge DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) are now available for preview as a standalone Windows 10 app from the Microsoft Store.</span></span> <span data-ttu-id="e40cb-112">应用商店版本提供了一个*选择器*面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。</span><span class="sxs-lookup"><span data-stu-id="e40cb-112">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span> <span data-ttu-id="e40cb-113">此外，DevTools 应用还能够调试应用 \(中的 Web 内容，如 Office、Cortana、EdgeHTML [Webview](../../hosting/webview/index.md)和 Windows 安装的 [PWA](../../progressive-web-apps/windows-features.md)\) 。</span><span class="sxs-lookup"><span data-stu-id="e40cb-113">Also exclusive to the DevTools app is the ability to debug web content in apps \(such as add-ins for Office, Cortana, EdgeHTML [webview](../../hosting/webview/index.md), and [Windows-installed PWAs](../../progressive-web-apps/windows-features.md)\).</span></span>

<span data-ttu-id="e40cb-114">Edge DevTools 在 () 选择器面板 (中仍 `F12`) 。</span><span class="sxs-lookup"><span data-stu-id="e40cb-114">The Edge DevTools are also still available (`F12`) from within the browser (without the chooser panel).</span></span>

<span data-ttu-id="e40cb-115">将 DevTools 与浏览器分离可提供以下 UX 和体系结构优势：</span><span class="sxs-lookup"><span data-stu-id="e40cb-115">Decoupling the DevTools from the browser provides these UX and architectural advantages:</span></span>

- <span data-ttu-id="e40cb-116">DevTools 从 Microsoft Edge 在单独的应用容器沙盒中运行，为两者提供更好的可靠性。</span><span class="sxs-lookup"><span data-stu-id="e40cb-116">The DevTools run in a separate app container sandbox from Microsoft Edge, providing better reliability for both.</span></span>
- <span data-ttu-id="e40cb-117">该应用提供在活动 DevTools 实例选项卡 (轻松切换，而无需在打开的 Microsoft Edge 选项卡) </span><span class="sxs-lookup"><span data-stu-id="e40cb-117">The app provides easy switching between active DevTools instance tabs (rather than having to switch between open Microsoft Edge tabs)</span></span>
- <span data-ttu-id="e40cb-118">我们能够通过跨浏览器 API 检测 *EdgeHTML* 浏览器引擎，并打开它到更大的开发工具 [生态系统](https://github.com/WICG/devtools-protocol/)。</span><span class="sxs-lookup"><span data-stu-id="e40cb-118">We're able to instrument the *EdgeHTML* browser engine and open it to the larger devtools ecosystem with [cross-browser APIs](https://github.com/WICG/devtools-protocol/).</span></span>
- <span data-ttu-id="e40cb-119">我们可以独立于 Windows 应用版和 EdgeHTML (发布周期) DevTools 更新。</span><span class="sxs-lookup"><span data-stu-id="e40cb-119">We can ship DevTools updates independently from the Windows (and EdgeHTML) release cycle.</span></span>

<span data-ttu-id="e40cb-120">查看 *DevTools 指南，* 详细了解使用 [DevTools](../index.md)应用进行本地和远程调试。</span><span class="sxs-lookup"><span data-stu-id="e40cb-120">Check out the *DevTools guide* for more on [local and remote debugging using the DevTools app](../index.md).</span></span>

## <span data-ttu-id="e40cb-121">DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="e40cb-121">DevTools Protocol</span></span>

<span data-ttu-id="e40cb-122">开发人员工具可以使用 [**Microsoft Edge DevTools 协议**](../../devtools-protocol/index.md) 来检查和调试 Microsoft Edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="e40cb-122">Developer tools can use the [**Microsoft Edge DevTools Protocol**](../../devtools-protocol/index.md) to inspect and debug the Microsoft Edge browser.</span></span> <span data-ttu-id="e40cb-123">它提供了一组组织到 EdgeHTML 引擎检测的不同 [域中](../../devtools-protocol/0.1/domains/index.md) 的方法和事件。</span><span class="sxs-lookup"><span data-stu-id="e40cb-123">It provides a set of methods and events that are organized into different [Domains](../../devtools-protocol/0.1/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="e40cb-124">工具客户端可以调用这些方法，并通过与 Microsoft Edge 或 Windows Device Portal 托管的 *DevTools 服务器* 交换的 JSON Web 套接字消息来 [监视这些事件](/windows/mixed-reality/using-the-windows-device-portal)。</span><span class="sxs-lookup"><span data-stu-id="e40cb-124">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge or the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> 
 
 <span data-ttu-id="e40cb-125">Microsoft Edge DevTools 使用此协议[](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)启用从 Microsoft Store 提供的独立[DevTools](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)客户端远程调试运行 Microsoft Edge 的主机。</span><span class="sxs-lookup"><span data-stu-id="e40cb-125">Microsoft Edge DevTools uses this protocol to enable [remote debugging](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge from the [standalone DevTools client](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) available from the Microsoft Store.</span></span> <span data-ttu-id="e40cb-126">目前，此预览支持仅限于在另一台桌面设备或 VM 上对另一个边缘进行 JS 调试。</span><span class="sxs-lookup"><span data-stu-id="e40cb-126">Currently this preview support is limited to JS debugging of another Edge on another desktop device or VM.</span></span> <span data-ttu-id="e40cb-127">随着时间的推移，我们将针对任何 Windows 10 设备上的任何 EdgeHTML 实例添加对整套 DevTools 的支持。</span><span class="sxs-lookup"><span data-stu-id="e40cb-127">Over time, we'll add support for the full set of DevTools against any EdgeHTML instance on any Windows 10 device.</span></span>  
 
 <span data-ttu-id="e40cb-128">最新的 [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) 版本 (Visual Studio 15.7 Preview 1 或更高版本) 使用 DevTools 协议启用从任何 ASP.NET 或 .NET Core 项目的 Visual Studio IDE 中启动和调试 Microsoft Edge (JavaScript 代码) 。</span><span class="sxs-lookup"><span data-stu-id="e40cb-128">The latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) builds (Visual Studio 15.7 Preview 1 or later) use the DevTools Protocol to enable launching and debugging Microsoft Edge (JavaScript code) from within the Visual Studio IDE of any ASP.NET or .NET Core project.</span></span>

## <span data-ttu-id="e40cb-129">IndexedDB 检查</span><span class="sxs-lookup"><span data-stu-id="e40cb-129">IndexedDB inspection</span></span>

<span data-ttu-id="e40cb-130">此版本的 [**调试**](../debugger.md) 器新增了 [IndexedDB 管理器](../storage.md#indexeddb-manager) ，支持检查和刷新对象存储和删除单个键值条目。</span><span class="sxs-lookup"><span data-stu-id="e40cb-130">New to the [**Debugger**](../debugger.md) this release is an [IndexedDB Manager](../storage.md#indexeddb-manager) with support for inspecting and refreshing your object stores and deleting individual key-value entries.</span></span> <span data-ttu-id="e40cb-131">预计未来版本中会有更多的功能。</span><span class="sxs-lookup"><span data-stu-id="e40cb-131">Expect even more functionality in future releases.</span></span>

## <span data-ttu-id="e40cb-132">PWA 调试</span><span class="sxs-lookup"><span data-stu-id="e40cb-132">PWA debugging</span></span>

<span data-ttu-id="e40cb-133">现在默认启用对调试渐进 Web 应用 (PWA) ，为服务工作者、缓存[**API**](../storage.md#cache-manager)和[](../service-workers.md)[**IndexedDB**](../storage.md#indexeddb-manager)管理提供工具选项卡。</span><span class="sxs-lookup"><span data-stu-id="e40cb-133">Support for debugging Progressive Web Apps (PWAs) is now enabled by default, providing tool tabs for [**Service Workers**](../service-workers.md), [**Cache API**](../storage.md#cache-manager), and [**IndexedDB**](../storage.md#indexeddb-manager) management.</span></span>

<span data-ttu-id="e40cb-134">此外，[网络](../network.md#toolbar)面板工具栏有一个新按钮"绕过 所有网络请求的服务工作线程"，以作为网络代理打开/关闭注册的服务工作者：</span><span class="sxs-lookup"><span data-stu-id="e40cb-134">Additionally, the [Network panel toolbar](../network.md#toolbar) has a new button, **Bypass Service Worker for all network requests**, to toggle on/off your registered service workers as network proxies:</span></span>

![网络工具栏按钮：绕过所有网络请求的服务工作线程](../media/network_toolbar_bypass_sw.png)

<span data-ttu-id="e40cb-136">可以通过从独立[DevTools](../index.md#microsoft-store-app)应用选择器中的本地目标 (浏览器选项卡/PWA/webview) 列表中选择[PWA，将 PWA](../../progressive-web-apps/windows-features.md)调试为已安装的 Windows 10 应用。 [](../../progressive-web-apps/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app)</span><span class="sxs-lookup"><span data-stu-id="e40cb-136">You can debug your [PWA as an installed Windows 10 app](../../progressive-web-apps/windows-features.md) by selecting it from the list of [**Local**](../../progressive-web-apps/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app) targets (browser tab/PWA/webview) in the chooser of the [standalone DevTools app](../index.md#microsoft-store-app).</span></span>  

## <span data-ttu-id="e40cb-137">固定到 Microsoft Edge 中的右侧</span><span class="sxs-lookup"><span data-stu-id="e40cb-137">Docking to the right in Microsoft Edge</span></span>

<span data-ttu-id="e40cb-138">除了停靠在底部和从浏览器窗口取消停靠 DevTools 之外，你现在还可以将 DevTools 停靠在从 Microsoft Edge 中调试的页面的右侧。</span><span class="sxs-lookup"><span data-stu-id="e40cb-138">You can now dock the DevTools to the right of the page you're debugging from within Microsoft Edge, in addition to docking at the bottom and undocking the DevTools from the browser window.</span></span> <span data-ttu-id="e40cb-139">用于 `Ctrl+Shift+D` 在扩展坞 **底部**、 **扩展坞右侧**和 **Undock** 位置之间循环，或在 DevTools 右上角的图标之间循环：</span><span class="sxs-lookup"><span data-stu-id="e40cb-139">Use `Ctrl+Shift+D` to cycle between the **Dock Bottom**, **Dock Right**, and **Undock** positions, or the icons in the top-right corner of the DevTools:</span></span>

![DevTools (未停靠状态) 扩展选项](../media/docking_buttons.png) 
