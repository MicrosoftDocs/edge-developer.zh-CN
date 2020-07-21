---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2DevToolsProtocolEventReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: a26a2c18c402bffe11353b2f53f0559acde3663b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886157"
---
# <span data-ttu-id="e2c94-104">0.8.355-接口 IWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="e2c94-104">0.8.355 - interface IWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="e2c94-105">调用方实现此接口以接收来自[IWebView2WebView](IWebView2WebView.md)的 DevToolsProtocolEventReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="e2c94-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the [IWebView2WebView](IWebView2WebView.md).</span></span>

## <span data-ttu-id="e2c94-106">摘要</span><span class="sxs-lookup"><span data-stu-id="e2c94-106">Summary</span></span>

 <span data-ttu-id="e2c94-107">成员</span><span class="sxs-lookup"><span data-stu-id="e2c94-107">Members</span></span>                        | <span data-ttu-id="e2c94-108">描述</span><span class="sxs-lookup"><span data-stu-id="e2c94-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e2c94-109">调用</span><span class="sxs-lookup"><span data-stu-id="e2c94-109">Invoke</span></span>](#invoke) | <span data-ttu-id="e2c94-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e2c94-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="e2c94-111">成员</span><span class="sxs-lookup"><span data-stu-id="e2c94-111">Members</span></span>

#### <span data-ttu-id="e2c94-112">调用</span><span class="sxs-lookup"><span data-stu-id="e2c94-112">Invoke</span></span> 

<span data-ttu-id="e2c94-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="e2c94-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="e2c94-114">公共 HRESULT[调用](#invoke)（[IWebView2WebView](IWebView2WebView.md) \* web 视图，[IWebView2DevToolsProtocolEventReceivedEventArgs](IWebView2DevToolsProtocolEventReceivedEventArgs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="e2c94-114">public HRESULT [Invoke](#invoke)([IWebView2WebView](IWebView2WebView.md) \* webview,[IWebView2DevToolsProtocolEventReceivedEventArgs](IWebView2DevToolsProtocolEventReceivedEventArgs.md) \* args)</span></span>

