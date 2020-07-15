---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: c0980f26ef06497cded81e2f9c7c00162af18d9b
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878090"
---
# <span data-ttu-id="1967d-104">0.8.355-接口 IWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1967d-104">0.8.355 - interface IWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="1967d-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="1967d-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="1967d-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="1967d-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="1967d-107">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="1967d-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="1967d-108">摘要</span><span class="sxs-lookup"><span data-stu-id="1967d-108">Summary</span></span>

 <span data-ttu-id="1967d-109">成员</span><span class="sxs-lookup"><span data-stu-id="1967d-109">Members</span></span>                        | <span data-ttu-id="1967d-110">描述</span><span class="sxs-lookup"><span data-stu-id="1967d-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1967d-111">调用</span><span class="sxs-lookup"><span data-stu-id="1967d-111">Invoke</span></span>](#invoke) | <span data-ttu-id="1967d-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1967d-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="1967d-113">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="1967d-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="1967d-114">成员</span><span class="sxs-lookup"><span data-stu-id="1967d-114">Members</span></span>

#### <span data-ttu-id="1967d-115">调用</span><span class="sxs-lookup"><span data-stu-id="1967d-115">Invoke</span></span> 

<span data-ttu-id="1967d-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1967d-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1967d-117">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="1967d-117">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2WebResourceRequestedEventArgs](IWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

