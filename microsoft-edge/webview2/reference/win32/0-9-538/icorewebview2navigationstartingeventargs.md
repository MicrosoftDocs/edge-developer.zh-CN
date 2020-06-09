---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 705289c386a174bf6ac3929fabf9ede92e0987ae
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698409"
---
# <span data-ttu-id="4af7e-104">interface ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="4af7e-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="4af7e-105">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="4af7e-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="4af7e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4af7e-106">Summary</span></span>

 <span data-ttu-id="4af7e-107">成员</span><span class="sxs-lookup"><span data-stu-id="4af7e-107">Members</span></span>                        | <span data-ttu-id="4af7e-108">描述</span><span class="sxs-lookup"><span data-stu-id="4af7e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4af7e-109">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="4af7e-109">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="4af7e-110">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="4af7e-110">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="4af7e-111">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="4af7e-111">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="4af7e-112">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="4af7e-112">True when the navigation is redirected.</span></span>
[<span data-ttu-id="4af7e-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4af7e-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="4af7e-114">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="4af7e-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="4af7e-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4af7e-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="4af7e-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="4af7e-116">The ID of the navigation.</span></span>
[<span data-ttu-id="4af7e-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="4af7e-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="4af7e-118">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="4af7e-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="4af7e-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4af7e-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4af7e-120">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="4af7e-120">The uri of the requested navigation.</span></span>
[<span data-ttu-id="4af7e-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="4af7e-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="4af7e-122">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="4af7e-122">Set the Cancel property.</span></span>

## <span data-ttu-id="4af7e-123">成员</span><span class="sxs-lookup"><span data-stu-id="4af7e-123">Members</span></span>

#### <span data-ttu-id="4af7e-124">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="4af7e-124">get_Cancel</span></span> 

<span data-ttu-id="4af7e-125">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="4af7e-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="4af7e-126">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="4af7e-126">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="4af7e-127">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="4af7e-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="4af7e-128">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="4af7e-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="4af7e-129">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="4af7e-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="4af7e-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="4af7e-130">get_IsRedirected</span></span> 

<span data-ttu-id="4af7e-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="4af7e-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="4af7e-132">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="4af7e-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="4af7e-133">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="4af7e-133">get_IsUserInitiated</span></span> 

<span data-ttu-id="4af7e-134">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="4af7e-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="4af7e-135">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="4af7e-135">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="4af7e-136">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="4af7e-136">get_NavigationId</span></span> 

<span data-ttu-id="4af7e-137">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="4af7e-137">The ID of the navigation.</span></span>

> <span data-ttu-id="4af7e-138">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="4af7e-138">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="4af7e-139">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="4af7e-139">get_RequestHeaders</span></span> 

<span data-ttu-id="4af7e-140">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="4af7e-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="4af7e-141">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="4af7e-141">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="4af7e-142">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="4af7e-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="4af7e-143">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4af7e-143">get_Uri</span></span> 

<span data-ttu-id="4af7e-144">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="4af7e-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="4af7e-145">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="4af7e-145">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4af7e-146">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="4af7e-146">put_Cancel</span></span> 

<span data-ttu-id="4af7e-147">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="4af7e-147">Set the Cancel property.</span></span>

> <span data-ttu-id="4af7e-148">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="4af7e-148">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

