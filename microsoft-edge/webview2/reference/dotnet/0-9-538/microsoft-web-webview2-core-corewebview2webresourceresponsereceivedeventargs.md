---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2WebResourceResponseReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: a8c988fdfee72ed22e74886b440819d7a9d6fe24
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010507"
---
# <span data-ttu-id="c01f0-104">0.9.579-WebView2 的 CoreWebView2WebResourceResponseReceivedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="c01f0-104">0.9.579 - Microsoft.Web.WebView2.Core.CoreWebView2WebResourceResponseReceivedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="c01f0-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="c01f0-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="c01f0-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c01f0-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="c01f0-107">WebResourceResponseReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c01f0-107">Event args for the WebResourceResponseReceived event.</span></span>

## <span data-ttu-id="c01f0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c01f0-108">Summary</span></span>

 <span data-ttu-id="c01f0-109">成员</span><span class="sxs-lookup"><span data-stu-id="c01f0-109">Members</span></span>                        | <span data-ttu-id="c01f0-110">描述</span><span class="sxs-lookup"><span data-stu-id="c01f0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c01f0-111">请求</span><span class="sxs-lookup"><span data-stu-id="c01f0-111">Request</span></span>](#request) | <span data-ttu-id="c01f0-112">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="c01f0-112">Web resource request object.</span></span>
[<span data-ttu-id="c01f0-113">响应</span><span class="sxs-lookup"><span data-stu-id="c01f0-113">Response</span></span>](#response) | <span data-ttu-id="c01f0-114">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="c01f0-114">Web resource response object.</span></span>
[<span data-ttu-id="c01f0-115">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="c01f0-115">PopulateResponseContentAsync</span></span>](#populateresponsecontentasync) | <span data-ttu-id="c01f0-116">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="c01f0-116">Async method to request the Content stream of the response.</span></span>

## <span data-ttu-id="c01f0-117">成员</span><span class="sxs-lookup"><span data-stu-id="c01f0-117">Members</span></span>

#### <span data-ttu-id="c01f0-118">请求</span><span class="sxs-lookup"><span data-stu-id="c01f0-118">Request</span></span> 

<span data-ttu-id="c01f0-119">Web 资源请求对象。</span><span class="sxs-lookup"><span data-stu-id="c01f0-119">Web resource request object.</span></span>

> <span data-ttu-id="c01f0-120">公共 HttpRequestMessage [请求](#request)</span><span class="sxs-lookup"><span data-stu-id="c01f0-120">public HttpRequestMessage [Request](#request)</span></span>

<span data-ttu-id="c01f0-121">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c01f0-121">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="c01f0-122">响应</span><span class="sxs-lookup"><span data-stu-id="c01f0-122">Response</span></span> 

<span data-ttu-id="c01f0-123">Web 资源响应对象。</span><span class="sxs-lookup"><span data-stu-id="c01f0-123">Web resource response object.</span></span>

> <span data-ttu-id="c01f0-124">公共 HttpResponseMessage [响应](#response)</span><span class="sxs-lookup"><span data-stu-id="c01f0-124">public HttpResponseMessage [Response](#response)</span></span>

<span data-ttu-id="c01f0-125">对此对象所做的任何修改都将被忽略。</span><span class="sxs-lookup"><span data-stu-id="c01f0-125">Any modifications to this object will be ignored.</span></span>

#### <span data-ttu-id="c01f0-126">PopulateResponseContentAsync</span><span class="sxs-lookup"><span data-stu-id="c01f0-126">PopulateResponseContentAsync</span></span> 

<span data-ttu-id="c01f0-127">请求响应的内容流的异步方法。</span><span class="sxs-lookup"><span data-stu-id="c01f0-127">Async method to request the Content stream of the response.</span></span>

> <span data-ttu-id="c01f0-128">公共异步任务 [PopulateResponseContentAsync](#populateresponsecontentasync) ( # A1</span><span class="sxs-lookup"><span data-stu-id="c01f0-128">public async Task [PopulateResponseContentAsync](#populateresponsecontentasync)()</span></span>

