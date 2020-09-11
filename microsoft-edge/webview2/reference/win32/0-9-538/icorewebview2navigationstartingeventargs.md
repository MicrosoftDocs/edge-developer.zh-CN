---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationStartingEventArgs
ms.openlocfilehash: 8bf2cf37ef76256987a52fd5491e5c995244dd65
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011298"
---
# 0.9.579-接口 ICoreWebView2NavigationStartingEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

> 公共 HRESULT [get_Cancel](#get_cancel) (BOOL * Cancel) 

如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。 出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。 这意味着可以在导航的请求中设置和使用 cookie。

#### get_IsRedirected 

当导航被重定向时为 True。

> 公共 HRESULT [get_IsRedirected](#get_isredirected) (BOOL * IsRedirected) 

#### get_IsUserInitiated 

当导航是通过用户手势启动时（相对于编程导航）时，为 True。

> 公共 HRESULT [get_IsUserInitiated](#get_isuserinitiated) (BOOL * IsUserInitiated) 

#### get_NavigationId 

导航的 ID。

> 公共 HRESULT [get_NavigationId](#get_navigationid) (UINT64 * navigation_id) 

#### get_RequestHeaders 

导航的 HTTP 请求标头。

> 公共 HRESULT [get_RequestHeaders](#get_requestheaders) ([ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) * * RequestHeaders) 

注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。

#### get_Uri 

所请求的导航的 uri。

> 公共 HRESULT [get_Uri](#get_uri) (LPWSTR * Uri) 

#### put_Cancel 

设置 "取消" 属性。

> public HRESULT [put_Cancel](#put_cancel) (BOOL Cancel) 

