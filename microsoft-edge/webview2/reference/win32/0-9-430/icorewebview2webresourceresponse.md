---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2WebResourceResponse
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 61f731a948dee970731ba3dbe83426cbb40eb831
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883999"
---
# 0.9.430-接口 ICoreWebView2WebResourceResponse 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceResponse
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

> 公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpResponseHeaders](ICoreWebView2HttpResponseHeaders.md) * * 标题）

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

