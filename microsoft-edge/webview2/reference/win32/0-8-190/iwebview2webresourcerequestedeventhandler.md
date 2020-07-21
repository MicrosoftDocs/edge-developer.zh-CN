---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 70ecc1898f9a72656f12b912d103116c381d4218
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885672"
---
# <span data-ttu-id="fc832-104">0.8.355-接口 IWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fc832-104">0.8.355 - interface IWebView2WebResourceRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="fc832-105">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="fc832-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="fc832-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fc832-106">Summary</span></span>

 <span data-ttu-id="fc832-107">成员</span><span class="sxs-lookup"><span data-stu-id="fc832-107">Members</span></span>                        | <span data-ttu-id="fc832-108">描述</span><span class="sxs-lookup"><span data-stu-id="fc832-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fc832-109">调用</span><span class="sxs-lookup"><span data-stu-id="fc832-109">Invoke</span></span>](#invoke) | <span data-ttu-id="fc832-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fc832-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="fc832-111">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="fc832-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="fc832-112">成员</span><span class="sxs-lookup"><span data-stu-id="fc832-112">Members</span></span>

#### <span data-ttu-id="fc832-113">调用</span><span class="sxs-lookup"><span data-stu-id="fc832-113">Invoke</span></span> 

<span data-ttu-id="fc832-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fc832-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="fc832-115">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="fc832-115">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

