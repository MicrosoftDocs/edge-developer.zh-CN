---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2HttpResponseHeaders
ms.openlocfilehash: 1622d2c19159bca76e036408810e2ca145d30e85
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011690"
---
# <span data-ttu-id="eceee-104">interface ICoreWebView2HttpResponseHeaders</span><span class="sxs-lookup"><span data-stu-id="eceee-104">interface ICoreWebView2HttpResponseHeaders</span></span> 

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

<span data-ttu-id="eceee-105">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="eceee-105">HTTP response headers.</span></span>

## <span data-ttu-id="eceee-106">摘要</span><span class="sxs-lookup"><span data-stu-id="eceee-106">Summary</span></span>

 <span data-ttu-id="eceee-107">成员</span><span class="sxs-lookup"><span data-stu-id="eceee-107">Members</span></span>                        | <span data-ttu-id="eceee-108">描述</span><span class="sxs-lookup"><span data-stu-id="eceee-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="eceee-109">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="eceee-109">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="eceee-110">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="eceee-110">Appends header line with name and value.</span></span>
[<span data-ttu-id="eceee-111">Contains</span><span class="sxs-lookup"><span data-stu-id="eceee-111">Contains</span></span>](#contains) | <span data-ttu-id="eceee-112">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="eceee-112">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="eceee-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="eceee-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="eceee-114">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="eceee-114">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="eceee-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="eceee-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="eceee-116">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="eceee-116">Gets the header values matching the name.</span></span>
[<span data-ttu-id="eceee-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="eceee-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="eceee-118">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="eceee-118">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="eceee-119">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="eceee-119">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="eceee-120">成员</span><span class="sxs-lookup"><span data-stu-id="eceee-120">Members</span></span>

#### <span data-ttu-id="eceee-121">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="eceee-121">AppendHeader</span></span> 

<span data-ttu-id="eceee-122">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="eceee-122">Appends header line with name and value.</span></span>

> <span data-ttu-id="eceee-123">public HRESULT [AppendHeader](#appendheader) (LPCWSTR NAME，LPCWSTR 值) </span><span class="sxs-lookup"><span data-stu-id="eceee-123">public HRESULT [AppendHeader](#appendheader)(LPCWSTR name, LPCWSTR value)</span></span>

#### <span data-ttu-id="eceee-124">Contains</span><span class="sxs-lookup"><span data-stu-id="eceee-124">Contains</span></span> 

<span data-ttu-id="eceee-125">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="eceee-125">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="eceee-126">public HRESULT [包含](#contains) (LPCWSTR NAME，BOOL \* 包含) </span><span class="sxs-lookup"><span data-stu-id="eceee-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="eceee-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="eceee-127">GetHeader</span></span> 

<span data-ttu-id="eceee-128">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="eceee-128">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="eceee-129">public HRESULT [GetHeader](#getheader) (LPCWSTR NAME，LPWSTR \* value) </span><span class="sxs-lookup"><span data-stu-id="eceee-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="eceee-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="eceee-130">GetHeaders</span></span> 

<span data-ttu-id="eceee-131">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="eceee-131">Gets the header values matching the name.</span></span>

> <span data-ttu-id="eceee-132">公共 HRESULT [GetHeaders](#getheaders) (LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器) </span><span class="sxs-lookup"><span data-stu-id="eceee-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="eceee-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="eceee-133">GetIterator</span></span> 

<span data-ttu-id="eceee-134">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="eceee-134">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="eceee-135">公共 HRESULT [GetIterator](#getiterator) ([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器) </span><span class="sxs-lookup"><span data-stu-id="eceee-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

