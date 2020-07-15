---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2MoveFocusRequestedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: dd141e135275d815458ce66a93dfc9ef3e7b33a8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878860"
---
# <span data-ttu-id="62cb4-104">CoreWebView2MoveFocusRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="62cb4-104">Microsoft.Web.WebView2.Core.CoreWebView2MoveFocusRequestedEventArgs class</span></span> 

<span data-ttu-id="62cb4-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="62cb4-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="62cb4-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="62cb4-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="62cb4-107">MoveFocusRequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="62cb4-107">Event args for the MoveFocusRequested event.</span></span>

## <span data-ttu-id="62cb4-108">摘要</span><span class="sxs-lookup"><span data-stu-id="62cb4-108">Summary</span></span>

 <span data-ttu-id="62cb4-109">成员</span><span class="sxs-lookup"><span data-stu-id="62cb4-109">Members</span></span>                        | <span data-ttu-id="62cb4-110">描述</span><span class="sxs-lookup"><span data-stu-id="62cb4-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="62cb4-111">Handled</span><span class="sxs-lookup"><span data-stu-id="62cb4-111">Handled</span></span>](#handled) | <span data-ttu-id="62cb4-112">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="62cb4-112">Indicate whether the event has been handled by the app.</span></span>
[<span data-ttu-id="62cb4-113">原因</span><span class="sxs-lookup"><span data-stu-id="62cb4-113">Reason</span></span>](#reason) | <span data-ttu-id="62cb4-114">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="62cb4-114">The reason for WebView to fire the MoveFocus Requested event.</span></span>

## <span data-ttu-id="62cb4-115">成员</span><span class="sxs-lookup"><span data-stu-id="62cb4-115">Members</span></span>

#### <span data-ttu-id="62cb4-116">Handled</span><span class="sxs-lookup"><span data-stu-id="62cb4-116">Handled</span></span> 

<span data-ttu-id="62cb4-117">指示事件是否已由应用处理。</span><span class="sxs-lookup"><span data-stu-id="62cb4-117">Indicate whether the event has been handled by the app.</span></span>

> <span data-ttu-id="62cb4-118">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="62cb4-118">public bool [Handled](#handled)</span></span>

<span data-ttu-id="62cb4-119">如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。</span><span class="sxs-lookup"><span data-stu-id="62cb4-119">If the app has moved the focus to its desired location, it should set Handled property to TRUE.</span></span> <span data-ttu-id="62cb4-120">当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。</span><span class="sxs-lookup"><span data-stu-id="62cb4-120">When Handled property is false after the event handler returns, default action will be taken.</span></span> <span data-ttu-id="62cb4-121">默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。</span><span class="sxs-lookup"><span data-stu-id="62cb4-121">The default action is to try to find the next tab stop child window in the app and try to move focus to that window.</span></span> <span data-ttu-id="62cb4-122">如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。</span><span class="sxs-lookup"><span data-stu-id="62cb4-122">If there is no other such window to move focus to, focus will be cycled within the WebView's web content.</span></span>

#### <span data-ttu-id="62cb4-123">原因</span><span class="sxs-lookup"><span data-stu-id="62cb4-123">Reason</span></span> 

<span data-ttu-id="62cb4-124">Web 视图触发 MoveFocus 请求事件的原因。</span><span class="sxs-lookup"><span data-stu-id="62cb4-124">The reason for WebView to fire the MoveFocus Requested event.</span></span>

> <span data-ttu-id="62cb4-125">公共 CoreWebView2MoveFocusReason[原因](#reason)</span><span class="sxs-lookup"><span data-stu-id="62cb4-125">public CoreWebView2MoveFocusReason [Reason](#reason)</span></span>

