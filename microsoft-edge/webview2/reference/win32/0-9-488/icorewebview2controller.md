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
# interface ICoreWebView2Controller 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2Controller
  : public IUnknown
```

此接口是 CoreWebView2 对象的所有者，并且支持调整大小、显示和隐藏、重点介绍以及与窗口化和合成相关的其他功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[add_AcceleratorKeyPressed](#add_acceleratorkeypressed) | 为 AcceleratorKeyPressed 事件添加事件处理程序。
[add_GotFocus](#add_gotfocus) | 为 GotFocus 事件添加事件处理程序。
[add_LostFocus](#add_lostfocus) | 为 LostFocus 事件添加事件处理程序。
[add_MoveFocusRequested](#add_movefocusrequested) | 为 MoveFocusRequested 事件添加事件处理程序。
[add_ZoomFactorChanged](#add_zoomfactorchanged) | 为 ZoomFactorChanged 事件添加事件处理程序。
[关闭](#close) | 关闭 Web 视图并清理基础浏览器实例。
[get_Bounds](#get_bounds) | Web 视图边界。
[get_CoreWebView2](#get_corewebview2) | 获取与此 CoreWebView2Controller 关联的 CoreWebView2。
[get_IsVisible](#get_isvisible) | IsVisible 属性确定是显示还是隐藏 web 视图。
[get_ParentWindow](#get_parentwindow) | 由此 Web 视图用于呈现内容的应用提供的父窗口。
[get_ZoomFactor](#get_zoomfactor) | Web 视图的缩放系数。
[MoveFocus](#movefocus) | 将焦点移动到 Web 视图中。
[NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged) | 这是与界限分开的通知，告诉 Web 视图其父（或任何上级） HWND 已移动。
[put_Bounds](#put_bounds) | 设置界限属性。
[put_IsVisible](#put_isvisible) | 设置 IsVisible 属性。
[put_ParentWindow](#put_parentwindow) | 设置 Web 视图的父窗口。
[put_ZoomFactor](#put_zoomfactor) | 设置 ZoomFactor 属性。
[remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed) | 删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。
[remove_GotFocus](#remove_gotfocus) | 删除以前使用 add_GotFocus 添加的事件处理程序。
[remove_LostFocus](#remove_lostfocus) | 删除以前使用 add_LostFocus 添加的事件处理程序。
[remove_MoveFocusRequested](#remove_movefocusrequested) | 删除以前使用 add_MoveFocusRequested 添加的事件处理程序。
[remove_ZoomFactorChanged](#remove_zoomfactorchanged) | 删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。
[SetBoundsAndZoomFactor](#setboundsandzoomfactor) | 同时更新边界和 ZoomFactor 属性。

CoreWebView2Controller 拥有 CoreWebView2，如果对 CoreWebView2Controller 的所有引用消失，则将关闭 Web 视图。

## 成员

#### add_AcceleratorKeyPressed 

为 AcceleratorKeyPressed 事件添加事件处理程序。

> public HRESULT [add_AcceleratorKeyPressed](#add_acceleratorkeypressed)（[ICoreWebView2AcceleratorKeyPressedEventHandler](icorewebview2acceleratorkeypressedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图获得焦点时，当按下或释放加速键或键组合时，将激发 AcceleratorKeyPressed。 如果某个键出现以下情况之一，则将其视为一个加速器：

1. 按 Ctrl 或 Alt 当前正在保持，或者

1. 按下的键不会映射到字符。 一些特定的键永远不会被视为加速器，如 Shift。 转义键始终被视为加速键。

通过按住键导致的 Autorepeated 键事件也会引发此事件。 你可以通过检查事件参数 "KeyEventLParam" 或 "PhysicalKeyStatus" 来筛选这些问题。

在窗口模式下，此事件处理程序是同步调用的。 在事件参数或事件处理程序返回之前调用句柄（）之前，浏览器进程将被阻止，并且传出进程间 COM 调用将失败，并显示 RPC_E_CANTCALLOUT_ININPUTSYNCCALL。 但是，所有 CoreWebView2 API 方法都有效。

在无窗口模式下，异步调用事件处理程序。 在调用事件处理程序返回或句柄（）时，将不会访问浏览器，但浏览器进程本身将不会被阻止，并且传出 COM 调用将正常工作。

建议你先调用句柄（TRUE），然后才能知道你希望处理加速键。

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

#### add_GotFocus 

为 GotFocus 事件添加事件处理程序。

> public HRESULT [add_GotFocus](#add_gotfocus)（[ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图获得焦点时，将引发 GotFocus。

#### add_LostFocus 

为 LostFocus 事件添加事件处理程序。

> public HRESULT [add_LostFocus](#add_lostfocus)（[ICoreWebView2FocusChangedEventHandler](icorewebview2focuschangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图失去焦点时，将激发 LostFocus。 在引发 MoveFocusRequested 事件的情况下，当 MoveFocusRequested 事件引发时，焦点仍在 Web 视图上。 只有在应用的 MoveFocusRequested 事件或从 Web 视图中设置焦点的情况下，才会在应用的代码或默认操作时引发丢失焦点。

#### add_MoveFocusRequested 

为 MoveFocusRequested 事件添加事件处理程序。

> public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)（[ICoreWebView2MoveFocusRequestedEventHandler](icorewebview2movefocusrequestedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。 激发此事件时，Web 视图的焦点未发生更改。

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

#### add_ZoomFactorChanged 

为 ZoomFactorChanged 事件添加事件处理程序。

> public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)（[ICoreWebView2ZoomFactorChangedEventHandler](icorewebview2zoomfactorchangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。 由于调用方修改了 ZoomFactor 属性，或者由于用户手动修改缩放，因此可能会激发该事件。 当调用方通过 ZoomFactor 属性对其进行修改时，内部缩放系数将立即更新，并且将不会出现 ZoomFactorChanged 事件。 Web 视图将每个网站的上次使用的缩放系数相关联。 因此，在导航到其他页面时，可以更改缩放系数。 当缩放系数因此而更改时，ZoomFactorChanged 事件将在 ContentLoading 事件后立即触发。

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

#### 关闭 

关闭 Web 视图并清理基础浏览器实例。

> 公共 HRESULT [Close](#close)（）

清理浏览器实例将释放为 Web 视图供电的资源。 如果没有其他 WebViews 使用浏览器实例，则将关闭该浏览器实例。

调用 Close 后，所有方法调用都将失败，事件处理程序将停止触发。 具体说来，当调用 Close 时，Web 视图将释放其对其事件处理程序的引用。

当 CoreWebView2Controller 失去其最终引用且 destructed 时，将隐式调用 Close。 但最佳做法是显式调用 Close 以避免 Web 视图和应用代码之间任何意外的引用循环。 尤其是，如果你在事件处理程序中捕获对 Web 视图的引用，你将在 Web 视图和事件处理程序之间创建引用循环。 调用 Close 将通过释放所有事件处理程序来中断此周期。 但是，为了避免这种情况，最佳做法是在 Web 视图上显式调用 Close，而不捕获对 Web 视图的引用以确保可正确清理 Web 视图。

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

#### get_Bounds 

Web 视图边界。

> public HRESULT [get_Bounds](#get_bounds)（RECT * 界限）

界限相对于父 HWND。 应用有两种方法可以放置 Web 视图：

1. 创建作为 Web 视图父 HWND 的子 HWND。 将此窗口放置在 Web 视图应位于的位置。 在这种情况下，对 Web 视图的 Bound's 左上角（偏移）使用（0，0）。

1. 将应用最顶部的窗口用作 Web 视图父 HWND。 设置 Web 视图的 Bound's 左上角，以便 Web 视图正确地放置在应用中。 绑定的值位于主机的坐标空间中。

#### get_CoreWebView2 

获取与此 CoreWebView2Controller 关联的 CoreWebView2。

> 公共 HRESULT [get_CoreWebView2](#get_corewebview2)（[ICoreWebView2](icorewebview2.md) * * CoreWebView2）

#### get_IsVisible 

IsVisible 属性确定是显示还是隐藏 web 视图。

> public HRESULT [get_IsVisible](#get_isvisible)（BOOL * IsVisible）

如果 IsVisible 设置为 false，则 web 视图将是透明的，不会呈现。 但是，这不会影响包含 web 视图的窗口（传递到 CreateCoreWebView2Controller 的 HWND 参数）。 如果你希望该窗口也消失，除了修改 IsVisible 属性外，还可直接对其调用 ShowWindow。 在最小化或还原顶级窗口时，Web 视图作为子窗口不会收到窗口消息。 出于性能原因，开发人员应在应用窗口最小化时将 Web 视图的 IsVisible 属性设置为 false，并在还原应用窗口时将其设置为 false。 应用窗口可通过在接收 WM_SYSCOMMAND 消息时处理 SC_MINIMIZE 和 SC_RESTORE 命令来执行此操作。

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_controller->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_controller->put_IsVisible(m_isVisible);
}
```

