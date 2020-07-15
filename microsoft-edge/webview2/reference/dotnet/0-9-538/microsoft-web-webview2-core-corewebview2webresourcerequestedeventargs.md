---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2WebResourceRequestedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 53cc31bc714417ab902fa8fdef9fd83f80871f10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879665"
---
# <span data-ttu-id="f76ba-104">CoreWebView2WebResourceRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="f76ba-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

<span data-ttu-id="f76ba-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="f76ba-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f76ba-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="f76ba-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f76ba-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f76ba-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="f76ba-108">摘要</span><span class="sxs-lookup"><span data-stu-id="f76ba-108">Summary</span></span>

 <span data-ttu-id="f76ba-109">成员</span><span class="sxs-lookup"><span data-stu-id="f76ba-109">Members</span></span>                        | <span data-ttu-id="f76ba-110">描述</span><span class="sxs-lookup"><span data-stu-id="f76ba-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f76ba-111">请求</span><span class="sxs-lookup"><span data-stu-id="f76ba-111">Request</span></span>](#request) | <span data-ttu-id="f76ba-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="f76ba-112">The HTTP request.</span></span>
[<span data-ttu-id="f76ba-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="f76ba-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="f76ba-114">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="f76ba-114">The web resource request contexts.</span></span>
[<span data-ttu-id="f76ba-115">响应</span><span class="sxs-lookup"><span data-stu-id="f76ba-115">Response</span></span>](#response) | <span data-ttu-id="f76ba-116">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="f76ba-116">The HTTP response.</span></span>
[<span data-ttu-id="f76ba-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="f76ba-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="f76ba-118">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="f76ba-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="f76ba-119">成员</span><span class="sxs-lookup"><span data-stu-id="f76ba-119">Members</span></span>

#### <span data-ttu-id="f76ba-120">请求</span><span class="sxs-lookup"><span data-stu-id="f76ba-120">Request</span></span> 

<span data-ttu-id="f76ba-121">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="f76ba-121">The HTTP request.</span></span>

> <span data-ttu-id="f76ba-122">公共 HttpRequestMessage[请求](#request)</span><span class="sxs-lookup"><span data-stu-id="f76ba-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="f76ba-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="f76ba-123">ResourceContext</span></span> 

<span data-ttu-id="f76ba-124">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="f76ba-124">The web resource request contexts.</span></span>

> <span data-ttu-id="f76ba-125">公共[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="f76ba-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="f76ba-126">响应</span><span class="sxs-lookup"><span data-stu-id="f76ba-126">Response</span></span> 

<span data-ttu-id="f76ba-127">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="f76ba-127">The HTTP response.</span></span>

> <span data-ttu-id="f76ba-128">公共 HttpResponseMessage[响应](#response)</span><span class="sxs-lookup"><span data-stu-id="f76ba-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="f76ba-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="f76ba-129">GetDeferral</span></span> 

<span data-ttu-id="f76ba-130">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="f76ba-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="f76ba-131">公共[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="f76ba-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="f76ba-132">你可以使用 CoreWebView2Deferral 对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="f76ba-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

