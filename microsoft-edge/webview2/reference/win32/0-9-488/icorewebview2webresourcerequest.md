---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2WebResourceRequest
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b60df5b7493ab095c6e71f7d28dbb6ec78d39052
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10883768"
---
# 0.9.515-接口 ICoreWebView2WebResourceRequest 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequest
  : public IUnknown
```

与 WebResourceRequested 事件一起使用的 HTTP 请求。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Content](#get_content) | 作为流的 HTTP 请求消息正文。
[get_Headers](#get_headers) | 可变 HTTP 请求标头。
[get_Method](#get_method) | HTTP 请求方法。
[get_Uri](#get_uri) | 请求 URI。
[put_Content](#put_content) | 设置内容属性。
[put_Method](#put_method) | 设置 Method 属性。
[put_Uri](#put_uri) | 设置 Uri 属性。

## 成员

#### get_Content 

作为流的 HTTP 请求消息正文。

> 公共 HRESULT [get_Content](#get_content)（IStream * * 内容）

发布数据将在此处显示。 如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。 流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。 Null 表示没有内容数据。 将应用 IStream 语义（返回 S_OK 以读取调用，直到所有数据用尽为止）

#### get_Headers 

可变 HTTP 请求标头。

> 公共 HRESULT [get_Headers](#get_headers)（[ICoreWebView2HttpRequestHeaders](icorewebview2httprequestheaders.md) * * 标题）

#### get_Method 

HTTP 请求方法。

> 公共 HRESULT [get_Method](#get_method)（LPWSTR * 方法）

#### get_Uri 

请求 URI。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### put_Content 

设置内容属性。

> 公共 HRESULT [put_Content](#put_content)（IStream * 内容）

#### put_Method 

设置 Method 属性。

> public HRESULT [put_Method](#put_method)（LPCWSTR 方法）

#### put_Uri 

设置 Uri 属性。

> 公共 HRESULT [put_Uri](#put_uri)（LPCWSTR Uri）

