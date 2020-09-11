---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceRequest 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5c8d164b24995cc31070232dd9b1a2d88fc16cec
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011657"
---
# <span data-ttu-id="c4ccd-104">CoreWebView2WebResourceRequest 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="c4ccd-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceRequest class</span></span> 

<span data-ttu-id="c4ccd-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="c4ccd-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="c4ccd-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c4ccd-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="c4ccd-107">与 WebResourceRequested 事件一起使用的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-107">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="c4ccd-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c4ccd-108">Summary</span></span>

 <span data-ttu-id="c4ccd-109">成员</span><span class="sxs-lookup"><span data-stu-id="c4ccd-109">Members</span></span>                        | <span data-ttu-id="c4ccd-110">描述</span><span class="sxs-lookup"><span data-stu-id="c4ccd-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c4ccd-111">内容</span><span class="sxs-lookup"><span data-stu-id="c4ccd-111">Content</span></span>](#content) | <span data-ttu-id="c4ccd-112">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-112">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="c4ccd-113">标题</span><span class="sxs-lookup"><span data-stu-id="c4ccd-113">Headers</span></span>](#headers) | <span data-ttu-id="c4ccd-114">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-114">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="c4ccd-115">方法</span><span class="sxs-lookup"><span data-stu-id="c4ccd-115">Method</span></span>](#method) | <span data-ttu-id="c4ccd-116">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-116">The HTTP request method.</span></span>
[<span data-ttu-id="c4ccd-117">Uri</span><span class="sxs-lookup"><span data-stu-id="c4ccd-117">Uri</span></span>](#uri) | <span data-ttu-id="c4ccd-118">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-118">The request URI.</span></span>

## <span data-ttu-id="c4ccd-119">成员</span><span class="sxs-lookup"><span data-stu-id="c4ccd-119">Members</span></span>

#### <span data-ttu-id="c4ccd-120">内容</span><span class="sxs-lookup"><span data-stu-id="c4ccd-120">Content</span></span> 

<span data-ttu-id="c4ccd-121">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-121">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="c4ccd-122">公共流 [内容](#content)</span><span class="sxs-lookup"><span data-stu-id="c4ccd-122">public Stream [Content](#content)</span></span>

<span data-ttu-id="c4ccd-123">发布数据将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-123">POST data would be here.</span></span> <span data-ttu-id="c4ccd-124">如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-124">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="c4ccd-125">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-125">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="c4ccd-126">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-126">Null means no content data.</span></span> <span data-ttu-id="c4ccd-127">IStream 语义将应用 (返回 S_OK 以读取呼叫，直到所有数据用尽) 。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-127">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="c4ccd-128">标题</span><span class="sxs-lookup"><span data-stu-id="c4ccd-128">Headers</span></span> 

<span data-ttu-id="c4ccd-129">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-129">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="c4ccd-130">公共 [CoreWebView2HttpRequestHeaders](microsoft-web-webview2-core-corewebview2httprequestheaders.md) [标题](#headers)</span><span class="sxs-lookup"><span data-stu-id="c4ccd-130">public [CoreWebView2HttpRequestHeaders](microsoft-web-webview2-core-corewebview2httprequestheaders.md) [Headers](#headers)</span></span>

#### <span data-ttu-id="c4ccd-131">方法</span><span class="sxs-lookup"><span data-stu-id="c4ccd-131">Method</span></span> 

<span data-ttu-id="c4ccd-132">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-132">The HTTP request method.</span></span>

> <span data-ttu-id="c4ccd-133">公共字符串 [方法](#method)</span><span class="sxs-lookup"><span data-stu-id="c4ccd-133">public string [Method](#method)</span></span>

#### <span data-ttu-id="c4ccd-134">Uri</span><span class="sxs-lookup"><span data-stu-id="c4ccd-134">Uri</span></span> 

<span data-ttu-id="c4ccd-135">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="c4ccd-135">The request URI.</span></span>

> <span data-ttu-id="c4ccd-136">公共字符串 [Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="c4ccd-136">public string [Uri](#uri)</span></span>

