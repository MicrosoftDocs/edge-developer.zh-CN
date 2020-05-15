---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b23b724977b9d164c48dc99d0da2e64d61539549
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653159"
---
# <span data-ttu-id="7c2ea-104">interface ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="7c2ea-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="7c2ea-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="7c2ea-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="7c2ea-107">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-107">HTTP response headers.</span></span>

## <span data-ttu-id="7c2ea-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7c2ea-108">Summary</span></span>

 <span data-ttu-id="7c2ea-109">成员</span><span class="sxs-lookup"><span data-stu-id="7c2ea-109">Members</span></span>                        | <span data-ttu-id="7c2ea-110">描述</span><span class="sxs-lookup"><span data-stu-id="7c2ea-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7c2ea-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="7c2ea-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="7c2ea-112">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="7c2ea-113">Contains</span><span class="sxs-lookup"><span data-stu-id="7c2ea-113">Contains</span></span>](#contains) | <span data-ttu-id="7c2ea-114">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="7c2ea-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="7c2ea-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="7c2ea-116">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="7c2ea-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="7c2ea-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="7c2ea-118">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="7c2ea-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="7c2ea-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="7c2ea-120">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="7c2ea-121">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="7c2ea-122">成员</span><span class="sxs-lookup"><span data-stu-id="7c2ea-122">Members</span></span>

#### <span data-ttu-id="7c2ea-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="7c2ea-123">AppendHeader</span></span> 

<span data-ttu-id="7c2ea-124">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="7c2ea-125">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="7c2ea-125">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="7c2ea-126">Contains</span><span class="sxs-lookup"><span data-stu-id="7c2ea-126">Contains</span></span> 

<span data-ttu-id="7c2ea-127">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="7c2ea-128">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="7c2ea-128">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="7c2ea-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="7c2ea-129">GetHeader</span></span> 

<span data-ttu-id="7c2ea-130">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="7c2ea-131">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="7c2ea-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="7c2ea-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="7c2ea-132">GetHeaders</span></span> 

<span data-ttu-id="7c2ea-133">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="7c2ea-134">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="7c2ea-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="7c2ea-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="7c2ea-135">GetIterator</span></span> 

<span data-ttu-id="7c2ea-136">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="7c2ea-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="7c2ea-137">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="7c2ea-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

