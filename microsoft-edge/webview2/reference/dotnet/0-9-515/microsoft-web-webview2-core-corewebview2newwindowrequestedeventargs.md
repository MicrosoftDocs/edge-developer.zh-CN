---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: d10154fbaeb8dca0247dc721a2144899feba38df
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880008"
---
# <span data-ttu-id="5b010-104">0.9.515-WebView2 的 CoreWebView2NewWindowRequestedEventArgs 类</span><span class="sxs-lookup"><span data-stu-id="5b010-104">0.9.515 - Microsoft.Web.WebView2.Core.CoreWebView2NewWindowRequestedEventArgs class</span></span> 

> [!NOTE]
> <span data-ttu-id="5b010-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="5b010-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="5b010-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="5b010-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="5b010-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5b010-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5b010-108">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5b010-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5b010-109">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="5b010-109">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="5b010-110">摘要</span><span class="sxs-lookup"><span data-stu-id="5b010-110">Summary</span></span>

 <span data-ttu-id="5b010-111">成员</span><span class="sxs-lookup"><span data-stu-id="5b010-111">Members</span></span>                        | <span data-ttu-id="5b010-112">描述</span><span class="sxs-lookup"><span data-stu-id="5b010-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5b010-113">Handled</span><span class="sxs-lookup"><span data-stu-id="5b010-113">Handled</span></span>](#handled) | <span data-ttu-id="5b010-114">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="5b010-114">Whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="5b010-115">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5b010-115">IsUserInitiated</span></span>](#isuserinitiated) | <span data-ttu-id="5b010-116">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="5b010-116">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="5b010-117">NewWindow</span><span class="sxs-lookup"><span data-stu-id="5b010-117">NewWindow</span></span>](#newwindow) | <span data-ttu-id="5b010-118">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="5b010-118">Gets the new window.</span></span>
[<span data-ttu-id="5b010-119">Uri</span><span class="sxs-lookup"><span data-stu-id="5b010-119">Uri</span></span>](#uri) | <span data-ttu-id="5b010-120">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="5b010-120">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="5b010-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="5b010-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="5b010-122">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="5b010-122">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

<span data-ttu-id="5b010-123">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="5b010-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="5b010-124">成员</span><span class="sxs-lookup"><span data-stu-id="5b010-124">Members</span></span>

#### <span data-ttu-id="5b010-125">Handled</span><span class="sxs-lookup"><span data-stu-id="5b010-125">Handled</span></span> 

<span data-ttu-id="5b010-126">NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="5b010-126">Whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="5b010-127">公共 bool 已[处理](#handled)</span><span class="sxs-lookup"><span data-stu-id="5b010-127">public bool [Handled](#handled)</span></span>

<span data-ttu-id="5b010-128">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="5b010-128">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="5b010-129">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="5b010-129">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="5b010-130">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="5b010-130">Default is false.</span></span>

#### <span data-ttu-id="5b010-131">IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="5b010-131">IsUserInitiated</span></span> 

<span data-ttu-id="5b010-132">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="5b010-132">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="5b010-133">公共 bool [IsUserInitiated](#isuserinitiated)</span><span class="sxs-lookup"><span data-stu-id="5b010-133">public bool [IsUserInitiated](#isuserinitiated)</span></span>

#### <span data-ttu-id="5b010-134">NewWindow</span><span class="sxs-lookup"><span data-stu-id="5b010-134">NewWindow</span></span> 

<span data-ttu-id="5b010-135">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="5b010-135">Gets the new window.</span></span>

> <span data-ttu-id="5b010-136">公共 CoreWebView2 [NewWindow](#newwindow)</span><span class="sxs-lookup"><span data-stu-id="5b010-136">public CoreWebView2 [NewWindow](#newwindow)</span></span>

#### <span data-ttu-id="5b010-137">Uri</span><span class="sxs-lookup"><span data-stu-id="5b010-137">Uri</span></span> 

<span data-ttu-id="5b010-138">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="5b010-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="5b010-139">公共字符串[Uri](#uri)</span><span class="sxs-lookup"><span data-stu-id="5b010-139">public string [Uri](#uri)</span></span>

<span data-ttu-id="5b010-140">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="5b010-140">The target webview should not be navigated.</span></span> <span data-ttu-id="5b010-141">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="5b010-141">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="5b010-142">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="5b010-142">GetDeferral</span></span> 

<span data-ttu-id="5b010-143">获取 CoreWebView2Deferral 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="5b010-143">Obtain a CoreWebView2Deferral object and put the event into a deferred state.</span></span>

> <span data-ttu-id="5b010-144">公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）</span><span class="sxs-lookup"><span data-stu-id="5b010-144">public CoreWebView2Deferral [GetDeferral](#getdeferral)()</span></span>

<span data-ttu-id="5b010-145">你可以使用 CoreWebView2Deferral 对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="5b010-145">You can use the CoreWebView2Deferral object to complete the window open request at a later time.</span></span> <span data-ttu-id="5b010-146">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="5b010-146">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

