---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CreateWebViewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 381f46c6682a77905d9caa720e4ba9b2d1d531b7
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886143"
---
# 0.8.355-接口 IWebView2CreateWebViewCompletedHandler 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CreateWebViewCompletedHandler
  : public IUnknown
```

调用方实现此接口以接收通过 CreateWebView 创建的 Web 视图。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[调用](#invoke) | 调用以向实施者提供相应的异步方法调用的完成状态和结果。

## 成员

#### 调用 

调用以向实施者提供相应的异步方法调用的完成状态和结果。

> 公共 HRESULT[调用](#invoke)（hresult 结果，[IWebView2WebView](IWebView2WebView.md) * web 视图）

