---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: e12809d1db7e8c7764ad75e9a10f44ac3f445fa4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652957"
---
# <span data-ttu-id="e3dac-104">interface ICoreWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="e3dac-104">interface ICoreWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="e3dac-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e3dac-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="e3dac-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e3dac-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="e3dac-107">HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="e3dac-107">HTTP request headers.</span></span>

## <span data-ttu-id="e3dac-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e3dac-108">Summary</span></span>

 <span data-ttu-id="e3dac-109">成员</span><span class="sxs-lookup"><span data-stu-id="e3dac-109">Members</span></span>                        | <span data-ttu-id="e3dac-110">描述</span><span class="sxs-lookup"><span data-stu-id="e3dac-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e3dac-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="e3dac-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="e3dac-112">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="e3dac-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="e3dac-113">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="e3dac-113">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="e3dac-114">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="e3dac-114">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="e3dac-115">Contains</span><span class="sxs-lookup"><span data-stu-id="e3dac-115">Contains</span></span>](#contains) | <span data-ttu-id="e3dac-116">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="e3dac-116">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="e3dac-117">SetHeader</span><span class="sxs-lookup"><span data-stu-id="e3dac-117">SetHeader</span></span>](#setheader) | <span data-ttu-id="e3dac-118">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="e3dac-118">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="e3dac-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="e3dac-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="e3dac-120">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="e3dac-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="e3dac-121">GetIterator</span><span class="sxs-lookup"><span data-stu-id="e3dac-121">GetIterator</span></span>](#getiterator) | <span data-ttu-id="e3dac-122">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="e3dac-122">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="e3dac-123">用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="e3dac-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="e3dac-124">注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="e3dac-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="e3dac-125">成员</span><span class="sxs-lookup"><span data-stu-id="e3dac-125">Members</span></span>

#### <span data-ttu-id="e3dac-126">GetHeader</span><span class="sxs-lookup"><span data-stu-id="e3dac-126">GetHeader</span></span> 

<span data-ttu-id="e3dac-127">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="e3dac-127">Gets the header value matching the name.</span></span>

> <span data-ttu-id="e3dac-128">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="e3dac-128">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="e3dac-129">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="e3dac-129">GetHeaders</span></span> 

<span data-ttu-id="e3dac-130">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="e3dac-130">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="e3dac-131">公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="e3dac-131">public HRESULT [GetHeaders](#getheaders)(LPCWSTR name,[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

#### <span data-ttu-id="e3dac-132">Contains</span><span class="sxs-lookup"><span data-stu-id="e3dac-132">Contains</span></span> 

<span data-ttu-id="e3dac-133">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="e3dac-133">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="e3dac-134">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="e3dac-134">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="e3dac-135">SetHeader</span><span class="sxs-lookup"><span data-stu-id="e3dac-135">SetHeader</span></span> 

<span data-ttu-id="e3dac-136">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="e3dac-136">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="e3dac-137">公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="e3dac-137">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="e3dac-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="e3dac-138">RemoveHeader</span></span> 

<span data-ttu-id="e3dac-139">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="e3dac-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="e3dac-140">公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="e3dac-140">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="e3dac-141">GetIterator</span><span class="sxs-lookup"><span data-stu-id="e3dac-141">GetIterator</span></span> 

<span data-ttu-id="e3dac-142">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="e3dac-142">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="e3dac-143">公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="e3dac-143">public HRESULT [GetIterator](#getiterator)([ICoreWebView2HttpHeadersCollectionIterator](ICoreWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

