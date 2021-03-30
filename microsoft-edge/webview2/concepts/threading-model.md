---
description: 线程模型
title: 线程模型|WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/29/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 7b447f5cc5fcce3439166638d47a0b87e5536c0a
ms.sourcegitcommit: 5e218b24fb21fcfa9c82b99f17373fed1ba5a21c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/29/2021
ms.locfileid: "11462041"
---
# <a name="threading-model"></a><span data-ttu-id="8cdd0-104">线程模型</span><span class="sxs-lookup"><span data-stu-id="8cdd0-104">Threading model</span></span> 

:::row:::
   :::column span="1":::
      <span data-ttu-id="8cdd0-105">支持的平台：</span><span class="sxs-lookup"><span data-stu-id="8cdd0-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="8cdd0-106">Win32、Windows Forms、WinUi、WPF</span><span class="sxs-lookup"><span data-stu-id="8cdd0-106">Win32, Windows Forms, WinUi, WPF</span></span>
   :::column-end:::
:::row-end:::  

<span data-ttu-id="8cdd0-107">WebView2 控件基于组件对象模型 [ (COM) ][WindowsWin32ComTheComponentObjectModel] 并且必须在单个线程的 Sta (STA [) ][WindowsWin32ComSingleThreadedApartments] 上运行。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-107">The WebView2 control is based on the [Component Object Model (COM)][WindowsWin32ComTheComponentObjectModel] and must run on a [Single Threaded Apartments (STA)][WindowsWin32ComSingleThreadedApartments] thread.</span></span>  

## <a name="thread-safety"></a><span data-ttu-id="8cdd0-108">线程安全</span><span class="sxs-lookup"><span data-stu-id="8cdd0-108">Thread safety</span></span>  

<span data-ttu-id="8cdd0-109">必须在 UI 线程上创建 WebView2。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-109">The WebView2 must be created on a UI thread.</span></span>  <span data-ttu-id="8cdd0-110">具体来说，是具有消息等待的线程。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-110">Specifically, a thread with a message pump.</span></span>  <span data-ttu-id="8cdd0-111">所有回调都发生在该线程上，并且必须在该线程上完成对 WebView2 的请求。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-111">All callbacks occur on that thread and requests into the WebView2 must be done on that thread.</span></span>  <span data-ttu-id="8cdd0-112">从另一个线程使用 WebView2 不安全。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-112">It isn't safe to use the WebView2 from another thread.</span></span>  

<span data-ttu-id="8cdd0-113">唯一的例外是 `Content` 属性 `CoreWebView2WebResourceRequest` 。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-113">The only exception is for the `Content` property of `CoreWebView2WebResourceRequest`.</span></span>  <span data-ttu-id="8cdd0-114">从 `Content` 后台线程读取属性流。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-114">The `Content` property stream is read from a background thread.</span></span>  <span data-ttu-id="8cdd0-115">该流应为敏捷流，或从后台 STA 创建，以防止性能下降至 UI 线程。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-115">The stream should be agile or be created from a background STA to prevent performance degradation to the UI thread.</span></span>  

## <a name="re-entrancy"></a><span data-ttu-id="8cdd0-116">重新entrancy</span><span class="sxs-lookup"><span data-stu-id="8cdd0-116">Re-entrancy</span></span>  

<span data-ttu-id="8cdd0-117">包括事件处理程序和完成处理程序的回调将串行运行。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-117">Callbacks including event handlers and completion handlers run serially.</span></span>  
<span data-ttu-id="8cdd0-118">运行事件处理程序并开始消息循环后，将无法以重新进入的方式运行任何事件处理程序或完成回调。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-118">After you run an event handler and begin a message loop, you're unable to run any event handler or completion callback in a re-entrant manner.</span></span>  

## <a name="deferrals"></a><span data-ttu-id="8cdd0-119">Deferrals</span><span class="sxs-lookup"><span data-stu-id="8cdd0-119">Deferrals</span></span>  

<span data-ttu-id="8cdd0-120">某些 WebView2 事件读取相关事件参数上设置的值，或在事件处理程序完成后启动一些操作。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-120">Some WebView2 events read values set on the related event arguments or start some action after the event handler completes.</span></span>  <span data-ttu-id="8cdd0-121">如果还需要运行异步操作（如事件处理程序），请对关联事件的事件参数 `GetDeferral` 使用 方法。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-121">If you also need to run an asynchronous operation such an event handler, use the `GetDeferral` method on the event arguments of the associated events.</span></span>  <span data-ttu-id="8cdd0-122">返回的对象可确保在请求 的 方法之前不会认为事件 `Deferral` `Complete` `Deferral` 处理程序已完成。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-122">The returned `Deferral` object ensures the event handler isn't considered complete until the `Complete` method of the `Deferral` is requested.</span></span>  

