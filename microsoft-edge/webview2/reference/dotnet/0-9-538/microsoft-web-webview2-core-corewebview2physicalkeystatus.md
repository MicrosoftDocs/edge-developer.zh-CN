---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2PhysicalKeyStatus 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 280fe2d970d78bf1ea7a79b21f5081510ee27053
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878769"
---
# CoreWebView2PhysicalKeyStatus 结构的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

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

