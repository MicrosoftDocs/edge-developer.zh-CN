---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 7072a25636efb638fcb42c593aa6cc77e990965a
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698498"
---
# <span data-ttu-id="3d83a-104">interface ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="3d83a-104">interface ICoreWebView2WebResourceResponse</span></span> 

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="3d83a-105">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="3d83a-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="3d83a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3d83a-106">Summary</span></span>

 <span data-ttu-id="3d83a-107">成员</span><span class="sxs-lookup"><span data-stu-id="3d83a-107">Members</span></span>                        | <span data-ttu-id="3d83a-108">描述</span><span class="sxs-lookup"><span data-stu-id="3d83a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3d83a-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="3d83a-109">get_Content</span></span>](#get_content) | <span data-ttu-id="3d83a-110">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="3d83a-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="3d83a-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="3d83a-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="3d83a-112">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="3d83a-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="3d83a-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="3d83a-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="3d83a-114">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="3d83a-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="3d83a-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="3d83a-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="3d83a-116">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="3d83a-116">The HTTP response status code.</span></span>
[<span data-ttu-id="3d83a-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="3d83a-117">put_Content</span></span>](#put_content) | <span data-ttu-id="3d83a-118">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="3d83a-118">Set the Content property.</span></span>
[<span data-ttu-id="3d83a-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="3d83a-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="3d83a-120">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="3d83a-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="3d83a-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="3d83a-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="3d83a-122">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="3d83a-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="3d83a-123">成员</span><span class="sxs-lookup"><span data-stu-id="3d83a-123">Members</span></span>

#### <span data-ttu-id="3d83a-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="3d83a-124">get_Content</span></span> 

<span data-ttu-id="3d83a-125">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="3d83a-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="3d83a-126">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="3d83a-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="3d83a-127">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="3d83a-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="3d83a-128">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="3d83a-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="3d83a-129">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="3d83a-129">Null means no content data.</span></span> <span data-ttu-id="3d83a-130">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="3d83a-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="3d83a-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="3d83a-131">get_Headers</span></span> 

<span data-ttu-id="3d83a-132">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="3d83a-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="3d83a-133">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="3d83a-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="3d83a-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="3d83a-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="3d83a-135">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="3d83a-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="3d83a-136">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="3d83a-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="3d83a-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="3d83a-137">get_StatusCode</span></span> 

<span data-ttu-id="3d83a-138">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="3d83a-138">The HTTP response status code.</span></span>

> <span data-ttu-id="3d83a-139">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="3d83a-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="3d83a-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="3d83a-140">put_Content</span></span> 

<span data-ttu-id="3d83a-141">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="3d83a-141">Set the Content property.</span></span>

> <span data-ttu-id="3d83a-142">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="3d83a-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="3d83a-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="3d83a-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="3d83a-144">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="3d83a-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="3d83a-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="3d83a-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="3d83a-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="3d83a-146">put_StatusCode</span></span> 

<span data-ttu-id="3d83a-147">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="3d83a-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="3d83a-148">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="3d83a-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

