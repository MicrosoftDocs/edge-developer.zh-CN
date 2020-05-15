---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2f3effd612303d1532c7220d566791a800753b37
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652842"
---
# <span data-ttu-id="cdee4-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="cdee4-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="cdee4-105">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="cdee4-105">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="cdee4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="cdee4-106">Summary</span></span>

 <span data-ttu-id="cdee4-107">成员</span><span class="sxs-lookup"><span data-stu-id="cdee4-107">Members</span></span>                        | <span data-ttu-id="cdee4-108">描述</span><span class="sxs-lookup"><span data-stu-id="cdee4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="cdee4-109">调用</span><span class="sxs-lookup"><span data-stu-id="cdee4-109">Invoke</span></span>](#invoke) | <span data-ttu-id="cdee4-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="cdee4-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="cdee4-111">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="cdee4-111">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="cdee4-112">成员</span><span class="sxs-lookup"><span data-stu-id="cdee4-112">Members</span></span>

#### <span data-ttu-id="cdee4-113">调用</span><span class="sxs-lookup"><span data-stu-id="cdee4-113">Invoke</span></span> 

<span data-ttu-id="cdee4-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="cdee4-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="cdee4-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="cdee4-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

