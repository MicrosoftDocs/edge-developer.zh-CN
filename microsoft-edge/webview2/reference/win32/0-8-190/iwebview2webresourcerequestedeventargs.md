---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: aa5206be13790fd7a783f2afb4471de90fc8f2ae
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885714"
---
# <span data-ttu-id="d5840-104">0.8.355-接口 IWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d5840-104">0.8.355 - interface IWebView2WebResourceRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="d5840-105">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d5840-105">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="d5840-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d5840-106">Summary</span></span>

 <span data-ttu-id="d5840-107">成员</span><span class="sxs-lookup"><span data-stu-id="d5840-107">Members</span></span>                        | <span data-ttu-id="d5840-108">描述</span><span class="sxs-lookup"><span data-stu-id="d5840-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d5840-109">get_Request</span><span class="sxs-lookup"><span data-stu-id="d5840-109">get_Request</span></span>](#get_request) | <span data-ttu-id="d5840-110">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="d5840-110">The HTTP request.</span></span>
[<span data-ttu-id="d5840-111">get_Response</span><span class="sxs-lookup"><span data-stu-id="d5840-111">get_Response</span></span>](#get_response) | <span data-ttu-id="d5840-112">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="d5840-112">The HTTP response.</span></span>
[<span data-ttu-id="d5840-113">put_Response</span><span class="sxs-lookup"><span data-stu-id="d5840-113">put_Response</span></span>](#put_response) | <span data-ttu-id="d5840-114">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="d5840-114">Set the Response property.</span></span>
[<span data-ttu-id="d5840-115">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d5840-115">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="d5840-116">获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="d5840-116">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

## <span data-ttu-id="d5840-117">成员</span><span class="sxs-lookup"><span data-stu-id="d5840-117">Members</span></span>

#### <span data-ttu-id="d5840-118">get_Request</span><span class="sxs-lookup"><span data-stu-id="d5840-118">get_Request</span></span> 

<span data-ttu-id="d5840-119">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="d5840-119">The HTTP request.</span></span>

> <span data-ttu-id="d5840-120">公共 HRESULT [get_Request](#get_request)（[IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="d5840-120">public HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="d5840-121">get_Response</span><span class="sxs-lookup"><span data-stu-id="d5840-121">get_Response</span></span> 

<span data-ttu-id="d5840-122">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="d5840-122">The HTTP response.</span></span>

> <span data-ttu-id="d5840-123">公共 HRESULT [get_Response](#get_response)（[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="d5840-123">public HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="d5840-124">put_Response</span><span class="sxs-lookup"><span data-stu-id="d5840-124">put_Response</span></span> 

<span data-ttu-id="d5840-125">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="d5840-125">Set the Response property.</span></span>

> <span data-ttu-id="d5840-126">公共 HRESULT [put_Response](#put_response)（[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="d5840-126">public HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="d5840-127">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="d5840-127">GetDeferral</span></span> 

<span data-ttu-id="d5840-128">获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="d5840-128">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="d5840-129">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="d5840-129">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="d5840-130">你可以使用[IWebView2Deferral](IWebView2Deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="d5840-130">You can use the [IWebView2Deferral](IWebView2Deferral.md) object to complete the network request at a later time.</span></span>

