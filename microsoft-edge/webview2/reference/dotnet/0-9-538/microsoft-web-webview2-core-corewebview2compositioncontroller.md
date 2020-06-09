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
# CoreWebView2CompositionController 类的 WebView2 

> [!NOTE]
> 这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

此类是 CoreWebView2Controller 类的扩展，用于支持可视化托管。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[Cursor](#cursor) | Web 视图所认为的当前光标应该是。
[CursorChanged](#cursorchanged) | 当 Web 视图认为光标应更改时，将引发此事件。
[RootVisualTarget](#rootvisualtarget) | RootVisualTarget 是托管应用的可视化树中的视觉对象。
[UIAProvider](#uiaprovider) | 返回 Web 视图的 UI 自动化提供程序。
[CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid) | 用于将从系统接收的 pointerId 转换为 CoreWebView2ExperimentalPointerInfo 的帮助程序函数。
[SendMouseInput](#sendmouseinput) | 如果 eventKind 为 CoreWebView2MouseEventKind 或 CoreWebView2MouseEventKind，则 mouseData 指定滚轮移动量。
[SendPointerInput](#sendpointerinput) | SendPointerInput 接受在 CoreWebView2PointerEventKind 中定义的类型的触摸或笔指针输入。

## 成员

#### Cursor 

Web 视图所认为的当前光标应该是。

> 公共 IntPtr[光标](#cursor)

应使用 SetCursor 设置光标，或在 SetClassLongPtr 的 Web 视图的相应父/祖先 HWND WM_SETCURSOR 中设置光标。 如果你要执行的操作比立即设置光标更多，则可以释放 HCURSOR，以便建议使用 CopyCursor/DestroyCursor 保留你自己的副本。

#### CursorChanged 

当 Web 视图认为光标应更改时，将引发此事件。

> 公共事件 EventHandler< 对象 > [CursorChanged](#cursorchanged)

例如，当鼠标光标当前为默认光标，但随后在文本上移动时，它可能会尝试更改为 IBeam 光标。

#### RootVisualTarget 

RootVisualTarget 是托管应用的可视化树中的视觉对象。

> 公共对象[RootVisualTarget](#rootvisualtarget)

此视觉对象是 Web 视图将连接其可视化树的位置。 应用使用此视觉对象在应用内放置 Web 视图。 应用仍需要使用界限属性来调整 Web 视图的大小。 RootVisualTarget 属性可以是 IDCompositionVisual 或 Windows：： UI：：合成：： ContainerVisual。 在从属性 setter 返回之前，Web 视图会将其可视化树连接到提供的视觉对象。 应用需要在其设备上进行提交设置 RootVisualTarget 属性。 RootVisualTarget 属性支持将设置为 nullptr 以断开 Web 视图与应用的可视化树的连接。

#### UIAProvider 

返回 Web 视图的 UI 自动化提供程序。

> 公共对象[UIAProvider](#uiaprovider)

#### CreateCoreWebView2PointerInfoFromPointerId 

用于将从系统接收的 pointerId 转换为 CoreWebView2ExperimentalPointerInfo 的帮助程序函数。

> public [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) [CreateCoreWebView2PointerInfoFromPointerId](#createcorewebview2pointerinfofrompointerid)（Uint PointerId，IntPtr ParentWindow，Matrix4x4 转换）

parentWindow 是包含 web 视图的 HWND。 这可以是 hwnd 树中包含 web 视图的任何 HWND。 CoreWebView2Matrix4x4 是从该 HWND 到 web 视图的转换。 返回的 CoreWebView2ExperimentalPointerInfo 在 SendPointerInfo 中使用。 指针类型必须是 "笔" 或 "触摸"，否则函数将失败。

#### SendMouseInput 

如果 eventKind 为 CoreWebView2MouseEventKind 或 CoreWebView2MouseEventKind，则 mouseData 指定滚轮移动量。

> public void [SendMouseInput](#sendmouseinput)（[CoreWebView2MouseEventKind](./namespace-microsoft-web-webview2-core.md) eventKind， [CoreWebView2MouseEventVirtualKeys](./namespace-microsoft-web-webview2-core.md) virtualKeys，uint mouseData，point point）

正值表示滑轮向前旋转，远离用户。负值表示滑轮向后旋转，朝向用户。 一个滚轮单击定义为 WHEEL_DELTA，即120。 如果 eventKind 为 CoreWebView2MouseEventKind 或 XButtonDown，则 CoreWebView2MouseEventKind 指定按下或释放哪些 X 按钮。 如果按下/释放第一个 X 按钮，此值应为1，如果按下/释放第二个 X 按钮，则为2。 如果 eventKind 为 CoreWebView2MouseEventKind，则 virtualKeys、mouseData 和 point 均应为零。 如果 eventKind 为任何其他值，则 mouseData 应为零。 Point 应位于 Web 视图的工作区坐标空间中。 若要跟踪在 Web 视图中启动并可能在 Web 视图和主机应用程序外部移动的鼠标事件，建议使用调用 SetCapture 和 ReleaseCapture。 为了消除悬停弹出窗口，还建议发送 WM_MOUSELEAVE 消息。

#### SendPointerInput 

SendPointerInput 接受在 CoreWebView2PointerEventKind 中定义的类型的触摸或笔指针输入。

> 公共 void [SendPointerInput](#sendpointerinput)（[CoreWebView2PointerEventKind 事件](./namespace-microsoft-web-webview2-core.md)、 [CoreWebView2PointerInfo](microsoft-web-webview2-core-corewebview2pointerinfo.md) pointerInfo）

必须首先将系统中的任何指针输入转换为 CoreWebView2ExperimentalPointerInfo。

