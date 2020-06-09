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
ms.openlocfilehash: 072ce10e7ac1f34238278366c3e8799a3268cb0b
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697530"
---
# CoreWebView2WebResourceRequestedEventArgs 类的 WebView2 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

