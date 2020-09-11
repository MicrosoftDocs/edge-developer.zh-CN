---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceRequestedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 501483894a2abca58c5a1856ab587b93be904c8b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011656"
---
# <span data-ttu-id="75594-104">CoreWebView2WebResourceRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="75594-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

<span data-ttu-id="75594-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="75594-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="75594-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="75594-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="75594-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="75594-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="75594-108">摘要</span><span class="sxs-lookup"><span data-stu-id="75594-108">Summary</span></span>

 <span data-ttu-id="75594-109">成员</span><span class="sxs-lookup"><span data-stu-id="75594-109">Members</span></span>                        | <span data-ttu-id="75594-110">描述</span><span class="sxs-lookup"><span data-stu-id="75594-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="75594-111">请求</span><span class="sxs-lookup"><span data-stu-id="75594-111">Request</span></span>](#request) | <span data-ttu-id="75594-112">Web 资源请求。</span><span class="sxs-lookup"><span data-stu-id="75594-112">The Web resource request.</span></span>
[<span data-ttu-id="75594-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="75594-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="75594-114">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="75594-114">The web resource request context.</span></span>
[<span data-ttu-id="75594-115">响应</span><span class="sxs-lookup"><span data-stu-id="75594-115">Response</span></span>](#response) | <span data-ttu-id="75594-116">Web 资源响应对象的占位符。</span><span class="sxs-lookup"><span data-stu-id="75594-116">A placeholder for the web resource response object.</span></span>
[<span data-ttu-id="75594-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="75594-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="75594-118">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="75594-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="75594-119">成员</span><span class="sxs-lookup"><span data-stu-id="75594-119">Members</span></span>

#### <span data-ttu-id="75594-120">请求</span><span class="sxs-lookup"><span data-stu-id="75594-120">Request</span></span> 

<span data-ttu-id="75594-121">Web 资源请求。</span><span class="sxs-lookup"><span data-stu-id="75594-121">The Web resource request.</span></span>

> <span data-ttu-id="75594-122">公共 [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [请求](#request)</span><span class="sxs-lookup"><span data-stu-id="75594-122">public [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [Request](#request)</span></span>

<span data-ttu-id="75594-123">请求对象可能缺少某些标题，这些标题将在稍后的网络堆栈中添加。</span><span class="sxs-lookup"><span data-stu-id="75594-123">The request object may be missing some headers that are added by network stack later on.</span></span>

#### <span data-ttu-id="75594-124">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="75594-124">ResourceContext</span></span> 

<span data-ttu-id="75594-125">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="75594-125">The web resource request context.</span></span>

> <span data-ttu-id="75594-126">公共 [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="75594-126">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="75594-127">响应</span><span class="sxs-lookup"><span data-stu-id="75594-127">Response</span></span> 

<span data-ttu-id="75594-128">Web 资源响应对象的占位符。</span><span class="sxs-lookup"><span data-stu-id="75594-128">A placeholder for the web resource response object.</span></span>

> <span data-ttu-id="75594-129">公共 [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [响应](#response)</span><span class="sxs-lookup"><span data-stu-id="75594-129">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [Response](#response)</span></span>

<span data-ttu-id="75594-130">如果设置了此对象，将在此响应中完成 web 资源请求。</span><span class="sxs-lookup"><span data-stu-id="75594-130">If this object is set, the web resource request will be completed with this response.</span></span> <span data-ttu-id="75594-131">可以使用 CreateWebResourceResponse 创建空的 Web 资源响应对象，然后对其进行修改以构造响应。</span><span class="sxs-lookup"><span data-stu-id="75594-131">An empty Web resource response object can be created with CreateWebResourceResponse and then modified to construct the response.</span></span>

#### <span data-ttu-id="75594-132">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="75594-132">GetDeferral</span></span> 

<span data-ttu-id="75594-133">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="75594-133">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="75594-134">公共 [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral) ( # A1</span><span class="sxs-lookup"><span data-stu-id="75594-134">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="75594-135">你可以使用 CoreWebView2Deferral 对象在以后的时间完成该请求。</span><span class="sxs-lookup"><span data-stu-id="75594-135">You can use the CoreWebView2Deferral object to complete the request at a later time.</span></span>

