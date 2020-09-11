---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2WebMessageReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebMessageReceivedEventHandler
ms.openlocfilehash: 77af4fc8c3e05e46883e6d2428d9fa9015815f8b
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010367"
---
# <span data-ttu-id="01e09-104">0.9.579-接口 ICoreWebView2WebMessageReceivedEventHandler</span><span class="sxs-lookup"><span data-stu-id="01e09-104">0.9.579 - interface ICoreWebView2WebMessageReceivedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebMessageReceivedEventHandler
  : public IUnknown
```

<span data-ttu-id="01e09-105">调用方实现此接口以接收 WebMessageReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="01e09-105">The caller implements this interface to receive the WebMessageReceived event.</span></span>

## <span data-ttu-id="01e09-106">摘要</span><span class="sxs-lookup"><span data-stu-id="01e09-106">Summary</span></span>

 <span data-ttu-id="01e09-107">成员</span><span class="sxs-lookup"><span data-stu-id="01e09-107">Members</span></span>                        | <span data-ttu-id="01e09-108">描述</span><span class="sxs-lookup"><span data-stu-id="01e09-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="01e09-109">调用</span><span class="sxs-lookup"><span data-stu-id="01e09-109">Invoke</span></span>](#invoke) | <span data-ttu-id="01e09-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="01e09-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="01e09-111">成员</span><span class="sxs-lookup"><span data-stu-id="01e09-111">Members</span></span>

#### <span data-ttu-id="01e09-112">调用</span><span class="sxs-lookup"><span data-stu-id="01e09-112">Invoke</span></span> 

<span data-ttu-id="01e09-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="01e09-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="01e09-114">public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、 [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* 参数) </span><span class="sxs-lookup"><span data-stu-id="01e09-114">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, [ICoreWebView2WebMessageReceivedEventArgs](icorewebview2webmessagereceivedeventargs.md) \* args)</span></span>

