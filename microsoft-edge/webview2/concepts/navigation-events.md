---
description: 导航
title: 导航|WebView 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/06/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: d133bfb99808d0e036c4b46be9ef82039aee49eb
ms.sourcegitcommit: 777b16ef10363f2dfd755f115ee2d4c81a8de46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "11535704"
---
# <a name="navigation-events"></a><span data-ttu-id="89f22-104">导航事件</span><span class="sxs-lookup"><span data-stu-id="89f22-104">Navigation events</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="89f22-105">支持的平台：</span><span class="sxs-lookup"><span data-stu-id="89f22-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="89f22-106">Win32、Windows Forms、WinUi、WPF</span><span class="sxs-lookup"><span data-stu-id="89f22-106">Win32, Windows Forms, WinUi, WPF</span></span>
   :::column-end:::
:::row-end:::  

<span data-ttu-id="89f22-107">导航事件在 WebView2 实例中显示的内容发生特定异步操作时运行。</span><span class="sxs-lookup"><span data-stu-id="89f22-107">Navigation events run when specific asynchronous actions occur to the content displayed in a WebView2 instance.</span></span>  <span data-ttu-id="89f22-108">例如，当 WebView2 用户导航到新网站时，本机内容会使用 事件侦听 `NavigationStarting` 更改。</span><span class="sxs-lookup"><span data-stu-id="89f22-108">For example, when a WebView2 user navigates to a new website, the native content listens for the change using `NavigationStarting` event.</span></span>  <span data-ttu-id="89f22-109">导航操作完成后，运行 `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="89f22-109">When the navigation action completes, `NavigationCompleted` runs.</span></span>  <span data-ttu-id="89f22-110">有关导航事件的良好示例，请导航到 [WebView2 入门指南][Webview2IndexGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="89f22-110">For a good example of navigation events, navigate to [WebView2 Get Started guide][Webview2IndexGetStarted].</span></span>  

<!--todo:  Move the relevant information out of the get started guide to better focus the content and leave the most concise elements in the get started guide.  -->   

<span data-ttu-id="89f22-111">导航事件的正常顺序为 `NavigationStarting` `SourceChanged` 、、、 `ContentLoading` `HistoryChanged` 和 `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="89f22-111">The normal sequence of navigation events is `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span>  <span data-ttu-id="89f22-112">以下事件描述每次导航期间 WebView2 的状态。</span><span class="sxs-lookup"><span data-stu-id="89f22-112">The following events describe the state of WebView2 during each navigation.</span></span>  

:::row:::
   :::column span="1":::
      :::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 导航事件" lightbox="../media/navigation-graph.png":::
         <span data-ttu-id="89f22-114">Microsoft Edge WebView2 导航事件</span><span class="sxs-lookup"><span data-stu-id="89f22-114">The Microsoft Edge WebView2 Navigation Events</span></span>  
      :::image-end:::  
      
      > [!NOTE]
      > <span data-ttu-id="89f22-115">该图表示导航事件，这些事件 `NavigationId` 在各自的 event 参数上具有相同的属性。</span><span class="sxs-lookup"><span data-stu-id="89f22-115">The figure represents navigation events with the same `NavigationId` property on the respective event argument.</span></span>  
   :::column-end:::
   :::column span="2":::
      | <span data-ttu-id="89f22-116">Sequence</span><span class="sxs-lookup"><span data-stu-id="89f22-116">Sequence</span></span> | <span data-ttu-id="89f22-117">事件名称</span><span class="sxs-lookup"><span data-stu-id="89f22-117">Event name</span></span> | <span data-ttu-id="89f22-118">详细信息</span><span class="sxs-lookup"><span data-stu-id="89f22-118">Details</span></span> |  
      |:--- |:--- |:--- |  
      | <span data-ttu-id="89f22-119">1</span><span class="sxs-lookup"><span data-stu-id="89f22-119">1</span></span> | `NavigationStarting`  |  <span data-ttu-id="89f22-120">WebView2 开始导航，导航结果为网络请求。</span><span class="sxs-lookup"><span data-stu-id="89f22-120">WebView2 starts to navigate and the navigation results in a network request.</span></span>  <span data-ttu-id="89f22-121">在事件期间，主机可能会禁止该请求。</span><span class="sxs-lookup"><span data-stu-id="89f22-121">The host may disallow the request during the event.</span></span>  |  
      | <span data-ttu-id="89f22-122">2</span><span class="sxs-lookup"><span data-stu-id="89f22-122">2</span></span> | `SourceChanged`  |  <span data-ttu-id="89f22-123">WebView2 的源将更改到新的 URL。</span><span class="sxs-lookup"><span data-stu-id="89f22-123">The source of WebView2 changes to a new URL.</span></span>  <span data-ttu-id="89f22-124">该事件可能由不会导致网络请求（如片段导航）的导航操作导致。</span><span class="sxs-lookup"><span data-stu-id="89f22-124">The event may result from a navigation action that does not cause a network request such as a fragment navigation.</span></span>  |  
      | <span data-ttu-id="89f22-125">3</span><span class="sxs-lookup"><span data-stu-id="89f22-125">3</span></span> | `ContentLoading`  |  <span data-ttu-id="89f22-126">WebView 开始加载新页面的内容。</span><span class="sxs-lookup"><span data-stu-id="89f22-126">WebView starts loading content for the new page.</span></span>  |  
      | <span data-ttu-id="89f22-127">4</span><span class="sxs-lookup"><span data-stu-id="89f22-127">4</span></span> | `HistoryChanged`  |  <span data-ttu-id="89f22-128">导航导致 WebView2 的历史记录更新。</span><span class="sxs-lookup"><span data-stu-id="89f22-128">The navigation causes the history of WebView2 to update.</span></span>  |  
      | <span data-ttu-id="89f22-129">5</span><span class="sxs-lookup"><span data-stu-id="89f22-129">5</span></span> | `NavigationCompleted`  |  <span data-ttu-id="89f22-130">WebView2 完成新页面上的内容加载。</span><span class="sxs-lookup"><span data-stu-id="89f22-130">WebView2 completes loading content on the new page.</span></span>  |  
   :::column-end:::
:::row-end:::

<span data-ttu-id="89f22-131">使用导航 ID \ (`NavigationId` event\) 跟踪每个新文档的导航事件。</span><span class="sxs-lookup"><span data-stu-id="89f22-131">Track navigation events to each new document using the navigation ID \(`NavigationId` event\).</span></span>  <span data-ttu-id="89f22-132">每次 `NavigationId` 成功导航到新文档时，WebView 事件都会更改。</span><span class="sxs-lookup"><span data-stu-id="89f22-132">The `NavigationId` event of WebView changes every time a successful navigation to a new document completes.</span></span>  

 <span data-ttu-id="89f22-133">具有不同事件实例的 `NavigationId` 导航事件可能会重叠。</span><span class="sxs-lookup"><span data-stu-id="89f22-133">Navigation events with different instances of `NavigationId` event may overlap.</span></span>  <span data-ttu-id="89f22-134">例如，启动导航事件时，必须等待相关 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="89f22-134">For instance, when you start a navigation event, you must wait for the related `NavigationStarting` event.</span></span>  <span data-ttu-id="89f22-135">如果随后启动另一个导航，则应该会看到第一个导航的事件，后跟第二个导航的事件，然后是第一个导航的事件，然后是第二个导航的所有其他相应导航事件。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`</span><span class="sxs-lookup"><span data-stu-id="89f22-135">If you then start another navigation, you should see the `NavigationStarting` event for the first navigate followed by the `NavigationStarting` event for the second navigate, followed by the `NavigationCompleted` event for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span>  
 
 <span data-ttu-id="89f22-136">在错误情况下，根据导航是否继续导航到错误页面，可能（也可能没有 `ContentLoading` ）事件。</span><span class="sxs-lookup"><span data-stu-id="89f22-136">In error cases, there may or may not be a `ContentLoading` event depending on whether the navigation is continued to an error page.</span></span>  
 
 <span data-ttu-id="89f22-137">如果 HTTP 重定向发生，则一行中有多个事件，其中更高版本的事件参数设置了属性，但是 `NavigationStarting` `IsRedirect` `NavigationId` 该事件保持不变。</span><span class="sxs-lookup"><span data-stu-id="89f22-137">If an HTTP redirect occurs, there are multiple `NavigationStarting` events in a row, where later event arguments have the `IsRedirect` property set, however the `NavigationId` event remains the same.</span></span>  
 
 <span data-ttu-id="89f22-138">相同的文档导航事件（如导航到片段）不会导致事件， `NavigationStarting` 并且不会增加 `NavigationId` 事件。</span><span class="sxs-lookup"><span data-stu-id="89f22-138">Same document navigation events, such as navigating to a fragment, do not result in the `NavigationStarting` event and do not increment the `NavigationId` event.</span></span>  

