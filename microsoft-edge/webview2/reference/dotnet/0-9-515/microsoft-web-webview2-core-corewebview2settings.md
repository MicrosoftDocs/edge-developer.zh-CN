---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2Settings
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: c31e81fba190d9c8c72d344c7fa1e442d5365d4e
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886390"
---
# 0.9.515-WebView2 的 CoreWebView2Settings 类 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

定义启用、禁用或修改 Web 视图功能的属性。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。
[AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled) | 加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。
[AreDevToolsEnabled](#aredevtoolsenabled) | AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。
[AreHostObjectsAllowed](#arehostobjectsallowed) | AreHostObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。
[IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。
[IsScriptEnabled](#isscriptenabled) | 控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。
[IsStatusBarEnabled](#isstatusbarenabled) | IsStatusBarEnabled 控制状态栏是否将显示。
[IsWebMessageEnabled](#iswebmessageenabled) | 加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。
[IsZoomControlEnabled](#iszoomcontrolenabled) | IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。

在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。

## 成员

#### AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled 属性用于阻止在 web 视图中向用户显示默认上下文菜单。

> 公共 bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)

默认值为 TRUE。

#### AreDefaultScriptDialogsEnabled 

加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。

> 公共 bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)

如果设置为 false，则 Web 视图不会呈现默认的 javascript 对话框（具体由 javascript 警报、confirm、prompt 函数和 beforeunload 事件所显示的对话框）。 相反，如果 SetScriptDialogOpeningEventHandler 设置了事件处理程序，则 Web 视图将发送一个包含对话框的所有信息的事件，并允许主机应用显示其自己的自定义 UI。

#### AreDevToolsEnabled 

AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。

> 公共 bool [AreDevToolsEnabled](#aredevtoolsenabled)

默认情况下为 true。

#### AreHostObjectsAllowed 

AreHostObjectsAllowed 属性用于控制是否可以从 web 视图中的页面访问主机对象。

> 公共 bool [AreHostObjectsAllowed](#arehostobjectsallowed)

默认值为 TRUE。

#### IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。

> 公共 bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)

默认值为 TRUE。 如果禁用，将在发生相关错误时显示空白页。

#### IsScriptEnabled 

控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。

> 公共 bool [IsScriptEnabled](#isscriptenabled)

这仅影响文档中的脚本;即使脚本被禁用，用 ExecuteScript 插入的脚本也会运行。 默认情况下为 true。

#### IsStatusBarEnabled 

IsStatusBarEnabled 控制状态栏是否将显示。

> 公共 bool [IsStatusBarEnabled](#isstatusbarenabled)

状态栏通常显示在 Web 视图的左下方，并且在用户悬停在其上方和其他信息时显示链接的 URI 等内容。 默认情况下为 true。

#### IsWebMessageEnabled 

加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。

> 公共 bool [IsWebMessageEnabled](#iswebmessageenabled)

如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和，从主机到 web 视图的顶级 HTML 文档的通信是允许通过 web 视图、和 window。 chrome 的消息事件（有关详细信息，请参阅 PostWebMessageAsJson 文档）。 通过 window 的 postMessage 函数和 SetWebMessageReceivedEventHandler 方法，允许从 web 视图的顶级 HTML 文档到主机的通信（有关详细信息，请参阅 SetWebMessageReceivedEventHandler 文档）。 如果设置为 false，则不允许通信。 PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。 默认情况下为 true。

#### IsZoomControlEnabled 

IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。

> 公共 bool [IsZoomControlEnabled](#iszoomcontrolenabled)

默认值为 TRUE。 当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。

