---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 643e2e998cc8ca70bfd90fbcb9bbf1f6c690322b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884545"
---
# <span data-ttu-id="f328f-104">0.9.430-接口 ICoreWebView2MoveFocusRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="f328f-104">0.9.430 - interface ICoreWebView2MoveFocusRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="f328f-105">MoveFocusRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="f328f-105">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="f328f-106">摘要</span><span class="sxs-lookup"><span data-stu-id="f328f-106">Summary</span></span>

 <span data-ttu-id="f328f-107">成员</span><span class="sxs-lookup"><span data-stu-id="f328f-107">Members</span></span>                        | <span data-ttu-id="f328f-108">描述</span><span class="sxs-lookup"><span data-stu-id="f328f-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f328f-109">get_Reason</span><span class="sxs-lookup"><span data-stu-id="f328f-109">get_Reason</span></span>](#get_reason) | <span data-ttu-id="f328f-110">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="f328f-110">The reason for WebView to fire the MoveFocus Requested event.</span></span>
[<span data-ttu-id="f328f-111">get_Handled</span><span class="sxs-lookup"><span data-stu-id="f328f-111">get_Handled</span></span>](#get_handled) | <span data-ttu-id="f328f-112">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="f328f-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="f328f-113">put_Handled</span><span class="sxs-lookup"><span data-stu-id="f328f-113">put_Handled</span></span>](#put_handled) | <span data-ttu-id="f328f-114">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="f328f-114">Set the Handled property.</span></span>

## <span data-ttu-id="f328f-115">成员</span><span class="sxs-lookup"><span data-stu-id="f328f-115">Members</span></span>

#### <span data-ttu-id="f328f-116">get_Reason</span><span class="sxs-lookup"><span data-stu-id="f328f-116">get_Reason</span></span> 

<span data-ttu-id="f328f-117">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="f328f-117">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="f328f-118">public HRESULT [get_Reason](#get_reason)（CORE_WEBVIEW2_MOVE_FOCUS_REASON \* 值）</span><span class="sxs-lookup"><span data-stu-id="f328f-118">public HRESULT [get_Reason](#get_reason)(CORE_WEBVIEW2_MOVE_FOCUS_REASON \* value)</span></span>

#### <span data-ttu-id="f328f-119">get_Handled</span><span class="sxs-lookup"><span data-stu-id="f328f-119">get_Handled</span></span> 

<span data-ttu-id="f328f-120">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="f328f-120">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="f328f-121">公共 HRESULT [get_Handled](#get_handled)（布尔 \* 值）</span><span class="sxs-lookup"><span data-stu-id="f328f-121">public HRESULT [get_Handled](#get_handled)(BOOL \* value)</span></span>

<span data-ttu-id="f328f-122">如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="f328f-122">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="f328f-123">当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。</span><span class="sxs-lookup"><span data-stu-id="f328f-123">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="f328f-124">默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。</span><span class="sxs-lookup"><span data-stu-id="f328f-124">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="f328f-125">如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。</span><span class="sxs-lookup"><span data-stu-id="f328f-125">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="f328f-126">put_Handled</span><span class="sxs-lookup"><span data-stu-id="f328f-126">put_Handled</span></span> 

<span data-ttu-id="f328f-127">设置已处理的属性。</span><span class="sxs-lookup"><span data-stu-id="f328f-127">Set the Handled property.</span></span>

> <span data-ttu-id="f328f-128">public HRESULT [put_Handled](#put_handled)（布尔值）</span><span class="sxs-lookup"><span data-stu-id="f328f-128">public HRESULT [put_Handled](#put_handled)(BOOL value)</span></span>

