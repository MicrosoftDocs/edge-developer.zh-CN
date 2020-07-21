---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWindowFeatures
ms.openlocfilehash: 2672f2aac842fd475f6148c439dbecdacd7793ee
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885401"
---
# interface ICoreWebView2ExperimentalWindowFeatures 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWindowFeatures
  : public IUnknown
```

Web 视图弹出窗口的窗口功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Height](#get_height) | 窗口的高度。
[get_Left](#get_left) | 窗口的左侧位置。 如果 HasPosition 为 false，则不会失败。
[get_MenuBar](#get_menubar) | 是否显示菜单栏。
[get_ScrollBars](#get_scrollbars) | 是否显示滚动条。
[get_Status](#get_status) | 是否添加状态栏。
[get_Toolbar](#get_toolbar) | 是否显示浏览器工具栏。
[get_Top](#get_top) | 窗口的顶部位置。 如果 HasPosition 为 false，则不会失败。
[get_Width](#get_width) | 窗口的宽度。
[HasPosition](#hasposition) | 具有指定的 left 和 top 值。
[HasSize](#hassize) | 具有指定的高度和宽度值。

这些字段与传递到 window 的 "windowFeatures" 相匹配。在中指定的打开[https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)

## 成员

#### get_Height 

窗口的高度。

> 公共 HRESULT [get_Height](#get_height)（UINT32 * Height）

最小值为100。 如果 HasSize 为 false，则不会失败。

#### get_Left 

窗口的左侧位置。 如果 HasPosition 为 false，则不会失败。

> 公共 HRESULT [get_Left](#get_left)（UINT32 * Left）

#### get_MenuBar 

是否显示菜单栏。

> public HRESULT [get_MenuBar](#get_menubar)（BOOL * MenuBar）

#### get_ScrollBars 

是否显示滚动条。

> 公共 HRESULT [get_ScrollBars](#get_scrollbars)（布尔 * 滚动条）

#### get_Status 

是否添加状态栏。

> 公共 HRESULT [get_Status](#get_status)（布尔 * 状态）

#### get_Toolbar 

是否显示浏览器工具栏。

> 公共 HRESULT [get_Toolbar](#get_toolbar)（BOOL * 工具栏）

#### get_Top 

窗口的顶部位置。 如果 HasPosition 为 false，则不会失败。

> 公共 HRESULT [get_Top](#get_top)（UINT32 * Top）

#### get_Width 

窗口的宽度。

> 公共 HRESULT [get_Width](#get_width)（UINT32 * Width）

最小值为100。 如果 HasSize 为 false，则不会失败。

#### HasPosition 

具有指定的 left 和 top 值。

> 公共 HRESULT [HasPosition](#hasposition)（BOOL * HasPosition）

#### HasSize 

具有指定的高度和宽度值。

> 公共 HRESULT [HasSize](#hassize)（BOOL * HasSize）

