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
ms.openlocfilehash: a02a7ac3e31f959e80d5a3bdc41e39f653b9949c
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653139"
---
# interface IWebView2NewVersionAvailableEventHandler 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2NewVersionAvailableEventHandler
  : public IUnknown
```

调用方实现此接口以接收 NewVersionAvailable 事件。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[调用](#invoke) | 调用以向实施者提供对应事件的事件参数。

使用[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md)的 get_NewVersion 方法获取新的版本号。

## 成员

#### 调用 

调用以向实施者提供对应事件的事件参数。

> public HRESULT [Invoke](#invoke)（[IWebView2Environment](IWebView2Environment.md) * webviewEnvironment，[IWebView2NewVersionAvailableEventArgs](IWebView2NewVersionAvailableEventArgs.md) * 参数）

