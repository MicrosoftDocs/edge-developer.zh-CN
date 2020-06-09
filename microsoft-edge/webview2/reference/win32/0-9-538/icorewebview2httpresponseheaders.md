---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 508ecacc867330c73132ae7e446b7483ea002f83
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698540"
---
# interface ICoreWebView2HttpResponseHeaders 

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

