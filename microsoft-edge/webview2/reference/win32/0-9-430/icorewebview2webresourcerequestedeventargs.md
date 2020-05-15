---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 59557ca86e8b044fb937fe93b3060c0879abb6f1
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653133"
---
# <span data-ttu-id="ea177-104">interface ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ea177-104">interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="ea177-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="ea177-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="ea177-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="ea177-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="ea177-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ea177-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="ea177-108">摘要</span><span class="sxs-lookup"><span data-stu-id="ea177-108">Summary</span></span>

 <span data-ttu-id="ea177-109">成员</span><span class="sxs-lookup"><span data-stu-id="ea177-109">Members</span></span>                        | <span data-ttu-id="ea177-110">描述</span><span class="sxs-lookup"><span data-stu-id="ea177-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ea177-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="ea177-111">get_Request</span></span>](#get_request) | <span data-ttu-id="ea177-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="ea177-112">The HTTP request.</span></span>
[<span data-ttu-id="ea177-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="ea177-113">get_Response</span></span>](#get_response) | <span data-ttu-id="ea177-114">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="ea177-114">The HTTP response.</span></span>
[<span data-ttu-id="ea177-115">put_Response</span><span class="sxs-lookup"><span data-stu-id="ea177-115">put_Response</span></span>](#put_response) | <span data-ttu-id="ea177-116">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="ea177-116">Set the Response property.</span></span>
[<span data-ttu-id="ea177-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ea177-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="ea177-118">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="ea177-118">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="ea177-119">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ea177-119">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="ea177-120">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="ea177-120">The web resource request contexts.</span></span>

## <span data-ttu-id="ea177-121">成员</span><span class="sxs-lookup"><span data-stu-id="ea177-121">Members</span></span>

#### <span data-ttu-id="ea177-122">get_Request</span><span class="sxs-lookup"><span data-stu-id="ea177-122">get_Request</span></span> 

<span data-ttu-id="ea177-123">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="ea177-123">The HTTP request.</span></span>

> <span data-ttu-id="ea177-124">公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="ea177-124">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="ea177-125">get_Response</span><span class="sxs-lookup"><span data-stu-id="ea177-125">get_Response</span></span> 

<span data-ttu-id="ea177-126">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="ea177-126">The HTTP response.</span></span>

> <span data-ttu-id="ea177-127">公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="ea177-127">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="ea177-128">put_Response</span><span class="sxs-lookup"><span data-stu-id="ea177-128">put_Response</span></span> 

<span data-ttu-id="ea177-129">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="ea177-129">Set the Response property.</span></span>

> <span data-ttu-id="ea177-130">公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="ea177-130">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="ea177-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="ea177-131">GetDeferral</span></span> 

<span data-ttu-id="ea177-132">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="ea177-132">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="ea177-133">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="ea177-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="ea177-134">你可以使用[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="ea177-134">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="ea177-135">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="ea177-135">get_ResourceContext</span></span> 

<span data-ttu-id="ea177-136">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="ea177-136">The web resource request contexts.</span></span>

> <span data-ttu-id="ea177-137">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="ea177-137">public HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

