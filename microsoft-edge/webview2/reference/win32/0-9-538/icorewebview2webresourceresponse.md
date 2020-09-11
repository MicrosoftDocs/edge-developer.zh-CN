---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceResponse
ms.openlocfilehash: f94aa86f589f49930de9186cdca4a6ae943d286f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011380"
---
# <span data-ttu-id="f8087-104">0.9.579-接口 ICoreWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="f8087-104">0.9.579 - interface ICoreWebView2WebResourceResponse</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="f8087-105">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="f8087-105">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="f8087-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f8087-106">Summary</span></span>

 <span data-ttu-id="f8087-107">成员</span><span class="sxs-lookup"><span data-stu-id="f8087-107">Members</span></span>                        | <span data-ttu-id="f8087-108">描述</span><span class="sxs-lookup"><span data-stu-id="f8087-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f8087-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="f8087-109">get_Content</span></span>](#get_content) | <span data-ttu-id="f8087-110">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="f8087-110">HTTP response content as stream.</span></span>
[<span data-ttu-id="f8087-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="f8087-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="f8087-112">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="f8087-112">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="f8087-113">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="f8087-113">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="f8087-114">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="f8087-114">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="f8087-115">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="f8087-115">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="f8087-116">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="f8087-116">The HTTP response status code.</span></span>
[<span data-ttu-id="f8087-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="f8087-117">put_Content</span></span>](#put_content) | <span data-ttu-id="f8087-118">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="f8087-118">Set the Content property.</span></span>
[<span data-ttu-id="f8087-119">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="f8087-119">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="f8087-120">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="f8087-120">Set the ReasonPhrase property.</span></span>
[<span data-ttu-id="f8087-121">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="f8087-121">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="f8087-122">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="f8087-122">Set the StatusCode property.</span></span>

## <span data-ttu-id="f8087-123">成员</span><span class="sxs-lookup"><span data-stu-id="f8087-123">Members</span></span>

#### <span data-ttu-id="f8087-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="f8087-124">get_Content</span></span> 

<span data-ttu-id="f8087-125">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="f8087-125">HTTP response content as stream.</span></span>

> <span data-ttu-id="f8087-126">公共 HRESULT [get_Content](#get_content) (IStream \* \* 内容) </span><span class="sxs-lookup"><span data-stu-id="f8087-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="f8087-127">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="f8087-127">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="f8087-128">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="f8087-128">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="f8087-129">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="f8087-129">Null means no content data.</span></span> <span data-ttu-id="f8087-130">IStream 语义将应用 (返回 S_OK 以读取调用，直到所有数据耗尽) </span><span class="sxs-lookup"><span data-stu-id="f8087-130">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="f8087-131">get_Headers</span><span class="sxs-lookup"><span data-stu-id="f8087-131">get_Headers</span></span> 

<span data-ttu-id="f8087-132">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="f8087-132">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="f8087-133">公共 HRESULT [get_Headers](#get_headers) ([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \* \* 标题) </span><span class="sxs-lookup"><span data-stu-id="f8087-133">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpResponseHeaders](icorewebview2httpresponseheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="f8087-134">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="f8087-134">get_ReasonPhrase</span></span> 

<span data-ttu-id="f8087-135">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="f8087-135">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="f8087-136">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase) (LPWSTR \* ReasonPhrase) </span><span class="sxs-lookup"><span data-stu-id="f8087-136">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="f8087-137">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="f8087-137">get_StatusCode</span></span> 

<span data-ttu-id="f8087-138">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="f8087-138">The HTTP response status code.</span></span>

> <span data-ttu-id="f8087-139">公共 HRESULT [get_StatusCode](#get_statuscode) (Int \* StatusCode) </span><span class="sxs-lookup"><span data-stu-id="f8087-139">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="f8087-140">put_Content</span><span class="sxs-lookup"><span data-stu-id="f8087-140">put_Content</span></span> 

<span data-ttu-id="f8087-141">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="f8087-141">Set the Content property.</span></span>

> <span data-ttu-id="f8087-142">公共 HRESULT [put_Content](#put_content) (IStream \* 内容) </span><span class="sxs-lookup"><span data-stu-id="f8087-142">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="f8087-143">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="f8087-143">put_ReasonPhrase</span></span> 

<span data-ttu-id="f8087-144">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="f8087-144">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="f8087-145">公共 HRESULT [put_ReasonPhrase](#put_reasonphrase) (LPCWSTR ReasonPhrase) </span><span class="sxs-lookup"><span data-stu-id="f8087-145">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

#### <span data-ttu-id="f8087-146">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="f8087-146">put_StatusCode</span></span> 

<span data-ttu-id="f8087-147">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="f8087-147">Set the StatusCode property.</span></span>

> <span data-ttu-id="f8087-148">公共 HRESULT [put_StatusCode](#put_statuscode) (int StatusCode) </span><span class="sxs-lookup"><span data-stu-id="f8087-148">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

