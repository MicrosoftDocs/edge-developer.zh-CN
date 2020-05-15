---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 3b348d64bb09fcdc693ffbdfa5481fe6d7520cae
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652873"
---
# <span data-ttu-id="01a11-104">interface ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="01a11-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="01a11-105">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="01a11-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="01a11-106">摘要</span><span class="sxs-lookup"><span data-stu-id="01a11-106">Summary</span></span>

 <span data-ttu-id="01a11-107">成员</span><span class="sxs-lookup"><span data-stu-id="01a11-107">Members</span></span>                        | <span data-ttu-id="01a11-108">描述</span><span class="sxs-lookup"><span data-stu-id="01a11-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="01a11-109">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="01a11-109">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="01a11-110">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="01a11-110">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="01a11-111">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="01a11-111">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="01a11-112">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="01a11-112">True when the navigation is redirected.</span></span>
[<span data-ttu-id="01a11-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="01a11-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="01a11-114">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="01a11-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="01a11-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="01a11-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="01a11-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="01a11-116">The ID of the navigation.</span></span>
[<span data-ttu-id="01a11-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="01a11-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="01a11-118">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="01a11-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="01a11-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="01a11-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="01a11-120">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="01a11-120">The uri of the requested navigation.</span></span>
[<span data-ttu-id="01a11-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="01a11-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="01a11-122">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="01a11-122">Set the Cancel property.</span></span>

## <span data-ttu-id="01a11-123">成员</span><span class="sxs-lookup"><span data-stu-id="01a11-123">Members</span></span>

#### <span data-ttu-id="01a11-124">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="01a11-124">get_Cancel</span></span> 

<span data-ttu-id="01a11-125">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="01a11-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="01a11-126">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="01a11-126">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="01a11-127">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="01a11-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="01a11-128">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="01a11-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="01a11-129">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="01a11-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="01a11-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="01a11-130">get_IsRedirected</span></span> 

<span data-ttu-id="01a11-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="01a11-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="01a11-132">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="01a11-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="01a11-133">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="01a11-133">get_IsUserInitiated</span></span> 

<span data-ttu-id="01a11-134">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="01a11-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="01a11-135">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="01a11-135">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="01a11-136">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="01a11-136">get_NavigationId</span></span> 

<span data-ttu-id="01a11-137">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="01a11-137">The ID of the navigation.</span></span>

> <span data-ttu-id="01a11-138">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="01a11-138">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="01a11-139">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="01a11-139">get_RequestHeaders</span></span> 

<span data-ttu-id="01a11-140">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="01a11-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="01a11-141">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="01a11-141">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="01a11-142">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="01a11-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="01a11-143">get_Uri</span><span class="sxs-lookup"><span data-stu-id="01a11-143">get_Uri</span></span> 

<span data-ttu-id="01a11-144">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="01a11-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="01a11-145">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="01a11-145">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="01a11-146">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="01a11-146">put_Cancel</span></span> 

<span data-ttu-id="01a11-147">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="01a11-147">Set the Cancel property.</span></span>

> <span data-ttu-id="01a11-148">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="01a11-148">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

