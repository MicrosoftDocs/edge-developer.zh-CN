---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: Microsoft WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2、浏览器控件、边缘 html、
ms.openlocfilehash: f577cb08bf6029821f9aa3919e73273c82201712
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011647"
---
# Microsoft.Web.WebView2.Core 命名空间 

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[CoreWebView2CapturePreviewImageFormat](#corewebview2capturepreviewimageformat) | CoreWebView2CapturePreview 方法使用的图像格式。
[CoreWebView2KeyEventKind](#corewebview2keyeventkind) | 触发 AcceleratorKeyPressed 事件的键事件的类型。
[CoreWebView2MouseEventKind](#corewebview2mouseeventkind) | SendMouseInput 用于传达发送给 Web 视图的鼠标事件类型的鼠标事件类型。
[CoreWebView2MouseEventVirtualKeys](#corewebview2mouseeventvirtualkeys) | 与 SendMouseInput 的 CoreWebView2MouseEventKind 关联的鼠标事件虚拟键。
[CoreWebView2MoveFocusReason](#corewebview2movefocusreason) | 移动焦点的原因。
[CoreWebView2PermissionKind](#corewebview2permissionkind) | 权限请求的类型。
[CoreWebView2PermissionState](#corewebview2permissionstate) | 对权限请求的响应。
[CoreWebView2PointerEventKind](#corewebview2pointereventkind) | SendPointerInput 使用的指针事件类型，用于传达发送到 Web 视图的指针事件的类型。
[CoreWebView2ProcessFailedKind](#corewebview2processfailedkind) | CoreWebView2ProcessFailedEventHandler 类中使用的进程失败类型。
[CoreWebView2ScriptDialogKind](#corewebview2scriptdialogkind) | CoreWebView2ScriptDialogOpeningEventHandler 类中使用的 JavaScript 对话框类型。
[CoreWebView2WebErrorStatus](#corewebview2weberrorstatus) | Web 导航的错误状态值。
[CoreWebView2WebResourceContext](#corewebview2webresourcecontext) | Web 资源请求上下文的枚举。
CoreWebView2 | WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。
CoreWebView2AcceleratorKeyPressedEventArgs | AcceleratorKeyPressed 事件的事件参数。
CoreWebView2CompositionController | 此类是 CoreWebView2Controller 类的扩展，用于支持可视化托管。
CoreWebView2ContentLoadingEventArgs | ContentLoading 事件的事件参数。
CoreWebView2Controller | 此类是 CoreWebView2 对象的所有者，并且支持调整大小、显示和隐藏、重点介绍以及与窗口化和合成相关的其他功能。
CoreWebView2Deferral | 此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。
CoreWebView2DevToolsProtocolEventReceivedEventArgs | DevToolsProtocolEventReceived 事件的事件参数。
CoreWebView2DevToolsProtocolEventReceiver | 将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。
CoreWebView2Environment | 这表示 WebView2 环境。
CoreWebView2EnvironmentOptions | 用于创建 WebView2 环境的选项。
CoreWebView2HttpHeadersCollectionIterator | HTTP 标头集合的迭代器。
CoreWebView2HttpRequestHeaders | HTTP 请求标头。
CoreWebView2HttpResponseHeaders | HTTP 响应标头。
CoreWebView2MoveFocusRequestedEventArgs | MoveFocusRequested 事件的事件参数。
CoreWebView2NavigationCompletedEventArgs | NavigationCompleted 事件的事件参数。
CoreWebView2NavigationStartingEventArgs | NavigationStarting 事件的事件参数。
CoreWebView2NewWindowRequestedEventArgs | Webview.newwindowrequested 事件的事件参数。
CoreWebView2PermissionRequestedEventArgs | Webview.permissionrequested 事件的事件参数。
CoreWebView2PointerInfo | 这通常表示一个组合的 win32 POINTER_INFO/POINTER_TOUCH_INFO/POINTER_PEN_INFO 对象。
CoreWebView2ProcessFailedEventArgs | ProcessFailed 事件的事件参数。
CoreWebView2ScriptDialogOpeningEventArgs | ScriptDialogOpening 事件的事件参数。
CoreWebView2Settings | 定义启用、禁用或修改 Web 视图功能的属性。
CoreWebView2SourceChangedEventArgs | SourceChanged 事件的事件参数。
CoreWebView2WebMessageReceivedEventArgs | WebMessageReceived 事件的事件参数。
CoreWebView2WebResourceRequest | 与 WebResourceRequested 事件一起使用的 HTTP 请求。
CoreWebView2WebResourceRequestedEventArgs | WebResourceRequested 事件的事件参数。
CoreWebView2WebResourceResponse | 与 WebResourceRequested 事件一起使用的 HTTP 响应。
CoreWebView2WebResourceResponseReceivedEventArgs | WebResourceResponseReceived 事件的事件参数。
CoreWebView2WindowFeatures | Web 视图弹出窗口的窗口功能。
EdgeNotFoundException | 缺少边缘安装时引发的异常。
CoreWebView2Matrix4x4 | 此转换用于在调用 CreateCoreWebView2PointerInfoFromPointerId 时计算正确的坐标。
CoreWebView2PhysicalKeyStatus | 一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。

## 成员

#### CoreWebView2CapturePreviewImageFormat 

CoreWebView2CapturePreview 方法使用的图像格式。

> 枚举 [CoreWebView2CapturePreviewImageFormat](#corewebview2capturepreviewimageformat)

 值                         | 描述
--------------------------------|---------------------------------------------
Png            | PNG 图像格式。
Jpeg            | JPEG 图像格式。

#### CoreWebView2KeyEventKind 

触发 AcceleratorKeyPressed 事件的键事件的类型。

> 枚举 [CoreWebView2KeyEventKind](#corewebview2keyeventkind)

 值                         | 描述
--------------------------------|---------------------------------------------
KeyDown            | 对应于窗口消息 WM_KEYDOWN。
KeyUp            | 对应于窗口消息 WM_KEYUP。
SystemKeyDown            | 对应于窗口消息 WM_SYSKEYDOWN。
SystemKeyUp            | 对应于窗口消息 WM_SYSKEYUP。

#### CoreWebView2MouseEventKind 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

SendMouseInput 用于传达发送给 Web 视图的鼠标事件类型的鼠标事件类型。

> 枚举 [CoreWebView2MouseEventKind](#corewebview2mouseeventkind)

 值                         | 描述
--------------------------------|---------------------------------------------
HorizontalWheel            | 鼠标水平滚轮滚动事件，WM_MOUSEHWHEEL。
LeftButtonDoubleClick            | 左键双击鼠标事件，WM_LBUTTONDBLCLK "。
LeftButtonDown            | 按下鼠标左键的事件，WM_LBUTTONDOWN。
LeftButtonUp            | 左键向上鼠标事件，WM_LBUTTONUP。
离开            | 鼠标离开事件，WM_MOUSELEAVE。
MiddleButtonDoubleClick            | 中间按钮双击鼠标事件，WM_MBUTTONDBLCLK "。
MiddleButtonDown            | 中间按钮鼠标事件，WM_MBUTTONDOWN。
MiddleButtonUp            | 中间按钮鼠标事件，WM_MBUTTONUP。
移动            | 鼠标移动事件，WM_MOUSEMOVE。
RightButtonDoubleClick            | 右键按钮双击鼠标事件，WM_RBUTTONDBLCLK "。
RightButtonDown            | 右键按钮按下鼠标事件，WM_RBUTTONDOWN。
RightButtonUp            | 右键按钮鼠标事件，WM_RBUTTONUP。
滚轮            | 鼠标滚轮滚动事件，WM_MOUSEWHEEL。
XButtonDoubleClick            | 第一个或第二个 X 按钮双击鼠标事件，WM_XBUTTONDBLCLK "。
XButtonDown            | 按鼠标事件的第一个或第二个 X 按钮事件，WM_XBUTTONDOWN "。
XButtonUp            | 第一个或第二个 X 按钮上的鼠标事件，WM_XBUTTONUP。

#### CoreWebView2MouseEventVirtualKeys 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

与 SendMouseInput 的 CoreWebView2MouseEventKind 关联的鼠标事件虚拟键。

> 枚举 [CoreWebView2MouseEventVirtualKeys](#corewebview2mouseeventvirtualkeys)

 值                         | 描述
--------------------------------|---------------------------------------------
无            | 未按下任何其他键。
LeftButton            | 按下鼠标左键，MK_LBUTTON。
RightButton            | 鼠标右键按下，MK_RBUTTON "。
Shift            | SHIFT 键按下，MK_SHIFT。
控件            | 按下 CTRL 键，MK_CONTROL "。
MiddleButton            | 鼠标中键按下，MK_MBUTTON。
XButton1            | 按下 "第一个 X" 按钮，MK_XBUTTON1 "。
XButton2            | 第二个 X 按钮按下，MK_XBUTTON2。

#### CoreWebView2MoveFocusReason 

移动焦点的原因。

> 枚举 [CoreWebView2MoveFocusReason](#corewebview2movefocusreason)

 值                         | 描述
--------------------------------|---------------------------------------------
式            | 将焦点放入 Web 视图中的代码。
下一个            | 由于向前遍历 Tab 遍历，移动焦点。
前一个            | 由于 Tab 向后移动焦点。

#### CoreWebView2PermissionKind 

权限请求的类型。

> 枚举 [CoreWebView2PermissionKind](#corewebview2permissionkind)

 值                         | 描述
--------------------------------|---------------------------------------------
UnknownPermission            | 未知权限。
麦克风            | 捕获音频的权限。
相机            | 捕获视频的权限。
地理位置            | 访问地理位置的权限。
通知            | 发送 web 通知的权限。
OtherSensors            | 访问通用传感器的权限。
ClipboardRead            | 在没有用户手势的情况下读取系统剪贴板的权限。

#### CoreWebView2PermissionState 

对权限请求的响应。

> 枚举 [CoreWebView2PermissionState](#corewebview2permissionstate)

 值                         | 描述
--------------------------------|---------------------------------------------
默认值            | 使用默认的浏览器行为，这通常会提示用户做出决策。
允许            | 授予权限请求。
拒绝            | 拒绝权限请求。

#### CoreWebView2PointerEventKind 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

SendPointerInput 使用的指针事件类型，用于传达发送到 Web 视图的指针事件的类型。

> 枚举 [CoreWebView2PointerEventKind](#corewebview2pointereventkind)

 值                         | 描述
--------------------------------|---------------------------------------------
激活            | 对应于 WM_POINTERACTIVATE。
向下            | 对应于 WM_POINTERDOWN。
Enter            | 对应于 WM_POINTERENTER。
离开            | 对应于 WM_POINTERLEAVE。
向上            | 对应于 WM_POINTERUP。
更新            | 对应于 WM_POINTERUPDATE。

#### CoreWebView2ProcessFailedKind 

CoreWebView2ProcessFailedEventHandler 类中使用的进程失败类型。

> 枚举 [CoreWebView2ProcessFailedKind](#corewebview2processfailedkind)

 值                         | 描述
--------------------------------|---------------------------------------------
BrowserProcessExited            | 指示浏览器进程意外终止。
RenderProcessExited            | 指示呈现进程意外终止。
RenderProcessUnresponsive            | 指示呈现过程变得不响应。

#### CoreWebView2ScriptDialogKind 

CoreWebView2ScriptDialogOpeningEventHandler 类中使用的 JavaScript 对话框类型。

> 枚举 [CoreWebView2ScriptDialogKind](#corewebview2scriptdialogkind)

 值                         | 描述
--------------------------------|---------------------------------------------
警报            | 通过窗口调用的对话框。警报 JavaScript 函数。
“确认”            | 通过窗口调用的对话框。确认 JavaScript 函数。
输入            | 通过窗口调用的对话框。提示 JavaScript 函数。
Beforeunload            | 通过 beforeunload JavaScript 函数调用的对话框。

#### CoreWebView2WebErrorStatus 

Web 导航的错误状态值。

> 枚举 [CoreWebView2WebErrorStatus](#corewebview2weberrorstatus)

 值                         | 描述
--------------------------------|---------------------------------------------
Unknown            | 出现未知错误。
CertificateCommonNameIsIncorrect            | SSL 证书公用名与 web 地址不匹配。
CertificateExpired            | SSL 证书已过期。
ClientCertificateContainsErrors            | SSL 客户端证书包含错误。
CertificateRevoked            | SSL 证书已被吊销。
CertificateIsInvalid            | SSL 证书无效 &ndash; 这可能意味着证书与主机名的公钥 pin 不匹配，证书由不受信任的颁发机构或使用弱标志算法签名，证书声明的 DNS 名称违反了名称约束，证书包含弱密钥，证书的有效期太长，缺少吊销信息或吊销机制、非唯一的主机名、缺少证书透明信息，或者证书被链接到 [旧版 Symantec 根](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)。
ServerUnreachable            | 无法访问主机。
超时            | 连接超时。
ErrorHttpInvalidServerResponse            | 服务器返回了无效或无法识别的响应。
ConnectionAborted            | 连接已中止。
ConnectionReset            | 已重置连接。
断开连接            | 互联网连接已丢失。
CannotConnect            | 无法连接到目标。
HostNameNotResolved            | 无法解析提供的主机名。
OperationCanceled            | 操作已取消。
RedirectFailed            | 请求重定向失败。
UnexpectedError            | 出现意外错误。

#### CoreWebView2WebResourceContext 

Web 资源请求上下文的枚举。

> 枚举 [CoreWebView2WebResourceContext](#corewebview2webresourcecontext)

 值                         | 描述
--------------------------------|---------------------------------------------
全部            | 所有资源。
文档            | 文档资源。
单            | CSS 资源。
图像            | 图像资源。
媒体            | 其他媒体资源（如视频）。
字体            | 字体资源。
脚本            | 脚本资源。
XmlHttpRequest            | XML HTTP 请求。
Last            | 获取 API 通信。
TextTrack            | TextTrack 资源。
EventSource            | EventSource API 通信。
Websocket            | WebSocket API 通信。
部件            | Web 应用清单。
SignedExchange            | 已签名的 HTTP 交换。
Ping            | Ping 请求。
CspViolationReport            | CSP 冲突报告。
Other            | 其他资源。

