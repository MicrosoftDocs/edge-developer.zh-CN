---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2FocusChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2FocusChangedEventHandler
ms.openlocfilehash: 7e02fb9480f70dbffe6d33cfd7fb436c26c97da3
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011361"
---
# <span data-ttu-id="bc5db-104">0.9.579-接口 ICoreWebView2FocusChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="bc5db-104">0.9.579 - interface ICoreWebView2FocusChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2FocusChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="bc5db-105">调用方实现此方法以接收 GotFocus 和 LostFocus 事件。</span><span class="sxs-lookup"><span data-stu-id="bc5db-105">The caller implements this method to receive the GotFocus and LostFocus events.</span></span>

## <span data-ttu-id="bc5db-106">摘要</span><span class="sxs-lookup"><span data-stu-id="bc5db-106">Summary</span></span>

 <span data-ttu-id="bc5db-107">成员</span><span class="sxs-lookup"><span data-stu-id="bc5db-107">Members</span></span>                        | <span data-ttu-id="bc5db-108">描述</span><span class="sxs-lookup"><span data-stu-id="bc5db-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="bc5db-109">调用</span><span class="sxs-lookup"><span data-stu-id="bc5db-109">Invoke</span></span>](#invoke) | <span data-ttu-id="bc5db-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bc5db-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="bc5db-111">此事件没有事件参数。</span><span class="sxs-lookup"><span data-stu-id="bc5db-111">There are no event args for this event.</span></span>

## <span data-ttu-id="bc5db-112">成员</span><span class="sxs-lookup"><span data-stu-id="bc5db-112">Members</span></span>

#### <span data-ttu-id="bc5db-113">调用</span><span class="sxs-lookup"><span data-stu-id="bc5db-113">Invoke</span></span> 

<span data-ttu-id="bc5db-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="bc5db-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="bc5db-115">公共 HRESULT [调用](#invoke) ([ICoreWebView2Controller](icorewebview2controller.md) \* sender、IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="bc5db-115">public HRESULT [Invoke](#invoke)([ICoreWebView2Controller](icorewebview2controller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="bc5db-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="bc5db-116">There are no event args and the args parameter will be null.</span></span>

