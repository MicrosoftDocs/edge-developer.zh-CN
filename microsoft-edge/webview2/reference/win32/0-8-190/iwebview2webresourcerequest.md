---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 3c9736c8b5a3cfb0de994285f3a1f90d62666fd0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878146"
---
# <span data-ttu-id="5078b-104">0.8.355-接口 IWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="5078b-104">0.8.355 - interface IWebView2WebResourceRequest</span></span> 

> [!NOTE]
> <span data-ttu-id="5078b-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="5078b-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="5078b-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="5078b-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="5078b-107">与 WebResourceRequested 事件一起使用的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="5078b-107">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="5078b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5078b-108">Summary</span></span>

 <span data-ttu-id="5078b-109">成员</span><span class="sxs-lookup"><span data-stu-id="5078b-109">Members</span></span>                        | <span data-ttu-id="5078b-110">描述</span><span class="sxs-lookup"><span data-stu-id="5078b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5078b-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="5078b-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="5078b-112">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="5078b-112">The request URI.</span></span>
[<span data-ttu-id="5078b-113">put_Uri</span><span class="sxs-lookup"><span data-stu-id="5078b-113">put_Uri</span></span>](#put_uri) | <span data-ttu-id="5078b-114">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="5078b-114">Set the Uri property.</span></span>
[<span data-ttu-id="5078b-115">get_Method</span><span class="sxs-lookup"><span data-stu-id="5078b-115">get_Method</span></span>](#get_method) | <span data-ttu-id="5078b-116">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="5078b-116">The HTTP request method.</span></span>
[<span data-ttu-id="5078b-117">put_Method</span><span class="sxs-lookup"><span data-stu-id="5078b-117">put_Method</span></span>](#put_method) | <span data-ttu-id="5078b-118">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="5078b-118">Set the Method property.</span></span>
[<span data-ttu-id="5078b-119">get_Content</span><span class="sxs-lookup"><span data-stu-id="5078b-119">get_Content</span></span>](#get_content) | <span data-ttu-id="5078b-120">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="5078b-120">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="5078b-121">put_Content</span><span class="sxs-lookup"><span data-stu-id="5078b-121">put_Content</span></span>](#put_content) | <span data-ttu-id="5078b-122">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="5078b-122">Set the Content property.</span></span>
[<span data-ttu-id="5078b-123">get_Headers</span><span class="sxs-lookup"><span data-stu-id="5078b-123">get_Headers</span></span>](#get_headers) | <span data-ttu-id="5078b-124">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="5078b-124">The mutable HTTP request headers.</span></span>

## <span data-ttu-id="5078b-125">成员</span><span class="sxs-lookup"><span data-stu-id="5078b-125">Members</span></span>

#### <span data-ttu-id="5078b-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="5078b-126">get_Uri</span></span> 

<span data-ttu-id="5078b-127">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="5078b-127">The request URI.</span></span>

> <span data-ttu-id="5078b-128">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="5078b-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="5078b-129">put_Uri</span><span class="sxs-lookup"><span data-stu-id="5078b-129">put_Uri</span></span> 

<span data-ttu-id="5078b-130">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="5078b-130">Set the Uri property.</span></span>

> <span data-ttu-id="5078b-131">公共 HRESULT [put_Uri](#put_uri)（LPCWSTR Uri）</span><span class="sxs-lookup"><span data-stu-id="5078b-131">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

#### <span data-ttu-id="5078b-132">get_Method</span><span class="sxs-lookup"><span data-stu-id="5078b-132">get_Method</span></span> 

<span data-ttu-id="5078b-133">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="5078b-133">The HTTP request method.</span></span>

> <span data-ttu-id="5078b-134">公共 HRESULT [get_Method](#get_method)（LPWSTR \* 方法）</span><span class="sxs-lookup"><span data-stu-id="5078b-134">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="5078b-135">put_Method</span><span class="sxs-lookup"><span data-stu-id="5078b-135">put_Method</span></span> 

<span data-ttu-id="5078b-136">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="5078b-136">Set the Method property.</span></span>

> <span data-ttu-id="5078b-137">public HRESULT [put_Method](#put_method)（LPCWSTR 方法）</span><span class="sxs-lookup"><span data-stu-id="5078b-137">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="5078b-138">get_Content</span><span class="sxs-lookup"><span data-stu-id="5078b-138">get_Content</span></span> 

<span data-ttu-id="5078b-139">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="5078b-139">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="5078b-140">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="5078b-140">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="5078b-141">发布数据将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="5078b-141">POST data would be here.</span></span> <span data-ttu-id="5078b-142">如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。</span><span class="sxs-lookup"><span data-stu-id="5078b-142">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="5078b-143">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="5078b-143">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="5078b-144">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="5078b-144">Null means no content data.</span></span> <span data-ttu-id="5078b-145">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="5078b-145">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="5078b-146">put_Content</span><span class="sxs-lookup"><span data-stu-id="5078b-146">put_Content</span></span> 

<span data-ttu-id="5078b-147">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="5078b-147">Set the Content property.</span></span>

> <span data-ttu-id="5078b-148">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="5078b-148">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="5078b-149">get_Headers</span><span class="sxs-lookup"><span data-stu-id="5078b-149">get_Headers</span></span> 

<span data-ttu-id="5078b-150">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="5078b-150">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="5078b-151">公共 HRESULT [get_Headers](#get_headers)（[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="5078b-151">public HRESULT [get_Headers](#get_headers)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* headers)</span></span>

