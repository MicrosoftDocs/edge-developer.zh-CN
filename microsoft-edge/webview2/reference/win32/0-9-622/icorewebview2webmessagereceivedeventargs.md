---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebMessageReceivedEventArgs
ms.openlocfilehash: 1a541bc5c735f67013464347781de5163a7c01b2
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011787"
---
# interface ICoreWebView2WebMessageReceivedEventArgs 

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

WebMessageReceived 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Source](#get_source) | 发送此 web 消息的文档的 URI。
[get_WebMessageAsJson](#get_webmessageasjson) | 从 Web 视图内容发布到转换为 JSON 字符串的主机的消息。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | 如果从 Web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

## 成员

#### get_Source 

发送此 web 消息的文档的 URI。

> 公共 HRESULT [get_Source](#get_source) (LPWSTR * Source) 

#### get_WebMessageAsJson 

从 Web 视图内容发布到转换为 JSON 字符串的主机的消息。

> 公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson) (LPWSTR * WebMessageAsJson) 

使用此对象通过 JavaScript 对象进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：

```
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

如果从 Web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

> 公共 HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring) (LPWSTR * webMessageAsString) 

如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。 使用此操作通过简单字符串进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：

```
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

