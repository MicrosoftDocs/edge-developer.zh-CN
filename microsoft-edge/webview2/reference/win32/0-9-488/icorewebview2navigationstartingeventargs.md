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
ms.openlocfilehash: d56f40a9780313c79f421559eaf54750828542a5
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697187"
---
# <span data-ttu-id="c21c9-104">interface ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="c21c9-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="c21c9-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="c21c9-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="c21c9-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="c21c9-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="c21c9-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c21c9-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="c21c9-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c21c9-108">Summary</span></span>

 <span data-ttu-id="c21c9-109">成员</span><span class="sxs-lookup"><span data-stu-id="c21c9-109">Members</span></span>                        | <span data-ttu-id="c21c9-110">描述</span><span class="sxs-lookup"><span data-stu-id="c21c9-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c21c9-111">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="c21c9-111">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="c21c9-112">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="c21c9-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="c21c9-113">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="c21c9-113">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="c21c9-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="c21c9-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="c21c9-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="c21c9-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="c21c9-116">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="c21c9-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="c21c9-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="c21c9-117">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="c21c9-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="c21c9-118">The ID of the navigation.</span></span>
[<span data-ttu-id="c21c9-119">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="c21c9-119">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="c21c9-120">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c21c9-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="c21c9-121">get_Uri</span><span class="sxs-lookup"><span data-stu-id="c21c9-121">get_Uri</span></span>](#get_uri) | <span data-ttu-id="c21c9-122">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="c21c9-122">The uri of the requested navigation.</span></span>
[<span data-ttu-id="c21c9-123">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="c21c9-123">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="c21c9-124">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="c21c9-124">Set the Cancel property.</span></span>

## <span data-ttu-id="c21c9-125">成员</span><span class="sxs-lookup"><span data-stu-id="c21c9-125">Members</span></span>

#### <span data-ttu-id="c21c9-126">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="c21c9-126">get_Cancel</span></span> 

<span data-ttu-id="c21c9-127">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="c21c9-127">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="c21c9-128">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="c21c9-128">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="c21c9-129">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="c21c9-129">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="c21c9-130">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="c21c9-130">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="c21c9-131">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="c21c9-131">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="c21c9-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="c21c9-132">get_IsRedirected</span></span> 

<span data-ttu-id="c21c9-133">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="c21c9-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="c21c9-134">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="c21c9-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="c21c9-135">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="c21c9-135">get_IsUserInitiated</span></span> 

<span data-ttu-id="c21c9-136">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="c21c9-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="c21c9-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="c21c9-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="c21c9-138">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="c21c9-138">get_NavigationId</span></span> 

<span data-ttu-id="c21c9-139">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="c21c9-139">The ID of the navigation.</span></span>

> <span data-ttu-id="c21c9-140">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="c21c9-140">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="c21c9-141">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="c21c9-141">get_RequestHeaders</span></span> 

<span data-ttu-id="c21c9-142">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c21c9-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="c21c9-143">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="c21c9-143">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="c21c9-144">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c21c9-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="c21c9-145">get_Uri</span><span class="sxs-lookup"><span data-stu-id="c21c9-145">get_Uri</span></span> 

<span data-ttu-id="c21c9-146">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="c21c9-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="c21c9-147">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="c21c9-147">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="c21c9-148">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="c21c9-148">put_Cancel</span></span> 

<span data-ttu-id="c21c9-149">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="c21c9-149">Set the Cancel property.</span></span>

> <span data-ttu-id="c21c9-150">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="c21c9-150">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

