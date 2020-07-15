---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: d2b1aa9bbfc15aa44023a43425bb2fc939165cae
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880155"
---
# <span data-ttu-id="581a8-104">0.9.430-接口 ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="581a8-104">0.9.430 - interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="581a8-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="581a8-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="581a8-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="581a8-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="581a8-107">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="581a8-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="581a8-108">摘要</span><span class="sxs-lookup"><span data-stu-id="581a8-108">Summary</span></span>

 <span data-ttu-id="581a8-109">成员</span><span class="sxs-lookup"><span data-stu-id="581a8-109">Members</span></span>                        | <span data-ttu-id="581a8-110">描述</span><span class="sxs-lookup"><span data-stu-id="581a8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="581a8-111">调用</span><span class="sxs-lookup"><span data-stu-id="581a8-111">Invoke</span></span>](#invoke) | <span data-ttu-id="581a8-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="581a8-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="581a8-113">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="581a8-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="581a8-114">成员</span><span class="sxs-lookup"><span data-stu-id="581a8-114">Members</span></span>

#### <span data-ttu-id="581a8-115">调用</span><span class="sxs-lookup"><span data-stu-id="581a8-115">Invoke</span></span> 

<span data-ttu-id="581a8-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="581a8-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="581a8-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="581a8-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

