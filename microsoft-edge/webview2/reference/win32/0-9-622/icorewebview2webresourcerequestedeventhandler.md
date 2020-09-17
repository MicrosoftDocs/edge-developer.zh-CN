---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceRequestedEventHandler
ms.openlocfilehash: 6aa36c8b28a3e47a796324987687ab23179aae10
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011621"
---
# <span data-ttu-id="97643-104">interface ICoreWebView2WebResourceRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="97643-104">interface ICoreWebView2WebResourceRequestedEventHandler</span></span> 

```
interface ICoreWebView2WebResourceRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="97643-105">当 URL 请求通过网络 (、文件等 ) 在 Web 资源匹配的 Web 资源和 AddWebResourceRequestedFilter 中指定的 URL 的 Web 视图中进行时激发。</span><span class="sxs-lookup"><span data-stu-id="97643-105">Fires when a URL request (through network, file etc.) is made in the webview for a Web resource matching resource context filter and URL specified in AddWebResourceRequestedFilter.</span></span>

## <span data-ttu-id="97643-106">摘要</span><span class="sxs-lookup"><span data-stu-id="97643-106">Summary</span></span>

 <span data-ttu-id="97643-107">成员</span><span class="sxs-lookup"><span data-stu-id="97643-107">Members</span></span>                        | <span data-ttu-id="97643-108">描述</span><span class="sxs-lookup"><span data-stu-id="97643-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="97643-109">调用</span><span class="sxs-lookup"><span data-stu-id="97643-109">Invoke</span></span>](#invoke) | <span data-ttu-id="97643-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="97643-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="97643-111">宿主可以查看和修改请求，或向 HTTP 提供类似模式的响应，在这种情况下，请求立即完成。</span><span class="sxs-lookup"><span data-stu-id="97643-111">The host can view and modify the request or provide a response in a similar pattern to HTTP, in which case the request immediately completed.</span></span> <span data-ttu-id="97643-112">这可能不包含由网络堆栈添加的任何请求标头，如授权标头。</span><span class="sxs-lookup"><span data-stu-id="97643-112">This may not contain any request headers that are added by the network stack, such as Authorization headers.</span></span>

## <span data-ttu-id="97643-113">成员</span><span class="sxs-lookup"><span data-stu-id="97643-113">Members</span></span>

#### <span data-ttu-id="97643-114">调用</span><span class="sxs-lookup"><span data-stu-id="97643-114">Invoke</span></span> 

<span data-ttu-id="97643-115">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="97643-115">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="97643-116">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="97643-116">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebResourceRequestedEventArgs](icorewebview2webresourcerequestedeventargs.md) \* args)</span></span>
