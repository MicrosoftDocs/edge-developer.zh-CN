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
ms.openlocfilehash: 19018ff63b62b0d76bed6dcce9cf1dbce2a37b11
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698455"
---
# <span data-ttu-id="364e3-104">interface ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="364e3-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="364e3-105">HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="364e3-105">HTTP request headers.</span></span>

## <span data-ttu-id="364e3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="364e3-106">Summary</span></span>

 <span data-ttu-id="364e3-107">成员</span><span class="sxs-lookup"><span data-stu-id="364e3-107">Members</span></span>                        | <span data-ttu-id="364e3-108">描述</span><span class="sxs-lookup"><span data-stu-id="364e3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="364e3-109">Contains</span><span class="sxs-lookup"><span data-stu-id="364e3-109">Contains</span></span>](#contains) | <span data-ttu-id="364e3-110">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="364e3-110">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="364e3-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="364e3-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="364e3-112">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="364e3-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="364e3-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="364e3-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="364e3-114">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="364e3-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="364e3-115">GetIterator</span><span class="sxs-lookup"><span data-stu-id="364e3-115">GetIterator</span></span>](#getiterator) | <span data-ttu-id="364e3-116">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="364e3-116">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="364e3-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="364e3-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="364e3-118">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="364e3-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="364e3-119">SetHeader</span><span class="sxs-lookup"><span data-stu-id="364e3-119">SetHeader</span></span>](#setheader) | <span data-ttu-id="364e3-120">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="364e3-120">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="364e3-121">用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="364e3-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="364e3-122">注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="364e3-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="364e3-123">成员</span><span class="sxs-lookup"><span data-stu-id="364e3-123">Members</span></span>

#### <span data-ttu-id="364e3-124">Contains</span><span class="sxs-lookup"><span data-stu-id="364e3-124">Contains</span></span> 

<span data-ttu-id="364e3-125">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="364e3-125">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="364e3-126">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="364e3-126">public HRESULT [Contains](#contains)(LPCWSTR name, BOOL \* contains)</span></span>

#### <span data-ttu-id="364e3-127">GetHeader</span><span class="sxs-lookup"><span data-stu-id="364e3-127">GetHeader</span></span> 

<span data-ttu-id="364e3-128">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="364e3-128">Gets the header value matching the name.</span></span>

> <span data-ttu-id="364e3-129">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="364e3-129">public HRESULT [GetHeader](#getheader)(LPCWSTR name, LPWSTR \* value)</span></span>

#### <span data-ttu-id="364e3-130">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="364e3-130">GetHeaders</span></span> 

<span data-ttu-id="364e3-131">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="364e3-131">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="364e3-132">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="364e3-132">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name, [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="364e3-133">GetIterator</span><span class="sxs-lookup"><span data-stu-id="364e3-133">GetIterator</span></span> 

<span data-ttu-id="364e3-134">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="364e3-134">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="364e3-135">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="364e3-135">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="364e3-136">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="364e3-136">RemoveHeader</span></span> 

<span data-ttu-id="364e3-137">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="364e3-137">Removes header that matches the name.</span></span>

> <span data-ttu-id="364e3-138">公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="364e3-138">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="364e3-139">SetHeader</span><span class="sxs-lookup"><span data-stu-id="364e3-139">SetHeader</span></span> 

<span data-ttu-id="364e3-140">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="364e3-140">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="364e3-141">公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="364e3-141">public HRESULT [SetHeader](#setheader)(LPCWSTR name, LPCWSTR value)</span></span>

