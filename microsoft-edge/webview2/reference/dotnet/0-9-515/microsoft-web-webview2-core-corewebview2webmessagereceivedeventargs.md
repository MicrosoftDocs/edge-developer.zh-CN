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
ms.openlocfilehash: b917f309194316b26ee94aa94dc8289ef4430007
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697537"
---
# <span data-ttu-id="a0d0c-104">CoreWebView2WebMessageReceivedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a0d0c-104">Microsoft.Web.WebView2.Core.CoreWebView2WebMessageReceivedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="a0d0c-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="a0d0c-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="a0d0c-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a0d0c-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a0d0c-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="a0d0c-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a0d0c-109">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-109">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="a0d0c-110">摘要</span><span class="sxs-lookup"><span data-stu-id="a0d0c-110">Summary</span></span>

 <span data-ttu-id="a0d0c-111">成员</span><span class="sxs-lookup"><span data-stu-id="a0d0c-111">Members</span></span>                        | <span data-ttu-id="a0d0c-112">描述</span><span class="sxs-lookup"><span data-stu-id="a0d0c-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a0d0c-113">来源</span><span class="sxs-lookup"><span data-stu-id="a0d0c-113">Source</span></span>](#source) | <span data-ttu-id="a0d0c-114">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-114">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="a0d0c-115">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="a0d0c-115">WebMessageAsJson</span></span>](#webmessageasjson) | <span data-ttu-id="a0d0c-116">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-116">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="a0d0c-117">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="a0d0c-117">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="a0d0c-118">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-118">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="a0d0c-119">成员</span><span class="sxs-lookup"><span data-stu-id="a0d0c-119">Members</span></span>

#### <span data-ttu-id="a0d0c-120">来源</span><span class="sxs-lookup"><span data-stu-id="a0d0c-120">Source</span></span> 

<span data-ttu-id="a0d0c-121">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-121">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="a0d0c-122">公共字符串[源](#source)</span><span class="sxs-lookup"><span data-stu-id="a0d0c-122">public string [Source](#source)</span></span>

#### <span data-ttu-id="a0d0c-123">WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="a0d0c-123">WebMessageAsJson</span></span> 

<span data-ttu-id="a0d0c-124">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-124">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="a0d0c-125">公共字符串[WebMessageAsJson](#webmessageasjson)</span><span class="sxs-lookup"><span data-stu-id="a0d0c-125">public string [WebMessageAsJson](#webmessageasjson)</span></span>

<span data-ttu-id="a0d0c-126">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-126">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="a0d0c-127">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="a0d0c-127">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="a0d0c-128">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="a0d0c-128">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="a0d0c-129">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-129">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="a0d0c-130">公共字符串[TryGetWebMessageAsString](#trygetwebmessageasstring)（）</span><span class="sxs-lookup"><span data-stu-id="a0d0c-130">public string [TryGetWebMessageAsString](#trygetwebmessageasstring)()</span></span>

<span data-ttu-id="a0d0c-131">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-131">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="a0d0c-132">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="a0d0c-132">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="a0d0c-133">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="a0d0c-133">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

