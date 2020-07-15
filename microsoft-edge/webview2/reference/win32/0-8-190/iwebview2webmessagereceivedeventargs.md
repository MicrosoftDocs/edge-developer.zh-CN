---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: d70162803cfb2f9d1f0cfbf7e7397ee1cdbeec0e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878188"
---
# <span data-ttu-id="fcb0c-104">0.8.355-接口 IWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="fcb0c-104">0.8.355 - interface IWebView2WebMessageReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="fcb0c-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="fcb0c-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="fcb0c-107">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="fcb0c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="fcb0c-108">Summary</span></span>

 <span data-ttu-id="fcb0c-109">成员</span><span class="sxs-lookup"><span data-stu-id="fcb0c-109">Members</span></span>                        | <span data-ttu-id="fcb0c-110">描述</span><span class="sxs-lookup"><span data-stu-id="fcb0c-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fcb0c-111">get_Source</span><span class="sxs-lookup"><span data-stu-id="fcb0c-111">get_Source</span></span>](#get_source) | <span data-ttu-id="fcb0c-112">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="fcb0c-113">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="fcb0c-113">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="fcb0c-114">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="fcb0c-115">get_WebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="fcb0c-115">get_WebMessageAsString</span></span>](#get_webmessageasstring) | <span data-ttu-id="fcb0c-116">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="fcb0c-117">成员</span><span class="sxs-lookup"><span data-stu-id="fcb0c-117">Members</span></span>

#### <span data-ttu-id="fcb0c-118">get_Source</span><span class="sxs-lookup"><span data-stu-id="fcb0c-118">get_Source</span></span> 

<span data-ttu-id="fcb0c-119">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="fcb0c-120">公共 HRESULT [get_Source](#get_source)（LPWSTR \* Source）</span><span class="sxs-lookup"><span data-stu-id="fcb0c-120">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="fcb0c-121">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="fcb0c-121">get_WebMessageAsJson</span></span> 

<span data-ttu-id="fcb0c-122">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="fcb0c-123">公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson)（LPWSTR \* WebMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="fcb0c-123">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="fcb0c-124">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="fcb0c-125">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="fcb0c-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```cpp
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="fcb0c-126">get_WebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="fcb0c-126">get_WebMessageAsString</span></span> 

<span data-ttu-id="fcb0c-127">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="fcb0c-128">公共 HRESULT [get_WebMessageAsString](#get_webmessageasstring)（LPWSTR \* WebMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="fcb0c-128">public HRESULT [get_WebMessageAsString](#get_webmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="fcb0c-129">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="fcb0c-130">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="fcb0c-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="fcb0c-131">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="fcb0c-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```cpp
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

