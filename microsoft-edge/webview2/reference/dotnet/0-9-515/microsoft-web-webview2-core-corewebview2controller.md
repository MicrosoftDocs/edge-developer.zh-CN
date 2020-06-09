---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 2b9ad09fd347a6719523213e5ebc13d9000d536b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697705"
---
# <span data-ttu-id="f8154-104">CoreWebView2Controller 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="f8154-104">Microsoft.Web.WebView2.Core.CoreWebView2Controller class</span></span> 

> [!NOTE]
> <span data-ttu-id="f8154-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="f8154-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="f8154-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="f8154-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="f8154-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="f8154-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="f8154-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="f8154-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="f8154-109">此类是 CoreWebView2 对象的所有者，并且支持调整大小、显示和隐藏、重点介绍以及与窗口化和合成相关的其他功能。</span><span class="sxs-lookup"><span data-stu-id="f8154-109">This class is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="f8154-110">摘要</span><span class="sxs-lookup"><span data-stu-id="f8154-110">Summary</span></span>

 <span data-ttu-id="f8154-111">成员</span><span class="sxs-lookup"><span data-stu-id="f8154-111">Members</span></span>                        | <span data-ttu-id="f8154-112">描述</span><span class="sxs-lookup"><span data-stu-id="f8154-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="f8154-113">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="f8154-113">AcceleratorKeyPressed</span></span>](#acceleratorkeypressed) | <span data-ttu-id="f8154-114">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="f8154-114">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>
