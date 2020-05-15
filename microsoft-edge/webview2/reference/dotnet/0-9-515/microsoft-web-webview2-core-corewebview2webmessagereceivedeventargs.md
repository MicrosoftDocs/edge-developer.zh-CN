---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f9bedb19620b0669d4aac35be4786702940b2a72
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652891"
---
# <span data-ttu-id="e2b30-104">CoreWebView2WebMessageReceivedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="e2b30-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

<span data-ttu-id="e2b30-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="e2b30-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="e2b30-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="e2b30-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="e2b30-107">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e2b30-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="e2b30-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e2b30-108">Summary</span></span>

 <span data-ttu-id="e2b30-109">成员</span><span class="sxs-lookup"><span data-stu-id="e2b30-109">Members</span></span>                        | <span data-ttu-id="e2b30-110">描述</span><span class="sxs-lookup"><span data-stu-id="e2b30-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e2b30-111">来源</span><span class="sxs-lookup"><span data-stu-id="e2b30-111">Source</span></span>](#source) | <span data-ttu-id="e2b30-112">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="e2b30-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="e2b30-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="e2b30-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="e2b30-114">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="e2b30-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="e2b30-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="e2b30-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="e2b30-116">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="e2b30-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="e2b30-117">成员</span><span class="sxs-lookup"><span data-stu-id="e2b30-117">Members</span></span>

#### <span data-ttu-id="e2b30-118">来源</span><span class="sxs-lookup"><span data-stu-id="e2b30-118">Source</span></span> 

<span data-ttu-id="e2b30-119">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="e2b30-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="e2b30-120">公共字符串[源](#source)</span><span class="sxs-lookup"><span data-stu-id="e2b30-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="e2b30-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="e2b30-121">WebMessageAsJson</span></span> 

<span data-ttu-id="e2b30-122">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="e2b30-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="e2b30-123">公共字符串[WebMessageAsJson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="e2b30-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="e2b30-124">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="e2b30-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="e2b30-125">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="e2b30-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="e2b30-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="e2b30-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="e2b30-127">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="e2b30-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="e2b30-128">公共字符串[TryGetWebMessageAsString](#trygetwebmessageasstring)（）</span><span class="sxs-lookup"><span data-stu-id="e2b30-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="e2b30-129">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="e2b30-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="e2b30-130">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="e2b30-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="e2b30-131">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="e2b30-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

