---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: c57c0df57915361e2d32024a5512616dea96a923
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653143"
---
# <span data-ttu-id="4b10d-104">interface ICoreWebView2WebMessageReceivedEventArgs</span><span class="sxs-lookup"><span data-stu-id="4b10d-104">interface ICoreWebView2WebMessageReceivedEventArgs</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

<span data-ttu-id="4b10d-105">WebMessageReceived 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="4b10d-105">Event args for the WebMessageReceived event.</span></span>

## <span data-ttu-id="4b10d-106">摘要</span><span class="sxs-lookup"><span data-stu-id="4b10d-106">Summary</span></span>

 <span data-ttu-id="4b10d-107">成员</span><span class="sxs-lookup"><span data-stu-id="4b10d-107">Members</span></span>                        | <span data-ttu-id="4b10d-108">描述</span><span class="sxs-lookup"><span data-stu-id="4b10d-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="4b10d-109">get_Source</span><span class="sxs-lookup"><span data-stu-id="4b10d-109">get_Source</span></span>](#get_source) | <span data-ttu-id="4b10d-110">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="4b10d-110">The URI of the document that sent this web message.</span></span>
[<span data-ttu-id="4b10d-111">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="4b10d-111">get_WebMessageAsJson</span></span>](#get_webmessageasjson) | <span data-ttu-id="4b10d-112">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="4b10d-112">The message posted from the webview content to the host converted to a JSON string.</span></span>
[<span data-ttu-id="4b10d-113">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="4b10d-113">TryGetWebMessageAsString</span></span>](#trygetwebmessageasstring) | <span data-ttu-id="4b10d-114">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="4b10d-114">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

## <span data-ttu-id="4b10d-115">成员</span><span class="sxs-lookup"><span data-stu-id="4b10d-115">Members</span></span>

#### <span data-ttu-id="4b10d-116">get_Source</span><span class="sxs-lookup"><span data-stu-id="4b10d-116">get_Source</span></span> 

<span data-ttu-id="4b10d-117">发送此 web 消息的文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="4b10d-117">The URI of the document that sent this web message.</span></span>

> <span data-ttu-id="4b10d-118">公共 HRESULT [get_Source](#get_source)（LPWSTR \* Source）</span><span class="sxs-lookup"><span data-stu-id="4b10d-118">public HRESULT [get_Source](#get_source)(LPWSTR \* source)</span></span>

#### <span data-ttu-id="4b10d-119">get_WebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="4b10d-119">get_WebMessageAsJson</span></span> 

<span data-ttu-id="4b10d-120">从 web 视图内容发布到转换为 JSON 字符串的主机的消息。</span><span class="sxs-lookup"><span data-stu-id="4b10d-120">The message posted from the webview content to the host converted to a JSON string.</span></span>

> <span data-ttu-id="4b10d-121">公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson)（LPWSTR \* WebMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="4b10d-121">public HRESULT [get_WebMessageAsJson](#get_webmessageasjson)(LPWSTR \* webMessageAsJson)</span></span>

<span data-ttu-id="4b10d-122">使用此对象通过 JavaScript 对象进行通信。</span><span class="sxs-lookup"><span data-stu-id="4b10d-122">Use this to communicate via JavaScript objects.</span></span>

<span data-ttu-id="4b10d-123">例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：</span><span class="sxs-lookup"><span data-stu-id="4b10d-123">For example the following postMessage calls result in the following WebMessageAsJson values:</span></span>

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### <span data-ttu-id="4b10d-124">TryGetWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="4b10d-124">TryGetWebMessageAsString</span></span> 

<span data-ttu-id="4b10d-125">如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。</span><span class="sxs-lookup"><span data-stu-id="4b10d-125">If the message posted from the webview content to the host is a string type, this method will return the value of that string.</span></span>

> <span data-ttu-id="4b10d-126">公共 HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)（LPWSTR \* webMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="4b10d-126">public HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)(LPWSTR \* webMessageAsString)</span></span>

<span data-ttu-id="4b10d-127">如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="4b10d-127">If the message posted is some other kind of JavaScript type this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="4b10d-128">使用此操作通过简单字符串进行通信。</span><span class="sxs-lookup"><span data-stu-id="4b10d-128">Use this to communicate via simple strings.</span></span>

<span data-ttu-id="4b10d-129">例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：</span><span class="sxs-lookup"><span data-stu-id="4b10d-129">For example the following postMessage calls result in the following WebMessageAsString values:</span></span>

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```
