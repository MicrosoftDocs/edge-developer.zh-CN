---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ContainsFullScreenElementChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ContainsFullScreenElementChangedEventHandler
ms.openlocfilehash: 0477f9868dc472cab71dad4b10ff85fa034515a1
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011804"
---
# <span data-ttu-id="d39d5-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="d39d5-104">interface ICoreWebView2ContainsFullScreenElementChangedEventHandler</span></span> 

```
interface ICoreWebView2ContainsFullScreenElementChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="d39d5-105">调用方实现此方法以接收 ContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="d39d5-105">The caller implements this method to receive the ContainsFullScreenElementChanged events.</span></span>

## <span data-ttu-id="d39d5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="d39d5-106">Summary</span></span>

 <span data-ttu-id="d39d5-107">成员</span><span class="sxs-lookup"><span data-stu-id="d39d5-107">Members</span></span>                        | <span data-ttu-id="d39d5-108">描述</span><span class="sxs-lookup"><span data-stu-id="d39d5-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d39d5-109">调用</span><span class="sxs-lookup"><span data-stu-id="d39d5-109">Invoke</span></span>](#invoke) | <span data-ttu-id="d39d5-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d39d5-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="d39d5-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="d39d5-111">There are no event args for this event.</span></span>

## <span data-ttu-id="d39d5-112">成员</span><span class="sxs-lookup"><span data-stu-id="d39d5-112">Members</span></span>

#### <span data-ttu-id="d39d5-113">调用</span><span class="sxs-lookup"><span data-stu-id="d39d5-113">Invoke</span></span> 

<span data-ttu-id="d39d5-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="d39d5-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="d39d5-115">公共 HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) \* sender、IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="d39d5-115">public HRESULT [Invoke](#invoke)([ICoreWebView2](icorewebview2.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="d39d5-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="d39d5-116">There are no event args and the args parameter will be null.</span></span>
