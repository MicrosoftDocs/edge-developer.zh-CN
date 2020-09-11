---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2HttpResponseHeaders
ms.openlocfilehash: 6278f29f983503916e0015ab4bbac44f79ffe3d9
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011305"
---
# <span data-ttu-id="c907a-104">0.9.579-接口 ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="c907a-104">0.9.579 - interface ICoreWebView2HttpResponseHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="c907a-105">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="c907a-105">HTTP response headers.</span></span>

## <span data-ttu-id="c907a-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c907a-106">Summary</span></span>

 <span data-ttu-id="c907a-107">成员</span><span class="sxs-lookup"><span data-stu-id="c907a-107">Members</span></span>                        | <span data-ttu-id="c907a-108">描述</span><span class="sxs-lookup"><span data-stu-id="c907a-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c907a-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="c907a-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="c907a-110">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="c907a-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="c907a-111">Contains</span><span class="sxs-lookup"><span data-stu-id="c907a-111">Contains</span></span>](#contains) | <span data-ttu-id="c907a-112">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="c907a-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="c907a-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="c907a-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="c907a-114">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="c907a-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="c907a-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c907a-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="c907a-116">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c907a-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="c907a-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c907a-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="c907a-118">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c907a-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="c907a-119">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="c907a-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="c907a-120">成员</span><span class="sxs-lookup"><span data-stu-id="c907a-120">Members</span></span>

#### <span data-ttu-id="c907a-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="c907a-121">AppendHeader</span></span> 

<span data-ttu-id="c907a-122">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="c907a-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="c907a-123">public HRESULT [AppendHeader](#appendheader) (LPCWSTR NAME，LPCWSTR 值) </span><span class="sxs-lookup"><span data-stu-id="c907a-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="c907a-124">Contains</span><span class="sxs-lookup"><span data-stu-id="c907a-124">Contains</span></span> 

<span data-ttu-id="c907a-125">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="c907a-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="c907a-126">public HRESULT [包含](#contains) (LPCWSTR NAME，BOOL \* 包含) </span><span class="sxs-lookup"><span data-stu-id="c907a-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="c907a-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="c907a-127">GetHeader</span></span> 

<span data-ttu-id="c907a-128">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="c907a-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="c907a-129">public HRESULT [GetHeader](#getheader) (LPCWSTR NAME，LPWSTR \* value) </span><span class="sxs-lookup"><span data-stu-id="c907a-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="c907a-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c907a-130">GetHeaders</span></span> 

<span data-ttu-id="c907a-131">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c907a-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="c907a-132">公共 HRESULT [GetHeaders](#getheaders) (LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器) </span><span class="sxs-lookup"><span data-stu-id="c907a-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="c907a-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c907a-133">GetIterator</span></span> 

<span data-ttu-id="c907a-134">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c907a-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="c907a-135">公共 HRESULT [GetIterator](#getiterator) ([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器) </span><span class="sxs-lookup"><span data-stu-id="c907a-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

