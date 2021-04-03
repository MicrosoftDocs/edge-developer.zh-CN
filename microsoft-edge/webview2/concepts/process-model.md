---
description: 进程模型
title: 过程模型|WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 149234fe99485460f9d0c677b176a42d3b1e5050
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470849"
---
# <a name="process-model"></a><span data-ttu-id="7b58b-104">进程模型</span><span class="sxs-lookup"><span data-stu-id="7b58b-104">Process model</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="7b58b-105">支持的平台：</span><span class="sxs-lookup"><span data-stu-id="7b58b-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="7b58b-106">Win32、Windows Forms、WinUi、WPF</span><span class="sxs-lookup"><span data-stu-id="7b58b-106">Win32, Windows Forms, WinUi, WPF</span></span>
   :::column-end:::
:::row-end:::  

<span data-ttu-id="7b58b-107">WebView2 使用与 Microsoft Edge 浏览器相同的进程模型。</span><span class="sxs-lookup"><span data-stu-id="7b58b-107">WebView2 uses the same process model as the Microsoft Edge browser.</span></span>  <span data-ttu-id="7b58b-108">有关浏览器进程模型详细信息，请导航到"浏览器体系结构[- 内部查看新式 Web 浏览器"。][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]</span><span class="sxs-lookup"><span data-stu-id="7b58b-108">For more information about the browser process model, navigate to [Browser Architecture - Inside look at modern web browser][GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture].</span></span>  

<span data-ttu-id="7b58b-109">一个浏览器进程与呈现器进程和其他实用程序进程关联，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="7b58b-109">One browser process is associated with the renderer processes and other utility processes as described in that article.</span></span>  <span data-ttu-id="7b58b-110">此外，如果指定了 WebView2，主机应用请求进程将使用 WebView2。</span><span class="sxs-lookup"><span data-stu-id="7b58b-110">Additionally, if WebView2 is specified, the host app requesting processes use WebView2.</span></span>  

:::image type="complex" source="../media/process-model-1.png" alt-text="进程 1" lightbox="../media/process-model-1.png":::
   <span data-ttu-id="7b58b-112">进程 1</span><span class="sxs-lookup"><span data-stu-id="7b58b-112">Process 1</span></span>  
:::image-end:::  

<span data-ttu-id="7b58b-113">浏览器进程仅与一个用户数据文件夹相关联。</span><span class="sxs-lookup"><span data-stu-id="7b58b-113">A browser process is associated with only one user data folder.</span></span>  <span data-ttu-id="7b58b-114">请求进程可以指定多个用户数据文件夹。</span><span class="sxs-lookup"><span data-stu-id="7b58b-114">A request process may specify more than one user data folder.</span></span>  <span data-ttu-id="7b58b-115">指定多个用户数据文件夹的请求进程与相同数量的浏览器进程关联。</span><span class="sxs-lookup"><span data-stu-id="7b58b-115">A request process that specifies more than one user data folder is associated with the same number of browser processes.</span></span>  
<span data-ttu-id="7b58b-116">例如，请求访问两个用户数据文件夹的请求进程使用两个浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="7b58b-116">For example, a request process that requests access to two user data folders uses two browser processes.</span></span>  

:::image type="complex" source="../media/process-model-2.png" alt-text="过程 2" lightbox="../media/process-model-2.png":::
   <span data-ttu-id="7b58b-118">过程 2</span><span class="sxs-lookup"><span data-stu-id="7b58b-118">Process 2</span></span>  
:::image-end:::  

<span data-ttu-id="7b58b-119">浏览器进程与多个呈现器进程关联。</span><span class="sxs-lookup"><span data-stu-id="7b58b-119">A browser process is associated with several renderer processes.</span></span>  <span data-ttu-id="7b58b-120">WebView 2 实例创建一个浏览器进程来为框架提供服务。</span><span class="sxs-lookup"><span data-stu-id="7b58b-120">A WebView 2 instance creates a browser process to service frames.</span></span>  <span data-ttu-id="7b58b-121">浏览器进程可能与多个帧关联。</span><span class="sxs-lookup"><span data-stu-id="7b58b-121">A browser process may be associated with multiple frames.</span></span>  <span data-ttu-id="7b58b-122">浏览器进程可能与 WebView2 的不同实例相关联。</span><span class="sxs-lookup"><span data-stu-id="7b58b-122">A browser process may be associated with different instances of WebView2.</span></span>  <span data-ttu-id="7b58b-123">呈现进程数因以下条件而异。</span><span class="sxs-lookup"><span data-stu-id="7b58b-123">The number of render processes varies based on the following conditions.</span></span>  

