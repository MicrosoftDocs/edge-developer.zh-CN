---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2WindowFeatures
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WindowFeatures
ms.openlocfilehash: 90b5a09a752250dc342e7eefad031c9b5b83d345
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011731"
---
# interface ICoreWebView2WindowFeatures 

```
interface ICoreWebView2WindowFeatures
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

这些字段与传递到 window 的 "windowFeatures" 相匹配。在中指定的打开 [https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features](https://developer.mozilla.org/en-US/docs/Web/API/Window/open#Window_features)

## 成员

#### get_Height 

窗口的高度。

> 公共 HRESULT [get_Height](#get_height) (UINT32 * Height) 

最小值为100。 如果 HasSize 为 false，则不会失败。

#### get_Left 

窗口的左侧位置。 如果 HasPosition 为 false，则不会失败。

> 公共 HRESULT [get_Left](#get_left) (UINT32 * Left) 

#### get_MenuBar 

是否显示菜单栏。

>  (BOOL * menuBar 的公共 HRESULT [get_MenuBar](#get_menubar)) 

#### get_ScrollBars 

是否显示滚动条。

> 公共 HRESULT [get_ScrollBars](#get_scrollbars) (BOOL * 滚动条) 

#### get_Status 

是否添加状态栏。

> 公共 HRESULT [get_Status](#get_status) (BOOL * 状态) 

#### get_Toolbar 

是否显示浏览器工具栏。

>  (BOOL * 工具栏的公共 HRESULT [get_Toolbar](#get_toolbar)) 

#### get_Top 

窗口的顶部位置。 如果 HasPosition 为 false，则不会失败。

> 公共 HRESULT [get_Top](#get_top) (UINT32 * Top) 

#### get_Width 

窗口的宽度。

> 公共 HRESULT [get_Width](#get_width) (UINT32 * Width) 

最小值为100。 如果 HasSize 为 false，则不会失败。

#### HasPosition 

具有指定的 left 和 top 值。

> 公共 HRESULT [HasPosition](#hasposition) (BOOL * HasPosition) 

#### HasSize 

具有指定的高度和宽度值。

> 公共 HRESULT [HasSize](#hassize) (BOOL * HasSize) 

