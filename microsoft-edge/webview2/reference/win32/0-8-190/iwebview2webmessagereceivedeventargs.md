---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 053e186aec3871b47e2eb5c6684bc00c934c3a77
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652923"
---
# <span data-ttu-id="61eb0-104">interface IWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="61eb0-104">interface IWebView2WebMessageReceivedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="61eb0-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="61eb0-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="61eb0-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="61eb0-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="61eb0-107">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="61eb0-107">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="61eb0-108">摘要</span><span class="sxs-lookup"><span data-stu-id="61eb0-108">Summary</span></span>

 <span data-ttu-id="61eb0-109">成员</span><span class="sxs-lookup"><span data-stu-id="61eb0-109">Members</span></span>                        | <span data-ttu-id="61eb0-110">描述</span><span class="sxs-lookup"><span data-stu-id="61eb0-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="61eb0-111">get_Source</span><span class="sxs-lookup"><span data-stu-id="61eb0-111">get_Source</span></span>](#get_source) | <span data-ttu-id="61eb0-112">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="61eb0-112">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="61eb0-113">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="61eb0-113">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="61eb0-114">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="61eb0-114">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="61eb0-115">get_WebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="61eb0-115">get_WebMessageAsString</span></span>](#get_webmessageasstring) | <span data-ttu-id="61eb0-116">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="61eb0-116">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="61eb0-117">成员</span><span class="sxs-lookup"><span data-stu-id="61eb0-117">Members</span></span>

#### <span data-ttu-id="61eb0-118">get_Source</span><span class="sxs-lookup"><span data-stu-id="61eb0-118">get_Source</span></span> 

<span data-ttu-id="61eb0-119">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="61eb0-119">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="61eb0-120">公共 HRESULT [get_Source](#get_source)（LPWSTR \* Source）</span><span class="sxs-lookup"><span data-stu-id="61eb0-120">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="61eb0-121">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="61eb0-121">get_WebMessageAsJson</span></span> 

<span data-ttu-id="61eb0-122">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="61eb0-122">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="61eb0-123">公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson)（LPWSTR \* WebMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="61eb0-123">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="61eb0-124">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="61eb0-124">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="61eb0-125">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="61eb0-125">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```cpp
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="61eb0-126">get_WebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="61eb0-126">get_WebMessageAsString</span></span> 

<span data-ttu-id="61eb0-127">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="61eb0-127">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="61eb0-128">公共 HRESULT [get_WebMessageAsString](#get_webmessageasstring)（LPWSTR \* WebMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="61eb0-128">public HRESULT [get_WebMessageAsString](#get_webmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="61eb0-129">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="61eb0-129">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="61eb0-130">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="61eb0-130">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="61eb0-131">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="61eb0-131">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```cpp
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

