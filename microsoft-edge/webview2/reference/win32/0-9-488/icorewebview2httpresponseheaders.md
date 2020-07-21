---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1daa6c3cdf03ce160968d43715f12ffa7eb41e84
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885581"
---
# <span data-ttu-id="fde7d-104">0.9.515-接口 ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="fde7d-104">0.9.515 - interface ICoreWebView2HttpResponseHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="fde7d-105">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="fde7d-105">HTTP response headers.</span></span>

## <span data-ttu-id="fde7d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fde7d-106">Summary</span></span>

 <span data-ttu-id="fde7d-107">成员</span><span class="sxs-lookup"><span data-stu-id="fde7d-107">Members</span></span>                        | <span data-ttu-id="fde7d-108">描述</span><span class="sxs-lookup"><span data-stu-id="fde7d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fde7d-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="fde7d-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="fde7d-110">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="fde7d-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="fde7d-111">Contains</span><span class="sxs-lookup"><span data-stu-id="fde7d-111">Contains</span></span>](#contains) | <span data-ttu-id="fde7d-112">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="fde7d-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="fde7d-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="fde7d-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="fde7d-114">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="fde7d-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="fde7d-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="fde7d-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="fde7d-116">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="fde7d-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="fde7d-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="fde7d-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="fde7d-118">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="fde7d-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="fde7d-119">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="fde7d-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="fde7d-120">成员</span><span class="sxs-lookup"><span data-stu-id="fde7d-120">Members</span></span>

#### <span data-ttu-id="fde7d-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="fde7d-121">AppendHeader</span></span> 

<span data-ttu-id="fde7d-122">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="fde7d-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="fde7d-123">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="fde7d-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="fde7d-124">Contains</span><span class="sxs-lookup"><span data-stu-id="fde7d-124">Contains</span></span> 

<span data-ttu-id="fde7d-125">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="fde7d-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="fde7d-126">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="fde7d-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="fde7d-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="fde7d-127">GetHeader</span></span> 

<span data-ttu-id="fde7d-128">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="fde7d-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="fde7d-129">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="fde7d-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="fde7d-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="fde7d-130">GetHeaders</span></span> 

<span data-ttu-id="fde7d-131">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="fde7d-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="fde7d-132">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="fde7d-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="fde7d-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="fde7d-133">GetIterator</span></span> 

<span data-ttu-id="fde7d-134">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="fde7d-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="fde7d-135">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="fde7d-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

