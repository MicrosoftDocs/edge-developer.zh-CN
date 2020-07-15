---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceRequestedEventHandler
ms.openlocfilehash: 9cd221ac1b528b0be52201daa0c15217534944a6
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879224"
---
# <span data-ttu-id="3be85-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3be85-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="3be85-105">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="3be85-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="3be85-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3be85-106">Summary</span></span>

 <span data-ttu-id="3be85-107">成员</span><span class="sxs-lookup"><span data-stu-id="3be85-107">Members</span></span>                        | <span data-ttu-id="3be85-108">描述</span><span class="sxs-lookup"><span data-stu-id="3be85-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3be85-109">调用</span><span class="sxs-lookup"><span data-stu-id="3be85-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3be85-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3be85-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="3be85-111">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="3be85-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="3be85-112">成员</span><span class="sxs-lookup"><span data-stu-id="3be85-112">Members</span></span>

#### <span data-ttu-id="3be85-113">调用</span><span class="sxs-lookup"><span data-stu-id="3be85-113">Invoke</span></span> 

<span data-ttu-id="3be85-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3be85-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3be85-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="3be85-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

