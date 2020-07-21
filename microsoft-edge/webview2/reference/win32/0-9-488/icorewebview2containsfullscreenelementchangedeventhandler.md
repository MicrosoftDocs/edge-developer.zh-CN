---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 41687dcb162d8d56e773b9050898e9f22bd034ab
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883880"
---
# <span data-ttu-id="7f2d1-104">0.9.515-接口 ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="7f2d1-104">0.9.515 - interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="7f2d1-105">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="7f2d1-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="7f2d1-106">摘要</span><span class="sxs-lookup"><span data-stu-id="7f2d1-106">Summary</span></span>

 <span data-ttu-id="7f2d1-107">成员</span><span class="sxs-lookup"><span data-stu-id="7f2d1-107">Members</span></span>                        | <span data-ttu-id="7f2d1-108">描述</span><span class="sxs-lookup"><span data-stu-id="7f2d1-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7f2d1-109">调用</span><span class="sxs-lookup"><span data-stu-id="7f2d1-109">Invoke</span></span>](#invoke) | <span data-ttu-id="7f2d1-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7f2d1-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="7f2d1-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="7f2d1-111">There are no event args for this event.</span></span>

## <span data-ttu-id="7f2d1-112">成员</span><span class="sxs-lookup"><span data-stu-id="7f2d1-112">Members</span></span>

#### <span data-ttu-id="7f2d1-113">调用</span><span class="sxs-lookup"><span data-stu-id="7f2d1-113">Invoke</span></span> 

<span data-ttu-id="7f2d1-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="7f2d1-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="7f2d1-115">公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数）</span><span class="sxs-lookup"><span data-stu-id="7f2d1-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="7f2d1-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="7f2d1-116">There are no event args and the args parameter will be null.</span></span>

