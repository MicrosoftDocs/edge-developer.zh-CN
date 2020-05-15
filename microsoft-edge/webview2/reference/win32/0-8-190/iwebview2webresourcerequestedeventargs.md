---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 899a6f50db1d77f3f24524c5ccec139dcbdbcaf9
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652869"
---
# <span data-ttu-id="772da-104">interface IWebView2WebResourceRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="772da-104">interface IWebView2WebResourceRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="772da-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="772da-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="772da-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="772da-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="772da-107">WebResourceRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="772da-107">Event args for the WebResourceRequested event.</span></span>

## <span data-ttu-id="772da-108">摘要</span><span class="sxs-lookup"><span data-stu-id="772da-108">Summary</span></span>

 <span data-ttu-id="772da-109">成员</span><span class="sxs-lookup"><span data-stu-id="772da-109">Members</span></span>                        | <span data-ttu-id="772da-110">描述</span><span class="sxs-lookup"><span data-stu-id="772da-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="772da-111">get_Request</span><span class="sxs-lookup"><span data-stu-id="772da-111">get_Request</span></span>](#get_request) | <span data-ttu-id="772da-112">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="772da-112">The HTTP request.</span></span>
[<span data-ttu-id="772da-113">get_Response</span><span class="sxs-lookup"><span data-stu-id="772da-113">get_Response</span></span>](#get_response) | <span data-ttu-id="772da-114">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="772da-114">The HTTP response.</span></span>
[<span data-ttu-id="772da-115">put_Response</span><span class="sxs-lookup"><span data-stu-id="772da-115">put_Response</span></span>](#put_response) | <span data-ttu-id="772da-116">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="772da-116">Set the Response property.</span></span>
[<span data-ttu-id="772da-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="772da-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="772da-118">获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="772da-118">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

## <span data-ttu-id="772da-119">成员</span><span class="sxs-lookup"><span data-stu-id="772da-119">Members</span></span>

#### <span data-ttu-id="772da-120">get_Request</span><span class="sxs-lookup"><span data-stu-id="772da-120">get_Request</span></span> 

<span data-ttu-id="772da-121">HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="772da-121">The HTTP request.</span></span>

> <span data-ttu-id="772da-122">公共 HRESULT [get_Request](#get_request)（[IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \* \* 请求）</span><span class="sxs-lookup"><span data-stu-id="772da-122">public HRESULT [get_Request](#get_request)([IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) \*\* request)</span></span>

#### <span data-ttu-id="772da-123">get_Response</span><span class="sxs-lookup"><span data-stu-id="772da-123">get_Response</span></span> 

<span data-ttu-id="772da-124">HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="772da-124">The HTTP response.</span></span>

> <span data-ttu-id="772da-125">公共 HRESULT [get_Response](#get_response)（[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* \* Response）</span><span class="sxs-lookup"><span data-stu-id="772da-125">public HRESULT [get_Response](#get_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \*\* response)</span></span>

#### <span data-ttu-id="772da-126">put_Response</span><span class="sxs-lookup"><span data-stu-id="772da-126">put_Response</span></span> 

<span data-ttu-id="772da-127">设置 Response 属性。</span><span class="sxs-lookup"><span data-stu-id="772da-127">Set the Response property.</span></span>

> <span data-ttu-id="772da-128">公共 HRESULT [put_Response](#put_response)（[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* Response）</span><span class="sxs-lookup"><span data-stu-id="772da-128">public HRESULT [put_Response](#put_response)([IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) \* response)</span></span>

#### <span data-ttu-id="772da-129">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="772da-129">GetDeferral</span></span> 

<span data-ttu-id="772da-130">获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="772da-130">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="772da-131">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="772da-131">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="772da-132">你可以使用[IWebView2Deferral](IWebView2Deferral.md)对象在以后的时间完成网络请求。</span><span class="sxs-lookup"><span data-stu-id="772da-132">You can use the [IWebView2Deferral](IWebView2Deferral.md) object to complete the network request at a later time.</span></span>

