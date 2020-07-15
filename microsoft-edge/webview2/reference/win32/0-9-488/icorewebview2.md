---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: e01f0e56c2ec8486a666a72c7e5fb25fd49bd8d9
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880981"
---
# 0.9.515-接口 ICoreWebView2 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2
  : public IUnknown
```

WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged) | ContainsFullScreenElement 属性更改时通知。
[add_ContentLoading](#add_contentloading) | 为 ContentLoading 事件添加事件处理程序。
[add_DocumentTitleChanged](#add_documenttitlechanged) | 为 DocumentTitleChanged 事件添加事件处理程序。
[add_FrameNavigationCompleted](#add_framenavigationcompleted) | 为 FrameNavigationCompleted 事件添加事件处理程序。
[add_FrameNavigationStarting](#add_framenavigationstarting) | 为 FrameNavigationStarting 事件添加事件处理程序。
[add_HistoryChanged](#add_historychanged) | 历史记录更改侦听顶级文档的导航历史记录更改。
[add_NavigationCompleted](#add_navigationcompleted) | 为 NavigationCompleted 事件添加事件处理程序。
[add_NavigationStarting](#add_navigationstarting) | 为 NavigationStarting 事件添加事件处理程序。
[add_NewWindowRequested](#add_newwindowrequested) | 为 Webview.newwindowrequested 事件添加事件处理程序。
[add_PermissionRequested](#add_permissionrequested) | 为 Webview.permissionrequested 事件添加事件处理程序。
[add_ProcessFailed](#add_processfailed) | 为 ProcessFailed 事件添加事件处理程序。
[add_ScriptDialogOpening](#add_scriptdialogopening) | 为 ScriptDialogOpening 事件添加事件处理程序。
[add_SourceChanged](#add_sourcechanged) | Source 属性更改时将触发 SourceChanged。
[add_WebMessageReceived](#add_webmessagereceived) | 当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。
[add_WebResourceRequested](#add_webresourcerequested) | 为 WebResourceRequested 事件添加事件处理程序。
[add_WindowCloseRequested](#add_windowcloserequested) | 为 WindowCloseRequested 事件添加事件处理程序。
[AddHostObjectToScript](#addhostobjecttoscript) | 将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。
[AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated) | 将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。
[AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) | 将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。
[CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod) | 调用异步 DevToolsProtocol 方法。
[CapturePreview](#capturepreview) | 捕获 Web 视图显示的图像。
[ExecuteScript](#executescript) | 从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。
[get_BrowserProcessId](#get_browserprocessid) | 托管 Web 视图的浏览器进程的进程 id。
[get_CanGoBack](#get_cangoback) | 如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。
[get_CanGoForward](#get_cangoforward) | 如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。
[get_ContainsFullScreenElement](#get_containsfullscreenelement) | 指示 Web 视图是否包含全屏 HTML 元素。
[get_DocumentTitle](#get_documenttitle) | 当前顶级文档的标题。
[get_Settings](#get_settings) | [ICoreWebView2Settings](icorewebview2settings.md)对象包含运行的 web 视图的各种可修改设置。
[get_Source](#get_source) | 当前顶级文档的 URI。
[GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver) | 获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。
[GoBack](#goback) | 将 Web 视图导航到导航历史记录中的上一页。
[GoForward](#goforward) | 将 Web 视图导航到导航历史记录中的下一页。
[导航](#navigate) | 导致将顶级文档导航到指定的 URI。
[NavigateToString](#navigatetostring) | 启动作为新文档的源 HTML 的 htmlContent 导航。
[OpenDevToolsWindow](#opendevtoolswindow) | 在 Web 视图中打开当前文档的 DevTools 窗口。
[PostWebMessageAsJson](#postwebmessageasjson) | 将指定的 webMessage 发布到此 Web 视图中的顶级文档。
[PostWebMessageAsString](#postwebmessageasstring) | 这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。
[重载](#reload) | 重新加载当前页面。
[remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged) | 删除以前使用相应的 add_ 事件方法添加的事件处理程序。
[remove_ContentLoading](#remove_contentloading) | 删除以前使用 add_ContentLoading 添加的事件处理程序。
[remove_DocumentTitleChanged](#remove_documenttitlechanged) | 删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。
[remove_FrameNavigationCompleted](#remove_framenavigationcompleted) | 删除以前使用 add_FrameNavigationCompleted 添加的事件处理程序。
[remove_FrameNavigationStarting](#remove_framenavigationstarting) | 删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。
[remove_HistoryChanged](#remove_historychanged) | 删除以前使用 add_HistoryChanged 添加的事件处理程序。
[remove_NavigationCompleted](#remove_navigationcompleted) | 删除以前使用 add_NavigationCompleted 添加的事件处理程序。
[remove_NavigationStarting](#remove_navigationstarting) | 删除以前使用 add_NavigationStarting 添加的事件处理程序。
[remove_NewWindowRequested](#remove_newwindowrequested) | 删除以前使用 add_NewWindowRequested 添加的事件处理程序。
[remove_PermissionRequested](#remove_permissionrequested) | 删除以前使用 add_PermissionRequested 添加的事件处理程序。
[remove_ProcessFailed](#remove_processfailed) | 删除以前使用 add_ProcessFailed 添加的事件处理程序。
[remove_ScriptDialogOpening](#remove_scriptdialogopening) | 删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。
[remove_SourceChanged](#remove_sourcechanged) | 删除以前使用 add_SourceChanged 添加的事件处理程序。
[remove_WebMessageReceived](#remove_webmessagereceived) | 删除以前使用 add_WebMessageReceived 添加的事件处理程序。
[remove_WebResourceRequested](#remove_webresourcerequested) | 删除以前使用 add_WebResourceRequested 添加的事件处理程序。
[remove_WindowCloseRequested](#remove_windowcloserequested) | 删除以前使用 add_WindowCloseRequested 添加的事件处理程序。
[RemoveHostObjectFromScript](#removehostobjectfromscript) | 删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) | 删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。
[RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) | 删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。
[停止](#stop) | 停止所有导航和挂起的资源提取。
[COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format) | ICoreWebView2：： CapturePreview 方法使用的图像格式。
[COREWEBVIEW2_KEY_EVENT_KIND](#corewebview2_key_event_kind) | 触发 AcceleratorKeyPressed 事件的键事件的类型。
[COREWEBVIEW2_MOVE_FOCUS_REASON](#corewebview2_move_focus_reason) | 移动焦点的原因。
[COREWEBVIEW2_PERMISSION_KIND](#corewebview2_permission_kind) | 权限请求的类型。
[COREWEBVIEW2_PERMISSION_STATE](#corewebview2_permission_state) | 对权限请求的响应。
[COREWEBVIEW2_PHYSICAL_KEY_STATUS](#corewebview2_physical_key_status) | 一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。
[COREWEBVIEW2_PROCESS_FAILED_KIND](#corewebview2_process_failed_kind) | ICoreWebView2ProcessFailedEventHandler 接口中使用的进程失败类型。
[COREWEBVIEW2_SCRIPT_DIALOG_KIND](#corewebview2_script_dialog_kind) | ICoreWebView2ScriptDialogOpeningEventHandler 接口中使用的 JavaScript 对话框类型。
[COREWEBVIEW2_WEB_ERROR_STATUS](#corewebview2_web_error_status) | Web 导航的错误状态值。
[COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) | Web 资源请求上下文的枚举。

## 导航事件

导航事件的常规序列为 NavigationStarting、SourceChanged、ContentLoading 和 NavigationCompleted。

![dot-inline-dotgraph-1.png](media/dot-inline-dotgraph-1.png)

请注意，这适用于具有相同的 NavigationId 事件参数的导航事件。 具有不同 NavigationId 事件参数的导航事件可能会重叠。 例如，如果你为其 NavigationStarting 事件启动导航等待，然后开始另一个导航，你将看到第一个导航的 NavigationStarting，后跟第二个导航的 NavigationStarting，然后是第一个导航的 NavigationCompleted 以及第二个导航的所有其余导航事件。 在错误情况下，可能会有也可能不是 ContentLoading 事件，具体取决于导航是否转到错误页面。 在 HTTP 重定向时，一行中将有多个 NavigationStarting 事件，并且第一个事件将设置其 IsRedirect 标志。

若要在 Web 视图中的 subframes 内监视或取消导航，请使用 FrameNavigationStarting。

## 流程模型

WebView2 使用与 Edge web 浏览器相同的进程模型。 用户会话中每个指定的用户数据目录都有一个 Edge 浏览器进程，该进程将为指定用户数据目录的任何 WebView2 调用进程提供服务。 这意味着一个 Edge 浏览器进程可能正在为多个呼叫流程提供服务，并且一个呼叫进程可能正在使用多个 Edge 浏览器进程。

![dot-inline-dotgraph-2.png](media/dot-inline-dotgraph-2.png)

浏览器进程关闭时，将出现一些数量的呈现器进程。 根据需要创建这些类，以在不同的 WebViews 中服务潜在的多个帧。 呈现器进程的数量因网站隔离浏览器功能和呈现在关联的 WebViews 中的独特断开的来源的数量而异。

![dot-inline-dotgraph-3.png](media/dot-inline-dotgraph-3.png)

你可以使用 ProcessFailure 事件对这些浏览器和呈现器进程中的崩溃和挂起做出反应。

你可以使用 Close 方法安全地关闭关联的浏览器和呈现器进程。

## 线程模型

WebView2 必须在 UI 线程上创建。 专门使用消息泵的线程。 所有回调都将在该线程上发生，并且对 Web 视图的调用必须在该线程上完成。 使用来自另一个线程的 Web 视图不安全。

回调包括事件处理程序和完成处理程序按顺序执行。 也就是说，如果你有一个事件处理程序正在运行并开始消息循环，则没有其他事件处理程序或完成回调将开始执行 reentrantly。

## 安全性

在使用 ExecuteScript、PostWebMessageAsJson、PostWebMessageAsString 或任何其他方法将信息发送到 Web 视图之前，请始终检查 Web 视图的 Source 属性。 在导致导航的页面中，Web 视图可能会通过与页面或脚本交互的最终用户导航到另一个页面。 同样，请小心处理 AddScriptToExecuteOnDocumentCreated。 所有将来的导航都将运行此脚本，如果它提供对仅适用于特定来源的信息的访问权限，则任何 HTML 文档都可能具有访问权限。

检查 ExecuteScript 方法调用的结果（WebMessageReceived 事件）时，请始终检查发件人的源或从 Web 视图中的 HTML 文档接收信息的任何其他机制验证 HTML 文档的 URI 是否是你所期望的内容。

构建要发送到 Web 视图的消息时，更喜欢使用 PostWebMessageAsJson 并使用 JSON 库构造 JSON 字符串参数。 这将避免任何潜在的编码信息意外进入 JSON 字符串或脚本并确保任何攻击者控制的输入都不能修改 JSON 消息的其余部分或运行任意脚本。

## 字符串类型

字符串输出参数是 LPWSTR null 终止的字符串。 被调用方使用 CoTaskMemAlloc 分配字符串。 所有权转移到呼叫方，由呼叫方负责使用 CoTaskMemFree 释放内存。

参数中的字符串是 LPCWSTR null 终止的字符串。 调用方确保字符串在同步函数调用期间有效。 如果被调用方需要在函数调用完成后将该值保留到某个点，则被调用方必须分配其自己的字符串值副本。

## URI 和 JSON 分析

各种方法以字符串形式提供或接受 Uri 和 JSON。 请使用你的首选库来分析和生成这些字符串。

如果 WinRT 适用于你的应用，则可以使用 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` 分析或生成 JSON 字符串， `RuntimeClass_Windows_Foundation_Uri` 或者 `IUriRuntimeClassFactory` 分析和生成 uri。 这两个功能都在 Win32 应用中使用。

