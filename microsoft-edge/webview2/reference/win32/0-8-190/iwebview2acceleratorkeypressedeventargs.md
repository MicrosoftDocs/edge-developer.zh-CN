---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2AcceleratorKeyPressedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 885ad6b161fbde6721e1812735ab50d7e0c3e8d9
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885049"
---
# 0.8.355-接口 IWebView2AcceleratorKeyPressedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2AcceleratorKeyPressedEventArgs
  : public IUnknown
```

AcceleratorKeyPressed 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_KeyEventType](#get_keyeventtype) | 导致引发事件的键事件类型。
[get_VirtualKey](#get_virtualkey) | 已按下或释放的键的 Win32 虚拟键代码。
[get_KeyEventLParam](#get_keyeventlparam) | 窗口消息附带的 LPARAM 值。
[get_PhysicalKeyStatus](#get_physicalkeystatus) | 表示在窗口消息的 LPARAM 中传递的信息的结构。
[满足](#handle) | 调用此操作将允许浏览器进程继续。

## 成员

#### get_KeyEventType 

导致引发事件的键事件类型。

> public HRESULT [get_KeyEventType](#get_keyeventtype)（WEBVIEW2_KEY_EVENT_TYPE * KeyEventType）

这是 WEBVIEW2_KEY_EVENT_TYPE_KEY_DOWN、WEBVIEW2_KEY_EVENT_TYPE_KEY_UP、WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_DOWN 或 WEBVIEW2_KEY_EVENT_TYPE_SYSTEM_KEY_UP 之一。

#### get_VirtualKey 

已按下或释放的键的 Win32 虚拟键代码。

> public HRESULT [get_VirtualKey](#get_virtualkey)（UINT * VirtualKey）

这将是 Win32 虚拟键常量之一，例如 VK_RETURN 或（大写字母） ASCII 值（如 "A"）。 可以通过调用 GetKeyState （VK_CONTROL）或 GetKeyState （VK_MENU）来检查 Ctrl 或 Alt 是否按下。

#### get_KeyEventLParam 

窗口消息附带的 LPARAM 值。

> 公共 HRESULT [get_KeyEventLParam](#get_keyeventlparam)（INT * lParam）

请参阅 WM_KEYDOWN 和 WM_KEYUP 消息的文档。

#### get_PhysicalKeyStatus 

表示在窗口消息的 LPARAM 中传递的信息的结构。

> public HRESULT [get_PhysicalKeyStatus](#get_physicalkeystatus)（WEBVIEW2_PHYSICAL_KEY_STATUS * PhysicalKeyStatus）

#### 满足 

调用此操作将允许浏览器进程继续。

> 公共 HRESULT[句柄](#handle)（已处理 BOOL）

传递 TRUE 将阻止浏览器对此加速键执行默认操作。 如果事件处理程序返回时没有调用[句柄（）](#handle)，则它等效于调用句柄（FALSE）。 调用[句柄（）](#handle)之后，或事件处理程序返回将不执行任何操作。

