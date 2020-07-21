---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b60df5b7493ab095c6e71f7d28dbb6ec78d39052
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883768"
---
# <span data-ttu-id="620aa-104">0.9.515-接口 ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="620aa-104">0.9.515 - interface ICoreWebView2WebResourceRequest</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="620aa-105">与 WebResourceRequested 事件一起使用的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="620aa-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="620aa-106">摘要</span><span class="sxs-lookup"><span data-stu-id="620aa-106">Summary</span></span>

 <span data-ttu-id="620aa-107">成员</span><span class="sxs-lookup"><span data-stu-id="620aa-107">Members</span></span>                        | <span data-ttu-id="620aa-108">描述</span><span class="sxs-lookup"><span data-stu-id="620aa-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="620aa-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="620aa-109">get_Content</span></span>](#get_content) | <span data-ttu-id="620aa-110">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="620aa-110">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="620aa-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="620aa-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="620aa-112">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="620aa-112">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="620aa-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="620aa-113">get_Method</span></span>](#get_method) | <span data-ttu-id="620aa-114">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="620aa-114">The HTTP request method.</span></span>
[<span data-ttu-id="620aa-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="620aa-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="620aa-116">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="620aa-116">The request URI.</span></span>
[<span data-ttu-id="620aa-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="620aa-117">put_Content</span></span>](#put_content) | <span data-ttu-id="620aa-118">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="620aa-118">Set the Content property.</span></span>
[<span data-ttu-id="620aa-119">put_Method</span><span class="sxs-lookup"><span data-stu-id="620aa-119">put_Method</span></span>](#put_method) | <span data-ttu-id="620aa-120">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="620aa-120">Set the Method property.</span></span>
[<span data-ttu-id="620aa-121">put_Uri</span><span class="sxs-lookup"><span data-stu-id="620aa-121">put_Uri</span></span>](#put_uri) | <span data-ttu-id="620aa-122">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="620aa-122">Set the Uri property.</span></span>

## <span data-ttu-id="620aa-123">成员</span><span class="sxs-lookup"><span data-stu-id="620aa-123">Members</span></span>

#### <span data-ttu-id="620aa-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="620aa-124">get_Content</span></span> 

<span data-ttu-id="620aa-125">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="620aa-125">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="620aa-126">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="620aa-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="620aa-127">发布数据将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="620aa-127">POST data would be here.</span></span> <span data-ttu-id="620aa-128">如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。</span><span class="sxs-lookup"><span data-stu-id="620aa-128">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="620aa-129">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="620aa-129">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="620aa-130">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="620aa-130">Null means no content data.</span></span> <span data-ttu-id="620aa-131">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="620aa-131">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="620aa-132">get_Headers</span><span class="sxs-lookup"><span data-stu-id="620aa-132">get_Headers</span></span> 

<span data-ttu-id="620aa-133">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="620aa-133">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="620aa-134">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="620aa-134">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="620aa-135">get_Method</span><span class="sxs-lookup"><span data-stu-id="620aa-135">get_Method</span></span> 

<span data-ttu-id="620aa-136">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="620aa-136">The HTTP request method.</span></span>

> <span data-ttu-id="620aa-137">公共 HRESULT [get_Method](#get_method)（LPWSTR \* 方法）</span><span class="sxs-lookup"><span data-stu-id="620aa-137">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="620aa-138">get_Uri</span><span class="sxs-lookup"><span data-stu-id="620aa-138">get_Uri</span></span> 

<span data-ttu-id="620aa-139">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="620aa-139">The request URI.</span></span>

> <span data-ttu-id="620aa-140">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="620aa-140">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="620aa-141">put_Content</span><span class="sxs-lookup"><span data-stu-id="620aa-141">put_Content</span></span> 

<span data-ttu-id="620aa-142">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="620aa-142">Set the Content property.</span></span>

> <span data-ttu-id="620aa-143">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="620aa-143">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="620aa-144">put_Method</span><span class="sxs-lookup"><span data-stu-id="620aa-144">put_Method</span></span> 

<span data-ttu-id="620aa-145">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="620aa-145">Set the Method property.</span></span>

> <span data-ttu-id="620aa-146">public HRESULT [put_Method](#put_method)（LPCWSTR 方法）</span><span class="sxs-lookup"><span data-stu-id="620aa-146">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="620aa-147">put_Uri</span><span class="sxs-lookup"><span data-stu-id="620aa-147">put_Uri</span></span> 

<span data-ttu-id="620aa-148">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="620aa-148">Set the Uri property.</span></span>

> <span data-ttu-id="620aa-149">公共 HRESULT [put_Uri](#put_uri)（LPCWSTR Uri）</span><span class="sxs-lookup"><span data-stu-id="620aa-149">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