如果你使用 IUri 和 CreateUri 来分析 Uri，你可能希望使用以下 URI 创建标志使 CreateUri 行为与 Web 视图中的 URI 分析更密切匹配： `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## 调试

打开具有普通快捷方式的 DevTools： `F12` 或 `Ctrl+Shift+I` 。 在 `--auto-open-devtools-for-tabs` 首次创建 Web 视图时，可以使用 command 参数开关让 DevTools 窗口立即打开。 有关如何向浏览器进程提供其他命令行参数，请参阅 CreateCoreWebView2Controller 文档。 签出 LoaderOverride 注册表项，在 CreateCoreWebView2Controller 文档中无需修改你的应用程序，即可试用不同版本的 WebView2。

## 版本控制

在使用特定版本的 SDK 构建你的应用后，你的应用可能会使用已安装的旧版本或更高版本的浏览器二进制文件运行。 在 WebView2 版本1.0.0.0 之前，可能会在更新期间发生中断更改，这些更改将阻止你的 SDK 使用安装的浏览器二进制文件的不同版本。 在版本1.0.0.0 后，SDK 的不同版本可以按照以下最佳做法使用安装的浏览器的不同版本：

若要对 API 进行重大更改，请确保在调用 DLL 导出 CreateCoreWebView2Environment 时和在任何 CoreWebView2 对象上调用 QueryInterface 时检查是否失败。 E_NOINTERFACE 的返回值可指示 SDK 与 Edge 浏览器二进制文件不兼容。

从 QueryInterface 检查失败还将考虑 SDK 比 Edge 浏览器的版本更新的情况，并且你的应用尝试使用 Edge 浏览器不兼容的接口。

当接口不可用时，你可以考虑禁用关联的功能（如果可能），或者向最终用户通知他们需要更新其浏览器。

## 成员

#### add_ContainsFullScreenElementChanged 

ContainsFullScreenElement 属性更改时通知。

> public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)（[ICoreWebView2ContainsFullScreenElementChangedEventHandler](icorewebview2containsfullscreenelementchangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。 例如，当视频元素请求进入全屏时，此事件非常有用。 然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<ICoreWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(
                        sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
                    if (m_containsFullscreenElement)
                    {
                        EnterFullScreen();
                    }
                    else
                    {
                        ExitFullScreen();
                    }
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### add_ContentLoading 

为 ContentLoading 事件添加事件处理程序。

> public HRESULT [add_ContentLoading](#add_contentloading)（[ICoreWebView2ContentLoadingEventHandler](icorewebview2contentloadingeventhandler.md) * eventHandler，EventRegistrationToken * token）

ContentLoading 在加载任何内容之前激发，包括使用 AddScriptToExecuteOnDocumentCreated ContentLoading 添加的脚本在同一页面导航（如通过片段导航或历史记录）发生时不会触发。 这将遵循 NavigationStarting 和 SourceChanged 事件，并在 HistoryChanged 和 NavigationCompleted 事件之前。

#### add_DocumentTitleChanged 

为 DocumentTitleChanged 事件添加事件处理程序。

> public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)（[ICoreWebView2DocumentTitleChangedEventHandler](icorewebview2documenttitlechangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<ICoreWebView2DocumentTitleChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### add_FrameNavigationCompleted 

为 FrameNavigationCompleted 事件添加事件处理程序。

> public HRESULT [add_FrameNavigationCompleted](#add_framenavigationcompleted)（[ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当子框架已完全加载（已激发了 FrameNavigationCompleted）或加载时出错，已停止加载时，将引发事件。

```cpp
    // Register a handler for the FrameNavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    CHECK_FAILURE(m_webView->add_FrameNavigationCompleted(
        Callback<ICoreWebView2NavigationCompletedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    std::wstring error_msg = WebErrorStatusToString(webErrorStatus);
                    MessageBox(nullptr,
                       (std::wstring(L"IFrame navigation failed with the ") +
                         L"give in error " + error_msg).c_str(),
                       L"Navigation Failure", MB_OK);
                    if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_frameNavigationCompletedToken));
