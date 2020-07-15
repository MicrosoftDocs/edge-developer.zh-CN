---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 95c0a881a8a201d21ca9cb2662c282b36efa2ed3
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878104"
---
# 0.8.355-接口 IWebView2WebResourceResponse 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2WebResourceResponse
  : public IUnknown
```

与 WebResourceRequested 事件一起使用的 HTTP 响应。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Content](#get_content) | 流形式的 HTTP 响应内容。
[put_Content](#put_content) | 设置内容属性。
[get_Headers](#get_headers) | 已重写 HTTP 响应标头。
[get_StatusCode](#get_statuscode) | HTTP 响应状态代码。
[put_StatusCode](#put_statuscode) | 设置 StatusCode 属性。
[get_ReasonPhrase](#get_reasonphrase) | HTTP 响应原因短语。
[put_ReasonPhrase](#put_reasonphrase) | 设置 ReasonPhrase 属性。

## 成员

#### get_Content 

流形式的 HTTP 响应内容。

> 公共 HRESULT [get_Content](#get_content)（IStream * * 内容）

在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。 流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。 Null 表示没有内容数据。 将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）

#### put_Content 

设置内容属性。

> 公共 HRESULT [put_Content](#put_content)（IStream * 内容）

#### get_Headers 

已重写 HTTP 响应标头。

> 公共 HRESULT [get_Headers](#get_headers)（[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md) * * 标题）

#### get_StatusCode 

HTTP 响应状态代码。

> 公共 HRESULT [get_StatusCode](#get_statuscode)（Int * StatusCode）

#### put_StatusCode 

设置 StatusCode 属性。

> 公共 HRESULT [put_StatusCode](#put_statuscode)（int StatusCode）

#### get_ReasonPhrase 

HTTP 响应原因短语。

> 公共 HRESULT [get_ReasonPhrase](#get_reasonphrase)（LPWSTR * ReasonPhrase）

#### put_ReasonPhrase 

设置 ReasonPhrase 属性。

> public HRESULT [put_ReasonPhrase](#put_reasonphrase)（LPCWSTR ReasonPhrase）

