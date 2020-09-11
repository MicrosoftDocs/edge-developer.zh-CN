---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2DevToolsProtocolEventReceiver 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 42ea3beb51dc315ed7ab3b7b0c04c7414adab2db
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011634"
---
# CoreWebView2DevToolsProtocolEventReceiver 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

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

每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。 将调用一个事件参数对象，该对象包含将 DevTools 协议事件的参数对象作为 JSON 字符串。

