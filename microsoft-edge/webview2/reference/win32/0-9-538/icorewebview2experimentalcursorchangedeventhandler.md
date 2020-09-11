---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2ExperimentalCursorChangedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalCursorChangedEventHandler
ms.openlocfilehash: e9bf743f9417645bee7a5692f5ef9ca9b646e7ab
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010220"
---
# <span data-ttu-id="96a45-104">0.9.579-接口 ICoreWebView2ExperimentalCursorChangedEventHandler</span><span class="sxs-lookup"><span data-stu-id="96a45-104">0.9.579 - interface ICoreWebView2ExperimentalCursorChangedEventHandler</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCursorChangedEventHandler
  : public IUnknown
```

<span data-ttu-id="96a45-105">调用方实现此接口以接收 CursorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="96a45-105">The caller implements this interface to receive CursorChanged events.</span></span>

## <span data-ttu-id="96a45-106">摘要</span><span class="sxs-lookup"><span data-stu-id="96a45-106">Summary</span></span>

 <span data-ttu-id="96a45-107">成员</span><span class="sxs-lookup"><span data-stu-id="96a45-107">Members</span></span>                        | <span data-ttu-id="96a45-108">描述</span><span class="sxs-lookup"><span data-stu-id="96a45-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="96a45-109">调用</span><span class="sxs-lookup"><span data-stu-id="96a45-109">Invoke</span></span>](#invoke) | <span data-ttu-id="96a45-110">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="96a45-110">Called to provide the implementer with the event args for the corresponding event.</span></span>

<span data-ttu-id="96a45-111">使用 Cursor 属性获取新光标。</span><span class="sxs-lookup"><span data-stu-id="96a45-111">Use the Cursor property to get the new cursor.</span></span>

## <span data-ttu-id="96a45-112">成员</span><span class="sxs-lookup"><span data-stu-id="96a45-112">Members</span></span>

#### <span data-ttu-id="96a45-113">调用</span><span class="sxs-lookup"><span data-stu-id="96a45-113">Invoke</span></span> 

<span data-ttu-id="96a45-114">调用以向实施者提供对应事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="96a45-114">Called to provide the implementer with the event args for the corresponding event.</span></span>

> <span data-ttu-id="96a45-115">公共 HRESULT [调用](#invoke) ([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender、IUnknown \* 参数) </span><span class="sxs-lookup"><span data-stu-id="96a45-115">public HRESULT [Invoke](#invoke)([ICoreWebView2ExperimentalCompositionController](icorewebview2experimentalcompositioncontroller.md) \* sender, IUnknown \* args)</span></span>

<span data-ttu-id="96a45-116">没有事件参数，args 参数将为 null。</span><span class="sxs-lookup"><span data-stu-id="96a45-116">There are no event args and the args parameter will be null.</span></span>

