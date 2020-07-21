---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 077c85b2458c2cf843c4d2f0548d17ec01ba4751
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885959"
---
# <span data-ttu-id="86f9b-104">0.8.355-接口 IWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="86f9b-104">0.8.355 - interface IWebView2HttpResponseHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="86f9b-105">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="86f9b-105">HTTP response headers.</span></span>

## <span data-ttu-id="86f9b-106">摘要</span><span class="sxs-lookup"><span data-stu-id="86f9b-106">Summary</span></span>

 <span data-ttu-id="86f9b-107">成员</span><span class="sxs-lookup"><span data-stu-id="86f9b-107">Members</span></span>                        | <span data-ttu-id="86f9b-108">描述</span><span class="sxs-lookup"><span data-stu-id="86f9b-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="86f9b-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="86f9b-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="86f9b-110">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="86f9b-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="86f9b-111">Contains</span><span class="sxs-lookup"><span data-stu-id="86f9b-111">Contains</span></span>](#contains) | <span data-ttu-id="86f9b-112">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="86f9b-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="86f9b-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="86f9b-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="86f9b-114">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="86f9b-114">Gets the header values matching the name.</span></span>
[<span data-ttu-id="86f9b-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="86f9b-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="86f9b-116">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="86f9b-116">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="86f9b-117">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="86f9b-117">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="86f9b-118">成员</span><span class="sxs-lookup"><span data-stu-id="86f9b-118">Members</span></span>

#### <span data-ttu-id="86f9b-119">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="86f9b-119">AppendHeader</span></span> 

<span data-ttu-id="86f9b-120">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="86f9b-120">Appends header line with name and value.</span></span>

> <span data-ttu-id="86f9b-121">公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="86f9b-121">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="86f9b-122">Contains</span><span class="sxs-lookup"><span data-stu-id="86f9b-122">Contains</span></span> 

<span data-ttu-id="86f9b-123">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="86f9b-123">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="86f9b-124">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="86f9b-124">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="86f9b-125">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="86f9b-125">GetHeaders</span></span> 

<span data-ttu-id="86f9b-126">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="86f9b-126">Gets the header values matching the name.</span></span>

> <span data-ttu-id="86f9b-127">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="86f9b-127">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="86f9b-128">GetIterator</span><span class="sxs-lookup"><span data-stu-id="86f9b-128">GetIterator</span></span> 

<span data-ttu-id="86f9b-129">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="86f9b-129">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="86f9b-130">公共 HRESULT [GetIterator](#getiterator)（[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="86f9b-130">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

