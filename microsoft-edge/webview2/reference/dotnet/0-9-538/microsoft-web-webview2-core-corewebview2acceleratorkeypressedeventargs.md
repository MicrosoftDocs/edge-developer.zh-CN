---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2AcceleratorKeyPressedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: ef1ca9707bba15fdaf8f37a306b56fdfc2c34588
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878979"
---
# CoreWebView2AcceleratorKeyPressedEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

AcceleratorKeyPressed 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[Handled](#handled) | 在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。
[KeyEventKind](#keyeventkind) | 导致引发事件的键事件类型。
[KeyEventLParam](#keyeventlparam) | 窗口消息附带的 LPARAM 值。
[PhysicalKeyStatus](#physicalkeystatus) | 表示在窗口消息的 LPARAM 中传递的信息的结构。
[VirtualKey](#virtualkey) | 已按下或释放的键的 Win32 虚拟键代码。

## 成员

#### Handled 

在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。

> 公共 bool 已[处理](#handled)

如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。 否则，Web 视图将对加速键执行默认操作。

#### KeyEventKind 

导致引发事件的键事件类型。

> 公共[CoreWebView2KeyEventKind](./namespace-microsoft-web-webview2-core.md) [KeyEventKind](#keyeventkind)

#### KeyEventLParam 

窗口消息附带的 LPARAM 值。

> 公共 int [KeyEventLParam](#keyeventlparam)

请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。

#### PhysicalKeyStatus 

表示在窗口消息的 LPARAM 中传递的信息的结构。

> 公共[CoreWebView2PhysicalKeyStatus](microsoft-web-webview2-core-corewebview2physicalkeystatus.md) [PhysicalKeyStatus](#physicalkeystatus)

#### VirtualKey 

已按下或释放的键的 Win32 虚拟键代码。

> 公共 uint [VirtualKey](#virtualkey)

这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。 可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。