*   <span data-ttu-id="7b58b-124">在浏览器中使用网站隔离功能。</span><span class="sxs-lookup"><span data-stu-id="7b58b-124">Use of the website isolation feature in your browser.</span></span>  
*   <span data-ttu-id="7b58b-125">在关联的 WebView2 实例中呈现的已断开连接源的数量。</span><span class="sxs-lookup"><span data-stu-id="7b58b-125">The number of distinct disconnected origins rendered in associated instances of WebView2.</span></span>  

<span data-ttu-id="7b58b-126">网站隔离浏览器功能在上一内容中进行了介绍。</span><span class="sxs-lookup"><span data-stu-id="7b58b-126">The website isolation browser feature is described in the previous content.</span></span> 
<!--todo:  which previous content?  -->  
 

<span data-ttu-id="7b58b-127">`CoreWebView2Environment`表示用户数据文件夹和浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="7b58b-127">The `CoreWebView2Environment` represents a user data folder and browser process.</span></span>  <span data-ttu-id="7b58b-128">不直接对应于任何一组进程，因为 WebView2 使用各种呈现器进程，具体取决于前面所述的 `CoreWebView2` 网站隔离。</span><span class="sxs-lookup"><span data-stu-id="7b58b-128">The `CoreWebView2` does not directly correspond to any one set of processes since various renderer processes are used by a WebView2 depending on website isolation as previously described.</span></span>  

<span data-ttu-id="7b58b-129">若要对浏览器和呈现器进程中的崩溃和挂起做出反应，请使用 `ProcessFailed` 的 事件 `CoreWebView2` 。</span><span class="sxs-lookup"><span data-stu-id="7b58b-129">To react to crashes and hangs in the browser and renderer processes, use the `ProcessFailed` event of `CoreWebView2`.</span></span>  

<span data-ttu-id="7b58b-130">若要安全关闭关联的浏览器和呈现器进程，请使用 的 `Close` `CoreWebView2Controller` 方法。</span><span class="sxs-lookup"><span data-stu-id="7b58b-130">To safely shut down associated browser and renderer processes, use the `Close` method of `CoreWebView2Controller`.</span></span>  

<span data-ttu-id="7b58b-131">若要从 WebView2 实例的 **DevTools** 窗口打开浏览器任务管理器窗口，请完成以下操作。</span><span class="sxs-lookup"><span data-stu-id="7b58b-131">To open the Browser Task Manager window from the **DevTools** window of a WebView2 instance, complete on of the following actions.</span></span>  

*   <span data-ttu-id="7b58b-132">选择 `Shift`+`Escape`。</span><span class="sxs-lookup"><span data-stu-id="7b58b-132">Select `Shift`+`Escape`.</span></span>  
*   <span data-ttu-id="7b58b-133">将鼠标悬停在 DevTools 窗口标题栏上，打开上下文菜单 \ (右键单击\) ，然后选择 `Browser task manager` 。</span><span class="sxs-lookup"><span data-stu-id="7b58b-133">Hover on the DevTools window title bar, open the contextual menu \(right-click\), and choose `Browser task manager`.</span></span>  

<span data-ttu-id="7b58b-134">将显示与 WebView2 的浏览器进程关联的所有进程，包括关联目的。</span><span class="sxs-lookup"><span data-stu-id="7b58b-134">All processes associated with the browser process of your WebView2 are displayed including associated purposes.</span></span>  

## <a name="see-also"></a><span data-ttu-id="7b58b-135">另请参阅</span><span class="sxs-lookup"><span data-stu-id="7b58b-135">See also</span></span>  

*   <span data-ttu-id="7b58b-136">若要开始使用 WebView2，请导航到 ["WebView2 入门指南"][Webview2IndexGettingStarted] 指南。</span><span class="sxs-lookup"><span data-stu-id="7b58b-136">To Get Started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2IndexGettingStarted] guides.</span></span>  
*   <span data-ttu-id="7b58b-137">有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="7b58b-137">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>  
*   <span data-ttu-id="7b58b-138">有关 WebView2 API 的更多详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="7b58b-138">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  
*   <span data-ttu-id="7b58b-139">有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]</span><span class="sxs-lookup"><span data-stu-id="7b58b-139">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="7b58b-140">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="7b58b-140">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGettingStarted]: ../index.md#getting-started "入门 - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  

[GoogleDeveloperWebUpdates201809InsideBrowserPart1BrowserArchitecture]: https://developers.google.com/web/updates/2018/09/inside-browser-part1#browser-architecture "浏览器体系结构 - 内部查看新式 Web 浏览器 (第 1 部分) "  
