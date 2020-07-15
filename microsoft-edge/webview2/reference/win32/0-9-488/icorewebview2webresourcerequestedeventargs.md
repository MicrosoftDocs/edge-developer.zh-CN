---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 70a7d997dfd89b6d9bb8eb8af9a87ff0a130b69f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880302"
---
# <span data-ttu-id="6b35b-104">0.9.515-接口 ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6b35b-104">0.9.515 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="6b35b-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="6b35b-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="6b35b-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="6b35b-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="6b35b-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6b35b-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="6b35b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6b35b-108">Summary</span></span>

 <span data-ttu-id="6b35b-109">成员</span><span class="sxs-lookup"><span data-stu-id="6b35b-109">Members</span></span>                        | <span data-ttu-id="6b35b-110">描述</span><span class="sxs-lookup"><span data-stu-id="6b35b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6b35b-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="6b35b-111">get_Request</span></span>](#get_request) | <span data-ttu-id="6b35b-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="6b35b-112">The HTTP request.</span></span>
[<span data-ttu-id="6b35b-113">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="6b35b-113">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="6b35b-114">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="6b35b-114">The web resource request contexts.</span></span>
[<span data-ttu-id="6b35b-115">get_Response</span><span class="sxs-lookup"><span data-stu-id="6b35b-115">get_Response</span></span>](#get_response) | <span data-ttu-id="6b35b-116">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="6b35b-116">The HTTP response.</span></span>
[<span data-ttu-id="6b35b-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6b35b-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="6b35b-118">获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="6b35b-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="6b35b-119">put_Response</span><span class="sxs-lookup"><span data-stu-id="6b35b-119">put_Response</span></span>](#put_response) | <span data-ttu-id="6b35b-120">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="6b35b-120">Set the Response property.</span></span>

## <span data-ttu-id="6b35b-121">成员</span><span class="sxs-lookup"><span data-stu-id="6b35b-121">Members</span></span>

#### <span data-ttu-id="6b35b-122">get_Request</span><span class="sxs-lookup"><span data-stu-id="6b35b-122">get_Request</span></span> 

<span data-ttu-id="6b35b-123">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="6b35b-123">The HTTP request.</span></span>

> <span data-ttu-id="6b35b-124">公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="6b35b-124">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="6b35b-125">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="6b35b-125">get_ResourceContext</span></span> 

<span data-ttu-id="6b35b-126">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="6b35b-126">The web resource request contexts.</span></span>

> <span data-ttu-id="6b35b-127">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="6b35b-127">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="6b35b-128">get_Response</span><span class="sxs-lookup"><span data-stu-id="6b35b-128">get_Response</span></span> 

<span data-ttu-id="6b35b-129">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="6b35b-129">The HTTP response.</span></span>

> <span data-ttu-id="6b35b-130">公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="6b35b-130">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

#### <span data-ttu-id="6b35b-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6b35b-131">GetDeferral</span></span> 

<span data-ttu-id="6b35b-132">获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="6b35b-132">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="6b35b-133">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="6b35b-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="6b35b-134">你可以使用[ICoreWebView2Deferral](icorewebview2deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="6b35b-134">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="6b35b-135">put_Response</span><span class="sxs-lookup"><span data-stu-id="6b35b-135">put_Response</span></span> 

<span data-ttu-id="6b35b-136">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="6b35b-136">Set the Response property.</span></span>

> <span data-ttu-id="6b35b-137">公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="6b35b-137">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

