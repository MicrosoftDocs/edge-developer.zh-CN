---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 9210a4b70d0e2edf30cbaad906f57b360688dfe8
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652887"
---
# <span data-ttu-id="8106b-104">CoreWebView2WebResourceRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="8106b-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

<span data-ttu-id="8106b-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="8106b-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8106b-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="8106b-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8106b-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="8106b-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="8106b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="8106b-108">Summary</span></span>

 <span data-ttu-id="8106b-109">成员</span><span class="sxs-lookup"><span data-stu-id="8106b-109">Members</span></span>                        | <span data-ttu-id="8106b-110">描述</span><span class="sxs-lookup"><span data-stu-id="8106b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8106b-111">请求</span><span class="sxs-lookup"><span data-stu-id="8106b-111">Request</span></span>](#request) | <span data-ttu-id="8106b-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="8106b-112">The HTTP request.</span></span>
[<span data-ttu-id="8106b-113">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="8106b-113">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="8106b-114">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="8106b-114">The web resource request contexts.</span></span>
[<span data-ttu-id="8106b-115">响应</span><span class="sxs-lookup"><span data-stu-id="8106b-115">Response</span></span>](#response) | <span data-ttu-id="8106b-116">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="8106b-116">The HTTP response.</span></span>
[<span data-ttu-id="8106b-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8106b-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="8106b-118">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="8106b-118">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="8106b-119">成员</span><span class="sxs-lookup"><span data-stu-id="8106b-119">Members</span></span>

#### <span data-ttu-id="8106b-120">请求</span><span class="sxs-lookup"><span data-stu-id="8106b-120">Request</span></span> 

<span data-ttu-id="8106b-121">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="8106b-121">The HTTP request.</span></span>

> <span data-ttu-id="8106b-122">公共 HttpRequestMessage[请求](#request)</span><span class="sxs-lookup"><span data-stu-id="8106b-122">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="8106b-123">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="8106b-123">ResourceContext</span></span> 

<span data-ttu-id="8106b-124">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="8106b-124">The web resource request contexts.</span></span>

> <span data-ttu-id="8106b-125">公共[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="8106b-125">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="8106b-126">响应</span><span class="sxs-lookup"><span data-stu-id="8106b-126">Response</span></span> 

<span data-ttu-id="8106b-127">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="8106b-127">The HTTP response.</span></span>

> <span data-ttu-id="8106b-128">公共 HttpResponseMessage[响应](#response)</span><span class="sxs-lookup"><span data-stu-id="8106b-128">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="8106b-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="8106b-129">GetDeferral</span></span> 

<span data-ttu-id="8106b-130">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="8106b-130">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="8106b-131">公共[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="8106b-131">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="8106b-132">你可以使用 CoreWebView2Deferral 对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="8106b-132">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