[<span data-ttu-id="f8154-115">界</span><span class="sxs-lookup"><span data-stu-id="f8154-115">Bounds</span></span>](#bounds) | <span data-ttu-id="f8154-116">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="f8154-116">The webview bounds.</span></span>
[<span data-ttu-id="f8154-117">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="f8154-117">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="f8154-118">获取与此 CoreWebView2Controller 关联的 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="f8154-118">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>
[<span data-ttu-id="f8154-119">GotFocus</span><span class="sxs-lookup"><span data-stu-id="f8154-119">GotFocus</span></span>](#gotfocus) | <span data-ttu-id="f8154-120">当 Web 视图获得焦点时，将引发 GotFocus。</span><span class="sxs-lookup"><span data-stu-id="f8154-120">GotFocus fires when WebView got focus.</span></span>
[<span data-ttu-id="f8154-121">IsVisible</span><span class="sxs-lookup"><span data-stu-id="f8154-121">IsVisible</span></span>](#isvisible) | <span data-ttu-id="f8154-122">IsVisible 属性确定是显示还是隐藏 web 视图。</span><span class="sxs-lookup"><span data-stu-id="f8154-122">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="f8154-123">LostFocus</span><span class="sxs-lookup"><span data-stu-id="f8154-123">LostFocus</span></span>](#lostfocus) | <span data-ttu-id="f8154-124">当 Web 视图失去焦点时，将激发 LostFocus。</span><span class="sxs-lookup"><span data-stu-id="f8154-124">LostFocus fires when WebView lost focus.</span></span>
[<span data-ttu-id="f8154-125">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="f8154-125">MoveFocusRequested</span></span>](#movefocusrequested) | <span data-ttu-id="f8154-126">当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。</span><span class="sxs-lookup"><span data-stu-id="f8154-126">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>
[<span data-ttu-id="f8154-127">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="f8154-127">ParentWindow</span></span>](#parentwindow) | <span data-ttu-id="f8154-128">由此 Web 视图用于呈现内容的应用提供的父窗口。</span><span class="sxs-lookup"><span data-stu-id="f8154-128">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="f8154-129">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="f8154-129">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="f8154-130">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="f8154-130">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="f8154-131">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="f8154-131">ZoomFactorChanged</span></span>](#zoomfactorchanged) | <span data-ttu-id="f8154-132">当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-132">The event fires when the ZoomFactor property of the WebView changes.</span></span>
[<span data-ttu-id="f8154-133">关闭</span><span class="sxs-lookup"><span data-stu-id="f8154-133">Close</span></span>](#close) | <span data-ttu-id="f8154-134">关闭 Web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="f8154-134">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="f8154-135">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="f8154-135">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="f8154-136">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="f8154-136">Move focus into WebView.</span></span>
[<span data-ttu-id="f8154-137">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="f8154-137">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="f8154-138">这是与界限分开的通知，告诉 Web 视图其父（或任何上级） HWND 已移动。</span><span class="sxs-lookup"><span data-stu-id="f8154-138">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="f8154-139">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="f8154-139">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="f8154-140">同时更新边界和 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="f8154-140">Update Bounds and ZoomFactor properties at the same time.</span></span>

<span data-ttu-id="f8154-141">CoreWebView2Controller 拥有 CoreWebView2，如果对 CoreWebView2Controller 的所有引用消失，则将关闭 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="f8154-141">The CoreWebView2Controller owns the CoreWebView2, and if all references to the CoreWebView2Controller go away, the WebView will be closed.</span></span>

## <span data-ttu-id="f8154-142">成员</span><span class="sxs-lookup"><span data-stu-id="f8154-142">Members</span></span>

#### <span data-ttu-id="f8154-143">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="f8154-143">AcceleratorKeyPressed</span></span> 

<span data-ttu-id="f8154-144">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="f8154-144">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>

> <span data-ttu-id="f8154-145">公共事件 EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)  >  [AcceleratorKeyPressed](#acceleratorkeypressed)</span><span class="sxs-lookup"><span data-stu-id="f8154-145">public event EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md) > [AcceleratorKeyPressed](#acceleratorkeypressed)</span></span>

<span data-ttu-id="f8154-146">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="f8154-146">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="f8154-147">如果某个键出现以下情况之一，则将其视为一个加速器：</span><span class="sxs-lookup"><span data-stu-id="f8154-147">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="f8154-148">按 Ctrl 或 Alt 当前正在保持，或者</span><span class="sxs-lookup"><span data-stu-id="f8154-148">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="f8154-149">按下的键不会映射到字符。</span><span class="sxs-lookup"><span data-stu-id="f8154-149">the pressed key does not map to a character.</span></span> <span data-ttu-id="f8154-150">一些特定的键永远不会被视为加速器，如 Shift。</span><span class="sxs-lookup"><span data-stu-id="f8154-150">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="f8154-151">转义键始终被视为加速键。</span><span class="sxs-lookup"><span data-stu-id="f8154-151">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="f8154-152">通过按住键导致的 Autorepeated 键事件也会引发此事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-152">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="f8154-153">你可以通过检查事件参数 "KeyEventLParam" 或 "PhysicalKeyStatus" 来筛选这些问题。</span><span class="sxs-lookup"><span data-stu-id="f8154-153">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="f8154-154">在窗口模式下，此事件处理程序是同步调用的。</span><span class="sxs-lookup"><span data-stu-id="f8154-154">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="f8154-155">在事件参数或事件处理程序返回之前调用句柄（）之前，浏览器进程将被阻止，并且传出进程间 COM 调用将失败，并显示 RPC_E_CANTCALLOUT_ININPUTSYNCCALL。</span><span class="sxs-lookup"><span data-stu-id="f8154-155">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="f8154-156">但是，所有 CoreWebView2 API 方法都有效。</span><span class="sxs-lookup"><span data-stu-id="f8154-156">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="f8154-157">在无窗口模式下，异步调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="f8154-157">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="f8154-158">在调用事件处理程序返回或句柄（）时，将不会访问浏览器，但浏览器进程本身将不会被阻止，并且传出 COM 调用将正常工作。</span><span class="sxs-lookup"><span data-stu-id="f8154-158">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="f8154-159">建议你先调用句柄（TRUE），然后才能知道你希望处理加速键。</span><span class="sxs-lookup"><span data-stu-id="f8154-159">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

#### <span data-ttu-id="f8154-160">界</span><span class="sxs-lookup"><span data-stu-id="f8154-160">Bounds</span></span> 

<span data-ttu-id="f8154-161">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="f8154-161">The webview bounds.</span></span>

> <span data-ttu-id="f8154-162">公共矩形[边界](#bounds)</span><span class="sxs-lookup"><span data-stu-id="f8154-162">public Rect [Bounds](#bounds)</span></span>

<span data-ttu-id="f8154-163">界限相对于父 HWND。</span><span class="sxs-lookup"><span data-stu-id="f8154-163">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="f8154-164">应用有两种方法可以放置 Web 视图：</span><span class="sxs-lookup"><span data-stu-id="f8154-164">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="f8154-165">创建作为 Web 视图父 HWND 的子 HWND。</span><span class="sxs-lookup"><span data-stu-id="f8154-165">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="f8154-166">将此窗口放置在 Web 视图应位于的位置。</span><span class="sxs-lookup"><span data-stu-id="f8154-166">Position this window where the WebView should be.</span></span> <span data-ttu-id="f8154-167">在这种情况下，对 Web 视图的 Bound's 左上角（偏移）使用（0，0）。</span><span class="sxs-lookup"><span data-stu-id="f8154-167">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="f8154-168">将应用最顶部的窗口用作 Web 视图父 HWND。</span><span class="sxs-lookup"><span data-stu-id="f8154-168">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="f8154-169">设置 Web 视图的 Bound's 左上角，以便 Web 视图正确地放置在应用中。</span><span class="sxs-lookup"><span data-stu-id="f8154-169">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="f8154-170">绑定的值位于主机的坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="f8154-170">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="f8154-171">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="f8154-171">CoreWebView2</span></span> 

<span data-ttu-id="f8154-172">获取与此 CoreWebView2Controller 关联的 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="f8154-172">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>

> <span data-ttu-id="f8154-173">公共[CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="f8154-173">public [CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span></span>

#### <span data-ttu-id="f8154-174">GotFocus</span><span class="sxs-lookup"><span data-stu-id="f8154-174">GotFocus</span></span> 

<span data-ttu-id="f8154-175">当 Web 视图获得焦点时，将引发 GotFocus。</span><span class="sxs-lookup"><span data-stu-id="f8154-175">GotFocus fires when WebView got focus.</span></span>

> <span data-ttu-id="f8154-176">公共事件 EventHandler< 对象 > [GotFocus](#gotfocus)</span><span class="sxs-lookup"><span data-stu-id="f8154-176">public event EventHandler< object > [GotFocus](#gotfocus)</span></span>

#### <span data-ttu-id="f8154-177">IsVisible</span><span class="sxs-lookup"><span data-stu-id="f8154-177">IsVisible</span></span> 

<span data-ttu-id="f8154-178">IsVisible 属性确定是显示还是隐藏 web 视图。</span><span class="sxs-lookup"><span data-stu-id="f8154-178">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="f8154-179">公共 bool [IsVisible](#isvisible)</span><span class="sxs-lookup"><span data-stu-id="f8154-179">public bool [IsVisible](#isvisible)</span></span>

<span data-ttu-id="f8154-180">如果 IsVisible 设置为 false，则 web 视图将是透明的，不会呈现。</span><span class="sxs-lookup"><span data-stu-id="f8154-180">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="f8154-181">但是，这不会影响包含 web 视图的窗口（传递到 CreateCoreWebView2Controller 的 HWND 参数）。</span><span class="sxs-lookup"><span data-stu-id="f8154-181">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Controller).</span></span> <span data-ttu-id="f8154-182">如果你希望该窗口也消失，除了修改 IsVisible 属性外，还可直接对其调用 ShowWindow。</span><span class="sxs-lookup"><span data-stu-id="f8154-182">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="f8154-183">在最小化或还原顶级窗口时，Web 视图作为子窗口不会收到窗口消息。</span><span class="sxs-lookup"><span data-stu-id="f8154-183">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="f8154-184">出于性能原因，开发人员应在应用窗口最小化时将 Web 视图的 IsVisible 属性设置为 false，并在还原应用窗口时将其设置为 false。</span><span class="sxs-lookup"><span data-stu-id="f8154-184">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="f8154-185">应用窗口可通过在接收 WM_SYSCOMMAND 消息时处理 SC_MINIMIZE 和 SC_RESTORE 命令来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="f8154-185">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

#### <span data-ttu-id="f8154-186">LostFocus</span><span class="sxs-lookup"><span data-stu-id="f8154-186">LostFocus</span></span> 

<span data-ttu-id="f8154-187">当 Web 视图失去焦点时，将激发 LostFocus。</span><span class="sxs-lookup"><span data-stu-id="f8154-187">LostFocus fires when WebView lost focus.</span></span>

> <span data-ttu-id="f8154-188">公共事件 EventHandler< 对象 > [LostFocus](#lostfocus)</span><span class="sxs-lookup"><span data-stu-id="f8154-188">public event EventHandler< object > [LostFocus](#lostfocus)</span></span>

<span data-ttu-id="f8154-189">在引发 MoveFocusRequested 事件的情况下，当 MoveFocusRequested 事件引发时，焦点仍在 Web 视图上。</span><span class="sxs-lookup"><span data-stu-id="f8154-189">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="f8154-190">只有在应用的 MoveFocusRequested 事件或从 Web 视图中设置焦点的情况下，才会在应用的代码或默认操作时引发丢失焦点。</span><span class="sxs-lookup"><span data-stu-id="f8154-190">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="f8154-191">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="f8154-191">MoveFocusRequested</span></span> 

<span data-ttu-id="f8154-192">当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。</span><span class="sxs-lookup"><span data-stu-id="f8154-192">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>

> <span data-ttu-id="f8154-193">公共事件 EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)  >  [MoveFocusRequested](#movefocusrequested)</span><span class="sxs-lookup"><span data-stu-id="f8154-193">public event EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md) > [MoveFocusRequested](#movefocusrequested)</span></span>

<span data-ttu-id="f8154-194">激发此事件时，Web 视图的焦点未发生更改。</span><span class="sxs-lookup"><span data-stu-id="f8154-194">The WebView's focus has not changed when this event is fired.</span></span>

#### <span data-ttu-id="f8154-195">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="f8154-195">ParentWindow</span></span> 

<span data-ttu-id="f8154-196">由此 Web 视图用于呈现内容的应用提供的父窗口。</span><span class="sxs-lookup"><span data-stu-id="f8154-196">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="f8154-197">公共 IntPtr [ParentWindow](#parentwindow)</span><span class="sxs-lookup"><span data-stu-id="f8154-197">public IntPtr [ParentWindow](#parentwindow)</span></span>

<span data-ttu-id="f8154-198">设置该属性将导致 Web 视图将其窗口重定为新提供的窗口。</span><span class="sxs-lookup"><span data-stu-id="f8154-198">Setting the property will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="f8154-199">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="f8154-199">ZoomFactor</span></span> 

<span data-ttu-id="f8154-200">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="f8154-200">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="f8154-201">公共双[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="f8154-201">public double [ZoomFactor](#zoomfactor)</span></span>

<span data-ttu-id="f8154-202">请注意，更改缩放系数可能会导致 `window.innerWidth/innerHeight` 页面布局和页面布局的更改。</span><span class="sxs-lookup"><span data-stu-id="f8154-202">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="f8154-203">由主机通过调用 ZoomFactor 应用的缩放系数成为 Web 视图的新默认缩放。</span><span class="sxs-lookup"><span data-stu-id="f8154-203">A zoom factor that is applied by the host by calling ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="f8154-204">此缩放系数在跨导航应用，并且是当用户按 ctrl + 0 时，将在 Web 视图中返回 "缩放系数"。</span><span class="sxs-lookup"><span data-stu-id="f8154-204">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="f8154-205">如果用户更改了缩放系数（从而导致应用收到 ZoomFactorChanged），则该缩放仅适用于当前页面。</span><span class="sxs-lookup"><span data-stu-id="f8154-205">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="f8154-206">任何用户应用的缩放仅适用于当前页面，并且在导航时重置。</span><span class="sxs-lookup"><span data-stu-id="f8154-206">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="f8154-207">不允许指定小于或等于0的 zoomFactor。</span><span class="sxs-lookup"><span data-stu-id="f8154-207">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="f8154-208">Web 视图也具有内部受支持的缩放系数范围。</span><span class="sxs-lookup"><span data-stu-id="f8154-208">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="f8154-209">当指定的缩放系数超出该范围时，它将规范化为在范围内，并且将针对应用的已应用的缩放系数引发 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-209">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="f8154-210">当此范围规范化发生时，ZoomFactor 属性将报告在 ZoomFactor 属性的以前修改期间指定的缩放系数，直到在 web 视图应用标准化的缩放系数后收到 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-210">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="f8154-211">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="f8154-211">ZoomFactorChanged</span></span> 

<span data-ttu-id="f8154-212">当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-212">The event fires when the ZoomFactor property of the WebView changes.</span></span>

> <span data-ttu-id="f8154-213">公共事件 EventHandler< 对象 > [ZoomFactorChanged](#zoomfactorchanged)</span><span class="sxs-lookup"><span data-stu-id="f8154-213">public event EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)</span></span>

<span data-ttu-id="f8154-214">由于调用方修改了 ZoomFactor 属性，或者由于用户手动修改缩放，因此可能会激发该事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-214">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="f8154-215">当调用方通过 ZoomFactor 属性对其进行修改时，内部缩放系数将立即更新，并且将不会出现 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="f8154-215">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="f8154-216">Web 视图将每个网站的上次使用的缩放系数相关联。</span><span class="sxs-lookup"><span data-stu-id="f8154-216">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="f8154-217">因此，在导航到其他页面时，可以更改缩放系数。</span><span class="sxs-lookup"><span data-stu-id="f8154-217">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="f8154-218">当缩放系数因此而更改时，ZoomFactorChanged 事件将在 ContentLoading 事件后立即触发。</span><span class="sxs-lookup"><span data-stu-id="f8154-218">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

#### <span data-ttu-id="f8154-219">关闭</span><span class="sxs-lookup"><span data-stu-id="f8154-219">Close</span></span> 

<span data-ttu-id="f8154-220">关闭 Web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="f8154-220">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="f8154-221">公共 void [Close](#close)（）</span><span class="sxs-lookup"><span data-stu-id="f8154-221">public void [Close](#close)()</span></span>

<span data-ttu-id="f8154-222">清理浏览器实例将释放为 Web 视图供电的资源。</span><span class="sxs-lookup"><span data-stu-id="f8154-222">Cleaning up the browser instance will release the resources powering the WebView.</span></span> <span data-ttu-id="f8154-223">如果没有其他 WebViews 使用浏览器实例，则将关闭该浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="f8154-223">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="f8154-224">调用 Close 后，所有方法调用都将失败，事件处理程序将停止触发。</span><span class="sxs-lookup"><span data-stu-id="f8154-224">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="f8154-225">具体说来，当调用 Close 时，Web 视图将释放其对其事件处理程序的引用。</span><span class="sxs-lookup"><span data-stu-id="f8154-225">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="f8154-226">当 CoreWebView2Controller 失去其最终引用且 destructed 时，将隐式调用 Close。</span><span class="sxs-lookup"><span data-stu-id="f8154-226">Close is implicitly called when the CoreWebView2Controller loses its final reference and is destructed.</span></span> <span data-ttu-id="f8154-227">但最佳做法是显式调用 Close 以避免 Web 视图和应用代码之间任何意外的引用循环。</span><span class="sxs-lookup"><span data-stu-id="f8154-227">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="f8154-228">尤其是，如果你在事件处理程序中捕获对 Web 视图的引用，你将在 Web 视图和事件处理程序之间创建引用循环。</span><span class="sxs-lookup"><span data-stu-id="f8154-228">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="f8154-229">调用 Close 将通过释放所有事件处理程序来中断此周期。</span><span class="sxs-lookup"><span data-stu-id="f8154-229">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="f8154-230">但是，为了避免这种情况，最佳做法是在 Web 视图上显式调用 Close，而不捕获对 Web 视图的引用以确保可正确清理 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="f8154-230">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

#### <span data-ttu-id="f8154-231">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="f8154-231">MoveFocus</span></span> 

<span data-ttu-id="f8154-232">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="f8154-232">Move focus into WebView.</span></span>

> <span data-ttu-id="f8154-233">公共 void [MoveFocus](#movefocus)（[CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md)理由）</span><span class="sxs-lookup"><span data-stu-id="f8154-233">public void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md) reason)</span></span>

<span data-ttu-id="f8154-234">在 Web 视图中托管的页面中，Web 视图将获得焦点，并且焦点将被设置为通信元素。</span><span class="sxs-lookup"><span data-stu-id="f8154-234">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="f8154-235">出于编程原因，焦点设置为以前具有焦点的元素，如果没有以前具有焦点的元素，则设置为默认元素。</span><span class="sxs-lookup"><span data-stu-id="f8154-235">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="f8154-236">出于下一个原因，焦点设置为第一个元素。</span><span class="sxs-lookup"><span data-stu-id="f8154-236">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="f8154-237">对于上一个原因，焦点设置为最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="f8154-237">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="f8154-238">Web 视图还可以通过用户交互获得焦点，例如单击 "在 Web 视图中" 或 "Tab"。</span><span class="sxs-lookup"><span data-stu-id="f8154-238">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="f8154-239">对于 "按 tab 键"，应用可以调用 MoveFocus 和 "下一个" 或 "上一步"，以便在确定 Web 视图是下一个 tabbable 元素时，分别与 tab 和 shift + tab 对齐。</span><span class="sxs-lookup"><span data-stu-id="f8154-239">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="f8154-240">或者，应用可以将 IsDialogMessage 作为其消息循环的一部分进行调用，以允许平台自动处理 tab 键切换。</span><span class="sxs-lookup"><span data-stu-id="f8154-240">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="f8154-241">平台将通过 WS_TABSTOP 旋转所有窗口。</span><span class="sxs-lookup"><span data-stu-id="f8154-241">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="f8154-242">当 Web 视图从 IsDialogMessage 获取焦点时，它将分别在 tab 和 shift + tab 的第一个或最后一个元素上放置焦点。</span><span class="sxs-lookup"><span data-stu-id="f8154-242">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

#### <span data-ttu-id="f8154-243">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="f8154-243">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="f8154-244">这是与界限分开的通知，告诉 Web 视图其父（或任何上级） HWND 已移动。</span><span class="sxs-lookup"><span data-stu-id="f8154-244">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="f8154-245">公共 void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)（）</span><span class="sxs-lookup"><span data-stu-id="f8154-245">public void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="f8154-246">这是辅助功能和 Web 视图中的某些对话框正常工作所必需的。</span><span class="sxs-lookup"><span data-stu-id="f8154-246">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span>

#### <span data-ttu-id="f8154-247">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="f8154-247">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="f8154-248">同时更新边界和 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="f8154-248">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="f8154-249">public void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)（Rect 边界，双 ZoomFactor）</span><span class="sxs-lookup"><span data-stu-id="f8154-249">public void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rect Bounds, double ZoomFactor)</span></span>

<span data-ttu-id="f8154-250">此操作是主机的视角的原子操作。</span><span class="sxs-lookup"><span data-stu-id="f8154-250">This operation is atomic from the host's perspective.</span></span> <span data-ttu-id="f8154-251">从此函数返回后，如果函数成功，则边界和 ZoomFactor 属性均已更新，如果函数失败，则不会更新。</span><span class="sxs-lookup"><span data-stu-id="f8154-251">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="f8154-252">如果边界和 ZoomFactor 均由同一比例（即界限和 ZoomFactor 两倍）进行更新，则页面将不会在 innerWidth/innerHeight 中看到更改，并且 Web 视图将以新的大小呈现内容，而无需中间 renderings。</span><span class="sxs-lookup"><span data-stu-id="f8154-252">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="f8154-253">此函数还可用于通过传入新值和另一个的当前值来更新 ZoomFactor 或界限之一。</span><span class="sxs-lookup"><span data-stu-id="f8154-253">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

