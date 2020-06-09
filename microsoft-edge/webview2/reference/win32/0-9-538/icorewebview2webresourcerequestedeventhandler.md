---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 64f29f8c771a14d569fd45f7359614795bbc0386
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698559"
---
# <span data-ttu-id="129a8-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="129a8-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="129a8-105">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="129a8-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="129a8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="129a8-106">Summary</span></span>

 <span data-ttu-id="129a8-107">成员</span><span class="sxs-lookup"><span data-stu-id="129a8-107">Members</span></span>                        | <span data-ttu-id="129a8-108">描述</span><span class="sxs-lookup"><span data-stu-id="129a8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="129a8-109">调用</span><span class="sxs-lookup"><span data-stu-id="129a8-109">Invoke</span></span>](#invoke) | <span data-ttu-id="129a8-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="129a8-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="129a8-111">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="129a8-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="129a8-112">成员</span><span class="sxs-lookup"><span data-stu-id="129a8-112">Members</span></span>

#### <span data-ttu-id="129a8-113">调用</span><span class="sxs-lookup"><span data-stu-id="129a8-113">Invoke</span></span> 

<span data-ttu-id="129a8-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="129a8-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="129a8-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="129a8-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

