---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 0f3564fa96bc1c13527cbf3b26ce92114d44eae4
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653006"
---
# interface IWebView2HttpResponseHeaders 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2HttpResponseHeaders
  : public IUnknown
```

HTTP 响应标头。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[AppendHeader](#appendheader) | 追加名称和值的标题行。
[Contains](#contains) | 检查标题是否包含与标题名称匹配的条目。
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

#### GetHeaders 

获取与名称匹配的标头值。

> 公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) * * 迭代器）

#### GetIterator 

获取整个响应标头集合上的迭代器。

> 公共 HRESULT [GetIterator](#getiterator)（[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) * * 迭代器）

