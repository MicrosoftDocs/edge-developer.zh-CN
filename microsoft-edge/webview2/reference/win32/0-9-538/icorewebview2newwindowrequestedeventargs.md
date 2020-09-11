---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NewWindowRequestedEventArgs
ms.openlocfilehash: 5486aa66e39e220e819bb00211a79bd449a25bfe
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010059"
---
# <span data-ttu-id="6e2e0-104">0.9.579-接口 ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="6e2e0-104">0.9.579 - interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="6e2e0-105">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="6e2e0-106">摘要</span><span class="sxs-lookup"><span data-stu-id="6e2e0-106">Summary</span></span>

 <span data-ttu-id="6e2e0-107">成员</span><span class="sxs-lookup"><span data-stu-id="6e2e0-107">Members</span></span>                        | <span data-ttu-id="6e2e0-108">描述</span><span class="sxs-lookup"><span data-stu-id="6e2e0-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6e2e0-109">get_Handled</span><span class="sxs-lookup"><span data-stu-id="6e2e0-109">get_Handled</span></span>](#get_handled) | <span data-ttu-id="6e2e0-110">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-110">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="6e2e0-111">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6e2e0-111">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="6e2e0-112">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-112">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="6e2e0-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="6e2e0-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="6e2e0-114">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-114">Gets the new window.</span></span>
[<span data-ttu-id="6e2e0-115">get_Uri</span><span class="sxs-lookup"><span data-stu-id="6e2e0-115">get_Uri</span></span>](#get_uri) | <span data-ttu-id="6e2e0-116">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-116">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="6e2e0-117">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6e2e0-117">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="6e2e0-118">获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-118">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>
[<span data-ttu-id="6e2e0-119">put_Handled</span><span class="sxs-lookup"><span data-stu-id="6e2e0-119">put_Handled</span></span>](#put_handled) | <span data-ttu-id="6e2e0-120">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-120">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="6e2e0-121">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="6e2e0-121">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="6e2e0-122">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-122">Sets a WebView as a result of the NewWindowRequest.</span></span>

<span data-ttu-id="6e2e0-123">当 web 浏览中请求打开一个新窗口 (通过 window 打开一个新窗口时，将引发此事件。 ) 打开 ( # A2 的内容。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-123">The event is fired when content inside webview requested to a open a new window (through window.open() and so on.)</span></span>

## <span data-ttu-id="6e2e0-124">成员</span><span class="sxs-lookup"><span data-stu-id="6e2e0-124">Members</span></span>

#### <span data-ttu-id="6e2e0-125">get_Handled</span><span class="sxs-lookup"><span data-stu-id="6e2e0-125">get_Handled</span></span> 

<span data-ttu-id="6e2e0-126">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-126">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="6e2e0-127"> (BOOL\ * 的公共 HRESULT [get_Handled](#get_handled) 已处理) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-127">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="6e2e0-128">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="6e2e0-128">get_IsUserInitiated</span></span> 

<span data-ttu-id="6e2e0-129">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-129">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="6e2e0-130">公共 HRESULT [get_IsUserInitiated](#get_isuserinitiated) (BOOL \* IsUserInitiated) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-130">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

<span data-ttu-id="6e2e0-131">对 Web 视图禁用了边缘弹出窗口阻止程序，以便应用可以使用此标志来阻止非用户启动的弹出窗口。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-131">The Edge popup blocker is disabled for WebView so the app can use this flag to block non-user initiated popups.</span></span>

#### <span data-ttu-id="6e2e0-132">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="6e2e0-132">get_NewWindow</span></span> 

<span data-ttu-id="6e2e0-133">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-133">Gets the new window.</span></span>

> <span data-ttu-id="6e2e0-134">公共 HRESULT [get_NewWindow](#get_newwindow) ([ICoreWebView2](icorewebview2.md) \* \* NewWindow) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-134">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](icorewebview2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="6e2e0-135">get_Uri</span><span class="sxs-lookup"><span data-stu-id="6e2e0-135">get_Uri</span></span> 

<span data-ttu-id="6e2e0-136">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-136">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="6e2e0-137">公共 HRESULT [get_Uri](#get_uri) (LPWSTR \* Uri) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-137">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="6e2e0-138">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="6e2e0-138">GetDeferral</span></span> 

<span data-ttu-id="6e2e0-139">获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-139">Obtain an [ICoreWebView2Deferral](icorewebview2deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="6e2e0-140">公共 HRESULT [GetDeferral](#getdeferral) ([ICoreWebView2Deferral](icorewebview2deferral.md) \* \* 延期) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-140">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](icorewebview2deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="6e2e0-141">你可以使用 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-141">You can use the [ICoreWebView2Deferral](icorewebview2deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="6e2e0-142">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-142">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

#### <span data-ttu-id="6e2e0-143">put_Handled</span><span class="sxs-lookup"><span data-stu-id="6e2e0-143">put_Handled</span></span> 

<span data-ttu-id="6e2e0-144">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-144">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="6e2e0-145"> (以 BOOL 方式处理的公共 HRESULT [put_Handled](#put_handled)) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-145">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="6e2e0-146">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-146">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="6e2e0-147">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-147">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="6e2e0-148">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-148">Default is false.</span></span>

#### <span data-ttu-id="6e2e0-149">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="6e2e0-149">put_NewWindow</span></span> 

<span data-ttu-id="6e2e0-150">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-150">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="6e2e0-151">公共 HRESULT [put_NewWindow](#put_newwindow) ([ICoreWebView2](icorewebview2.md) \* NewWindow) </span><span class="sxs-lookup"><span data-stu-id="6e2e0-151">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](icorewebview2.md) \* newWindow)</span></span>

<span data-ttu-id="6e2e0-152">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-152">The target webview should not be navigated.</span></span> <span data-ttu-id="6e2e0-153">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="6e2e0-153">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

