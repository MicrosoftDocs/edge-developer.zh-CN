---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 82c94869a84165de4c3b8d09937d6ea5d1f79256
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885686"
---
# <span data-ttu-id="e5a88-104">0.8.355-接口 IWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="e5a88-104">0.8.355 - interface IWebView2WebResourceResponse</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="e5a88-105">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="e5a88-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="e5a88-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e5a88-106">Summary</span></span>

 <span data-ttu-id="e5a88-107">成员</span><span class="sxs-lookup"><span data-stu-id="e5a88-107">Members</span></span>                        | <span data-ttu-id="e5a88-108">描述</span><span class="sxs-lookup"><span data-stu-id="e5a88-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e5a88-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="e5a88-109">get_Content</span></span>](#get_content) | <span data-ttu-id="e5a88-110">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="e5a88-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="e5a88-111">put_Content</span><span class="sxs-lookup"><span data-stu-id="e5a88-111">put_Content</span></span>](#put_content) | <span data-ttu-id="e5a88-112">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="e5a88-112">Set the Content property.</span></span>
[<span data-ttu-id="e5a88-113">get_Headers</span><span class="sxs-lookup"><span data-stu-id="e5a88-113">get_Headers</span></span>](#get_headers) | <span data-ttu-id="e5a88-114">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="e5a88-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="e5a88-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="e5a88-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="e5a88-116">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="e5a88-116">The HTTP response status code.</span></span>
[<span data-ttu-id="e5a88-117">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="e5a88-117">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="e5a88-118">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="e5a88-118">Set the StatusCode property.</span></span>
[<span data-ttu-id="e5a88-119">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="e5a88-119">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="e5a88-120">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="e5a88-120">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="e5a88-121">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="e5a88-121">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="e5a88-122">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="e5a88-122">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="e5a88-123">成员</span><span class="sxs-lookup"><span data-stu-id="e5a88-123">Members</span></span>

#### <span data-ttu-id="e5a88-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="e5a88-124">get_Content</span></span> 

<span data-ttu-id="e5a88-125">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="e5a88-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="e5a88-126">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="e5a88-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="e5a88-127">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="e5a88-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="e5a88-128">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="e5a88-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="e5a88-129">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="e5a88-129">Null means no content data.</span></span> <span data-ttu-id="e5a88-130">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="e5a88-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="e5a88-131">put_Content</span><span class="sxs-lookup"><span data-stu-id="e5a88-131">put_Content</span></span> 

<span data-ttu-id="e5a88-132">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="e5a88-132">Set the Content property.</span></span>

> <span data-ttu-id="e5a88-133">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="e5a88-133">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="e5a88-134">get_Headers</span><span class="sxs-lookup"><span data-stu-id="e5a88-134">get_Headers</span></span> 

<span data-ttu-id="e5a88-135">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="e5a88-135">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="e5a88-136">公共 HRESULT [get_Headers](#get_headers)（[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="e5a88-136">public HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="e5a88-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="e5a88-137">get_StatusCode</span></span> 

<span data-ttu-id="e5a88-138">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="e5a88-138">The HTTP response status code.</span></span>

> <span data-ttu-id="e5a88-139">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="e5a88-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="e5a88-140">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="e5a88-140">put_StatusCode</span></span> 

<span data-ttu-id="e5a88-141">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="e5a88-141">Set the StatusCode property.</span></span>

> <span data-ttu-id="e5a88-142">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="e5a88-142">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="e5a88-143">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="e5a88-143">get_ReasonPhrase</span></span> 

<span data-ttu-id="e5a88-144">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="e5a88-144">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="e5a88-145">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="e5a88-145">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="e5a88-146">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="e5a88-146">put_ReasonPhrase</span></span> 

<span data-ttu-id="e5a88-147">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="e5a88-147">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="e5a88-148">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="e5a88-148">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

