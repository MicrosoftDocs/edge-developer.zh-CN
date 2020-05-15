---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: c4f76c468cc5001c9eae347247dd5ffb8a60594f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653158"
---
# <span data-ttu-id="1badb-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="1badb-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="1badb-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="1badb-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="1badb-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="1badb-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="1badb-107">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="1badb-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="1badb-108">摘要</span><span class="sxs-lookup"><span data-stu-id="1badb-108">Summary</span></span>

 <span data-ttu-id="1badb-109">成员</span><span class="sxs-lookup"><span data-stu-id="1badb-109">Members</span></span>                        | <span data-ttu-id="1badb-110">描述</span><span class="sxs-lookup"><span data-stu-id="1badb-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1badb-111">调用</span><span class="sxs-lookup"><span data-stu-id="1badb-111">Invoke</span></span>](#invoke) | <span data-ttu-id="1badb-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1badb-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="1badb-113">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="1badb-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="1badb-114">成员</span><span class="sxs-lookup"><span data-stu-id="1badb-114">Members</span></span>

#### <span data-ttu-id="1badb-115">调用</span><span class="sxs-lookup"><span data-stu-id="1badb-115">Invoke</span></span> 

<span data-ttu-id="1badb-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1badb-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="1badb-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) \* sender、[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="1badb-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](ICoreWebView2.md) \* sender,[ICoreWebView2WebResourceRequestedEventArgs](ICoreWebView2WebResourceRequestedEventArgs.md) \* args)</span></span>

