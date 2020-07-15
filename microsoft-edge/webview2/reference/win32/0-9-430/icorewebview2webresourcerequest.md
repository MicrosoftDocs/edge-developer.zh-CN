---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: a2ac747a9981b3d44e8dbddd390bbb9b72690105
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880134"
---
# <span data-ttu-id="623e6-104">0.9.430-接口 ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="623e6-104">0.9.430 - interface ICoreWebView2WebResourceRequest</span></span> 

> [!NOTE]
> <span data-ttu-id="623e6-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="623e6-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="623e6-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="623e6-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="623e6-107">与 WebResourceRequested 事件一起使用的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="623e6-107">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="623e6-108">摘要</span><span class="sxs-lookup"><span data-stu-id="623e6-108">Summary</span></span>

 <span data-ttu-id="623e6-109">成员</span><span class="sxs-lookup"><span data-stu-id="623e6-109">Members</span></span>                        | <span data-ttu-id="623e6-110">描述</span><span class="sxs-lookup"><span data-stu-id="623e6-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="623e6-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="623e6-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="623e6-112">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="623e6-112">The request URI.</span></span>
[<span data-ttu-id="623e6-113">put_Uri</span><span class="sxs-lookup"><span data-stu-id="623e6-113">put_Uri</span></span>](#put_uri) | <span data-ttu-id="623e6-114">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="623e6-114">Set the Uri property.</span></span>
[<span data-ttu-id="623e6-115">get_Method</span><span class="sxs-lookup"><span data-stu-id="623e6-115">get_Method</span></span>](#get_method) | <span data-ttu-id="623e6-116">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="623e6-116">The HTTP request method.</span></span>
[<span data-ttu-id="623e6-117">put_Method</span><span class="sxs-lookup"><span data-stu-id="623e6-117">put_Method</span></span>](#put_method) | <span data-ttu-id="623e6-118">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="623e6-118">Set the Method property.</span></span>
[<span data-ttu-id="623e6-119">get_Content</span><span class="sxs-lookup"><span data-stu-id="623e6-119">get_Content</span></span>](#get_content) | <span data-ttu-id="623e6-120">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="623e6-120">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="623e6-121">put_Content</span><span class="sxs-lookup"><span data-stu-id="623e6-121">put_Content</span></span>](#put_content) | <span data-ttu-id="623e6-122">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="623e6-122">Set the Content property.</span></span>
[<span data-ttu-id="623e6-123">get_Headers</span><span class="sxs-lookup"><span data-stu-id="623e6-123">get_Headers</span></span>](#get_headers) | <span data-ttu-id="623e6-124">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="623e6-124">The mutable HTTP request headers.</span></span>

## <span data-ttu-id="623e6-125">成员</span><span class="sxs-lookup"><span data-stu-id="623e6-125">Members</span></span>

#### <span data-ttu-id="623e6-126">get_Uri</span><span class="sxs-lookup"><span data-stu-id="623e6-126">get_Uri</span></span> 

<span data-ttu-id="623e6-127">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="623e6-127">The request URI.</span></span>

> <span data-ttu-id="623e6-128">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="623e6-128">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="623e6-129">put_Uri</span><span class="sxs-lookup"><span data-stu-id="623e6-129">put_Uri</span></span> 

<span data-ttu-id="623e6-130">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="623e6-130">Set the Uri property.</span></span>

> <span data-ttu-id="623e6-131">公共 HRESULT [put_Uri](#put_uri)（LPCWSTR Uri）</span><span class="sxs-lookup"><span data-stu-id="623e6-131">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

#### <span data-ttu-id="623e6-132">get_Method</span><span class="sxs-lookup"><span data-stu-id="623e6-132">get_Method</span></span> 

<span data-ttu-id="623e6-133">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="623e6-133">The HTTP request method.</span></span>

> <span data-ttu-id="623e6-134">公共 HRESULT [get_Method](#get_method)（LPWSTR \* 方法）</span><span class="sxs-lookup"><span data-stu-id="623e6-134">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="623e6-135">put_Method</span><span class="sxs-lookup"><span data-stu-id="623e6-135">put_Method</span></span> 

<span data-ttu-id="623e6-136">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="623e6-136">Set the Method property.</span></span>

> <span data-ttu-id="623e6-137">public HRESULT [put_Method](#put_method)（LPCWSTR 方法）</span><span class="sxs-lookup"><span data-stu-id="623e6-137">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="623e6-138">get_Content</span><span class="sxs-lookup"><span data-stu-id="623e6-138">get_Content</span></span> 

<span data-ttu-id="623e6-139">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="623e6-139">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="623e6-140">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="623e6-140">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="623e6-141">发布数据将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="623e6-141">POST data would be here.</span></span> <span data-ttu-id="623e6-142">如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。</span><span class="sxs-lookup"><span data-stu-id="623e6-142">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="623e6-143">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="623e6-143">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="623e6-144">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="623e6-144">Null means no content data.</span></span> <span data-ttu-id="623e6-145">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="623e6-145">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="623e6-146">put_Content</span><span class="sxs-lookup"><span data-stu-id="623e6-146">put_Content</span></span> 

<span data-ttu-id="623e6-147">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="623e6-147">Set the Content property.</span></span>

> <span data-ttu-id="623e6-148">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="623e6-148">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="623e6-149">get_Headers</span><span class="sxs-lookup"><span data-stu-id="623e6-149">get_Headers</span></span> 

<span data-ttu-id="623e6-150">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="623e6-150">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="623e6-151">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="623e6-151">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) \*\* headers)</span></span>

