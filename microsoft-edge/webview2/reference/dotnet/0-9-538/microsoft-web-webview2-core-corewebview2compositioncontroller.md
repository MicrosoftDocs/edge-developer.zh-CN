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
ms.openlocfilehash: 33adcccc4174a4ebcbabe4a169cd430942ad8a5a
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698549"
---
# <span data-ttu-id="8be6b-104">CoreWebView2CompositionController 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="8be6b-104">Microsoft.Web.WebView2.Core.CoreWebView2CompositionController class</span></span> 

> [!NOTE]
> <span data-ttu-id="8be6b-105">这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。</span><span class="sxs-lookup"><span data-stu-id="8be6b-105">This is an [experimental API](../../../concepts/versioning.md#experimental-apis) that shipped with our SDK version [0.9.538-prerelease](../../../releasenotes.md#09538).</span></span>

<span data-ttu-id="8be6b-106">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="8be6b-106">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="8be6b-107">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="8be6b-107">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="8be6b-108">此类是 CoreWebView2Controller 类的扩展，用于支持可视化托管。</span><span class="sxs-lookup"><span data-stu-id="8be6b-108">This class is an extension of the CoreWebView2Controller class to support visual hosting.</span></span>

## <span data-ttu-id="8be6b-109">摘要</span><span class="sxs-lookup"><span data-stu-id="8be6b-109">Summary</span></span>

 <span data-ttu-id="8be6b-110">成员</span><span class="sxs-lookup"><span data-stu-id="8be6b-110">Members</span></span>                        | <span data-ttu-id="8be6b-111">描述</span><span class="sxs-lookup"><span data-stu-id="8be6b-111">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="8be6b-112">Cursor</span><span class="sxs-lookup"><span data-stu-id="8be6b-112">Cursor</span></span>](#cursor) | <span data-ttu-id="8be6b-113">Web 视图所认为的当前光标应该是。</span><span class="sxs-lookup"><span data-stu-id="8be6b-113">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="8be6b-114">CursorChanged</span><span class="sxs-lookup"><span data-stu-id="8be6b-114">CursorChanged</span></span>](#cursorchanged) | <span data-ttu-id="8be6b-115">当 Web 视图认为光标应更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="8be6b-115">The event fires when WebView thinks the cursor should be changed.</span></span>
[<span data-ttu-id="8be6b-116">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="8be6b-116">RootVisualTarget</span></span>](#rootvisualtarget) | <span data-ttu-id="8be6b-117">RootVisualTarget 是托管应用的可视化树中的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="8be6b-117">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="8be6b-118">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="8be6b-118">UIAProvider</span></span>](#uiaprovider) | <span data-ttu-id="8be6b-119">返回 Web 视图的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="8be6b-119">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="8be6b-120">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="8be6b-120">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="8be6b-121">用于将从系统接收的 pointerId 转换为 CoreWebView2ExperimentalPointerInfo 的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="8be6b-121">A helper function to convert a pointerId received from the system into a CoreWebView2ExperimentalPointerInfo.</span></span>
[<span data-ttu-id="8be6b-122">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="8be6b-122">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="8be6b-123">如果 eventKind 为 CoreWebView2MouseEventKind 或 CoreWebView2MouseEventKind，则 mouseData 指定滚轮移动量。</span><span class="sxs-lookup"><span data-stu-id="8be6b-123">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="8be6b-124">SendPointerInput</span><span class="sxs-lookup"><span data-stu-id="8be6b-124">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="8be6b-125">SendPointerInput 接受在 CoreWebView2PointerEventKind 中定义的类型的触摸或笔指针输入。</span><span class="sxs-lookup"><span data-stu-id="8be6b-125">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

## <span data-ttu-id="8be6b-126">成员</span><span class="sxs-lookup"><span data-stu-id="8be6b-126">Members</span></span>

#### <span data-ttu-id="8be6b-127">Cursor</span><span class="sxs-lookup"><span data-stu-id="8be6b-127">Cursor</span></span> 

<span data-ttu-id="8be6b-128">Web 视图所认为的当前光标应该是。</span><span class="sxs-lookup"><span data-stu-id="8be6b-128">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="8be6b-129">公共 IntPtr[光标](#cursor)</span><span class="sxs-lookup"><span data-stu-id="8be6b-129">public IntPtr [Cursor](#cursor)</span></span>

<span data-ttu-id="8be6b-130">应使用 SetCursor 设置光标，或在 SetClassLongPtr 的 Web 视图的相应父/祖先 HWND WM_SETCURSOR 中设置光标。</span><span class="sxs-lookup"><span data-stu-id="8be6b-130">The cursor should be set in WM_SETCURSOR through Mouse.SetCursor or set on the corresponding parent/ancestor HWND of the WebView through SetClassLongPtr.</span></span> <span data-ttu-id="8be6b-131">如果你要执行的操作比立即设置光标更多，则可以释放 HCURSOR，以便建议使用 CopyCursor/DestroyCursor 保留你自己的副本。</span><span class="sxs-lookup"><span data-stu-id="8be6b-131">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="8be6b-132">CursorChanged</span><span class="sxs-lookup"><span data-stu-id="8be6b-132">CursorChanged</span></span> 

<span data-ttu-id="8be6b-133">当 Web 视图认为光标应更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="8be6b-133">The event fires when WebView thinks the cursor should be changed.</span></span>

> <span data-ttu-id="8be6b-134">公共事件 EventHandler< 对象 > [CursorChanged](#cursorchanged)</span><span class="sxs-lookup"><span data-stu-id="8be6b-134">public event EventHandler< object > [CursorChanged](#cursorchanged)</span></span>

<span data-ttu-id="8be6b-135">例如，当鼠标光标当前为默认光标，但随后在文本上移动时，它可能会尝试更改为 IBeam 光标。</span><span class="sxs-lookup"><span data-stu-id="8be6b-135">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span>

#### <span data-ttu-id="8be6b-136">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="8be6b-136">RootVisualTarget</span></span> 

<span data-ttu-id="8be6b-137">RootVisualTarget 是托管应用的可视化树中的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="8be6b-137">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="8be6b-138">公共对象[RootVisualTarget](#rootvisualtarget)</span><span class="sxs-lookup"><span data-stu-id="8be6b-138">public object [RootVisualTarget](#rootvisualtarget)</span></span>

<span data-ttu-id="8be6b-139">此视觉对象是 Web 视图将连接其可视化树的位置。</span><span class="sxs-lookup"><span data-stu-id="8be6b-139">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="8be6b-140">应用使用此视觉对象在应用内放置 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="8be6b-140">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="8be6b-141">应用仍需要使用界限属性来调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="8be6b-141">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="8be6b-142">RootVisualTarget 属性可以是 IDCompositionVisual 或 Windows：： UI：：合成：： ContainerVisual。</span><span class="sxs-lookup"><span data-stu-id="8be6b-142">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="8be6b-143">在从属性 setter 返回之前，Web 视图会将其可视化树连接到提供的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="8be6b-143">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="8be6b-144">应用需要在其设备上进行提交设置 RootVisualTarget 属性。</span><span class="sxs-lookup"><span data-stu-id="8be6b-144">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="8be6b-145">RootVisualTarget 属性支持将设置为 nullptr 以断开 Web 视图与应用的可视化树的连接。</span><span class="sxs-lookup"><span data-stu-id="8be6b-145">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span>

#### <span data-ttu-id="8be6b-146">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="8be6b-146">UIAProvider</span></span> 

<span data-ttu-id="8be6b-147">返回 Web 视图的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="8be6b-147">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="8be6b-148">公共对象[UIAProvider](#uiaprovider)</span><span class="sxs-lookup"><span data-stu-id="8be6b-148">public object [UIAProvider](#uiaprovider)</span></span>

#### <span data-ttu-id="8be6b-149">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="8be6b-149">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="8be6b-150">用于将从系统接收的 pointerId 转换为 CoreWebView2ExperimentalPointerInfo 的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="8be6b-150">A helper function to convert a pointerId received from the system into a CoreWebView2ExperimentalPointerInfo.</span></span>

> <span data-ttu-id="8be6b-151">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)（Uint PointerId，IntPtr ParentWindow，Matrix4x4 转换）</span><span class="sxs-lookup"><span data-stu-id="8be6b-151">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(uint PointerId, IntPtr ParentWindow, Matrix4x4 transform)</span></span>

<span data-ttu-id="8be6b-152">parentWindow 是包含 web 视图的 HWND。</span><span class="sxs-lookup"><span data-stu-id="8be6b-152">parentWindow is the HWND that contains the webview.</span></span> <span data-ttu-id="8be6b-153">这可以是 hwnd 树中包含 web 视图的任何 HWND。</span><span class="sxs-lookup"><span data-stu-id="8be6b-153">This can be any HWND in the hwnd tree that contains the webview.</span></span> <span data-ttu-id="8be6b-154">CoreWebView2Matrix4x4 是从该 HWND 到 web 视图的转换。</span><span class="sxs-lookup"><span data-stu-id="8be6b-154">The CoreWebView2Matrix4x4 is the transform from that HWND to the webview.</span></span> <span data-ttu-id="8be6b-155">返回的 CoreWebView2ExperimentalPointerInfo 在 SendPointerInfo 中使用。</span><span class="sxs-lookup"><span data-stu-id="8be6b-155">The returned CoreWebView2ExperimentalPointerInfo is used in SendPointerInfo.</span></span> <span data-ttu-id="8be6b-156">指针类型必须是 "笔" 或 "触摸"，否则函数将失败。</span><span class="sxs-lookup"><span data-stu-id="8be6b-156">The pointer type must be either pen or touch or the function will fail.</span></span>

#### <span data-ttu-id="8be6b-157">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="8be6b-157">SendMouseInput</span></span> 

<span data-ttu-id="8be6b-158">如果 eventKind 为 CoreWebView2MouseEventKind 或 CoreWebView2MouseEventKind，则 mouseData 指定滚轮移动量。</span><span class="sxs-lookup"><span data-stu-id="8be6b-158">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="8be6b-159">public void [SendMouseInput](#sendmouseinput)（[CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind， [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys，uint mouseData，point point）</span><span class="sxs-lookup"><span data-stu-id="8be6b-159">public void [SendMouseInput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind, [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys, uint mouseData, Point point)</span></span>

<span data-ttu-id="8be6b-160">正值表示滑轮向前旋转，远离用户。负值表示滑轮向后旋转，朝向用户。</span><span class="sxs-lookup"><span data-stu-id="8be6b-160">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="8be6b-161">一个滚轮单击定义为 WHEEL_DELTA，即120。</span><span class="sxs-lookup"><span data-stu-id="8be6b-161">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="8be6b-162">如果 eventKind 为 CoreWebView2MouseEventKind 或 XButtonDown，则 CoreWebView2MouseEventKind 指定按下或释放哪些 X 按钮。</span><span class="sxs-lookup"><span data-stu-id="8be6b-162">If eventKind is CoreWebView2MouseEventKind.XButtonDoubleClick CoreWebView2MouseEventKind.XButtonDown, or CoreWebView2MouseEventKind.XButtonUp, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="8be6b-163">如果按下/释放第一个 X 按钮，此值应为1，如果按下/释放第二个 X 按钮，则为2。</span><span class="sxs-lookup"><span data-stu-id="8be6b-163">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="8be6b-164">如果 eventKind 为 CoreWebView2MouseEventKind，则 virtualKeys、mouseData 和 point 均应为零。</span><span class="sxs-lookup"><span data-stu-id="8be6b-164">If eventKind is CoreWebView2MouseEventKind.Leave, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="8be6b-165">如果 eventKind 为任何其他值，则 mouseData 应为零。</span><span class="sxs-lookup"><span data-stu-id="8be6b-165">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="8be6b-166">Point 应位于 Web 视图的工作区坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="8be6b-166">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="8be6b-167">若要跟踪在 Web 视图中启动并可能在 Web 视图和主机应用程序外部移动的鼠标事件，建议使用调用 SetCapture 和 ReleaseCapture。</span><span class="sxs-lookup"><span data-stu-id="8be6b-167">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="8be6b-168">为了消除悬停弹出窗口，还建议发送 WM_MOUSELEAVE 消息。</span><span class="sxs-lookup"><span data-stu-id="8be6b-168">To dismiss hover popups, it is also recommended to send WM_MOUSELEAVE messages.</span></span>

#### <span data-ttu-id="8be6b-169">SendPointerInput</span><span class="sxs-lookup"><span data-stu-id="8be6b-169">SendPointerInput</span></span> 

<span data-ttu-id="8be6b-170">SendPointerInput 接受在 CoreWebView2PointerEventKind 中定义的类型的触摸或笔指针输入。</span><span class="sxs-lookup"><span data-stu-id="8be6b-170">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

> <span data-ttu-id="8be6b-171">公共 void [SendPointerInput](#sendpointerinput)（[CoreWebView2PointerEventKind 事件](./namespace-microsoft-web-webview2-core.md)、 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo）</span><span class="sxs-lookup"><span data-stu-id="8be6b-171">public void [SendPointerInput](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventType, [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo)</span></span>

<span data-ttu-id="8be6b-172">必须首先将系统中的任何指针输入转换为 CoreWebView2ExperimentalPointerInfo。</span><span class="sxs-lookup"><span data-stu-id="8be6b-172">Any pointer input from the system must be converted into a CoreWebView2ExperimentalPointerInfo first.</span></span>

