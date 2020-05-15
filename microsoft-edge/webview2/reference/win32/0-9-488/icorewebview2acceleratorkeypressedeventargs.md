---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/28/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 10311cf26b66e824447461530f1ce0870ea01ceb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652917"
---
# interface ICoreWebView2AcceleratorKeyPressedEventArgs 

```
interface ICoreWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

AcceleratorKeyPressed 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Handled](#get_handled) | 在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。
[get_KeyEventKind](#get_keyeventkind) | 导致引发事件的键事件类型。
[get_KeyEventLParam](#get_keyeventlparam) | 窗口消息附带的 LPARAM 值。
[get_PhysicalKeyStatus](#get_physicalkeystatus) | 表示在窗口消息的 LPARAM 中传递的信息的结构。
[get_VirtualKey](#get_virtualkey) | 已按下或释放的键的 Win32 虚拟键代码。
[put_Handled](#put_handled) | 设置已处理的属性。

## 成员

#### get_Handled 

在 AcceleratorKeyPressedEvent 处理程序调用期间，Web 视图将被阻止，以等待该加速器是否将由主机处理。

> 公共 HRESULT [get_Handled](#get_handled)（BOOL * 已处理）

如果已处理的属性设置为 TRUE，则这将阻止 Web 视图对此加速键执行默认操作。 否则，Web 视图将对加速键执行默认操作。

#### get_KeyEventKind 

导致引发事件的键事件类型。

> public HRESULT [get_KeyEventKind](#get_keyeventkind)（COREWEBVIEW2_KEY_EVENT_KIND * KeyEventKind）

#### get_KeyEventLParam 

窗口消息附带的 LPARAM 值。

> 公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT * lParam）

请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。

#### get_PhysicalKeyStatus 

表示在窗口消息的 LPARAM 中传递的信息的结构。

> public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（COREWEBVIEW2_PHYSICAL_KEY_STATUS * PhysicalKeyStatus）

#### get_VirtualKey 

已按下或释放的键的 Win32 虚拟键代码。

> public HRESULT [get_VirtualKey](#get_virtualkey)（UINT * VirtualKey）

这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。 可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。

#### put_Handled 

设置已处理的属性。

> 公共的 HRESULT [put_Handled](#put_handled)（BOOL 已处理）

