---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 95c0a881a8a201d21ca9cb2662c282b36efa2ed3
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878104"
---
# <span data-ttu-id="9c21f-104">0.8.355-接口 IWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="9c21f-104">0.8.355 - interface IWebView2WebResourceResponse</span></span> 

> [!NOTE]
> <span data-ttu-id="9c21f-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="9c21f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="9c21f-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="9c21f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="9c21f-107">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="9c21f-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="9c21f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9c21f-108">Summary</span></span>

 <span data-ttu-id="9c21f-109">成员</span><span class="sxs-lookup"><span data-stu-id="9c21f-109">Members</span></span>                        | <span data-ttu-id="9c21f-110">描述</span><span class="sxs-lookup"><span data-stu-id="9c21f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9c21f-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="9c21f-111">get_Content</span></span>](#get_content) | <span data-ttu-id="9c21f-112">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="9c21f-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="9c21f-113">put_Content</span><span class="sxs-lookup"><span data-stu-id="9c21f-113">put_Content</span></span>](#put_content) | <span data-ttu-id="9c21f-114">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="9c21f-114">Set the Content property.</span></span>
[<span data-ttu-id="9c21f-115">get_Headers</span><span class="sxs-lookup"><span data-stu-id="9c21f-115">get_Headers</span></span>](#get_headers) | <span data-ttu-id="9c21f-116">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="9c21f-116">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="9c21f-117">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9c21f-117">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="9c21f-118">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="9c21f-118">The HTTP response status code.</span></span>
[<span data-ttu-id="9c21f-119">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9c21f-119">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="9c21f-120">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="9c21f-120">Set the StatusCode property.</span></span>
[<span data-ttu-id="9c21f-121">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9c21f-121">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="9c21f-122">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="9c21f-122">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="9c21f-123">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9c21f-123">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="9c21f-124">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="9c21f-124">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="9c21f-125">成员</span><span class="sxs-lookup"><span data-stu-id="9c21f-125">Members</span></span>

#### <span data-ttu-id="9c21f-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="9c21f-126">get_Content</span></span> 

<span data-ttu-id="9c21f-127">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="9c21f-127">HTTP response content as stream.</span></span>

> <span data-ttu-id="9c21f-128">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="9c21f-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="9c21f-129">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="9c21f-129">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="9c21f-130">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="9c21f-130">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="9c21f-131">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="9c21f-131">Null means no content data.</span></span> <span data-ttu-id="9c21f-132">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="9c21f-132">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="9c21f-133">put_Content</span><span class="sxs-lookup"><span data-stu-id="9c21f-133">put_Content</span></span> 

<span data-ttu-id="9c21f-134">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="9c21f-134">Set the Content property.</span></span>

> <span data-ttu-id="9c21f-135">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="9c21f-135">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="9c21f-136">get_Headers</span><span class="sxs-lookup"><span data-stu-id="9c21f-136">get_Headers</span></span> 

<span data-ttu-id="9c21f-137">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="9c21f-137">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="9c21f-138">公共 HRESULT [get_Headers](#get_headers)（[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="9c21f-138">public HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="9c21f-139">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9c21f-139">get_StatusCode</span></span> 

<span data-ttu-id="9c21f-140">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="9c21f-140">The HTTP response status code.</span></span>

> <span data-ttu-id="9c21f-141">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="9c21f-141">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="9c21f-142">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9c21f-142">put_StatusCode</span></span> 

<span data-ttu-id="9c21f-143">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="9c21f-143">Set the StatusCode property.</span></span>

> <span data-ttu-id="9c21f-144">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="9c21f-144">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="9c21f-145">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9c21f-145">get_ReasonPhrase</span></span> 

<span data-ttu-id="9c21f-146">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="9c21f-146">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="9c21f-147">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="9c21f-147">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="9c21f-148">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9c21f-148">put_ReasonPhrase</span></span> 

<span data-ttu-id="9c21f-149">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="9c21f-149">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="9c21f-150">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="9c21f-150">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

