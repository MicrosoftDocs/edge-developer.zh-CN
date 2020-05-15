---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 2e3afec26b0e09a80182118f74b6f50733b0c71a
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652993"
---
# interface IWebView2MoveFocusRequestedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2MoveFocusRequestedEventArgs
  : public IUnknown
```

MoveFocusRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Reason](#get_reason) | Web 视图触发 MoveFocus 请求事件的原因。
[get_Handled](#get_handled) | 指示事件是否已由应用处理。
[put_Handled](#put_handled) | 设置已处理的属性。

## 成员

#### get_Reason 

Web 视图触发 MoveFocus 请求事件的原因。

> public HRESULT [get_Reason](#get_reason)（WEBVIEW2_MOVE_FOCUS_REASON * 值）

#### get_Handled 

指示事件是否已由应用处理。

> 公共 HRESULT [get_Handled](#get_handled)（布尔 * 值）

如果应用已将焦点移动到所需位置，则应将 "已处理" 属性设置为 TRUE。 当已处理的属性在事件处理程序返回后为 false 时，将采取默认操作。 默认操作是尝试在应用中查找下一个制表位子窗口，然后尝试将焦点移动到该窗口。 如果没有其他此类窗口将焦点移至，则焦点将在 web 视图的 web 内容中循环。

#### put_Handled 

设置已处理的属性。

> public HRESULT [put_Handled](#put_handled)（布尔值）

