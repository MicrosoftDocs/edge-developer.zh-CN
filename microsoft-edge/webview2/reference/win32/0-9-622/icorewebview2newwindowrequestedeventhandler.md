---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2NewWindowRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NewWindowRequestedEventHandler
ms.openlocfilehash: 99fb8261e6ed170b09bc87f9a1372e0e2cc53954
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011781"
---
# <span data-ttu-id="bfa29-104">interface ICoreWebView2NewWindowRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="bfa29-104">interface ICoreWebView2NewWindowRequestedEventHandler</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="bfa29-105">调用方实现此接口以接收 Webview.newwindowrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="bfa29-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="bfa29-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bfa29-106">Summary</span></span>

 <span data-ttu-id="bfa29-107">成员</span><span class="sxs-lookup"><span data-stu-id="bfa29-107">Members</span></span>                        | <span data-ttu-id="bfa29-108">描述</span><span class="sxs-lookup"><span data-stu-id="bfa29-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bfa29-109">调用</span><span class="sxs-lookup"><span data-stu-id="bfa29-109">Invoke</span></span>](#invoke) | <span data-ttu-id="bfa29-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bfa29-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="bfa29-111">成员</span><span class="sxs-lookup"><span data-stu-id="bfa29-111">Members</span></span>

#### <span data-ttu-id="bfa29-112">调用</span><span class="sxs-lookup"><span data-stu-id="bfa29-112">Invoke</span></span> 

<span data-ttu-id="bfa29-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bfa29-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="bfa29-114">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="bfa29-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2NewWindowRequestedEventArgs](icorewebview2newwindowrequestedeventargs.md) \* args)</span></span>

