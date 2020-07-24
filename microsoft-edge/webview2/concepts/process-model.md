---
description: 流程模型
title: 流程模型
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8548308896815266fbd1e150da979b56cfb268e2
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895537"
---
# <span data-ttu-id="d5df8-104">流程模型</span><span class="sxs-lookup"><span data-stu-id="d5df8-104">Process model</span></span>  

<span data-ttu-id="d5df8-105">WebView2 使用与 Microsoft Edge 浏览器相同的进程模型。</span><span class="sxs-lookup"><span data-stu-id="d5df8-105">WebView2 uses the same process model as the Microsoft Edge browser.</span></span>  <span data-ttu-id="d5df8-106">有关浏览器进程模型的详细信息，请参阅[浏览器体系结构-内部查看新式 web 浏览器][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]。</span><span class="sxs-lookup"><span data-stu-id="d5df8-106">For more information about the browser process model, see [Browser Architecture - Inside look at modern web browser][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture].</span></span> 

<span data-ttu-id="d5df8-107">一个浏览器进程与该文章中所述的呈现程序进程和其他实用工具进程相关联。</span><span class="sxs-lookup"><span data-stu-id="d5df8-107">One browser process is associated with the renderer processes and other utility processes as described in that article.</span></span>  <span data-ttu-id="d5df8-108">此外，在 WebView2 的情况下，存在使用 WebView2 请求进程的主机应用。</span><span class="sxs-lookup"><span data-stu-id="d5df8-108">Additionally, in the case of WebView2, there are host app requesting processes using WebView2.</span></span>  

:::image type="complex" source="../media/process-model-1.png" alt-text="Process 1" lightbox="../media/process-model-1.png":::
   <span data-ttu-id="d5df8-110">Process 1</span><span class="sxs-lookup"><span data-stu-id="d5df8-110">Process 1</span></span>  
:::image-end:::  

<span data-ttu-id="d5df8-111">在为任何 WebView2 请求进程的用户会话中为每个用户的数据文件夹指定一个浏览器进程，指定该用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="d5df8-111">One browser process is specified per user data folder in a user session that serve any WebView2 requesting process that specifies that user data folder.</span></span>  <span data-ttu-id="d5df8-112">这意味着一个浏览器进程可能正在为多个请求进程提供服务，而一个请求进程可能正在使用多个浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="d5df8-112">This means one browser process may be serving multiple requesting processes and one requesting process may be using multiple browser processes.</span></span>  

:::image type="complex" source="../media/process-model-2.png" alt-text="过程2" lightbox="../media/process-model-2.png":::
   <span data-ttu-id="d5df8-114">过程2</span><span class="sxs-lookup"><span data-stu-id="d5df8-114">Process 2</span></span>  
:::image-end:::  

<span data-ttu-id="d5df8-115">浏览器进程具有一些关联的呈现器进程。</span><span class="sxs-lookup"><span data-stu-id="d5df8-115">A browser process has some number of associated renderer processes.</span></span>  <span data-ttu-id="d5df8-116">根据需要创建浏览器进程，以便在 WebView2 的不同实例中服务潜在的多个帧。</span><span class="sxs-lookup"><span data-stu-id="d5df8-116">The browser processes are created as required to service potentially multiple frames in different instances of WebView2.</span></span>  <span data-ttu-id="d5df8-117">呈现器进程的数量因网站隔离浏览器功能和在 WebView2 相关联的实例中呈现的唯一断开的来源的数量而异。</span><span class="sxs-lookup"><span data-stu-id="d5df8-117">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated instances of WebView2.</span></span>  <span data-ttu-id="d5df8-118">以前的内容中介绍了网站隔离浏览器功能。</span><span class="sxs-lookup"><span data-stu-id="d5df8-118">The site isolation browser feature is described in the previous content.</span></span>  

<span data-ttu-id="d5df8-119">`CoreWebView2Environment`表示用户数据文件夹和浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="d5df8-119">The `CoreWebView2Environment` represents a user data folder and browser process.</span></span>  <span data-ttu-id="d5df8-120">不 `CoreWebView2` 会直接对应于任何一组进程，因为各种呈现程序进程由 WebView2 使用，具体取决于前面所述的网站隔离。</span><span class="sxs-lookup"><span data-stu-id="d5df8-120">The `CoreWebView2` does not directly correspond to any one set of processes since various renderer processes are used by a WebView2 depending on site isolation as previously described.</span></span>  

<span data-ttu-id="d5df8-121">你可以使用的事件来响应在这些浏览器和呈现器进程中崩溃和挂起 `ProcessFailed` `CoreWebView2` 。</span><span class="sxs-lookup"><span data-stu-id="d5df8-121">You are able to react to crashes and hangs in these browser and renderer processes using the `ProcessFailed` event of `CoreWebView2`.</span></span>  

<span data-ttu-id="d5df8-122">你可以使用的方法安全地关闭关联浏览器和呈现器进程 `Close` `CoreWebView2Controller` 。</span><span class="sxs-lookup"><span data-stu-id="d5df8-122">You are able to safely shutdown associated browser and renderer processes using the `Close` method of `CoreWebView2Controller`.</span></span>  

<span data-ttu-id="d5df8-123">若要从 WebView2 实例的**DevTools**窗口中打开浏览器任务管理器窗口，您可以选择 `Shift` + `Escape` 或悬停在 DevTools 窗口标题栏上，打开上下文菜单 \ （右键单击 \），然后选择 `Browser task manager` 。</span><span class="sxs-lookup"><span data-stu-id="d5df8-123">To open the Browser Task Manager window from the **DevTools** window of a WebView2 instance, you are able to select `Shift`+`Escape` or hover on the DevTools window title bar, open the contextual menu \(right-click\), and choose `Browser task manager`.</span></span>  <span data-ttu-id="d5df8-124">将显示与你的 WebView2 的浏览器进程关联的所有进程，包括相关用途。</span><span class="sxs-lookup"><span data-stu-id="d5df8-124">All processes associated with the browser process of your WebView2 are displayed including associated purposes.</span></span>  

<!-- links -->  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "浏览器体系结构-在新式 web 浏览器中查看（第1部分）"  
