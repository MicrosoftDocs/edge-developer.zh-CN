---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2DevToolsProtocolEventReceivedEventHandler
ms.openlocfilehash: 163ab3f16b6d835fc64aef4ea0fdff2883084faa
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010262"
---
# <span data-ttu-id="ae086-104">0.9.579-接口 ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="ae086-104">0.9.579 - interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="ae086-105">调用方实现此接口以接收 Web 视图中的 DevToolsProtocolEventReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="ae086-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="ae086-106">摘要</span><span class="sxs-lookup"><span data-stu-id="ae086-106">Summary</span></span>

 <span data-ttu-id="ae086-107">成员</span><span class="sxs-lookup"><span data-stu-id="ae086-107">Members</span></span>                        | <span data-ttu-id="ae086-108">描述</span><span class="sxs-lookup"><span data-stu-id="ae086-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="ae086-109">调用</span><span class="sxs-lookup"><span data-stu-id="ae086-109">Invoke</span></span>](#invoke) | <span data-ttu-id="ae086-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ae086-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="ae086-111">成员</span><span class="sxs-lookup"><span data-stu-id="ae086-111">Members</span></span>

#### <span data-ttu-id="ae086-112">调用</span><span class="sxs-lookup"><span data-stu-id="ae086-112">Invoke</span></span> 

<span data-ttu-id="ae086-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="ae086-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="ae086-114">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="ae086-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

