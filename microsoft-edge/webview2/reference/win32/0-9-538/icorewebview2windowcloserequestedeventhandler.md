---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2WindowCloseRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WindowCloseRequestedEventHandler
ms.openlocfilehash: 34b0f941029251824cdc108e0aca41e6eab93695
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011375"
---
# <span data-ttu-id="a8363-104">0.9.579-接口 ICoreWebView2WindowCloseRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="a8363-104">0.9.579 - interface ICoreWebView2WindowCloseRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WindowCloseRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="a8363-105">调用方实现此接口以接收 Webview.newwindowrequested 事件。</span><span class="sxs-lookup"><span data-stu-id="a8363-105">The caller implements this interface to receive NewWindowRequested events.</span></span>

## <span data-ttu-id="a8363-106">摘要</span><span class="sxs-lookup"><span data-stu-id="a8363-106">Summary</span></span>

 <span data-ttu-id="a8363-107">成员</span><span class="sxs-lookup"><span data-stu-id="a8363-107">Members</span></span>                        | <span data-ttu-id="a8363-108">描述</span><span class="sxs-lookup"><span data-stu-id="a8363-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a8363-109">调用</span><span class="sxs-lookup"><span data-stu-id="a8363-109">Invoke</span></span>](#invoke) | <span data-ttu-id="a8363-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a8363-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="a8363-111">成员</span><span class="sxs-lookup"><span data-stu-id="a8363-111">Members</span></span>

#### <span data-ttu-id="a8363-112">调用</span><span class="sxs-lookup"><span data-stu-id="a8363-112">Invoke</span></span> 

<span data-ttu-id="a8363-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="a8363-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="a8363-114">公共 HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="a8363-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="a8363-115">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="a8363-115">There are no event args and the args parameter will be null.</span></span>

