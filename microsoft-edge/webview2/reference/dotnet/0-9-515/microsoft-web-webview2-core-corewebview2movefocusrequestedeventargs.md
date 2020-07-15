---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 37d64a18589df936383efe05317c1a625b841a6e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877656"
---
# <span data-ttu-id="98b03-104">0.9.515-WebView2 的 CoreWebView2MoveFocusRequestedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="98b03-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2MoveFocusRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="98b03-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="98b03-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="98b03-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="98b03-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="98b03-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="98b03-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="98b03-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="98b03-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="98b03-109">MoveFocusRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="98b03-109">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="98b03-110">摘要</span><span class="sxs-lookup"><span data-stu-id="98b03-110">Summary</span></span>

 <span data-ttu-id="98b03-111">成员</span><span class="sxs-lookup"><span data-stu-id="98b03-111">Members</span></span>                        | <span data-ttu-id="98b03-112">描述</span><span class="sxs-lookup"><span data-stu-id="98b03-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="98b03-113">Handled</span><span class="sxs-lookup"><span data-stu-id="98b03-113">Handled</span></span>](#handled) | <span data-ttu-id="98b03-114">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="98b03-114">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="98b03-115">原因</span><span class="sxs-lookup"><span data-stu-id="98b03-115">Reason</span></span>](#reason) | <span data-ttu-id="98b03-116">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="98b03-116">The reason for WebView to fire the MoveFocus Requested event.</span></span>

## <span data-ttu-id="98b03-117">成员</span><span class="sxs-lookup"><span data-stu-id="98b03-117">Members</span></span>

#### <span data-ttu-id="98b03-118">Handled</span><span class="sxs-lookup"><span data-stu-id="98b03-118">Handled</span></span> 

<span data-ttu-id="98b03-119">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="98b03-119">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="98b03-120">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="98b03-120">public bool [Handled](#handled)</span></span>

<span data-ttu-id="98b03-121">如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="98b03-121">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="98b03-122">当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。</span><span class="sxs-lookup"><span data-stu-id="98b03-122">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="98b03-123">默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。</span><span class="sxs-lookup"><span data-stu-id="98b03-123">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="98b03-124">如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。</span><span class="sxs-lookup"><span data-stu-id="98b03-124">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="98b03-125">原因</span><span class="sxs-lookup"><span data-stu-id="98b03-125">Reason</span></span> 

<span data-ttu-id="98b03-126">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="98b03-126">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="98b03-127">公共 CoreWebView2MoveFocusReason[原因](#reason)</span><span class="sxs-lookup"><span data-stu-id="98b03-127">public CoreWebView2MoveFocusReason [Reason](#reason)</span></span>

