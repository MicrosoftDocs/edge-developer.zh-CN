---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceResponseReceivedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 2d0660616de0c234b1535b2af127843fea3a3a53
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011651"
---
# <span data-ttu-id="77f98-104">CoreWebView2WebResourceResponseReceivedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="77f98-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponseReceivedEventArgs class</span></span> 

<span data-ttu-id="77f98-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="77f98-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="77f98-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="77f98-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="77f98-107">WebResourceResponseReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="77f98-107">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="77f98-108">摘要</span><span class="sxs-lookup"><span data-stu-id="77f98-108">Summary</span></span>

 <span data-ttu-id="77f98-109">成员</span><span class="sxs-lookup"><span data-stu-id="77f98-109">Members</span></span>                        | <span data-ttu-id="77f98-110">描述</span><span class="sxs-lookup"><span data-stu-id="77f98-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="77f98-111">请求</span><span class="sxs-lookup"><span data-stu-id="77f98-111">Request</span></span>](#request) | <span data-ttu-id="77f98-112">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="77f98-112">Web resource request object.</span></span>
[<span data-ttu-id="77f98-113">响应</span><span class="sxs-lookup"><span data-stu-id="77f98-113">Response</span></span>](#response) | <span data-ttu-id="77f98-114">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="77f98-114">Web resource response object.</span></span>
[<span data-ttu-id="77f98-115">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="77f98-115">PopulateResponseContentAsync</span></span>](#populateresponsecontentasync) | <span data-ttu-id="77f98-116">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="77f98-116">Async method to request the Content stream of the response.</span></span>

## <span data-ttu-id="77f98-117">成员</span><span class="sxs-lookup"><span data-stu-id="77f98-117">Members</span></span>

#### <span data-ttu-id="77f98-118">请求</span><span class="sxs-lookup"><span data-stu-id="77f98-118">Request</span></span> 

<span data-ttu-id="77f98-119">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="77f98-119">Web resource request object.</span></span>

> <span data-ttu-id="77f98-120">公共 [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [请求](#request)</span><span class="sxs-lookup"><span data-stu-id="77f98-120">public [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [Request](#request)</span></span>

<span data-ttu-id="77f98-121">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="77f98-121">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="77f98-122">响应</span><span class="sxs-lookup"><span data-stu-id="77f98-122">Response</span></span> 

<span data-ttu-id="77f98-123">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="77f98-123">Web resource response object.</span></span>

> <span data-ttu-id="77f98-124">公共 [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [响应](#response)</span><span class="sxs-lookup"><span data-stu-id="77f98-124">public [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [Response](#response)</span></span>

<span data-ttu-id="77f98-125">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="77f98-125">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="77f98-126">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="77f98-126">PopulateResponseContentAsync</span></span> 

<span data-ttu-id="77f98-127">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="77f98-127">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="77f98-128">公共异步任务 [PopulateResponseContentAsync](#populateresponsecontentasync) ( # A1</span><span class="sxs-lookup"><span data-stu-id="77f98-128">public async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span></span>

