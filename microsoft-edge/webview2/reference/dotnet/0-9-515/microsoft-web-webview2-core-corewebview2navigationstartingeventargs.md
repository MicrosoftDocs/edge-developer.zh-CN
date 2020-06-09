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
ms.openlocfilehash: 98e242ace5eb0ae5958ddb1eb6cd380d194294be
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697628"
---
# <span data-ttu-id="104a2-104">CoreWebView2NavigationStartingEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="104a2-104">Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="104a2-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="104a2-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="104a2-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="104a2-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="104a2-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="104a2-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="104a2-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="104a2-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="104a2-109">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="104a2-109">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="104a2-110">摘要</span><span class="sxs-lookup"><span data-stu-id="104a2-110">Summary</span></span>

 <span data-ttu-id="104a2-111">成员</span><span class="sxs-lookup"><span data-stu-id="104a2-111">Members</span></span>                        | <span data-ttu-id="104a2-112">描述</span><span class="sxs-lookup"><span data-stu-id="104a2-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="104a2-113">取消</span><span class="sxs-lookup"><span data-stu-id="104a2-113">Cancel</span></span>](#cancel) | <span data-ttu-id="104a2-114">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="104a2-114">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="104a2-115">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="104a2-115">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="104a2-116">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="104a2-116">True when the navigation is redirected.</span></span>
[<span data-ttu-id="104a2-117">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="104a2-117">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="104a2-118">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="104a2-118">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="104a2-119">NavigationId</span><span class="sxs-lookup"><span data-stu-id="104a2-119">NavigationId</span></span>](#navigationid) | <span data-ttu-id="104a2-120">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="104a2-120">The ID of the navigation.</span></span>
[<span data-ttu-id="104a2-121">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="104a2-121">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="104a2-122">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="104a2-122">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="104a2-123">Uri</span><span class="sxs-lookup"><span data-stu-id="104a2-123">Uri</span></span>](#uri) | <span data-ttu-id="104a2-124">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="104a2-124">The uri of the requested navigation.</span></span>

## <span data-ttu-id="104a2-125">成员</span><span class="sxs-lookup"><span data-stu-id="104a2-125">Members</span></span>

#### <span data-ttu-id="104a2-126">取消</span><span class="sxs-lookup"><span data-stu-id="104a2-126">Cancel</span></span> 

<span data-ttu-id="104a2-127">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="104a2-127">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="104a2-128">公共 bool[取消](#cancel)</span><span class="sxs-lookup"><span data-stu-id="104a2-128">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="104a2-129">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="104a2-129">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="104a2-130">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="104a2-130">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="104a2-131">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="104a2-131">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="104a2-132">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="104a2-132">IsRedirected</span></span> 

<span data-ttu-id="104a2-133">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="104a2-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="104a2-134">公共 bool [IsRedirected](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="104a2-134">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="104a2-135">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="104a2-135">IsUserInitiated</span></span> 

<span data-ttu-id="104a2-136">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="104a2-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="104a2-137">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="104a2-137">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="104a2-138">NavigationId</span><span class="sxs-lookup"><span data-stu-id="104a2-138">NavigationId</span></span> 

<span data-ttu-id="104a2-139">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="104a2-139">The ID of the navigation.</span></span>

> <span data-ttu-id="104a2-140">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="104a2-140">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="104a2-141">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="104a2-141">RequestHeaders</span></span> 

<span data-ttu-id="104a2-142">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="104a2-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="104a2-143">公共 HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="104a2-143">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="104a2-144">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="104a2-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="104a2-145">Uri</span><span class="sxs-lookup"><span data-stu-id="104a2-145">Uri</span></span> 

<span data-ttu-id="104a2-146">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="104a2-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="104a2-147">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="104a2-147">public string [Uri](#uri)</span></span>

