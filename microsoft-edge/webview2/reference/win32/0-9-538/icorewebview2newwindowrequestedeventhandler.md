---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2NewWindowRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NewWindowRequestedEventHandler
ms.openlocfilehash: 61782812565de1d9a958e4bd3838d39519ad25e9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879553"
---
# <span data-ttu-id="d68e5-104">interface ICoreWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d68e5-104">interface ICoreWebView2NewWindowRequestedEventHandler</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="d68e5-105">调用方实现此接口以接收 Webview.newwindowrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="d68e5-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="d68e5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d68e5-106">Summary</span></span>

 <span data-ttu-id="d68e5-107">成员</span><span class="sxs-lookup"><span data-stu-id="d68e5-107">Members</span></span>                        | <span data-ttu-id="d68e5-108">描述</span><span class="sxs-lookup"><span data-stu-id="d68e5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d68e5-109">调用</span><span class="sxs-lookup"><span data-stu-id="d68e5-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d68e5-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d68e5-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d68e5-111">成员</span><span class="sxs-lookup"><span data-stu-id="d68e5-111">Members</span></span>

#### <span data-ttu-id="d68e5-112">调用</span><span class="sxs-lookup"><span data-stu-id="d68e5-112">Invoke</span></span> 

<span data-ttu-id="d68e5-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d68e5-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d68e5-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="d68e5-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* args)</span></span>