#### get_ParentWindow 

由此 Web 视图用于呈现内容的应用提供的父窗口。

> 公共 HRESULT [get_ParentWindow](#get_parentwindow)（HWND * topLevelWindow）

此 API 最初返回传递到 CreateCoreWebView2Controller 的窗口。

#### get_ZoomFactor 

Web 视图的缩放系数。

> 公共 HRESULT [get_ZoomFactor](#get_zoomfactor)（Double * ZoomFactor）

请注意，更改缩放系数可能会导致 `window.innerWidth/innerHeight` 页面布局和页面布局的更改。 由主机通过调用 ZoomFactor 应用的缩放系数成为 Web 视图的新默认缩放。 此缩放系数在跨导航应用，并且是当用户按 ctrl + 0 时，将在 Web 视图中返回 "缩放系数"。 如果用户更改了缩放系数（从而导致应用收到 ZoomFactorChanged），则该缩放仅适用于当前页面。 任何用户应用的缩放仅适用于当前页面，并且在导航时重置。 不允许指定小于或等于0的 zoomFactor。 Web 视图也具有内部受支持的缩放系数范围。 当指定的缩放系数超出该范围时，它将规范化为在范围内，并且将针对应用的已应用的缩放系数引发 ZoomFactorChanged 事件。 当此范围规范化发生时，ZoomFactor 属性将报告在 ZoomFactor 属性的以前修改期间指定的缩放系数，直到在 web 视图应用标准化的缩放系数后收到 ZoomFactorChanged 事件。

#### MoveFocus 

将焦点移动到 Web 视图中。

> 公共 HRESULT [MoveFocus](#movefocus)（COREWEBVIEW2_MOVE_FOCUS_REASON 原因）

在 Web 视图中托管的页面中，Web 视图将获得焦点，并且焦点将被设置为通信元素。 出于编程原因，焦点设置为以前具有焦点的元素，如果没有以前具有焦点的元素，则设置为默认元素。 出于下一个原因，焦点设置为第一个元素。 对于上一个原因，焦点设置为最后一个元素。 Web 视图还可以通过用户交互获得焦点，例如单击 "在 Web 视图中" 或 "Tab"。 对于 "按 tab 键"，应用可以调用 MoveFocus 和 "下一个" 或 "上一步"，以便在确定 Web 视图是下一个 tabbable 元素时，分别与 tab 和 shift + tab 对齐。 或者，应用可以将 IsDialogMessage 作为其消息循环的一部分进行调用，以允许平台自动处理 tab 键切换。 平台将通过 WS_TABSTOP 旋转所有窗口。 当 Web 视图从 IsDialogMessage 获取焦点时，它将分别在 tab 和 shift + tab 的第一个或最后一个元素上放置焦点。

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

#### NotifyParentWindowPositionChanged 

这是与界限分开的通知，告诉 Web 视图其父（或任何上级） HWND 已移动。

> 公共 HRESULT [NotifyParentWindowPositionChanged](#notifyparentwindowpositionchanged)（）

这是辅助功能和 Web 视图中的某些对话框正常工作所必需的。 
```cpp
    if (message == WM_MOVE || message == WM_MOVING)
    {
        m_controller->NotifyParentWindowPositionChanged();
        return true;
    }
```

#### put_Bounds 

设置界限属性。

> public HRESULT [put_Bounds](#put_bounds)（RECT 界限）

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

#### put_IsVisible 

设置 IsVisible 属性。

> 公共 HRESULT [put_IsVisible](#put_isvisible)（布尔值 IsVisible）

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

#### put_ParentWindow 

设置 Web 视图的父窗口。

> 公共 HRESULT [put_ParentWindow](#put_parentwindow)（HWND topLevelWindow）

这将导致 Web 视图将其窗口重定为新提供的窗口。

#### put_ZoomFactor 

设置 ZoomFactor 属性。

> 公共 HRESULT [put_ZoomFactor](#put_zoomfactor)（double ZoomFactor）

#### remove_AcceleratorKeyPressed 

删除以前使用 add_AcceleratorKeyPressed 添加的事件处理程序。

> public HRESULT [remove_AcceleratorKeyPressed](#remove_acceleratorkeypressed)（EventRegistrationToken 标记）

#### remove_GotFocus 

删除以前使用 add_GotFocus 添加的事件处理程序。

> public HRESULT [remove_GotFocus](#remove_gotfocus)（EventRegistrationToken 标记）

#### remove_LostFocus 

删除以前使用 add_LostFocus 添加的事件处理程序。

> public HRESULT [remove_LostFocus](#remove_lostfocus)（EventRegistrationToken 标记）

#### remove_MoveFocusRequested 

删除以前使用 add_MoveFocusRequested 添加的事件处理程序。

> public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)（EventRegistrationToken 标记）

#### remove_ZoomFactorChanged 

删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。

> public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)（EventRegistrationToken 标记）

#### SetBoundsAndZoomFactor 

同时更新边界和 ZoomFactor 属性。

> 公共 HRESULT [SetBoundsAndZoomFactor](#setboundsandzoomfactor)（RECT 边界，双 zoomFactor）

此操作是主机的视角的原子操作。 从此函数返回后，如果函数成功，则边界和 ZoomFactor 属性均已更新，如果函数失败，则不会更新。 如果边界和 ZoomFactor 均由同一比例（即界限和 ZoomFactor 两倍）进行更新，则页面将不会在 innerWidth/innerHeight 中看到更改，并且 Web 视图将以新的大小呈现内容，而无需中间 renderings。 此函数还可用于通过传入新值和另一个的当前值来更新 ZoomFactor 或界限之一。

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

