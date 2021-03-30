---
description: 导航
title: 导航
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/05/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: ac15b9f32a29c64bbdc2a7886fa654a2d71a5453
ms.sourcegitcommit: 4cea8cf99b5f12db9d2daba99bbf48f3ccc537fe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314795"
---
# <span data-ttu-id="0d3cd-104">导航事件</span><span class="sxs-lookup"><span data-stu-id="0d3cd-104">Navigation events</span></span>  

<span data-ttu-id="0d3cd-105">导航事件的正常顺序是 `NavigationStarting` `SourceChanged` `ContentLoading` `HistoryChanged` ，，，然后 `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-105">The normal sequence of navigation events is `NavigationStarting`, `SourceChanged`, `ContentLoading`, `HistoryChanged`, and then `NavigationCompleted`.</span></span>  <span data-ttu-id="0d3cd-106">以下事件描述每次导航期间 WebView2 的状态。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-106">The following events describe the state of WebView2 during each navigation.</span></span>  

| <span data-ttu-id="0d3cd-107">Sequence</span><span class="sxs-lookup"><span data-stu-id="0d3cd-107">Sequence</span></span> | <span data-ttu-id="0d3cd-108">事件名称</span><span class="sxs-lookup"><span data-stu-id="0d3cd-108">Event name</span></span> | <span data-ttu-id="0d3cd-109">详细信息</span><span class="sxs-lookup"><span data-stu-id="0d3cd-109">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="0d3cd-110">1</span><span class="sxs-lookup"><span data-stu-id="0d3cd-110">1</span></span> | `NavigationStarting`  |  <span data-ttu-id="0d3cd-111">WebView2 开始导航，导航导致网络请求。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-111">WebView2 starts to navigate and the navigation results in a network request.</span></span>  <span data-ttu-id="0d3cd-112">主机能够在事件期间禁止请求。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-112">The host is able to disallow the request during the event.</span></span>  |  
| <span data-ttu-id="0d3cd-113">2</span><span class="sxs-lookup"><span data-stu-id="0d3cd-113">2</span></span> | `SourceChanged`  |  <span data-ttu-id="0d3cd-114">WebView2 的源将更改到新 URL。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-114">The source of WebView2 changes to a new URL.</span></span>  <span data-ttu-id="0d3cd-115">该事件可能由不会引起网络请求（如片段导航）的导航导致。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-115">The event may result from a navigation that does not cause a network request such as a fragment navigation.</span></span>  |  
| <span data-ttu-id="0d3cd-116">3</span><span class="sxs-lookup"><span data-stu-id="0d3cd-116">3</span></span> | `HistoryChanged`  |  <span data-ttu-id="0d3cd-117">由于导航，WebView2 的历史记录会更新。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-117">The history of WebView2 updates as a result of the navigation.</span></span>  |  
| <span data-ttu-id="0d3cd-118">4</span><span class="sxs-lookup"><span data-stu-id="0d3cd-118">4</span></span> | `ContentLoading`  |  <span data-ttu-id="0d3cd-119">WebView2 开始加载新页面的内容。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-119">WebView2 starts loading content for the new page.</span></span>  |  
| <span data-ttu-id="0d3cd-120">5</span><span class="sxs-lookup"><span data-stu-id="0d3cd-120">5</span></span> | `NavigationCompleted`  |  <span data-ttu-id="0d3cd-121">WebView2 将完成新页面上的内容加载。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-121">WebView2 completes loading content on the new page.</span></span>  |  

<span data-ttu-id="0d3cd-122">使用 `navigations` 导航 ID \(`NavigationId` \) 跟踪每个新文档。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-122">Track `navigations` to each new document using the navigation ID \(`NavigationId`\).</span></span>  <span data-ttu-id="0d3cd-123">每次 `NavigationId` 成功导航到新文档时，WebView 都会更改。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-123">The `NavigationId` of WebView changes every time there is a successful navigation to a new document.</span></span>

:::image type="complex" source="../media/navigation-graph.png" alt-text="Microsoft Edge WebView2 导航事件" lightbox="../media/navigation-graph.png":::
   <span data-ttu-id="0d3cd-125">Microsoft Edge WebView2 导航事件</span><span class="sxs-lookup"><span data-stu-id="0d3cd-125">The Microsoft Edge WebView2 Navigation Events</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="0d3cd-126">上图表示在各自的事件参数上具有相同的属性 `NavigationId` 的导航事件。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-126">The previous figure represents navigation events with the same `NavigationId` property on the respective event arg.</span></span>  

 `Navigations` <span data-ttu-id="0d3cd-127">事件实例不同的 `NavigationId` 事件可能会重叠。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-127">events with different instances of `NavigationId` event may overlap.</span></span>  <span data-ttu-id="0d3cd-128">例如，启动导航时，必须等待相关 `NavigationStarting` 事件。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-128">For instance when you start a navigation, you have to wait for the related `NavigationStarting` event.</span></span>  <span data-ttu-id="0d3cd-129">如果随后启动另一个导航，则应该会看到第一个导航的事件，后跟第二个导航的事件，然后是第一个导航的事件，然后是第二个导航的所有其他相应导航事件。 `NavigationStarting` `NavigationStarting` `NavigationCompleted`</span><span class="sxs-lookup"><span data-stu-id="0d3cd-129">If you then start another navigation, you should see the `NavigationStarting` event for the first navigate followed by the `NavigationStarting` event for the second navigate, followed by the `NavigationCompleted` event for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span>  
 
 <span data-ttu-id="0d3cd-130">在错误情况下，可能会或可能不会发生事件，具体取决于导航 `ContentLoading` 是否继续导航到错误页面。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-130">In error cases there may or may not be a `ContentLoading` event depending on whether the navigation is continued to an error page.</span></span>  
 
 <span data-ttu-id="0d3cd-131">对于 HTTP 重定向，一行中有多个事件，其中后续事件参数设置了属性，但 `NavigationStarting` `IsRedirect` 事件参数 `NavigationId` 保持不变。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-131">In the case of an HTTP redirect, there are multiple `NavigationStarting` events in a row, where subsequent event args have the `IsRedirect` property set, however the `NavigationId` remains the same.</span></span>  
 
 <span data-ttu-id="0d3cd-132">相同的 `navigations` 文档（如导航到片段）不会产生 `NavigationStarting` 事件，并且不会增加 `NavigationId` 。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-132">Same document `navigations`, such as navigating to a fragment, do not result in the `NavigationStarting` event and do not increment the `NavigationId`.</span></span>  

<span data-ttu-id="0d3cd-133">若要监视或取消 WebView 中的子框架内部，请使用和事件，这些事件的行为与等效的非 `navigations` `FrameNavigationStarting` `FrameNavigationCompleted` 帧对应事件类似。</span><span class="sxs-lookup"><span data-stu-id="0d3cd-133">To monitor or cancel `navigations` inside subframes in the WebView, use the `FrameNavigationStarting` and the `FrameNavigationCompleted` events which act just like the equivalent non-frame counterpart events.</span></span>  

<!-- links -->  
