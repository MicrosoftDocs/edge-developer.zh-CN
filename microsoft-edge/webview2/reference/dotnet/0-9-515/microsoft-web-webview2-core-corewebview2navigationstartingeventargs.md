---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8b7ac3ab27cf5a2d9e80a77eabc488599820a02f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653230"
---
# <span data-ttu-id="9b751-104">CoreWebView2NavigationStartingEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="9b751-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

<span data-ttu-id="9b751-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="9b751-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9b751-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="9b751-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9b751-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9b751-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="9b751-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9b751-108">Summary</span></span>

 <span data-ttu-id="9b751-109">成员</span><span class="sxs-lookup"><span data-stu-id="9b751-109">Members</span></span>                        | <span data-ttu-id="9b751-110">描述</span><span class="sxs-lookup"><span data-stu-id="9b751-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9b751-111">取消</span><span class="sxs-lookup"><span data-stu-id="9b751-111">Cancel</span></span>](#cancel) | <span data-ttu-id="9b751-112">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="9b751-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="9b751-113">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="9b751-113">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="9b751-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="9b751-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="9b751-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="9b751-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="9b751-116">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="9b751-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="9b751-117">NavigationId</span><span class="sxs-lookup"><span data-stu-id="9b751-117">NavigationId</span></span>](#navigationid) | <span data-ttu-id="9b751-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="9b751-118">The ID of the navigation.</span></span>
[<span data-ttu-id="9b751-119">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="9b751-119">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="9b751-120">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="9b751-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="9b751-121">Uri</span><span class="sxs-lookup"><span data-stu-id="9b751-121">Uri</span></span>](#uri) | <span data-ttu-id="9b751-122">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="9b751-122">The uri of the requested navigation.</span></span>

## <span data-ttu-id="9b751-123">成员</span><span class="sxs-lookup"><span data-stu-id="9b751-123">Members</span></span>

#### <span data-ttu-id="9b751-124">取消</span><span class="sxs-lookup"><span data-stu-id="9b751-124">Cancel</span></span> 

<span data-ttu-id="9b751-125">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="9b751-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="9b751-126">公共 bool[取消](#cancel)</span><span class="sxs-lookup"><span data-stu-id="9b751-126">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="9b751-127">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="9b751-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="9b751-128">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="9b751-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="9b751-129">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="9b751-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="9b751-130">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="9b751-130">IsRedirected</span></span> 

<span data-ttu-id="9b751-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="9b751-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="9b751-132">公共 bool [IsRedirected](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="9b751-132">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="9b751-133">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="9b751-133">IsUserInitiated</span></span> 

<span data-ttu-id="9b751-134">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="9b751-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="9b751-135">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="9b751-135">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="9b751-136">NavigationId</span><span class="sxs-lookup"><span data-stu-id="9b751-136">NavigationId</span></span> 

<span data-ttu-id="9b751-137">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="9b751-137">The ID of the navigation.</span></span>

> <span data-ttu-id="9b751-138">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="9b751-138">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="9b751-139">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="9b751-139">RequestHeaders</span></span> 

<span data-ttu-id="9b751-140">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="9b751-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="9b751-141">公共 HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="9b751-141">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="9b751-142">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="9b751-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="9b751-143">Uri</span><span class="sxs-lookup"><span data-stu-id="9b751-143">Uri</span></span> 

<span data-ttu-id="9b751-144">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="9b751-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="9b751-145">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="9b751-145">public string [Uri](#uri)</span></span>

