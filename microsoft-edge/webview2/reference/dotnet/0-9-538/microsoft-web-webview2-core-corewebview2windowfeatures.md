---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2WindowFeatures 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 4866626111908eae9800da0baabec0356d5d4bf8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879651"
---
# CoreWebView2WindowFeatures 类的 WebView2 

> [!NOTE]
> 这是我们的 SDK 版本[0.9.538](../../../releasenotes.md#09538)预发布版附带的[实验性 API](../../../concepts/versioning.md#experimental-apis) 。

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

Web 视图弹出窗口的窗口功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[高度](#height) | 窗口的高度。
[向左](#left) | 窗口的左侧位置。
[菜单栏](#menubar) | 是否显示菜单栏。
[滚动条](#scrollbars) | 是否显示滚动条。
[状态](#status) | 是否添加状态栏。
[工具栏](#toolbar) | 是否显示浏览器工具栏。
[Top](#top) | 窗口的顶部位置。
[宽度](#width) | 窗口的宽度。
[HasPosition](#hasposition) | 具有指定的 left 和 top 值。
[HasSize](#hassize) | 具有指定的高度和宽度值。

## 成员

#### 高度 

窗口的高度。

> 公共 uint[高度](#height)

#### 向左 

窗口的左侧位置。

> public uint [Left](#left)

如果 HasPosition 为 false，则不会失败。

#### 菜单栏 

是否显示菜单栏。

> 公共 int[菜单栏](#menubar)

#### 滚动条 

是否显示滚动条。

> 公共 int[滚动条](#scrollbars)

#### 状态 

是否添加状态栏。

> 公共 int[状态](#status)

#### 工具栏 

是否显示浏览器工具栏。

> 公共 int[工具栏](#toolbar)

#### Top 

窗口的顶部位置。

> 公共 uint[顶部](#top)

如果 HasPosition 为 false，则不会失败。

#### 宽度 

窗口的宽度。

> 公共 uint[宽度](#width)

#### HasPosition 

具有指定的 left 和 top 值。

> 公共 int [HasPosition](#hasposition)（）

#### HasSize 

具有指定的高度和宽度值。

> 公共 int [HasSize](#hassize)（）

