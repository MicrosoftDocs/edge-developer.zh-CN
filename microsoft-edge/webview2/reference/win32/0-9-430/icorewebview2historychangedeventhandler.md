---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 8fd3533d8f479866989f719be6e48c437fae4ddb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653151"
---
# interface ICoreWebView2HistoryChangedEventHandler 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

> 公共 HRESULT[调用](#invoke)（[ICoreWebView2](ICoreWebView2.md) * web 视图、IUnknown * 参数）

