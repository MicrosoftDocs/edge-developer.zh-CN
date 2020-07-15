---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: c2ac2e499e6bbd49f411a001e061af72fda524b5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877880"
---
# <span data-ttu-id="fe407-104">0.9.430-接口 ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="fe407-104">0.9.430 - interface ICoreWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="fe407-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="fe407-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="fe407-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="fe407-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="fe407-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fe407-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="fe407-108">摘要</span><span class="sxs-lookup"><span data-stu-id="fe407-108">Summary</span></span>

 <span data-ttu-id="fe407-109">成员</span><span class="sxs-lookup"><span data-stu-id="fe407-109">Members</span></span>                        | <span data-ttu-id="fe407-110">描述</span><span class="sxs-lookup"><span data-stu-id="fe407-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fe407-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="fe407-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="fe407-112">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="fe407-112">The uri of the requested navigation.</span></span>
[<span data-ttu-id="fe407-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="fe407-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="fe407-114">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="fe407-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="fe407-115">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="fe407-115">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="fe407-116">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="fe407-116">True when the navigation is redirected.</span></span>
[<span data-ttu-id="fe407-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="fe407-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="fe407-118">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="fe407-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="fe407-119">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="fe407-119">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="fe407-120">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="fe407-120">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="fe407-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="fe407-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="fe407-122">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="fe407-122">Set the Cancel property.</span></span>
[<span data-ttu-id="fe407-123">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="fe407-123">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="fe407-124">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="fe407-124">The ID of the navigation.</span></span>

## <span data-ttu-id="fe407-125">成员</span><span class="sxs-lookup"><span data-stu-id="fe407-125">Members</span></span>

#### <span data-ttu-id="fe407-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="fe407-126">get_Uri</span></span> 

<span data-ttu-id="fe407-127">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="fe407-127">The uri of the requested navigation.</span></span>

> <span data-ttu-id="fe407-128">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="fe407-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="fe407-129">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="fe407-129">get_IsUserInitiated</span></span> 

<span data-ttu-id="fe407-130">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="fe407-130">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="fe407-131">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="fe407-131">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="fe407-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="fe407-132">get_IsRedirected</span></span> 

<span data-ttu-id="fe407-133">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="fe407-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="fe407-134">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="fe407-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="fe407-135">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="fe407-135">get_RequestHeaders</span></span> 

<span data-ttu-id="fe407-136">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="fe407-136">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="fe407-137">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="fe407-137">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="fe407-138">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="fe407-138">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="fe407-139">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="fe407-139">get_Cancel</span></span> 

<span data-ttu-id="fe407-140">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="fe407-140">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="fe407-141">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="fe407-141">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="fe407-142">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="fe407-142">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="fe407-143">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="fe407-143">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="fe407-144">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="fe407-144">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="fe407-145">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="fe407-145">put_Cancel</span></span> 

<span data-ttu-id="fe407-146">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="fe407-146">Set the Cancel property.</span></span>

> <span data-ttu-id="fe407-147">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="fe407-147">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

#### <span data-ttu-id="fe407-148">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="fe407-148">get_NavigationId</span></span> 

<span data-ttu-id="fe407-149">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="fe407-149">The ID of the navigation.</span></span>

> <span data-ttu-id="fe407-150">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="fe407-150">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

