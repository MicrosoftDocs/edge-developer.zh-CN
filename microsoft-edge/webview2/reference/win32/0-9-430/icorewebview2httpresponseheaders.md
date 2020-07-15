---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 44f7477eaa81198ef64d332faa0c3a22225d5ea4
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880967"
---
# <span data-ttu-id="3cd38-104">0.9.430-接口 ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="3cd38-104">0.9.430 - interface ICoreWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="3cd38-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="3cd38-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="3cd38-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="3cd38-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="3cd38-107">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="3cd38-107">HTTP response headers.</span></span>

## <span data-ttu-id="3cd38-108">摘要</span><span class="sxs-lookup"><span data-stu-id="3cd38-108">Summary</span></span>

 <span data-ttu-id="3cd38-109">成员</span><span class="sxs-lookup"><span data-stu-id="3cd38-109">Members</span></span>                        | <span data-ttu-id="3cd38-110">描述</span><span class="sxs-lookup"><span data-stu-id="3cd38-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3cd38-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="3cd38-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="3cd38-112">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="3cd38-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="3cd38-113">Contains</span><span class="sxs-lookup"><span data-stu-id="3cd38-113">Contains</span></span>](#contains) | <span data-ttu-id="3cd38-114">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="3cd38-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="3cd38-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="3cd38-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="3cd38-116">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="3cd38-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="3cd38-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="3cd38-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="3cd38-118">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="3cd38-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="3cd38-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="3cd38-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="3cd38-120">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="3cd38-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="3cd38-121">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="3cd38-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="3cd38-122">成员</span><span class="sxs-lookup"><span data-stu-id="3cd38-122">Members</span></span>

#### <span data-ttu-id="3cd38-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="3cd38-123">AppendHeader</span></span> 

<span data-ttu-id="3cd38-124">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="3cd38-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="3cd38-125">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="3cd38-125">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="3cd38-126">Contains</span><span class="sxs-lookup"><span data-stu-id="3cd38-126">Contains</span></span> 

<span data-ttu-id="3cd38-127">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="3cd38-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="3cd38-128">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="3cd38-128">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="3cd38-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="3cd38-129">GetHeader</span></span> 

<span data-ttu-id="3cd38-130">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="3cd38-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="3cd38-131">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="3cd38-131">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="3cd38-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="3cd38-132">GetHeaders</span></span> 

<span data-ttu-id="3cd38-133">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="3cd38-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="3cd38-134">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="3cd38-134">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="3cd38-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="3cd38-135">GetIterator</span></span> 

<span data-ttu-id="3cd38-136">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="3cd38-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="3cd38-137">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="3cd38-137">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