```

#### add_FrameNavigationStarting 

为 FrameNavigationStarting 事件添加事件处理程序。

> public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)（[ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。 这也会引发重定向。

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));
        }
        return S_OK;
    }).Get(), &m_frameNavigationStartingToken));
```

#### add_HistoryChanged 

历史记录更改侦听顶级文档的导航历史记录更改。

> public HRESULT [add_HistoryChanged](#add_historychanged)（[ICoreWebView2HistoryChangedEventHandler](icorewebview2historychangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

使用历史记录更改检查 CanGoBack/CanGoForward 值是否已更改。 使用 GoBack/GoForward 时也会触发 HistoryChanged。 HistoryChanged 在 SourceChanged 和 ContentLoading 后激发。 为 HistoryChanged 事件添加事件处理程序。 
```cpp
    // Register a handler for the HistoryChanged event.
    // Update the Back, Forward buttons.
    CHECK_FAILURE(m_webView->add_HistoryChanged(
        Callback<ICoreWebView2HistoryChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);

                return S_OK;
            })
            .Get(),
        &m_historyChangedToken));
```

#### add_NavigationCompleted 

为 NavigationCompleted 事件添加事件处理程序。

> public HRESULT [add_NavigationCompleted](#add_navigationcompleted)（[ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<ICoreWebView2NavigationCompletedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### add_NavigationStarting 

为 NavigationStarting 事件添加事件处理程序。

> public HRESULT [add_NavigationStarting](#add_navigationstarting)（[ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。 这也会引发重定向。

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
        }
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
        return S_OK;
    }).Get(), &m_navigationStartingToken));
