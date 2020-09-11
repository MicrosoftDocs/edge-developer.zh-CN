---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NewWindowRequestedEventArgs
ms.openlocfilehash: d1cf39fe71c4b00f10a14da8a65428eb24daa71f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011740"
---
# <span data-ttu-id="97316-104">interface ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="97316-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="97316-105">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="97316-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="97316-106">摘要</span><span class="sxs-lookup"><span data-stu-id="97316-106">Summary</span></span>

 <span data-ttu-id="97316-107">成员</span><span class="sxs-lookup"><span data-stu-id="97316-107">Members</span></span>                        | <span data-ttu-id="97316-108">描述</span><span class="sxs-lookup"><span data-stu-id="97316-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="97316-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="97316-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="97316-110">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="97316-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="97316-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="97316-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="97316-112">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="97316-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="97316-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="97316-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="97316-114">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="97316-114">Gets the new window.</span></span>
[<span data-ttu-id="97316-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="97316-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="97316-116">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="97316-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="97316-117">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="97316-117">get_WindowFeatures</span></span>](#get_windowfeatures) | <span data-ttu-id="97316-118">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="97316-118">Window features specified by the window.open call.</span></span>
[<span data-ttu-id="97316-119">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="97316-119">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="97316-120">获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="97316-120">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="97316-121">put_Handled</span><span class="sxs-lookup"><span data-stu-id="97316-121">put_Handled</span></span>](#put_handled) | <span data-ttu-id="97316-122">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="97316-122">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="97316-123">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="97316-123">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="97316-124">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="97316-124">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="97316-125">当 web 浏览中请求打开一个新窗口 (通过 window 打开一个新窗口时，将引发此事件。 ) 打开 ( # A2 的内容。</span><span class="sxs-lookup"><span data-stu-id="97316-125">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="97316-126">成员</span><span class="sxs-lookup"><span data-stu-id="97316-126">Members</span></span>

#### <span data-ttu-id="97316-127">get_Handled</span><span class="sxs-lookup"><span data-stu-id="97316-127">get_Handled</span></span> 

<span data-ttu-id="97316-128">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="97316-128">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="97316-129"> (BOOL\ * 的公共 HRESULT [get_Handled](#get_handled) 已处理) </span><span class="sxs-lookup"><span data-stu-id="97316-129">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="97316-130">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="97316-130">get_IsUserInitiated</span></span> 

<span data-ttu-id="97316-131">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="97316-131">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="97316-132">公共 HRESULT [get_IsUserInitiated](#get_isuserinitiated) (BOOL \* IsUserInitiated) </span><span class="sxs-lookup"><span data-stu-id="97316-132">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="97316-133">对 Web 视图禁用了边缘弹出窗口阻止程序，以便应用可以使用此标志来阻止非用户启动的弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="97316-133">The Edge popup blocker is disabled for WebView so the app can use this flag to block non-user initiated popups.</span></span>

#### <span data-ttu-id="97316-134">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="97316-134">get_NewWindow</span></span> 

<span data-ttu-id="97316-135">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="97316-135">Gets the new window.</span></span>

> <span data-ttu-id="97316-136">公共 HRESULT [get_NewWindow](#get_newwindow) ([ICoreWebView2](icorewebview2.md) \* \* NewWindow) </span><span class="sxs-lookup"><span data-stu-id="97316-136">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="97316-137">get_Uri</span><span class="sxs-lookup"><span data-stu-id="97316-137">get_Uri</span></span> 

<span data-ttu-id="97316-138">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="97316-138">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="97316-139">公共 HRESULT [get_Uri](#get_uri) (LPWSTR \* Uri) </span><span class="sxs-lookup"><span data-stu-id="97316-139">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="97316-140">get_WindowFeatures</span><span class="sxs-lookup"><span data-stu-id="97316-140">get_WindowFeatures</span></span> 

<span data-ttu-id="97316-141">窗口指定的窗口功能。打开通话。</span><span class="sxs-lookup"><span data-stu-id="97316-141">Window features specified by the window.open call.</span></span>

> <span data-ttu-id="97316-142">公共 HRESULT [get_WindowFeatures](#get_windowfeatures) ([ICoreWebView2WindowFeatures](icorewebview2windowfeatures.md) \* \* WindowFeatures) </span><span class="sxs-lookup"><span data-stu-id="97316-142">public HRESULT [get_WindowFeatures](#get_windowfeatures)([ICoreWebView2WindowFeatures](icorewebview2windowfeatures.md) \*\* windowFeatures)</span></span>

<span data-ttu-id="97316-143">可将这些功能考虑到新的 web 视图窗口的位置和大小调整。</span><span class="sxs-lookup"><span data-stu-id="97316-143">These features can be considered for positioning and sizing of new webview windows.</span></span>

#### <span data-ttu-id="97316-144">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="97316-144">GetDeferral</span></span> 

<span data-ttu-id="97316-145">获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="97316-145">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="97316-146">公共 HRESULT [GetDeferral](#getdeferral) ([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期) </span><span class="sxs-lookup"><span data-stu-id="97316-146">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="97316-147">你可以使用 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="97316-147">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="97316-148">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="97316-148">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="97316-149">put_Handled</span><span class="sxs-lookup"><span data-stu-id="97316-149">put_Handled</span></span> 

<span data-ttu-id="97316-150">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="97316-150">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="97316-151"> (以 BOOL 方式处理的公共 HRESULT [put_Handled](#put_handled)) </span><span class="sxs-lookup"><span data-stu-id="97316-151">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="97316-152">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="97316-152">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="97316-153">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="97316-153">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="97316-154">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="97316-154">Default is false.</span></span>

#### <span data-ttu-id="97316-155">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="97316-155">put_NewWindow</span></span> 

<span data-ttu-id="97316-156">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="97316-156">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="97316-157">公共 HRESULT [put_NewWindow](#put_newwindow) ([ICoreWebView2](icorewebview2.md) \* NewWindow) </span><span class="sxs-lookup"><span data-stu-id="97316-157">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="97316-158">不应导航目标 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="97316-158">The target WebView should not be navigated.</span></span> <span data-ttu-id="97316-159">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="97316-159">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

