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
ms.openlocfilehash: 63044cae80aebfb1e759070ec797673b0c9378d2
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697250"
---
# <span data-ttu-id="7a188-104">interface ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="7a188-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="7a188-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="7a188-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="7a188-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="7a188-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="7a188-107">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="7a188-107">HTTP response headers.</span></span>

## <span data-ttu-id="7a188-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7a188-108">Summary</span></span>

 <span data-ttu-id="7a188-109">成员</span><span class="sxs-lookup"><span data-stu-id="7a188-109">Members</span></span>                        | <span data-ttu-id="7a188-110">描述</span><span class="sxs-lookup"><span data-stu-id="7a188-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7a188-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="7a188-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="7a188-112">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="7a188-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="7a188-113">Contains</span><span class="sxs-lookup"><span data-stu-id="7a188-113">Contains</span></span>](#contains) | <span data-ttu-id="7a188-114">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="7a188-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="7a188-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="7a188-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="7a188-116">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="7a188-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="7a188-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="7a188-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="7a188-118">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="7a188-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="7a188-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="7a188-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="7a188-120">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="7a188-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="7a188-121">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="7a188-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="7a188-122">成员</span><span class="sxs-lookup"><span data-stu-id="7a188-122">Members</span></span>

#### <span data-ttu-id="7a188-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="7a188-123">AppendHeader</span></span> 

<span data-ttu-id="7a188-124">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="7a188-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="7a188-125">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="7a188-125">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="7a188-126">Contains</span><span class="sxs-lookup"><span data-stu-id="7a188-126">Contains</span></span> 

<span data-ttu-id="7a188-127">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="7a188-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="7a188-128">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="7a188-128">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="7a188-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="7a188-129">GetHeader</span></span> 

<span data-ttu-id="7a188-130">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="7a188-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="7a188-131">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="7a188-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="7a188-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="7a188-132">GetHeaders</span></span> 

<span data-ttu-id="7a188-133">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="7a188-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="7a188-134">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="7a188-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="7a188-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="7a188-135">GetIterator</span></span> 

<span data-ttu-id="7a188-136">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="7a188-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="7a188-137">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="7a188-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

