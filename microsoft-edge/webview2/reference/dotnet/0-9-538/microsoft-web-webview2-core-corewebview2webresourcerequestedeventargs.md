---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 2282b36d3b7dfcca83f84ed50a976d4e6622ce07
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010122"
---
# <span data-ttu-id="7f363-104">0.9.579-WebView2 的 CoreWebView2WebResourceRequestedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="7f363-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="7f363-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="7f363-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="7f363-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="7f363-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="7f363-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7f363-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="7f363-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7f363-108">Summary</span></span>

 <span data-ttu-id="7f363-109">成员</span><span class="sxs-lookup"><span data-stu-id="7f363-109">Members</span></span>                        | <span data-ttu-id="7f363-110">描述</span><span class="sxs-lookup"><span data-stu-id="7f363-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7f363-111">请求</span><span class="sxs-lookup"><span data-stu-id="7f363-111">Request</span></span>](#request) | <span data-ttu-id="7f363-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="7f363-112">The HTTP request.</span></span>
[<span data-ttu-id="7f363-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="7f363-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="7f363-114">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="7f363-114">The web resource request contexts.</span></span>
[<span data-ttu-id="7f363-115">响应</span><span class="sxs-lookup"><span data-stu-id="7f363-115">Response</span></span>](#response) | <span data-ttu-id="7f363-116">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="7f363-116">The HTTP response.</span></span>
[<span data-ttu-id="7f363-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="7f363-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="7f363-118">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="7f363-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="7f363-119">成员</span><span class="sxs-lookup"><span data-stu-id="7f363-119">Members</span></span>

#### <span data-ttu-id="7f363-120">请求</span><span class="sxs-lookup"><span data-stu-id="7f363-120">Request</span></span> 

<span data-ttu-id="7f363-121">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="7f363-121">The HTTP request.</span></span>

> <span data-ttu-id="7f363-122">公共 HttpRequestMessage [请求](#request)</span><span class="sxs-lookup"><span data-stu-id="7f363-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="7f363-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="7f363-123">ResourceContext</span></span> 

<span data-ttu-id="7f363-124">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="7f363-124">The web resource request contexts.</span></span>

> <span data-ttu-id="7f363-125">公共 [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="7f363-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="7f363-126">响应</span><span class="sxs-lookup"><span data-stu-id="7f363-126">Response</span></span> 

<span data-ttu-id="7f363-127">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="7f363-127">The HTTP response.</span></span>

> <span data-ttu-id="7f363-128">公共 HttpResponseMessage [响应](#response)</span><span class="sxs-lookup"><span data-stu-id="7f363-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="7f363-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="7f363-129">GetDeferral</span></span> 

<span data-ttu-id="7f363-130">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="7f363-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="7f363-131">公共 [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral) ( # A1</span><span class="sxs-lookup"><span data-stu-id="7f363-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="7f363-132">你可以使用 CoreWebView2Deferral 对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="7f363-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

