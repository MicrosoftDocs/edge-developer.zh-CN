---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 52218ddcbecdaf3bdb736af877493c85d4460c10
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878041"
---
# 0.8.355-接口 IWebView2WebView2 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2WebView2
  : public IUnknown
```

由主 Web 视图对象实现的附加功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[停止](#stop) | 停止所有导航和挂起的资源提取。

你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。 有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。

## 成员

#### 停止 

停止所有导航和挂起的资源提取。

> 公共 HRESULT[停止](#stop)（）

