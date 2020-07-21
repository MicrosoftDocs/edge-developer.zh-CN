---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 1e0148c0d1e27cb4f1c52fb6ad55cc2e7613a94b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885966"
---
# <span data-ttu-id="3fff6-104">0.8.355-接口 IWebView2HttpRequestHeaders</span><span class="sxs-lookup"><span data-stu-id="3fff6-104">0.8.355 - interface IWebView2HttpRequestHeaders</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpRequestHeaders
  : public IUnknown
```

<span data-ttu-id="3fff6-105">HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="3fff6-105">HTTP request headers.</span></span>

## <span data-ttu-id="3fff6-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3fff6-106">Summary</span></span>

 <span data-ttu-id="3fff6-107">成员</span><span class="sxs-lookup"><span data-stu-id="3fff6-107">Members</span></span>                        | <span data-ttu-id="3fff6-108">描述</span><span class="sxs-lookup"><span data-stu-id="3fff6-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3fff6-109">GetHeader</span><span class="sxs-lookup"><span data-stu-id="3fff6-109">GetHeader</span></span>](#getheader) | <span data-ttu-id="3fff6-110">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="3fff6-110">Gets the header value matching the name.</span></span>
[<span data-ttu-id="3fff6-111">Contains</span><span class="sxs-lookup"><span data-stu-id="3fff6-111">Contains</span></span>](#contains) | <span data-ttu-id="3fff6-112">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="3fff6-112">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="3fff6-113">SetHeader</span><span class="sxs-lookup"><span data-stu-id="3fff6-113">SetHeader</span></span>](#setheader) | <span data-ttu-id="3fff6-114">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="3fff6-114">Adds or updates header that matches the name.</span></span>
[<span data-ttu-id="3fff6-115">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="3fff6-115">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="3fff6-116">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="3fff6-116">Removes header that matches the name.</span></span>
[<span data-ttu-id="3fff6-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="3fff6-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="3fff6-118">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="3fff6-118">Gets an iterator over the collection of request headers.</span></span>

<span data-ttu-id="3fff6-119">用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="3fff6-119">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="3fff6-120">注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="3fff6-120">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="3fff6-121">成员</span><span class="sxs-lookup"><span data-stu-id="3fff6-121">Members</span></span>

#### <span data-ttu-id="3fff6-122">GetHeader</span><span class="sxs-lookup"><span data-stu-id="3fff6-122">GetHeader</span></span> 

<span data-ttu-id="3fff6-123">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="3fff6-123">Gets the header value matching the name.</span></span>

> <span data-ttu-id="3fff6-124">公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR \* value）</span><span class="sxs-lookup"><span data-stu-id="3fff6-124">public HRESULT [GetHeader](#getheader)(LPCWSTR name,LPWSTR \* value)</span></span>

#### <span data-ttu-id="3fff6-125">Contains</span><span class="sxs-lookup"><span data-stu-id="3fff6-125">Contains</span></span> 

<span data-ttu-id="3fff6-126">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="3fff6-126">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="3fff6-127">public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL \* 包含）</span><span class="sxs-lookup"><span data-stu-id="3fff6-127">public HRESULT [Contains](#contains)(LPCWSTR name,BOOL \* contains)</span></span>

#### <span data-ttu-id="3fff6-128">SetHeader</span><span class="sxs-lookup"><span data-stu-id="3fff6-128">SetHeader</span></span> 

<span data-ttu-id="3fff6-129">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="3fff6-129">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="3fff6-130">公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）</span><span class="sxs-lookup"><span data-stu-id="3fff6-130">public HRESULT [SetHeader](#setheader)(LPCWSTR name,LPCWSTR value)</span></span>

#### <span data-ttu-id="3fff6-131">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="3fff6-131">RemoveHeader</span></span> 

<span data-ttu-id="3fff6-132">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="3fff6-132">Removes header that matches the name.</span></span>

> <span data-ttu-id="3fff6-133">公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="3fff6-133">public HRESULT [RemoveHeader](#removeheader)(LPCWSTR name)</span></span>

#### <span data-ttu-id="3fff6-134">GetIterator</span><span class="sxs-lookup"><span data-stu-id="3fff6-134">GetIterator</span></span> 

<span data-ttu-id="3fff6-135">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="3fff6-135">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="3fff6-136">公共 HRESULT [GetIterator](#getiterator)（[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \* \* 迭代器）</span><span class="sxs-lookup"><span data-stu-id="3fff6-136">public HRESULT [GetIterator](#getiterator)([IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) \*\* iterator)</span></span>

