---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ProcessFailedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ProcessFailedEventHandler
ms.openlocfilehash: 5ae5a64bfbcd0692d7c284974e960f9ed6249e50
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877397"
---
# <span data-ttu-id="fc846-104">interface ICoreWebView2ProcessFailedEventHandler</span><span class="sxs-lookup"><span data-stu-id="fc846-104">interface ICoreWebView2ProcessFailedEventHandler</span></span> 

```
interface ICoreWebView2ProcessFailedEventHandler
  : public IUnknown
```

<span data-ttu-id="fc846-105">调用方实现此接口以接收 ProcessFailed 事件。</span><span class="sxs-lookup"><span data-stu-id="fc846-105">The caller implements this interface to receive ProcessFailed events.</span></span>

## <span data-ttu-id="fc846-106">摘要</span><span class="sxs-lookup"><span data-stu-id="fc846-106">Summary</span></span>

 <span data-ttu-id="fc846-107">成员</span><span class="sxs-lookup"><span data-stu-id="fc846-107">Members</span></span>                        | <span data-ttu-id="fc846-108">描述</span><span class="sxs-lookup"><span data-stu-id="fc846-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="fc846-109">调用</span><span class="sxs-lookup"><span data-stu-id="fc846-109">Invoke</span></span>](#invoke) | <span data-ttu-id="fc846-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fc846-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="fc846-111">成员</span><span class="sxs-lookup"><span data-stu-id="fc846-111">Members</span></span>

#### <span data-ttu-id="fc846-112">调用</span><span class="sxs-lookup"><span data-stu-id="fc846-112">Invoke</span></span> 

<span data-ttu-id="fc846-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="fc846-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="fc846-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="fc846-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2ProcessFailedEventArgs](icorewebview2processfailedeventargs.md) \* args)</span></span>

