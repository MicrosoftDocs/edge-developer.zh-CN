---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a3d1f899cb270f9a44d92d647ab2f5a4d5c3b02a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886365"
---
# <span data-ttu-id="0947d-104">0.9.515-WebView2 的 CoreWebView2WebMessageReceivedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="0947d-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="0947d-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="0947d-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="0947d-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="0947d-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="0947d-107">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0947d-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="0947d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="0947d-108">Summary</span></span>

 <span data-ttu-id="0947d-109">成员</span><span class="sxs-lookup"><span data-stu-id="0947d-109">Members</span></span>                        | <span data-ttu-id="0947d-110">描述</span><span class="sxs-lookup"><span data-stu-id="0947d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0947d-111">来源</span><span class="sxs-lookup"><span data-stu-id="0947d-111">Source</span></span>](#source) | <span data-ttu-id="0947d-112">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="0947d-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="0947d-113">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="0947d-113">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="0947d-114">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="0947d-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="0947d-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="0947d-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="0947d-116">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="0947d-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="0947d-117">成员</span><span class="sxs-lookup"><span data-stu-id="0947d-117">Members</span></span>

#### <span data-ttu-id="0947d-118">来源</span><span class="sxs-lookup"><span data-stu-id="0947d-118">Source</span></span> 

<span data-ttu-id="0947d-119">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="0947d-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="0947d-120">公共字符串[源](#source)</span><span class="sxs-lookup"><span data-stu-id="0947d-120">public string [Source](#source)</span></span>

#### <span data-ttu-id="0947d-121">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="0947d-121">WebMessageAsJson</span></span> 

<span data-ttu-id="0947d-122">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="0947d-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="0947d-123">公共字符串[WebMessageAsJson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="0947d-123">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="0947d-124">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="0947d-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="0947d-125">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="0947d-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="0947d-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="0947d-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="0947d-127">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="0947d-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="0947d-128">公共字符串[TryGetWebMessageAsString](#trygetwebmessageasstring)（）</span><span class="sxs-lookup"><span data-stu-id="0947d-128">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="0947d-129">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="0947d-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="0947d-130">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="0947d-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="0947d-131">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="0947d-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

