---
description: 2018年4月更新 (EdgeHTML 17) 中添加到 Microsoft Edge DevTools 的功能
title: DevTools EdgeHTML 17
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、edgehtml 17
ms.custom: seodec18
ms.openlocfilehash: cc110071422f858acf840c1eaf100696a6e3cf03
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563434"
---
# <span data-ttu-id="98441-104">DevTools 2018 年4月更新 (EdgeHTML 17) </span><span class="sxs-lookup"><span data-stu-id="98441-104">DevTools in the Windows 10 April 2018 update (EdgeHTML 17)</span></span>

<span data-ttu-id="98441-105">DevTools 的 EdgeHTML 17 版以两种方式提供：作为传统的浏览器 (`F12`) Microsoft Edge 的工具，并从 Microsoft Store 中预览为独立的 [Windows 10 应用](#microsoft-edge-devtools-app-preview) ！</span><span class="sxs-lookup"><span data-stu-id="98441-105">The EdgeHTML 17 release of the DevTools ships in two ways: as the traditional in-browser (`F12`) tools for Microsoft Edge, and previewing as a standalone [Windows 10 app](#microsoft-edge-devtools-app-preview) from the Microsoft Store!</span></span>

<span data-ttu-id="98441-106">这些工具已经过大量主要功能的更新，包括对 [远程调试](../../devtools-guide.md#remote-debugging) (的基本支持，通过我们的新的 [DevTools 协议](#devtools-protocol)) 、 [PWA 调试功能](#pwa-debugging)、 [IndexedDB 缓存管理](#indexeddb-inspection)、 [垂直停靠](#docking-to-the-right-in-microsoft-edge) 等！</span><span class="sxs-lookup"><span data-stu-id="98441-106">The tools have been updated with a number of major features, including basic support for [remote debugging](../../devtools-guide.md#remote-debugging) (via our new [DevTools Protocol](#devtools-protocol)), [PWA debugging features](#pwa-debugging), [IndexedDB cache management](#indexeddb-inspection), [vertical docking](#docking-to-the-right-in-microsoft-edge) and more!</span></span> <span data-ttu-id="98441-107">我们还继续在性能和可靠性方面作为日常投资的一部分，开始上次发布的整体 [重构工作](./edgehtml-16.md) 。</span><span class="sxs-lookup"><span data-stu-id="98441-107">We also continued the overall [refactoring effort](./edgehtml-16.md) started last release as part of ongoing investments in performance and reliability.</span></span>

<span data-ttu-id="98441-108">下面是 [Windows 10 2018 年4月更新](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)) 中提供的最新 Microsoft Edge DevTools 功能。</span><span class="sxs-lookup"><span data-stu-id="98441-108">Here are the latest Microsoft Edge DevTools features that shipped in the [Windows 10 April 2018 Update](/windows/uwp/whats-new/windows-10-build-17134) ([EdgeHTML 17](https://aka.ms/devguide_edgehtml_17)).</span></span>

## <span data-ttu-id="98441-109">Microsoft Edge DevTools 应用预览</span><span class="sxs-lookup"><span data-stu-id="98441-109">Microsoft Edge DevTools app preview</span></span>

![Microsoft Edge DevTools 应用](../../devtools-protocol/media/microsoft-edge-devtools.png) 

<span data-ttu-id="98441-111">[**Microsoft Edge DevTools**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab)现在可用作 microsoft Store 中的独立 Windows 10 应用的预览版。</span><span class="sxs-lookup"><span data-stu-id="98441-111">The [**Microsoft Edge DevTools**](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj?activetab=pivot%3aoverviewtab) are now available for preview as a standalone Windows 10 app from the Microsoft Store.</span></span> <span data-ttu-id="98441-112">应用商店版本提供了一个*选择器*面板（用于连接以打开本地和远程页面目标）以及一个选项卡式布局（便于在 DevTools 实例之间进行切换）。</span><span class="sxs-lookup"><span data-stu-id="98441-112">With the store version comes a *chooser* panel for attaching to open local and remote page targets and a tabbed layout for easy switching between DevTools instances.</span></span> <span data-ttu-id="98441-113">此外，DevTools 应用的独占功能是在 (应用中调试 web 内容的功能，例如 Office、Cortana、EdgeHTML [web 视图](../../webview.md)和 [Windows 安装的 PWAs](../../progressive-web-apps-edgehtml/windows-features.md)) 的加载项。</span><span class="sxs-lookup"><span data-stu-id="98441-113">Also exclusive to the DevTools app is the ability to debug web content in apps (such as add-ins for Office, Cortana, EdgeHTML [webview](../../webview.md), and [Windows-installed PWAs](../../progressive-web-apps-edgehtml/windows-features.md)).</span></span>

<span data-ttu-id="98441-114">此外，还可 `F12` 从浏览 (器中 () 边缘 DevTools，但不) 选择器面板。</span><span class="sxs-lookup"><span data-stu-id="98441-114">The Edge DevTools are also still available (`F12`) from within the browser (without the chooser panel).</span></span>

<span data-ttu-id="98441-115">将 DevTools 与浏览器相分离可提供以下 UX 和体系结构优势：</span><span class="sxs-lookup"><span data-stu-id="98441-115">Decoupling the DevTools from the browser provides these UX and architectural advantages:</span></span>

- <span data-ttu-id="98441-116">DevTools 在单独的应用容器沙盒中从 Microsoft Edge 运行，从而提供更高的可靠性。</span><span class="sxs-lookup"><span data-stu-id="98441-116">The DevTools run in a separate app container sandbox from Microsoft Edge, providing better reliability for both.</span></span>
- <span data-ttu-id="98441-117">该应用提供了在活动的 DevTools 实例选项 (卡之间轻松切换的功能，而无需在打开的 Microsoft Edge 选项卡之间切换) </span><span class="sxs-lookup"><span data-stu-id="98441-117">The app provides easy switching between active DevTools instance tabs (rather than having to switch between open Microsoft Edge tabs)</span></span>
- <span data-ttu-id="98441-118">我们能够检测 *EdgeHTML* 浏览器引擎，并通过 [跨浏览器 api](https://github.com/WICG/devtools-protocol/)将其打开到更大的 devtools 生态系统。</span><span class="sxs-lookup"><span data-stu-id="98441-118">We're able to instrument the *EdgeHTML* browser engine and open it to the larger devtools ecosystem with [cross-browser APIs](https://github.com/WICG/devtools-protocol/).</span></span>
- <span data-ttu-id="98441-119">我们可以独立于 Windows (和 EdgeHTML) 发布周期装运 DevTools 更新。</span><span class="sxs-lookup"><span data-stu-id="98441-119">We can ship DevTools updates independently from the Windows (and EdgeHTML) release cycle.</span></span>

<span data-ttu-id="98441-120">有关[使用 DevTools 应用进行本地和远程调试](../../devtools-guide.md)的详细信息，请参阅*DevTools 指南*。</span><span class="sxs-lookup"><span data-stu-id="98441-120">Check out the *DevTools guide* for more on [local and remote debugging using the DevTools app](../../devtools-guide.md).</span></span>

## <span data-ttu-id="98441-121">DevTools 协议</span><span class="sxs-lookup"><span data-stu-id="98441-121">DevTools Protocol</span></span>

<span data-ttu-id="98441-122">开发人员工具可以使用 [**Microsoft Edge DevTools 协议**](../../devtools-protocol/index.md) 来检查和调试 Microsoft edge 浏览器。</span><span class="sxs-lookup"><span data-stu-id="98441-122">Developer tools can use the [**Microsoft Edge DevTools Protocol**](../../devtools-protocol/index.md) to inspect and debug the Microsoft Edge browser.</span></span> <span data-ttu-id="98441-123">它提供了一组方法和事件，这些方法和事件组织到 EdgeHTML 引擎规范的不同 [域](../../devtools-protocol/0.1/domains/index.md) 中。</span><span class="sxs-lookup"><span data-stu-id="98441-123">It provides a set of methods and events that are organized into different [Domains](../../devtools-protocol/0.1/domains/index.md) of EdgeHTML engine instrumentation.</span></span>

 <span data-ttu-id="98441-124">工具客户可以通过与由 Microsoft Edge 或[Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal)托管的*DevTools 服务器*交换的 JSON web 套接字消息来调用这些方法并监视这些事件。</span><span class="sxs-lookup"><span data-stu-id="98441-124">Tooling clients can call these methods and monitor these events through JSON web socket messages exchanged with the *DevTools Server* hosted by Microsoft Edge or the [Windows Device Portal](/windows/mixed-reality/using-the-windows-device-portal).</span></span> 
 
 <span data-ttu-id="98441-125">Microsoft Edge DevTools 使用此协议，从 Microsoft Store 提供的[独立 DevTools 客户端](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj)开始对运行 microsoft Edge 的主机进行[远程调试](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview)。</span><span class="sxs-lookup"><span data-stu-id="98441-125">Microsoft Edge DevTools uses this protocol to enable [remote debugging](../../devtools-protocol/0.1/clients.md#microsoft-edge-devtools-preview) of a host machine running Microsoft Edge from the [standalone DevTools client](https://www.microsoft.com/store/p/microsoft-edge-devtools-preview/9mzbfrmz0mnj) available from the Microsoft Store.</span></span> <span data-ttu-id="98441-126">当前，此预览支持仅限于对另一个桌面设备或 VM 上的另一边缘的 JS 调试。</span><span class="sxs-lookup"><span data-stu-id="98441-126">Currently this preview support is limited to JS debugging of another Edge on another desktop device or VM.</span></span> <span data-ttu-id="98441-127">随着时间的推移，我们将为任何 Windows 10 设备上的任何 EdgeHTML 实例添加对完整 DevTools 集的支持。</span><span class="sxs-lookup"><span data-stu-id="98441-127">Over time, we'll add support for the full set of DevTools against any EdgeHTML instance on any Windows 10 device.</span></span>  
 
 <span data-ttu-id="98441-128"> (Visual Studio 15.7 Preview 1 或更高版本中的最新 [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) 预览版) 使用 DevTools 协议从任何 ASP.NET 或 .net Core 项目的 VISUAL Studio IDE 中启用 Microsoft Edge (JavaScript 代码) 。</span><span class="sxs-lookup"><span data-stu-id="98441-128">The latest [**Visual Studio Preview**](https://www.visualstudio.com/vs/preview/) builds (Visual Studio 15.7 Preview 1 or later) use the DevTools Protocol to enable launching and debugging Microsoft Edge (JavaScript code) from within the Visual Studio IDE of any ASP.NET or .NET Core project.</span></span>

## <span data-ttu-id="98441-129">IndexedDB 检查</span><span class="sxs-lookup"><span data-stu-id="98441-129">IndexedDB inspection</span></span>

<span data-ttu-id="98441-130">[**调试器**](../debugger.md)的新增版本此版本是[IndexedDB 管理器](../storage.md#indexeddb-manager)，支持检查和刷新对象存储和删除单个键值条目。</span><span class="sxs-lookup"><span data-stu-id="98441-130">New to the [**Debugger**](../debugger.md) this release is an [IndexedDB Manager](../storage.md#indexeddb-manager) with support for inspecting and refreshing your object stores and deleting individual key-value entries.</span></span> <span data-ttu-id="98441-131">将来的版本中预计还会有更多的功能。</span><span class="sxs-lookup"><span data-stu-id="98441-131">Expect even more functionality in future releases.</span></span>

## <span data-ttu-id="98441-132">PWA 调试</span><span class="sxs-lookup"><span data-stu-id="98441-132">PWA debugging</span></span>

<span data-ttu-id="98441-133">支持调试渐进式 Web 应用 (PWAs) 现在在默认情况下处于启用状态，为 [**服务工作人员**](../service-workers.md)、 [**缓存 API**](../storage.md#cache-manager)和 [**IndexedDB**](../storage.md#indexeddb-manager) 管理提供工具选项卡。</span><span class="sxs-lookup"><span data-stu-id="98441-133">Support for debugging Progressive Web Apps (PWAs) is now enabled by default, providing tool tabs for [**Service Workers**](../service-workers.md), [**Cache API**](../storage.md#cache-manager), and [**IndexedDB**](../storage.md#indexeddb-manager) management.</span></span>

<span data-ttu-id="98441-134">此外，" [网络" 面板工具栏](../network.md#toolbar) 上有一个 "新建" 按钮， **跳过所有网络请求的服务工作人员**，以将您的注册服务工作人员切换为网络代理：</span><span class="sxs-lookup"><span data-stu-id="98441-134">Additionally, the [Network panel toolbar](../network.md#toolbar) has a new button, **Bypass Service Worker for all network requests**, to toggle on/off your registered service workers as network proxies:</span></span>

!["网络" 工具栏按钮：绕过所有网络请求的服务工作人员](../media/network_toolbar_bypass_sw.png)

<span data-ttu-id="98441-136">你可以将[PWA 调试为已安装的 Windows 10 应用](../../progressive-web-apps-edgehtml/windows-features.md)，方法是从[DevTools 应用](../../devtools-guide.md#microsoft-store-app)的选择器中的浏览器选项卡/PWA/Web 视图) 选择[**本地**](../../progressive-web-apps-edgehtml/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app) (目标列表。</span><span class="sxs-lookup"><span data-stu-id="98441-136">You can debug your [PWA as an installed Windows 10 app](../../progressive-web-apps-edgehtml/windows-features.md) by selecting it from the list of [**Local**](../../progressive-web-apps-edgehtml/windows-features.md#debug-your-pwa-edgehtml-as-a-windows-app) targets (browser tab/PWA/webview) in the chooser of the [standalone DevTools app](../../devtools-guide.md#microsoft-store-app).</span></span>  

## <span data-ttu-id="98441-137">在 Microsoft Edge 中停靠到右侧</span><span class="sxs-lookup"><span data-stu-id="98441-137">Docking to the right in Microsoft Edge</span></span>

<span data-ttu-id="98441-138">现在，除了停靠在浏览器窗口的底部，还可以将 DevTools 停靠在你正在从 Microsoft Edge 中调试的页面右侧。</span><span class="sxs-lookup"><span data-stu-id="98441-138">You can now dock the DevTools to the right of the page you're debugging from within Microsoft Edge, in addition to docking at the bottom and undocking the DevTools from the browser window.</span></span> <span data-ttu-id="98441-139">用于 `Ctrl+Shift+D` 在 **停靠**位置、 **停靠右侧**和取消 **停靠** 位置之间循环，或 DevTools 的右上角中的图标：</span><span class="sxs-lookup"><span data-stu-id="98441-139">Use `Ctrl+Shift+D` to cycle between the **Dock Bottom**, **Dock Right**, and **Undock** positions, or the icons in the top-right corner of the DevTools:</span></span>

![DevTools (处于未插接状态) 停靠选项](../media/docking_buttons.png) 
