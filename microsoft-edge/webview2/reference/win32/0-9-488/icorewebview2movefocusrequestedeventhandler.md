---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2MoveFocusRequestedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 45f9b638347d096ce89c9fcaac1bfb7e904ebee9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886284"
---
# <span data-ttu-id="faf71-104">0.9.515-接口 ICoreWebView2MoveFocusRequestedEventHandler</span><span class="sxs-lookup"><span data-stu-id="faf71-104">0.9.515 - interface ICoreWebView2MoveFocusRequestedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventHandler
  : public IUnknown
```

<span data-ttu-id="faf71-105">调用方实现此方法以接收 MoveFocusRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="faf71-105">The caller implements this method to receive the MoveFocusRequested event.</span></span>

## <span data-ttu-id="faf71-106">摘要</span><span class="sxs-lookup"><span data-stu-id="faf71-106">Summary</span></span>

 <span data-ttu-id="faf71-107">成员</span><span class="sxs-lookup"><span data-stu-id="faf71-107">Members</span></span>                        | <span data-ttu-id="faf71-108">描述</span><span class="sxs-lookup"><span data-stu-id="faf71-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="faf71-109">调用</span><span class="sxs-lookup"><span data-stu-id="faf71-109">Invoke</span></span>](#invoke) | <span data-ttu-id="faf71-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="faf71-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

## <span data-ttu-id="faf71-111">成员</span><span class="sxs-lookup"><span data-stu-id="faf71-111">Members</span></span>

#### <span data-ttu-id="faf71-112">调用</span><span class="sxs-lookup"><span data-stu-id="faf71-112">Invoke</span></span> 

<span data-ttu-id="faf71-113">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="faf71-113">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="faf71-114">公共 HRESULT[调用](#invoke)（[ICoreWebView2Controller](icorewebview2controller.md) \* sender、 [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* 参数）</span><span class="sxs-lookup"><span data-stu-id="faf71-114">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, [ICoreWebView2MoveFocusRequestedEventArgs](icorewebview2movefocusrequestedeventargs.md) \* args)</span></span>

