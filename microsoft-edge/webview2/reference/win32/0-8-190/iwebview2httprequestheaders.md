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
ms.openlocfilehash: aea00f37f28034e1b7a33d4fd11c5ed78f779d00
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653092"
---
# <span data-ttu-id="d172f-104">interface IWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="d172f-104">interface IWebView2HttpRequestHeaders</span></span> 

> [!NOTE]
> <span data-ttu-id="d172f-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d172f-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="d172f-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d172f-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="d172f-107">HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="d172f-107">HTTP request headers.</span></span>

## <span data-ttu-id="d172f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d172f-108">Summary</span></span>

 <span data-ttu-id="d172f-109">成员</span><span class="sxs-lookup"><span data-stu-id="d172f-109">Members</span></span>                        | <span data-ttu-id="d172f-110">描述</span><span class="sxs-lookup"><span data-stu-id="d172f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d172f-111">GetHeader</span><span class="sxs-lookup"><span data-stu-id="d172f-111">GetHeader</span></span>](#getheader) | <span data-ttu-id="d172f-112">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="d172f-112">Gets the header value matching the name.</span></span>
[<span data-ttu-id="d172f-113">Contains</span><span class="sxs-lookup"><span data-stu-id="d172f-113">Contains</span></span>](#contains) | <span data-ttu-id="d172f-114">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="d172f-114">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="d172f-115">SetHeader</span><span class="sxs-lookup"><span data-stu-id="d172f-115">SetHeader</span></span>](#setheader) | <span data-ttu-id="d172f-116">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d172f-116">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="d172f-117">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="d172f-117">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="d172f-118">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d172f-118">Removes header that matches the name.</span></span>
[<span data-ttu-id="d172f-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="d172f-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="d172f-120">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="d172f-120">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="d172f-121">用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="d172f-121">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="d172f-122">注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="d172f-122">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="d172f-123">成员</span><span class="sxs-lookup"><span data-stu-id="d172f-123">Members</span></span>

#### <span data-ttu-id="d172f-124">GetHeader</span><span class="sxs-lookup"><span data-stu-id="d172f-124">GetHeader</span></span> 

<span data-ttu-id="d172f-125">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="d172f-125">Gets the header value matching the name.</span></span>

> <span data-ttu-id="d172f-126">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="d172f-126">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="d172f-127">Contains</span><span class="sxs-lookup"><span data-stu-id="d172f-127">Contains</span></span> 

<span data-ttu-id="d172f-128">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="d172f-128">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="d172f-129">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="d172f-129">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="d172f-130">SetHeader</span><span class="sxs-lookup"><span data-stu-id="d172f-130">SetHeader</span></span> 

<span data-ttu-id="d172f-131">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d172f-131">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="d172f-132">公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="d172f-132">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="d172f-133">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="d172f-133">RemoveHeader</span></span> 

<span data-ttu-id="d172f-134">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d172f-134">Removes header that matches the name.</span></span>

> <span data-ttu-id="d172f-135">公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="d172f-135">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="d172f-136">GetIterator</span><span class="sxs-lookup"><span data-stu-id="d172f-136">GetIterator</span></span> 

<span data-ttu-id="d172f-137">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="d172f-137">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="d172f-138">公共 HRESULT [GetIterator](#getiterator)（[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="d172f-138">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

