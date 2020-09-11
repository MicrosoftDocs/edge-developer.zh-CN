---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2。 CoreWebView2NavigationStartingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5f63cd8a9dc16ee82d77fe4b5a0b705eb79e7c6f
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010933"
---
# 0.9.579-WebView2 的 CoreWebView2NavigationStartingEventArgs 类 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

> 公共 bool [取消](#cancel)

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

> 公共字符串 [Uri](#uri)

