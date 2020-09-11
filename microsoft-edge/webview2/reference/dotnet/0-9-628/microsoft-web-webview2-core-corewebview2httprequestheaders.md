---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2HttpRequestHeaders 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 1441d5a45caf4e8f561de2487438b66e067760f6
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011636"
---
# <span data-ttu-id="d4193-104">CoreWebView2HttpRequestHeaders 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="d4193-104">Microsoft.Web.WebView2.Core.CoreWebView2HttpRequestHeaders class</span></span> 

<span data-ttu-id="d4193-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="d4193-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="d4193-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="d4193-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="d4193-107">HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="d4193-107">HTTP request headers.</span></span>

## <span data-ttu-id="d4193-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d4193-108">Summary</span></span>

 <span data-ttu-id="d4193-109">成员</span><span class="sxs-lookup"><span data-stu-id="d4193-109">Members</span></span>                        | <span data-ttu-id="d4193-110">描述</span><span class="sxs-lookup"><span data-stu-id="d4193-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d4193-111">Contains</span><span class="sxs-lookup"><span data-stu-id="d4193-111">Contains</span></span>](#contains) | <span data-ttu-id="d4193-112">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="d4193-112">Checks whether the headers contain an entry matching the header name.</span></span>
[<span data-ttu-id="d4193-113">GetHeader</span><span class="sxs-lookup"><span data-stu-id="d4193-113">GetHeader</span></span>](#getheader) | <span data-ttu-id="d4193-114">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="d4193-114">Gets the header value matching the name.</span></span>
[<span data-ttu-id="d4193-115">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="d4193-115">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="d4193-116">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="d4193-116">Gets the header value matching the name via an iterator.</span></span>
[<span data-ttu-id="d4193-117">GetIterator</span><span class="sxs-lookup"><span data-stu-id="d4193-117">GetIterator</span></span>](#getiterator) | <span data-ttu-id="d4193-118">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="d4193-118">Gets an iterator over the collection of request headers.</span></span>
[<span data-ttu-id="d4193-119">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="d4193-119">RemoveHeader</span></span>](#removeheader) | <span data-ttu-id="d4193-120">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d4193-120">Removes header that matches the name.</span></span>
[<span data-ttu-id="d4193-121">SetHeader</span><span class="sxs-lookup"><span data-stu-id="d4193-121">SetHeader</span></span>](#setheader) | <span data-ttu-id="d4193-122">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d4193-122">Adds or updates header that matches the name.</span></span>

<span data-ttu-id="d4193-123">用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="d4193-123">Used to inspect the HTTP request on WebResourceRequested event and NavigationStarting event.</span></span> <span data-ttu-id="d4193-124">注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="d4193-124">Note, you can modify the HTTP request headers from a WebResourceRequested event, but not from a NavigationStarting event.</span></span>

## <span data-ttu-id="d4193-125">成员</span><span class="sxs-lookup"><span data-stu-id="d4193-125">Members</span></span>

#### <span data-ttu-id="d4193-126">Contains</span><span class="sxs-lookup"><span data-stu-id="d4193-126">Contains</span></span> 

<span data-ttu-id="d4193-127">检查标题是否包含与标头名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="d4193-127">Checks whether the headers contain an entry matching the header name.</span></span>

> <span data-ttu-id="d4193-128">public bool [包含](#contains) (的字符串名称) </span><span class="sxs-lookup"><span data-stu-id="d4193-128">public bool [Contains](#contains)(string name)</span></span>

#### <span data-ttu-id="d4193-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="d4193-129">GetHeader</span></span> 

<span data-ttu-id="d4193-130">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="d4193-130">Gets the header value matching the name.</span></span>

> <span data-ttu-id="d4193-131"> (字符串名称的公共字符串 [GetHeader](#getheader)) </span><span class="sxs-lookup"><span data-stu-id="d4193-131">public string [GetHeader](#getheader)(string name)</span></span>

#### <span data-ttu-id="d4193-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="d4193-132">GetHeaders</span></span> 

<span data-ttu-id="d4193-133">通过迭代器获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="d4193-133">Gets the header value matching the name via an iterator.</span></span>

> <span data-ttu-id="d4193-134">public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders) (字符串名称) </span><span class="sxs-lookup"><span data-stu-id="d4193-134">public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(string name)</span></span>

#### <span data-ttu-id="d4193-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="d4193-135">GetIterator</span></span> 

<span data-ttu-id="d4193-136">获取请求标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="d4193-136">Gets an iterator over the collection of request headers.</span></span>

> <span data-ttu-id="d4193-137">公共 CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator) ( # A1</span><span class="sxs-lookup"><span data-stu-id="d4193-137">public CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator)()</span></span>

#### <span data-ttu-id="d4193-138">RemoveHeader</span><span class="sxs-lookup"><span data-stu-id="d4193-138">RemoveHeader</span></span> 

<span data-ttu-id="d4193-139">删除与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d4193-139">Removes header that matches the name.</span></span>

> <span data-ttu-id="d4193-140">public void [RemoveHeader](#removeheader) (字符串名称) </span><span class="sxs-lookup"><span data-stu-id="d4193-140">public void [RemoveHeader](#removeheader)(string name)</span></span>

#### <span data-ttu-id="d4193-141">SetHeader</span><span class="sxs-lookup"><span data-stu-id="d4193-141">SetHeader</span></span> 

<span data-ttu-id="d4193-142">添加或更新与名称匹配的标题。</span><span class="sxs-lookup"><span data-stu-id="d4193-142">Adds or updates header that matches the name.</span></span>

> <span data-ttu-id="d4193-143">public void [SetHeader](#setheader) (字符串名称，字符串值) </span><span class="sxs-lookup"><span data-stu-id="d4193-143">public void [SetHeader](#setheader)(string name, string value)</span></span>

