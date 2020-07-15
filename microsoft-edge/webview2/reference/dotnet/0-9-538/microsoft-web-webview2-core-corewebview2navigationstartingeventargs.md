---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2NavigationStartingEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: cd692de6aaa3dc694fb2fe149411e5fd64de1ee2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878867"
---
# <span data-ttu-id="a42f5-104">CoreWebView2NavigationStartingEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a42f5-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

<span data-ttu-id="a42f5-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a42f5-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a42f5-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a42f5-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a42f5-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a42f5-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="a42f5-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a42f5-108">Summary</span></span>

 <span data-ttu-id="a42f5-109">成员</span><span class="sxs-lookup"><span data-stu-id="a42f5-109">Members</span></span>                        | <span data-ttu-id="a42f5-110">描述</span><span class="sxs-lookup"><span data-stu-id="a42f5-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a42f5-111">取消</span><span class="sxs-lookup"><span data-stu-id="a42f5-111">Cancel</span></span>](#cancel) | <span data-ttu-id="a42f5-112">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="a42f5-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="a42f5-113">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="a42f5-113">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="a42f5-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="a42f5-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="a42f5-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="a42f5-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="a42f5-116">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="a42f5-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="a42f5-117">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a42f5-117">NavigationId</span></span>](#navigationid) | <span data-ttu-id="a42f5-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a42f5-118">The ID of the navigation.</span></span>
[<span data-ttu-id="a42f5-119">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="a42f5-119">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="a42f5-120">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="a42f5-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="a42f5-121">Uri</span><span class="sxs-lookup"><span data-stu-id="a42f5-121">Uri</span></span>](#uri) | <span data-ttu-id="a42f5-122">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="a42f5-122">The uri of the requested navigation.</span></span>

## <span data-ttu-id="a42f5-123">成员</span><span class="sxs-lookup"><span data-stu-id="a42f5-123">Members</span></span>

#### <span data-ttu-id="a42f5-124">取消</span><span class="sxs-lookup"><span data-stu-id="a42f5-124">Cancel</span></span> 

<span data-ttu-id="a42f5-125">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="a42f5-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="a42f5-126">公共 bool[取消](#cancel)</span><span class="sxs-lookup"><span data-stu-id="a42f5-126">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="a42f5-127">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="a42f5-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="a42f5-128">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="a42f5-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="a42f5-129">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="a42f5-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="a42f5-130">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="a42f5-130">IsRedirected</span></span> 

<span data-ttu-id="a42f5-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="a42f5-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="a42f5-132">公共 bool [IsRedirected](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="a42f5-132">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="a42f5-133">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="a42f5-133">IsUserInitiated</span></span> 

<span data-ttu-id="a42f5-134">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="a42f5-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="a42f5-135">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="a42f5-135">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="a42f5-136">NavigationId</span><span class="sxs-lookup"><span data-stu-id="a42f5-136">NavigationId</span></span> 

<span data-ttu-id="a42f5-137">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="a42f5-137">The ID of the navigation.</span></span>

> <span data-ttu-id="a42f5-138">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="a42f5-138">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="a42f5-139">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="a42f5-139">RequestHeaders</span></span> 

<span data-ttu-id="a42f5-140">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="a42f5-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="a42f5-141">公共 HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="a42f5-141">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="a42f5-142">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="a42f5-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="a42f5-143">Uri</span><span class="sxs-lookup"><span data-stu-id="a42f5-143">Uri</span></span> 

<span data-ttu-id="a42f5-144">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="a42f5-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="a42f5-145">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="a42f5-145">public string [Uri](#uri)</span></span>

