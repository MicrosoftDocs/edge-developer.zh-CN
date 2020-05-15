---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 2ea3500c5e230b543f75241c47c58163276942da
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653039"
---
# <span data-ttu-id="1ee17-104">interface ICoreWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="1ee17-104">interface ICoreWebView2NewWindowRequestedEventArgs</span></span> 

> [!NOTE]
> <span data-ttu-id="1ee17-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="1ee17-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="1ee17-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="1ee17-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="1ee17-107">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="1ee17-107">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="1ee17-108">摘要</span><span class="sxs-lookup"><span data-stu-id="1ee17-108">Summary</span></span>

 <span data-ttu-id="1ee17-109">成员</span><span class="sxs-lookup"><span data-stu-id="1ee17-109">Members</span></span>                        | <span data-ttu-id="1ee17-110">描述</span><span class="sxs-lookup"><span data-stu-id="1ee17-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="1ee17-111">get_Uri</span><span class="sxs-lookup"><span data-stu-id="1ee17-111">get_Uri</span></span>](#get_uri) | <span data-ttu-id="1ee17-112">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="1ee17-112">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="1ee17-113">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="1ee17-113">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="1ee17-114">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="1ee17-114">Sets a WebView as a result of the NewWindowRequest.</span></span>
[<span data-ttu-id="1ee17-115">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="1ee17-115">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="1ee17-116">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="1ee17-116">Gets the new window.</span></span>
[<span data-ttu-id="1ee17-117">put_Handled</span><span class="sxs-lookup"><span data-stu-id="1ee17-117">put_Handled</span></span>](#put_handled) | <span data-ttu-id="1ee17-118">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="1ee17-118">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="1ee17-119">get_Handled</span><span class="sxs-lookup"><span data-stu-id="1ee17-119">get_Handled</span></span>](#get_handled) | <span data-ttu-id="1ee17-120">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="1ee17-120">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="1ee17-121">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="1ee17-121">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="1ee17-122">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="1ee17-122">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="1ee17-123">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="1ee17-123">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="1ee17-124">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="1ee17-124">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

<span data-ttu-id="1ee17-125">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="1ee17-125">The event is fired when content inside webview requested to a open a new window (through window.open() etc.)</span></span>

## <span data-ttu-id="1ee17-126">成员</span><span class="sxs-lookup"><span data-stu-id="1ee17-126">Members</span></span>

#### <span data-ttu-id="1ee17-127">get_Uri</span><span class="sxs-lookup"><span data-stu-id="1ee17-127">get_Uri</span></span> 

<span data-ttu-id="1ee17-128">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="1ee17-128">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="1ee17-129">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="1ee17-129">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="1ee17-130">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="1ee17-130">put_NewWindow</span></span> 

<span data-ttu-id="1ee17-131">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="1ee17-131">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="1ee17-132">公共 HRESULT [put_NewWindow](#put_newwindow)（[ICoreWebView2](ICoreWebView2.md) \* NewWindow）</span><span class="sxs-lookup"><span data-stu-id="1ee17-132">public HRESULT [put_NewWindow](#put_newwindow)([ICoreWebView2](ICoreWebView2.md) \* newWindow)</span></span>

<span data-ttu-id="1ee17-133">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="1ee17-133">The target webview should not be navigated.</span></span> <span data-ttu-id="1ee17-134">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="1ee17-134">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="1ee17-135">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="1ee17-135">get_NewWindow</span></span> 

<span data-ttu-id="1ee17-136">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="1ee17-136">Gets the new window.</span></span>

> <span data-ttu-id="1ee17-137">公共 HRESULT [get_NewWindow](#get_newwindow)（[ICoreWebView2](ICoreWebView2.md) \* \* NewWindow）</span><span class="sxs-lookup"><span data-stu-id="1ee17-137">public HRESULT [get_NewWindow](#get_newwindow)([ICoreWebView2](ICoreWebView2.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="1ee17-138">put_Handled</span><span class="sxs-lookup"><span data-stu-id="1ee17-138">put_Handled</span></span> 

<span data-ttu-id="1ee17-139">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="1ee17-139">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="1ee17-140">公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）</span><span class="sxs-lookup"><span data-stu-id="1ee17-140">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="1ee17-141">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="1ee17-141">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="1ee17-142">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="1ee17-142">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="1ee17-143">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="1ee17-143">Default is false.</span></span>

#### <span data-ttu-id="1ee17-144">get_Handled</span><span class="sxs-lookup"><span data-stu-id="1ee17-144">get_Handled</span></span> 

<span data-ttu-id="1ee17-145">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="1ee17-145">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="1ee17-146">公共 HRESULT [get_Handled](#get_handled)（BOOL \* 已处理）</span><span class="sxs-lookup"><span data-stu-id="1ee17-146">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="1ee17-147">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="1ee17-147">get_IsUserInitiated</span></span> 

<span data-ttu-id="1ee17-148">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="1ee17-148">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="1ee17-149">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="1ee17-149">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="1ee17-150">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="1ee17-150">GetDeferral</span></span> 

<span data-ttu-id="1ee17-151">获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="1ee17-151">Obtain an [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="1ee17-152">公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="1ee17-152">public HRESULT [GetDeferral](#getdeferral)([ICoreWebView2Deferral](ICoreWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="1ee17-153">你可以使用[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="1ee17-153">You can use the [ICoreWebView2Deferral](ICoreWebView2Deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="1ee17-154">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="1ee17-154">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

