---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 826cdf960a20e32b8e0fa6b5a8ddad720ac137a6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877579"
---
# <span data-ttu-id="fb71a-104">0.9.430-接口 ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fb71a-104">0.9.430 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="fb71a-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="fb71a-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="fb71a-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="fb71a-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="fb71a-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fb71a-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="fb71a-108">摘要</span><span class="sxs-lookup"><span data-stu-id="fb71a-108">Summary</span></span>

 <span data-ttu-id="fb71a-109">成员</span><span class="sxs-lookup"><span data-stu-id="fb71a-109">Members</span></span>                        | <span data-ttu-id="fb71a-110">描述</span><span class="sxs-lookup"><span data-stu-id="fb71a-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fb71a-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="fb71a-111">get_Request</span></span>](#get_request) | <span data-ttu-id="fb71a-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="fb71a-112">The HTTP request.</span></span>
[<span data-ttu-id="fb71a-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="fb71a-113">get_Response</span></span>](#get_response) | <span data-ttu-id="fb71a-114">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="fb71a-114">The HTTP response.</span></span>
[<span data-ttu-id="fb71a-115">put_Response</span><span class="sxs-lookup"><span data-stu-id="fb71a-115">put_Response</span></span>](#put_response) | <span data-ttu-id="fb71a-116">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="fb71a-116">Set the Response property.</span></span>
[<span data-ttu-id="fb71a-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="fb71a-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="fb71a-118">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="fb71a-118">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="fb71a-119">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="fb71a-119">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="fb71a-120">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="fb71a-120">The web resource request contexts.</span></span>

## <span data-ttu-id="fb71a-121">成员</span><span class="sxs-lookup"><span data-stu-id="fb71a-121">Members</span></span>

#### <span data-ttu-id="fb71a-122">get_Request</span><span class="sxs-lookup"><span data-stu-id="fb71a-122">get_Request</span></span> 

<span data-ttu-id="fb71a-123">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="fb71a-123">The HTTP request.</span></span>

> <span data-ttu-id="fb71a-124">公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="fb71a-124">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="fb71a-125">get_Response</span><span class="sxs-lookup"><span data-stu-id="fb71a-125">get_Response</span></span> 

<span data-ttu-id="fb71a-126">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="fb71a-126">The HTTP response.</span></span>

> <span data-ttu-id="fb71a-127">公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="fb71a-127">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="fb71a-128">put_Response</span><span class="sxs-lookup"><span data-stu-id="fb71a-128">put_Response</span></span> 

<span data-ttu-id="fb71a-129">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="fb71a-129">Set the Response property.</span></span>

> <span data-ttu-id="fb71a-130">公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="fb71a-130">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="fb71a-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="fb71a-131">GetDeferral</span></span> 

<span data-ttu-id="fb71a-132">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="fb71a-132">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="fb71a-133">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="fb71a-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="fb71a-134">你可以使用[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="fb71a-134">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="fb71a-135">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="fb71a-135">get_ResourceContext</span></span> 

<span data-ttu-id="fb71a-136">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="fb71a-136">The web resource request contexts.</span></span>

> <span data-ttu-id="fb71a-137">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="fb71a-137">public HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

