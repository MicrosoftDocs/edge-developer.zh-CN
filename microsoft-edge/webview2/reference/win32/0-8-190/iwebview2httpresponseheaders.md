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
ms.openlocfilehash: 0f3564fa96bc1c13527cbf3b26ce92114d44eae4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653006"
---
# <span data-ttu-id="c1fc2-104">interface IWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="c1fc2-104">interface IWebView2HttpResponseHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="c1fc2-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="c1fc2-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="c1fc2-107">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-107">HTTP response headers.</span></span>

## <span data-ttu-id="c1fc2-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c1fc2-108">Summary</span></span>

 <span data-ttu-id="c1fc2-109">成员</span><span class="sxs-lookup"><span data-stu-id="c1fc2-109">Members</span></span>                        | <span data-ttu-id="c1fc2-110">描述</span><span class="sxs-lookup"><span data-stu-id="c1fc2-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c1fc2-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="c1fc2-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="c1fc2-112">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="c1fc2-113">Contains</span><span class="sxs-lookup"><span data-stu-id="c1fc2-113">Contains</span></span>](#contains) | <span data-ttu-id="c1fc2-114">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="c1fc2-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c1fc2-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="c1fc2-116">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="c1fc2-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c1fc2-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="c1fc2-118">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="c1fc2-119">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="c1fc2-120">成员</span><span class="sxs-lookup"><span data-stu-id="c1fc2-120">Members</span></span>

#### <span data-ttu-id="c1fc2-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="c1fc2-121">AppendHeader</span></span> 

<span data-ttu-id="c1fc2-122">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="c1fc2-123">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="c1fc2-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="c1fc2-124">Contains</span><span class="sxs-lookup"><span data-stu-id="c1fc2-124">Contains</span></span> 

<span data-ttu-id="c1fc2-125">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="c1fc2-126">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="c1fc2-126">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="c1fc2-127">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c1fc2-127">GetHeaders</span></span> 

<span data-ttu-id="c1fc2-128">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-128">Gets the header values matching the name.</span></span>

> <span data-ttu-id="c1fc2-129">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="c1fc2-129">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="c1fc2-130">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c1fc2-130">GetIterator</span></span> 

<span data-ttu-id="c1fc2-131">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c1fc2-131">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="c1fc2-132">公共 HRESULT [GetIterator](#getiterator)（[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="c1fc2-132">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

