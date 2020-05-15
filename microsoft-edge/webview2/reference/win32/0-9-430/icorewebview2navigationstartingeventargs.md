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
ms.openlocfilehash: b0b868b99d3f77679b3684a20e7744d7a22fd715
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652992"
---
# interface ICoreWebView2NavigationStartingEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2NavigationStartingEventArgs
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
[get_NavigationId](#get_navigationid) | 导航的 ID。

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

> 公共 HRESULT [get_RequestHeaders](#get_requestheaders)（[ICoreWebView2HttpRequestHeaders](ICoreWebView2HttpRequestHeaders.md) * * RequestHeaders）

注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。

#### get_Cancel 

主持人可以将此标志设置为取消导航。

> 公共 HRESULT [get_Cancel](#get_cancel)（BOOL * 取消）

如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。 出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。 这意味着可以在导航的请求中设置和使用 cookie。

#### put_Cancel 

设置 "取消" 属性。

> 公共 HRESULT [put_Cancel](#put_cancel)（BOOL 取消）

#### get_NavigationId 

导航的 ID。

> 公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 * navigation_id）

