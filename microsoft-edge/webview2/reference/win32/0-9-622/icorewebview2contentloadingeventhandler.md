---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2ContentLoadingEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ContentLoadingEventHandler
ms.openlocfilehash: 305f9fe0071385d2eaf83b26bd3cc2ee553df6df
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011802"
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

> public HRESULT [调用](#invoke) ([ICoreWebView2](icorewebview2.md) * sender、 [ICoreWebView2ContentLoadingEventArgs](icorewebview2contentloadingeventargs.md) * 参数) 

