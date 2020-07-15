---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebMessageReceivedEventHandler
ms.openlocfilehash: 47402035918c49a86c8e973c207d4f54d7d829c7
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879350"
---
# <span data-ttu-id="d1e3f-104">interface ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d1e3f-104">interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="d1e3f-105">调用方实现此接口以接收 WebMessageReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="d1e3f-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="d1e3f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d1e3f-106">Summary</span></span>

 <span data-ttu-id="d1e3f-107">成员</span><span class="sxs-lookup"><span data-stu-id="d1e3f-107">Members</span></span>                        | <span data-ttu-id="d1e3f-108">描述</span><span class="sxs-lookup"><span data-stu-id="d1e3f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d1e3f-109">调用</span><span class="sxs-lookup"><span data-stu-id="d1e3f-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d1e3f-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d1e3f-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="d1e3f-111">成员</span><span class="sxs-lookup"><span data-stu-id="d1e3f-111">Members</span></span>

#### <span data-ttu-id="d1e3f-112">调用</span><span class="sxs-lookup"><span data-stu-id="d1e3f-112">Invoke</span></span> 

<span data-ttu-id="d1e3f-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d1e3f-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d1e3f-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="d1e3f-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

