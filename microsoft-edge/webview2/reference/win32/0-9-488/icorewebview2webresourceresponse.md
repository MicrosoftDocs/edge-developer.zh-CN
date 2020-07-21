---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: e17e12759bef051a33e99999f0e938da5bd16939
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883782"
---
# <span data-ttu-id="1e6c9-104">0.9.515-接口 ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="1e6c9-104">0.9.515 - interface ICoreWebView2WebResourceResponse</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="1e6c9-105">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="1e6c9-106">摘要</span><span class="sxs-lookup"><span data-stu-id="1e6c9-106">Summary</span></span>

 <span data-ttu-id="1e6c9-107">成员</span><span class="sxs-lookup"><span data-stu-id="1e6c9-107">Members</span></span>                        | <span data-ttu-id="1e6c9-108">描述</span><span class="sxs-lookup"><span data-stu-id="1e6c9-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1e6c9-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="1e6c9-109">get_Content</span></span>](#get_content) | <span data-ttu-id="1e6c9-110">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="1e6c9-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="1e6c9-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="1e6c9-112">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="1e6c9-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="1e6c9-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="1e6c9-114">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="1e6c9-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="1e6c9-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="1e6c9-116">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-116">The HTTP response status code.</span></span>
[<span data-ttu-id="1e6c9-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="1e6c9-117">put_Content</span></span>](#put_content) | <span data-ttu-id="1e6c9-118">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-118">Set the Content property.</span></span>
[<span data-ttu-id="1e6c9-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="1e6c9-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="1e6c9-120">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="1e6c9-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="1e6c9-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="1e6c9-122">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="1e6c9-123">成员</span><span class="sxs-lookup"><span data-stu-id="1e6c9-123">Members</span></span>

#### <span data-ttu-id="1e6c9-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="1e6c9-124">get_Content</span></span> 

<span data-ttu-id="1e6c9-125">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="1e6c9-126">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="1e6c9-127">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="1e6c9-128">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="1e6c9-129">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-129">Null means no content data.</span></span> <span data-ttu-id="1e6c9-130">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="1e6c9-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="1e6c9-131">get_Headers</span></span> 

<span data-ttu-id="1e6c9-132">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="1e6c9-133">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="1e6c9-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="1e6c9-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="1e6c9-135">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="1e6c9-136">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="1e6c9-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="1e6c9-137">get_StatusCode</span></span> 

<span data-ttu-id="1e6c9-138">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-138">The HTTP response status code.</span></span>

> <span data-ttu-id="1e6c9-139">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="1e6c9-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="1e6c9-140">put_Content</span></span> 

<span data-ttu-id="1e6c9-141">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-141">Set the Content property.</span></span>

> <span data-ttu-id="1e6c9-142">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="1e6c9-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="1e6c9-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="1e6c9-144">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="1e6c9-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="1e6c9-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="1e6c9-146">put_StatusCode</span></span> 

<span data-ttu-id="1e6c9-147">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="1e6c9-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="1e6c9-148">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="1e6c9-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

