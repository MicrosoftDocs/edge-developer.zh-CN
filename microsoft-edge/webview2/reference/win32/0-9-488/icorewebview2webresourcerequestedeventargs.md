---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8cdedd8051f52b7f6ad187ec948eabef96c6670b
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652853"
---
# <span data-ttu-id="95505-104">interface ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="95505-104">interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="95505-105">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="95505-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="95505-106">摘要</span><span class="sxs-lookup"><span data-stu-id="95505-106">Summary</span></span>

 <span data-ttu-id="95505-107">成员</span><span class="sxs-lookup"><span data-stu-id="95505-107">Members</span></span>                        | <span data-ttu-id="95505-108">描述</span><span class="sxs-lookup"><span data-stu-id="95505-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="95505-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="95505-109">get_Request</span></span>](#get_request) | <span data-ttu-id="95505-110">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="95505-110">The HTTP request.</span></span>
[<span data-ttu-id="95505-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="95505-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="95505-112">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="95505-112">The web resource request contexts.</span></span>
[<span data-ttu-id="95505-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="95505-113">get_Response</span></span>](#get_response) | <span data-ttu-id="95505-114">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="95505-114">The HTTP response.</span></span>
[<span data-ttu-id="95505-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="95505-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="95505-116">获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="95505-116">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="95505-117">put_Response</span><span class="sxs-lookup"><span data-stu-id="95505-117">put_Response</span></span>](#put_response) | <span data-ttu-id="95505-118">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="95505-118">Set the Response property.</span></span>

## <span data-ttu-id="95505-119">成员</span><span class="sxs-lookup"><span data-stu-id="95505-119">Members</span></span>

#### <span data-ttu-id="95505-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="95505-120">get_Request</span></span> 

<span data-ttu-id="95505-121">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="95505-121">The HTTP request.</span></span>

> <span data-ttu-id="95505-122">公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="95505-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

#### <span data-ttu-id="95505-123">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="95505-123">get_ResourceContext</span></span> 

<span data-ttu-id="95505-124">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="95505-124">The web resource request contexts.</span></span>

> <span data-ttu-id="95505-125">公共 HRESULT [get_ResourceContext](#get_resourcecontext)（COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文）</span><span class="sxs-lookup"><span data-stu-id="95505-125">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="95505-126">get_Response</span><span class="sxs-lookup"><span data-stu-id="95505-126">get_Response</span></span> 

<span data-ttu-id="95505-127">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="95505-127">The HTTP response.</span></span>

> <span data-ttu-id="95505-128">公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="95505-128">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

#### <span data-ttu-id="95505-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="95505-129">GetDeferral</span></span> 

<span data-ttu-id="95505-130">获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="95505-130">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="95505-131">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="95505-131">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="95505-132">你可以使用[ICoreWebView2Deferral](icorewebview2deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="95505-132">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the network request at a later time.</span></span>

#### <span data-ttu-id="95505-133">put_Response</span><span class="sxs-lookup"><span data-stu-id="95505-133">put_Response</span></span> 

<span data-ttu-id="95505-134">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="95505-134">Set the Response property.</span></span>

> <span data-ttu-id="95505-135">公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="95505-135">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

