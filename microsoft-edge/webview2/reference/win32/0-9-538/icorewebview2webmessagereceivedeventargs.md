---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebMessageReceivedEventArgs
ms.openlocfilehash: 61805f34ac3ef3a51dcd5b746b77a7bdad8cdb5c
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877600"
---
# <span data-ttu-id="ce502-104">interface ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="ce502-104">interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="ce502-105">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ce502-105">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="ce502-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ce502-106">Summary</span></span>

 <span data-ttu-id="ce502-107">成员</span><span class="sxs-lookup"><span data-stu-id="ce502-107">Members</span></span>                        | <span data-ttu-id="ce502-108">描述</span><span class="sxs-lookup"><span data-stu-id="ce502-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ce502-109">get_Source</span><span class="sxs-lookup"><span data-stu-id="ce502-109">get_Source</span></span>](#get_source) | <span data-ttu-id="ce502-110">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="ce502-110">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="ce502-111">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="ce502-111">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="ce502-112">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="ce502-112">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="ce502-113">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="ce502-113">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="ce502-114">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="ce502-114">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="ce502-115">成员</span><span class="sxs-lookup"><span data-stu-id="ce502-115">Members</span></span>

#### <span data-ttu-id="ce502-116">get_Source</span><span class="sxs-lookup"><span data-stu-id="ce502-116">get_Source</span></span> 

<span data-ttu-id="ce502-117">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="ce502-117">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="ce502-118">公共 HRESULT [get_Source](#get_source)（LPWSTR \* Source）</span><span class="sxs-lookup"><span data-stu-id="ce502-118">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="ce502-119">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="ce502-119">get_WebMessageAsJson</span></span> 

<span data-ttu-id="ce502-120">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="ce502-120">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="ce502-121">公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson)（LPWSTR \* WebMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="ce502-121">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="ce502-122">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce502-122">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="ce502-123">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="ce502-123">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="ce502-124">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="ce502-124">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="ce502-125">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="ce502-125">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="ce502-126">公共 HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)（LPWSTR \* webMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="ce502-126">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="ce502-127">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="ce502-127">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="ce502-128">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="ce502-128">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="ce502-129">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="ce502-129">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

