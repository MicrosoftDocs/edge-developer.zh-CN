---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 9aa44483fc824f8a26af6293f031c58d681de624
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880470"
---
# <span data-ttu-id="23ddf-104">0.9.515-接口 ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="23ddf-104">0.9.515 - interface ICoreWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="23ddf-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="23ddf-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="23ddf-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="23ddf-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="23ddf-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="23ddf-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="23ddf-108">摘要</span><span class="sxs-lookup"><span data-stu-id="23ddf-108">Summary</span></span>

 <span data-ttu-id="23ddf-109">成员</span><span class="sxs-lookup"><span data-stu-id="23ddf-109">Members</span></span>                        | <span data-ttu-id="23ddf-110">描述</span><span class="sxs-lookup"><span data-stu-id="23ddf-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="23ddf-111">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="23ddf-111">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="23ddf-112">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="23ddf-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="23ddf-113">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="23ddf-113">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="23ddf-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="23ddf-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="23ddf-115">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="23ddf-115">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="23ddf-116">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="23ddf-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="23ddf-117">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="23ddf-117">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="23ddf-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="23ddf-118">The ID of the navigation.</span></span>
[<span data-ttu-id="23ddf-119">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="23ddf-119">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="23ddf-120">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="23ddf-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="23ddf-121">get_Uri</span><span class="sxs-lookup"><span data-stu-id="23ddf-121">get_Uri</span></span>](#get_uri) | <span data-ttu-id="23ddf-122">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="23ddf-122">The uri of the requested navigation.</span></span>
[<span data-ttu-id="23ddf-123">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="23ddf-123">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="23ddf-124">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="23ddf-124">Set the Cancel property.</span></span>

## <span data-ttu-id="23ddf-125">成员</span><span class="sxs-lookup"><span data-stu-id="23ddf-125">Members</span></span>

#### <span data-ttu-id="23ddf-126">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="23ddf-126">get_Cancel</span></span> 

<span data-ttu-id="23ddf-127">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="23ddf-127">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="23ddf-128">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="23ddf-128">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="23ddf-129">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="23ddf-129">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="23ddf-130">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="23ddf-130">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="23ddf-131">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="23ddf-131">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="23ddf-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="23ddf-132">get_IsRedirected</span></span> 

<span data-ttu-id="23ddf-133">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="23ddf-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="23ddf-134">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="23ddf-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="23ddf-135">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="23ddf-135">get_IsUserInitiated</span></span> 

<span data-ttu-id="23ddf-136">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="23ddf-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="23ddf-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="23ddf-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="23ddf-138">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="23ddf-138">get_NavigationId</span></span> 

<span data-ttu-id="23ddf-139">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="23ddf-139">The ID of the navigation.</span></span>

> <span data-ttu-id="23ddf-140">公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 \* navigation_id）</span><span class="sxs-lookup"><span data-stu-id="23ddf-140">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigation_id)</span></span>

#### <span data-ttu-id="23ddf-141">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="23ddf-141">get_RequestHeaders</span></span> 

<span data-ttu-id="23ddf-142">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="23ddf-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="23ddf-143">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="23ddf-143">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="23ddf-144">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="23ddf-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="23ddf-145">get_Uri</span><span class="sxs-lookup"><span data-stu-id="23ddf-145">get_Uri</span></span> 

<span data-ttu-id="23ddf-146">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="23ddf-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="23ddf-147">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="23ddf-147">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="23ddf-148">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="23ddf-148">put_Cancel</span></span> 

<span data-ttu-id="23ddf-149">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="23ddf-149">Set the Cancel property.</span></span>

> <span data-ttu-id="23ddf-150">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="23ddf-150">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

