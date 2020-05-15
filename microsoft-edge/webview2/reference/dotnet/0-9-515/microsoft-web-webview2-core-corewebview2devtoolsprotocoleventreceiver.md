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
ms.openlocfilehash: 23ee363fd90416d07c76644879a5f4b6cc2acabe
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653119"
---
# CoreWebView2DevToolsProtocolEventReceiver 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

将为特定的 DevTools 协议事件创建一个接收器，并允许你订阅和取消订阅该事件。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived) | 订阅 DevToolsProtocol 事件。

通过 GetDevToolsProtocolEventReceiver 从 Web 视图对象中获取。

## 成员

#### DevToolsProtocolEventReceived 

订阅 DevToolsProtocol 事件。

> 公共事件 EventHandler< [CoreWebView2DevToolsProtocolEventReceivedEventArgs](microsoft-web-webview2-core-corewebview2devtoolsprotocoleventreceivedeventargs.md)  >  [DevToolsProtocolEventReceived](#devtoolsprotocoleventreceived)

每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。 将使用包含 DevTools 协议事件参数对象的事件参数对象作为 JSON 字符串调用调用。

