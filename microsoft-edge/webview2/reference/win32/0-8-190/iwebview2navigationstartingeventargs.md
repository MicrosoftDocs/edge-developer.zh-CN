---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 5996f0eff4db17530750eb39c7693ea0f8496a4d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885883"
---
# <span data-ttu-id="5047f-104">0.8.355-接口 IWebView2NavigationStartingEventArgs</span><span class="sxs-lookup"><span data-stu-id="5047f-104">0.8.355 - interface IWebView2NavigationStartingEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationStartingEventArgs
  : public IUnknown
```

<span data-ttu-id="5047f-105">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5047f-105">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="5047f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="5047f-106">Summary</span></span>

 <span data-ttu-id="5047f-107">成员</span><span class="sxs-lookup"><span data-stu-id="5047f-107">Members</span></span>                        | <span data-ttu-id="5047f-108">描述</span><span class="sxs-lookup"><span data-stu-id="5047f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5047f-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="5047f-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="5047f-110">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="5047f-110">The uri of the requested navigation.</span></span>
[<span data-ttu-id="5047f-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5047f-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="5047f-112">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="5047f-112">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="5047f-113">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="5047f-113">get_IsRedirected</span></span>](#get_isredirected) | <span data-ttu-id="5047f-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="5047f-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="5047f-115">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="5047f-115">get_RequestHeaders</span></span>](#get_requestheaders) | <span data-ttu-id="5047f-116">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="5047f-116">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="5047f-117">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="5047f-117">get_Cancel</span></span>](#get_cancel) | <span data-ttu-id="5047f-118">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="5047f-118">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="5047f-119">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="5047f-119">put_Cancel</span></span>](#put_cancel) | <span data-ttu-id="5047f-120">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="5047f-120">Set the Cancel property.</span></span>

## <span data-ttu-id="5047f-121">成员</span><span class="sxs-lookup"><span data-stu-id="5047f-121">Members</span></span>

#### <span data-ttu-id="5047f-122">get_Uri</span><span class="sxs-lookup"><span data-stu-id="5047f-122">get_Uri</span></span> 

<span data-ttu-id="5047f-123">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="5047f-123">The uri of the requested navigation.</span></span>

> <span data-ttu-id="5047f-124">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="5047f-124">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="5047f-125">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5047f-125">get_IsUserInitiated</span></span> 

<span data-ttu-id="5047f-126">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="5047f-126">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="5047f-127">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="5047f-127">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="5047f-128">get_IsRedirected</span><span class="sxs-lookup"><span data-stu-id="5047f-128">get_IsRedirected</span></span> 

<span data-ttu-id="5047f-129">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="5047f-129">True when the navigation is redirected.</span></span>

> <span data-ttu-id="5047f-130">public HRESULT [get_IsRedirected](#get_isredirected)（BOOL \* IsRedirected）</span><span class="sxs-lookup"><span data-stu-id="5047f-130">public HRESULT [get_IsRedirected](#get_isredirected)(BOOL \* isRedirected)</span></span>

#### <span data-ttu-id="5047f-131">get_RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="5047f-131">get_RequestHeaders</span></span> 

<span data-ttu-id="5047f-132">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="5047f-132">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="5047f-133">公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* RequestHeaders）</span><span class="sxs-lookup"><span data-stu-id="5047f-133">public HRESULT [get_RequestHeaders](#get_requestheaders)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* requestHeaders)</span></span>

<span data-ttu-id="5047f-134">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="5047f-134">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="5047f-135">get_Cancel</span><span class="sxs-lookup"><span data-stu-id="5047f-135">get_Cancel</span></span> 

<span data-ttu-id="5047f-136">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="5047f-136">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="5047f-137">公共 HRESULT [get_Cancel](#get_cancel)（BOOL \* 取消）</span><span class="sxs-lookup"><span data-stu-id="5047f-137">public HRESULT [get_Cancel](#get_cancel)(BOOL \* cancel)</span></span>

<span data-ttu-id="5047f-138">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="5047f-138">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="5047f-139">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="5047f-139">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="5047f-140">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="5047f-140">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="5047f-141">put_Cancel</span><span class="sxs-lookup"><span data-stu-id="5047f-141">put_Cancel</span></span> 

<span data-ttu-id="5047f-142">设置 "取消" 属性。</span><span class="sxs-lookup"><span data-stu-id="5047f-142">Set the Cancel property.</span></span>

> <span data-ttu-id="5047f-143">公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）</span><span class="sxs-lookup"><span data-stu-id="5047f-143">public HRESULT [put_Cancel](#put_cancel)(BOOL cancel)</span></span>

