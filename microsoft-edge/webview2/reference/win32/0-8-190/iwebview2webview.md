---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 5c84cfb703c8901560307b7bba8bc7887cb19377
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652808"
---
# interface IWebView2WebView 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2WebView
  : public IUnknown
```

WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Settings](#get_settings) | [IWebView2Settings](IWebView2Settings.md)对象包含运行的 web 视图的各种可修改设置。
[get_Source](#get_source) | 当前顶级文档的 URI。
[导航](#navigate) | 导致将顶级文档导航到指定的 URI。
[MoveFocus](#movefocus) | 将焦点移动到 Web 视图中。
[NavigateToString](#navigatetostring) | 启动作为新文档的源 HTML 的 htmlContent 导航。
[add_NavigationStarting](#add_navigationstarting) | 为 NavigationStarting 事件添加事件处理程序。
[remove_NavigationStarting](#remove_navigationstarting) | 删除以前使用 add_NavigationStarting 添加的事件处理程序。
[add_DocumentStateChanged](#add_documentstatechanged) | 为 DocumentStateChanged 事件添加事件处理程序。
[remove_DocumentStateChanged](#remove_documentstatechanged) | 删除以前使用 add_DocumentStateChanged 添加的事件处理程序。
[add_NavigationCompleted](#add_navigationcompleted) | 为 NavigationCompleted 事件添加事件处理程序。
[remove_NavigationCompleted](#remove_navigationcompleted) | 删除以前使用 add_NavigationCompleted 添加的事件处理程序。
[add_FrameNavigationStarting](#add_framenavigationstarting) | 为 FrameNavigationStarting 事件添加事件处理程序。
[remove_FrameNavigationStarting](#remove_framenavigationstarting) | 删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。
[add_MoveFocusRequested](#add_movefocusrequested) | 为 MoveFocusRequested 事件添加事件处理程序。
[remove_MoveFocusRequested](#remove_movefocusrequested) | 删除以前使用 add_MoveFocusRequested 添加的事件处理程序。
[add_GotFocus](#add_gotfocus) | 为 GotFocus 事件添加事件处理程序。
[remove_GotFocus](#remove_gotfocus) | 删除以前使用 add_GotFocus 添加的事件处理程序。
[add_LostFocus](#add_lostfocus) | 为 LostFocus 事件添加事件处理程序。
[remove_LostFocus](#remove_lostfocus) | 删除以前使用 add_LostFocus 添加的事件处理程序。
[add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated) | 此 API 将被弃用，请使用新的 add_WebResourceRequested API。
[remove_WebResourceRequested](#remove_webresourcerequested) | 删除以前使用 add_WebResourceRequested 添加的事件处理程序。
[add_ScriptDialogOpening](#add_scriptdialogopening) | 为 ScriptDialogOpening 事件添加事件处理程序。
[remove_ScriptDialogOpening](#remove_scriptdialogopening) | 删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。
[add_ZoomFactorChanged](#add_zoomfactorchanged) | 为 ZoomFactorChanged 事件添加事件处理程序。
[remove_ZoomFactorChanged](#remove_zoomfactorchanged) | 删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。
[add_PermissionRequested](#add_permissionrequested) | 为 Webview.permissionrequested 事件添加事件处理程序。
[remove_PermissionRequested](#remove_permissionrequested) | 删除以前使用 add_PermissionRequested 添加的事件处理程序。
[add_ProcessFailed](#add_processfailed) | 为 ProcessFailed 事件添加事件处理程序。
[remove_ProcessFailed](#remove_processfailed) | 删除以前使用 add_ProcessFailed 添加的事件处理程序。
[AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated) | 将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。
[RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) | 删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。
[ExecuteScript](#executescript) | 从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。
[CapturePreview](#capturepreview) | 捕获 Web 视图显示的图像。
[重载](#reload) | 重新加载当前页面。
[get_Bounds](#get_bounds) | Web 视图边界。
[put_Bounds](#put_bounds) | 设置界限属性。
[get_ZoomFactor](#get_zoomfactor) | Web 视图中当前页面的缩放系数。
[put_ZoomFactor](#put_zoomfactor) | 设置 ZoomFactor 属性。
[get_IsVisible](#get_isvisible) | IsVisible 属性确定是显示还是隐藏 web 视图。
[put_IsVisible](#put_isvisible) | 设置 IsVisible 属性。
[PostWebMessageAsJson](#postwebmessageasjson) | 将指定的 webMessage 发布到此[IWebView2WebView]()中的最高级别文档。
[PostWebMessageAsString](#postwebmessageasstring) | 这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。
[add_WebMessageReceived](#add_webmessagereceived) | 当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。
[remove_WebMessageReceived](#remove_webmessagereceived) | 删除以前使用 add_WebMessageReceived 添加的事件处理程序。
[关闭](#close) | 关闭 web 视图并清理基础浏览器实例。
[CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod) | 调用异步 DevToolsProtocol 方法。
[add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived) | 订阅 DevToolsProtocol 事件。
[remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived) | 删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。
[get_BrowserProcessId](#get_browserprocessid) | 托管 Web 视图的浏览器进程的进程 id。
[get_CanGoBack](#get_cangoback) | 可将 web 视图导航到导航历史记录中的上一页。
[get_CanGoForward](#get_cangoforward) | 可将 web 视图导航到导航历史记录中的下一页。
[GoBack](#goback) | 将 web 视图导航到导航历史记录中的上一页。
[GoForward](#goforward) | 将 web 视图导航到导航历史记录中的下一页。
[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) | [IWebView2WebView：： CapturePreview](#capturepreview)方法使用的图像格式。
[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind) | [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)接口中使用的 JavaScript 对话框类型。
[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind) | [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)接口中使用的进程失败类型。
[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type) | 权限请求的类型。
[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state) | 对权限请求的响应。
[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) | 移动焦点的原因。
[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status) | Web 导航的错误状态值。
[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) | Web 资源请求上下文的枚举。

## 导航事件

导航事件的正常序列是 NavigationStarting、DocumentStateChanged 和 NavigationCompleted。

![dot-inline-dotgraph-1](media/dot-inline-dotgraph-1.png)

请注意，这适用于具有相同的 NavigationId 事件参数的导航事件。 具有不同 NavigationId 事件参数的导航事件可能会重叠。 例如，如果你为其 NavigationStarting 事件启动导航等待，然后开始另一个导航，你将看到第一个导航的 NavigationStarting，后跟第二个导航的 NavigationStarting，然后是第一个导航的 NavigationCompleted 以及第二个导航的所有其余导航事件。 在错误情况下，可能会有也可能不是 DocumentStateChanged 事件，具体取决于导航是否转到错误页面。 在 HTTP 重定向时，一行中将有多个 NavigationStarting 事件，并且第一个事件将设置其 IsRedirect 标志。

对于 Web 视图内部的 subframes，引发的唯一导航事件是 NavigationStarting 事件，它使主机能够阻止 subframe 导航。

## 流程模型

WebView2 使用与 Edge web 浏览器相同的进程模型。 用户会话中每个指定的用户数据目录都有一个 Edge 浏览器进程，该进程将为指定用户数据目录的任何 WebView2 调用进程提供服务。 这意味着一个 Edge 浏览器进程可能正在为多个呼叫流程提供服务，并且一个呼叫进程可能正在使用多个 Edge 浏览器进程。

![dot-inline-dotgraph-2](media/dot-inline-dotgraph-2.png)

浏览器进程关闭时，将出现一些数量的呈现器进程。 根据需要创建这些类，以在不同的 WebViews 中服务潜在的多个帧。 呈现器进程的数量因网站隔离浏览器功能和呈现在关联的 WebViews 中的独特断开的来源的数量而异。

![dot-inline-dotgraph-3](media/dot-inline-dotgraph-3.png)

你可以使用 ProcessFailure 事件对这些浏览器和呈现器进程中的崩溃和挂起做出反应。

你可以使用 Close 方法安全地关闭关联的浏览器和呈现器进程。

## 线程模型

WebView2 必须在 UI 线程上创建。 专门使用消息泵的线程。 所有回调都将在该线程上发生，并且对 Web 视图的调用必须在该线程上完成。 使用来自另一个线程的 Web 视图不安全。

回调包括事件处理程序和完成处理程序按顺序执行。 也就是说，如果你有一个事件处理程序正在运行并开始消息循环，则没有其他事件处理程序或完成回调将开始执行 reentrantly。

## 安全

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

打开具有普通快捷方式的 DevTools： `F12` 或 `Ctrl+Shift+I` 。 在 `--auto-open-devtools-for-tabs` 首次创建 Web 视图时，可以使用 command 参数开关让 DevTools 窗口立即打开。 有关如何向浏览器进程提供其他命令行参数，请参阅 CreateWebView 文档。 签出 LoaderOverride 注册表项，在 CreateWebView 文档中无需修改你的应用程序，即可试用不同版本的 WebView2。

## 版本控制

在使用特定版本的 SDK 构建你的应用后，你的应用可能会使用已安装的旧版本或更高版本的浏览器二进制文件运行。 在 WebView2 版本1.0.0.0 之前，可能会在更新期间发生中断更改，这些更改将阻止你的 SDK 使用安装的浏览器二进制文件的不同版本。 在版本1.0.0.0 后，SDK 的不同版本可以按照以下最佳做法使用安装的浏览器的不同版本：

若要对 API 进行重大更改，请确保在调用 DLL 导出 CreateWebView2Environment 时和在任何 WebView2 对象上调用 QueryInterface 时检查是否失败。 E_NOINTERFACE 的返回值可指示 SDK 与 Edge 浏览器二进制文件不兼容。

从 QueryInterface 检查失败还将考虑 SDK 比 Edge 浏览器的版本更新的情况，并且你的应用尝试使用 Edge 浏览器不兼容的接口。

当接口不可用时，你可以考虑禁用关联的功能（如果可能），或者向最终用户通知他们需要更新其浏览器。

## 成员

#### get_Settings 

[IWebView2Settings](IWebView2Settings.md)对象包含运行的 web 视图的各种可修改设置。

> 公共 HRESULT [get_Settings](#get_settings)（[IWebView2Settings](IWebView2Settings.md) * * 设置）

#### get_Source 

当前顶级文档的 URI。

> 公共 HRESULT [get_Source](#get_source)（LPWSTR * uri）

在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 DocumentStateChanged 事件的一部分。 它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
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
        &m_documentStateChangedToken));
```