```

#### add_NewWindowRequested 

为 Webview.newwindowrequested 事件添加事件处理程序。

> public HRESULT [add_NewWindowRequested](#add_newwindowrequested)（[ICoreWebView2NewWindowRequestedEventHandler](icorewebview2newwindowrequestedeventhandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。 应用可以传递将被视为打开的窗口的目标 web 视图。

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<ICoreWebView2NewWindowRequestedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<ICoreWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));
                AppWindow* newAppWindow;

                newAppWindow = new AppWindow(m_creationModeId, L"");
                newAppWindow->m_isPopupWindow = true;
                newAppWindow->m_onWebViewFirstInitialized = [args, deferral, newAppWindow]() {
                    CHECK_FAILURE(args->put_NewWindow(newAppWindow->m_webView.get()));
                    CHECK_FAILURE(args->put_Handled(TRUE));
                    CHECK_FAILURE(deferral->Complete());
                };

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### add_PermissionRequested 

为 Webview.permissionrequested 事件添加事件处理程序。

> public HRESULT [add_PermissionRequested](#add_permissionrequested)（[ICoreWebView2PermissionRequestedEventHandler](icorewebview2permissionrequestedeventhandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图中的内容请求访问某些权限资源的权限时引发。

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<ICoreWebView2PermissionRequestedEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        COREWEBVIEW2_PERMISSION_KIND kind = COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionKind(&kind));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionKind(kind);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        COREWEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? COREWEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? COREWEBVIEW2_PERMISSION_STATE_DENY
            :                     COREWEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### add_ProcessFailed 

为 ProcessFailed 事件添加事件处理程序。

> public HRESULT [add_ProcessFailed](#add_processfailed)（[ICoreWebView2ProcessFailedEventHandler](icorewebview2processfailedeventhandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图进程意外终止或停止响应时激发。

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<ICoreWebView2ProcessFailedEventHandler>(
            [this](ICoreWebView2* sender,
                ICoreWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        COREWEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser process exited unexpectedly.  Recreate webview?",
                L"Browser process exited",
                MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process has stopped responding.  Recreate webview?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process exited unexpectedly. Reload page?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                CHECK_FAILURE(m_webView->Reload());
            }
        }
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### add_ScriptDialogOpening 

为 ScriptDialogOpening 事件添加事件处理程序。

> public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)（[ICoreWebView2ScriptDialogOpeningEventHandler](icorewebview2scriptdialogopeningeventhandler.md) * eventHandler，EventRegistrationToken * token）

将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。 仅当 ICoreWebView2Settings：： AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发。 ScriptDialogOpening 事件可用于取消对话框或使用自定义对话框替换默认对话框。

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<ICoreWebView2ScriptDialogOpeningEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<ICoreWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            COREWEBVIEW2_SCRIPT_DIALOG_KIND type;
            wil::unique_cotaskmem_string message;
            wil::unique_cotaskmem_string defaultText;

            CHECK_FAILURE(eventArgs->get_Uri(&uri));
            CHECK_FAILURE(eventArgs->get_Kind(&type));
            CHECK_FAILURE(eventArgs->get_Message(&message));
            CHECK_FAILURE(eventArgs->get_DefaultText(&defaultText));

            std::wstring promptString = std::wstring(L"The page at '")
                + uri.get() + L"' says:";
            TextInputDialog dialog(
                m_appWindow->GetMainWindow(),
                L"Script Dialog",
                promptString.c_str(),
                message.get(),
                defaultText.get(),
                /* readonly */ type != COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<ICoreWebView2Deferral> deferral;
            CHECK_FAILURE(args->GetDeferral(&deferral));
            m_completeDeferredDialog = [showDialog, deferral]
            {
                showDialog();
                CHECK_FAILURE(deferral->Complete());
            };
        }
        else
        {
            showDialog();
        }

        return S_OK;
    }).Get(), &m_scriptDialogOpeningToken));
```

#### add_SourceChanged 

Source 属性更改时将触发 SourceChanged。

