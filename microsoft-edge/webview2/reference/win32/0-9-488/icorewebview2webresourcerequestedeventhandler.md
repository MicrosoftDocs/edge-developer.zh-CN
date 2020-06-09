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
ms.openlocfilehash: 622a7e93912a3380cc0d7dabae9293734cd3fcfa
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697936"
---
# <span data-ttu-id="26735-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="26735-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

> [!NOTE]
> <span data-ttu-id="26735-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="26735-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="26735-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="26735-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="26735-107">在 web 视图中发出 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="26735-107">Fires when an HTTP request is made in the webview.</span></span>

## <span data-ttu-id="26735-108">摘要</span><span class="sxs-lookup"><span data-stu-id="26735-108">Summary</span></span>

 <span data-ttu-id="26735-109">成员</span><span class="sxs-lookup"><span data-stu-id="26735-109">Members</span></span>                        | <span data-ttu-id="26735-110">描述</span><span class="sxs-lookup"><span data-stu-id="26735-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="26735-111">调用</span><span class="sxs-lookup"><span data-stu-id="26735-111">Invoke</span></span>](#invoke) | <span data-ttu-id="26735-112">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="26735-112">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="26735-113">主机可以替代请求、响应标头和响应内容。</span><span class="sxs-lookup"><span data-stu-id="26735-113">The host can override request, response headers and response content.</span></span>

## <span data-ttu-id="26735-114">成员</span><span class="sxs-lookup"><span data-stu-id="26735-114">Members</span></span>

#### <span data-ttu-id="26735-115">调用</span><span class="sxs-lookup"><span data-stu-id="26735-115">Invoke</span></span> 

<span data-ttu-id="26735-116">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="26735-116">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="26735-117">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="26735-117">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

