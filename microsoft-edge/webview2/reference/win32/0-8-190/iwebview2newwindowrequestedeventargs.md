---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NewWindowRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: cbcac385546c44e776ed48b8ae4d3ab754b614e0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885891"
---
# <span data-ttu-id="718c4-104">0.8.355-接口 IWebView2NewWindowRequestedEventArgs</span><span class="sxs-lookup"><span data-stu-id="718c4-104">0.8.355 - interface IWebView2NewWindowRequestedEventArgs</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NewWindowRequestedEventArgs
  : public IUnknown
```

<span data-ttu-id="718c4-105">Webview.newwindowrequested 事件的事件参数。</span><span class="sxs-lookup"><span data-stu-id="718c4-105">Event args for the NewWindowRequested event.</span></span>

## <span data-ttu-id="718c4-106">摘要</span><span class="sxs-lookup"><span data-stu-id="718c4-106">Summary</span></span>

 <span data-ttu-id="718c4-107">成员</span><span class="sxs-lookup"><span data-stu-id="718c4-107">Members</span></span>                        | <span data-ttu-id="718c4-108">描述</span><span class="sxs-lookup"><span data-stu-id="718c4-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="718c4-109">get_Uri</span><span class="sxs-lookup"><span data-stu-id="718c4-109">get_Uri</span></span>](#get_uri) | <span data-ttu-id="718c4-110">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="718c4-110">The target uri of the NewWindowRequest.</span></span>
[<span data-ttu-id="718c4-111">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="718c4-111">put_NewWindow</span></span>](#put_newwindow) | <span data-ttu-id="718c4-112">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="718c4-112">Sets a WebView as a result of the NewWindowRequest.</span></span>
[<span data-ttu-id="718c4-113">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="718c4-113">get_NewWindow</span></span>](#get_newwindow) | <span data-ttu-id="718c4-114">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="718c4-114">Gets the new window.</span></span>
[<span data-ttu-id="718c4-115">put_Handled</span><span class="sxs-lookup"><span data-stu-id="718c4-115">put_Handled</span></span>](#put_handled) | <span data-ttu-id="718c4-116">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="718c4-116">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="718c4-117">get_Handled</span><span class="sxs-lookup"><span data-stu-id="718c4-117">get_Handled</span></span>](#get_handled) | <span data-ttu-id="718c4-118">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="718c4-118">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>
[<span data-ttu-id="718c4-119">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="718c4-119">get_IsUserInitiated</span></span>](#get_isuserinitiated) | <span data-ttu-id="718c4-120">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="718c4-120">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>
[<span data-ttu-id="718c4-121">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="718c4-121">GetDeferral</span></span>](#getdeferral) | <span data-ttu-id="718c4-122">获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="718c4-122">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

<span data-ttu-id="718c4-123">如果 web 视图中的内容请求打开一个新窗口（通过 "打开" （）等），将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="718c4-123">The event is fired when content inside webview requested to a open a new window (through window.open() etc.)</span></span>

## <span data-ttu-id="718c4-124">成员</span><span class="sxs-lookup"><span data-stu-id="718c4-124">Members</span></span>

#### <span data-ttu-id="718c4-125">get_Uri</span><span class="sxs-lookup"><span data-stu-id="718c4-125">get_Uri</span></span> 

<span data-ttu-id="718c4-126">NewWindowRequest 的目标 uri。</span><span class="sxs-lookup"><span data-stu-id="718c4-126">The target uri of the NewWindowRequest.</span></span>

> <span data-ttu-id="718c4-127">公共 HRESULT [get_Uri](#get_uri)（LPWSTR \* Uri）</span><span class="sxs-lookup"><span data-stu-id="718c4-127">public HRESULT [get_Uri](#get_uri)(LPWSTR \* uri)</span></span>

#### <span data-ttu-id="718c4-128">put_NewWindow</span><span class="sxs-lookup"><span data-stu-id="718c4-128">put_NewWindow</span></span> 

<span data-ttu-id="718c4-129">将 Web 视图设置为 NewWindowRequest 的结果。</span><span class="sxs-lookup"><span data-stu-id="718c4-129">Sets a WebView as a result of the NewWindowRequest.</span></span>

> <span data-ttu-id="718c4-130">公共 HRESULT [put_NewWindow](#put_newwindow)（[IWebView2WebView](IWebView2WebView.md) \* NewWindow）</span><span class="sxs-lookup"><span data-stu-id="718c4-130">public HRESULT [put_NewWindow](#put_newwindow)([IWebView2WebView](IWebView2WebView.md) \* newWindow)</span></span>

<span data-ttu-id="718c4-131">不应导航目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="718c4-131">The target webview should not be navigated.</span></span> <span data-ttu-id="718c4-132">如果设置了 NewWindow，其顶级窗口将返回为打开的 WindowProxy。</span><span class="sxs-lookup"><span data-stu-id="718c4-132">If the NewWindow is set, its top level window will return as the opened WindowProxy.</span></span>

#### <span data-ttu-id="718c4-133">get_NewWindow</span><span class="sxs-lookup"><span data-stu-id="718c4-133">get_NewWindow</span></span> 

<span data-ttu-id="718c4-134">获取新窗口。</span><span class="sxs-lookup"><span data-stu-id="718c4-134">Gets the new window.</span></span>

> <span data-ttu-id="718c4-135">公共 HRESULT [get_NewWindow](#get_newwindow)（[IWebView2WebView](IWebView2WebView.md) \* \* NewWindow）</span><span class="sxs-lookup"><span data-stu-id="718c4-135">public HRESULT [get_NewWindow](#get_newwindow)([IWebView2WebView](IWebView2WebView.md) \*\* newWindow)</span></span>

#### <span data-ttu-id="718c4-136">put_Handled</span><span class="sxs-lookup"><span data-stu-id="718c4-136">put_Handled</span></span> 

<span data-ttu-id="718c4-137">设置 NewWindowRequestedEvent 是否由主机处理。</span><span class="sxs-lookup"><span data-stu-id="718c4-137">Sets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="718c4-138">公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）</span><span class="sxs-lookup"><span data-stu-id="718c4-138">public HRESULT [put_Handled](#put_handled)(BOOL handled)</span></span>

<span data-ttu-id="718c4-139">如果此参数为 false 且未设置 NewWindow，则 Web 视图将打开一个弹出窗口，并且该窗口将以打开的 WindowProxy 的形式返回。</span><span class="sxs-lookup"><span data-stu-id="718c4-139">If this is false and no NewWindow is set, the WebView will open a popup window and it will be returned as opened WindowProxy.</span></span> <span data-ttu-id="718c4-140">如果设置为 true 且没有为窗口设置 NewWindow，则打开的 WindowProxy 将针对虚拟窗口对象，并且不会加载任何窗口。</span><span class="sxs-lookup"><span data-stu-id="718c4-140">If set to true and no NewWindow is set for a window.open call, the opened WindowProxy will be for an dummy window object and no window will load.</span></span> <span data-ttu-id="718c4-141">默认值为 false。</span><span class="sxs-lookup"><span data-stu-id="718c4-141">Default is false.</span></span>

#### <span data-ttu-id="718c4-142">get_Handled</span><span class="sxs-lookup"><span data-stu-id="718c4-142">get_Handled</span></span> 

<span data-ttu-id="718c4-143">获取 NewWindowRequestedEvent 是否由 host 处理。</span><span class="sxs-lookup"><span data-stu-id="718c4-143">Gets whether the NewWindowRequestedEvent is handled by host.</span></span>

> <span data-ttu-id="718c4-144">公共 HRESULT [get_Handled](#get_handled)（BOOL \* 已处理）</span><span class="sxs-lookup"><span data-stu-id="718c4-144">public HRESULT [get_Handled](#get_handled)(BOOL \* handled)</span></span>

#### <span data-ttu-id="718c4-145">get_IsUserInitiated</span><span class="sxs-lookup"><span data-stu-id="718c4-145">get_IsUserInitiated</span></span> 

<span data-ttu-id="718c4-146">通过用户笔势（如单击带有目标的定位点标记）启动新的窗口请求时，IsUserInitiated 为 true。</span><span class="sxs-lookup"><span data-stu-id="718c4-146">IsUserInitiated is true when the new window request was initiated through a user gesture such as clicking an anchor tag with target.</span></span>

> <span data-ttu-id="718c4-147">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL \* IsUserInitiated）</span><span class="sxs-lookup"><span data-stu-id="718c4-147">public HRESULT [get_IsUserInitiated](#get_isuserinitiated)(BOOL \* isUserInitiated)</span></span>

#### <span data-ttu-id="718c4-148">GetDeferral</span><span class="sxs-lookup"><span data-stu-id="718c4-148">GetDeferral</span></span> 

<span data-ttu-id="718c4-149">获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。</span><span class="sxs-lookup"><span data-stu-id="718c4-149">Obtain an [IWebView2Deferral](IWebView2Deferral.md) object and put the event into a deferred state.</span></span>

> <span data-ttu-id="718c4-150">公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) \* \* 延迟）</span><span class="sxs-lookup"><span data-stu-id="718c4-150">public HRESULT [GetDeferral](#getdeferral)([IWebView2Deferral](IWebView2Deferral.md) \*\* deferral)</span></span>

<span data-ttu-id="718c4-151">你可以使用[IWebView2Deferral](IWebView2Deferral.md)对象在以后的时间完成窗口打开请求。</span><span class="sxs-lookup"><span data-stu-id="718c4-151">You can use the [IWebView2Deferral](IWebView2Deferral.md) object to complete the window open request at a later time.</span></span> <span data-ttu-id="718c4-152">当此事件延迟时，opener 窗口将返回到 unnavigated 窗口的 WindowProxy，该窗口将在延迟完成时进行导航。</span><span class="sxs-lookup"><span data-stu-id="718c4-152">While this event is deferred the opener window will be returned a WindowProxy to an unnavigated window, which will navigate when the deferral is complete.</span></span>

