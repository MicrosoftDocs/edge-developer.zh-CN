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
ms.openlocfilehash: f9bedb19620b0669d4aac35be4786702940b2a72
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652891"
---
# CoreWebView2WebMessageReceivedEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

WebMessageReceived 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[来源](#source) | 发送此 web 消息的文档的 URI。
[WebMessageAsJson](#webmessageasjson) | 从 web 视图内容发布到转换为 JSON 字符串的主机的消息。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | 如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

## 成员

#### 来源 

发送此 web 消息的文档的 URI。

> 公共字符串[源](#source)

#### WebMessageAsJson 

从 web 视图内容发布到转换为 JSON 字符串的主机的消息。

> 公共字符串[WebMessageAsJson](#webmessageasjson)

使用此对象通过 JavaScript 对象进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

> 公共字符串[TryGetWebMessageAsString](#trygetwebmessageasstring)（）

如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。 使用此操作通过简单字符串进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

