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
ms.openlocfilehash: 9210a4b70d0e2edf30cbaad906f57b360688dfe8
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652887"
---
# CoreWebView2WebResourceRequestedEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

WebResourceRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[请求](#request) | HTTP 请求。
[ResourceContext](#resourcecontext) | Web 资源请求上下文。
[响应](#response) | HTTP 响应。
[GetDeferral](#getdeferral) | 获取 CoreWebView2Deferral 对象并将事件置于延迟状态。

## 成员

#### 请求 

HTTP 请求。

> 公共 HttpRequestMessage[请求](#request)

#### ResourceContext 

Web 资源请求上下文。

> 公共[CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) [ResourceContext](#resourcecontext)

#### 响应 

HTTP 响应。

> 公共 HttpResponseMessage[响应](#response)

#### GetDeferral 

获取 CoreWebView2Deferral 对象并将事件置于延迟状态。

> 公共[CoreWebView2Deferral](microsoft-web-webview2-core-corewebview2deferral.md) [GetDeferral](#getdeferral)（）

你可以使用 CoreWebView2Deferral 对象在以后的时间完成网络请求。

