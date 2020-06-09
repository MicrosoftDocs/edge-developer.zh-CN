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
ms.openlocfilehash: 8bf8dcf40524425a7ef166c5007d60de738efb67
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698480"
---
# interface ICoreWebView2ContentLoadingEventHandler 

```
interface ICoreWebView2ContentLoadingEventHandler
  : public IUnknown
```

调用方实现此接口以接收 ContentLoading 事件。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[调用](#invoke) | 调用以向实施者提供对应事件的事件参数。

## 成员

#### 调用 

调用以向实施者提供对应事件的事件参数。

> 公共 HRESULT[调用](#invoke)（[ICoreWebView2](icorewebview2.md) * web 视图， [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) * 参数）

