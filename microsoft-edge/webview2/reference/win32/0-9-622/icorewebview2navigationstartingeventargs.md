---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationStartingEventArgs
ms.openlocfilehash: ebfb4aaf3f0c2b5531aaab3783572cf550bebf83
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011761"
---
# <span data-ttu-id="b42ac-104">interface ICoreWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="b42ac-104">interface ICoreWebView2NavigationStartingEventArgs</span></span> 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="b42ac-105">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="b42ac-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="b42ac-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b42ac-106">Summary</span></span>

 <span data-ttu-id="b42ac-107">成员</span><span class="sxs-lookup"><span data-stu-id="b42ac-107">Members</span></span>                        | <span data-ttu-id="b42ac-108">描述</span><span class="sxs-lookup"><span data-stu-id="b42ac-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b42ac-109">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="b42ac-109">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="b42ac-110">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="b42ac-110">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="b42ac-111">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="b42ac-111">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="b42ac-112">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="b42ac-112">True when the navigation is redirected.</span></span>
[<span data-ttu-id="b42ac-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="b42ac-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="b42ac-114">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="b42ac-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="b42ac-115">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="b42ac-115">get_NavigationId</span></span>](#get_navigationid) | <span data-ttu-id="b42ac-116">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="b42ac-116">The ID of the navigation.</span></span>
[<span data-ttu-id="b42ac-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="b42ac-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="b42ac-118">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="b42ac-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="b42ac-119">get_Uri</span><span class="sxs-lookup"><span data-stu-id="b42ac-119">get_Uri</span></span>](#get_uri) | <span data-ttu-id="b42ac-120">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="b42ac-120">The uri of the requested navigation.</span></span>
[<span data-ttu-id="b42ac-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="b42ac-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="b42ac-122">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="b42ac-122">Set the Cancel property.</span></span>

## <span data-ttu-id="b42ac-123">成员</span><span class="sxs-lookup"><span data-stu-id="b42ac-123">Members</span></span>

#### <span data-ttu-id="b42ac-124">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="b42ac-124">get_Cancel</span></span> 

<span data-ttu-id="b42ac-125">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="b42ac-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="b42ac-126">公共 HRESULT [get_Cancel](#get_cancel) (BOOL \* Cancel) </span><span class="sxs-lookup"><span data-stu-id="b42ac-126">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="b42ac-127">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="b42ac-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="b42ac-128">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="b42ac-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="b42ac-129">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="b42ac-129">This means cookies can be set and used part of a request for the navigation.</span></span> <span data-ttu-id="b42ac-130">取消导航至 "关于"：不支持对 srcdoc 的空白或框架导航。</span><span class="sxs-lookup"><span data-stu-id="b42ac-130">Cancellation for navigation to about:blank or frame navigation to srcdoc is not supported.</span></span> <span data-ttu-id="b42ac-131">此类尝试将被忽略。</span><span class="sxs-lookup"><span data-stu-id="b42ac-131">Such attempts will be ignored.</span></span>

#### <span data-ttu-id="b42ac-132">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="b42ac-132">get_IsRedirected</span></span> 

<span data-ttu-id="b42ac-133">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="b42ac-133">True when the navigation is redirected.</span></span>

> <span data-ttu-id="b42ac-134">公共 HRESULT [get_IsRedirected](#get_isredirected) (BOOL \* IsRedirected) </span><span class="sxs-lookup"><span data-stu-id="b42ac-134">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="b42ac-135">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="b42ac-135">get_IsUserInitiated</span></span> 

<span data-ttu-id="b42ac-136">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="b42ac-136">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="b42ac-137">公共 HRESULT [get_IsUserInitiated](#get_isuserinitiated) (BOOL \* IsUserInitiated) </span><span class="sxs-lookup"><span data-stu-id="b42ac-137">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="b42ac-138">get_NavigationId</span><span class="sxs-lookup"><span data-stu-id="b42ac-138">get_NavigationId</span></span> 

<span data-ttu-id="b42ac-139">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="b42ac-139">The ID of the navigation.</span></span>

> <span data-ttu-id="b42ac-140">公共 HRESULT [get_NavigationId](#get_navigationid) (UINT64 \* NavigationId) </span><span class="sxs-lookup"><span data-stu-id="b42ac-140">public HRESULT [get_NavigationId](#get_navigationid)(UINT64 \* navigationId)</span></span>

#### <span data-ttu-id="b42ac-141">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="b42ac-141">get_RequestHeaders</span></span> 

<span data-ttu-id="b42ac-142">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="b42ac-142">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="b42ac-143">公共 HRESULT [get_RequestHeaders](#get_requestheaders) ([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* RequestHeaders) </span><span class="sxs-lookup"><span data-stu-id="b42ac-143">public HRESULT [get_RequestHeaders](#get_requestheaders)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="b42ac-144">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="b42ac-144">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="b42ac-145">get_Uri</span><span class="sxs-lookup"><span data-stu-id="b42ac-145">get_Uri</span></span> 

<span data-ttu-id="b42ac-146">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="b42ac-146">The uri of the requested navigation.</span></span>

> <span data-ttu-id="b42ac-147">公共 HRESULT [get_Uri](#get_uri) (LPWSTR \* Uri) </span><span class="sxs-lookup"><span data-stu-id="b42ac-147">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="b42ac-148">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="b42ac-148">put_Cancel</span></span> 

<span data-ttu-id="b42ac-149">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="b42ac-149">Set the Cancel property.</span></span>

> <span data-ttu-id="b42ac-150">public HRESULT [put_Cancel](#put_cancel) (BOOL Cancel) </span><span class="sxs-lookup"><span data-stu-id="b42ac-150">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

