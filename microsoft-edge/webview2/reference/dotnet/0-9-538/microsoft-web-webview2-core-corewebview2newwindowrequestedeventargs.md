---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2NewWindowRequestedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 2a2934e1fef6c601155cb4002a0c97ca1629099e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878804"
---
# <span data-ttu-id="9106e-104">CoreWebView2NewWindowRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="9106e-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

<span data-ttu-id="9106e-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="9106e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="9106e-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="9106e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="9106e-107">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="9106e-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="9106e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9106e-108">Summary</span></span>

 <span data-ttu-id="9106e-109">成员</span><span class="sxs-lookup"><span data-stu-id="9106e-109">Members</span></span>                        | <span data-ttu-id="9106e-110">描述</span><span class="sxs-lookup"><span data-stu-id="9106e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9106e-111">Handled</span><span class="sxs-lookup"><span data-stu-id="9106e-111">Handled</span></span>](#handled) | <span data-ttu-id="9106e-112">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="9106e-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="9106e-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="9106e-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="9106e-114">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="9106e-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="9106e-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="9106e-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="9106e-116">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="9106e-116">Gets the new window.</span></span>
[<span data-ttu-id="9106e-117">Uri</span><span class="sxs-lookup"><span data-stu-id="9106e-117">Uri</span></span>](#uri) | <span data-ttu-id="9106e-118">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="9106e-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="9106e-119">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="9106e-119">WindowFeatures</span></span>](#windowfeatures) | <span data-ttu-id="9106e-120">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="9106e-120">Window features specified by the window.open call.</span></span>
[<span data-ttu-id="9106e-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="9106e-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="9106e-122">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="9106e-122">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="9106e-123">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="9106e-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="9106e-124">成员</span><span class="sxs-lookup"><span data-stu-id="9106e-124">Members</span></span>

#### <span data-ttu-id="9106e-125">Handled</span><span class="sxs-lookup"><span data-stu-id="9106e-125">Handled</span></span> 

<span data-ttu-id="9106e-126">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="9106e-126">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="9106e-127">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="9106e-127">public bool [Handled](#handled)</span></span>

<span data-ttu-id="9106e-128">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="9106e-128">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="9106e-129">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="9106e-129">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="9106e-130">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="9106e-130">Default is false.</span></span>

#### <span data-ttu-id="9106e-131">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="9106e-131">IsUserInitiated</span></span> 

<span data-ttu-id="9106e-132">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="9106e-132">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="9106e-133">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="9106e-133">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="9106e-134">NewWindow</span><span class="sxs-lookup"><span data-stu-id="9106e-134">NewWindow</span></span> 

<span data-ttu-id="9106e-135">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="9106e-135">Gets the new window.</span></span>

> <span data-ttu-id="9106e-136">公共 CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="9106e-136">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="9106e-137">Uri</span><span class="sxs-lookup"><span data-stu-id="9106e-137">Uri</span></span> 

<span data-ttu-id="9106e-138">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="9106e-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="9106e-139">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="9106e-139">public string [Uri](#uri)</span></span>

<span data-ttu-id="9106e-140">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="9106e-140">The target webview should not be navigated.</span></span> <span data-ttu-id="9106e-141">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="9106e-141">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="9106e-142">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="9106e-142">WindowFeatures</span></span> 

<span data-ttu-id="9106e-143">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="9106e-143">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="9106e-144">公共 CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="9106e-144">public CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)</span></span>

<span data-ttu-id="9106e-145">可将这些功能考虑到新的 web 视图窗口的位置和大小调整。</span><span class="sxs-lookup"><span data-stu-id="9106e-145">These features can be considered for positioning and sizing of new webview windows.</span></span>

#### <span data-ttu-id="9106e-146">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="9106e-146">GetDeferral</span></span> 

<span data-ttu-id="9106e-147">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="9106e-147">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="9106e-148">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="9106e-148">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="9106e-149">你可以使用 CoreWebView2Deferral 对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="9106e-149">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="9106e-150">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="9106e-150">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

