---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: e9d84fbd459d56b82ab4b7d253526e517960c1db
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885716"
---
# <span data-ttu-id="4f928-104">0.8.355-接口 IWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="4f928-104">0.8.355 - interface IWebView2WebResourceRequest</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="4f928-105">与 WebResourceRequested 事件一起使用的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="4f928-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="4f928-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4f928-106">Summary</span></span>

 <span data-ttu-id="4f928-107">成员</span><span class="sxs-lookup"><span data-stu-id="4f928-107">Members</span></span>                        | <span data-ttu-id="4f928-108">描述</span><span class="sxs-lookup"><span data-stu-id="4f928-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4f928-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4f928-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="4f928-110">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="4f928-110">The request URI.</span></span>
[<span data-ttu-id="4f928-111">put_Uri</span><span class="sxs-lookup"><span data-stu-id="4f928-111">put_Uri</span></span>](#put_uri) | <span data-ttu-id="4f928-112">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="4f928-112">Set the Uri property.</span></span>
[<span data-ttu-id="4f928-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="4f928-113">get_Method</span></span>](#get_method) | <span data-ttu-id="4f928-114">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="4f928-114">The HTTP request method.</span></span>
[<span data-ttu-id="4f928-115">put_Method</span><span class="sxs-lookup"><span data-stu-id="4f928-115">put_Method</span></span>](#put_method) | <span data-ttu-id="4f928-116">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="4f928-116">Set the Method property.</span></span>
[<span data-ttu-id="4f928-117">get_Content</span><span class="sxs-lookup"><span data-stu-id="4f928-117">get_Content</span></span>](#get_content) | <span data-ttu-id="4f928-118">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="4f928-118">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="4f928-119">put_Content</span><span class="sxs-lookup"><span data-stu-id="4f928-119">put_Content</span></span>](#put_content) | <span data-ttu-id="4f928-120">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="4f928-120">Set the Content property.</span></span>
[<span data-ttu-id="4f928-121">get_Headers</span><span class="sxs-lookup"><span data-stu-id="4f928-121">get_Headers</span></span>](#get_headers) | <span data-ttu-id="4f928-122">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="4f928-122">The mutable HTTP request headers.</span></span>

## <span data-ttu-id="4f928-123">成员</span><span class="sxs-lookup"><span data-stu-id="4f928-123">Members</span></span>

#### <span data-ttu-id="4f928-124">get_Uri</span><span class="sxs-lookup"><span data-stu-id="4f928-124">get_Uri</span></span> 

<span data-ttu-id="4f928-125">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="4f928-125">The request URI.</span></span>

> <span data-ttu-id="4f928-126">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="4f928-126">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="4f928-127">put_Uri</span><span class="sxs-lookup"><span data-stu-id="4f928-127">put_Uri</span></span> 

<span data-ttu-id="4f928-128">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="4f928-128">Set the Uri property.</span></span>

> <span data-ttu-id="4f928-129">公共 HRESULT [put_Uri](#put_uri)（LPCWSTR Uri）</span><span class="sxs-lookup"><span data-stu-id="4f928-129">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

#### <span data-ttu-id="4f928-130">get_Method</span><span class="sxs-lookup"><span data-stu-id="4f928-130">get_Method</span></span> 

<span data-ttu-id="4f928-131">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="4f928-131">The HTTP request method.</span></span>

> <span data-ttu-id="4f928-132">公共 HRESULT [get_Method](#get_method)（LPWSTR \* 方法）</span><span class="sxs-lookup"><span data-stu-id="4f928-132">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="4f928-133">put_Method</span><span class="sxs-lookup"><span data-stu-id="4f928-133">put_Method</span></span> 

<span data-ttu-id="4f928-134">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="4f928-134">Set the Method property.</span></span>

> <span data-ttu-id="4f928-135">public HRESULT [put_Method](#put_method)（LPCWSTR 方法）</span><span class="sxs-lookup"><span data-stu-id="4f928-135">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="4f928-136">get_Content</span><span class="sxs-lookup"><span data-stu-id="4f928-136">get_Content</span></span> 

<span data-ttu-id="4f928-137">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="4f928-137">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="4f928-138">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="4f928-138">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="4f928-139">发布数据将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="4f928-139">POST data would be here.</span></span> <span data-ttu-id="4f928-140">如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。</span><span class="sxs-lookup"><span data-stu-id="4f928-140">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="4f928-141">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="4f928-141">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="4f928-142">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="4f928-142">Null means no content data.</span></span> <span data-ttu-id="4f928-143">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="4f928-143">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="4f928-144">put_Content</span><span class="sxs-lookup"><span data-stu-id="4f928-144">put_Content</span></span> 

<span data-ttu-id="4f928-145">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="4f928-145">Set the Content property.</span></span>

> <span data-ttu-id="4f928-146">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="4f928-146">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="4f928-147">get_Headers</span><span class="sxs-lookup"><span data-stu-id="4f928-147">get_Headers</span></span> 

<span data-ttu-id="4f928-148">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="4f928-148">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="4f928-149">公共 HRESULT [get_Headers](#get_headers)（[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="4f928-149">public HRESULT [get_Headers](#get_headers)([IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) \*\* headers)</span></span>

