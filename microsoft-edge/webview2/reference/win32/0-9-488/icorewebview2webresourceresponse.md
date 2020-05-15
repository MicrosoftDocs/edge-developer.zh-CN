---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d6b51600479f47eebb09d5cff8fb096455fb1766
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652850"
---
# <span data-ttu-id="24e52-104">interface ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="24e52-104">interface ICoreWebView2WebResourceResponse</span></span> 

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="24e52-105">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="24e52-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="24e52-106">摘要</span><span class="sxs-lookup"><span data-stu-id="24e52-106">Summary</span></span>

 <span data-ttu-id="24e52-107">成员</span><span class="sxs-lookup"><span data-stu-id="24e52-107">Members</span></span>                        | <span data-ttu-id="24e52-108">描述</span><span class="sxs-lookup"><span data-stu-id="24e52-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="24e52-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="24e52-109">get_Content</span></span>](#get_content) | <span data-ttu-id="24e52-110">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="24e52-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="24e52-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="24e52-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="24e52-112">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="24e52-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="24e52-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="24e52-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="24e52-114">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="24e52-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="24e52-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="24e52-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="24e52-116">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="24e52-116">The HTTP response status code.</span></span>
[<span data-ttu-id="24e52-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="24e52-117">put_Content</span></span>](#put_content) | <span data-ttu-id="24e52-118">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="24e52-118">Set the Content property.</span></span>
[<span data-ttu-id="24e52-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="24e52-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="24e52-120">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="24e52-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="24e52-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="24e52-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="24e52-122">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="24e52-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="24e52-123">成员</span><span class="sxs-lookup"><span data-stu-id="24e52-123">Members</span></span>

#### <span data-ttu-id="24e52-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="24e52-124">get_Content</span></span> 

<span data-ttu-id="24e52-125">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="24e52-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="24e52-126">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="24e52-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="24e52-127">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="24e52-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="24e52-128">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="24e52-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="24e52-129">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="24e52-129">Null means no content data.</span></span> <span data-ttu-id="24e52-130">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="24e52-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="24e52-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="24e52-131">get_Headers</span></span> 

<span data-ttu-id="24e52-132">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="24e52-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="24e52-133">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="24e52-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="24e52-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="24e52-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="24e52-135">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="24e52-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="24e52-136">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="24e52-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="24e52-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="24e52-137">get_StatusCode</span></span> 

<span data-ttu-id="24e52-138">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="24e52-138">The HTTP response status code.</span></span>

> <span data-ttu-id="24e52-139">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="24e52-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="24e52-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="24e52-140">put_Content</span></span> 

<span data-ttu-id="24e52-141">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="24e52-141">Set the Content property.</span></span>

> <span data-ttu-id="24e52-142">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="24e52-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="24e52-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="24e52-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="24e52-144">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="24e52-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="24e52-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="24e52-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="24e52-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="24e52-146">put_StatusCode</span></span> 

<span data-ttu-id="24e52-147">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="24e52-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="24e52-148">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="24e52-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