> public HRESULT [add_SourceChanged](#add_sourcechanged)（[ICoreWebView2SourceChangedEventHandler](icorewebview2sourcechangedeventhandler.md) * eventHandler，EventRegistrationToken * token）

导航到其他网站或片段导航时，将引发 SourceChanged。 对于其他类型的导航（如页面重新加载或 pushState，其 URL 与当前页面相同），不会引发此类导航。 SourceChanged 将在 ContentLoading 之前激发，以便导航到新文档。 为 SourceChanged 事件添加事件处理程序。 
```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### add_WebMessageReceived 

当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。

> public HRESULT [add_WebMessageReceived](#add_webmessagereceived)（[ICoreWebView2WebMessageReceivedEventHandler](icorewebview2webmessagereceivedeventhandler.md) * 处理程序，EventRegistrationToken * token）

PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。

```html
        window.chrome.webview.addEventListener('message', arg => {
            if ("SetColor" in arg.data) {
                document.getElementById("colorable").style.color = arg.data.SetColor;
            }
            if ("WindowBounds" in arg.data) {
                document.getElementById("window-bounds").value = arg.data.WindowBounds;
            }
        });

        function SetTitleText() {
            let titleText = document.getElementById("title-text");
            window.chrome.webview.postMessage(`SetTitleText ${titleText.value}`);
        }
        function GetWindowBounds() {
            window.chrome.webview.postMessage("GetWindowBounds");
        }
```
 调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 的对象参数调用通过此 SetWebMessageReceivedEventHandler 方法设置的[ICoreWebView2WebMessageReceivedEventHandler](icorewebview2webmessagereceivedeventhandler.md) 。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### add_WebResourceRequested 

为 WebResourceRequested 事件添加事件处理程序。

> public HRESULT [add_WebResourceRequested](#add_webresourcerequested)（[ICoreWebView2WebResourceRequestedEventHandler](icorewebview2webresourcerequestedeventhandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。 必须至少添加一个筛选器，才能触发该事件。

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        COREWEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### add_WindowCloseRequested 

为 WindowCloseRequested 事件添加事件处理程序。

> public HRESULT [add_WindowCloseRequested](#add_windowcloserequested)（[ICoreWebView2WindowCloseRequestedEventHandler](icorewebview2windowcloserequestedeventhandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图中请求关闭窗口的内容（如在窗口后）关闭窗口时激发。调用 close。 如果应用程序有意义，则应用应关闭 Web 视图和相关应用窗口。

```cpp
    // Register a handler for the WindowCloseRequested event.
    // This handler will close the app window if it is not the main window.
    CHECK_FAILURE(m_webView->add_WindowCloseRequested(
        Callback<ICoreWebView2WindowCloseRequestedEventHandler>([this](
                                                                    ICoreWebView2* sender,
                                                                    IUnknown* args) {
            if (m_isPopupWindow)
            {
                CloseAppWindow();
            }
            return S_OK;
        }).Get(),
        nullptr));
```

#### AddHostObjectToScript 

将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。

> public HRESULT [AddHostObjectToScript](#addhostobjecttoscript)（LPCWSTR NAME，VARIANT * object）

主机对象通过来公开为主机对象代理 `window.chrome.webview.hostObjects.<name>` 。 主机对象代理承诺并将解析为表示主机对象的对象。 如果应用未添加具有名称的对象，则该承诺将被拒绝。 当 JavaScript 代码访问对象的属性或方法时，承诺将返回，它将解析为属性或方法从主机返回的值，或者在出现错误时被拒绝，例如在对象上没有此类属性或参数无效的情况下被拒绝。 例如，当应用程序代码执行以下操作时：

```
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddHostObjectToScript(L"host_object", &host);
```

Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法：

```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。 远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。 可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。 嵌套数组的支持深度为3。 不支持按引用类型的数组。 VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。 在 JavaScript null 中，未定义映射到 VT_EMPTY。

此外，所有主机对象都公开为 `window.chrome.webview.hostObjects.sync.<name>` 。 此处，主机对象作为同步主机对象代理公开。 这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。 因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.hostObjects.<name>` API。

同步主机对象代理和异步主机对象代理都可以代理相同的主机对象。 一个代理所做的远程更改将反映在同一主机对象的任何其他代理中，无论其他代理和同步还是异步。

虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。 尝试执行此操作将失败，并 HRESULT_FROM_WIN32 （ERROR_POSSIBLE_DEADLOCK）。

主机对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。 作为函数或对象原型一部分的属性或方法在本地运行。 此外，数组中的任何属性或方法 `chrome.webview.hostObjects.options.forceLocalProperties` 也将在本地运行。 这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。 你可以根据需要向此数组添加更多。

有一种方法 `chrome.webview.hostObjects.cleanupSome` 可以最大努力垃圾回收主机对象代理。

宿主对象代理还具有以下可在本地运行的方法：

* applyHostFunction、getHostProperty、setHostProperty：对主机对象执行方法调用、属性获取或属性设置。 如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。 例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。 而 `proxy.applyHostFunction('toString')` `toString` 是在主机代理对象上运行。

* getLocalProperty、setLocalProperty：执行属性 get 或本地设置属性。 你可以使用这些方法强制获取或设置主机对象代理本身的属性，而不是它所表示的主机对象上的属性。 例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从 host 代理对象命名的属性。 但 `proxy.getLocalProperty('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。

* 同步：异步主机对象代理公开同步方法，该方法可为同一主机对象的同步主机对象代理返回承诺。 例如， `chrome.webview.hostObjects.sample.methodCall()` 返回一个异步主机对象代理。 可以 `sync` 改为使用该方法获取同步主机对象代理： `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* 异步：同步主机对象代理公开一个 async 方法，该方法会阻止并返回同一主机对象的异步主机对象代理。 例如， `chrome.webview.hostObjects.sync.sample.methodCall()` 返回同步主机对象代理。 `async`在此块上调用该方法，然后返回同一 host 对象的异步主机对象代理： `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* 然后：异步主机对象代理具有 then 方法。 这使它们能够可等待。 `then` 将返回通过主机对象的表示形式解析的承诺。 如果代理表示 JavaScript 文本，则会在本地返回一个副本。 如果代理表示一个函数，则返回非可等待代理。 如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为主机对象代理返回该对象的副本。

所有其他属性和方法调用（除了上述远程对象代理方法、forceLocalProperties 列表和函数和对象原型上的属性）都是远程运行的。 异步主机对象代理返回表示异步完成远程调用该方法或获取属性的一种承诺。 在远程操作完成后，承诺将解决该操作的结果值。 同步主机对象代理的工作方式类似，但阻止了 JavaScript 执行，并等待远程操作完成。

在异步主机对象代理上设置属性的工作方式略有不同。 Set 将立即返回，返回值为将设置的值。 这是 JavaScript 代理对象的要求。 如果需要异步等待属性设置为 "完成"，请使用 setHostProperty 方法，该方法将返回上述承诺。 同步对象属性 set 属性在设置该属性之前同步地阻止。

例如，假设你有一个具有以下接口的 COM 对象

```idl
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IHostObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        [propget] HRESULT IndexedProperty(INT index, [out, retval] BSTR * stringResult);
        [propput] HRESULT IndexedProperty(INT index, [in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);

    };
```
 我们可以将此接口的实例添加到我们的 JavaScript 中 `AddHostObjectToScript` 。 在这种情况下，我们将其命名 `sample` 为：

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_hostObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddHostObjectToScript multiple times in a row without
            // calling RemoveHostObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(
                m_webView->AddHostObjectToScript(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```
 然后，在 HTML 文档中，我们可以通过以下方式使用该 COM 对象 `chrome.webview.hostObjects.sample` ：

```html
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
        const propertyValue = await chrome.webview.hostObjects.sample.property;
        document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
        const propertyValue = chrome.webview.hostObjects.sync.sample.property;
        document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
        const propertyValue = document.getElementById("setPropertyAsyncInput").value;
        // The following line will work but it will return immediately before the property value has actually been set.
        // If you need to set the property and wait for the property to change value, use the setRemote function.
        chrome.webview.hostObjects.sample.property = propertyValue;
        document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
        const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
        // If you care about waiting until the property has actually changed value use the setRemote function.
        await chrome.webview.hostObjects.sample.setRemote("property", propertyValue);
        document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
        const propertyValue = document.getElementById("setPropertySyncInput").value;
        chrome.webview.hostObjects.sync.sample.property = propertyValue;
        document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("getIndexedPropertyAsyncButton").addEventListener("click", async () => {
        const index = parseInt(document.getElementById("getIndexedPropertyAsyncParam").value);
        const resultValue = await chrome.webview.hostObjects.sample.IndexedProperty[index];
        document.getElementById("getIndexedPropertyAsyncOutput").textContent = resultValue;
        });
        document.getElementById("setIndexedPropertyAsyncButton").addEventListener("click", async () => {
        const index = parseInt(document.getElementById("setIndexedPropertyAsyncParam1").value);
        const value = document.getElementById("setIndexedPropertyAsyncParam2").value;;
        chrome.webview.hostObjects.sample.IndexedProperty[index] = value;
        document.getElementById("setIndexedPropertyAsyncOutput").textContent = "Set";
        });
        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
        const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
        const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
        const resultValue = await chrome.webview.hostObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
        document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
        const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
        const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
        const resultValue = chrome.webview.hostObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
        document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
        chrome.webview.hostObjects.sample.CallCallbackAsynchronously(() => {
        document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
        });
        });
```

#### AddScriptToExecuteOnDocumentCreated 

将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。

> 公共 HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)（LPCWSTR JavaScript， [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md) * 处理程序）

插入的脚本将应用于所有未来的顶级文档和子框架导航，直到使用 RemoveScriptToExecuteOnDocumentCreated 删除。 这是异步应用的，你必须等待完成处理程序运行，然后才能确保脚本已准备好在将来的导航上执行。

请注意，如果 HTML 文档通过[沙盒](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#attr-sandbox)属性或[内容安全策略 HTTP 标头](https://developer.mozilla.org/en-US/docs/Web/HTTP/Headers/Content-Security-Policy)进行了某种类型的沙盒，则会影响在此处运行脚本。 例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。

```cpp
// Prompt the user for some script and register it to execute whenever a new page loads.
void ScriptComponent::AddInitializeScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Add Initialize Script",
        L"Initialization Script:",
        L"Enter the JavaScript code to run as the initialization script that "
            L"runs before any script in the HTML document.",
    // This example script stops child frames from opening new windows.  Because
    // the initialization script runs before any script in the HTML document, we
    // can trust the results of our checks on window.parent and window.top.
        L"if (window.parent !== window.top) {\r\n"
        L"    delete window.open;\r\n"
        L"}");
    if (dialog.confirmed)
    {
        m_webView->AddScriptToExecuteOnDocumentCreated(
            dialog.input.c_str(),
            Callback<ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### AddWebResourceRequestedFilter 

将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。

> 公共 HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（LPCWSTR const uri， [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext）

URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。 nullptr 等效于 L ""。 有关资源上下文筛选器的说明，请参阅 COREWEBVIEW2_WEB_RESOURCE_CONTEXT enum。

#### CallDevToolsProtocolMethod 

调用异步 DevToolsProtocol 方法。

> 公共 HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)（LPCWSTR 方法，LPCWSTR ParametersAsJson， [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](icorewebview2calldevtoolsprotocolmethodcompletedhandler.md) * 处理程序）

有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。 "方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。 ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。 当方法异步完成时，将调用处理程序的 Invoke 方法。 将使用方法的返回对象作为 JSON 字符串调用调用。

```cpp
// Prompt the user for the name and parameters of a CDP method, then call it.
void ScriptComponent::CallCdpMethod()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Call CDP Method",
        L"CDP method name:",
        L"Enter the CDP method name to call, followed by a space,\r\n"
            L"followed by the parameters in JSON format.",
        L"Runtime.evaluate {\"expression\":\"alert(\\\"test\\\")\"}");
    if (dialog.confirmed)
    {
        size_t delimiterPos = dialog.input.find(L' ');
        std::wstring methodName = dialog.input.substr(0, delimiterPos);
        std::wstring methodParams =
            (delimiterPos < dialog.input.size()
                ? dialog.input.substr(delimiterPos + 1)
                : L"{}");

        m_webView->CallDevToolsProtocolMethod(
            methodName.c_str(),
            methodParams.c_str(),
            Callback<ICoreWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### CapturePreview 

捕获 Web 视图显示的图像。

> public HRESULT [CapturePreview](#capturepreview)（[COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format) ImageFormat、IStream * imageStream、 [ICoreWebView2CapturePreviewCompletedHandler](icorewebview2capturepreviewcompletedhandler.md) * 处理程序）

指定具有 imageFormat 参数的图像的格式。 生成的图像二进制数据将写入所提供的 imageStream 参数。 当 CapturePreview 完成写入流时，将调用所提供的处理程序参数上的 Invoke 方法。

```cpp
// Show the user a file selection dialog, then save a screenshot of the WebView
// to the selected file.
void FileComponent::SaveScreenshot()
{
    OPENFILENAME openFileName = {};
    openFileName.lStructSize = sizeof(openFileName);
    openFileName.hwndOwner = nullptr;
    openFileName.hInstance = nullptr;
    WCHAR fileName[MAX_PATH] = L"WebView2_Screenshot.png";
    openFileName.lpstrFile = fileName;
    openFileName.lpstrFilter = L"PNG File\0*.png\0";
    openFileName.nMaxFile = ARRAYSIZE(fileName);
    openFileName.Flags = OFN_OVERWRITEPROMPT;

    if (GetSaveFileName(&openFileName))
    {
        wil::com_ptr<IStream> stream;
        CHECK_FAILURE(SHCreateStreamOnFileEx(
            fileName, STGM_READWRITE | STGM_CREATE, FILE_ATTRIBUTE_NORMAL, TRUE, nullptr,
            &stream));

        HWND mainWindow = m_appWindow->GetMainWindow();

        CHECK_FAILURE(m_webView->CapturePreview(
            COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<ICoreWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### ExecuteScript 

从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。

> 公共 HRESULT [ExecuteScript](#executescript)（LPCWSTR JavaScript， [ICoreWebView2ExecuteScriptCompletedHandler](icorewebview2executescriptcompletedhandler.md) * 处理程序）

这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。 结果值是一个 JSON 编码的字符串。 如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。 请注意，没有显式返回值的函数将返回 undefined。 如果执行的脚本引发了未处理的异常，则结果也为 "null"。 此方法是异步应用的。 如果在导航过程中 NavigationStarting 事件后调用该方法，则会在加载新文档时在新文档中执行该脚本，同时引发 ContentLoading。 即使 IsScriptEnabled 设置为 FALSE，ExecuteScript 仍可正常工作。

```cpp
// Prompt the user for some script and then execute it.
void ScriptComponent::InjectScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Inject Script",
        L"Enter script code:",
        L"Enter the JavaScript code to run in the webview.",
        L"window.getComputedStyle(document.body).backgroundColor");
    if (dialog.confirmed)
    {
        m_webView->ExecuteScript(dialog.input.c_str(),
            Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
                [](HRESULT error, PCWSTR result) -> HRESULT
        {
            if (error != S_OK) {
                ShowFailure(error, L"ExecuteScript failed");
            }
            MessageBox(nullptr, result, L"ExecuteScript Result", MB_OK);
            return S_OK;
        }).Get());
    }
}
```

#### get_BrowserProcessId 

托管 Web 视图的浏览器进程的进程 id。

> 公共 HRESULT [get_BrowserProcessId](#get_browserprocessid)（UINT32 * 值）

#### get_CanGoBack 

如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。

> public HRESULT [get_CanGoBack](#get_cangoback)（BOOL * CanGoBack）

如果 CanGoBack 更改值，将引发 HistoryChanged 事件。

#### get_CanGoForward 

如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。

> public HRESULT [get_CanGoForward](#get_cangoforward)（BOOL * CanGoForward）

如果 CanGoForward 更改值，将引发 HistoryChanged 事件。

#### get_ContainsFullScreenElement 

指示 Web 视图是否包含全屏 HTML 元素。

> public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)（BOOL * ContainsFullScreenElement）

#### get_DocumentTitle 

当前顶级文档的标题。

> 公共 HRESULT [get_DocumentTitle](#get_documenttitle)（LPWSTR * 标题）

如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。

#### get_Settings 

[ICoreWebView2Settings](icorewebview2settings.md)对象包含运行的 web 视图的各种可修改设置。

> 公共 HRESULT [get_Settings](#get_settings)（[ICoreWebView2Settings](icorewebview2settings.md) * * 设置）

#### get_Source 

当前顶级文档的 URI。

> 公共 HRESULT [get_Source](#get_source)（LPWSTR * uri）

在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 SourceChanged 事件的一部分。 它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### GetDevToolsProtocolEventReceiver 

获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。

> public HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)（LPCWSTR 名称 = [ICoreWebView2DevToolsProtocolEventReceiver](icorewebview2devtoolsprotocoleventreceiver.md) * * 接收器）

事件名称参数是该事件的格式的完整名称 `{domain}.{event}` 。 有关 DevTools 协议事件描述和事件参数的列表，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### GoBack 

将 Web 视图导航到导航历史记录中的上一页。

> 公共 HRESULT [GoBack](#goback)（）

#### GoForward 

将 Web 视图导航到导航历史记录中的下一页。

> 公共 HRESULT [GoForward](#goforward)（）

#### 导航 

导致将顶级文档导航到指定的 URI。

> 公共 HRESULT[导航](#navigate)（LPCWSTR uri）

有关详细信息，请参阅导航事件。 请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。

```cpp
void ControlComponent::NavigateToAddressBar()
{
    int length = GetWindowTextLength(m_toolbar->addressBarWindow);
    std::wstring uri(length, 0);
    PWSTR buffer = const_cast<PWSTR>(uri.data());
    GetWindowText(m_toolbar->addressBarWindow, buffer, length + 1);

    HRESULT hr = m_webView->Navigate(uri.c_str());
    if (hr == E_INVALIDARG)
    {
        // An invalid URI was provided.
        if (uri.find(L' ') == std::wstring::npos
            && uri.find(L'.') != std::wstring::npos)
        {
            // If it contains a dot and no spaces, try tacking http:// on the front.
            hr = m_webView->Navigate((L"http://" + uri).c_str());
        }
        else
        {
            // Otherwise treat it as a web search. We aren't bothering to escape
            // URL syntax characters such as & and #
            hr = m_webView->Navigate((L"https://bing.com/search?q=" + uri).c_str());
        }
    }
    if (hr != E_INVALIDARG) {
        CHECK_FAILURE(hr);
    }
}
```

#### NavigateToString 

启动作为新文档的源 HTML 的 htmlContent 导航。

> 公共 HRESULT [NavigateToString](#navigatetostring)（LPCWSTR htmlContent）

HtmlContent 参数不能大于 2 MB 的字符。 新页面的来源将显示为 "空白"。

```cpp
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### OpenDevToolsWindow 

在 Web 视图中打开当前文档的 DevTools 窗口。

> 公共 HRESULT [OpenDevToolsWindow](#opendevtoolswindow)（）

如果在 DevTools 窗口已打开时调用，则不执行任何操作

#### PostWebMessageAsJson 

将指定的 webMessage 发布到此 Web 视图中的顶级文档。

> 公共 HRESULT [PostWebMessageAsJson](#postwebmessageasjson)（LPCWSTR webMessageAsJson）

将激发顶级文档的 "chrome" 消息事件。 该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件：

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

事件参数是的实例 `MessageEvent` 。 ICoreWebView2Settings：： IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并显示 E_INVALIDARG。 事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。 事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。 有关从 web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 SetWebMessageReceivedEventHandler。 此消息将异步发送。 如果在将邮件发布到页面之前发生导航，则不会发送邮件。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### PostWebMessageAsString 

这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。

> 公共 HRESULT [PostWebMessageAsString](#postwebmessageasstring)（LPCWSTR webMessageAsString）

此行为与 PostWebMessageAsJson 完全相同，但 `window.chrome.webview` 消息事件参数的 data 属性将是与 webMessageAsString 具有相同值的字符串。 如果想要通过简单的字符串而不是 JSON 对象进行通信，请使用此操作，而不是 PostWebMessageAsJson。

#### 重载 

重新加载当前页面。

> 公共 HRESULT[重装](#reload)（）

这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。 但是，将不会修改后退/前进历史记录。

#### remove_ContainsFullScreenElementChanged 

删除以前使用相应的 add_ 事件方法添加的事件处理程序。

> public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)（EventRegistrationToken 标记）

#### remove_ContentLoading 

删除以前使用 add_ContentLoading 添加的事件处理程序。

> public HRESULT [remove_ContentLoading](#remove_contentloading)（EventRegistrationToken 标记）

#### remove_DocumentTitleChanged 

删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。

> public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)（EventRegistrationToken 标记）

#### remove_FrameNavigationCompleted 

删除以前使用 add_FrameNavigationCompleted 添加的事件处理程序。

> public HRESULT [remove_FrameNavigationCompleted](#remove_framenavigationcompleted)（EventRegistrationToken 标记）

#### remove_FrameNavigationStarting 

删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。

> public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)（EventRegistrationToken 标记）

#### remove_HistoryChanged 

删除以前使用 add_HistoryChanged 添加的事件处理程序。

> public HRESULT [remove_HistoryChanged](#remove_historychanged)（EventRegistrationToken 标记）

#### remove_NavigationCompleted 

删除以前使用 add_NavigationCompleted 添加的事件处理程序。

> public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)（EventRegistrationToken 标记）

#### remove_NavigationStarting 

删除以前使用 add_NavigationStarting 添加的事件处理程序。

> public HRESULT [remove_NavigationStarting](#remove_navigationstarting)（EventRegistrationToken 标记）

#### remove_NewWindowRequested 

删除以前使用 add_NewWindowRequested 添加的事件处理程序。

> public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)（EventRegistrationToken 标记）

#### remove_PermissionRequested 

删除以前使用 add_PermissionRequested 添加的事件处理程序。

> public HRESULT [remove_PermissionRequested](#remove_permissionrequested)（EventRegistrationToken 标记）

#### remove_ProcessFailed 

删除以前使用 add_ProcessFailed 添加的事件处理程序。

> public HRESULT [remove_ProcessFailed](#remove_processfailed)（EventRegistrationToken 标记）

#### remove_ScriptDialogOpening 

删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。

> public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)（EventRegistrationToken 标记）

#### remove_SourceChanged 

删除以前使用 add_SourceChanged 添加的事件处理程序。

> public HRESULT [remove_SourceChanged](#remove_sourcechanged)（EventRegistrationToken 标记）

#### remove_WebMessageReceived 

删除以前使用 add_WebMessageReceived 添加的事件处理程序。

> public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)（EventRegistrationToken 标记）

#### remove_WebResourceRequested 

删除以前使用 add_WebResourceRequested 添加的事件处理程序。

> public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)（EventRegistrationToken 标记）

#### remove_WindowCloseRequested 

删除以前使用 add_WindowCloseRequested 添加的事件处理程序。

> public HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)（EventRegistrationToken 标记）

#### RemoveHostObjectFromScript 

删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。

> 公共 HRESULT [RemoveHostObjectFromScript](#removehostobjectfromscript)（LPCWSTR name）

当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。 为已删除或从未添加的名称调用此方法将失败。

#### RemoveScriptToExecuteOnDocumentCreated 

删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。

> 公共 HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)（LPCWSTR id）

#### RemoveWebResourceRequestedFilter 

删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。

> 公共 HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（LPCWSTR const uri， [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext）

如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。 返回从未添加的筛选器 E_INVALIDARG。

#### 停止 

停止所有导航和挂起的资源提取。

> 公共 HRESULT[停止](#stop)（）

不会停止脚本。

#### COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT 

ICoreWebView2：： CapturePreview 方法使用的图像格式。

> 枚举[COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG            | PNG 图像格式。
COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG            | JPEG 图像格式。

#### COREWEBVIEW2_KEY_EVENT_KIND 

触发 AcceleratorKeyPressed 事件的键事件的类型。

> 枚举[COREWEBVIEW2_KEY_EVENT_KIND](#corewebview2_key_event_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN            | 对应于窗口消息 WM_KEYDOWN。
COREWEBVIEW2_KEY_EVENT_KIND_KEY_UP            | 对应于窗口消息 WM_KEYUP。
COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN            | 对应于窗口消息 WM_SYSKEYDOWN。
COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP            | 对应于窗口消息 WM_SYSKEYUP。

#### COREWEBVIEW2_MOVE_FOCUS_REASON 

移动焦点的原因。

> 枚举[COREWEBVIEW2_MOVE_FOCUS_REASON](#corewebview2_move_focus_reason)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC            | 将焦点放入 Web 视图中的代码。
COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT            | 由于向前遍历 Tab 遍历，移动焦点。
COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS            | 由于 Tab 向后移动焦点。

#### COREWEBVIEW2_PERMISSION_KIND 

权限请求的类型。

> 枚举[COREWEBVIEW2_PERMISSION_KIND](#corewebview2_permission_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION            | 未知权限。
COREWEBVIEW2_PERMISSION_KIND_MICROPHONE            | 捕获音频的权限。
COREWEBVIEW2_PERMISSION_KIND_CAMERA            | 捕获视频的权限。
COREWEBVIEW2_PERMISSION_KIND_GEOLOCATION            | 访问地理位置的权限。
COREWEBVIEW2_PERMISSION_KIND_NOTIFICATIONS            | 发送 web 通知的权限。
COREWEBVIEW2_PERMISSION_KIND_OTHER_SENSORS            | 访问通用传感器的权限。
COREWEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ            | 在没有用户手势的情况下读取系统剪贴板的权限。

#### COREWEBVIEW2_PERMISSION_STATE 

对权限请求的响应。

> 枚举[COREWEBVIEW2_PERMISSION_STATE](#corewebview2_permission_state)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_PERMISSION_STATE_DEFAULT            | 使用默认的浏览器行为，这通常会提示用户做出决策。
COREWEBVIEW2_PERMISSION_STATE_ALLOW            | 授予权限请求。
COREWEBVIEW2_PERMISSION_STATE_DENY            | 拒绝权限请求。

#### COREWEBVIEW2_PHYSICAL_KEY_STATUS 

一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。

> typedef [COREWEBVIEW2_PHYSICAL_KEY_STATUS](#corewebview2_physical_key_status)

有关详细信息，请参阅 WM_KEYDOWN 的文档[https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)

#### COREWEBVIEW2_PROCESS_FAILED_KIND 

ICoreWebView2ProcessFailedEventHandler 接口中使用的进程失败类型。

> 枚举[COREWEBVIEW2_PROCESS_FAILED_KIND](#corewebview2_process_failed_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED            | 指示浏览器进程意外终止。
COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED            | 指示呈现进程意外终止。
COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE            | 指示呈现过程变得无响应。

#### COREWEBVIEW2_SCRIPT_DIALOG_KIND 

ICoreWebView2ScriptDialogOpeningEventHandler 接口中使用的 JavaScript 对话框类型。

> 枚举[COREWEBVIEW2_SCRIPT_DIALOG_KIND](#corewebview2_script_dialog_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_SCRIPT_DIALOG_KIND_ALERT            | 通过窗口调用的对话框。警报 JavaScript 函数。
COREWEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM            | 通过窗口调用的对话框。确认 JavaScript 函数。
COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT            | 通过窗口调用的对话框。提示 JavaScript 函数。
COREWEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD            | 通过 beforeunload JavaScript 事件调用的对话框。

#### COREWEBVIEW2_WEB_ERROR_STATUS 

Web 导航的错误状态值。

> 枚举[COREWEBVIEW2_WEB_ERROR_STATUS](#corewebview2_web_error_status)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_WEB_ERROR_STATUS_UNKNOWN            | 出现未知错误。
COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT            | SSL 证书公用名与 web 地址不匹配。
COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED            | SSL 证书已过期。
COREWEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS            | SSL 客户端证书包含错误。
COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED            | SSL 证书已被吊销。
COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID            | SSL 证书无效 &ndash; 这可能意味着证书与主机名的公钥 pin 不匹配，证书由不受信任的颁发机构或使用弱标志算法签名，证书声明的 DNS 名称违反了名称约束，证书包含弱密钥，证书的有效期太长，缺少吊销信息或吊销机制、非唯一的主机名、缺少证书透明信息，或者证书被链接到[旧版 Symantec 根](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)。
COREWEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE            | 无法访问主机。
COREWEBVIEW2_WEB_ERROR_STATUS_TIMEOUT            | 连接超时。
COREWEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE            | 服务器返回了无效或无法识别的响应。
COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED            | 连接已中止。
COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET            | 已重置连接。
COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED            | 互联网连接已丢失。
COREWEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT            | 无法连接到目标。
COREWEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED            | 无法解析提供的主机名。
COREWEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED            | 操作已取消。
COREWEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED            | 请求重定向失败。
COREWEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR            | 出现意外错误。

#### COREWEBVIEW2_WEB_RESOURCE_CONTEXT 

Web 资源请求上下文的枚举。

> 枚举[COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context)

 值                         | 描述
--------------------------------|---------------------------------------------
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_ALL            | 所有资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT            | 文档资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET            | CSS 资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE            | 图像资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA            | 其他媒体资源（如视频）。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FONT            | 字体资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT            | 脚本资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST            | XML HTTP 请求。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH            | 获取 API 通信。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK            | TextTrack 资源。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE            | EventSource API 通信。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET            | WebSocket API 通信。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST            | Web 应用清单。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE            | 已签名的 HTTP 交换。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_PING            | Ping 请求。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT            | CSP 冲突报告。
COREWEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER            | 其他资源。

