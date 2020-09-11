---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Controller 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 1162061dc3555968c5732372b083951b22998145
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011710"
---
# <span data-ttu-id="a6d85-104">CoreWebView2Controller 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="a6d85-104">Microsoft.Web.WebView2.Core.CoreWebView2Controller class</span></span> 

<span data-ttu-id="a6d85-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="a6d85-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="a6d85-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="a6d85-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="a6d85-107">此类是 CoreWebView2 对象的所有者，并且支持调整大小、显示和隐藏、重点介绍以及与窗口化和合成相关的其他功能。</span><span class="sxs-lookup"><span data-stu-id="a6d85-107">This class is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="a6d85-108">摘要</span><span class="sxs-lookup"><span data-stu-id="a6d85-108">Summary</span></span>

 <span data-ttu-id="a6d85-109">成员</span><span class="sxs-lookup"><span data-stu-id="a6d85-109">Members</span></span>                        | <span data-ttu-id="a6d85-110">描述</span><span class="sxs-lookup"><span data-stu-id="a6d85-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="a6d85-111">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="a6d85-111">AcceleratorKeyPressed</span></span>](#acceleratorkeypressed) | <span data-ttu-id="a6d85-112">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="a6d85-112">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>
[<span data-ttu-id="a6d85-113">界</span><span class="sxs-lookup"><span data-stu-id="a6d85-113">Bounds</span></span>](#bounds) | <span data-ttu-id="a6d85-114">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="a6d85-114">The WebView bounds.</span></span>
[<span data-ttu-id="a6d85-115">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="a6d85-115">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="a6d85-116">获取与此 CoreWebView2Controller 关联的 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="a6d85-116">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>
[<span data-ttu-id="a6d85-117">GotFocus</span><span class="sxs-lookup"><span data-stu-id="a6d85-117">GotFocus</span></span>](#gotfocus) | <span data-ttu-id="a6d85-118">当 Web 视图获得焦点时，将引发 GotFocus。</span><span class="sxs-lookup"><span data-stu-id="a6d85-118">GotFocus fires when WebView got focus.</span></span>
[<span data-ttu-id="a6d85-119">IsVisible</span><span class="sxs-lookup"><span data-stu-id="a6d85-119">IsVisible</span></span>](#isvisible) | <span data-ttu-id="a6d85-120">IsVisible 属性确定是显示还是隐藏 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="a6d85-120">The IsVisible property determines whether to show or hide the WebView.</span></span>
[<span data-ttu-id="a6d85-121">LostFocus</span><span class="sxs-lookup"><span data-stu-id="a6d85-121">LostFocus</span></span>](#lostfocus) | <span data-ttu-id="a6d85-122">当 Web 视图失去焦点时，将激发 LostFocus。</span><span class="sxs-lookup"><span data-stu-id="a6d85-122">LostFocus fires when WebView lost focus.</span></span>
[<span data-ttu-id="a6d85-123">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="a6d85-123">MoveFocusRequested</span></span>](#movefocusrequested) | <span data-ttu-id="a6d85-124">当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。</span><span class="sxs-lookup"><span data-stu-id="a6d85-124">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>
[<span data-ttu-id="a6d85-125">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="a6d85-125">ParentWindow</span></span>](#parentwindow) | <span data-ttu-id="a6d85-126">由此 Web 视图用于呈现内容的应用提供的父窗口。</span><span class="sxs-lookup"><span data-stu-id="a6d85-126">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="a6d85-127">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="a6d85-127">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="a6d85-128">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="a6d85-128">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="a6d85-129">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="a6d85-129">ZoomFactorChanged</span></span>](#zoomfactorchanged) | <span data-ttu-id="a6d85-130">当 Web 视图的 ZoomFactor 属性更改时，将触发 ZoomFactorChanged。</span><span class="sxs-lookup"><span data-stu-id="a6d85-130">ZoomFactorChanged fires when the ZoomFactor property of the WebView changes.</span></span>
[<span data-ttu-id="a6d85-131">关闭</span><span class="sxs-lookup"><span data-stu-id="a6d85-131">Close</span></span>](#close) | <span data-ttu-id="a6d85-132">关闭 Web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="a6d85-132">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="a6d85-133">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="a6d85-133">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="a6d85-134">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="a6d85-134">Move focus into WebView.</span></span>
[<span data-ttu-id="a6d85-135">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="a6d85-135">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="a6d85-136">这是与界限分开的通知，告诉 Web 视图其父 (或任何上级) HWND 移动。</span><span class="sxs-lookup"><span data-stu-id="a6d85-136">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="a6d85-137">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="a6d85-137">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="a6d85-138">同时更新边界和 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="a6d85-138">Update Bounds and ZoomFactor properties at the same time.</span></span>

<span data-ttu-id="a6d85-139">CoreWebView2Controller 拥有 CoreWebView2，如果对 CoreWebView2Controller 的所有引用消失，则将关闭 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="a6d85-139">The CoreWebView2Controller owns the CoreWebView2, and if all references to the CoreWebView2Controller go away, the WebView will be closed.</span></span>

## <span data-ttu-id="a6d85-140">成员</span><span class="sxs-lookup"><span data-stu-id="a6d85-140">Members</span></span>

#### <span data-ttu-id="a6d85-141">AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="a6d85-141">AcceleratorKeyPressed</span></span> 

<span data-ttu-id="a6d85-142">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="a6d85-142">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span>

> <span data-ttu-id="a6d85-143">公共事件 EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md)  >  [AcceleratorKeyPressed](#acceleratorkeypressed)</span><span class="sxs-lookup"><span data-stu-id="a6d85-143">public event EventHandler< [CoreWebView2AcceleratorKeyPressedEventArgs](microsoft-web-webview2-core-corewebview2acceleratorkeypressedeventargs.md) > [AcceleratorKeyPressed](#acceleratorkeypressed)</span></span>

<span data-ttu-id="a6d85-144">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="a6d85-144">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="a6d85-145">如果某个键出现以下情况之一，则将其视为一个加速器：</span><span class="sxs-lookup"><span data-stu-id="a6d85-145">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="a6d85-146">按 Ctrl 或 Alt 当前正在保持，或者</span><span class="sxs-lookup"><span data-stu-id="a6d85-146">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="a6d85-147">按下的键不会映射到字符。</span><span class="sxs-lookup"><span data-stu-id="a6d85-147">the pressed key does not map to a character.</span></span> <span data-ttu-id="a6d85-148">一些特定的键永远不会被视为加速器，如 Shift。</span><span class="sxs-lookup"><span data-stu-id="a6d85-148">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="a6d85-149">转义键始终被视为加速键。</span><span class="sxs-lookup"><span data-stu-id="a6d85-149">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="a6d85-150">通过按住键导致的 Autorepeated 键事件也会引发此事件。</span><span class="sxs-lookup"><span data-stu-id="a6d85-150">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="a6d85-151">你可以通过检查事件参数 "KeyEventLParam" 或 "PhysicalKeyStatus" 来筛选这些问题。</span><span class="sxs-lookup"><span data-stu-id="a6d85-151">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="a6d85-152">在窗口模式下，此事件处理程序是同步调用的。</span><span class="sxs-lookup"><span data-stu-id="a6d85-152">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="a6d85-153">在调用已处理 ( 事件参数或事件处理程序上的 # A1 之前，浏览器进程将被阻止，并且传出的进程间 COM 调用将失败，并出现 RPC_E_CANTCALLOUT_ININPUTSYNCCALL。</span><span class="sxs-lookup"><span data-stu-id="a6d85-153">Until you call Handled() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="a6d85-154">但是，所有 CoreWebView2 API 方法都有效。</span><span class="sxs-lookup"><span data-stu-id="a6d85-154">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="a6d85-155">在无窗口模式下，异步调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="a6d85-155">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="a6d85-156">在事件处理程序返回或处理之前，其他输入将无法访问浏览器 ( # A1 被调用，但浏览器进程本身将不会被阻止，并且传出 COM 调用将正常工作。</span><span class="sxs-lookup"><span data-stu-id="a6d85-156">Further input will not reach the browser until the event handler returns or Handled() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="a6d85-157">建议调用 (TRUE) 处理，因为你知道要处理加速键。</span><span class="sxs-lookup"><span data-stu-id="a6d85-157">It is recommended to call Handled(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

#### <span data-ttu-id="a6d85-158">界</span><span class="sxs-lookup"><span data-stu-id="a6d85-158">Bounds</span></span> 

<span data-ttu-id="a6d85-159">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="a6d85-159">The WebView bounds.</span></span>

> <span data-ttu-id="a6d85-160">公共矩形 [边界](#bounds)</span><span class="sxs-lookup"><span data-stu-id="a6d85-160">public Rectangle [Bounds](#bounds)</span></span>

<span data-ttu-id="a6d85-161">界限相对于父 HWND。</span><span class="sxs-lookup"><span data-stu-id="a6d85-161">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="a6d85-162">应用有两种方法可以放置 Web 视图：</span><span class="sxs-lookup"><span data-stu-id="a6d85-162">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="a6d85-163">创建作为 Web 视图父 HWND 的子 HWND。</span><span class="sxs-lookup"><span data-stu-id="a6d85-163">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="a6d85-164">将此窗口放置在 Web 视图应位于的位置。</span><span class="sxs-lookup"><span data-stu-id="a6d85-164">Position this window where the WebView should be.</span></span> <span data-ttu-id="a6d85-165">在这种情况下，请使用 (偏移) 的 Bound's 左上角的 (0，0) 。</span><span class="sxs-lookup"><span data-stu-id="a6d85-165">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="a6d85-166">将应用最顶部的窗口用作 Web 视图父 HWND。</span><span class="sxs-lookup"><span data-stu-id="a6d85-166">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="a6d85-167">设置 Web 视图的 Bound's 左上角，以便 Web 视图正确地放置在应用中。</span><span class="sxs-lookup"><span data-stu-id="a6d85-167">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="a6d85-168">绑定的值位于主机的坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="a6d85-168">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="a6d85-169">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="a6d85-169">CoreWebView2</span></span> 

<span data-ttu-id="a6d85-170">获取与此 CoreWebView2Controller 关联的 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="a6d85-170">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>

> <span data-ttu-id="a6d85-171">公共 [CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="a6d85-171">public [CoreWebView2](microsoft-web-webview2-core-corewebview2.md) [CoreWebView2](#corewebview2)</span></span>

#### <span data-ttu-id="a6d85-172">GotFocus</span><span class="sxs-lookup"><span data-stu-id="a6d85-172">GotFocus</span></span> 

<span data-ttu-id="a6d85-173">当 Web 视图获得焦点时，将引发 GotFocus。</span><span class="sxs-lookup"><span data-stu-id="a6d85-173">GotFocus fires when WebView got focus.</span></span>

> <span data-ttu-id="a6d85-174">公共事件 EventHandler< 对象 > [GotFocus](#gotfocus)</span><span class="sxs-lookup"><span data-stu-id="a6d85-174">public event EventHandler< object > [GotFocus](#gotfocus)</span></span>

#### <span data-ttu-id="a6d85-175">IsVisible</span><span class="sxs-lookup"><span data-stu-id="a6d85-175">IsVisible</span></span> 

<span data-ttu-id="a6d85-176">IsVisible 属性确定是显示还是隐藏 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="a6d85-176">The IsVisible property determines whether to show or hide the WebView.</span></span>

> <span data-ttu-id="a6d85-177">公共 bool [IsVisible](#isvisible)</span><span class="sxs-lookup"><span data-stu-id="a6d85-177">public bool [IsVisible](#isvisible)</span></span>

<span data-ttu-id="a6d85-178">如果 IsVisible 设置为 false，则 Web 视图将是透明的，不会呈现。</span><span class="sxs-lookup"><span data-stu-id="a6d85-178">If IsVisible is set to false, the WebView will be transparent and will not be rendered.</span></span> <span data-ttu-id="a6d85-179">但是，这不会影响 (传递到 CreateCoreWebView2Controller) 的 HWND 参数的包含 Web 视图的窗口。</span><span class="sxs-lookup"><span data-stu-id="a6d85-179">However, this will not affect the window containing the WebView (the HWND parameter that was passed to CreateCoreWebView2Controller).</span></span> <span data-ttu-id="a6d85-180">如果你希望该窗口也消失，除了修改 IsVisible 属性外，还可直接对其调用 ShowWindow。</span><span class="sxs-lookup"><span data-stu-id="a6d85-180">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="a6d85-181">在最小化或还原顶级窗口时，Web 视图作为子窗口不会收到窗口消息。</span><span class="sxs-lookup"><span data-stu-id="a6d85-181">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="a6d85-182">出于性能原因，开发人员应在应用窗口最小化时将 Web 视图的 IsVisible 属性设置为 false，并在还原应用窗口时将其设置为 false。</span><span class="sxs-lookup"><span data-stu-id="a6d85-182">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="a6d85-183">应用窗口可通过在接收 WM_SYSCOMMAND 消息时处理 SC_MINIMIZE 和 SC_RESTORE 命令来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="a6d85-183">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

#### <span data-ttu-id="a6d85-184">LostFocus</span><span class="sxs-lookup"><span data-stu-id="a6d85-184">LostFocus</span></span> 

<span data-ttu-id="a6d85-185">当 Web 视图失去焦点时，将激发 LostFocus。</span><span class="sxs-lookup"><span data-stu-id="a6d85-185">LostFocus fires when WebView lost focus.</span></span>

> <span data-ttu-id="a6d85-186">公共事件 EventHandler< 对象 > [LostFocus](#lostfocus)</span><span class="sxs-lookup"><span data-stu-id="a6d85-186">public event EventHandler< object > [LostFocus](#lostfocus)</span></span>

<span data-ttu-id="a6d85-187">在引发 MoveFocusRequested 事件的情况下，当 MoveFocusRequested 事件引发时，焦点仍在 Web 视图上。</span><span class="sxs-lookup"><span data-stu-id="a6d85-187">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="a6d85-188">仅当应用的 MoveFocusRequested 事件的代码或默认操作设置焦点离开 Web 视图时，LostFocus 才会随后引发。</span><span class="sxs-lookup"><span data-stu-id="a6d85-188">LostFocus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="a6d85-189">MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="a6d85-189">MoveFocusRequested</span></span> 

<span data-ttu-id="a6d85-190">当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。</span><span class="sxs-lookup"><span data-stu-id="a6d85-190">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span>

> <span data-ttu-id="a6d85-191">公共事件 EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md)  >  [MoveFocusRequested](#movefocusrequested)</span><span class="sxs-lookup"><span data-stu-id="a6d85-191">public event EventHandler< [CoreWebView2MoveFocusRequestedEventArgs](microsoft-web-webview2-core-corewebview2movefocusrequestedeventargs.md) > [MoveFocusRequested](#movefocusrequested)</span></span>

<span data-ttu-id="a6d85-192">激发此事件时，Web 视图的焦点未发生更改。</span><span class="sxs-lookup"><span data-stu-id="a6d85-192">The WebView's focus has not changed when this event is fired.</span></span>

#### <span data-ttu-id="a6d85-193">ParentWindow</span><span class="sxs-lookup"><span data-stu-id="a6d85-193">ParentWindow</span></span> 

<span data-ttu-id="a6d85-194">由此 Web 视图用于呈现内容的应用提供的父窗口。</span><span class="sxs-lookup"><span data-stu-id="a6d85-194">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="a6d85-195">公共 IntPtr [ParentWindow](#parentwindow)</span><span class="sxs-lookup"><span data-stu-id="a6d85-195">public IntPtr [ParentWindow](#parentwindow)</span></span>

<span data-ttu-id="a6d85-196">设置该属性将导致 Web 视图将其窗口重定为新提供的窗口。</span><span class="sxs-lookup"><span data-stu-id="a6d85-196">Setting the property will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="a6d85-197">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="a6d85-197">ZoomFactor</span></span> 

<span data-ttu-id="a6d85-198">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="a6d85-198">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="a6d85-199">公共双 [ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="a6d85-199">public double [ZoomFactor](#zoomfactor)</span></span>

<span data-ttu-id="a6d85-200">请注意，更改缩放系数可能会导致 `window.innerWidth/innerHeight` 页面布局和页面布局的更改。</span><span class="sxs-lookup"><span data-stu-id="a6d85-200">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="a6d85-201">由主机通过调用 ZoomFactor 应用的缩放系数成为 Web 视图的新默认缩放。</span><span class="sxs-lookup"><span data-stu-id="a6d85-201">A zoom factor that is applied by the host by calling ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="a6d85-202">此缩放系数在跨导航应用，并且是当用户按 ctrl + 0 时，将在 Web 视图中返回 "缩放系数"。</span><span class="sxs-lookup"><span data-stu-id="a6d85-202">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="a6d85-203">如果用户更改了缩放系数 (导致应用收到 ZoomFactorChanged) ，则该缩放仅适用于当前页面。</span><span class="sxs-lookup"><span data-stu-id="a6d85-203">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="a6d85-204">任何用户应用的缩放仅适用于当前页面，并且在导航时重置。</span><span class="sxs-lookup"><span data-stu-id="a6d85-204">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="a6d85-205">不允许指定小于或等于0的 zoomFactor。</span><span class="sxs-lookup"><span data-stu-id="a6d85-205">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="a6d85-206">Web 视图也具有内部受支持的缩放系数范围。</span><span class="sxs-lookup"><span data-stu-id="a6d85-206">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="a6d85-207">当指定的缩放系数超出该范围时，它将规范化为在范围内，并且将针对应用的已应用的缩放系数引发 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="a6d85-207">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="a6d85-208">当此范围规范化发生时，ZoomFactor 属性将报告在 ZoomFactor 属性的以前修改期间指定的缩放系数，直到在 Web 视图应用标准化的缩放系数后收到 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="a6d85-208">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after WebView applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="a6d85-209">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="a6d85-209">ZoomFactorChanged</span></span> 

<span data-ttu-id="a6d85-210">当 Web 视图的 ZoomFactor 属性更改时，将触发 ZoomFactorChanged。</span><span class="sxs-lookup"><span data-stu-id="a6d85-210">ZoomFactorChanged fires when the ZoomFactor property of the WebView changes.</span></span>

> <span data-ttu-id="a6d85-211">公共事件 EventHandler< 对象 > [ZoomFactorChanged](#zoomfactorchanged)</span><span class="sxs-lookup"><span data-stu-id="a6d85-211">public event EventHandler< object > [ZoomFactorChanged](#zoomfactorchanged)</span></span>

<span data-ttu-id="a6d85-212">由于调用方修改了 ZoomFactor 属性，或者由于用户手动修改缩放，因此可能会激发该事件。</span><span class="sxs-lookup"><span data-stu-id="a6d85-212">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="a6d85-213">当调用方通过 ZoomFactor 属性对其进行修改时，内部缩放系数将立即更新，并且将不会出现 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="a6d85-213">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="a6d85-214">Web 视图将每个网站的上次使用的缩放系数相关联。</span><span class="sxs-lookup"><span data-stu-id="a6d85-214">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="a6d85-215">因此，在导航到其他页面时，可以更改缩放系数。</span><span class="sxs-lookup"><span data-stu-id="a6d85-215">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="a6d85-216">当缩放系数因此而更改时，ZoomFactorChanged 事件将在 ContentLoading 事件后立即触发。</span><span class="sxs-lookup"><span data-stu-id="a6d85-216">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

#### <span data-ttu-id="a6d85-217">关闭</span><span class="sxs-lookup"><span data-stu-id="a6d85-217">Close</span></span> 

<span data-ttu-id="a6d85-218">关闭 Web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="a6d85-218">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="a6d85-219">公共 void [Close](#close) ( # A1</span><span class="sxs-lookup"><span data-stu-id="a6d85-219">public void [Close](#close)()</span></span>

<span data-ttu-id="a6d85-220">清理浏览器实例将释放为 Web 视图供电的资源。</span><span class="sxs-lookup"><span data-stu-id="a6d85-220">Cleaning up the browser instance will release the resources powering the WebView.</span></span> <span data-ttu-id="a6d85-221">如果没有其他 WebViews 使用浏览器实例，则将关闭该浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="a6d85-221">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="a6d85-222">调用 Close 后，所有方法调用都将失败，事件处理程序将停止触发。</span><span class="sxs-lookup"><span data-stu-id="a6d85-222">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="a6d85-223">具体说来，当调用 Close 时，Web 视图将释放其对其事件处理程序的引用。</span><span class="sxs-lookup"><span data-stu-id="a6d85-223">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="a6d85-224">当 CoreWebView2Controller 失去其最终引用且 destructed 时，将隐式调用 Close。</span><span class="sxs-lookup"><span data-stu-id="a6d85-224">Close is implicitly called when the CoreWebView2Controller loses its final reference and is destructed.</span></span> <span data-ttu-id="a6d85-225">但最佳做法是显式调用 Close 以避免 Web 视图和应用代码之间任何意外的引用循环。</span><span class="sxs-lookup"><span data-stu-id="a6d85-225">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="a6d85-226">尤其是，如果你在事件处理程序中捕获对 Web 视图的引用，你将在 Web 视图和事件处理程序之间创建引用循环。</span><span class="sxs-lookup"><span data-stu-id="a6d85-226">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="a6d85-227">调用 Close 将通过释放所有事件处理程序来中断此周期。</span><span class="sxs-lookup"><span data-stu-id="a6d85-227">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="a6d85-228">但是，为了避免这种情况，最佳做法是在 Web 视图上显式调用 Close，而不捕获对 Web 视图的引用以确保可正确清理 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="a6d85-228">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

#### <span data-ttu-id="a6d85-229">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="a6d85-229">MoveFocus</span></span> 

<span data-ttu-id="a6d85-230">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="a6d85-230">Move focus into WebView.</span></span>

> <span data-ttu-id="a6d85-231">public void [MoveFocus](#movefocus) ([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md) 理由) </span><span class="sxs-lookup"><span data-stu-id="a6d85-231">public void [MoveFocus](#movefocus)([CoreWebView2MoveFocusReason](./namespace-microsoft-web-webview2-core.md) reason)</span></span>

<span data-ttu-id="a6d85-232">在 Web 视图中托管的页面中，Web 视图将获得焦点，并且焦点将被设置为通信元素。</span><span class="sxs-lookup"><span data-stu-id="a6d85-232">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="a6d85-233">出于编程原因，焦点设置为以前具有焦点的元素，如果没有以前具有焦点的元素，则设置为默认元素。</span><span class="sxs-lookup"><span data-stu-id="a6d85-233">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="a6d85-234">出于下一个原因，焦点设置为第一个元素。</span><span class="sxs-lookup"><span data-stu-id="a6d85-234">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="a6d85-235">对于上一个原因，焦点设置为最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="a6d85-235">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="a6d85-236">Web 视图还可以通过用户交互获得焦点，例如单击 "在 Web 视图中" 或 "Tab"。</span><span class="sxs-lookup"><span data-stu-id="a6d85-236">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="a6d85-237">对于 "按 tab 键"，应用可以调用 MoveFocus 和 "下一个" 或 "上一步"，以便在确定 Web 视图是下一个 tabbable 元素时，分别与 tab 和 shift + tab 对齐。</span><span class="sxs-lookup"><span data-stu-id="a6d85-237">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="a6d85-238">或者，应用可以将 IsDialogMessage 作为其消息循环的一部分进行调用，以允许平台自动处理 tab 键切换。</span><span class="sxs-lookup"><span data-stu-id="a6d85-238">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="a6d85-239">平台将通过 WS_TABSTOP 旋转所有窗口。</span><span class="sxs-lookup"><span data-stu-id="a6d85-239">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="a6d85-240">当 Web 视图从 IsDialogMessage 获取焦点时，它将分别在 tab 和 shift + tab 的第一个或最后一个元素上放置焦点。</span><span class="sxs-lookup"><span data-stu-id="a6d85-240">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

#### <span data-ttu-id="a6d85-241">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="a6d85-241">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="a6d85-242">这是与界限分开的通知，告诉 Web 视图其父 (或任何上级) HWND 移动。</span><span class="sxs-lookup"><span data-stu-id="a6d85-242">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="a6d85-243">公共 void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged) ( # A1</span><span class="sxs-lookup"><span data-stu-id="a6d85-243">public void [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="a6d85-244">这是辅助功能和 Web 视图中的某些对话框正常工作所必需的。</span><span class="sxs-lookup"><span data-stu-id="a6d85-244">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span>

#### <span data-ttu-id="a6d85-245">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="a6d85-245">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="a6d85-246">同时更新边界和 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="a6d85-246">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="a6d85-247">public void [SetBoundsAndZoomFactor](#setboundsandzoomfactor) (矩形边界，双 ZoomFactor) </span><span class="sxs-lookup"><span data-stu-id="a6d85-247">public void [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(Rectangle Bounds, double ZoomFactor)</span></span>

<span data-ttu-id="a6d85-248">此操作是主机的视角的原子操作。</span><span class="sxs-lookup"><span data-stu-id="a6d85-248">This operation is atomic from the host's perspective.</span></span> <span data-ttu-id="a6d85-249">从此函数返回后，如果函数成功，则边界和 ZoomFactor 属性均已更新，如果函数失败，则不会更新。</span><span class="sxs-lookup"><span data-stu-id="a6d85-249">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="a6d85-250">如果边界和 ZoomFactor 都由同一比例更新 (也就是说，ZoomFactor 和都两) 倍，则页面将不会在 innerWidth/innerHeight 中看到更改，并且 Web 视图将以新的大小呈现内容，而无需中间 renderings。</span><span class="sxs-lookup"><span data-stu-id="a6d85-250">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="a6d85-251">此函数还可用于通过传入新值和另一个的当前值来更新 ZoomFactor 或界限之一。</span><span class="sxs-lookup"><span data-stu-id="a6d85-251">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

