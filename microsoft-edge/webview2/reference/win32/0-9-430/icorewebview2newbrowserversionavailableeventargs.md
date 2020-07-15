---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2NewBrowserVersionAvailableEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: f59b5acac510b66eae0e1ada51e28b6dd9363ca8
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877852"
---
# 0.9.430-接口 ICoreWebView2NewBrowserVersionAvailableEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2NewBrowserVersionAvailableEventArgs
  : public IUnknown
```

NewBrowserVersionAvailable 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_NewVersion](#get_newversion) | 当前[ICoreWebView2Environment](ICoreWebView2Environment.md)的浏览器版本信息。

## 成员

#### get_NewVersion 

当前[ICoreWebView2Environment](ICoreWebView2Environment.md)的浏览器版本信息。

> 公共 HRESULT [get_NewVersion](#get_newversion)（LPWSTR * 新版）

