---
description: 导航
title: 导航
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/23/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 0df8e12acb11824006515ac711250d776d276e36
ms.sourcegitcommit: 553957c101f83681b363103cb6af56bf20173f23
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/24/2020
ms.locfileid: "10895553"
---
# <span data-ttu-id="e1929-104">导航事件</span><span class="sxs-lookup"><span data-stu-id="e1929-104">Navigation events</span></span>  

<span data-ttu-id="e1929-105">导航事件的正常顺序为、、、 `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` 和 `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="e1929-105">The normal sequence of navigation events is `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span>  <span data-ttu-id="e1929-106">以下事件描述了每个导航期间 WebView2 的状态。</span><span class="sxs-lookup"><span data-stu-id="e1929-106">The following events describe the state of WebView2 during each navigation.</span></span>  

| <span data-ttu-id="e1929-107">次序</span><span class="sxs-lookup"><span data-stu-id="e1929-107">Sequence</span></span> | <span data-ttu-id="e1929-108">事件名称</span><span class="sxs-lookup"><span data-stu-id="e1929-108">Event name</span></span> | <span data-ttu-id="e1929-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="e1929-109">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="e1929-110">raid-1</span><span class="sxs-lookup"><span data-stu-id="e1929-110">1</span></span> | `NavigationStarting`  |  <span data-ttu-id="e1929-111">WebView2 将开始导航，并且导航会导致网络请求。</span><span class="sxs-lookup"><span data-stu-id="e1929-111">WebView2 starts to navigate and the navigation results in a network request.</span></span>  <span data-ttu-id="e1929-112">主机能够在事件期间禁止请求。</span><span class="sxs-lookup"><span data-stu-id="e1929-112">The host is able to disallow the request during the event.</span></span>  |  
| <span data-ttu-id="e1929-113">ppls-2</span><span class="sxs-lookup"><span data-stu-id="e1929-113">2</span></span> | `SourceChanged`  |  <span data-ttu-id="e1929-114">WebView2 的源更改为新的 URL。</span><span class="sxs-lookup"><span data-stu-id="e1929-114">The source of WebView2 changes to a new URL.</span></span>  <span data-ttu-id="e1929-115">此事件可能是由不会导致网络请求（如片段导航）的导航导致的。</span><span class="sxs-lookup"><span data-stu-id="e1929-115">The event may result from a navigation that does not cause a network request such as a fragment navigation.</span></span>  |  
| <span data-ttu-id="e1929-116">三维空间</span><span class="sxs-lookup"><span data-stu-id="e1929-116">3</span></span> | `HistoryChanged`  |  <span data-ttu-id="e1929-117">导航的结果 WebView2 更新的历史记录。</span><span class="sxs-lookup"><span data-stu-id="e1929-117">The history of WebView2 updates as a result of the navigation.</span></span>  |  
| <span data-ttu-id="e1929-118">第</span><span class="sxs-lookup"><span data-stu-id="e1929-118">4</span></span> | `ContentLoading`  |  <span data-ttu-id="e1929-119">Web 视图开始为新页面加载内容。</span><span class="sxs-lookup"><span data-stu-id="e1929-119">WebView starts loading content for the new page.</span></span>  |  
| <span data-ttu-id="e1929-120">级</span><span class="sxs-lookup"><span data-stu-id="e1929-120">5</span></span> | `NavigationCompleted`  |  <span data-ttu-id="e1929-121">WebView2 完成在新页面上加载内容的工作。</span><span class="sxs-lookup"><span data-stu-id="e1929-121">WebView2 completes loading content on the new page.</span></span>  |  

<span data-ttu-id="e1929-122">`navigations`使用导航 ID \ （\）跟踪到每个新文档 `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="e1929-122">Track `navigations` to each new document using the navigation ID \(`NavigationId`\).</span></span>  <span data-ttu-id="e1929-123">`NavigationId`每次成功导航到新文档时，Web 视图的更改。</span><span class="sxs-lookup"><span data-stu-id="e1929-123">The `NavigationId` of WebView changes every time there is a successful navigation to a new document.</span></span>

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 导航事件" lightbox="../media/navigation-graph.png":::
   <span data-ttu-id="e1929-125">Microsoft Edge WebView2 导航事件</span><span class="sxs-lookup"><span data-stu-id="e1929-125">The Microsoft Edge WebView2 Navigation Events</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="e1929-126">上图表示具有相应事件参数的相同属性的导航事件 `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="e1929-126">The previous figure represents navigation events with the same `NavigationId` property on the respective event arg.</span></span>  

 `Navigations` <span data-ttu-id="e1929-127">具有不同事件实例的事件 `NavigationId` 可能会重叠。</span><span class="sxs-lookup"><span data-stu-id="e1929-127">events with different instances of `NavigationId` event may overlap.</span></span>  <span data-ttu-id="e1929-128">例如，当您启动导航时，您必须等待相关 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="e1929-128">For instance when you start a navigation, you have to wait for the related `NavigationStarting` event.</span></span>  <span data-ttu-id="e1929-129">如果你随后开始另一个导航，你应该看到 `NavigationStarting` 第一个导航的事件，后跟第 `NavigationStarting` 二个导航的事件，然后是 `NavigationCompleted` 第一个导航的事件，然后是第二个导航的所有其余导航事件。</span><span class="sxs-lookup"><span data-stu-id="e1929-129">If you then start another navigation, you should see the `NavigationStarting` event for the first navigate followed by the `NavigationStarting` event for the second navigate, followed by the `NavigationCompleted` event for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span>  
 
 <span data-ttu-id="e1929-130">在错误情况下，可能会有也可能不是 `ContentLoading` 事件，具体取决于导航是否转到错误页面。</span><span class="sxs-lookup"><span data-stu-id="e1929-130">In error cases there may or may not be a `ContentLoading` event depending on whether the navigation is continued to an error page.</span></span>  
 
 <span data-ttu-id="e1929-131">在 HTTP 重定向的情况下，一行中有多个 `NavigationStarting` 事件，后续事件参数 `IsRedirect` 设置了属性，但是保持不变 `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="e1929-131">In the case of an HTTP redirect, there are multiple `NavigationStarting` events in a row, where subsequent event args have the `IsRedirect` property set, however the `NavigationId` remains the same.</span></span>  
 
 <span data-ttu-id="e1929-132">同一文档 `navigations` （例如导航到片段）不会导致 `NavigationStarting` 事件，也不会增加 `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="e1929-132">Same document `navigations`, such as navigating to a fragment, do not result in the `NavigationStarting` event and do not increment the `NavigationId`.</span></span>  

<span data-ttu-id="e1929-133">若要 `navigations` 在 Web 视图中的 subframes 内监视或取消，请使用 `FrameNavigationStarting` 与 `FrameNavigationCompleted` 等效的非帧对应事件相同的事件。</span><span class="sxs-lookup"><span data-stu-id="e1929-133">To monitor or cancel `navigations` inside subframes in the WebView, use the `FrameNavigationStarting` and the `FrameNavigationCompleted` events which act just like the equivalent non-frame counterpart events.</span></span>  

<!-- links -->  
