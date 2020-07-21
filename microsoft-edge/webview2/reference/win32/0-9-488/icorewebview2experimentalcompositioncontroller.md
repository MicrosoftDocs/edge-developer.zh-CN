---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2ExperimentalCompositionController
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: ddb3fce4f3f9799bcfaf8a9aa297c3207392f916
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884538"
---
# 0.9.515-接口 ICoreWebView2ExperimentalCompositionController 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalCompositionController
  : public IUnknown
```

此接口是支持可视化托管的 ICoreWebView2Controller 接口的扩展。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[add_CursorChanged](#add_cursorchanged) | 为 CursorChanged 事件添加事件处理程序。
[CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid) | 用于将从系统接收的 pointerId 转换为[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)的帮助程序函数。
[get_Cursor](#get_cursor) | Web 视图所认为的当前光标应该是。
[get_RootVisualTarget](#get_rootvisualtarget) | RootVisualTarget 是托管应用的可视化树中的视觉对象。
[get_UIAProvider](#get_uiaprovider) | 返回 Web 视图的 UI 自动化提供程序。
[put_RootVisualTarget](#put_rootvisualtarget) | 设置 RootVisualTarget 属性。
[remove_CursorChanged](#remove_cursorchanged) | 删除以前使用 add_CursorChanged 添加的事件处理程序。
[SendMouseInput](#sendmouseinput) | 如果 eventKind 为 COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL 或 COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL，则 mouseData 指定滚轮移动量。
[SendPointerInput](#sendpointerinput) | SendPointerInput 接受在 COREWEBVIEW2_POINTER_EVENT_KIND 中定义的类型的触摸或笔指针输入。
[COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4) | 表示3D 变换的矩阵。
[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) | SendMouseInput 用于传达发送给 Web 视图的鼠标事件类型的鼠标事件类型。
[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) | 与 SendMouseInput 的 COREWEBVIEW2_MOUSE_EVENT_KIND 相关联的鼠标事件虚拟键。
[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind) | SendPointerInput 使用的指针事件类型，用于传达发送到 Web 视图的指针事件的类型。

实现 ICoreWebView2ExperimentalCompositionController 接口的对象也将实现 ICoreWebView2Controller。 调用方应使用 ICoreWebView2Controller 来调整大小、可见性、焦点等，然后使用 ICoreWebView2ExperimentalCompositionController 连接到组合树并提供用于 Web 视图的输入。

## 成员

#### add_CursorChanged 

为 CursorChanged 事件添加事件处理程序。

> public HRESULT [add_CursorChanged](#add_cursorchanged)（[ICoreWebView2ExperimentalCursorChangedEventHandler](icorewebview2experimentalcursorchangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图认为光标应更改时，将引发此事件。 例如，当鼠标光标当前为默认光标，但随后在文本上移动时，它可能会尝试更改为 IBeam 光标。

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

#### CreateCoreWebView2PointerInfoFromPointerId 

用于将从系统接收的 pointerId 转换为[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)的帮助程序函数。

> public HRESULT [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)（UINT POINTERID、HWND parentWindow、struct COREWEBVIEW2_MATRIX_4X4 Transform、 [ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) * * pointerInfo）

parentWindow 是包含 web 视图的 HWND。 这可以是 hwnd 树中包含 web 视图的任何 HWND。 COREWEBVIEW2_MATRIX_4X4 是从该 HWND 到 web 视图的转换。 返回的[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md)在 SendPointerInfo 中使用。 指针类型必须是 "笔" 或 "触摸"，否则函数将失败。



#### get_Cursor 

Web 视图所认为的当前光标应该是。

> 公共 HRESULT [get_Cursor](#get_cursor)（HCURSOR * 游标）

光标应在 WM_SETCURSOR 通过：： SetCursor 设置，或在 Web 视图的相应父/祖先 HWND 上设置：： SetClassLongPtr。 如果你要执行的操作比立即设置光标更多，则可以释放 HCURSOR，以便建议使用 CopyCursor/DestroyCursor 保留你自己的副本。

#### get_RootVisualTarget 

RootVisualTarget 是托管应用的可视化树中的视觉对象。

> 公共 HRESULT [get_RootVisualTarget](#get_rootvisualtarget)（IUnknown * * 目标）

此视觉对象是 Web 视图将连接其可视化树的位置。 应用使用此视觉对象在应用内放置 Web 视图。 应用仍需要使用界限属性来调整 Web 视图的大小。 RootVisualTarget 属性可以是 IDCompositionVisual 或 Windows：： UI：：合成：： ContainerVisual。 在从属性 setter 返回之前，Web 视图会将其可视化树连接到提供的视觉对象。 应用需要在其设备上进行提交设置 RootVisualTarget 属性。 RootVisualTarget 属性支持将设置为 nullptr 以断开 Web 视图与应用的可视化树的连接。 
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

#### get_UIAProvider 

返回 Web 视图的 UI 自动化提供程序。

> 公共 HRESULT [get_UIAProvider](#get_uiaprovider)（IUnknown * * 提供程序）

#### put_RootVisualTarget 

设置 RootVisualTarget 属性。

> 公共 HRESULT [put_RootVisualTarget](#put_rootvisualtarget)（IUnknown * 目标）

#### remove_CursorChanged 

删除以前使用 add_CursorChanged 添加的事件处理程序。

> public HRESULT [remove_CursorChanged](#remove_cursorchanged)（EventRegistrationToken 标记）

#### SendMouseInput 

如果 eventKind 为 COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL 或 COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL，则 mouseData 指定滚轮移动量。

> public HRESULT [SendMouseInput](#sendmouseinput)（[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind) eventKind， [COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys) virtualKeys，UINT32 mouseData，point）

正值表示滑轮向前旋转，远离用户。负值表示滑轮向后旋转，朝向用户。 一个滚轮单击定义为 WHEEL_DELTA，即120。 如果 eventKind 是 COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN 或 COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP，则 mouseData 指定按下或释放哪些 X 按钮。 如果按下/释放第一个 X 按钮，此值应为1，如果按下/释放第二个 X 按钮，则为2。 如果 eventKind 为 COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE，则 virtualKeys、mouseData 和 point 均应为零。 如果 eventKind 为任何其他值，则 mouseData 应为零。 Point 应位于 Web 视图的工作区坐标空间中。 若要跟踪在 Web 视图中启动并可能在 Web 视图和主机应用程序外部移动的鼠标事件，建议使用调用 SetCapture 和 ReleaseCapture。 为了消除悬停弹出窗口，还建议发送 WM_MOUSELEAVE 消息。 
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

#### SendPointerInput 

SendPointerInput 接受在 COREWEBVIEW2_POINTER_EVENT_KIND 中定义的类型的触摸或笔指针输入。

> 公共 HRESULT [SendPointerInput](#sendpointerinput)（[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)事件[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) * pointerInfo）

必须首先将系统中的任何指针输入转换为[ICoreWebView2ExperimentalPointerInfo](icorewebview2experimentalpointerinfo.md) 。

#### COREWEBVIEW2_MATRIX_4X4 

表示3D 变换的矩阵。

> typedef [COREWEBVIEW2_MATRIX_4X4](#corewebview2_matrix_4x4)

此转换用于在调用 CreateCoreWebView2PointerInfoFromPointerId 时计算正确的坐标。 这等效于 D2D1_MATRIX_4X4_F

#### COREWEBVIEW2_MOUSE_EVENT_KIND 

SendMouseInput 用于传达发送给 Web 视图的鼠标事件类型的鼠标事件类型。

> 枚举[COREWEBVIEW2_MOUSE_EVENT_KIND](#corewebview2_mouse_event_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_MOUSE_EVENT_KIND_HORIZONTAL_WHEEL            | 鼠标水平滚轮滚动事件，WM_MOUSEHWHEEL。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOUBLE_CLICK            | 左键双击鼠标事件，WM_LBUTTONDBLCLK "。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_DOWN            | 按下鼠标左键的事件，WM_LBUTTONDOWN。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEFT_BUTTON_UP            | 左键向上鼠标事件，WM_LBUTTONUP。
COREWEBVIEW2_MOUSE_EVENT_KIND_LEAVE            | 鼠标离开事件，WM_MOUSELEAVE。
COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOUBLE_CLICK            | 中间按钮双击鼠标事件，WM_MBUTTONDBLCLK "。
COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_DOWN            | 中间按钮鼠标事件，WM_MBUTTONDOWN。
COREWEBVIEW2_MOUSE_EVENT_KIND_MIDDLE_BUTTON_UP            | 中间按钮鼠标事件，WM_MBUTTONUP。
COREWEBVIEW2_MOUSE_EVENT_KIND_MOVE            | 鼠标移动事件，WM_MOUSEMOVE。
COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOUBLE_CLICK            | 右键按钮双击鼠标事件，WM_RBUTTONDBLCLK "。
COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_DOWN            | 右键按钮按下鼠标事件，WM_RBUTTONDOWN。
COREWEBVIEW2_MOUSE_EVENT_KIND_RIGHT_BUTTON_UP            | 右键按钮鼠标事件，WM_RBUTTONUP。
COREWEBVIEW2_MOUSE_EVENT_KIND_WHEEL            | 鼠标滚轮滚动事件，WM_MOUSEWHEEL。
COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOUBLE_CLICK            | 第一个或第二个 X 按钮双击鼠标事件，WM_XBUTTONDBLCLK "。
COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_DOWN            | 按鼠标事件的第一个或第二个 X 按钮事件，WM_XBUTTONDOWN "。
COREWEBVIEW2_MOUSE_EVENT_KIND_X_BUTTON_UP            | 第一个或第二个 X 按钮上的鼠标事件，WM_XBUTTONUP。

此枚举的值与匹配的 WM_ * 窗口消息对齐。

#### COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS 

与 SendMouseInput 的 COREWEBVIEW2_MOUSE_EVENT_KIND 相关联的鼠标事件虚拟键。

> 枚举[COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS](#corewebview2_mouse_event_virtual_keys)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_NONE            | 未按下任何其他键。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_LEFT_BUTTON            | 按下鼠标左键，MK_LBUTTON。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_RIGHT_BUTTON            | 鼠标右键按下，MK_RBUTTON "。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_SHIFT            | SHIFT 键按下，MK_SHIFT。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_CONTROL            | 按下 CTRL 键，MK_CONTROL "。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_MIDDLE_BUTTON            | 鼠标中键按下，MK_MBUTTON。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON1            | 按下 "第一个 X" 按钮，MK_XBUTTON1 "。
COREWEBVIEW2_MOUSE_EVENT_VIRTUAL_KEYS_X_BUTTON2            | 第二个 X 按钮按下，MK_XBUTTON2。

如果为事件按下多个虚拟键，则这些值可以合并为位标志。 此枚举的值与匹配的 MK_ * 鼠标键对齐。

#### COREWEBVIEW2_POINTER_EVENT_KIND 

SendPointerInput 使用的指针事件类型，用于传达发送到 Web 视图的指针事件的类型。

> 枚举[COREWEBVIEW2_POINTER_EVENT_KIND](#corewebview2_pointer_event_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_POINTER_EVENT_KIND_ACTIVATE            | 对应于 WM_POINTERACTIVATE。
COREWEBVIEW2_POINTER_EVENT_KIND_DOWN            | 对应于 WM_POINTERDOWN。
COREWEBVIEW2_POINTER_EVENT_KIND_ENTER            | 对应于 WM_POINTERENTER。
COREWEBVIEW2_POINTER_EVENT_KIND_LEAVE            | 对应于 WM_POINTERLEAVE。
COREWEBVIEW2_POINTER_EVENT_KIND_UP            | 对应于 WM_POINTERUP。
COREWEBVIEW2_POINTER_EVENT_KIND_UPDATE            | 对应于 WM_POINTERUPDATE。

此枚举的值与匹配的 WM_POINTER * 窗口消息对齐。

