---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationStartingEventArgs
ms.openlocfilehash: 8f4f366d02280163141c9591d04d72c5f5d9d082
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879756"
---
# interface ICoreWebView2NavigationStartingEventArgs 

```
interface ICoreWebView2NavigationStartingEventArgs
  : public IUnknown
```

NavigationStarting 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Cancel](#get_cancel) | 主持人可以将此标志设置为取消导航。
[get_IsRedirected](#get_isredirected) | 当导航被重定向时为 True。
[get_IsUserInitiated](#get_isuserinitiated) | 当导航是通过用户手势启动时（相对于编程导航）时，为 True。
[get_NavigationId](#get_navigationid) | 导航的 ID。
[get_RequestHeaders](#get_requestheaders) | 导航的 HTTP 请求标头。
[get_Uri](#get_uri) | 所请求的导航的 uri。
[put_Cancel](#put_cancel) | 设置 "取消" 属性。

## 成员

#### get_Cancel 

主持人可以将此标志设置为取消导航。

> 公共 HRESULT [get_Cancel](#get_cancel)（BOOL * 取消）

如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。 出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。 这意味着可以在导航的请求中设置和使用 cookie。

#### get_IsRedirected 

当导航被重定向时为 True。

> public HRESULT [get_IsRedirected](#get_isredirected)（BOOL * IsRedirected）

#### get_IsUserInitiated 

当导航是通过用户手势启动时（相对于编程导航）时，为 True。

> public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL * IsUserInitiated）

#### get_NavigationId 

导航的 ID。

> 公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 * navigation_id）

#### get_RequestHeaders 

导航的 HTTP 请求标头。

> 公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) * * RequestHeaders）

注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。

#### get_Uri 

所请求的导航的 uri。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### put_Cancel 

设置 "取消" 属性。

> 公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）

