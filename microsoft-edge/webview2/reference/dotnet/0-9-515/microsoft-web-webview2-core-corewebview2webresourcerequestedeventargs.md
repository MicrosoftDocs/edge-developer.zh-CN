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
ms.openlocfilehash: 072ce10e7ac1f34238278366c3e8799a3268cb0b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697530"
---
# <span data-ttu-id="09414-104">CoreWebView2WebResourceRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="09414-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="09414-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="09414-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="09414-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="09414-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="09414-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="09414-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="09414-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="09414-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="09414-109">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="09414-109">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="09414-110">摘要</span><span class="sxs-lookup"><span data-stu-id="09414-110">Summary</span></span>

 <span data-ttu-id="09414-111">成员</span><span class="sxs-lookup"><span data-stu-id="09414-111">Members</span></span>                        | <span data-ttu-id="09414-112">描述</span><span class="sxs-lookup"><span data-stu-id="09414-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="09414-113">请求</span><span class="sxs-lookup"><span data-stu-id="09414-113">Request</span></span>](#request) | <span data-ttu-id="09414-114">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="09414-114">The HTTP request.</span></span>
[<span data-ttu-id="09414-115">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="09414-115">ResourceContext</span></span>](#resourcecontext) | <span data-ttu-id="09414-116">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="09414-116">The web resource request contexts.</span></span>
[<span data-ttu-id="09414-117">响应</span><span class="sxs-lookup"><span data-stu-id="09414-117">Response</span></span>](#response) | <span data-ttu-id="09414-118">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="09414-118">The HTTP response.</span></span>
[<span data-ttu-id="09414-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="09414-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="09414-120">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="09414-120">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

## <span data-ttu-id="09414-121">成员</span><span class="sxs-lookup"><span data-stu-id="09414-121">Members</span></span>

#### <span data-ttu-id="09414-122">请求</span><span class="sxs-lookup"><span data-stu-id="09414-122">Request</span></span> 

<span data-ttu-id="09414-123">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="09414-123">The HTTP request.</span></span>

> <span data-ttu-id="09414-124">公共 HttpRequestMessage[请求](#request)</span><span class="sxs-lookup"><span data-stu-id="09414-124">public HttpRequestMessage [Request](#request)</span></span>

#### <span data-ttu-id="09414-125">ResourceContext</span><span class="sxs-lookup"><span data-stu-id="09414-125">ResourceContext</span></span> 

<span data-ttu-id="09414-126">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="09414-126">The web resource request contexts.</span></span>

> <span data-ttu-id="09414-127">公共[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span><span class="sxs-lookup"><span data-stu-id="09414-127">public [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)</span></span>

#### <span data-ttu-id="09414-128">响应</span><span class="sxs-lookup"><span data-stu-id="09414-128">Response</span></span> 

<span data-ttu-id="09414-129">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="09414-129">The HTTP response.</span></span>

> <span data-ttu-id="09414-130">公共 HttpResponseMessage[响应](#response)</span><span class="sxs-lookup"><span data-stu-id="09414-130">public HttpResponseMessage [Response](#response)</span></span>

#### <span data-ttu-id="09414-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="09414-131">GetDeferral</span></span> 

<span data-ttu-id="09414-132">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="09414-132">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="09414-133">公共[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="09414-133">public [CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="09414-134">你可以使用 CoreWebView2Deferral 对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="09414-134">You can use the CoreWebView2Deferral object to complete the network request at a later time.</span></span>

