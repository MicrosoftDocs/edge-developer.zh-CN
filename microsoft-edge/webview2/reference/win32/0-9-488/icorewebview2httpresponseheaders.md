---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2HttpResponseHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 1daa6c3cdf03ce160968d43715f12ffa7eb41e84
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885581"
---
# 0.9.515-接口 ICoreWebView2HttpResponseHeaders 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2HttpResponseHeaders
  : public IUnknown
```

HTTP 响应标头。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[AppendHeader](#appendheader) | 追加名称和值的标题行。
[Contains](#contains) | 检查标题是否包含与标题名称匹配的条目。
[GetHeader](#getheader) | 获取与名称匹配的集合中的第一个 header 值。
[GetHeaders](#getheaders) | 获取与名称匹配的标头值。
[GetIterator](#getiterator) | 获取整个响应标头集合上的迭代器。

用于为 WebResourceRequested 事件构造 WebResourceResponse。

## 成员

#### AppendHeader 

追加名称和值的标题行。

> 公共 HRESULT [AppendHeader](#appendheader)（LPCWSTR NAME，LPCWSTR 值）

#### Contains 

检查标题是否包含与标题名称匹配的条目。

> public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL * 包含）

#### GetHeader 

获取与名称匹配的集合中的第一个 header 值。

> 公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR * value）

#### GetHeaders 

获取与名称匹配的标头值。

> 公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * 迭代器）

#### GetIterator 

获取整个响应标头集合上的迭代器。

> 公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * 迭代器）

