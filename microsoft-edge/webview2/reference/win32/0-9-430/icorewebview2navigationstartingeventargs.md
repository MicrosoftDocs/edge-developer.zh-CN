---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: bd9d10d5f281b2e8f0a5d0687235560c44edc170
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886435"
---
# <span data-ttu-id="83241-104">0.9.430-接口 ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="83241-104">0.9.430 - interface ICoreWebView2NavigationStartingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="83241-105">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="83241-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="83241-106">摘要</span><span class="sxs-lookup"><span data-stu-id="83241-106">Summary</span></span>

 <span data-ttu-id="83241-107">成员</span><span class="sxs-lookup"><span data-stu-id="83241-107">Members</span></span>                        | <span data-ttu-id="83241-108">描述</span><span class="sxs-lookup"><span data-stu-id="83241-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="83241-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="83241-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="83241-110">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="83241-110">The uri of the requested navigation.</span></span>
[<span data-ttu-id="83241-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="83241-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="83241-112">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="83241-112">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="83241-113">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="83241-113">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="83241-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="83241-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="83241-115">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="83241-115">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="83241-116">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="83241-116">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="83241-117">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="83241-117">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="83241-118">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="83241-118">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="83241-119">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="83241-119">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="83241-120">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="83241-120">Set the Cancel property.</span></span>
[<span data-ttu-id="83241-121">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="83241-121">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="83241-122">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="83241-122">The ID of the navigation.</span></span>

## <span data-ttu-id="83241-123">成员</span><span class="sxs-lookup"><span data-stu-id="83241-123">Members</span></span>

#### <span data-ttu-id="83241-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="83241-124">get_Uri</span></span> 

<span data-ttu-id="83241-125">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="83241-125">The uri of the requested navigation.</span></span>

> <span data-ttu-id="83241-126">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="83241-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="83241-127">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="83241-127">get_IsUserInitiated</span></span> 

<span data-ttu-id="83241-128">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="83241-128">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="83241-129">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="83241-129">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="83241-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="83241-130">get_IsRedirected</span></span> 

<span data-ttu-id="83241-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="83241-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="83241-132">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="83241-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="83241-133">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="83241-133">get_RequestHeaders</span></span> 

<span data-ttu-id="83241-134">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="83241-134">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="83241-135">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="83241-135">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="83241-136">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="83241-136">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="83241-137">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="83241-137">get_Cancel</span></span> 

<span data-ttu-id="83241-138">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="83241-138">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="83241-139">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="83241-139">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="83241-140">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="83241-140">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="83241-141">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="83241-141">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="83241-142">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="83241-142">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="83241-143">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="83241-143">put_Cancel</span></span> 

<span data-ttu-id="83241-144">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="83241-144">Set the Cancel property.</span></span>

> <span data-ttu-id="83241-145">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="83241-145">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

#### <span data-ttu-id="83241-146">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="83241-146">get_NavigationId</span></span> 

<span data-ttu-id="83241-147">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="83241-147">The ID of the navigation.</span></span>

> <span data-ttu-id="83241-148">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="83241-148">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

