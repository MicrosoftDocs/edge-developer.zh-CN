---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 8bc625d12cc3b3ebe06970fd282dd8f60bcabd22
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878398"
---
# <span data-ttu-id="0dc9e-104">0.8.355-接口 IWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="0dc9e-104">0.8.355 - interface IWebView2NavigationStartingEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="0dc9e-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="0dc9e-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="0dc9e-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="0dc9e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0dc9e-108">Summary</span></span>

 <span data-ttu-id="0dc9e-109">成员</span><span class="sxs-lookup"><span data-stu-id="0dc9e-109">Members</span></span>                        | <span data-ttu-id="0dc9e-110">描述</span><span class="sxs-lookup"><span data-stu-id="0dc9e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0dc9e-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0dc9e-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="0dc9e-112">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-112">The uri of the requested navigation.</span></span>
[<span data-ttu-id="0dc9e-113">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="0dc9e-113">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="0dc9e-114">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-114">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="0dc9e-115">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="0dc9e-115">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="0dc9e-116">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-116">True when the navigation is redirected.</span></span>
[<span data-ttu-id="0dc9e-117">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="0dc9e-117">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="0dc9e-118">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-118">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="0dc9e-119">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="0dc9e-119">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="0dc9e-120">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-120">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="0dc9e-121">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="0dc9e-121">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="0dc9e-122">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-122">Set the Cancel property.</span></span>

## <span data-ttu-id="0dc9e-123">成员</span><span class="sxs-lookup"><span data-stu-id="0dc9e-123">Members</span></span>

#### <span data-ttu-id="0dc9e-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0dc9e-124">get_Uri</span></span> 

<span data-ttu-id="0dc9e-125">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-125">The uri of the requested navigation.</span></span>

> <span data-ttu-id="0dc9e-126">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="0dc9e-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="0dc9e-127">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="0dc9e-127">get_IsUserInitiated</span></span> 

<span data-ttu-id="0dc9e-128">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-128">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="0dc9e-129">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="0dc9e-129">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="0dc9e-130">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="0dc9e-130">get_IsRedirected</span></span> 

<span data-ttu-id="0dc9e-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="0dc9e-132">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="0dc9e-132">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="0dc9e-133">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="0dc9e-133">get_RequestHeaders</span></span> 

<span data-ttu-id="0dc9e-134">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-134">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="0dc9e-135">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="0dc9e-135">public HRESULT [get_RequestHeaders](#get_requestheaders)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="0dc9e-136">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-136">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="0dc9e-137">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="0dc9e-137">get_Cancel</span></span> 

<span data-ttu-id="0dc9e-138">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-138">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="0dc9e-139">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="0dc9e-139">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="0dc9e-140">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-140">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="0dc9e-141">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-141">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="0dc9e-142">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-142">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="0dc9e-143">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="0dc9e-143">put_Cancel</span></span> 

<span data-ttu-id="0dc9e-144">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="0dc9e-144">Set the Cancel property.</span></span>

> <span data-ttu-id="0dc9e-145">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="0dc9e-145">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

