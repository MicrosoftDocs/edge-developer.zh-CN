---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: ad3f4e5e95b0309628644f17e5d647ab6d4af658
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652858"
---
# <span data-ttu-id="6c102-104">interface IWebView2WebResourceResponse</span><span class="sxs-lookup"><span data-stu-id="6c102-104">interface IWebView2WebResourceResponse</span></span> 

> [!NOTE]
> <span data-ttu-id="6c102-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="6c102-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="6c102-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="6c102-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceResponse
  : public IUnknown
```

<span data-ttu-id="6c102-107">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="6c102-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="6c102-108">摘要</span><span class="sxs-lookup"><span data-stu-id="6c102-108">Summary</span></span>

 <span data-ttu-id="6c102-109">成员</span><span class="sxs-lookup"><span data-stu-id="6c102-109">Members</span></span>                        | <span data-ttu-id="6c102-110">描述</span><span class="sxs-lookup"><span data-stu-id="6c102-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6c102-111">get_Content</span><span class="sxs-lookup"><span data-stu-id="6c102-111">get_Content</span></span>](#get_content) | <span data-ttu-id="6c102-112">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="6c102-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="6c102-113">put_Content</span><span class="sxs-lookup"><span data-stu-id="6c102-113">put_Content</span></span>](#put_content) | <span data-ttu-id="6c102-114">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="6c102-114">Set the Content property.</span></span>
[<span data-ttu-id="6c102-115">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6c102-115">get_Headers</span></span>](#get_headers) | <span data-ttu-id="6c102-116">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="6c102-116">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="6c102-117">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c102-117">get_StatusCode</span></span>](#get_statuscode) | <span data-ttu-id="6c102-118">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="6c102-118">The HTTP response status code.</span></span>
[<span data-ttu-id="6c102-119">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c102-119">put_StatusCode</span></span>](#put_statuscode) | <span data-ttu-id="6c102-120">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="6c102-120">Set the StatusCode property.</span></span>
[<span data-ttu-id="6c102-121">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c102-121">get_ReasonPhrase</span></span>](#get_reasonphrase) | <span data-ttu-id="6c102-122">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="6c102-122">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="6c102-123">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c102-123">put_ReasonPhrase</span></span>](#put_reasonphrase) | <span data-ttu-id="6c102-124">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="6c102-124">Set the ReasonPhrase property.</span></span>

## <span data-ttu-id="6c102-125">成员</span><span class="sxs-lookup"><span data-stu-id="6c102-125">Members</span></span>

#### <span data-ttu-id="6c102-126">get_Content</span><span class="sxs-lookup"><span data-stu-id="6c102-126">get_Content</span></span> 

<span data-ttu-id="6c102-127">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="6c102-127">HTTP response content as stream.</span></span>

> <span data-ttu-id="6c102-128">公共 HRESULT [get_Content](#get_content)（IStream \* \* 内容）</span><span class="sxs-lookup"><span data-stu-id="6c102-128">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="6c102-129">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="6c102-129">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="6c102-130">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="6c102-130">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="6c102-131">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="6c102-131">Null means no content data.</span></span> <span data-ttu-id="6c102-132">将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）</span><span class="sxs-lookup"><span data-stu-id="6c102-132">IStream semantics apply (return S_OK to Read calls until all data is exhausted)</span></span>

#### <span data-ttu-id="6c102-133">put_Content</span><span class="sxs-lookup"><span data-stu-id="6c102-133">put_Content</span></span> 

<span data-ttu-id="6c102-134">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="6c102-134">Set the Content property.</span></span>

> <span data-ttu-id="6c102-135">公共 HRESULT [put_Content](#put_content)（IStream \* 内容）</span><span class="sxs-lookup"><span data-stu-id="6c102-135">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="6c102-136">get_Headers</span><span class="sxs-lookup"><span data-stu-id="6c102-136">get_Headers</span></span> 

<span data-ttu-id="6c102-137">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="6c102-137">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="6c102-138">公共 HRESULT [get_Headers](#get_headers)（[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \* \* 标题）</span><span class="sxs-lookup"><span data-stu-id="6c102-138">public HRESULT [get_Headers](#get_headers)([IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="6c102-139">get_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c102-139">get_StatusCode</span></span> 

<span data-ttu-id="6c102-140">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="6c102-140">The HTTP response status code.</span></span>

> <span data-ttu-id="6c102-141">公共 HRESULT [get_StatusCode](#get_statuscode)（Int \* StatusCode）</span><span class="sxs-lookup"><span data-stu-id="6c102-141">public HRESULT [get_StatusCode](#get_statuscode)(int \* statusCode)</span></span>

#### <span data-ttu-id="6c102-142">put_StatusCode</span><span class="sxs-lookup"><span data-stu-id="6c102-142">put_StatusCode</span></span> 

<span data-ttu-id="6c102-143">设置 StatusCode 属性。</span><span class="sxs-lookup"><span data-stu-id="6c102-143">Set the StatusCode property.</span></span>

> <span data-ttu-id="6c102-144">公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）</span><span class="sxs-lookup"><span data-stu-id="6c102-144">public HRESULT [put_StatusCode](#put_statuscode)(int statusCode)</span></span>

#### <span data-ttu-id="6c102-145">get_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c102-145">get_ReasonPhrase</span></span> 

<span data-ttu-id="6c102-146">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="6c102-146">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="6c102-147">公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR \* ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="6c102-147">public HRESULT [get_ReasonPhrase](#get_reasonphrase)(LPWSTR \* reasonPhrase)</span></span>

#### <span data-ttu-id="6c102-148">put_ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="6c102-148">put_ReasonPhrase</span></span> 

<span data-ttu-id="6c102-149">设置 ReasonPhrase 属性。</span><span class="sxs-lookup"><span data-stu-id="6c102-149">Set the ReasonPhrase property.</span></span>

> <span data-ttu-id="6c102-150">public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）</span><span class="sxs-lookup"><span data-stu-id="6c102-150">public HRESULT [put_ReasonPhrase](#put_reasonphrase)(LPCWSTR reasonPhrase)</span></span>

