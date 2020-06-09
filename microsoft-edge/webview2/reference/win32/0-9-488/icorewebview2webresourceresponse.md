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
ms.openlocfilehash: 5b80691f0e42be4cdea7c99b165bfe9cebf632dd
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697929"
---
# <span data-ttu-id="9b1ba-104">interface ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="9b1ba-104">interface ICoreWebView2WebResourceResponse</span></span> 

> [!NOTE]
> <span data-ttu-id="9b1ba-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="9b1ba-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="9b1ba-107">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="9b1ba-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9b1ba-108">Summary</span></span>

 <span data-ttu-id="9b1ba-109">成员</span><span class="sxs-lookup"><span data-stu-id="9b1ba-109">Members</span></span>                        | <span data-ttu-id="9b1ba-110">描述</span><span class="sxs-lookup"><span data-stu-id="9b1ba-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9b1ba-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="9b1ba-111">get_Content</span></span>](#get_content) | <span data-ttu-id="9b1ba-112">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="9b1ba-113">get_Headers</span><span class="sxs-lookup"><span data-stu-id="9b1ba-113">get_Headers</span></span>](#get_headers) | <span data-ttu-id="9b1ba-114">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="9b1ba-115">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9b1ba-115">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="9b1ba-116">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-116">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="9b1ba-117">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9b1ba-117">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="9b1ba-118">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-118">The HTTP response status code.</span></span>
[<span data-ttu-id="9b1ba-119">put_Content</span><span class="sxs-lookup"><span data-stu-id="9b1ba-119">put_Content</span></span>](#put_content) | <span data-ttu-id="9b1ba-120">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-120">Set the Content property.</span></span>
[<span data-ttu-id="9b1ba-121">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9b1ba-121">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="9b1ba-122">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-122">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="9b1ba-123">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9b1ba-123">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="9b1ba-124">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-124">Set the StatusCode property.</span></span>

## <span data-ttu-id="9b1ba-125">成员</span><span class="sxs-lookup"><span data-stu-id="9b1ba-125">Members</span></span>

#### <span data-ttu-id="9b1ba-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="9b1ba-126">get_Content</span></span> 

<span data-ttu-id="9b1ba-127">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-127">HTTP response content as stream.</span></span>

> <span data-ttu-id="9b1ba-128">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="9b1ba-129">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-129">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="9b1ba-130">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-130">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="9b1ba-131">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-131">Null means no content data.</span></span> <span data-ttu-id="9b1ba-132">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-132">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="9b1ba-133">get_Headers</span><span class="sxs-lookup"><span data-stu-id="9b1ba-133">get_Headers</span></span> 

<span data-ttu-id="9b1ba-134">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-134">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="9b1ba-135">公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-135">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="9b1ba-136">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9b1ba-136">get_ReasonPhrase</span></span> 

<span data-ttu-id="9b1ba-137">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-137">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="9b1ba-138">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-138">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="9b1ba-139">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9b1ba-139">get_StatusCode</span></span> 

<span data-ttu-id="9b1ba-140">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-140">The HTTP response status code.</span></span>

> <span data-ttu-id="9b1ba-141">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-141">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="9b1ba-142">put_Content</span><span class="sxs-lookup"><span data-stu-id="9b1ba-142">put_Content</span></span> 

<span data-ttu-id="9b1ba-143">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-143">Set the Content property.</span></span>

> <span data-ttu-id="9b1ba-144">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-144">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="9b1ba-145">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="9b1ba-145">put_ReasonPhrase</span></span> 

<span data-ttu-id="9b1ba-146">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-146">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="9b1ba-147">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-147">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="9b1ba-148">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="9b1ba-148">put_StatusCode</span></span> 

<span data-ttu-id="9b1ba-149">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="9b1ba-149">Set the StatusCode property.</span></span>

> <span data-ttu-id="9b1ba-150">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="9b1ba-150">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

