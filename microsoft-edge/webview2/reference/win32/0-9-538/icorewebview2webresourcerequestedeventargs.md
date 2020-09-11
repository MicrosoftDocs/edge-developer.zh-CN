---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceRequestedEventArgs
ms.openlocfilehash: 2e55a43282a7548acefdb0b1ed1b8cac2254ef21
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010388"
---
# <span data-ttu-id="865e5-104">0.9.579-接口 ICoreWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="865e5-104">0.9.579 - interface ICoreWebView2WebResourceRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="865e5-105">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="865e5-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="865e5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="865e5-106">Summary</span></span>

 <span data-ttu-id="865e5-107">成员</span><span class="sxs-lookup"><span data-stu-id="865e5-107">Members</span></span>                        | <span data-ttu-id="865e5-108">描述</span><span class="sxs-lookup"><span data-stu-id="865e5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="865e5-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="865e5-109">get_Request</span></span>](#get_request) | <span data-ttu-id="865e5-110">Web 资源请求。</span><span class="sxs-lookup"><span data-stu-id="865e5-110">The Web resource request.</span></span>
[<span data-ttu-id="865e5-111">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="865e5-111">get_ResourceContext</span></span>](#get_resourcecontext) | <span data-ttu-id="865e5-112">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="865e5-112">The web resource request context.</span></span>
[<span data-ttu-id="865e5-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="865e5-113">get_Response</span></span>](#get_response) | <span data-ttu-id="865e5-114">Web 资源响应对象的占位符。</span><span class="sxs-lookup"><span data-stu-id="865e5-114">A placeholder for the web resource response object.</span></span>
[<span data-ttu-id="865e5-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="865e5-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="865e5-116">获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="865e5-116">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="865e5-117">put_Response</span><span class="sxs-lookup"><span data-stu-id="865e5-117">put_Response</span></span>](#put_response) | <span data-ttu-id="865e5-118">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="865e5-118">Set the Response property.</span></span>

## <span data-ttu-id="865e5-119">成员</span><span class="sxs-lookup"><span data-stu-id="865e5-119">Members</span></span>

#### <span data-ttu-id="865e5-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="865e5-120">get_Request</span></span> 

<span data-ttu-id="865e5-121">Web 资源请求。</span><span class="sxs-lookup"><span data-stu-id="865e5-121">The Web resource request.</span></span>

> <span data-ttu-id="865e5-122">公共 HRESULT [get_Request](#get_request) ([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \* \* 请求) </span><span class="sxs-lookup"><span data-stu-id="865e5-122">public HRESULT [get_Request](#get_request)([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) \*\* request)</span></span>

<span data-ttu-id="865e5-123">请求对象可能缺少某些标题，这些标题将在稍后的网络堆栈中添加。</span><span class="sxs-lookup"><span data-stu-id="865e5-123">The request object may be missing some headers that are added by network stack later on.</span></span>

#### <span data-ttu-id="865e5-124">get_ResourceContext</span><span class="sxs-lookup"><span data-stu-id="865e5-124">get_ResourceContext</span></span> 

<span data-ttu-id="865e5-125">Web 资源请求上下文。</span><span class="sxs-lookup"><span data-stu-id="865e5-125">The web resource request context.</span></span>

> <span data-ttu-id="865e5-126">公共 HRESULT [get_ResourceContext](#get_resourcecontext) (COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* 上下文) </span><span class="sxs-lookup"><span data-stu-id="865e5-126">public HRESULT [get_ResourceContext](#get_resourcecontext)(COREWEBVIEW2_WEB_RESOURCE_CONTEXT \* context)</span></span>

#### <span data-ttu-id="865e5-127">get_Response</span><span class="sxs-lookup"><span data-stu-id="865e5-127">get_Response</span></span> 

<span data-ttu-id="865e5-128">Web 资源响应对象的占位符。</span><span class="sxs-lookup"><span data-stu-id="865e5-128">A placeholder for the web resource response object.</span></span>

> <span data-ttu-id="865e5-129">公共 HRESULT [get_Response](#get_response) ([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* \* 响应) </span><span class="sxs-lookup"><span data-stu-id="865e5-129">public HRESULT [get_Response](#get_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \*\* response)</span></span>

<span data-ttu-id="865e5-130">如果设置了此对象，将在此响应中完成 web 资源请求。</span><span class="sxs-lookup"><span data-stu-id="865e5-130">If this object is set, the web resource request will be completed with this response.</span></span>

#### <span data-ttu-id="865e5-131">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="865e5-131">GetDeferral</span></span> 

<span data-ttu-id="865e5-132">获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="865e5-132">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="865e5-133">公共 HRESULT [GetDeferral](#getdeferral) ([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期) </span><span class="sxs-lookup"><span data-stu-id="865e5-133">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="865e5-134">你可以使用 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象在以后的时间完成该请求。</span><span class="sxs-lookup"><span data-stu-id="865e5-134">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the request at a later time.</span></span>

#### <span data-ttu-id="865e5-135">put_Response</span><span class="sxs-lookup"><span data-stu-id="865e5-135">put_Response</span></span> 

<span data-ttu-id="865e5-136">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="865e5-136">Set the Response property.</span></span>

> <span data-ttu-id="865e5-137">公共 HRESULT [put_Response](#put_response) ([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* Response) </span><span class="sxs-lookup"><span data-stu-id="865e5-137">public HRESULT [put_Response](#put_response)([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) \* response)</span></span>

<span data-ttu-id="865e5-138">可以使用 CreateWebResourceResponse 创建空的 Web 资源响应对象，然后对其进行修改以构造响应。</span><span class="sxs-lookup"><span data-stu-id="865e5-138">An empty Web resource response object can be created with CreateWebResourceResponse and then modified to construct the response.</span></span>

