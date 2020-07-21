---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1d3cae59c0906a94414ff135ef8d84fac7cc89b4
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885070"
---
# <span data-ttu-id="c9353-104">0.9.515-WebView2 的 CoreWebView2MoveFocusRequestedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="c9353-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2MoveFocusRequestedEventArgs class</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

<span data-ttu-id="c9353-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="c9353-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="c9353-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="c9353-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="c9353-107">MoveFocusRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="c9353-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="c9353-108">摘要</span><span class="sxs-lookup"><span data-stu-id="c9353-108">Summary</span></span>

 <span data-ttu-id="c9353-109">成员</span><span class="sxs-lookup"><span data-stu-id="c9353-109">Members</span></span>                        | <span data-ttu-id="c9353-110">描述</span><span class="sxs-lookup"><span data-stu-id="c9353-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="c9353-111">Handled</span><span class="sxs-lookup"><span data-stu-id="c9353-111">Handled</span></span>](#handled) | <span data-ttu-id="c9353-112">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="c9353-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="c9353-113">原因</span><span class="sxs-lookup"><span data-stu-id="c9353-113">Reason</span></span>](#reason) | <span data-ttu-id="c9353-114">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="c9353-114">The reason for WebView to fire the MoveFocus Requested event.</span></span>

## <span data-ttu-id="c9353-115">成员</span><span class="sxs-lookup"><span data-stu-id="c9353-115">Members</span></span>

#### <span data-ttu-id="c9353-116">Handled</span><span class="sxs-lookup"><span data-stu-id="c9353-116">Handled</span></span> 

<span data-ttu-id="c9353-117">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="c9353-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="c9353-118">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="c9353-118">public bool [Handled](#handled)</span></span>

<span data-ttu-id="c9353-119">如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="c9353-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="c9353-120">当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。</span><span class="sxs-lookup"><span data-stu-id="c9353-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="c9353-121">默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。</span><span class="sxs-lookup"><span data-stu-id="c9353-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="c9353-122">如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。</span><span class="sxs-lookup"><span data-stu-id="c9353-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="c9353-123">原因</span><span class="sxs-lookup"><span data-stu-id="c9353-123">Reason</span></span> 

<span data-ttu-id="c9353-124">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="c9353-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="c9353-125">公共 CoreWebView2MoveFocusReason[原因](#reason)</span><span class="sxs-lookup"><span data-stu-id="c9353-125">public CoreWebView2MoveFocusReason [Reason](#reason)</span></span>

