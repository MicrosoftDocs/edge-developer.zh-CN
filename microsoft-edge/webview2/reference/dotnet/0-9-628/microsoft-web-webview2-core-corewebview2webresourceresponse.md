---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceResponse 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5359634d83717ce844d2c1604a2645ceffc477cc
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011653"
---
# <span data-ttu-id="cba01-104">CoreWebView2WebResourceResponse 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="cba01-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponse class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="cba01-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="cba01-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="cba01-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="cba01-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="cba01-107">与 WebResourceRequested 事件一起使用的 HTTP 响应。</span><span class="sxs-lookup"><span data-stu-id="cba01-107">An HTTP response used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="cba01-108">摘要</span><span class="sxs-lookup"><span data-stu-id="cba01-108">Summary</span></span>

 <span data-ttu-id="cba01-109">成员</span><span class="sxs-lookup"><span data-stu-id="cba01-109">Members</span></span>                        | <span data-ttu-id="cba01-110">描述</span><span class="sxs-lookup"><span data-stu-id="cba01-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cba01-111">内容</span><span class="sxs-lookup"><span data-stu-id="cba01-111">Content</span></span>](#content) | <span data-ttu-id="cba01-112">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="cba01-112">HTTP response content as stream.</span></span>
[<span data-ttu-id="cba01-113">标题</span><span class="sxs-lookup"><span data-stu-id="cba01-113">Headers</span></span>](#headers) | <span data-ttu-id="cba01-114">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="cba01-114">Overridden HTTP response headers.</span></span>
[<span data-ttu-id="cba01-115">ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="cba01-115">ReasonPhrase</span></span>](#reasonphrase) | <span data-ttu-id="cba01-116">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="cba01-116">The HTTP response reason phrase.</span></span>
[<span data-ttu-id="cba01-117">StatusCode</span><span class="sxs-lookup"><span data-stu-id="cba01-117">StatusCode</span></span>](#statuscode) | <span data-ttu-id="cba01-118">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="cba01-118">The HTTP response status code.</span></span>

## <span data-ttu-id="cba01-119">成员</span><span class="sxs-lookup"><span data-stu-id="cba01-119">Members</span></span>

#### <span data-ttu-id="cba01-120">内容</span><span class="sxs-lookup"><span data-stu-id="cba01-120">Content</span></span> 

<span data-ttu-id="cba01-121">流形式的 HTTP 响应内容。</span><span class="sxs-lookup"><span data-stu-id="cba01-121">HTTP response content as stream.</span></span>

> <span data-ttu-id="cba01-122">公共流 [内容](#content)</span><span class="sxs-lookup"><span data-stu-id="cba01-122">public Stream [Content](#content)</span></span>

<span data-ttu-id="cba01-123">在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。</span><span class="sxs-lookup"><span data-stu-id="cba01-123">Stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="cba01-124">流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。</span><span class="sxs-lookup"><span data-stu-id="cba01-124">Stream should be agile or be created from a background thread to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="cba01-125">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="cba01-125">Null means no content data.</span></span> <span data-ttu-id="cba01-126">IStream 语义将应用 (返回 S_OK 以读取呼叫，直到所有数据用尽) 。</span><span class="sxs-lookup"><span data-stu-id="cba01-126">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="cba01-127">标题</span><span class="sxs-lookup"><span data-stu-id="cba01-127">Headers</span></span> 

<span data-ttu-id="cba01-128">已重写 HTTP 响应标头。</span><span class="sxs-lookup"><span data-stu-id="cba01-128">Overridden HTTP response headers.</span></span>

> <span data-ttu-id="cba01-129">公共 [CoreWebView2HttpResponseHeaders](microsoft-web-webview2-core-corewebview2httpresponseheaders.md) [标题](#headers)</span><span class="sxs-lookup"><span data-stu-id="cba01-129">public [CoreWebView2HttpResponseHeaders](microsoft-web-webview2-core-corewebview2httpresponseheaders.md) [Headers](#headers)</span></span>

#### <span data-ttu-id="cba01-130">ReasonPhrase</span><span class="sxs-lookup"><span data-stu-id="cba01-130">ReasonPhrase</span></span> 

<span data-ttu-id="cba01-131">HTTP 响应原因短语。</span><span class="sxs-lookup"><span data-stu-id="cba01-131">The HTTP response reason phrase.</span></span>

> <span data-ttu-id="cba01-132">公共字符串 [ReasonPhrase](#reasonphrase)</span><span class="sxs-lookup"><span data-stu-id="cba01-132">public string [ReasonPhrase](#reasonphrase)</span></span>

#### <span data-ttu-id="cba01-133">StatusCode</span><span class="sxs-lookup"><span data-stu-id="cba01-133">StatusCode</span></span> 

<span data-ttu-id="cba01-134">HTTP 响应状态代码。</span><span class="sxs-lookup"><span data-stu-id="cba01-134">The HTTP response status code.</span></span>

> <span data-ttu-id="cba01-135">公共 int [StatusCode](#statuscode)</span><span class="sxs-lookup"><span data-stu-id="cba01-135">public int [StatusCode](#statuscode)</span></span>

