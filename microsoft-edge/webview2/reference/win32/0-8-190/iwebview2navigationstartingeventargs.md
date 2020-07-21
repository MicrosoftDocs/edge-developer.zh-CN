---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 5996f0eff4db17530750eb39c7693ea0f8496a4d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885883"
---
# 0.8.355-接口 IWebView2NavigationStartingEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2NavigationStartingEventArgs
  : public IUnknown
```

NavigationStarting 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 所请求的导航的 uri。
[get_IsUserInitiated](#get_isuserinitiated) | 当导航是通过用户手势启动时（相对于编程导航）时，为 True。
[get_IsRedirected](#get_isredirected) | 当导航被重定向时为 True。
[get_RequestHeaders](#get_requestheaders) | 导航的 HTTP 请求标头。
[get_Cancel](#get_cancel) | 主持人可以将此标志设置为取消导航。
[put_Cancel](#put_cancel) | 设置 "取消" 属性。

## 成员

#### get_Uri 

所请求的导航的 uri。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### get_IsUserInitiated 

当导航是通过用户手势启动时（相对于编程导航）时，为 True。

> public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL * IsUserInitiated）

#### get_IsRedirected 

当导航被重定向时为 True。

> public HRESULT [get_IsRedirected](#get_isredirected)（BOOL * IsRedirected）

#### get_RequestHeaders 

导航的 HTTP 请求标头。

> 公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md) * * RequestHeaders）

注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。

#### get_Cancel 

主持人可以将此标志设置为取消导航。

> 公共 HRESULT [get_Cancel](#get_cancel)（BOOL * 取消）

如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。 出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。 这意味着可以在导航的请求中设置和使用 cookie。

#### put_Cancel 

设置 "取消" 属性。

> 公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）

