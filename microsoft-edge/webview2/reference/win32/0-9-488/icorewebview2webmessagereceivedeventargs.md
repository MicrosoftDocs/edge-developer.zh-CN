---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 40215d0c32b30000a93f59343547d60fc377ba03
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877320"
---
# <span data-ttu-id="d7f5f-104">0.9.515-接口 ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="d7f5f-104">0.9.515 - interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="d7f5f-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="d7f5f-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="d7f5f-107">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="d7f5f-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d7f5f-108">Summary</span></span>

 <span data-ttu-id="d7f5f-109">成员</span><span class="sxs-lookup"><span data-stu-id="d7f5f-109">Members</span></span>                        | <span data-ttu-id="d7f5f-110">描述</span><span class="sxs-lookup"><span data-stu-id="d7f5f-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d7f5f-111">get_Source</span><span class="sxs-lookup"><span data-stu-id="d7f5f-111">get_Source</span></span>](#get_source) | <span data-ttu-id="d7f5f-112">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="d7f5f-113">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="d7f5f-113">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="d7f5f-114">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="d7f5f-115">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="d7f5f-115">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="d7f5f-116">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="d7f5f-117">成员</span><span class="sxs-lookup"><span data-stu-id="d7f5f-117">Members</span></span>

#### <span data-ttu-id="d7f5f-118">get_Source</span><span class="sxs-lookup"><span data-stu-id="d7f5f-118">get_Source</span></span> 

<span data-ttu-id="d7f5f-119">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="d7f5f-120">公共 HRESULT [get_Source](#get_source)（LPWSTR \* Source）</span><span class="sxs-lookup"><span data-stu-id="d7f5f-120">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="d7f5f-121">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="d7f5f-121">get_WebMessageAsJson</span></span> 

<span data-ttu-id="d7f5f-122">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="d7f5f-123">公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson)（LPWSTR \* WebMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="d7f5f-123">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="d7f5f-124">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="d7f5f-125">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="d7f5f-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="d7f5f-126">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="d7f5f-126">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="d7f5f-127">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="d7f5f-128">公共 HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)（LPWSTR \* webMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="d7f5f-128">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="d7f5f-129">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="d7f5f-130">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="d7f5f-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="d7f5f-131">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="d7f5f-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

