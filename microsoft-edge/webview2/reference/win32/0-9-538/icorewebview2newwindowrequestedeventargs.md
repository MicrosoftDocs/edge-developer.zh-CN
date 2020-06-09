---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: af8df8ff67a0fbe7fd4ec9308b1562b9ef987933
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698571"
---
# <span data-ttu-id="0f5c8-104">interface ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="0f5c8-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="0f5c8-105">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="0f5c8-106">摘要</span><span class="sxs-lookup"><span data-stu-id="0f5c8-106">Summary</span></span>

 <span data-ttu-id="0f5c8-107">成员</span><span class="sxs-lookup"><span data-stu-id="0f5c8-107">Members</span></span>                        | <span data-ttu-id="0f5c8-108">描述</span><span class="sxs-lookup"><span data-stu-id="0f5c8-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="0f5c8-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="0f5c8-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="0f5c8-110">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="0f5c8-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="0f5c8-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="0f5c8-112">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="0f5c8-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="0f5c8-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="0f5c8-114">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-114">Gets the new window.</span></span>
[<span data-ttu-id="0f5c8-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0f5c8-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="0f5c8-116">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="0f5c8-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="0f5c8-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="0f5c8-118">获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="0f5c8-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="0f5c8-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="0f5c8-120">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-120">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="0f5c8-121">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="0f5c8-121">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="0f5c8-122">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-122">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="0f5c8-123">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="0f5c8-124">成员</span><span class="sxs-lookup"><span data-stu-id="0f5c8-124">Members</span></span>

#### <span data-ttu-id="0f5c8-125">get_Handled</span><span class="sxs-lookup"><span data-stu-id="0f5c8-125">get_Handled</span></span> 

<span data-ttu-id="0f5c8-126">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-126">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="0f5c8-127">公共 HRESULT [get_Handled](#get_handled)（BOOL \* 已处理）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-127">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="0f5c8-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="0f5c8-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="0f5c8-129">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-129">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="0f5c8-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="0f5c8-131">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="0f5c8-131">get_NewWindow</span></span> 

<span data-ttu-id="0f5c8-132">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-132">Gets the new window.</span></span>

> <span data-ttu-id="0f5c8-133">公共 HRESULT [get_NewWindow](#get_newwindow)（[ICoreWebView2](icorewebview2.md) \* \* NewWindow）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-133">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="0f5c8-134">get_Uri</span><span class="sxs-lookup"><span data-stu-id="0f5c8-134">get_Uri</span></span> 

<span data-ttu-id="0f5c8-135">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-135">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="0f5c8-136">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-136">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="0f5c8-137">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="0f5c8-137">GetDeferral</span></span> 

<span data-ttu-id="0f5c8-138">获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-138">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="0f5c8-139">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-139">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="0f5c8-140">你可以使用[ICoreWebView2Deferral](icorewebview2deferral.md)对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-140">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="0f5c8-141">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-141">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="0f5c8-142">put_Handled</span><span class="sxs-lookup"><span data-stu-id="0f5c8-142">put_Handled</span></span> 

<span data-ttu-id="0f5c8-143">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-143">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="0f5c8-144">公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-144">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="0f5c8-145">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-145">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="0f5c8-146">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-146">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="0f5c8-147">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-147">Default is false.</span></span>

#### <span data-ttu-id="0f5c8-148">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="0f5c8-148">put_NewWindow</span></span> 

<span data-ttu-id="0f5c8-149">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-149">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="0f5c8-150">公共 HRESULT [put_NewWindow](#put_newwindow)（[ICoreWebView2](icorewebview2.md) \* NewWindow）</span><span class="sxs-lookup"><span data-stu-id="0f5c8-150">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="0f5c8-151">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-151">The target webview should not be navigated.</span></span> <span data-ttu-id="0f5c8-152">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="0f5c8-152">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

