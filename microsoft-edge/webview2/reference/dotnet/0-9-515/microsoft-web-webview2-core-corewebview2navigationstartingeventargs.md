---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: ea3936ac1267fa085f62db843f5cac3fad2635b5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879784"
---
# 0.9.515-WebView2 的 CoreWebView2NavigationStartingEventArgs 类 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

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

