---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2WebResourceResponseReceivedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 44fc4f47aa10a7e409ac584cb75b750048056e47
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886503"
---
# <span data-ttu-id="a0b45-104">CoreWebView2WebResourceResponseReceivedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a0b45-104">Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponseReceivedEventArgs class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="a0b45-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a0b45-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a0b45-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a0b45-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a0b45-107">WebResourceResponseReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a0b45-107">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="a0b45-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a0b45-108">Summary</span></span>

 <span data-ttu-id="a0b45-109">成员</span><span class="sxs-lookup"><span data-stu-id="a0b45-109">Members</span></span>                        | <span data-ttu-id="a0b45-110">描述</span><span class="sxs-lookup"><span data-stu-id="a0b45-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a0b45-111">请求</span><span class="sxs-lookup"><span data-stu-id="a0b45-111">Request</span></span>](#request) | <span data-ttu-id="a0b45-112">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="a0b45-112">Web resource request object.</span></span>
[<span data-ttu-id="a0b45-113">响应</span><span class="sxs-lookup"><span data-stu-id="a0b45-113">Response</span></span>](#response) | <span data-ttu-id="a0b45-114">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="a0b45-114">Web resource response object.</span></span>
[<span data-ttu-id="a0b45-115">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="a0b45-115">PopulateResponseContentAsync</span></span>](#populateresponsecontentasync) | <span data-ttu-id="a0b45-116">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="a0b45-116">Async method to request the Content stream of the response.</span></span>

## <span data-ttu-id="a0b45-117">成员</span><span class="sxs-lookup"><span data-stu-id="a0b45-117">Members</span></span>

#### <span data-ttu-id="a0b45-118">请求</span><span class="sxs-lookup"><span data-stu-id="a0b45-118">Request</span></span> 

<span data-ttu-id="a0b45-119">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="a0b45-119">Web resource request object.</span></span>

> <span data-ttu-id="a0b45-120">公共 HttpRequestMessage[请求](#request)</span><span class="sxs-lookup"><span data-stu-id="a0b45-120">public HttpRequestMessage [Request](#request)</span></span>

<span data-ttu-id="a0b45-121">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a0b45-121">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="a0b45-122">响应</span><span class="sxs-lookup"><span data-stu-id="a0b45-122">Response</span></span> 

<span data-ttu-id="a0b45-123">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="a0b45-123">Web resource response object.</span></span>

> <span data-ttu-id="a0b45-124">公共 HttpResponseMessage[响应](#response)</span><span class="sxs-lookup"><span data-stu-id="a0b45-124">public HttpResponseMessage [Response](#response)</span></span>

<span data-ttu-id="a0b45-125">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="a0b45-125">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="a0b45-126">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="a0b45-126">PopulateResponseContentAsync</span></span> 

<span data-ttu-id="a0b45-127">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="a0b45-127">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="a0b45-128">公共异步任务[PopulateResponseContentAsync](#populateresponsecontentasync)（）</span><span class="sxs-lookup"><span data-stu-id="a0b45-128">public async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span></span>

