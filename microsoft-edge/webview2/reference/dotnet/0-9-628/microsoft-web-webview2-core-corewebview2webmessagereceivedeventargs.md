---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebMessageReceivedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: ab273337307eeef6e8842d337296756877939aff
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011658"
---
# CoreWebView2WebMessageReceivedEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

WebMessageReceived 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[来源](#source) | 发送此 web 消息的文档的 URI。
[WebMessageAsJson](#webmessageasjson) | 从 Web 视图内容发布到转换为 JSON 字符串的主机的消息。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | 如果从 Web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

## 成员

#### 来源 

发送此 web 消息的文档的 URI。

> 公共字符串 [源](#source)

#### WebMessageAsJson 

从 Web 视图内容发布到转换为 JSON 字符串的主机的消息。

> 公共字符串 [WebMessageAsJson](#webmessageasjson)

使用此对象通过 JavaScript 对象进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

如果从 Web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

> 公共字符串 [TryGetWebMessageAsString](#trygetwebmessageasstring) ( # A1

如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。 使用此操作通过简单字符串进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

