---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2HttpResponseHeaders 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 51218283460975421859c65da8a43553767ad216
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011700"
---
# <span data-ttu-id="dda5b-104">CoreWebView2HttpResponseHeaders 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="dda5b-104">Microsoft.Web.WebView2.Core.CoreWebView2HttpResponseHeaders class</span></span> 

<span data-ttu-id="dda5b-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="dda5b-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="dda5b-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="dda5b-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="dda5b-107">HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="dda5b-107">HTTP response headers.</span></span>

## <span data-ttu-id="dda5b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="dda5b-108">Summary</span></span>

 <span data-ttu-id="dda5b-109">成员</span><span class="sxs-lookup"><span data-stu-id="dda5b-109">Members</span></span>                        | <span data-ttu-id="dda5b-110">描述</span><span class="sxs-lookup"><span data-stu-id="dda5b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="dda5b-111">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="dda5b-111">AppendHeader</span></span>](#appendheader) | <span data-ttu-id="dda5b-112">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="dda5b-112">Appends header line with name and value.</span></span>
[<span data-ttu-id="dda5b-113">Contains</span><span class="sxs-lookup"><span data-stu-id="dda5b-113">Contains</span></span>](#contains) | <span data-ttu-id="dda5b-114">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="dda5b-114">Checks whether the headers contain entries matching the header name.</span></span>
[<span data-ttu-id="dda5b-115">GetHeader</span><span class="sxs-lookup"><span data-stu-id="dda5b-115">GetHeader</span></span>](#getheader) | <span data-ttu-id="dda5b-116">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="dda5b-116">Gets the first header value in the collection matching the name.</span></span>
[<span data-ttu-id="dda5b-117">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="dda5b-117">GetHeaders</span></span>](#getheaders) | <span data-ttu-id="dda5b-118">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="dda5b-118">Gets the header values matching the name.</span></span>
[<span data-ttu-id="dda5b-119">GetIterator</span><span class="sxs-lookup"><span data-stu-id="dda5b-119">GetIterator</span></span>](#getiterator) | <span data-ttu-id="dda5b-120">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="dda5b-120">Gets an iterator over the collection of entire response headers.</span></span>

<span data-ttu-id="dda5b-121">用于为 WebResourceRequested 事件构造 WebResourceResponse。</span><span class="sxs-lookup"><span data-stu-id="dda5b-121">Used to construct a WebResourceResponse for the WebResourceRequested event.</span></span>

## <span data-ttu-id="dda5b-122">成员</span><span class="sxs-lookup"><span data-stu-id="dda5b-122">Members</span></span>

#### <span data-ttu-id="dda5b-123">AppendHeader</span><span class="sxs-lookup"><span data-stu-id="dda5b-123">AppendHeader</span></span> 

<span data-ttu-id="dda5b-124">追加名称和值的标题行。</span><span class="sxs-lookup"><span data-stu-id="dda5b-124">Appends header line with name and value.</span></span>

> <span data-ttu-id="dda5b-125">public void [AppendHeader](#appendheader) (字符串名称，字符串值) </span><span class="sxs-lookup"><span data-stu-id="dda5b-125">public void [AppendHeader](#appendheader)(string name, string value)</span></span>

#### <span data-ttu-id="dda5b-126">Contains</span><span class="sxs-lookup"><span data-stu-id="dda5b-126">Contains</span></span> 

<span data-ttu-id="dda5b-127">检查标题是否包含与标题名称匹配的条目。</span><span class="sxs-lookup"><span data-stu-id="dda5b-127">Checks whether the headers contain entries matching the header name.</span></span>

> <span data-ttu-id="dda5b-128">public bool [包含](#contains) (的字符串名称) </span><span class="sxs-lookup"><span data-stu-id="dda5b-128">public bool [Contains](#contains)(string name)</span></span>

#### <span data-ttu-id="dda5b-129">GetHeader</span><span class="sxs-lookup"><span data-stu-id="dda5b-129">GetHeader</span></span> 

<span data-ttu-id="dda5b-130">获取与名称匹配的集合中的第一个 header 值。</span><span class="sxs-lookup"><span data-stu-id="dda5b-130">Gets the first header value in the collection matching the name.</span></span>

> <span data-ttu-id="dda5b-131"> (字符串名称的公共字符串 [GetHeader](#getheader)) </span><span class="sxs-lookup"><span data-stu-id="dda5b-131">public string [GetHeader](#getheader)(string name)</span></span>

#### <span data-ttu-id="dda5b-132">GetHeaders</span><span class="sxs-lookup"><span data-stu-id="dda5b-132">GetHeaders</span></span> 

<span data-ttu-id="dda5b-133">获取与名称匹配的标头值。</span><span class="sxs-lookup"><span data-stu-id="dda5b-133">Gets the header values matching the name.</span></span>

> <span data-ttu-id="dda5b-134">public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders) (字符串名称) </span><span class="sxs-lookup"><span data-stu-id="dda5b-134">public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders)(string name)</span></span>

#### <span data-ttu-id="dda5b-135">GetIterator</span><span class="sxs-lookup"><span data-stu-id="dda5b-135">GetIterator</span></span> 

<span data-ttu-id="dda5b-136">获取整个响应标头集合上的迭代器。</span><span class="sxs-lookup"><span data-stu-id="dda5b-136">Gets an iterator over the collection of entire response headers.</span></span>

> <span data-ttu-id="dda5b-137">公共 CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator) ( # A1</span><span class="sxs-lookup"><span data-stu-id="dda5b-137">public CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator)()</span></span>

