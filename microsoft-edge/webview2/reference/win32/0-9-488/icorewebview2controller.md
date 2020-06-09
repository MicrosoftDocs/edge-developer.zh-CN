---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: bcbf527f9cf49f9ed735909cf7f1ef8081517d8d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697313"
---
# <span data-ttu-id="26f8b-104">interface ICoreWebView2Controller</span><span class="sxs-lookup"><span data-stu-id="26f8b-104">interface ICoreWebView2Controller</span></span> 

> [!NOTE]
> <span data-ttu-id="26f8b-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="26f8b-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="26f8b-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="26f8b-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2Controller
  : public IUnknown
```

<span data-ttu-id="26f8b-107">此接口是 CoreWebView2 对象的所有者，并且支持调整大小、显示和隐藏、重点介绍以及与窗口化和合成相关的其他功能。</span><span class="sxs-lookup"><span data-stu-id="26f8b-107">This interface is the owner of the CoreWebView2 object, and provides support for resizing, showing and hiding, focusing, and other functionality related to windowing and composition.</span></span>

## <span data-ttu-id="26f8b-108">摘要</span><span class="sxs-lookup"><span data-stu-id="26f8b-108">Summary</span></span>

 <span data-ttu-id="26f8b-109">成员</span><span class="sxs-lookup"><span data-stu-id="26f8b-109">Members</span></span>                        | <span data-ttu-id="26f8b-110">描述</span><span class="sxs-lookup"><span data-stu-id="26f8b-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="26f8b-111">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="26f8b-111">add_AcceleratorKeyPressed</span></span>](#add_acceleratorkeypressed) | <span data-ttu-id="26f8b-112">为 AcceleratorKeyPressed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-112">Add an event handler for the AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="26f8b-113">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-113">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="26f8b-114">为 GotFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-114">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="26f8b-115">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-115">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="26f8b-116">为 LostFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-116">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="26f8b-117">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="26f8b-117">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="26f8b-118">为 MoveFocusRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-118">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="26f8b-119">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="26f8b-119">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="26f8b-120">为 ZoomFactorChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-120">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="26f8b-121">关闭</span><span class="sxs-lookup"><span data-stu-id="26f8b-121">Close</span></span>](#close) | <span data-ttu-id="26f8b-122">关闭 Web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="26f8b-122">Closes the WebView and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="26f8b-123">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="26f8b-123">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="26f8b-124">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="26f8b-124">The webview bounds.</span></span>
[<span data-ttu-id="26f8b-125">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="26f8b-125">get_CoreWebView2</span></span>](#get_corewebview2) | <span data-ttu-id="26f8b-126">获取与此 CoreWebView2Controller 关联的 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="26f8b-126">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>
[<span data-ttu-id="26f8b-127">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="26f8b-127">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="26f8b-128">IsVisible 属性确定是显示还是隐藏 web 视图。</span><span class="sxs-lookup"><span data-stu-id="26f8b-128">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="26f8b-129">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="26f8b-129">get_ParentWindow</span></span>](#get_parentwindow) | <span data-ttu-id="26f8b-130">由此 Web 视图用于呈现内容的应用提供的父窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-130">The parent window provided by the app that this WebView is using to render content.</span></span>
[<span data-ttu-id="26f8b-131">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="26f8b-131">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="26f8b-132">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="26f8b-132">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="26f8b-133">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-133">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="26f8b-134">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="26f8b-134">Move focus into WebView.</span></span>
[<span data-ttu-id="26f8b-135">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="26f8b-135">NotifyParentWindowPositionChanged</span></span>](#notifyparentwindowpositionchanged) | <span data-ttu-id="26f8b-136">这是与界限分开的通知，告诉 Web 视图其父（或任何上级） HWND 已移动。</span><span class="sxs-lookup"><span data-stu-id="26f8b-136">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>
[<span data-ttu-id="26f8b-137">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="26f8b-137">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="26f8b-138">设置界限属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-138">Set the Bounds property.</span></span>
[<span data-ttu-id="26f8b-139">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="26f8b-139">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="26f8b-140">设置 IsVisible 属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-140">Set the IsVisible property.</span></span>
[<span data-ttu-id="26f8b-141">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="26f8b-141">put_ParentWindow</span></span>](#put_parentwindow) | <span data-ttu-id="26f8b-142">设置 Web 视图的父窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-142">Set the parent window for the WebView.</span></span>
[<span data-ttu-id="26f8b-143">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="26f8b-143">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="26f8b-144">设置 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-144">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="26f8b-145">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="26f8b-145">remove_AcceleratorKeyPressed</span></span>](#remove_acceleratorkeypressed) | <span data-ttu-id="26f8b-146">删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-146">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>
[<span data-ttu-id="26f8b-147">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-147">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="26f8b-148">删除以前使用 add_GotFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-148">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="26f8b-149">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-149">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="26f8b-150">删除以前使用 add_LostFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-150">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="26f8b-151">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="26f8b-151">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="26f8b-152">删除以前使用 add_MoveFocusRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-152">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="26f8b-153">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="26f8b-153">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="26f8b-154">删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-154">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="26f8b-155">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="26f8b-155">SetBoundsAndZoomFactor</span></span>](#setboundsandzoomfactor) | <span data-ttu-id="26f8b-156">同时更新边界和 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-156">Update Bounds and ZoomFactor properties at the same time.</span></span>

<span data-ttu-id="26f8b-157">CoreWebView2Controller 拥有 CoreWebView2，如果对 CoreWebView2Controller 的所有引用消失，则将关闭 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="26f8b-157">The CoreWebView2Controller owns the CoreWebView2, and if all references to the CoreWebView2Controller go away, the WebView will be closed.</span></span>

## <span data-ttu-id="26f8b-158">成员</span><span class="sxs-lookup"><span data-stu-id="26f8b-158">Members</span></span>

#### <span data-ttu-id="26f8b-159">add_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="26f8b-159">add_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="26f8b-160">为 AcceleratorKeyPressed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-160">Add an event handler for the AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="26f8b-161">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)（[ICoreWebView2AcceleratorKeyPressedEventHandler](icorewebview2acceleratorkeypressedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="26f8b-161">public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)([ICoreWebView2AcceleratorKeyPressedEventHandler](icorewebview2acceleratorkeypressedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="26f8b-162">当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。</span><span class="sxs-lookup"><span data-stu-id="26f8b-162">AcceleratorKeyPressed fires when an accelerator key or key combo is pressed or released while the WebView is focused.</span></span> <span data-ttu-id="26f8b-163">如果某个键出现以下情况之一，则将其视为一个加速器：</span><span class="sxs-lookup"><span data-stu-id="26f8b-163">A key is considered an accelerator if either:</span></span>

1. <span data-ttu-id="26f8b-164">按 Ctrl 或 Alt 当前正在保持，或者</span><span class="sxs-lookup"><span data-stu-id="26f8b-164">Ctrl or Alt is currently being held, or</span></span>

1. <span data-ttu-id="26f8b-165">按下的键不会映射到字符。</span><span class="sxs-lookup"><span data-stu-id="26f8b-165">the pressed key does not map to a character.</span></span> <span data-ttu-id="26f8b-166">一些特定的键永远不会被视为加速器，如 Shift。</span><span class="sxs-lookup"><span data-stu-id="26f8b-166">A few specific keys are never considered accelerators, such as Shift.</span></span> <span data-ttu-id="26f8b-167">转义键始终被视为加速键。</span><span class="sxs-lookup"><span data-stu-id="26f8b-167">The Escape key is always considered an accelerator.</span></span>

<span data-ttu-id="26f8b-168">通过按住键导致的 Autorepeated 键事件也会引发此事件。</span><span class="sxs-lookup"><span data-stu-id="26f8b-168">Autorepeated key events caused by holding the key down will also fire this event.</span></span> <span data-ttu-id="26f8b-169">你可以通过检查事件参数 "KeyEventLParam" 或 "PhysicalKeyStatus" 来筛选这些问题。</span><span class="sxs-lookup"><span data-stu-id="26f8b-169">You can filter these out by checking the event args' KeyEventLParam or PhysicalKeyStatus.</span></span>

<span data-ttu-id="26f8b-170">在窗口模式下，此事件处理程序是同步调用的。</span><span class="sxs-lookup"><span data-stu-id="26f8b-170">In windowed mode, this event handler is called synchronously.</span></span> <span data-ttu-id="26f8b-171">在事件参数或事件处理程序返回之前调用句柄（）之前，浏览器进程将被阻止，并且传出进程间 COM 调用将失败，并显示 RPC_E_CANTCALLOUT_ININPUTSYNCCALL。</span><span class="sxs-lookup"><span data-stu-id="26f8b-171">Until you call Handle() on the event args or the event handler returns, the browser process will be blocked and outgoing cross-process COM calls will fail with RPC_E_CANTCALLOUT_ININPUTSYNCCALL.</span></span> <span data-ttu-id="26f8b-172">但是，所有 CoreWebView2 API 方法都有效。</span><span class="sxs-lookup"><span data-stu-id="26f8b-172">All CoreWebView2 API methods will work, however.</span></span>

<span data-ttu-id="26f8b-173">在无窗口模式下，异步调用事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-173">In windowless mode, the event handler is called asynchronously.</span></span> <span data-ttu-id="26f8b-174">在调用事件处理程序返回或句柄（）时，将不会访问浏览器，但浏览器进程本身将不会被阻止，并且传出 COM 调用将正常工作。</span><span class="sxs-lookup"><span data-stu-id="26f8b-174">Further input will not reach the browser until the event handler returns or Handle() is called, but the browser process itself will not be blocked, and outgoing COM calls will work normally.</span></span>

<span data-ttu-id="26f8b-175">建议你先调用句柄（TRUE），然后才能知道你希望处理加速键。</span><span class="sxs-lookup"><span data-stu-id="26f8b-175">It is recommended to call Handle(TRUE) as early as you can know that you want to handle the accelerator key.</span></span>

```cpp
    // Register a handler for the AcceleratorKeyPressed event.
    CHECK_FAILURE(m_controller->add_AcceleratorKeyPressed(
        Callback<ICoreWebView2AcceleratorKeyPressedEventHandler>(
            [this](
                ICoreWebView2Controller* sender,
                ICoreWebView2AcceleratorKeyPressedEventArgs* args) -> HRESULT {
                COREWEBVIEW2_KEY_EVENT_KIND kind;
                CHECK_FAILURE(args->get_KeyEventKind(&kind));
                // We only care about key down events.
                if (kind == COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN ||
                    kind == COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN)
                {
                    UINT key;
                    CHECK_FAILURE(args->get_VirtualKey(&key));
                    // Check if the key is one we want to handle.
                    if (std::function<void()> action =
                            m_appWindow->GetAcceleratorKeyFunction(key))
                    {
                        // Keep the browser from handling this key, whether it's autorepeated or
                        // not.
                        CHECK_FAILURE(args->put_Handled(TRUE));

                        // Filter out autorepeated keys.
                        COREWEBVIEW2_PHYSICAL_KEY_STATUS status;
                        CHECK_FAILURE(args->get_PhysicalKeyStatus(&status));
                        if (!status.WasKeyDown)
                        {
                            // Perform the action asynchronously to avoid blocking the
                            // browser process's event queue.
                            m_appWindow->RunAsync(action);
                        }
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_acceleratorKeyPressedToken));
```

#### <span data-ttu-id="26f8b-176">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-176">add_GotFocus</span></span> 

<span data-ttu-id="26f8b-177">为 GotFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-177">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="26f8b-178">public HRESULT [add_GotFocus](#add_gotfocus)（[ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="26f8b-178">public HRESULT [add_GotFocus](#add_gotfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="26f8b-179">当 Web 视图获得焦点时，将引发 GotFocus。</span><span class="sxs-lookup"><span data-stu-id="26f8b-179">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="26f8b-180">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-180">add_LostFocus</span></span> 

<span data-ttu-id="26f8b-181">为 LostFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-181">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="26f8b-182">public HRESULT [add_LostFocus](#add_lostfocus)（[ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="26f8b-182">public HRESULT [add_LostFocus](#add_lostfocus)([ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="26f8b-183">当 Web 视图失去焦点时，将激发 LostFocus。</span><span class="sxs-lookup"><span data-stu-id="26f8b-183">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="26f8b-184">在引发 MoveFocusRequested 事件的情况下，当 MoveFocusRequested 事件引发时，焦点仍在 Web 视图上。</span><span class="sxs-lookup"><span data-stu-id="26f8b-184">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="26f8b-185">只有在应用的 MoveFocusRequested 事件或从 Web 视图中设置焦点的情况下，才会在应用的代码或默认操作时引发丢失焦点。</span><span class="sxs-lookup"><span data-stu-id="26f8b-185">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="26f8b-186">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="26f8b-186">add_MoveFocusRequested</span></span> 

<span data-ttu-id="26f8b-187">为 MoveFocusRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-187">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="26f8b-188">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)（[ICoreWebView2MoveFocusRequestedEventHandler](icorewebview2movefocusrequestedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="26f8b-188">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([ICoreWebView2MoveFocusRequestedEventHandler](icorewebview2movefocusrequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="26f8b-189">当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。</span><span class="sxs-lookup"><span data-stu-id="26f8b-189">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="26f8b-190">激发此事件时，Web 视图的焦点未发生更改。</span><span class="sxs-lookup"><span data-stu-id="26f8b-190">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_controller->add_MoveFocusRequested(
        Callback<ICoreWebView2MoveFocusRequestedEventHandler>(
            [this](
                ICoreWebView2Controller* sender,
                ICoreWebView2MoveFocusRequestedEventArgs* args) -> HRESULT {
                if (!g_autoTabHandle)
                {
                    COREWEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### <span data-ttu-id="26f8b-191">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="26f8b-191">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="26f8b-192">为 ZoomFactorChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-192">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="26f8b-193">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)（[ICoreWebView2ZoomFactorChangedEventHandler](icorewebview2zoomfactorchangedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="26f8b-193">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([ICoreWebView2ZoomFactorChangedEventHandler](icorewebview2zoomfactorchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="26f8b-194">当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="26f8b-194">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="26f8b-195">由于调用方修改了 ZoomFactor 属性，或者由于用户手动修改缩放，因此可能会激发该事件。</span><span class="sxs-lookup"><span data-stu-id="26f8b-195">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="26f8b-196">当调用方通过 ZoomFactor 属性对其进行修改时，内部缩放系数将立即更新，并且将不会出现 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="26f8b-196">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="26f8b-197">Web 视图将每个网站的上次使用的缩放系数相关联。</span><span class="sxs-lookup"><span data-stu-id="26f8b-197">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="26f8b-198">因此，在导航到其他页面时，可以更改缩放系数。</span><span class="sxs-lookup"><span data-stu-id="26f8b-198">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="26f8b-199">当缩放系数因此而更改时，ZoomFactorChanged 事件将在 ContentLoading 事件后立即触发。</span><span class="sxs-lookup"><span data-stu-id="26f8b-199">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the ContentLoading event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_controller->add_ZoomFactorChanged(
        Callback<ICoreWebView2ZoomFactorChangedEventHandler>(
            [this](ICoreWebView2Controller* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### <span data-ttu-id="26f8b-200">关闭</span><span class="sxs-lookup"><span data-stu-id="26f8b-200">Close</span></span> 

<span data-ttu-id="26f8b-201">关闭 Web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="26f8b-201">Closes the WebView and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="26f8b-202">公共 HRESULT [Close](#close)（）</span><span class="sxs-lookup"><span data-stu-id="26f8b-202">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="26f8b-203">清理浏览器实例将释放为 Web 视图供电的资源。</span><span class="sxs-lookup"><span data-stu-id="26f8b-203">Cleaning up the browser instance will release the resources powering the WebView.</span></span> <span data-ttu-id="26f8b-204">如果没有其他 WebViews 使用浏览器实例，则将关闭该浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="26f8b-204">The browser instance will be shut down if there are no other WebViews using it.</span></span>

<span data-ttu-id="26f8b-205">调用 Close 后，所有方法调用都将失败，事件处理程序将停止触发。</span><span class="sxs-lookup"><span data-stu-id="26f8b-205">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="26f8b-206">具体说来，当调用 Close 时，Web 视图将释放其对其事件处理程序的引用。</span><span class="sxs-lookup"><span data-stu-id="26f8b-206">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="26f8b-207">当 CoreWebView2Controller 失去其最终引用且 destructed 时，将隐式调用 Close。</span><span class="sxs-lookup"><span data-stu-id="26f8b-207">Close is implicitly called when the CoreWebView2Controller loses its final reference and is destructed.</span></span> <span data-ttu-id="26f8b-208">但最佳做法是显式调用 Close 以避免 Web 视图和应用代码之间任何意外的引用循环。</span><span class="sxs-lookup"><span data-stu-id="26f8b-208">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="26f8b-209">尤其是，如果你在事件处理程序中捕获对 Web 视图的引用，你将在 Web 视图和事件处理程序之间创建引用循环。</span><span class="sxs-lookup"><span data-stu-id="26f8b-209">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="26f8b-210">调用 Close 将通过释放所有事件处理程序来中断此周期。</span><span class="sxs-lookup"><span data-stu-id="26f8b-210">Calling Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="26f8b-211">但是，为了避免这种情况，最佳做法是在 Web 视图上显式调用 Close，而不捕获对 Web 视图的引用以确保可正确清理 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="26f8b-211">But to avoid this situation it is best practice both to explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView(bool cleanupUserDataFolder)
{
    DeleteAllComponents();
    if (m_controller)
    {
        m_controller->Close();
        m_controller = nullptr;
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
    if (cleanupUserDataFolder)
    {
        // For non-UWP apps, the default user data folder {Executable File Name}.WebView2
        // is in the same directory next to the app executable. If end
        // developers specify userDataFolder during WebView environment
        // creation, they would need to pass in that explicit value here.
        // For more information about userDataFolder:
        // https://docs.microsoft.com/microsoft-edge/hosting/webview2/reference/win32/0-9-488/webview2-idl#createwebview2environmentwithoptions
        WCHAR userDataFolder[MAX_PATH] = L"";
        // Obtain the absolute path for relative paths that include "./" or "../"
        _wfullpath(
            userDataFolder, GetLocalPath(L"WebView2APISample.exe.WebView2").c_str(), MAX_PATH);
        std::wstring userDataFolderPath(userDataFolder);

        std::wstring message = L"Are you sure you want to clean up the user data folder at\n";
        message += userDataFolderPath;
        message += L"\n?\nWarning: This action is not reversible.\n\n";
        message += L"Click No if there are other open WebView instances.\n";

        if (MessageBox(m_mainWindow, message.c_str(), L"Cleanup User Data Folder", MB_YESNO) ==
            IDYES)
        {
            CHECK_FAILURE(DeleteFileRecursive(userDataFolderPath));
        }
    }
}
```

#### <span data-ttu-id="26f8b-212">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="26f8b-212">get_Bounds</span></span> 

<span data-ttu-id="26f8b-213">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="26f8b-213">The webview bounds.</span></span>

> <span data-ttu-id="26f8b-214">public HRESULT [get_Bounds](#get_bounds)（RECT \* 界限）</span><span class="sxs-lookup"><span data-stu-id="26f8b-214">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="26f8b-215">界限相对于父 HWND。</span><span class="sxs-lookup"><span data-stu-id="26f8b-215">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="26f8b-216">应用有两种方法可以放置 Web 视图：</span><span class="sxs-lookup"><span data-stu-id="26f8b-216">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="26f8b-217">创建作为 Web 视图父 HWND 的子 HWND。</span><span class="sxs-lookup"><span data-stu-id="26f8b-217">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="26f8b-218">将此窗口放置在 Web 视图应位于的位置。</span><span class="sxs-lookup"><span data-stu-id="26f8b-218">Position this window where the WebView should be.</span></span> <span data-ttu-id="26f8b-219">在这种情况下，对 Web 视图的 Bound's 左上角（偏移）使用（0，0）。</span><span class="sxs-lookup"><span data-stu-id="26f8b-219">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="26f8b-220">将应用最顶部的窗口用作 Web 视图父 HWND。</span><span class="sxs-lookup"><span data-stu-id="26f8b-220">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="26f8b-221">设置 Web 视图的 Bound's 左上角，以便 Web 视图正确地放置在应用中。</span><span class="sxs-lookup"><span data-stu-id="26f8b-221">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="26f8b-222">绑定的值位于主机的坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="26f8b-222">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="26f8b-223">get_CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="26f8b-223">get_CoreWebView2</span></span> 

<span data-ttu-id="26f8b-224">获取与此 CoreWebView2Controller 关联的 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="26f8b-224">Gets the CoreWebView2 associated with this CoreWebView2Controller.</span></span>

> <span data-ttu-id="26f8b-225">公共 HRESULT [get_CoreWebView2](#get_corewebview2)（[ICoreWebView2](icorewebview2.md) \* \* CoreWebView2）</span><span class="sxs-lookup"><span data-stu-id="26f8b-225">public HRESULT [get_CoreWebView2](#get_corewebview2)([ICoreWebView2](icorewebview2.md) \*\* coreWebView2)</span></span>

#### <span data-ttu-id="26f8b-226">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="26f8b-226">get_IsVisible</span></span> 

<span data-ttu-id="26f8b-227">IsVisible 属性确定是显示还是隐藏 web 视图。</span><span class="sxs-lookup"><span data-stu-id="26f8b-227">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="26f8b-228">public HRESULT [get_IsVisible](#get_isvisible)（BOOL \* IsVisible）</span><span class="sxs-lookup"><span data-stu-id="26f8b-228">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="26f8b-229">如果 IsVisible 设置为 false，则 web 视图将是透明的，不会呈现。</span><span class="sxs-lookup"><span data-stu-id="26f8b-229">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="26f8b-230">但是，这不会影响包含 web 视图的窗口（传递到 CreateCoreWebView2Controller 的 HWND 参数）。</span><span class="sxs-lookup"><span data-stu-id="26f8b-230">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateCoreWebView2Controller).</span></span> <span data-ttu-id="26f8b-231">如果你希望该窗口也消失，除了修改 IsVisible 属性外，还可直接对其调用 ShowWindow。</span><span class="sxs-lookup"><span data-stu-id="26f8b-231">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="26f8b-232">在最小化或还原顶级窗口时，Web 视图作为子窗口不会收到窗口消息。</span><span class="sxs-lookup"><span data-stu-id="26f8b-232">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="26f8b-233">出于性能原因，开发人员应在应用窗口最小化时将 Web 视图的 IsVisible 属性设置为 false，并在还原应用窗口时将其设置为 false。</span><span class="sxs-lookup"><span data-stu-id="26f8b-233">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="26f8b-234">应用窗口可通过在接收 WM_SYSCOMMAND 消息时处理 SC_MINIMIZE 和 SC_RESTORE 命令来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="26f8b-234">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_controller->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_controller->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="26f8b-235">get_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="26f8b-235">get_ParentWindow</span></span> 

<span data-ttu-id="26f8b-236">由此 Web 视图用于呈现内容的应用提供的父窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-236">The parent window provided by the app that this WebView is using to render content.</span></span>

> <span data-ttu-id="26f8b-237">公共 HRESULT [get_ParentWindow](#get_parentwindow)（HWND \* topLevelWindow）</span><span class="sxs-lookup"><span data-stu-id="26f8b-237">public HRESULT [get_ParentWindow](#get_parentwindow)(HWND \* topLevelWindow)</span></span>

<span data-ttu-id="26f8b-238">此 API 最初返回传递到 CreateCoreWebView2Controller 的窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-238">This API initially returns the window passed into CreateCoreWebView2Controller.</span></span>

#### <span data-ttu-id="26f8b-239">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="26f8b-239">get_ZoomFactor</span></span> 

<span data-ttu-id="26f8b-240">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="26f8b-240">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="26f8b-241">公共 HRESULT [get_ZoomFactor](#get_zoomfactor)（Double \* ZoomFactor）</span><span class="sxs-lookup"><span data-stu-id="26f8b-241">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="26f8b-242">请注意，更改缩放系数可能会导致 `window.innerWidth/innerHeight` 页面布局和页面布局的更改。</span><span class="sxs-lookup"><span data-stu-id="26f8b-242">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="26f8b-243">由主机通过调用 ZoomFactor 应用的缩放系数成为 Web 视图的新默认缩放。</span><span class="sxs-lookup"><span data-stu-id="26f8b-243">A zoom factor that is applied by the host by calling ZoomFactor becomes the new default zoom for the WebView.</span></span> <span data-ttu-id="26f8b-244">此缩放系数在跨导航应用，并且是当用户按 ctrl + 0 时，将在 Web 视图中返回 "缩放系数"。</span><span class="sxs-lookup"><span data-stu-id="26f8b-244">This zoom factor applies across navigations and is the zoom factor WebView is returned to when the user presses ctrl+0.</span></span> <span data-ttu-id="26f8b-245">如果用户更改了缩放系数（从而导致应用收到 ZoomFactorChanged），则该缩放仅适用于当前页面。</span><span class="sxs-lookup"><span data-stu-id="26f8b-245">When the zoom factor is changed by the user (resulting in the app receiving ZoomFactorChanged), that zoom applies only for the current page.</span></span> <span data-ttu-id="26f8b-246">任何用户应用的缩放仅适用于当前页面，并且在导航时重置。</span><span class="sxs-lookup"><span data-stu-id="26f8b-246">Any user applied zoom is only for the current page and is reset on a navigation.</span></span> <span data-ttu-id="26f8b-247">不允许指定小于或等于0的 zoomFactor。</span><span class="sxs-lookup"><span data-stu-id="26f8b-247">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="26f8b-248">Web 视图也具有内部受支持的缩放系数范围。</span><span class="sxs-lookup"><span data-stu-id="26f8b-248">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="26f8b-249">当指定的缩放系数超出该范围时，它将规范化为在范围内，并且将针对应用的已应用的缩放系数引发 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="26f8b-249">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="26f8b-250">当此范围规范化发生时，ZoomFactor 属性将报告在 ZoomFactor 属性的以前修改期间指定的缩放系数，直到在 web 视图应用标准化的缩放系数后收到 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="26f8b-250">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="26f8b-251">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-251">MoveFocus</span></span> 

<span data-ttu-id="26f8b-252">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="26f8b-252">Move focus into WebView.</span></span>

> <span data-ttu-id="26f8b-253">公共 HRESULT [MoveFocus](#movefocus)（COREWEBVIEW2_MOVE_FOCUS_REASON 原因）</span><span class="sxs-lookup"><span data-stu-id="26f8b-253">public HRESULT [MoveFocus](#movefocus)(COREWEBVIEW2_MOVE_FOCUS_REASON reason)</span></span>

<span data-ttu-id="26f8b-254">在 Web 视图中托管的页面中，Web 视图将获得焦点，并且焦点将被设置为通信元素。</span><span class="sxs-lookup"><span data-stu-id="26f8b-254">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="26f8b-255">出于编程原因，焦点设置为以前具有焦点的元素，如果没有以前具有焦点的元素，则设置为默认元素。</span><span class="sxs-lookup"><span data-stu-id="26f8b-255">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="26f8b-256">出于下一个原因，焦点设置为第一个元素。</span><span class="sxs-lookup"><span data-stu-id="26f8b-256">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="26f8b-257">对于上一个原因，焦点设置为最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="26f8b-257">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="26f8b-258">Web 视图还可以通过用户交互获得焦点，例如单击 "在 Web 视图中" 或 "Tab"。</span><span class="sxs-lookup"><span data-stu-id="26f8b-258">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="26f8b-259">对于 "按 tab 键"，应用可以调用 MoveFocus 和 "下一个" 或 "上一步"，以便在确定 Web 视图是下一个 tabbable 元素时，分别与 tab 和 shift + tab 对齐。</span><span class="sxs-lookup"><span data-stu-id="26f8b-259">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="26f8b-260">或者，应用可以将 IsDialogMessage 作为其消息循环的一部分进行调用，以允许平台自动处理 tab 键切换。</span><span class="sxs-lookup"><span data-stu-id="26f8b-260">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="26f8b-261">平台将通过 WS_TABSTOP 旋转所有窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-261">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="26f8b-262">当 Web 视图从 IsDialogMessage 获取焦点时，它将分别在 tab 和 shift + tab 的第一个或最后一个元素上放置焦点。</span><span class="sxs-lookup"><span data-stu-id="26f8b-262">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (size_t i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (size_t i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_controller->MoveFocus(COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_controller->MoveFocus(COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="26f8b-263">NotifyParentWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="26f8b-263">NotifyParentWindowPositionChanged</span></span> 

<span data-ttu-id="26f8b-264">这是与界限分开的通知，告诉 Web 视图其父（或任何上级） HWND 已移动。</span><span class="sxs-lookup"><span data-stu-id="26f8b-264">This is a notification separate from Bounds that tells WebView its parent (or any ancestor) HWND moved.</span></span>

> <span data-ttu-id="26f8b-265">公共 HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)（）</span><span class="sxs-lookup"><span data-stu-id="26f8b-265">public HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)()</span></span>

<span data-ttu-id="26f8b-266">这是辅助功能和 Web 视图中的某些对话框正常工作所必需的。</span><span class="sxs-lookup"><span data-stu-id="26f8b-266">This is needed for accessibility and certain dialogs in WebView to work correctly.</span></span> 
```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_controller->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### <span data-ttu-id="26f8b-267">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="26f8b-267">put_Bounds</span></span> 

<span data-ttu-id="26f8b-268">设置界限属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-268">Set the Bounds property.</span></span>

> <span data-ttu-id="26f8b-269">public HRESULT [put_Bounds](#put_bounds)（RECT 界限）</span><span class="sxs-lookup"><span data-stu-id="26f8b-269">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    SIZE webViewSize = {
            LONG((m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio * m_webViewScale),
            LONG((m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio * m_webViewScale) };

    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        webViewSize.cy + m_webViewBounds.top);
    desiredBounds.right = LONG(
        webViewSize.cx + m_webViewBounds.left);

    m_controller->put_Bounds(desiredBounds);
    if (m_compositionController)
    {
        POINT webViewOffset = {m_webViewBounds.left, m_webViewBounds.top};

        if (m_dcompDevice)
        {
            CHECK_FAILURE(m_dcompRootVisual->SetOffsetX(float(webViewOffset.x)));
            CHECK_FAILURE(m_dcompRootVisual->SetOffsetY(float(webViewOffset.y)));
            CHECK_FAILURE(m_dcompRootVisual->SetClip(
                {0, 0, float(webViewSize.cx), float(webViewSize.cy)}));
            CHECK_FAILURE(m_dcompDevice->Commit());
        }
        else if (m_wincompHelper)
        {
            m_wincompHelper->UpdateSizeAndPosition(webViewOffset, webViewSize);
        }
    }
}
```

#### <span data-ttu-id="26f8b-270">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="26f8b-270">put_IsVisible</span></span> 

<span data-ttu-id="26f8b-271">设置 IsVisible 属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-271">Set the IsVisible property.</span></span>

> <span data-ttu-id="26f8b-272">公共 HRESULT [put_IsVisible](#put_isvisible)（布尔值 IsVisible）</span><span class="sxs-lookup"><span data-stu-id="26f8b-272">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_controller->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_controller->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="26f8b-273">put_ParentWindow</span><span class="sxs-lookup"><span data-stu-id="26f8b-273">put_ParentWindow</span></span> 

<span data-ttu-id="26f8b-274">设置 Web 视图的父窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-274">Set the parent window for the WebView.</span></span>

> <span data-ttu-id="26f8b-275">公共 HRESULT [put_ParentWindow](#put_parentwindow)（HWND topLevelWindow）</span><span class="sxs-lookup"><span data-stu-id="26f8b-275">public HRESULT [put_ParentWindow](#put_parentwindow)(HWND topLevelWindow)</span></span>

<span data-ttu-id="26f8b-276">这将导致 Web 视图将其窗口重定为新提供的窗口。</span><span class="sxs-lookup"><span data-stu-id="26f8b-276">This will cause the WebView to reparent its window to the newly provided window.</span></span>

#### <span data-ttu-id="26f8b-277">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="26f8b-277">put_ZoomFactor</span></span> 

<span data-ttu-id="26f8b-278">设置 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-278">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="26f8b-279">公共 HRESULT [put_ZoomFactor](#put_zoomfactor)（double ZoomFactor）</span><span class="sxs-lookup"><span data-stu-id="26f8b-279">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="26f8b-280">remove_AcceleratorKeyPressed</span><span class="sxs-lookup"><span data-stu-id="26f8b-280">remove_AcceleratorKeyPressed</span></span> 

<span data-ttu-id="26f8b-281">删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-281">Remove an event handler previously added with add_AcceleratorKeyPressed.</span></span>

> <span data-ttu-id="26f8b-282">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="26f8b-282">public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="26f8b-283">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-283">remove_GotFocus</span></span> 

<span data-ttu-id="26f8b-284">删除以前使用 add_GotFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-284">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="26f8b-285">public HRESULT [remove_GotFocus](#remove_gotfocus)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="26f8b-285">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="26f8b-286">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="26f8b-286">remove_LostFocus</span></span> 

<span data-ttu-id="26f8b-287">删除以前使用 add_LostFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-287">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="26f8b-288">public HRESULT [remove_LostFocus](#remove_lostfocus)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="26f8b-288">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="26f8b-289">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="26f8b-289">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="26f8b-290">删除以前使用 add_MoveFocusRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-290">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="26f8b-291">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="26f8b-291">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="26f8b-292">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="26f8b-292">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="26f8b-293">删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="26f8b-293">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="26f8b-294">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="26f8b-294">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="26f8b-295">SetBoundsAndZoomFactor</span><span class="sxs-lookup"><span data-stu-id="26f8b-295">SetBoundsAndZoomFactor</span></span> 

<span data-ttu-id="26f8b-296">同时更新边界和 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="26f8b-296">Update Bounds and ZoomFactor properties at the same time.</span></span>

> <span data-ttu-id="26f8b-297">公共 HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)（RECT 边界，双 zoomFactor）</span><span class="sxs-lookup"><span data-stu-id="26f8b-297">public HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)(RECT bounds, double zoomFactor)</span></span>

<span data-ttu-id="26f8b-298">此操作是主机的视角的原子操作。</span><span class="sxs-lookup"><span data-stu-id="26f8b-298">This operation is atomic from the host's perspective.</span></span> <span data-ttu-id="26f8b-299">从此函数返回后，如果函数成功，则边界和 ZoomFactor 属性均已更新，如果函数失败，则不会更新。</span><span class="sxs-lookup"><span data-stu-id="26f8b-299">After returning from this function, the Bounds and ZoomFactor properties will have both been updated if the function is successful, or neither will be updated if the function fails.</span></span> <span data-ttu-id="26f8b-300">如果边界和 ZoomFactor 均由同一比例（即界限和 ZoomFactor 两倍）进行更新，则页面将不会在 innerWidth/innerHeight 中看到更改，并且 Web 视图将以新的大小呈现内容，而无需中间 renderings。</span><span class="sxs-lookup"><span data-stu-id="26f8b-300">If Bounds and ZoomFactor are both updated by the same scale (i.e. Bounds and ZoomFactor are both doubled), then the page will not see a change in window.innerWidth/innerHeight and the WebView will render the content at the new size and zoom without intermediate renderings.</span></span> <span data-ttu-id="26f8b-301">此函数还可用于通过传入新值和另一个的当前值来更新 ZoomFactor 或界限之一。</span><span class="sxs-lookup"><span data-stu-id="26f8b-301">This function can also be used to update just one of ZoomFactor or Bounds by passing in the new value for one and the current value for the other.</span></span>

```cpp
void ViewComponent::SetScale(float scale)
{
    RECT bounds;
    CHECK_FAILURE(m_controller->get_Bounds(&bounds));
    double scaleChange = scale / m_webViewScale;

    bounds.bottom = LONG(
        (bounds.bottom - bounds.top) * scaleChange + bounds.top);
    bounds.right = LONG(
        (bounds.right - bounds.left) * scaleChange + bounds.left);

    m_webViewScale = scale;
    m_controller->SetBoundsAndZoomFactor(bounds, scale);
}
```

