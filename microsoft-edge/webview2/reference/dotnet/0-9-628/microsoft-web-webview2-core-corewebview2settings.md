---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2Settings 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 87b78956c29dac74bd023556a8c495222d248e9f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011663"
---
# CoreWebView2Settings 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

定义启用、禁用或修改 Web 视图功能的属性。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled) | AreDefaultContextMenusEnabled 属性用于阻止在 Web 视图中向用户显示默认上下文菜单。
[AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled) | 加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。
[AreDevToolsEnabled](#aredevtoolsenabled) | AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。
[AreHostObjectsAllowed](#arehostobjectsallowed) | AreHostObjectsAllowed 属性用于控制是否可以从 Web 视图中的页面访问主机对象。
[IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled) | IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。
[IsScriptEnabled](#isscriptenabled) | 控制在 Web 视图中的所有未来导航中是否启用了 JavaScript 执行。
[IsStatusBarEnabled](#isstatusbarenabled) | IsStatusBarEnabled 控制状态栏是否将显示。
[IsWebMessageEnabled](#iswebmessageenabled) | 加载新的 HTML 文档时，将使用 IsWebMessageEnabled 属性。
[IsZoomControlEnabled](#iszoomcontrolenabled) | IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。

在 NavigationStarting 事件之后设置所做的更改将不会应用到下一个顶级导航。

## 成员

#### AreDefaultContextMenusEnabled 

AreDefaultContextMenusEnabled 属性用于阻止在 Web 视图中向用户显示默认上下文菜单。

> 公共 bool [AreDefaultContextMenusEnabled](#aredefaultcontextmenusenabled)

默认情况下为 true。

#### AreDefaultScriptDialogsEnabled 

加载新的 HTML 文档时，将使用 AreDefaultScriptDialogsEnabled。

> 公共 bool [AreDefaultScriptDialogsEnabled](#aredefaultscriptdialogsenabled)

如果设置为 false，则 Web 视图不会呈现默认的 JavaScript 对话框 (特定的 JavaScript 对话框，具体由 JavaScript 警报、确认、提示函数和 beforeunload 事件) 所示。 如果设置为 true，则还可以订阅将包含对话框的所有信息的 ScriptDialogOpening 事件，并允许主机应用显示其自己的自定义 UI。 默认情况下为 true。

#### AreDevToolsEnabled 

AreDevToolsEnabled 控制用户是否可以使用上下文菜单或键盘快捷方式打开 DevTools 窗口。

> 公共 bool [AreDevToolsEnabled](#aredevtoolsenabled)

默认情况下为 true。

#### AreHostObjectsAllowed 

AreHostObjectsAllowed 属性用于控制是否可以从 Web 视图中的页面访问主机对象。

> 公共 bool [AreHostObjectsAllowed](#arehostobjectsallowed)

默认情况下为 true。

#### IsBuiltInErrorPageEnabled 

IsBuiltInErrorPageEnabled 属性用于禁用内置错误页面，用于导航故障和呈现进程失败。

> 公共 bool [IsBuiltInErrorPageEnabled](#isbuiltinerrorpageenabled)

默认情况下为 true。 如果禁用，将在发生相关错误时显示空白页。

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

如果设置为 true，则通过 PostWebMessageAsJson、PostWebMessageAsString 和 window HTML 文档从主机到 Web 视图的顶级 HTML 文档的通信是允许的。 web 视图的消息事件 (有关详细信息) ，请参阅 PostWebMessageAsJson 文档。 通过 postMessage 函数和 WebMessageReceived (事件，从 Web 视图的顶级 HTML 文档到主机的通信是允许的，请参阅 WebMessageReceived 文档了解详细信息) 。 如果设置为 false，则不允许通信。 PostWebMessageAsJson 和 PostWebMessageAsString 将失败 E_ACCESSDENIED，并且通过引发 Error 对象的实例，postMessage 将失败。 默认情况下为 true。

#### IsZoomControlEnabled 

IsZoomControlEnabled 属性用于阻止用户影响 Web 视图的缩放。

> 公共 bool [IsZoomControlEnabled](#iszoomcontrolenabled)

默认情况下为 true。 当禁用时，用户将无法使用 ctrl +/-或 ctrl + 鼠标滚轮进行缩放，但缩放可通过 ZoomFactor API 设置。

