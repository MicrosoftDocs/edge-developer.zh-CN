---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 28ed6db251095e2baf6474950c6839dc4a5a8633
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653238"
---
# CoreWebView2PhysicalKeyStatus 结构的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[IsExtendedKey](#isextendedkey) | 指示该键是否为扩展键。
[IsKeyReleased](#iskeyreleased) | 切换状态。
[IsMenuKeyDown](#ismenukeydown) | 上下文代码。
[RepeatCount](#repeatcount) | 当前消息的重复次数。
[ScanCode](#scancode) | 扫描代码。
[WasKeyDown](#waskeydown) | 以前的键状态。

有关详细信息，请参阅 WM_KEYDOWN 的文档 [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown) 。

## 成员

#### IsExtendedKey 

指示该键是否为扩展键。

> 公共 int [IsExtendedKey](#isextendedkey)

#### IsKeyReleased 

切换状态。

> 公共 int [IsKeyReleased](#iskeyreleased)

#### IsMenuKeyDown 

上下文代码。

> 公共 int [IsMenuKeyDown](#ismenukeydown)

#### RepeatCount 

当前消息的重复次数。

> 公共 uint [RepeatCount](#repeatcount)

#### ScanCode 

扫描代码。

> 公共 uint [ScanCode](#scancode)

#### WasKeyDown 

以前的键状态。

> 公共 int [WasKeyDown](#waskeydown)

