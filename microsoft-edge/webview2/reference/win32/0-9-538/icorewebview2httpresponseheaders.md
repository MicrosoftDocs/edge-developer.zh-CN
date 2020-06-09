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
ms.openlocfilehash: 508ecacc867330c73132ae7e446b7483ea002f83
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698540"
---
# <span data-ttu-id="a328c-104">interface ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="a328c-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="a328c-105">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="a328c-105">HTTP response headers.</span></span>

## <span data-ttu-id="a328c-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a328c-106">Summary</span></span>

 <span data-ttu-id="a328c-107">成员</span><span class="sxs-lookup"><span data-stu-id="a328c-107">Members</span></span>                        | <span data-ttu-id="a328c-108">描述</span><span class="sxs-lookup"><span data-stu-id="a328c-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a328c-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="a328c-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="a328c-110">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="a328c-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="a328c-111">Contains</span><span class="sxs-lookup"><span data-stu-id="a328c-111">Contains</span></span>](#contains) | <span data-ttu-id="a328c-112">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="a328c-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="a328c-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="a328c-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="a328c-114">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="a328c-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="a328c-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="a328c-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="a328c-116">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="a328c-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="a328c-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="a328c-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="a328c-118">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="a328c-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="a328c-119">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="a328c-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="a328c-120">成员</span><span class="sxs-lookup"><span data-stu-id="a328c-120">Members</span></span>

#### <span data-ttu-id="a328c-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="a328c-121">AppendHeader</span></span> 

<span data-ttu-id="a328c-122">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="a328c-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="a328c-123">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="a328c-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="a328c-124">Contains</span><span class="sxs-lookup"><span data-stu-id="a328c-124">Contains</span></span> 

<span data-ttu-id="a328c-125">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="a328c-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="a328c-126">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="a328c-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="a328c-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="a328c-127">GetHeader</span></span> 

<span data-ttu-id="a328c-128">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="a328c-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="a328c-129">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="a328c-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="a328c-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="a328c-130">GetHeaders</span></span> 

<span data-ttu-id="a328c-131">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="a328c-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="a328c-132">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="a328c-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="a328c-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="a328c-133">GetIterator</span></span> 

<span data-ttu-id="a328c-134">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="a328c-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="a328c-135">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="a328c-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

