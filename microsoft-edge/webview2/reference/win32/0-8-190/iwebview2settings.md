---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 649506b28e0ecdbff33b44bbd8010ddb3d2a66b0
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885798"
---
# 0.8.355-接口 IWebView2Settings 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2Settings
  : public IUnknown
```

定义启用、禁用或修改 Web 视图功能的属性。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsScriptEnabled](#get_isscriptenabled) | 控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。
[put_IsScriptEnabled](#put_isscriptenabled) | 设置 IsScriptEnabled 属性。
[get_IsWebMessageEnabled](#get_iswebmessageenabled) | 加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。
[put_IsWebMessageEnabled](#put_iswebmessageenabled) | 设置 IsWebMessageEnabled 属性。
[get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled) | 加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。
[put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled) | 设置 AreDefaultScriptDialogsEnabled 属性。
[get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated) | 此设置已弃用，并且将始终返回 false。
[put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated) | 此设置已弃用，并且将不起任何作用。
[get_IsStatusBarEnabled](#get_isstatusbarenabled) | IsStatusBarEnabled 控制状态栏是否将显示。
[put_IsStatusBarEnabled](#put_isstatusbarenabled) | 设置 IsStatusBarEnabled 属性。
[get_AreDevToolsEnabled](#get_aredevtoolsenabled) | AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。
[put_AreDevToolsEnabled](#put_aredevtoolsenabled) | 设置 AreDevToolsEnabled 属性。

在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。

## 成员

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

#### put_IsScriptEnabled 

设置 IsScriptEnabled 属性。

> 公共 HRESULT [put_IsScriptEnabled](#put_isscriptenabled)（布尔值 IsScriptEnabled）

#### get_IsWebMessageEnabled 

加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。

> public HRESULT [get_IsWebMessageEnabled](#get_iswebmessageenabled)（BOOL * IsWebMessageEnabled）

如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。 通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。 如果设置为 false，则不允许通信。 PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。 默认情况下为 true。

```cpp
    ComPtr<IWebView2Settings> settings;
    CHECK_FAILURE(m_webView->get_Settings(&settings));

    CHECK_FAILURE(settings->put_IsWebMessageEnabled(TRUE));
```

#### put_IsWebMessageEnabled 

设置 IsWebMessageEnabled 属性。

> 公共 HRESULT [put_IsWebMessageEnabled](#put_iswebmessageenabled)（布尔值 IsWebMessageEnabled）

#### get_AreDefaultScriptDialogsEnabled 

加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。

> public HRESULT [get_AreDefaultScriptDialogsEnabled](#get_aredefaultscriptdialogsenabled)（BOOL * AreDefaultScriptDialogsEnabled）

如果设置为 false，则 Web 视图不会呈现默认 javascript 对话框（具体由 javascript 警报、确认和提示函数显示的对话框）。 相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。

#### put_AreDefaultScriptDialogsEnabled 

设置 AreDefaultScriptDialogsEnabled 属性。

> 公共 HRESULT [put_AreDefaultScriptDialogsEnabled](#put_aredefaultscriptdialogsenabled)（布尔值 AreDefaultScriptDialogsEnabled）

#### get_IsFullscreenAllowed_deprecated 

此设置已弃用，并且将始终返回 false。

> public HRESULT [get_IsFullscreenAllowed_deprecated](#get_isfullscreenallowed_deprecated)（BOOL * IsFullscreenAllowed）

这意味着 Web 视图中的元素将仅填充 Web 视图边界。 此属性将被完全删除。 请改为收听 ContainsFullScreenElementChanged 事件。

控制 Web 视图中的元素是否允许全屏。 如果允许，则允许 web 内容（如 web 视图中的视频元素）全屏显示。 当不允许时，此类元素将在元素请求全屏时填充 Web 视图边界。 默认情况下为 true。

#### put_IsFullscreenAllowed_deprecated 

此设置已弃用，并且将不起任何作用。

> 公共 HRESULT [put_IsFullscreenAllowed_deprecated](#put_isfullscreenallowed_deprecated)（布尔值 IsFullscreenAllowed）

请改为收听 ContainsFullScreenElementChanged 事件。

设置 IsFullscreenAllowed 属性。

#### get_IsStatusBarEnabled 

IsStatusBarEnabled 控制状态栏是否将显示。

> public HRESULT [get_IsStatusBarEnabled](#get_isstatusbarenabled)（BOOL * IsStatusBarEnabled）

状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。 默认情况下为 true。

#### put_IsStatusBarEnabled 

设置 IsStatusBarEnabled 属性。

> 公共 HRESULT [put_IsStatusBarEnabled](#put_isstatusbarenabled)（布尔值 IsStatusBarEnabled）

#### get_AreDevToolsEnabled 

AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。

> public HRESULT [get_AreDevToolsEnabled](#get_aredevtoolsenabled)（BOOL * AreDevToolsEnabled）

默认情况下为 true。

#### put_AreDevToolsEnabled 

设置 AreDevToolsEnabled 属性。

> 公共 HRESULT [put_AreDevToolsEnabled](#put_aredevtoolsenabled)（布尔值 AreDevToolsEnabled）

