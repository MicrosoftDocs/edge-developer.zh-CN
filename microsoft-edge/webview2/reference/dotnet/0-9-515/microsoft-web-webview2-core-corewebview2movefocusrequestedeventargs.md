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
ms.openlocfilehash: 3c88108f0e1df89c62c8713ff37f35d0c759cf6c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653178"
---
# CoreWebView2MoveFocusRequestedEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

MoveFocusRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[Handled](#handled) | 指示事件是否已由应用处理。
[原因](#reason) | Web 视图触发 MoveFocus 请求事件的原因。

## 成员

#### Handled 

指示事件是否已由应用处理。

> 公共 bool 已[处理](#handled)

如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。 当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。 默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。 如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。

#### 原因 

Web 视图触发 MoveFocus 请求事件的原因。

> 公共 CoreWebView2MoveFocusReason[原因](#reason)

