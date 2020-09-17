---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2NewWindowRequestedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5e5d16c025dccf788b355280eaa3ac3e910f240d
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011672"
---
# <span data-ttu-id="99f47-104">CoreWebView2NewWindowRequestedEventArgs 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="99f47-104">Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

<span data-ttu-id="99f47-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="99f47-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="99f47-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="99f47-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="99f47-107">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="99f47-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="99f47-108">摘要</span><span class="sxs-lookup"><span data-stu-id="99f47-108">Summary</span></span>

 <span data-ttu-id="99f47-109">成员</span><span class="sxs-lookup"><span data-stu-id="99f47-109">Members</span></span>                        | <span data-ttu-id="99f47-110">描述</span><span class="sxs-lookup"><span data-stu-id="99f47-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="99f47-111">Handled</span><span class="sxs-lookup"><span data-stu-id="99f47-111">Handled</span></span>](#handled) | <span data-ttu-id="99f47-112">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="99f47-112">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="99f47-113">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="99f47-113">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="99f47-114">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="99f47-114">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="99f47-115">NewWindow</span><span class="sxs-lookup"><span data-stu-id="99f47-115">NewWindow</span></span>](#newwindow) | <span data-ttu-id="99f47-116">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="99f47-116">Gets the new window.</span></span>
[<span data-ttu-id="99f47-117">Uri</span><span class="sxs-lookup"><span data-stu-id="99f47-117">Uri</span></span>](#uri) | <span data-ttu-id="99f47-118">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="99f47-118">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="99f47-119">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="99f47-119">WindowFeatures</span></span>](#windowfeatures) | <span data-ttu-id="99f47-120">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="99f47-120">Window features specified by the window.open call.</span></span>
[<span data-ttu-id="99f47-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="99f47-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="99f47-122">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="99f47-122">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="99f47-123">当 Web 浏览中请求打开一个新窗口 (通过 window 打开一个新窗口时，将引发此事件。 ) 打开 ( # A2 的内容。</span><span class="sxs-lookup"><span data-stu-id="99f47-123">The event is fired when content inside WebView requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="99f47-124">成员</span><span class="sxs-lookup"><span data-stu-id="99f47-124">Members</span></span>

#### <span data-ttu-id="99f47-125">Handled</span><span class="sxs-lookup"><span data-stu-id="99f47-125">Handled</span></span> 

<span data-ttu-id="99f47-126">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="99f47-126">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="99f47-127">公共 bool 已 [处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="99f47-127">public bool [Handled](#handled)</span></span>

<span data-ttu-id="99f47-128">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="99f47-128">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="99f47-129">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="99f47-129">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="99f47-130">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="99f47-130">Default is false.</span></span>

#### <span data-ttu-id="99f47-131">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="99f47-131">IsUserInitiated</span></span> 

<span data-ttu-id="99f47-132">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="99f47-132">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="99f47-133">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="99f47-133">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="99f47-134">NewWindow</span><span class="sxs-lookup"><span data-stu-id="99f47-134">NewWindow</span></span> 

<span data-ttu-id="99f47-135">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="99f47-135">Gets the new window.</span></span>

> <span data-ttu-id="99f47-136">公共 CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="99f47-136">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="99f47-137">Uri</span><span class="sxs-lookup"><span data-stu-id="99f47-137">Uri</span></span> 

<span data-ttu-id="99f47-138">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="99f47-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="99f47-139">公共字符串 [Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="99f47-139">public string [Uri](#uri)</span></span>

<span data-ttu-id="99f47-140">不应导航目标 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="99f47-140">The target WebView should not be navigated.</span></span> <span data-ttu-id="99f47-141">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="99f47-141">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="99f47-142">WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="99f47-142">WindowFeatures</span></span> 

<span data-ttu-id="99f47-143">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="99f47-143">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="99f47-144">公共 CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)</span><span class="sxs-lookup"><span data-stu-id="99f47-144">public CoreWebView2WindowFeatures [WindowFeatures](#windowfeatures)</span></span>

<span data-ttu-id="99f47-145">可将这些功能考虑到新的 Web 视图窗口的位置和大小调整。</span><span class="sxs-lookup"><span data-stu-id="99f47-145">These features can be considered for positioning and sizing of new WebView windows.</span></span>

#### <span data-ttu-id="99f47-146">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="99f47-146">GetDeferral</span></span> 

<span data-ttu-id="99f47-147">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="99f47-147">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="99f47-148">公共 CoreWebView2Deferral [GetDeferral](#getdeferral) ( # A1</span><span class="sxs-lookup"><span data-stu-id="99f47-148">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="99f47-149">你可以使用 CoreWebView2Deferral 对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="99f47-149">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="99f47-150">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="99f47-150">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>
