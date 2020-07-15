---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: a996660bb667ca0e556326e0bf2b71c15b9344c2
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880330"
---
# 0.9.515-接口 ICoreWebView2Settings 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2Settings
  : public IUnknown
```

定义启用、禁用或修改 Web 视图功能的属性。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。
[get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled) | 加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。
[get_AreDevToolsEnabled](#get_aredevtoolsenabled) | AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。
[get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed) | AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。
[get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。
[get_IsScriptEnabled](#get_isscriptenabled) | 控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。
[get_IsStatusBarEnabled](#get_isstatusbarenabled) | IsStatusBarEnabled 控制状态栏是否将显示。
[get_IsWebMessageEnabled](#get_iswebmessageenabled) | 加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。
[get_IsZoomControlEnabled](#get_iszoomcontrolenabled) | IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。
[put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled) | 设置 AreDefaultContextMenusEnabled 属性。
[put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled) | 设置 AreDefaultScriptDialogsEnabled 属性。
[put_AreDevToolsEnabled](#put_aredevtoolsenabled) | 设置 AreDevToolsEnabled 属性。
[put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed) | 设置 AreRemoteObjectsAllowed 属性。
[put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled) | 设置 IsBuiltInErrorPageEnabled 属性。
[put_IsScriptEnabled](#put_isscriptenabled) | 设置 IsScriptEnabled 属性。
[put_IsStatusBarEnabled](#put_isstatusbarenabled) | 设置 IsStatusBarEnabled 属性。
[put_IsWebMessageEnabled](#put_iswebmessageenabled) | 设置 IsWebMessageEnabled 属性。
[put_IsZoomControlEnabled](#put_iszoomcontrolenabled) | 设置 IsZoomControlEnabled 属性。

在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。

## 成员

#### get_AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。

> 公共 HRESULT [get_AreDefaultContextMenusEnabled](#get_aredefaultcontextmenusenabled)（已启用 BOOL *）

默认值为 TRUE。

```cpp
            BOOL allowContextMenus;
            CHECK_FAILURE(m_settings->get_AreDefaultContextMenusEnabled(
                &allowContextMenus));
            if (allowContextMenus) {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(FALSE));
                MessageBox(nullptr,
                L"Context menus will be disabled after the next navigation.",
                L"Settings change", MB_OK);
            }
            else {
                CHECK_FAILURE(m_settings->put_AreDefaultContextMenusEnabled(TRUE));
                MessageBox(nullptr,
                    L"Context menus will be enabled after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### get_AreDefaultScriptDialogsEnabled 

加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。

> public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL * AreDefaultScriptDialogsEnabled）

如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。 相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。

#### get_AreDevToolsEnabled 

AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。

> public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL * AreDevToolsEnabled）

默认情况下为 true。

#### get_AreRemoteObjectsAllowed 

AreRemoteObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。

> 公共 HRESULT [get_AreRemoteObjectsAllowed](#get_areremoteobjectsallowed)（允许使用 BOOL *）

默认值为 TRUE。

```cpp
            BOOL allowRemoteObjects;
            CHECK_FAILURE(m_settings->get_AreRemoteObjectsAllowed(&allowRemoteObjects));
            if (allowRemoteObjects)
            {
                CHECK_FAILURE(m_settings->put_AreRemoteObjectsAllowed(FALSE));
                MessageBox(
                    nullptr, L"Access to remote objects will be denied after the next navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_AreRemoteObjectsAllowed(TRUE));
                MessageBox(
                    nullptr, L"Access to remote objects will be allowed after the next navigation.",
                    L"Settings change", MB_OK);
            }
```

#### get_IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。

> 公共 HRESULT [get_IsBuiltInErrorPageEnabled](#get_isbuiltinerrorpageenabled)（已启用 BOOL *）

默认值为 TRUE。 如果禁用，将在发生相关错误时显示空白页。

```cpp
            BOOL enabled;
            CHECK_FAILURE(m_settings->get_IsBuiltInErrorPageEnabled(&enabled));
            if (enabled)
            {
                CHECK_FAILURE(m_settings->put_IsBuiltInErrorPageEnabled(FALSE));
                MessageBox(
                    nullptr, L"Built-in error page will be disabled for future navigation.",
                    L"Settings change", MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsBuiltInErrorPageEnabled(TRUE));
                MessageBox(
                    nullptr, L"Built-in error page will be enabled for future navigation.",
                    L"Settings change", MB_OK);
            }
```

#### get_IsScriptEnabled 

控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。

> public HRESULT [get_IsScriptEnabled](#get_isscriptenabled)（BOOL * IsScriptEnabled）

这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。 默认情况下为 true。

```cpp
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
```

#### get_IsStatusBarEnabled 

IsStatusBarEnabled 控制状态栏是否将显示。

> public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL * IsStatusBarEnabled）

状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。 默认情况下为 true。

#### get_IsWebMessageEnabled 

加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。

> public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL * IsWebMessageEnabled）

如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。 通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。 如果设置为 false，则不允许通信。 PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。 默认情况下为 true。

```cpp
    ComPtr<ICoreWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### get_IsZoomControlEnabled 

IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。

> 公共 HRESULT [get_IsZoomControlEnabled](#get_iszoomcontrolenabled)（已启用 BOOL *）

默认值为 TRUE。 当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。

```cpp
            BOOL zoomControlEnabled;
            CHECK_FAILURE(m_settings->get_IsZoomControlEnabled(&zoomControlEnabled));
            if (zoomControlEnabled)
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(FALSE));
                MessageBox(
                    nullptr, L"Zoom control will be disabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
            else
            {
                CHECK_FAILURE(m_settings->put_IsZoomControlEnabled(TRUE));
                MessageBox(
                    nullptr, L"Zoom control will be enabled after the next navigation.", L"Settings change",
                    MB_OK);
            }
```

#### put_AreDefaultContextMenusEnabled 

设置 AreDefaultContextMenusEnabled 属性。

> public HRESULT [put_AreDefaultContextMenusEnabled](#put_aredefaultcontextmenusenabled)（已启用 BOOL）

#### put_AreDefaultScriptDialogsEnabled 

设置 AreDefaultScriptDialogsEnabled 属性。

> 公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）

#### put_AreDevToolsEnabled 

设置 AreDevToolsEnabled 属性。

> 公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）

#### put_AreRemoteObjectsAllowed 

设置 AreRemoteObjectsAllowed 属性。

> 公共 HRESULT [put_AreRemoteObjectsAllowed](#put_areremoteobjectsallowed)（允许使用 BOOL）

#### put_IsBuiltInErrorPageEnabled 

设置 IsBuiltInErrorPageEnabled 属性。

> public HRESULT [put_IsBuiltInErrorPageEnabled](#put_isbuiltinerrorpageenabled)（已启用 BOOL）

#### put_IsScriptEnabled 

设置 IsScriptEnabled 属性。

> 公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）

#### put_IsStatusBarEnabled 

设置 IsStatusBarEnabled 属性。

> 公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）

#### put_IsWebMessageEnabled 

设置 IsWebMessageEnabled 属性。

> 公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）

#### put_IsZoomControlEnabled 

设置 IsZoomControlEnabled 属性。

> public HRESULT [put_IsZoomControlEnabled](#put_iszoomcontrolenabled)（已启用 BOOL）

