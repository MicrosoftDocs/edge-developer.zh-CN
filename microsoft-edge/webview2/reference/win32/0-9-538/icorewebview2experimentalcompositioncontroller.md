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
ms.openlocfilehash: 7ae58e35ccaa66e4a711f8e32e06459eb2208b67
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698454"
---
# <span data-ttu-id="6ac1f-104">interface ICoreWebView2ExperimentalCompositionController</span><span class="sxs-lookup"><span data-stu-id="6ac1f-104">interface ICoreWebView2ExperimentalCompositionController</span></span> 

> [!NOTE]
> <span data-ttu-id="6ac1f-105">这是使用预发行 SDK 版本0.9.538 随附的实验性 API。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-105">This an experimental API that is shipped with our prerelease SDK version 0.9.538.</span></span>

```
interface ICoreWebView2ExperimentalCompositionController
  : public IUnknown
```

<span data-ttu-id="6ac1f-106">此接口是支持可视化托管的 ICoreWebView2Controller 接口的扩展。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-106">This interface is an extension of the ICoreWebView2Controller interface to support visual hosting.</span></span>

## <span data-ttu-id="6ac1f-107">摘要</span><span class="sxs-lookup"><span data-stu-id="6ac1f-107">Summary</span></span>

 <span data-ttu-id="6ac1f-108">成员</span><span class="sxs-lookup"><span data-stu-id="6ac1f-108">Members</span></span>                        | <span data-ttu-id="6ac1f-109">描述</span><span class="sxs-lookup"><span data-stu-id="6ac1f-109">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="6ac1f-110">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="6ac1f-110">add_CursorChanged</span></span>](#add_cursorchanged) | <span data-ttu-id="6ac1f-111">为 CursorChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-111">Add an event handler for the CursorChanged event.</span></span>
[<span data-ttu-id="6ac1f-112">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="6ac1f-112">CreateCoreWebView2PointerInfoFromPointerId</span></span>](#createcorewebview2pointerinfofrompointerid) | <span data-ttu-id="6ac1f-113">用于将从系统接收的 pointerId 转换为[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-113">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>
[<span data-ttu-id="6ac1f-114">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="6ac1f-114">get_Cursor</span></span>](#get_cursor) | <span data-ttu-id="6ac1f-115">Web 视图所认为的当前光标应该是。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-115">The current cursor that WebView thinks it should be.</span></span>
[<span data-ttu-id="6ac1f-116">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="6ac1f-116">get_RootVisualTarget</span></span>](#get_rootvisualtarget) | <span data-ttu-id="6ac1f-117">RootVisualTarget 是托管应用的可视化树中的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-117">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>
[<span data-ttu-id="6ac1f-118">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="6ac1f-118">get_UIAProvider</span></span>](#get_uiaprovider) | <span data-ttu-id="6ac1f-119">返回 Web 视图的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-119">Returns the UI Automation Provider for the WebView.</span></span>
[<span data-ttu-id="6ac1f-120">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="6ac1f-120">put_RootVisualTarget</span></span>](#put_rootvisualtarget) | <span data-ttu-id="6ac1f-121">设置 RootVisualTarget 属性。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-121">Set the RootVisualTarget property.</span></span>
[<span data-ttu-id="6ac1f-122">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="6ac1f-122">remove_CursorChanged</span></span>](#remove_cursorchanged) | <span data-ttu-id="6ac1f-123">删除以前使用 add_CursorChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-123">Remove an event handler previously added with add_CursorChanged.</span></span>
[<span data-ttu-id="6ac1f-124">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="6ac1f-124">SendMouseInput</span></span>](#sendmouseinput) | <span data-ttu-id="6ac1f-125">如果 eventKind 为 COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL 或 COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL，则 mouseData 指定滚轮移动量。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-125">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>
[<span data-ttu-id="6ac1f-126">SendPointerInput</span><span class="sxs-lookup"><span data-stu-id="6ac1f-126">SendPointerInput</span></span>](#sendpointerinput) | <span data-ttu-id="6ac1f-127">SendPointerInput 接受在 COREWEBVIEW2_POINTER_EVENT_KIND 中定义的类型的触摸或笔指针输入。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-127">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>
[<span data-ttu-id="6ac1f-128">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="6ac1f-128">COREWEBVIEW2_MATRIX_4X4</span></span>](#corewebview2_matrix_4x4) | <span data-ttu-id="6ac1f-129">表示3D 变换的矩阵。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-129">Matrix that represents a 3D transform.</span></span>
[<span data-ttu-id="6ac1f-130">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="6ac1f-130">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span>](#corewebview2_mouse_event_kind) | <span data-ttu-id="6ac1f-131">SendMouseInput 用于传达发送给 Web 视图的鼠标事件类型的鼠标事件类型。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-131">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>
[<span data-ttu-id="6ac1f-132">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="6ac1f-132">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span>](#corewebview2_mouse_event_virtual_keys) | <span data-ttu-id="6ac1f-133">与 SendMouseInput 的 COREWEBVIEW2_MOUSE_EVENT_KIND 相关联的鼠标事件虚拟键。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-133">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>
[<span data-ttu-id="6ac1f-134">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="6ac1f-134">COREWEBVIEW2_POINTER_EVENT_KIND</span></span>](#corewebview2_pointer_event_kind) | <span data-ttu-id="6ac1f-135">SendPointerInput 使用的指针事件类型，用于传达发送到 Web 视图的指针事件的类型。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-135">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

<span data-ttu-id="6ac1f-136">实现 ICoreWebView2ExperimentalCompositionController 接口的对象也将实现 ICoreWebView2Controller。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-136">An object implementing the ICoreWebView2ExperimentalCompositionController interface will also implement ICoreWebView2Controller.</span></span> <span data-ttu-id="6ac1f-137">调用方应使用 ICoreWebView2Controller 来调整大小、可见性、焦点等，然后使用 ICoreWebView2ExperimentalCompositionController 连接到组合树并提供用于 Web 视图的输入。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-137">Callers are expected to use ICoreWebView2Controller for resizing, visibility, focus, and so on, and then use ICoreWebView2ExperimentalCompositionController to connect to a composition tree and provide input meant for the WebView.</span></span>

## <span data-ttu-id="6ac1f-138">成员</span><span class="sxs-lookup"><span data-stu-id="6ac1f-138">Members</span></span>

#### <span data-ttu-id="6ac1f-139">add_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="6ac1f-139">add_CursorChanged</span></span> 

<span data-ttu-id="6ac1f-140">为 CursorChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-140">Add an event handler for the CursorChanged event.</span></span>

> <span data-ttu-id="6ac1f-141">public HRESULT [add_CursorChanged](#add_cursorchanged)（[ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-141">public HRESULT [add_CursorChanged](#add_cursorchanged)([ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="6ac1f-142">当 Web 视图认为光标应更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-142">The event fires when WebView thinks the cursor should be changed.</span></span> <span data-ttu-id="6ac1f-143">例如，当鼠标光标当前为默认光标，但随后在文本上移动时，它可能会尝试更改为 IBeam 光标。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-143">For example, when the mouse cursor is currently the default cursor but is then moved over text, it may try to change to the IBeam cursor.</span></span>

```cpp
        // Register a handler for the CursorChanged event.
        CHECK_FAILURE(m_compositionController->add_CursorChanged(
            Callback<ICoreWebView2ExperimentalCursorChangedEventHandler>(
                [this](ICoreWebView2ExperimentalCompositionController* sender,
                       IUnknown* args) -> HRESULT {
                    HCURSOR cursor;
                    CHECK_FAILURE(sender->get_Cursor(&cursor));
                    SetClassLongPtr(m_appWindow->GetMainWindow(), GCLP_HCURSOR, (LONG_PTR)cursor);
                    return S_OK;
                })
                .Get(),
            &m_cursorChangedToken));
```

#### <span data-ttu-id="6ac1f-144">CreateCoreWebView2PointerInfoFromPointerId</span><span class="sxs-lookup"><span data-stu-id="6ac1f-144">CreateCoreWebView2PointerInfoFromPointerId</span></span> 

<span data-ttu-id="6ac1f-145">用于将从系统接收的 pointerId 转换为[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)的帮助程序函数。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-145">A helper function to convert a pointerId received from the system into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md).</span></span>

> <span data-ttu-id="6ac1f-146">public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)（UINT POINTERID、HWND parentWindow、struct COREWEBVIEW2_MATRIX_4X4 Transform、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* \* pointerInfo）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-146">public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)(UINT pointerId, HWND parentWindow, struct COREWEBVIEW2_MATRIX_4X4 transform, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \*\* pointerInfo)</span></span>

<span data-ttu-id="6ac1f-147">parentWindow 是包含 web 视图的 HWND。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-147">parentWindow is the HWND that contains the webview.</span></span> <span data-ttu-id="6ac1f-148">这可以是 hwnd 树中包含 web 视图的任何 HWND。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-148">This can be any HWND in the hwnd tree that contains the webview.</span></span> <span data-ttu-id="6ac1f-149">COREWEBVIEW2_MATRIX_4X4 是从该 HWND 到 web 视图的转换。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-149">The COREWEBVIEW2_MATRIX_4X4 is the transform from that HWND to the webview.</span></span> <span data-ttu-id="6ac1f-150">返回的[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)在 SendPointerInfo 中使用。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-150">The returned [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) is used in SendPointerInfo.</span></span> <span data-ttu-id="6ac1f-151">指针类型必须是 "笔" 或 "触摸"，否则函数将失败。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-151">The pointer type must be either pen or touch or the function will fail.</span></span>



#### <span data-ttu-id="6ac1f-152">get_Cursor</span><span class="sxs-lookup"><span data-stu-id="6ac1f-152">get_Cursor</span></span> 

<span data-ttu-id="6ac1f-153">Web 视图所认为的当前光标应该是。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-153">The current cursor that WebView thinks it should be.</span></span>

> <span data-ttu-id="6ac1f-154">公共 HRESULT [get_Cursor](#get_cursor)（HCURSOR \* 游标）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-154">public HRESULT [get_Cursor](#get_cursor)(HCURSOR \* cursor)</span></span>

<span data-ttu-id="6ac1f-155">光标应在 WM_SETCURSOR 通过：： SetCursor 设置，或在 Web 视图的相应父/祖先 HWND 上设置：： SetClassLongPtr。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-155">The cursor should be set in WM_SETCURSOR through ::SetCursor or set on the corresponding parent/ancestor HWND of the WebView through ::SetClassLongPtr.</span></span> <span data-ttu-id="6ac1f-156">如果你要执行的操作比立即设置光标更多，则可以释放 HCURSOR，以便建议使用 CopyCursor/DestroyCursor 保留你自己的副本。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-156">The HCURSOR can be freed so CopyCursor/DestroyCursor is recommended to keep your own copy if you are doing more than immediately setting the cursor.</span></span>

#### <span data-ttu-id="6ac1f-157">get_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="6ac1f-157">get_RootVisualTarget</span></span> 

<span data-ttu-id="6ac1f-158">RootVisualTarget 是托管应用的可视化树中的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-158">The RootVisualTarget is a visual in the hosting app's visual tree.</span></span>

> <span data-ttu-id="6ac1f-159">公共 HRESULT [get_RootVisualTarget](#get_rootvisualtarget)（IUnknown \* \* 目标）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-159">public HRESULT [get_RootVisualTarget](#get_rootvisualtarget)(IUnknown \*\* target)</span></span>

<span data-ttu-id="6ac1f-160">此视觉对象是 Web 视图将连接其可视化树的位置。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-160">This visual is where the WebView will connect its visual tree.</span></span> <span data-ttu-id="6ac1f-161">应用使用此视觉对象在应用内放置 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-161">The app uses this visual to position the WebView within the app.</span></span> <span data-ttu-id="6ac1f-162">应用仍需要使用界限属性来调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-162">The app still needs to use the Bounds property to size the WebView.</span></span> <span data-ttu-id="6ac1f-163">RootVisualTarget 属性可以是 IDCompositionVisual 或 Windows：： UI：：合成：： ContainerVisual。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-163">The RootVisualTarget property can be an IDCompositionVisual or a Windows::UI::Composition::ContainerVisual.</span></span> <span data-ttu-id="6ac1f-164">在从属性 setter 返回之前，Web 视图会将其可视化树连接到提供的视觉对象。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-164">WebView will connect its visual tree to the provided visual before returning from the property setter.</span></span> <span data-ttu-id="6ac1f-165">应用需要在其设备上进行提交设置 RootVisualTarget 属性。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-165">The app needs to commit on its device setting the RootVisualTarget property.</span></span> <span data-ttu-id="6ac1f-166">RootVisualTarget 属性支持将设置为 nullptr 以断开 Web 视图与应用的可视化树的连接。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-166">The RootVisualTarget property supports being set to nullptr to disconnect the WebView from the app's visual tree.</span></span> 
```cpp
            // Set the host app visual that the WebView will connect its visual
            // tree to.
            BuildDCompTreeUsingVisual();
            CHECK_FAILURE(m_compositionController->put_RootVisualTarget(m_dcompWebViewVisual.get()));
            CHECK_FAILURE(m_dcompDevice->Commit());
```

```cpp
// Create host app visual that the WebView will connect to.
//   - Create a IDCompositionTarget for the host window
//   - Create a visual and set that as the IDCompositionTarget's root
//   - Create another visual and add that to the IDCompositionTarget's root.
//     This visual will be the visual root for the WebView.
void ViewComponent::BuildDCompTreeUsingVisual()
{
    CHECK_FAILURE_BOOL(m_dcompDevice != nullptr);

    if (m_dcompWebViewVisual == nullptr)
    {
        CHECK_FAILURE(m_dcompDevice->CreateTargetForHwnd(
            m_appWindow->GetMainWindow(), TRUE, &m_dcompHwndTarget));
        CHECK_FAILURE(m_dcompDevice->CreateVisual(&m_dcompRootVisual));
        CHECK_FAILURE(m_dcompHwndTarget->SetRoot(m_dcompRootVisual.get()));
        CHECK_FAILURE(m_dcompDevice->CreateVisual(&m_dcompWebViewVisual));
        CHECK_FAILURE(m_dcompRootVisual->AddVisual(m_dcompWebViewVisual.get(), TRUE, nullptr));
    }
}
```

#### <span data-ttu-id="6ac1f-167">get_UIAProvider</span><span class="sxs-lookup"><span data-stu-id="6ac1f-167">get_UIAProvider</span></span> 

<span data-ttu-id="6ac1f-168">返回 Web 视图的 UI 自动化提供程序。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-168">Returns the UI Automation Provider for the WebView.</span></span>

> <span data-ttu-id="6ac1f-169">公共 HRESULT [get_UIAProvider](#get_uiaprovider)（IUnknown \* \* 提供程序）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-169">public HRESULT [get_UIAProvider](#get_uiaprovider)(IUnknown \*\* provider)</span></span>

#### <span data-ttu-id="6ac1f-170">put_RootVisualTarget</span><span class="sxs-lookup"><span data-stu-id="6ac1f-170">put_RootVisualTarget</span></span> 

<span data-ttu-id="6ac1f-171">设置 RootVisualTarget 属性。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-171">Set the RootVisualTarget property.</span></span>

> <span data-ttu-id="6ac1f-172">公共 HRESULT [put_RootVisualTarget](#put_rootvisualtarget)（IUnknown \* 目标）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-172">public HRESULT [put_RootVisualTarget](#put_rootvisualtarget)(IUnknown \* target)</span></span>

#### <span data-ttu-id="6ac1f-173">remove_CursorChanged</span><span class="sxs-lookup"><span data-stu-id="6ac1f-173">remove_CursorChanged</span></span> 

<span data-ttu-id="6ac1f-174">删除以前使用 add_CursorChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-174">Remove an event handler previously added with add_CursorChanged.</span></span>

> <span data-ttu-id="6ac1f-175">public HRESULT [remove_CursorChanged](#remove_cursorchanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-175">public HRESULT [remove_CursorChanged](#remove_cursorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="6ac1f-176">SendMouseInput</span><span class="sxs-lookup"><span data-stu-id="6ac1f-176">SendMouseInput</span></span> 

<span data-ttu-id="6ac1f-177">如果 eventKind 为 COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL 或 COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL，则 mouseData 指定滚轮移动量。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-177">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL or COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL, then mouseData specifies the amount of wheel movement.</span></span>

> <span data-ttu-id="6ac1f-178">public HRESULT [SendMouseInput](#sendmouseinput)（[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventKind， [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) virtualKeys，UINT32 mouseData，point）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-178">public HRESULT [SendMouseInput](#sendmouseinput)([COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventKind, [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) virtualKeys, UINT32 mouseData, POINT point)</span></span>

<span data-ttu-id="6ac1f-179">正值表示滑轮向前旋转，远离用户。负值表示滑轮向后旋转，朝向用户。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-179">A positive value indicates that the wheel was rotated forward, away from the user; a negative value indicates that the wheel was rotated backward, toward the user.</span></span> <span data-ttu-id="6ac1f-180">一个滚轮单击定义为 WHEEL_DELTA，即120。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-180">One wheel click is defined as WHEEL_DELTA, which is 120.</span></span> <span data-ttu-id="6ac1f-181">如果 eventKind 是 COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN 或 COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP，则 mouseData 指定按下或释放哪些 X 按钮。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-181">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN, or COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP, then mouseData specifies which X buttons were pressed or released.</span></span> <span data-ttu-id="6ac1f-182">如果按下/释放第一个 X 按钮，此值应为1，如果按下/释放第二个 X 按钮，则为2。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-182">This value should be 1 if the first X button is pressed/released and 2 if the second X button is pressed/released.</span></span> <span data-ttu-id="6ac1f-183">如果 eventKind 为 COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE，则 virtualKeys、mouseData 和 point 均应为零。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-183">If eventKind is COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE, then virtualKeys, mouseData, and point should all be zero.</span></span> <span data-ttu-id="6ac1f-184">如果 eventKind 为任何其他值，则 mouseData 应为零。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-184">If eventKind is any other value, then mouseData should be zero.</span></span> <span data-ttu-id="6ac1f-185">Point 应位于 Web 视图的工作区坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-185">Point is expected to be in the client coordinate space of the WebView.</span></span> <span data-ttu-id="6ac1f-186">若要跟踪在 Web 视图中启动并可能在 Web 视图和主机应用程序外部移动的鼠标事件，建议使用调用 SetCapture 和 ReleaseCapture。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-186">To track mouse events that start in the WebView and can potentially move outside of the WebView and host application, calling SetCapture and ReleaseCapture is recommended.</span></span> <span data-ttu-id="6ac1f-187">为了消除悬停弹出窗口，还建议发送 WM_MOUSELEAVE 消息。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-187">To dismiss hover popups, it is also recommended to send WM_MOUSELEAVE messages.</span></span> 
```cpp
bool ViewComponent::OnMouseMessage(UINT message, WPARAM wParam, LPARAM lParam)
{
    // Manually relay mouse messages to the WebView
    if (m_dcompDevice || m_wincompHelper)
    {
        POINT point;
        POINTSTOPOINT(point, lParam);
        if (message == WM_MOUSEWHEEL || message == WM_MOUSEHWHEEL)
        {
            // Mouse wheel messages are delivered in screen coordinates.
            // SendMouseInput expects client coordinates for the WebView, so convert
            // the point from screen to client.
            ::ScreenToClient(m_appWindow->GetMainWindow(), &point);
        }
        // Send the message to the WebView if the mouse location is inside the
        // bounds of the WebView, if the message is telling the WebView the
        // mouse has left the client area, or if we are currently capturing
        // mouse events.
        bool isMouseInWebView = PtInRect(&m_webViewBounds, point);
        if (isMouseInWebView || message == WM_MOUSELEAVE || m_isCapturingMouse)
        {
            DWORD mouseData = 0;

            switch (message)
            {
            case WM_MOUSEWHEEL:
            case WM_MOUSEHWHEEL:
                mouseData = GET_WHEEL_DELTA_WPARAM(wParam);
                break;
            case WM_XBUTTONDBLCLK:
            case WM_XBUTTONDOWN:
            case WM_XBUTTONUP:
                mouseData = GET_XBUTTON_WPARAM(wParam);
                break;
            case WM_MOUSEMOVE:
                if (!m_isTrackingMouse)
                {
                    // WebView needs to know when the mouse leaves the client area
                    // so that it can dismiss hover popups. TrackMouseEvent will
                    // provide a notification when the mouse leaves the client area.
                    TrackMouseEvents(TME_LEAVE);
                    m_isTrackingMouse = true;
                }
                break;
            case WM_MOUSELEAVE:
                m_isTrackingMouse = false;
                break;
            }

            // We need to capture the mouse in case the user drags the
            // mouse outside of the window bounds and we still need to send
            // mouse messages to the WebView process. This is useful for
            // scenarios like dragging the scroll bar or panning a map.
            // This is very similar to the Pointer Message case where a
            // press started inside of the WebView.
            if (message == WM_LBUTTONDOWN || message == WM_MBUTTONDOWN ||
                message == WM_RBUTTONDOWN || message == WM_XBUTTONDOWN)
            {
                if (isMouseInWebView && ::GetCapture() != m_appWindow->GetMainWindow())
                {
                    m_isCapturingMouse = true;
                    ::SetCapture(m_appWindow->GetMainWindow());
                }
            }
            else if (message == WM_LBUTTONUP || message == WM_MBUTTONUP ||
                message == WM_RBUTTONUP || message == WM_XBUTTONUP)
            {
                if (::GetCapture() == m_appWindow->GetMainWindow())
                {
                    m_isCapturingMouse = false;
                    ::ReleaseCapture();
                }
            }

            // Adjust the point from app client coordinates to webview client coordinates.
            // WM_MOUSELEAVE messages don't have a point, so don't adjust the point.
            if (message != WM_MOUSELEAVE)
            {
                point.x -= m_webViewBounds.left;
                point.y -= m_webViewBounds.top;
            }

            CHECK_FAILURE(m_compositionController->SendMouseInput(
                static_cast<COREWEBVIEW2_MOUSE_EVENT_KIND>(message),
                static_cast<COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS>(GET_KEYSTATE_WPARAM(wParam)),
                mouseData, point));
            return true;
        }
        else if (message == WM_MOUSEMOVE && m_isTrackingMouse)
        {
            // When the mouse moves outside of the WebView, but still inside the app
            // turn off mouse tracking and send the WebView a leave event.
            m_isTrackingMouse = false;
            TrackMouseEvents(TME_LEAVE | TME_CANCEL);
            OnMouseMessage(WM_MOUSELEAVE, 0, 0);
        }
    }
    return false;
}
```

#### <span data-ttu-id="6ac1f-188">SendPointerInput</span><span class="sxs-lookup"><span data-stu-id="6ac1f-188">SendPointerInput</span></span> 

<span data-ttu-id="6ac1f-189">SendPointerInput 接受在 COREWEBVIEW2_POINTER_EVENT_KIND 中定义的类型的触摸或笔指针输入。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-189">SendPointerInput accepts touch or pen pointer input of types defined in COREWEBVIEW2_POINTER_EVENT_KIND.</span></span>

> <span data-ttu-id="6ac1f-190">公共 HRESULT [SendPointerInput](#sendpointerinput)（[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)事件[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* pointerInfo）</span><span class="sxs-lookup"><span data-stu-id="6ac1f-190">public HRESULT [SendPointerInput](#sendpointerinput)([COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) eventType, [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) \* pointerInfo)</span></span>

<span data-ttu-id="6ac1f-191">必须首先将系统中的任何指针输入转换为[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) 。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-191">Any pointer input from the system must be converted into an [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) first.</span></span>

#### <span data-ttu-id="6ac1f-192">COREWEBVIEW2_MATRIX_4X4</span><span class="sxs-lookup"><span data-stu-id="6ac1f-192">COREWEBVIEW2_MATRIX_4X4</span></span> 

<span data-ttu-id="6ac1f-193">表示3D 变换的矩阵。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-193">Matrix that represents a 3D transform.</span></span>

> <span data-ttu-id="6ac1f-194">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span><span class="sxs-lookup"><span data-stu-id="6ac1f-194">typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)</span></span>

<span data-ttu-id="6ac1f-195">此转换用于在调用 CreateCoreWebView2PointerInfoFromPointerId 时计算正确的坐标。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-195">This transform is used to calculate correct coordinates when calling CreateCoreWebView2PointerInfoFromPointerId.</span></span> <span data-ttu-id="6ac1f-196">这等效于 D2D1_MATRIX_4X4_F</span><span class="sxs-lookup"><span data-stu-id="6ac1f-196">This is equivalent to a D2D1_MATRIX_4X4_F</span></span>

#### <span data-ttu-id="6ac1f-197">COREWEBVIEW2_MOUSE_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="6ac1f-197">COREWEBVIEW2_MOUSE_EVENT_KIND</span></span> 

<span data-ttu-id="6ac1f-198">SendMouseInput 用于传达发送给 Web 视图的鼠标事件类型的鼠标事件类型。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-198">Mouse event type used by SendMouseInput to convey the type of mouse event being sent to WebView.</span></span>

> <span data-ttu-id="6ac1f-199">枚举[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span><span class="sxs-lookup"><span data-stu-id="6ac1f-199">enum [COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)</span></span>

 <span data-ttu-id="6ac1f-200">值</span><span class="sxs-lookup"><span data-stu-id="6ac1f-200">Values</span></span>                         | <span data-ttu-id="6ac1f-201">描述</span><span class="sxs-lookup"><span data-stu-id="6ac1f-201">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="6ac1f-202">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span><span class="sxs-lookup"><span data-stu-id="6ac1f-202">COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL</span></span>            | <span data-ttu-id="6ac1f-203">鼠标水平滚轮滚动事件，WM_MOUSEHWHEEL。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-203">Mouse horizontal wheel scroll event, WM_MOUSEHWHEEL.</span></span>
<span data-ttu-id="6ac1f-204">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="6ac1f-204">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="6ac1f-205">左键双击鼠标事件，WM_LBUTTONDBLCLK "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-205">Left button double click mouse event, WM_LBUTTONDBLCLK.</span></span>
<span data-ttu-id="6ac1f-206">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="6ac1f-206">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN</span></span>            | <span data-ttu-id="6ac1f-207">按下鼠标左键的事件，WM_LBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-207">Left button down mouse event, WM_LBUTTONDOWN.</span></span>
<span data-ttu-id="6ac1f-208">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="6ac1f-208">COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP</span></span>            | <span data-ttu-id="6ac1f-209">左键向上鼠标事件，WM_LBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-209">Left button up mouse event, WM_LBUTTONUP.</span></span>
<span data-ttu-id="6ac1f-210">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="6ac1f-210">COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="6ac1f-211">鼠标离开事件，WM_MOUSELEAVE。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-211">Mouse leave event, WM_MOUSELEAVE.</span></span>
<span data-ttu-id="6ac1f-212">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="6ac1f-212">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="6ac1f-213">中间按钮双击鼠标事件，WM_MBUTTONDBLCLK "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-213">Middle button double click mouse event, WM_MBUTTONDBLCLK.</span></span>
<span data-ttu-id="6ac1f-214">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="6ac1f-214">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN</span></span>            | <span data-ttu-id="6ac1f-215">中间按钮鼠标事件，WM_MBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-215">Middle button down mouse event, WM_MBUTTONDOWN.</span></span>
<span data-ttu-id="6ac1f-216">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="6ac1f-216">COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP</span></span>            | <span data-ttu-id="6ac1f-217">中间按钮鼠标事件，WM_MBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-217">Middle button up mouse event, WM_MBUTTONUP.</span></span>
<span data-ttu-id="6ac1f-218">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span><span class="sxs-lookup"><span data-stu-id="6ac1f-218">COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE</span></span>            | <span data-ttu-id="6ac1f-219">鼠标移动事件，WM_MOUSEMOVE。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-219">Mouse move event, WM_MOUSEMOVE.</span></span>
<span data-ttu-id="6ac1f-220">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="6ac1f-220">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="6ac1f-221">右键按钮双击鼠标事件，WM_RBUTTONDBLCLK "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-221">Right button double click mouse event, WM_RBUTTONDBLCLK.</span></span>
<span data-ttu-id="6ac1f-222">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="6ac1f-222">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN</span></span>            | <span data-ttu-id="6ac1f-223">右键按钮按下鼠标事件，WM_RBUTTONDOWN。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-223">Right button down mouse event, WM_RBUTTONDOWN.</span></span>
<span data-ttu-id="6ac1f-224">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="6ac1f-224">COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP</span></span>            | <span data-ttu-id="6ac1f-225">右键按钮鼠标事件，WM_RBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-225">Right button up mouse event, WM_RBUTTONUP.</span></span>
<span data-ttu-id="6ac1f-226">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span><span class="sxs-lookup"><span data-stu-id="6ac1f-226">COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL</span></span>            | <span data-ttu-id="6ac1f-227">鼠标滚轮滚动事件，WM_MOUSEWHEEL。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-227">Mouse wheel scroll event, WM_MOUSEWHEEL.</span></span>
<span data-ttu-id="6ac1f-228">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span><span class="sxs-lookup"><span data-stu-id="6ac1f-228">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK</span></span>            | <span data-ttu-id="6ac1f-229">第一个或第二个 X 按钮双击鼠标事件，WM_XBUTTONDBLCLK "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-229">First or second X button double click mouse event, WM_XBUTTONDBLCLK.</span></span>
<span data-ttu-id="6ac1f-230">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span><span class="sxs-lookup"><span data-stu-id="6ac1f-230">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN</span></span>            | <span data-ttu-id="6ac1f-231">按鼠标事件的第一个或第二个 X 按钮事件，WM_XBUTTONDOWN "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-231">First or second X button down mouse event, WM_XBUTTONDOWN.</span></span>
<span data-ttu-id="6ac1f-232">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span><span class="sxs-lookup"><span data-stu-id="6ac1f-232">COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP</span></span>            | <span data-ttu-id="6ac1f-233">第一个或第二个 X 按钮上的鼠标事件，WM_XBUTTONUP。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-233">First or second X button up mouse event, WM_XBUTTONUP.</span></span>

<span data-ttu-id="6ac1f-234">此枚举的值与匹配的 WM_ \* 窗口消息对齐。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-234">The values of this enum align with the matching WM_\* window messages.</span></span>

#### <span data-ttu-id="6ac1f-235">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span><span class="sxs-lookup"><span data-stu-id="6ac1f-235">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS</span></span> 

<span data-ttu-id="6ac1f-236">与 SendMouseInput 的 COREWEBVIEW2_MOUSE_EVENT_KIND 相关联的鼠标事件虚拟键。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-236">Mouse event virtual keys associated with a COREWEBVIEW2_MOUSE_EVENT_KIND for SendMouseInput.</span></span>

> <span data-ttu-id="6ac1f-237">枚举[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span><span class="sxs-lookup"><span data-stu-id="6ac1f-237">enum [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)</span></span>

 <span data-ttu-id="6ac1f-238">值</span><span class="sxs-lookup"><span data-stu-id="6ac1f-238">Values</span></span>                         | <span data-ttu-id="6ac1f-239">描述</span><span class="sxs-lookup"><span data-stu-id="6ac1f-239">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="6ac1f-240">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span><span class="sxs-lookup"><span data-stu-id="6ac1f-240">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE</span></span>            | <span data-ttu-id="6ac1f-241">未按下任何其他键。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-241">No additional keys pressed.</span></span>
<span data-ttu-id="6ac1f-242">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="6ac1f-242">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON</span></span>            | <span data-ttu-id="6ac1f-243">按下鼠标左键，MK_LBUTTON。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-243">Left mouse button is down, MK_LBUTTON.</span></span>
<span data-ttu-id="6ac1f-244">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span><span class="sxs-lookup"><span data-stu-id="6ac1f-244">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON</span></span>            | <span data-ttu-id="6ac1f-245">鼠标右键按下，MK_RBUTTON "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-245">Right mouse button is down, MK_RBUTTON.</span></span>
<span data-ttu-id="6ac1f-246">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span><span class="sxs-lookup"><span data-stu-id="6ac1f-246">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT</span></span>            | <span data-ttu-id="6ac1f-247">SHIFT 键按下，MK_SHIFT。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-247">SHIFT key is down, MK_SHIFT.</span></span>
<span data-ttu-id="6ac1f-248">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span><span class="sxs-lookup"><span data-stu-id="6ac1f-248">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL</span></span>            | <span data-ttu-id="6ac1f-249">按下 CTRL 键，MK_CONTROL "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-249">CTRL key is down, MK_CONTROL.</span></span>
<span data-ttu-id="6ac1f-250">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span><span class="sxs-lookup"><span data-stu-id="6ac1f-250">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON</span></span>            | <span data-ttu-id="6ac1f-251">鼠标中键按下，MK_MBUTTON。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-251">Middle mouse button is down, MK_MBUTTON.</span></span>
<span data-ttu-id="6ac1f-252">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span><span class="sxs-lookup"><span data-stu-id="6ac1f-252">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1</span></span>            | <span data-ttu-id="6ac1f-253">按下 "第一个 X" 按钮，MK_XBUTTON1 "。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-253">First X button is down, MK_XBUTTON1.</span></span>
<span data-ttu-id="6ac1f-254">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span><span class="sxs-lookup"><span data-stu-id="6ac1f-254">COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2</span></span>            | <span data-ttu-id="6ac1f-255">第二个 X 按钮按下，MK_XBUTTON2。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-255">Second X button is down, MK_XBUTTON2.</span></span>

<span data-ttu-id="6ac1f-256">如果为事件按下多个虚拟键，则这些值可以合并为位标志。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-256">These values can be combined into a bit flag if more than one virtual key is pressed for the event.</span></span> <span data-ttu-id="6ac1f-257">此枚举的值与匹配的 MK_ \* 鼠标键对齐。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-257">The values of this enum align with the matching MK_\* mouse keys.</span></span>

#### <span data-ttu-id="6ac1f-258">COREWEBVIEW2_POINTER_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="6ac1f-258">COREWEBVIEW2_POINTER_EVENT_KIND</span></span> 

<span data-ttu-id="6ac1f-259">SendPointerInput 使用的指针事件类型，用于传达发送到 Web 视图的指针事件的类型。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-259">Pointer event type used by SendPointerInput to convey the type of pointer event being sent to WebView.</span></span>

> <span data-ttu-id="6ac1f-260">枚举[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span><span class="sxs-lookup"><span data-stu-id="6ac1f-260">enum [COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)</span></span>

 <span data-ttu-id="6ac1f-261">值</span><span class="sxs-lookup"><span data-stu-id="6ac1f-261">Values</span></span>                         | <span data-ttu-id="6ac1f-262">描述</span><span class="sxs-lookup"><span data-stu-id="6ac1f-262">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="6ac1f-263">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span><span class="sxs-lookup"><span data-stu-id="6ac1f-263">COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE</span></span>            | <span data-ttu-id="6ac1f-264">对应于 WM_POINTERACTIVATE。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-264">Corresponds to WM_POINTERACTIVATE.</span></span>
<span data-ttu-id="6ac1f-265">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span><span class="sxs-lookup"><span data-stu-id="6ac1f-265">COREWEBVIEW2_POINTER_EVENT_KIND_DOWN</span></span>            | <span data-ttu-id="6ac1f-266">对应于 WM_POINTERDOWN。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-266">Corresponds to WM_POINTERDOWN.</span></span>
<span data-ttu-id="6ac1f-267">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span><span class="sxs-lookup"><span data-stu-id="6ac1f-267">COREWEBVIEW2_POINTER_EVENT_KIND_ENTER</span></span>            | <span data-ttu-id="6ac1f-268">对应于 WM_POINTERENTER。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-268">Corresponds to WM_POINTERENTER.</span></span>
<span data-ttu-id="6ac1f-269">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span><span class="sxs-lookup"><span data-stu-id="6ac1f-269">COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE</span></span>            | <span data-ttu-id="6ac1f-270">对应于 WM_POINTERLEAVE。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-270">Corresponds to WM_POINTERLEAVE.</span></span>
<span data-ttu-id="6ac1f-271">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span><span class="sxs-lookup"><span data-stu-id="6ac1f-271">COREWEBVIEW2_POINTER_EVENT_KIND_UP</span></span>            | <span data-ttu-id="6ac1f-272">对应于 WM_POINTERUP。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-272">Corresponds to WM_POINTERUP.</span></span>
<span data-ttu-id="6ac1f-273">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span><span class="sxs-lookup"><span data-stu-id="6ac1f-273">COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE</span></span>            | <span data-ttu-id="6ac1f-274">对应于 WM_POINTERUPDATE。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-274">Corresponds to WM_POINTERUPDATE.</span></span>

<span data-ttu-id="6ac1f-275">此枚举的值与匹配的 WM_POINTER \* 窗口消息对齐。</span><span class="sxs-lookup"><span data-stu-id="6ac1f-275">The values of this enum align with the matching WM_POINTER\* window messages.</span></span>