<span data-ttu-id="89f22-139">若要监视或取消 WebView2 实例中的子框架内的导航事件，请使用 和 事件，这些事件与等效的非 `FrameNavigationStarting` `FrameNavigationCompleted` 帧对应事件类似。</span><span class="sxs-lookup"><span data-stu-id="89f22-139">To monitor or cancel navigation events inside subframes in a WebView2 instance, use the `FrameNavigationStarting` and `FrameNavigationCompleted` events that act just like the equivalent non-frame counterpart events.</span></span>  

## <a name="see-also"></a><span data-ttu-id="89f22-140">另请参阅</span><span class="sxs-lookup"><span data-stu-id="89f22-140">See also</span></span>  

*   <span data-ttu-id="89f22-141">若要开始使用 WebView2，请导航到 ["WebView2 入门指南"][Webview2IndexGetStarted] 指南。</span><span class="sxs-lookup"><span data-stu-id="89f22-141">To get started using WebView2, navigate to [WebView2 Get Started Guides][Webview2IndexGetStarted] guides.</span></span>  
*   <span data-ttu-id="89f22-142">有关 WebView2 功能的综合示例，请导航到 GitHub 上的 [WebView2Samples][GithubMicrosoftedgeWebview2samples] 存储库。</span><span class="sxs-lookup"><span data-stu-id="89f22-142">For a comprehensive example of WebView2 capabilities, navigate to [WebView2Samples repo][GithubMicrosoftedgeWebview2samples] on GitHub.</span></span>  
*   <span data-ttu-id="89f22-143">有关 WebView2 API 的更多详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="89f22-143">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  
*   <span data-ttu-id="89f22-144">有关 WebView2 的信息，请导航到["WebView2 资源"。][Webview2IndexNextSteps]</span><span class="sxs-lookup"><span data-stu-id="89f22-144">For more information about WebView2, navigate to [WebView2 Resources][Webview2IndexNextSteps].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="89f22-145">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="89f22-145">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2IndexGetStarted]: ../index.md#get-started "入门 - Microsoft Edge WebView2 |Microsoft Docs"  
[Webview2IndexNextSteps]: ../index.md#next-steps "下一步 - Microsoft Edge WebView2 |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  

[GithubMicrosoftedgeWebview2samples]: https://github.com/MicrosoftEdge/WebView2Samples "WebView2 示例 - MicrosoftEdge/WebView2Samples |GitHub"  
