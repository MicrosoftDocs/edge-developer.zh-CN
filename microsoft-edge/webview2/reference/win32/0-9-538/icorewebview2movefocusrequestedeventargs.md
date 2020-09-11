---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2MoveFocusRequestedEventArgs
ms.openlocfilehash: 7d86b0129c126b39ae8200550a024819e2004b49
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010024"
---
# <span data-ttu-id="01f3e-104">0.9.579-接口 ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="01f3e-104">0.9.579 - interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="01f3e-105">MoveFocusRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="01f3e-105">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="01f3e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="01f3e-106">Summary</span></span>

 <span data-ttu-id="01f3e-107">成员</span><span class="sxs-lookup"><span data-stu-id="01f3e-107">Members</span></span>                        | <span data-ttu-id="01f3e-108">描述</span><span class="sxs-lookup"><span data-stu-id="01f3e-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="01f3e-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="01f3e-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="01f3e-110">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="01f3e-110">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="01f3e-111">get_Reason</span><span class="sxs-lookup"><span data-stu-id="01f3e-111">get_Reason</span></span>](#get_reason) | <span data-ttu-id="01f3e-112">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="01f3e-112">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="01f3e-113">put_Handled</span><span class="sxs-lookup"><span data-stu-id="01f3e-113">put_Handled</span></span>](#put_handled) | <span data-ttu-id="01f3e-114">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="01f3e-114">Set the Handled property.</span></span>

## <span data-ttu-id="01f3e-115">成员</span><span class="sxs-lookup"><span data-stu-id="01f3e-115">Members</span></span>

#### <span data-ttu-id="01f3e-116">get_Handled</span><span class="sxs-lookup"><span data-stu-id="01f3e-116">get_Handled</span></span> 

<span data-ttu-id="01f3e-117">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="01f3e-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="01f3e-118">公共 HRESULT [get_Handled](#get_handled) (BOOL \* 值) </span><span class="sxs-lookup"><span data-stu-id="01f3e-118">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="01f3e-119">如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="01f3e-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="01f3e-120">当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。</span><span class="sxs-lookup"><span data-stu-id="01f3e-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="01f3e-121">默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。</span><span class="sxs-lookup"><span data-stu-id="01f3e-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="01f3e-122">如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。</span><span class="sxs-lookup"><span data-stu-id="01f3e-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="01f3e-123">get_Reason</span><span class="sxs-lookup"><span data-stu-id="01f3e-123">get_Reason</span></span> 

<span data-ttu-id="01f3e-124">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="01f3e-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="01f3e-125">public HRESULT [get_Reason](#get_reason) (COREWEBVIEW2_MOVE_FOCUS_REASON \* 值) </span><span class="sxs-lookup"><span data-stu-id="01f3e-125">public HRESULT [get_Reason](#get_reason)(COREWEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="01f3e-126">put_Handled</span><span class="sxs-lookup"><span data-stu-id="01f3e-126">put_Handled</span></span> 

<span data-ttu-id="01f3e-127">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="01f3e-127">Set the Handled property.</span></span>

> <span data-ttu-id="01f3e-128"> (布尔值的公共 HRESULT [put_Handled](#put_handled)) </span><span class="sxs-lookup"><span data-stu-id="01f3e-128">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

