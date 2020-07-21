---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 00aaddcc732076e4f7aa808b04132641fe7fe969
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886442"
---
# <span data-ttu-id="39097-104">0.9.430-接口 ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="39097-104">0.9.430 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="39097-105">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="39097-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="39097-106">摘要</span><span class="sxs-lookup"><span data-stu-id="39097-106">Summary</span></span>

 <span data-ttu-id="39097-107">成员</span><span class="sxs-lookup"><span data-stu-id="39097-107">Members</span></span>                        | <span data-ttu-id="39097-108">描述</span><span class="sxs-lookup"><span data-stu-id="39097-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="39097-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="39097-109">get_Request</span></span>](#get_request) | <span data-ttu-id="39097-110">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="39097-110">The HTTP request.</span></span>
[<span data-ttu-id="39097-111">get_Response</span><span class="sxs-lookup"><span data-stu-id="39097-111">get_Response</span></span>](#get_response) | <span data-ttu-id="39097-112">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="39097-112">The HTTP response.</span></span>
[<span data-ttu-id="39097-113">put_Response</span><span class="sxs-lookup"><span data-stu-id="39097-113">put_Response</span></span>](#put_response) | <span data-ttu-id="39097-114">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="39097-114">Set the Response property.</span></span>
[<span data-ttu-id="39097-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="39097-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="39097-116">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="39097-116">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="39097-117">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="39097-117">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="39097-118">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="39097-118">The web resource request contexts.</span></span>

## <span data-ttu-id="39097-119">成员</span><span class="sxs-lookup"><span data-stu-id="39097-119">Members</span></span>

#### <span data-ttu-id="39097-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="39097-120">get_Request</span></span> 

<span data-ttu-id="39097-121">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="39097-121">The HTTP request.</span></span>

> <span data-ttu-id="39097-122">公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="39097-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="39097-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="39097-123">get_Response</span></span> 

<span data-ttu-id="39097-124">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="39097-124">The HTTP response.</span></span>

> <span data-ttu-id="39097-125">公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="39097-125">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="39097-126">put_Response</span><span class="sxs-lookup"><span data-stu-id="39097-126">put_Response</span></span> 

<span data-ttu-id="39097-127">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="39097-127">Set the Response property.</span></span>

> <span data-ttu-id="39097-128">公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="39097-128">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="39097-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="39097-129">GetDeferral</span></span> 

<span data-ttu-id="39097-130">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="39097-130">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="39097-131">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="39097-131">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="39097-132">你可以使用[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="39097-132">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="39097-133">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="39097-133">get_ResourceContext</span></span> 

<span data-ttu-id="39097-134">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="39097-134">The web resource request contexts.</span></span>

> <span data-ttu-id="39097-135">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="39097-135">public HRESULT [get_ResourceContext](#get_resourcecontext)(CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

