---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: c154b80e29476666bc0b2121b3eba63009946b36
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698469"
---
# <span data-ttu-id="3f751-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="3f751-104">interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler</span></span> 

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="3f751-105">调用方实现此接口以接收 Web 视图中的 DevToolsProtocolEventReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="3f751-105">The caller implements this interface to receive DevToolsProtocolEventReceived events from the WebView.</span></span>

## <span data-ttu-id="3f751-106">摘要</span><span class="sxs-lookup"><span data-stu-id="3f751-106">Summary</span></span>

 <span data-ttu-id="3f751-107">成员</span><span class="sxs-lookup"><span data-stu-id="3f751-107">Members</span></span>                        | <span data-ttu-id="3f751-108">描述</span><span class="sxs-lookup"><span data-stu-id="3f751-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="3f751-109">调用</span><span class="sxs-lookup"><span data-stu-id="3f751-109">Invoke</span></span>](#invoke) | <span data-ttu-id="3f751-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3f751-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="3f751-111">成员</span><span class="sxs-lookup"><span data-stu-id="3f751-111">Members</span></span>

#### <span data-ttu-id="3f751-112">调用</span><span class="sxs-lookup"><span data-stu-id="3f751-112">Invoke</span></span> 

<span data-ttu-id="3f751-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="3f751-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="3f751-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="3f751-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2DevToolsProtocolEventReceivedEventArgs](icorewebview2devtoolsprotocoleventreceivedeventargs.md) \* args)</span></span>