#### 导航 

导致将顶级文档导航到指定的 URI。

> 公共 HRESULT[导航](#navigate)（LPCWSTR uri）

有关详细信息，请参阅导航事件。 请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。

```cpp
void ControlComponent::NavigateToAddressBar()
{
    WCHAR uri[2048] = L"";
    GetWindowText(m_toolbar->addressBarWindow, uri, ARRAYSIZE(uri));
    CHECK_FAILURE(m_webView->Navigate(uri));
}
```

#### MoveFocus 

将焦点移动到 Web 视图中。

> 公共 HRESULT [MoveFocus](#movefocus)（[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)原因）

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
            for (int i = 0; i < m_tabbableWindows.size(); i++)
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
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
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
    CHECK_FAILURE(m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
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

#### add_NavigationStarting 

为 NavigationStarting 事件添加事件处理程序。

> public HRESULT [add_NavigationStarting](#add_navigationstarting)（[IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。 这也会引发重定向。

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            if (userInitiated)
            {
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
            }
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

#### remove_NavigationStarting 

删除以前使用 add_NavigationStarting 添加的事件处理程序。

> public HRESULT [remove_NavigationStarting](#remove_navigationstarting)（EventRegistrationToken 标记）

#### add_DocumentStateChanged 

为 DocumentStateChanged 事件添加事件处理程序。

> public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)（[IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当新内容在 web 视图的主框架上开始加载或出现相同的页面导航时（例如通过片段导航或 pushState 导航），将触发 DocumentStateChanged。 这将遵循 NavigationStarting 事件，并在 NavigationCompleted 事件之前。

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
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
        &m_documentStateChangedToken));
```

#### remove_DocumentStateChanged 

删除以前使用 add_DocumentStateChanged 添加的事件处理程序。

> public HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)（EventRegistrationToken 标记）

#### add_NavigationCompleted 

为 NavigationCompleted 事件添加事件处理程序。

> public HRESULT [add_NavigationCompleted](#add_navigationcompleted)（[IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Back, Forward, and Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<IWebView2NavigationCompletedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }

                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### remove_NavigationCompleted 

删除以前使用 add_NavigationCompleted 添加的事件处理程序。

> public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)（EventRegistrationToken 标记）

#### add_FrameNavigationStarting 

为 FrameNavigationStarting 事件添加事件处理程序。

> public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)（[IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。 这也会引发重定向。

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
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

#### remove_FrameNavigationStarting 

删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。

> public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)（EventRegistrationToken 标记）

#### add_MoveFocusRequested 

为 MoveFocusRequested 事件添加事件处理程序。

> public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)（[IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。 激发此事件时，Web 视图的焦点未发生更改。

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_webView->add_MoveFocusRequested(
        Callback<IWebView2MoveFocusRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2MoveFocusRequestedEventArgs* args)
                -> HRESULT {
                if (!g_autoTabHandle)
                {
                    WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
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

#### remove_MoveFocusRequested 

删除以前使用 add_MoveFocusRequested 添加的事件处理程序。

> public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)（EventRegistrationToken 标记）

#### add_GotFocus 

为 GotFocus 事件添加事件处理程序。

> public HRESULT [add_GotFocus](#add_gotfocus)（[IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图获得焦点时，将引发 GotFocus。

#### remove_GotFocus 

删除以前使用 add_GotFocus 添加的事件处理程序。

> public HRESULT [remove_GotFocus](#remove_gotfocus)（EventRegistrationToken 标记）

#### add_LostFocus 

为 LostFocus 事件添加事件处理程序。

> public HRESULT [add_LostFocus](#add_lostfocus)（[IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图失去焦点时，将激发 LostFocus。 在引发 MoveFocusRequested 事件的情况下，当 MoveFocusRequested 事件引发时，焦点仍在 Web 视图上。 只有在应用的 MoveFocusRequested 事件或从 Web 视图中设置焦点的情况下，才会在应用的代码或默认操作时引发丢失焦点。

#### remove_LostFocus 

删除以前使用 add_LostFocus 添加的事件处理程序。

> public HRESULT [remove_LostFocus](#remove_lostfocus)（EventRegistrationToken 标记）

#### add_WebResourceRequested_deprecated 

此 API 将被弃用，请使用新的 add_WebResourceRequested API。

> public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)（LPCWSTR * const urlFilter，[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) * Const resourceContextFilter，SIZE_T filterLength，[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) * eventHandler，EventRegistrationToken * 标记）

为 WebResourceRequested 事件添加事件处理程序。 在 Web 视图执行任何 HTTP 请求时激发。 使用 urlFilter 将列表传递到要侦听的 url 的大小 filterLength。 每个 url 条目还支持通配符： "*" 匹配零个或多个字符，"？" 与一个字符完全匹配。 对于每个 urlFilter 条目，提供匹配的 resourceContextFilter，表示 WebResourceRequested 应触发的资源类型。 如果 filterLength 为0，则将针对所有网络请求触发该事件。 受支持的资源上下文包括：文档、样式表、图像、媒体、字体、脚本、XHR、Fetch。

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
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

#### remove_WebResourceRequested 

删除以前使用 add_WebResourceRequested 添加的事件处理程序。

> public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)（EventRegistrationToken 标记）

#### add_ScriptDialogOpening 

为 ScriptDialogOpening 事件添加事件处理程序。

> public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)（[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) * eventHandler，EventRegistrationToken * token）

将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。 仅当 IWebView2Settings：： AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发。

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<IWebView2ScriptDialogOpeningEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<IWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            WEBVIEW2_SCRIPT_DIALOG_KIND type;
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
                /* readonly */ type != WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<IWebView2Deferral> deferral;
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

#### remove_ScriptDialogOpening 

删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。

> public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)（EventRegistrationToken 标记）

#### add_ZoomFactorChanged 

为 ZoomFactorChanged 事件添加事件处理程序。

> public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)（[IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。 由于调用方修改了 ZoomFactor 属性，或者由于用户手动修改缩放，因此可能会激发该事件。 当调用方通过 ZoomFactor 属性对其进行修改时，内部缩放系数将立即更新，并且将不会出现 ZoomFactorChanged 事件。 Web 视图将每个网站的上次使用的缩放系数相关联。 因此，在导航到其他页面时，可以更改缩放系数。 当缩放系数因此而更改时，ZoomFactorChanged 事件将在 DocumentStateChanged 事件后立即触发。

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_webView->add_ZoomFactorChanged(
        Callback<IWebView2ZoomFactorChangedEventHandler>(
            [this](IWebView2WebView* sender, IUnknown* args) -> HRESULT {
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

#### remove_ZoomFactorChanged 

删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。

> public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)（EventRegistrationToken 标记）

#### add_PermissionRequested 

为 Webview.permissionrequested 事件添加事件处理程序。

> public HRESULT [add_PermissionRequested](#add_permissionrequested)（[IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图中的内容请求访问某些权限资源的权限时引发。

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<IWebView2PermissionRequestedEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        WEBVIEW2_PERMISSION_TYPE type = WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionType(&type));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionType(type);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? WEBVIEW2_PERMISSION_STATE_DENY
            :                     WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### remove_PermissionRequested 

删除以前使用 add_PermissionRequested 添加的事件处理程序。

> public HRESULT [remove_PermissionRequested](#remove_permissionrequested)（EventRegistrationToken 标记）

#### add_ProcessFailed 

为 ProcessFailed 事件添加事件处理程序。

> public HRESULT [add_ProcessFailed](#add_processfailed)（[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图进程意外终止或停止响应时激发。

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<IWebView2ProcessFailedEventHandler>(
            [this](IWebView2WebView* sender,
                IWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
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
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### remove_ProcessFailed 

删除以前使用 add_ProcessFailed 添加的事件处理程序。

> public HRESULT [remove_ProcessFailed](#remove_processfailed)（EventRegistrationToken 标记）

#### AddScriptToExecuteOnDocumentCreated 

将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。

> 公共 HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)（LPCWSTR JavaScript，[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) * 处理程序）

插入的脚本将应用于所有未来的顶级文档和子框架导航，直到使用 RemoveScriptToExecuteOnDocumentCreated 删除。 这是异步应用的，你必须等待完成处理程序运行，然后才能确保脚本已准备好在将来的导航上执行。

请注意，如果 HTML 文档通过[沙盒](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)属性或[内容安全策略 HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)进行了某种类型的沙盒，则会影响在此处运行脚本。 例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。

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
            Callback<IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### RemoveScriptToExecuteOnDocumentCreated 

删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。

> 公共 HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)（LPCWSTR id）

#### ExecuteScript 

从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。

> 公共 HRESULT [ExecuteScript](#executescript)（LPCWSTR JavaScript，[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) * 处理程序）

这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。 结果值是一个 JSON 编码的字符串。 如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。 请注意，没有显式返回值的函数将返回 undefined。 如果执行的脚本引发了未处理的异常，则结果也为 "null"。 此方法是异步应用的。 如果在 web 视图位于一个文档上时进行调用，并且在执行该调用之后但在执行 JavaScript 之前发生导航，则不会执行该脚本，并且将使用 E_FAIL 的 errorCode 参数调用该处理程序。 即使 IsScriptEnabled 设置为 FALSE，ExecuteScript 仍可正常工作。

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
            Callback<IWebView2ExecuteScriptCompletedHandler>(
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

#### CapturePreview 

捕获 Web 视图显示的图像。

> public HRESULT [CapturePreview](#capturepreview)（[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) ImageFormat、IStream * imageStream、[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) * 处理程序）

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
            WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<IWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### 重载 

重新加载当前页面。

> 公共 HRESULT[重装](#reload)（）

这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。 但是，将不会修改后退/前进历史记录。

#### get_Bounds 

Web 视图边界。

> public HRESULT [get_Bounds](#get_bounds)（RECT * 界限）

界限相对于父 HWND。 应用有两种方法可以放置 Web 视图：

1. 创建作为 Web 视图父 HWND 的子 HWND。 将此窗口放置在 Web 视图应位于的位置。 在这种情况下，对 Web 视图的 Bound's 左上角（偏移）使用（0，0）。

1. 将应用最顶部的窗口用作 Web 视图父 HWND。 设置 Web 视图的 Bound's 左上角，以便 Web 视图正确地放置在应用中。 绑定的值位于主机的坐标空间中。

#### put_Bounds 

设置界限属性。

> public HRESULT [put_Bounds](#put_bounds)（RECT 界限）

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        (m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio + m_webViewBounds.top);
    desiredBounds.right = LONG(
        (m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio + m_webViewBounds.left);

    m_webView->put_Bounds(desiredBounds);
}
```

#### get_ZoomFactor 

Web 视图中当前页面的缩放系数。

> 公共 HRESULT [get_ZoomFactor](#get_zoomfactor)（Double * ZoomFactor）

缩放系数按网站保持。 请注意，更改缩放系数可能会导致 `window.innerWidth/innerHeight` 页面布局和页面布局的更改。 当 Web 视图导航到来自不同网站的页面时，将不会应用上一页面的缩放系数。 如果应用要设置特定页面的缩放系数，则执行该操作的最早位置是在 DocumentStateChanged 事件处理程序中。 请注意，如果它执行此操作，则在针对指定的缩放系数接收 ZoomFactorChanged 事件之前，它可能会收到持续缩放系数的 ZoomFactorChanged 事件。 不允许指定小于或等于0的 zoomFactor。 Web 视图也具有内部受支持的缩放系数范围。 当指定的缩放系数超出该范围时，它将规范化为在范围内，并且将针对应用的已应用的缩放系数引发 ZoomFactorChanged 事件。 当此范围规范化发生时，ZoomFactor 属性将报告在 ZoomFactor 属性的以前修改期间指定的缩放系数，直到在 web 视图应用标准化的缩放系数后收到 ZoomFactorChanged 事件。

#### put_ZoomFactor 

设置 ZoomFactor 属性。

> 公共 HRESULT [put_ZoomFactor](#put_zoomfactor)（double ZoomFactor）

#### get_IsVisible 

IsVisible 属性确定是显示还是隐藏 web 视图。

> public HRESULT [get_IsVisible](#get_isvisible)（BOOL * IsVisible）

如果 IsVisible 设置为 false，则 web 视图将是透明的，不会呈现。 但是，这不会影响包含 web 视图的窗口（传递到 CreateWebView 的 HWND 参数）。 如果你希望该窗口也消失，除了修改 IsVisible 属性外，还可直接对其调用 ShowWindow。 在最小化或还原顶级窗口时，Web 视图作为子窗口不会收到窗口消息。 出于性能原因，开发人员应在应用窗口最小化时将 Web 视图的 IsVisible 属性设置为 false，并在还原应用窗口时将其设置为 false。 应用窗口可通过在接收 WM_SYSCOMMAND 消息时处理 SC_MINIMIZE 和 SC_RESTORE 命令来执行此操作。

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_webView->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_webView->put_IsVisible(m_isVisible);
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
            m_webView->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_webView->put_IsVisible(TRUE);
            }
        }
    }
```

#### PostWebMessageAsJson 

将指定的 webMessage 发布到此[IWebView2WebView]()中的最高级别文档。

> 公共 HRESULT [PostWebMessageAsJson](#postwebmessageasjson)（LPCWSTR webMessageAsJson）

将激发顶级文档的 "chrome" 消息事件。 该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件： 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 事件参数是的实例 `MessageEvent` 。 IWebView2Settings：： IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并显示 E_INVALIDARG。 事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。 事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。 有关从 web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 SetWebMessageReceivedEventHandler。 此消息将异步发送。 如果在将邮件发布到页面之前发生导航，则不会发送邮件。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
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

#### add_WebMessageReceived 

当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。

> public HRESULT [add_WebMessageReceived](#add_webmessagereceived)（[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) * 处理程序，EventRegistrationToken * token）

PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。

```cpp
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

 调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 的对象参数调用通过此 SetWebMessageReceivedEventHandler 方法设置的[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) 。

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
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

#### remove_WebMessageReceived 

删除以前使用 add_WebMessageReceived 添加的事件处理程序。

> public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)（EventRegistrationToken 标记）

#### 关闭 

关闭 web 视图并清理基础浏览器实例。

> 公共 HRESULT [Close](#close)（）

清理浏览器 instace 将释放为 web 视图供电的资源。 如果没有其他 webviews 使用浏览器实例，则将关闭该浏览器实例。

调用 Close 后，所有方法调用都将失败，事件处理程序将停止触发。 具体说来，当调用 Close 时，Web 视图将释放其对其事件处理程序的引用。

当 Web 视图失去其最终引用且为 destructed 时，将隐式调用 Close。 但最佳做法是显式调用 Close 以避免 Web 视图和应用代码之间任何意外的引用循环。 尤其是，如果你在事件处理程序中捕获对 Web 视图的引用，你将在 Web 视图和事件处理程序之间创建引用循环。 关闭将通过释放所有事件处理程序来中断此循环。 但是，为了避免这种情况，最佳做法是在 Web 视图上显式调用 Close，而不捕获对 Web 视图的引用，以确保可正确清理 Web 视图。

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView()
{
    DeleteAllComponents();
    if (m_webView)
    {
        m_webView->Close();
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
}
```

#### CallDevToolsProtocolMethod 

调用异步 DevToolsProtocol 方法。

> 公共 HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)（LPCWSTR 方法，LPCWSTR ParametersAsJson，[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) * 处理程序）

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
            Callback<IWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### add_DevToolsProtocolEventReceived 

订阅 DevToolsProtocol 事件。

> public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)（LPCWSTR 事件，[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) * 处理程序，EventRegistrationToken * 令牌）

有关可用事件的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。 事件名称参数是该事件的格式的完整名称 `{domain}.{event}` 。 每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。 将使用包含 CDP 事件的参数对象的事件参数对象作为 JSON 字符串调用调用。

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
        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(m_webView->remove_DevToolsProtocolEventReceived(
                eventName.c_str(),
                preexistingToken->second));
        }

        CHECK_FAILURE(m_webView->add_DevToolsProtocolEventReceived(
            eventName.c_str(),
            Callback<IWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](IWebView2WebView* sender,
                            IWebView2DevToolsProtocolEventReceivedEventArgs* args)
                -> HRESULT
        {
            wil::unique_cotaskmem_string parameterObjectAsJson;
            CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
            MessageBox(nullptr, parameterObjectAsJson.get(),
                       (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
            return S_OK;
        }).Get(), &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### remove_DevToolsProtocolEventReceived 

删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。

> 公共 HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)（LPCWSTR EventRegistrationToken、标记）

#### get_BrowserProcessId 

托管 Web 视图的浏览器进程的进程 id。

> 公共 HRESULT [get_BrowserProcessId](#get_browserprocessid)（UINT32 * 值）

#### get_CanGoBack 

可将 web 视图导航到导航历史记录中的上一页。

> public HRESULT [get_CanGoBack](#get_cangoback)（BOOL * CanGoBack）

get_CanGoBack DocumentStateChanged 事件更改值。

#### get_CanGoForward 

可将 web 视图导航到导航历史记录中的下一页。

> public HRESULT [get_CanGoForward](#get_cangoforward)（BOOL * CanGoForward）

get_CanGoForward DocumentStateChanged 事件更改值。

#### GoBack 

将 web 视图导航到导航历史记录中的上一页。

> 公共 HRESULT [GoBack](#goback)（）

#### GoForward 

将 web 视图导航到导航历史记录中的下一页。

> 公共 HRESULT [GoForward](#goforward)（）

#### WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT 

[IWebView2WebView：： CapturePreview](#capturepreview)方法使用的图像格式。

> 枚举[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG            | PNG 图像格式。
WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG            | JPEG 图像格式。

#### WEBVIEW2_SCRIPT_DIALOG_KIND 

[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)接口中使用的 JavaScript 对话框类型。

> 枚举[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT            | 通过窗口调用的对话框。警报 JavaScript 函数。
WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM            | 通过窗口调用的对话框。确认 JavaScript 函数。
WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT            | 通过窗口调用的对话框。提示 JavaScript 函数。

#### WEBVIEW2_PROCESS_FAILED_KIND 

[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)接口中使用的进程失败类型。

> 枚举[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED            | 指示浏览器进程意外终止。
WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED            | 指示呈现进程意外终止。
WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE            | 指示呈现过程变得无响应。

#### WEBVIEW2_PERMISSION_TYPE 

权限请求的类型。

> 枚举[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION            | 未知权限。
WEBVIEW2_PERMISSION_TYPE_MICROPHONE            | 捕获音频的权限。
WEBVIEW2_PERMISSION_TYPE_CAMERA            | 捕获视频的权限。
WEBVIEW2_PERMISSION_TYPE_GEOLOCATION            | 访问地理位置的权限。
WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS            | 发送 web 通知的权限。
WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS            | 访问通用传感器的权限。
WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ            | 在没有用户手势的情况下读取系统剪贴板的权限。

#### WEBVIEW2_PERMISSION_STATE 

对权限请求的响应。

> 枚举[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_PERMISSION_STATE_DEFAULT            | 使用默认的浏览器行为，这通常会提示用户做出决策。
WEBVIEW2_PERMISSION_STATE_ALLOW            | 授予权限请求。
WEBVIEW2_PERMISSION_STATE_DENY            | 拒绝权限请求。

#### WEBVIEW2_MOVE_FOCUS_REASON 

移动焦点的原因。

> 枚举[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC            | 将焦点放入 Web 视图中的代码。
WEBVIEW2_MOVE_FOCUS_REASON_NEXT            | 由于向前遍历 Tab 遍历，移动焦点。
WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS            | 由于 Tab 向后移动焦点。

#### WEBVIEW2_WEB_ERROR_STATUS 

Web 导航的错误状态值。

> 枚举[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN            | 出现未知错误。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT            | SSL 证书公用名与 web 地址不匹配。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED            | SSL 证书已过期。
WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS            | SSL 客户端证书包含错误。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED            | SSL 证书已被吊销。
WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID            | SSL 证书无效。
WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE            | 无法访问主机。
WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT            | 连接超时。
WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE            | 服务器返回了无效或无法识别的响应。
WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED            | 连接已中止。
WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET            | 已重置连接。
WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED            | 互联网连接已丢失。
WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT            | 无法连接到目标。
WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED            | 无法解析提供的主机名。
WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED            | 操作已取消。
WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED            | 请求重定向失败。
WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR            | 出现意外错误。

#### WEBVIEW2_WEB_RESOURCE_CONTEXT 

Web 资源请求上下文的枚举。

> 枚举[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)

 值                         | 描述
--------------------------------|---------------------------------------------
WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL            | 所有资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT            | 文档资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET            | CSS 资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE            | 图像资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA            | 其他媒体资源（如视频）。
WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT            | 字体资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT            | 脚本资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST            | XML HTTP 请求。
WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH            | 获取 API 通信。
WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK            | TextTrack 资源。
WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_PING            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT            | 
WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER            | 其他资源。
