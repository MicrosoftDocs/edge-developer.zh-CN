---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 04a8bf376ad7649021c4ab1555c3090cce5b52fb
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885609"
---
# <span data-ttu-id="c201e-104">0.9.430-接口 ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="c201e-104">0.9.430 - interface ICoreWebView2HttpRequestHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="c201e-105">HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c201e-105">HTTP request headers.</span></span>

## <span data-ttu-id="c201e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c201e-106">Summary</span></span>

 <span data-ttu-id="c201e-107">成员</span><span class="sxs-lookup"><span data-stu-id="c201e-107">Members</span></span>                        | <span data-ttu-id="c201e-108">描述</span><span class="sxs-lookup"><span data-stu-id="c201e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c201e-109">GetHeader</span><span class="sxs-lookup"><span data-stu-id="c201e-109">GetHeader</span></span>](#getheader) | <span data-ttu-id="c201e-110">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c201e-110">Gets the header value matching the name.</span></span>
[<span data-ttu-id="c201e-111">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c201e-111">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="c201e-112">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c201e-112">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="c201e-113">Contains</span><span class="sxs-lookup"><span data-stu-id="c201e-113">Contains</span></span>](#contains) | <span data-ttu-id="c201e-114">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="c201e-114">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="c201e-115">SetHeader</span><span class="sxs-lookup"><span data-stu-id="c201e-115">SetHeader</span></span>](#setheader) | <span data-ttu-id="c201e-116">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="c201e-116">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="c201e-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="c201e-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="c201e-118">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="c201e-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="c201e-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c201e-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="c201e-120">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c201e-120">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="c201e-121">用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="c201e-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="c201e-122">注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c201e-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="c201e-123">成员</span><span class="sxs-lookup"><span data-stu-id="c201e-123">Members</span></span>

#### <span data-ttu-id="c201e-124">GetHeader</span><span class="sxs-lookup"><span data-stu-id="c201e-124">GetHeader</span></span> 

<span data-ttu-id="c201e-125">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c201e-125">Gets the header value matching the name.</span></span>

> <span data-ttu-id="c201e-126">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="c201e-126">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="c201e-127">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="c201e-127">GetHeaders</span></span> 

<span data-ttu-id="c201e-128">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="c201e-128">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="c201e-129">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="c201e-129">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="c201e-130">Contains</span><span class="sxs-lookup"><span data-stu-id="c201e-130">Contains</span></span> 

<span data-ttu-id="c201e-131">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="c201e-131">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="c201e-132">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="c201e-132">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="c201e-133">SetHeader</span><span class="sxs-lookup"><span data-stu-id="c201e-133">SetHeader</span></span> 

<span data-ttu-id="c201e-134">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="c201e-134">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="c201e-135">公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="c201e-135">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="c201e-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="c201e-136">RemoveHeader</span></span> 

<span data-ttu-id="c201e-137">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="c201e-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="c201e-138">公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="c201e-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="c201e-139">GetIterator</span><span class="sxs-lookup"><span data-stu-id="c201e-139">GetIterator</span></span> 

<span data-ttu-id="c201e-140">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="c201e-140">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="c201e-141">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="c201e-141">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

