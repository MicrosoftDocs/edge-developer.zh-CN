---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2CompositionController 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 51c6ebb12130632c5fb08e2992caf6ae83a478b1
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011713"
---
# <span data-ttu-id="5f88e-104">CoreWebView2CompositionController 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="5f88e-104">Microsoft.Web.WebView2.Core.CoreWebView2CompositionController class</span></span> 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

<span data-ttu-id="5f88e-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5f88e-105">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="5f88e-106">程序集： Microsoft.Web.WebView2.Core.dll</span><span class="sxs-lookup"><span data-stu-id="5f88e-106">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="5f88e-107">此类是 CoreWebView2Controller 类的扩展，用于支持可视化托管。</span><span class="sxs-lookup"><span data-stu-id="5f88e-107">This class is an extension of the CoreWebView2Controller class to support visual hosting.</span></span>

## <span data-ttu-id="5f88e-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5f88e-108">Summary</span></span>

 <span data-ttu-id="5f88e-109">成员</span><span class="sxs-lookup"><span data-stu-id="5f88e-109">Members</span></span>                        | <span data-ttu-id="5f88e-110">描述</span><span class="sxs-lookup"><span data-stu-id="5f88e-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5f88e-111">Cursor</span><span class="sxs-lookup"><span data-stu-id="5f88e-111">Cursor</span></span>](#cursor) | <span data-ttu-id="5f88e-112">Web 视图所认为的当前光标应该是。</span><span class="sxs-lookup"><span data-stu-id="5f88e-112">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="5f88e-113">CursorChanged</span><span class="sxs-lookup"><span data-stu-id="5f88e-113">CursorChanged</span></span>](#cursorchanged) | <span data-ttu-id="5f88e-114">当 Web 视图认为光标应更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="5f88e-114">The event fires when WebView thinks the cursor should be changed.</span></span>
[<span data-ttu-id="5f88e-115">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="5f88e-115">RootVisualTarget</span></span>](#rootvisualtarget) | <span data-ttu-id="5f88e-116">RootVisualTarget 是托管应用的可视化树中的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="5f88e-116">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="5f88e-117">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="5f88e-117">UIAProvider</span></span>](#uiaprovider) | <span data-ttu-id="5f88e-118">返回 Web 视图的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f88e-118">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="5f88e-119">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="5f88e-119">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="5f88e-120">用于将从系统接收的 pointerId 转换为 CoreWebView2PointerInfo 的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="5f88e-120">A helper function to convert a pointerId received from the system into a CoreWebView2PointerInfo.</span></span>
[<span data-ttu-id="5f88e-121">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="5f88e-121">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="5f88e-122">如果 eventKind 为 CoreWebView2MouseEventKind 或 CoreWebView2MouseEventKind，则 mouseData 指定滚轮移动量。</span><span class="sxs-lookup"><span data-stu-id="5f88e-122">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="5f88e-123">SendPointerInput</span><span class="sxs-lookup"><span data-stu-id="5f88e-123">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="5f88e-124">SendPointerInput 接受在 CoreWebView2PointerEventKind 中定义的类型的触摸或笔指针输入。</span><span class="sxs-lookup"><span data-stu-id="5f88e-124">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

## <span data-ttu-id="5f88e-125">成员</span><span class="sxs-lookup"><span data-stu-id="5f88e-125">Members</span></span>

#### <span data-ttu-id="5f88e-126">Cursor</span><span class="sxs-lookup"><span data-stu-id="5f88e-126">Cursor</span></span> 

<span data-ttu-id="5f88e-127">Web 视图所认为的当前光标应该是。</span><span class="sxs-lookup"><span data-stu-id="5f88e-127">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="5f88e-128">公共 IntPtr [光标](#cursor)</span><span class="sxs-lookup"><span data-stu-id="5f88e-128">public IntPtr [Cursor](#cursor)</span></span>

<span data-ttu-id="5f88e-129">应使用 SetCursor 设置光标，或在 SetClassLongPtr 的 Web 视图的相应父/祖先 HWND WM_SETCURSOR 中设置光标。</span><span class="sxs-lookup"><span data-stu-id="5f88e-129">The cursor should be set in WM_SETCURSOR through Mouse.SetCursor or set on the corresponding parent/ancestor HWND of the WebView through SetClassLongPtr.</span></span> <span data-ttu-id="5f88e-130">如果你要执行的操作比立即设置光标更多，则可以释放 HCURSOR，以便建议使用 CopyCursor/DestroyCursor 保留你自己的副本。</span><span class="sxs-lookup"><span data-stu-id="5f88e-130">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="5f88e-131">CursorChanged</span><span class="sxs-lookup"><span data-stu-id="5f88e-131">CursorChanged</span></span> 

<span data-ttu-id="5f88e-132">当 Web 视图认为光标应更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="5f88e-132">The event fires when WebView thinks the cursor should be changed.</span></span>

> <span data-ttu-id="5f88e-133">公共事件 EventHandler< 对象 > [CursorChanged](#cursorchanged)</span><span class="sxs-lookup"><span data-stu-id="5f88e-133">public event EventHandler< object > [CursorChanged](#cursorchanged)</span></span>

<span data-ttu-id="5f88e-134">例如，当鼠标光标当前为默认光标，但随后在文本上移动时，它可能会尝试更改为 IBeam 光标。</span><span class="sxs-lookup"><span data-stu-id="5f88e-134">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span> <span data-ttu-id="5f88e-135">开发人员需要使用它来发送 CoreWebView2MouseEventKind。除了 CoreWebView2MouseEventKind 外，还会保留消息 (。通过 SendMouseInput API) 移动消息。</span><span class="sxs-lookup"><span data-stu-id="5f88e-135">It is expected for the developer to send CoreWebView2MouseEventKind.Leave messages (in addition to CoreWebView2MouseEventKind.Move messages) through the SendMouseInput API.</span></span> <span data-ttu-id="5f88e-136">这是为了确保鼠标实际位于用于发送 CursorChanged 事件的 Web 视图内。</span><span class="sxs-lookup"><span data-stu-id="5f88e-136">This is to ensure that the mouse is actually within the WebView that sends out CursorChanged events.</span></span>

#### <span data-ttu-id="5f88e-137">RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="5f88e-137">RootVisualTarget</span></span> 

<span data-ttu-id="5f88e-138">RootVisualTarget 是托管应用的可视化树中的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="5f88e-138">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="5f88e-139">公共对象 [RootVisualTarget](#rootvisualtarget)</span><span class="sxs-lookup"><span data-stu-id="5f88e-139">public object [RootVisualTarget](#rootvisualtarget)</span></span>

<span data-ttu-id="5f88e-140">此视觉对象是 Web 视图将连接其可视化树的位置。</span><span class="sxs-lookup"><span data-stu-id="5f88e-140">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="5f88e-141">应用使用此视觉对象在应用内放置 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="5f88e-141">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="5f88e-142">应用仍需要使用界限属性来调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="5f88e-142">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="5f88e-143">RootVisualTarget 属性可以是 IDCompositionVisual 或 Windows：： UI：：合成：： ContainerVisual。</span><span class="sxs-lookup"><span data-stu-id="5f88e-143">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="5f88e-144">在从属性 setter 返回之前，Web 视图会将其可视化树连接到提供的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="5f88e-144">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="5f88e-145">应用需要在其设备上进行提交设置 RootVisualTarget 属性。</span><span class="sxs-lookup"><span data-stu-id="5f88e-145">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="5f88e-146">RootVisualTarget 属性支持将设置为 nullptr 以断开 Web 视图与应用的可视化树的连接。</span><span class="sxs-lookup"><span data-stu-id="5f88e-146">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span>

#### <span data-ttu-id="5f88e-147">UIAProvider</span><span class="sxs-lookup"><span data-stu-id="5f88e-147">UIAProvider</span></span> 

<span data-ttu-id="5f88e-148">返回 Web 视图的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="5f88e-148">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="5f88e-149">公共对象 [UIAProvider](#uiaprovider)</span><span class="sxs-lookup"><span data-stu-id="5f88e-149">public object [UIAProvider](#uiaprovider)</span></span>

#### <span data-ttu-id="5f88e-150">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="5f88e-150">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="5f88e-151">用于将从系统接收的 pointerId 转换为 CoreWebView2PointerInfo 的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="5f88e-151">A helper function to convert a pointerId received from the system into a CoreWebView2PointerInfo.</span></span>

> <span data-ttu-id="5f88e-152">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid) (Uint PointerId，IntPtr ParentWindow，Matrix4x4 转换) </span><span class="sxs-lookup"><span data-stu-id="5f88e-152">public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(uint PointerId, IntPtr ParentWindow, Matrix4x4 transform)</span></span>

<span data-ttu-id="5f88e-153">parentWindow 是包含 Web 视图的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5f88e-153">parentWindow is the HWND that contains the WebView.</span></span> <span data-ttu-id="5f88e-154">这可以是 hwnd 树中包含 Web 视图的任何 HWND。</span><span class="sxs-lookup"><span data-stu-id="5f88e-154">This can be any HWND in the hwnd tree that contains the WebView.</span></span> <span data-ttu-id="5f88e-155">CoreWebView2Matrix4x4 是从该 HWND 到 Web 视图的转换。</span><span class="sxs-lookup"><span data-stu-id="5f88e-155">The CoreWebView2Matrix4x4 is the transform from that HWND to the WebView.</span></span> <span data-ttu-id="5f88e-156">返回的 CoreWebView2PointerInfo 在 SendPointerInfo 中使用。</span><span class="sxs-lookup"><span data-stu-id="5f88e-156">The returned CoreWebView2PointerInfo is used in SendPointerInfo.</span></span> <span data-ttu-id="5f88e-157">指针类型必须是 "笔" 或 "触摸"，否则函数将失败。</span><span class="sxs-lookup"><span data-stu-id="5f88e-157">The pointer type must be either pen or touch or the function will fail.</span></span>

#### <span data-ttu-id="5f88e-158">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="5f88e-158">SendMouseInput</span></span> 

<span data-ttu-id="5f88e-159">如果 eventKind 为 CoreWebView2MouseEventKind 或 CoreWebView2MouseEventKind，则 mouseData 指定滚轮移动量。</span><span class="sxs-lookup"><span data-stu-id="5f88e-159">If eventKind is CoreWebView2MouseEventKind.HorizontalWheel or CoreWebView2MouseEventKind.Wheel, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="5f88e-160">public void [SendMouseInput](#sendmouseinput) ([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind、 [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys、uint mouseData、point) </span><span class="sxs-lookup"><span data-stu-id="5f88e-160">public void [SendMouseInput](#sendmouseinput)([CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind, [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys, uint mouseData, Point point)</span></span>

<span data-ttu-id="5f88e-161">正值表示滑轮向前旋转，远离用户。负值表示滑轮向后旋转，朝向用户。</span><span class="sxs-lookup"><span data-stu-id="5f88e-161">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="5f88e-162">一个滚轮单击定义为 WHEEL_DELTA，即120。</span><span class="sxs-lookup"><span data-stu-id="5f88e-162">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="5f88e-163">如果 eventKind 为 CoreWebView2MouseEventKind 或 XButtonDown，则 CoreWebView2MouseEventKind 指定按下或释放哪些 X 按钮。</span><span class="sxs-lookup"><span data-stu-id="5f88e-163">If eventKind is CoreWebView2MouseEventKind.XButtonDoubleClick CoreWebView2MouseEventKind.XButtonDown, or CoreWebView2MouseEventKind.XButtonUp, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="5f88e-164">如果按下/释放第一个 X 按钮，此值应为1，如果按下/释放第二个 X 按钮，则为2。</span><span class="sxs-lookup"><span data-stu-id="5f88e-164">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="5f88e-165">如果 eventKind 为 CoreWebView2MouseEventKind，则 virtualKeys、mouseData 和 point 均应为零。</span><span class="sxs-lookup"><span data-stu-id="5f88e-165">If eventKind is CoreWebView2MouseEventKind.Leave, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="5f88e-166">如果 eventKind 为任何其他值，则 mouseData 应为零。</span><span class="sxs-lookup"><span data-stu-id="5f88e-166">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="5f88e-167">Point 应位于 Web 视图的工作区坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="5f88e-167">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="5f88e-168">若要跟踪在 Web 视图中启动并可能在 Web 视图和主机应用程序外部移动的鼠标事件，建议使用调用 SetCapture 和 ReleaseCapture。</span><span class="sxs-lookup"><span data-stu-id="5f88e-168">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="5f88e-169">若要消除悬停弹出窗口，还建议发送 CoreWebView2MouseEventKind。保留消息。</span><span class="sxs-lookup"><span data-stu-id="5f88e-169">To dismiss hover popups, it is also recommended to send CoreWebView2MouseEventKind.Leave messages.</span></span>

#### <span data-ttu-id="5f88e-170">SendPointerInput</span><span class="sxs-lookup"><span data-stu-id="5f88e-170">SendPointerInput</span></span> 

<span data-ttu-id="5f88e-171">SendPointerInput 接受在 CoreWebView2PointerEventKind 中定义的类型的触摸或笔指针输入。</span><span class="sxs-lookup"><span data-stu-id="5f88e-171">SendPointerInput accepts touch or pen pointer input of types defined in CoreWebView2PointerEventKind.</span></span>

> <span data-ttu-id="5f88e-172">public void [SendPointerInput](#sendpointerinput) ([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventKind， [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo) </span><span class="sxs-lookup"><span data-stu-id="5f88e-172">public void [SendPointerInput](#sendpointerinput)([CoreWebView2PointerEventKind](./namespace-microsoft-web-webview2-core.md) eventKind, [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo)</span></span>

<span data-ttu-id="5f88e-173">必须首先将系统中的任何指针输入转换为 CoreWebView2PointerInfo。</span><span class="sxs-lookup"><span data-stu-id="5f88e-173">Any pointer input from the system must be converted into a CoreWebView2PointerInfo first.</span></span>

