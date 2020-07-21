---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceRequestedEventHandler
ms.openlocfilehash: 3cdafae6480a3bf6e3a5bf96f7e7fba1ae8cc77c
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884517"
---
# <span data-ttu-id="c5f87-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="c5f87-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="c5f87-105">在与 AddWebResourceRequestedFilter 中指定的 Web 资源匹配的 Web 资源的 Web 资源中进行 URL 请求（通过网络、文件等）时激发。</span><span class="sxs-lookup"><span data-stu-id="c5f87-105">Fires when a URL request (through network, file etc.) is made in the webview for a Web resource matching resource context filter and URL specified in AddWebResourceRequestedFilter.</span></span>

## <span data-ttu-id="c5f87-106">摘要</span><span class="sxs-lookup"><span data-stu-id="c5f87-106">Summary</span></span>

 <span data-ttu-id="c5f87-107">成员</span><span class="sxs-lookup"><span data-stu-id="c5f87-107">Members</span></span>                        | <span data-ttu-id="c5f87-108">描述</span><span class="sxs-lookup"><span data-stu-id="c5f87-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c5f87-109">调用</span><span class="sxs-lookup"><span data-stu-id="c5f87-109">Invoke</span></span>](#invoke) | <span data-ttu-id="c5f87-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c5f87-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="c5f87-111">宿主可以查看和修改请求，或向 HTTP 提供类似模式的响应，在这种情况下，请求立即完成。</span><span class="sxs-lookup"><span data-stu-id="c5f87-111">The host can view and modify the request or provide a response in a similar pattern to HTTP, in which case the request immediately completed.</span></span> <span data-ttu-id="c5f87-112">这可能不包含由网络堆栈添加的任何请求标头，如授权标头。</span><span class="sxs-lookup"><span data-stu-id="c5f87-112">This may not contain any request headers that are added by the network stack, such as Authorization headers.</span></span>

## <span data-ttu-id="c5f87-113">成员</span><span class="sxs-lookup"><span data-stu-id="c5f87-113">Members</span></span>

#### <span data-ttu-id="c5f87-114">调用</span><span class="sxs-lookup"><span data-stu-id="c5f87-114">Invoke</span></span> 

<span data-ttu-id="c5f87-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c5f87-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="c5f87-116">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="c5f87-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>

