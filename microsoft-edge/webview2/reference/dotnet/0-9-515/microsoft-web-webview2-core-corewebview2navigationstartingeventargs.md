---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 8b7ac3ab27cf5a2d9e80a77eabc488599820a02f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653230"
---
# CoreWebView2NavigationStartingEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

NavigationStarting 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[取消](#cancel) | 主持人可以将此标志设置为取消导航。
[IsRedirected](#isredirected) | 当导航被重定向时为 True。
[IsUserInitiated](#isuserinitiated) | 当导航是通过用户手势启动时（相对于编程导航）时，为 True。
[NavigationId](#navigationid) | 导航的 ID。
[RequestHeaders](#requestheaders) | 导航的 HTTP 请求标头。
[Uri](#uri) | 所请求的导航的 uri。

## 成员

#### 取消 

主持人可以将此标志设置为取消导航。

> 公共 bool[取消](#cancel)

如果设置，则将显示为 "未发生导航"，并且当前页面的内容将保持不变。 出于性能原因，可能会发生 "获取 HTTP 请求"，而主机响应。 这意味着可以在导航的请求中设置和使用 cookie。

#### IsRedirected 

当导航被重定向时为 True。

> 公共 bool [IsRedirected](#isredirected)

#### IsUserInitiated 

当导航是通过用户手势启动时（相对于编程导航）时，为 True。

> 公共 bool [IsUserInitiated](#isuserinitiated)

#### NavigationId 

导航的 ID。

> 公共 ulong [NavigationId](#navigationid)

#### RequestHeaders 

导航的 HTTP 请求标头。

> 公共 HttpRequestHeaders [RequestHeaders](#requestheaders)

注意，你无法在 NavigationStarting 事件中修改 HTTP 请求标头。

#### Uri 

所请求的导航的 uri。

> 公共字符串[Uri](#uri)

