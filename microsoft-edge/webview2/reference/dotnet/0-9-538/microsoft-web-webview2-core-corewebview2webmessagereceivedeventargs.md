---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2WebMessageReceivedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 01c6a22ec84b85437920dceb66072089fd6d0d93
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879658"
---
# <span data-ttu-id="5c7b8-104">CoreWebView2WebMessageReceivedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="5c7b8-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

<span data-ttu-id="5c7b8-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5c7b8-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5c7b8-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5c7b8-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5c7b8-107">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="5c7b8-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5c7b8-108">Summary</span></span>

 <span data-ttu-id="5c7b8-109">成员</span><span class="sxs-lookup"><span data-stu-id="5c7b8-109">Members</span></span>                        | <span data-ttu-id="5c7b8-110">描述</span><span class="sxs-lookup"><span data-stu-id="5c7b8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5c7b8-111">来源</span><span class="sxs-lookup"><span data-stu-id="5c7b8-111">Source</span></span>](#source) | <span data-ttu-id="5c7b8-112">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="5c7b8-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="5c7b8-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="5c7b8-114">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="5c7b8-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="5c7b8-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="5c7b8-116">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="5c7b8-117">成员</span><span class="sxs-lookup"><span data-stu-id="5c7b8-117">Members</span></span>

#### <span data-ttu-id="5c7b8-118">来源</span><span class="sxs-lookup"><span data-stu-id="5c7b8-118">Source</span></span> 

<span data-ttu-id="5c7b8-119">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="5c7b8-120">公共字符串[源](#source)</span><span class="sxs-lookup"><span data-stu-id="5c7b8-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="5c7b8-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="5c7b8-121">WebMessageAsJson</span></span> 

<span data-ttu-id="5c7b8-122">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="5c7b8-123">公共字符串[WebMessageAsJson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="5c7b8-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="5c7b8-124">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="5c7b8-125">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="5c7b8-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="5c7b8-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="5c7b8-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="5c7b8-127">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="5c7b8-128">公共字符串[TryGetWebMessageAsString](#trygetwebmessageasstring)（）</span><span class="sxs-lookup"><span data-stu-id="5c7b8-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="5c7b8-129">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="5c7b8-130">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="5c7b8-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="5c7b8-131">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="5c7b8-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

