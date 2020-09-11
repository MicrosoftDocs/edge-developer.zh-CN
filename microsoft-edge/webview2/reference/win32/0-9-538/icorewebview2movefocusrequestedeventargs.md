---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2MoveFocusRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2MoveFocusRequestedEventArgs
ms.openlocfilehash: 7d86b0129c126b39ae8200550a024819e2004b49
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010024"
---
# 0.9.579-接口 ICoreWebView2MoveFocusRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

MoveFocusRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Handled](#get_handled) | 指示事件是否已由应用处理。
[get_Reason](#get_reason) | Web 视图触发 MoveFocus 请求事件的原因。
[put_Handled](#put_handled) | 设置已处理的属性。

## 成员

#### get_Handled 

指示事件是否已由应用处理。

> 公共 HRESULT [get_Handled](#get_handled) (BOOL * 值) 

如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。 当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。 默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。 如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。

#### get_Reason 

Web 视图触发 MoveFocus 请求事件的原因。

> public HRESULT [get_Reason](#get_reason) (COREWEBVIEW2_MOVE_FOCUS_REASON * 值) 

#### put_Handled 

设置已处理的属性。

>  (布尔值的公共 HRESULT [put_Handled](#put_handled)) 

