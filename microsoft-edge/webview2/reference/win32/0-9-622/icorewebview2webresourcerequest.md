---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceRequest
ms.openlocfilehash: 9d14162c8c451bc62de86a671c586f544fb4191b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011745"
---
# <span data-ttu-id="d959d-104">interface ICoreWebView2WebResourceRequest</span><span class="sxs-lookup"><span data-stu-id="d959d-104">interface ICoreWebView2WebResourceRequest</span></span> 

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

<span data-ttu-id="d959d-105">与 WebResourceRequested 事件一起使用的 HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="d959d-105">An HTTP request used with the WebResourceRequested event.</span></span>

## <span data-ttu-id="d959d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d959d-106">Summary</span></span>

 <span data-ttu-id="d959d-107">成员</span><span class="sxs-lookup"><span data-stu-id="d959d-107">Members</span></span>                        | <span data-ttu-id="d959d-108">描述</span><span class="sxs-lookup"><span data-stu-id="d959d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d959d-109">get_Content</span><span class="sxs-lookup"><span data-stu-id="d959d-109">get_Content</span></span>](#get_content) | <span data-ttu-id="d959d-110">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="d959d-110">The HTTP request message body as stream.</span></span>
[<span data-ttu-id="d959d-111">get_Headers</span><span class="sxs-lookup"><span data-stu-id="d959d-111">get_Headers</span></span>](#get_headers) | <span data-ttu-id="d959d-112">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="d959d-112">The mutable HTTP request headers.</span></span>
[<span data-ttu-id="d959d-113">get_Method</span><span class="sxs-lookup"><span data-stu-id="d959d-113">get_Method</span></span>](#get_method) | <span data-ttu-id="d959d-114">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="d959d-114">The HTTP request method.</span></span>
[<span data-ttu-id="d959d-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d959d-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="d959d-116">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="d959d-116">The request URI.</span></span>
[<span data-ttu-id="d959d-117">put_Content</span><span class="sxs-lookup"><span data-stu-id="d959d-117">put_Content</span></span>](#put_content) | <span data-ttu-id="d959d-118">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="d959d-118">Set the Content property.</span></span>
[<span data-ttu-id="d959d-119">put_Method</span><span class="sxs-lookup"><span data-stu-id="d959d-119">put_Method</span></span>](#put_method) | <span data-ttu-id="d959d-120">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="d959d-120">Set the Method property.</span></span>
[<span data-ttu-id="d959d-121">put_Uri</span><span class="sxs-lookup"><span data-stu-id="d959d-121">put_Uri</span></span>](#put_uri) | <span data-ttu-id="d959d-122">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="d959d-122">Set the Uri property.</span></span>

## <span data-ttu-id="d959d-123">成员</span><span class="sxs-lookup"><span data-stu-id="d959d-123">Members</span></span>

#### <span data-ttu-id="d959d-124">get_Content</span><span class="sxs-lookup"><span data-stu-id="d959d-124">get_Content</span></span> 

<span data-ttu-id="d959d-125">作为流的 HTTP 请求消息正文。</span><span class="sxs-lookup"><span data-stu-id="d959d-125">The HTTP request message body as stream.</span></span>

> <span data-ttu-id="d959d-126">公共 HRESULT [get_Content](#get_content) (IStream \* \* 内容) </span><span class="sxs-lookup"><span data-stu-id="d959d-126">public HRESULT [get_Content](#get_content)(IStream \*\* content)</span></span>

<span data-ttu-id="d959d-127">发布数据将在此处显示。</span><span class="sxs-lookup"><span data-stu-id="d959d-127">POST data would be here.</span></span> <span data-ttu-id="d959d-128">如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。</span><span class="sxs-lookup"><span data-stu-id="d959d-128">If a stream is set, which will override the message body, the stream must have all the content data available by the time this response's WebResourceRequested event deferral is completed.</span></span> <span data-ttu-id="d959d-129">流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。</span><span class="sxs-lookup"><span data-stu-id="d959d-129">Stream should be agile or be created from a background STA to prevent performance impact to the UI thread.</span></span> <span data-ttu-id="d959d-130">Null 表示没有内容数据。</span><span class="sxs-lookup"><span data-stu-id="d959d-130">Null means no content data.</span></span> <span data-ttu-id="d959d-131">IStream 语义将应用 (返回 S_OK 以读取呼叫，直到所有数据用尽) 。</span><span class="sxs-lookup"><span data-stu-id="d959d-131">IStream semantics apply (return S_OK to Read calls until all data is exhausted).</span></span>

#### <span data-ttu-id="d959d-132">get_Headers</span><span class="sxs-lookup"><span data-stu-id="d959d-132">get_Headers</span></span> 

<span data-ttu-id="d959d-133">可变 HTTP 请求标头。</span><span class="sxs-lookup"><span data-stu-id="d959d-133">The mutable HTTP request headers.</span></span>

> <span data-ttu-id="d959d-134">公共 HRESULT [get_Headers](#get_headers) ([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \* \* 标题) </span><span class="sxs-lookup"><span data-stu-id="d959d-134">public HRESULT [get_Headers](#get_headers)([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) \*\* headers)</span></span>

#### <span data-ttu-id="d959d-135">get_Method</span><span class="sxs-lookup"><span data-stu-id="d959d-135">get_Method</span></span> 

<span data-ttu-id="d959d-136">HTTP 请求方法。</span><span class="sxs-lookup"><span data-stu-id="d959d-136">The HTTP request method.</span></span>

> <span data-ttu-id="d959d-137">公共 HRESULT [get_Method](#get_method) (LPWSTR \* 方法) </span><span class="sxs-lookup"><span data-stu-id="d959d-137">public HRESULT [get_Method](#get_method)(LPWSTR \* method)</span></span>

#### <span data-ttu-id="d959d-138">get_Uri</span><span class="sxs-lookup"><span data-stu-id="d959d-138">get_Uri</span></span> 

<span data-ttu-id="d959d-139">请求 URI。</span><span class="sxs-lookup"><span data-stu-id="d959d-139">The request URI.</span></span>

> <span data-ttu-id="d959d-140">公共 HRESULT [get_Uri](#get_uri) (LPWSTR \* Uri) </span><span class="sxs-lookup"><span data-stu-id="d959d-140">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="d959d-141">put_Content</span><span class="sxs-lookup"><span data-stu-id="d959d-141">put_Content</span></span> 

<span data-ttu-id="d959d-142">设置内容属性。</span><span class="sxs-lookup"><span data-stu-id="d959d-142">Set the Content property.</span></span>

> <span data-ttu-id="d959d-143">公共 HRESULT [put_Content](#put_content) (IStream \* 内容) </span><span class="sxs-lookup"><span data-stu-id="d959d-143">public HRESULT [put_Content](#put_content)(IStream \* content)</span></span>

#### <span data-ttu-id="d959d-144">put_Method</span><span class="sxs-lookup"><span data-stu-id="d959d-144">put_Method</span></span> 

<span data-ttu-id="d959d-145">设置 Method 属性。</span><span class="sxs-lookup"><span data-stu-id="d959d-145">Set the Method property.</span></span>

> <span data-ttu-id="d959d-146">public HRESULT [put_Method](#put_method) (LPCWSTR 方法) </span><span class="sxs-lookup"><span data-stu-id="d959d-146">public HRESULT [put_Method](#put_method)(LPCWSTR method)</span></span>

#### <span data-ttu-id="d959d-147">put_Uri</span><span class="sxs-lookup"><span data-stu-id="d959d-147">put_Uri</span></span> 

<span data-ttu-id="d959d-148">设置 Uri 属性。</span><span class="sxs-lookup"><span data-stu-id="d959d-148">Set the Uri property.</span></span>

> <span data-ttu-id="d959d-149">公共 HRESULT [put_Uri](#put_uri) (LPCWSTR Uri) </span><span class="sxs-lookup"><span data-stu-id="d959d-149">public HRESULT [put_Uri](#put_uri)(LPCWSTR uri)</span></span>

