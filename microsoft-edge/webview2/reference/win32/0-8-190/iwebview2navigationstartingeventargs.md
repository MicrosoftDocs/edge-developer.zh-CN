---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 8bc625d12cc3b3ebe06970fd282dd8f60bcabd22
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878398"
---
# 0.8.355-接口 IWebView2NavigationStartingEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

