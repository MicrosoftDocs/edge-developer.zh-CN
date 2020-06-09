---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 0f14f8d281d4729d797eb5271a19cff67becafab
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698510"
---
# interface ICoreWebView2HistoryChangedEventHandler 

```
interface ICoreWebView2HistoryChangedEventHandler
  : public IUnknown
```

调用方实现此接口以接收 HistoryChanged 事件。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[调用](#invoke) | 没有事件参数，args 参数将为 null。

## 成员

#### 调用 

没有事件参数，args 参数将为 null。

> 公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) * web 视图、IUnknown * 参数）

