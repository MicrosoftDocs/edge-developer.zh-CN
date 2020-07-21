---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 61f731a948dee970731ba3dbe83426cbb40eb831
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883999"
---
# <span data-ttu-id="53f8a-104">0.9.430-接口 ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="53f8a-104">0.9.430 - interface ICoreWebView2WebResourceResponse</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="53f8a-105">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="53f8a-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="53f8a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="53f8a-106">Summary</span></span>

 <span data-ttu-id="53f8a-107">成员</span><span class="sxs-lookup"><span data-stu-id="53f8a-107">Members</span></span>                        | <span data-ttu-id="53f8a-108">描述</span><span class="sxs-lookup"><span data-stu-id="53f8a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="53f8a-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="53f8a-109">get_Content</span></span>](#get_content) | <span data-ttu-id="53f8a-110">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="53f8a-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="53f8a-111">put_Content</span><span class="sxs-lookup"><span data-stu-id="53f8a-111">put_Content</span></span>](#put_content) | <span data-ttu-id="53f8a-112">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="53f8a-112">Set the Content property.</span></span>
[<span data-ttu-id="53f8a-113">get_Headers</span><span class="sxs-lookup"><span data-stu-id="53f8a-113">get_Headers</span></span>](#get_headers) | <span data-ttu-id="53f8a-114">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="53f8a-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="53f8a-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="53f8a-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="53f8a-116">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="53f8a-116">The HTTP response status code.</span></span>
[<span data-ttu-id="53f8a-117">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="53f8a-117">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="53f8a-118">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="53f8a-118">Set the StatusCode property.</span></span>
[<span data-ttu-id="53f8a-119">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="53f8a-119">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="53f8a-120">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="53f8a-120">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="53f8a-121">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="53f8a-121">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="53f8a-122">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="53f8a-122">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="53f8a-123">成员</span><span class="sxs-lookup"><span data-stu-id="53f8a-123">Members</span></span>

#### <span data-ttu-id="53f8a-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="53f8a-124">get_Content</span></span> 

<span data-ttu-id="53f8a-125">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="53f8a-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="53f8a-126">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="53f8a-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="53f8a-127">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="53f8a-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="53f8a-128">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="53f8a-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="53f8a-129">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="53f8a-129">Null means no content data.</span></span> <span data-ttu-id="53f8a-130">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="53f8a-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="53f8a-131">put_Content</span><span class="sxs-lookup"><span data-stu-id="53f8a-131">put_Content</span></span> 

<span data-ttu-id="53f8a-132">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="53f8a-132">Set the Content property.</span></span>

> <span data-ttu-id="53f8a-133">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="53f8a-133">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="53f8a-134">get_Headers</span><span class="sxs-lookup"><span data-stu-id="53f8a-134">get_Headers</span></span> 

<span data-ttu-id="53f8a-135">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="53f8a-135">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="53f8a-136">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="53f8a-136">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="53f8a-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="53f8a-137">get_StatusCode</span></span> 

<span data-ttu-id="53f8a-138">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="53f8a-138">The HTTP response status code.</span></span>

> <span data-ttu-id="53f8a-139">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="53f8a-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="53f8a-140">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="53f8a-140">put_StatusCode</span></span> 

<span data-ttu-id="53f8a-141">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="53f8a-141">Set the StatusCode property.</span></span>

> <span data-ttu-id="53f8a-142">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="53f8a-142">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="53f8a-143">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="53f8a-143">get_ReasonPhrase</span></span> 

<span data-ttu-id="53f8a-144">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="53f8a-144">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="53f8a-145">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="53f8a-145">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="53f8a-146">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="53f8a-146">put_ReasonPhrase</span></span> 

<span data-ttu-id="53f8a-147">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="53f8a-147">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="53f8a-148">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="53f8a-148">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

