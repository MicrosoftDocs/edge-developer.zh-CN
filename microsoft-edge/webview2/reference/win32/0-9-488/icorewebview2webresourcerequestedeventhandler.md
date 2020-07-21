---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 4f2bb4e5077fea7583f7d9f9886923ea1867e1ce
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883678"
---
# <span data-ttu-id="142f3-104">0.9.515-接口 ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="142f3-104">0.9.515 - interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="142f3-105">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="142f3-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="142f3-106">摘要</span><span class="sxs-lookup"><span data-stu-id="142f3-106">Summary</span></span>

 <span data-ttu-id="142f3-107">成员</span><span class="sxs-lookup"><span data-stu-id="142f3-107">Members</span></span>                        | <span data-ttu-id="142f3-108">描述</span><span class="sxs-lookup"><span data-stu-id="142f3-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="142f3-109">调用</span><span class="sxs-lookup"><span data-stu-id="142f3-109">Invoke</span></span>](#invoke) | <span data-ttu-id="142f3-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="142f3-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="142f3-111">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="142f3-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="142f3-112">成员</span><span class="sxs-lookup"><span data-stu-id="142f3-112">Members</span></span>

#### <span data-ttu-id="142f3-113">调用</span><span class="sxs-lookup"><span data-stu-id="142f3-113">Invoke</span></span> 

<span data-ttu-id="142f3-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="142f3-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="142f3-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="142f3-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

