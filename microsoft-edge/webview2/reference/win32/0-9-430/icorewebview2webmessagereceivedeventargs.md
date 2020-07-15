---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebMessageReceivedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: c619c066151941f1177d55c973569c89f03daa2e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880162"
---
# 0.9.430-接口 ICoreWebView2WebMessageReceivedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2WebMessageReceivedEventArgs
  : public IUnknown
```

WebMessageReceived 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Source](#get_source) | 发送此 web 消息的文档的 URI。
[get_WebMessageAsJson](#get_webmessageasjson) | 从 web 视图内容发布到转换为 JSON 字符串的主机的消息。
[TryGetWebMessageAsString](#trygetwebmessageasstring) | 如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

## 成员

#### get_Source 

发送此 web 消息的文档的 URI。

> 公共 HRESULT [get_Source](#get_source)（LPWSTR * Source）

#### get_WebMessageAsJson 

从 web 视图内容发布到转换为 JSON 字符串的主机的消息。

> 公共 HRESULT [get_WebMessageAsJson](#get_webmessageasjson)（LPWSTR * WebMessageAsJson）

使用此对象通过 JavaScript 对象进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsJson 值：

```cpp
postMessage({'a': 'b'})      L"{\"a\": \"b\"}"
postMessage(1.2)             L"1.2"
postMessage('example')       L"\"example\""
```

#### TryGetWebMessageAsString 

如果从 web 视图内容发布到主机的消息是字符串类型，此方法将返回该字符串的值。

> 公共 HRESULT [TryGetWebMessageAsString](#trygetwebmessageasstring)（LPWSTR * webMessageAsString）

如果发布的消息是其他类型的 JavaScript 类型，则此方法将失败，并 E_INVALIDARG。 使用此操作通过简单字符串进行通信。

例如，以下 postMessage 调用将产生以下 WebMessageAsString 值：

```cpp
postMessage({'a': 'b'})      E_INVALIDARG
postMessage(1.2)             E_INVALIDARG
postMessage('example')       L"example"
```