<span data-ttu-id="8cdd0-123">例如，可以使用 事件在事件处理程序完成时提供 作为子 `NewWindowRequested` `CoreWebView2` 窗口进行连接的 。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-123">For instance, you may use the `NewWindowRequested` event to provide a `CoreWebView2` to connect as a child window when the event handler completes.</span></span>  <span data-ttu-id="8cdd0-124">但是，如果你需要异步创建 ，请对 请求 `CoreWebView2` `GetDeferral` 方法 `NewWindowRequestedEventArgs` 。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-124">But if you need to asynchronously create the `CoreWebView2`, request the `GetDeferral` method on the `NewWindowRequestedEventArgs`.</span></span>  <span data-ttu-id="8cdd0-125">在 上异步创建 和 设置 属性后，使用 方法返回 对象 `CoreWebView2` `NewWindow` 上的 `NewWindowRequestedEventArgs` `Complete` `Deferral` `GetDeferral` 请求。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-125">After you've asynchronously created the `CoreWebView2` and set the `NewWindow` property on the `NewWindowRequestedEventArgs`, request `Complete` on the `Deferral` object be returned using the `GetDeferral` method.</span></span>  

## <a name="block-the-ui-thread"></a><span data-ttu-id="8cdd0-126">阻止 UI 线程</span><span class="sxs-lookup"><span data-stu-id="8cdd0-126">Block the UI thread</span></span>  

<span data-ttu-id="8cdd0-127">WebView2 依赖 UI 线程的消息线索来运行事件处理程序回调和异步方法完成回调。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-127">The WebView2 relies on the message pump of the UI thread to run event handler callbacks and async method completion callbacks.</span></span>  <span data-ttu-id="8cdd0-128">如果使用阻止消息接收的方法（如 或 ），则 WebView2 事件处理程序和异步方法完成处理程序 `Task.Result` `WaitForSingleObject` 不会运行。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-128">If you use methods that block the message pump such as `Task.Result` or `WaitForSingleObject`, then your WebView2 event handlers and async method completion handlers don't run.</span></span>  <span data-ttu-id="8cdd0-129">例如，以下代码无法完成，因为邮件在等待完成时 `Task.Result` 停止消息 `ExecuteScriptAsync` 等待。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-129">For example, the following code doesn't complete, because `Task.Result` stops the message pump while it waits for `ExecuteScriptAsync` to complete.</span></span>  <span data-ttu-id="8cdd0-130">由于邮件的发送被阻止， `ExecuteScriptAsync` 无法完成。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-130">Since the message pump is blocked, the `ExecuteScriptAsync` isn't able to complete.</span></span>   

```csharp
private void Button_Click(object sender, EventArgs e)
{
    string result = webView2Control.CoreWebView2.ExecuteScriptAsync("'test'").Result;
    MessageBox.Show(this, result, "Script Result");
}
```  

<span data-ttu-id="8cdd0-131">使用和 `await` 等异步 `async` `await` 机制，该机制不会阻止消息的显示或 UI 线程。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-131">Use an asynchronous `await` mechanism such as `async` and `await`, which doesn't block the message pump or the UI thread.</span></span>  

```csharp
private async void Button_Click(object sender, EventArgs e)
{
    string result = await webView2Control.CoreWebView2.ExecuteScriptAsync("'test'");
    MessageBox.Show(this, result, "Script Result");
}
```  

## <a name="see-also"></a><span data-ttu-id="8cdd0-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8cdd0-132">See also</span></span>  

*   <span data-ttu-id="8cdd0-133">若要开始使用 WebView2，请导航到 ["WebView2 入门指南"][Webview2IndexGettingStarted] 指南。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-133">To get started using WebView2, navigate to [WebView2 Getting Started Guides][Webview2IndexGettingStarted] guides.</span></span>  
*   <span data-ttu-id="8cdd0-134">有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-134">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>  
*   <span data-ttu-id="8cdd0-135">有关 WebView2 API 的更多详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="8cdd0-135">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  
*   <span data-ttu-id="8cdd0-136">有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]</span><span class="sxs-lookup"><span data-stu-id="8cdd0-136">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="8cdd0-137">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="8cdd0-137">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGettingStarted]: ../index.md#getting-started "入门 - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  

[WindowsWin32ComSingleThreadedApartments]: /windows/win32/com/single-threaded-apartments "单线程处理|Microsoft Docs"  
[WindowsWin32ComTheComponentObjectModel]: /windows/win32/com/the-component-object-model "组件对象模型|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
