---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5f63cd8a9dc16ee82d77fe4b5a0b705eb79e7c6f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010933"
---
# <span data-ttu-id="6f6ab-104">0.9.579-WebView2 的 CoreWebView2NavigationStartingEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="6f6ab-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2NavigationStartingEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="6f6ab-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="6f6ab-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="6f6ab-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="6f6ab-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="6f6ab-107">NavigationStarting 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-107">Event args for the NavigationStarting event.</span></span>

## <span data-ttu-id="6f6ab-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6f6ab-108">Summary</span></span>

 <span data-ttu-id="6f6ab-109">成员</span><span class="sxs-lookup"><span data-stu-id="6f6ab-109">Members</span></span>                        | <span data-ttu-id="6f6ab-110">描述</span><span class="sxs-lookup"><span data-stu-id="6f6ab-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6f6ab-111">取消</span><span class="sxs-lookup"><span data-stu-id="6f6ab-111">Cancel</span></span>](#cancel) | <span data-ttu-id="6f6ab-112">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-112">The host may set this flag to cancel the navigation.</span></span>
[<span data-ttu-id="6f6ab-113">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="6f6ab-113">IsRedirected</span></span>](#isredirected) | <span data-ttu-id="6f6ab-114">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-114">True when the navigation is redirected.</span></span>
[<span data-ttu-id="6f6ab-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6f6ab-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="6f6ab-116">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-116">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>
[<span data-ttu-id="6f6ab-117">NavigationId</span><span class="sxs-lookup"><span data-stu-id="6f6ab-117">NavigationId</span></span>](#navigationid) | <span data-ttu-id="6f6ab-118">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-118">The ID of the navigation.</span></span>
[<span data-ttu-id="6f6ab-119">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6f6ab-119">RequestHeaders</span></span>](#requestheaders) | <span data-ttu-id="6f6ab-120">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-120">The HTTP request headers for the navigation.</span></span>
[<span data-ttu-id="6f6ab-121">Uri</span><span class="sxs-lookup"><span data-stu-id="6f6ab-121">Uri</span></span>](#uri) | <span data-ttu-id="6f6ab-122">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-122">The uri of the requested navigation.</span></span>

## <span data-ttu-id="6f6ab-123">成员</span><span class="sxs-lookup"><span data-stu-id="6f6ab-123">Members</span></span>

#### <span data-ttu-id="6f6ab-124">取消</span><span class="sxs-lookup"><span data-stu-id="6f6ab-124">Cancel</span></span> 

<span data-ttu-id="6f6ab-125">主持人可以将此标志设置为取消导航。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-125">The host may set this flag to cancel the navigation.</span></span>

> <span data-ttu-id="6f6ab-126">公共 bool [取消](#cancel)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-126">public bool [Cancel](#cancel)</span></span>

<span data-ttu-id="6f6ab-127">如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-127">If set, it will be as if the navigation never happened and the current page's content will be intact.</span></span> <span data-ttu-id="6f6ab-128">出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-128">For performance reasons, GET HTTP requests may happen, while the host is responding.</span></span> <span data-ttu-id="6f6ab-129">这意味着可以在导航的请求中设置和使用 cookie。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-129">This means cookies can be set and used part of a request for the navigation.</span></span>

#### <span data-ttu-id="6f6ab-130">IsRedirected</span><span class="sxs-lookup"><span data-stu-id="6f6ab-130">IsRedirected</span></span> 

<span data-ttu-id="6f6ab-131">当导航被重定向时为 True。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-131">True when the navigation is redirected.</span></span>

> <span data-ttu-id="6f6ab-132">公共 bool [IsRedirected](#isredirected)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-132">public bool [IsRedirected](#isredirected)</span></span>

#### <span data-ttu-id="6f6ab-133">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6f6ab-133">IsUserInitiated</span></span> 

<span data-ttu-id="6f6ab-134">当导航是通过用户手势启动时（相对于编程导航）时，为 True。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-134">True when the navigation was initiated through a user gesture as opposed to programmatic navigation.</span></span>

> <span data-ttu-id="6f6ab-135">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-135">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="6f6ab-136">NavigationId</span><span class="sxs-lookup"><span data-stu-id="6f6ab-136">NavigationId</span></span> 

<span data-ttu-id="6f6ab-137">导航的 ID。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-137">The ID of the navigation.</span></span>

> <span data-ttu-id="6f6ab-138">公共 ulong [NavigationId](#navigationid)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-138">public ulong [NavigationId](#navigationid)</span></span>

#### <span data-ttu-id="6f6ab-139">RequestHeaders</span><span class="sxs-lookup"><span data-stu-id="6f6ab-139">RequestHeaders</span></span> 

<span data-ttu-id="6f6ab-140">导航的 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-140">The HTTP request headers for the navigation.</span></span>

> <span data-ttu-id="6f6ab-141">公共 HttpRequestHeaders [RequestHeaders](#requestheaders)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-141">public HttpRequestHeaders [RequestHeaders](#requestheaders)</span></span>

<span data-ttu-id="6f6ab-142">注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-142">Note, you cannot modify the HTTP request headers in a NavigationStarting event.</span></span>

#### <span data-ttu-id="6f6ab-143">Uri</span><span class="sxs-lookup"><span data-stu-id="6f6ab-143">Uri</span></span> 

<span data-ttu-id="6f6ab-144">所请求的导航的 uri。</span><span class="sxs-lookup"><span data-stu-id="6f6ab-144">The uri of the requested navigation.</span></span>

> <span data-ttu-id="6f6ab-145">公共字符串 [Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="6f6ab-145">public string [Uri](#uri)</span></span>

