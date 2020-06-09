---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: effceb6fafb062b1747f39876b8d2a5e02721aa8
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697271"
---
# interface ICoreWebView2HttpRequestHeaders 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2HttpRequestHeaders
  : public IUnknown
```

HTTP 请求标头。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[Contains](#contains) | 检查标题是否包含与标头名称匹配的条目。
[GetHeader](#getheader) | 获取与名称匹配的标头值。
[GetHeaders](#getheaders) | 通过迭代器获取与名称匹配的标头值。
[GetIterator](#getiterator) | 获取请求标头集合上的迭代器。
[RemoveHeader](#removeheader) | 删除与名称匹配的标题。
[SetHeader](#setheader) | 添加或更新与名称匹配的标题。

用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。 注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。

## 成员

#### Contains 

检查标题是否包含与标头名称匹配的条目。

> public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL * 包含）

#### GetHeader 

获取与名称匹配的标头值。

> 公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR * value）

#### GetHeaders 

通过迭代器获取与名称匹配的标头值。

> 公共 HRESULT [GetHeaders](#getheaders)（LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * 迭代器）

#### GetIterator 

获取请求标头集合上的迭代器。

> 公共 HRESULT [GetIterator](#getiterator)（[ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * 迭代器）

#### RemoveHeader 

删除与名称匹配的标题。

> 公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）

#### SetHeader 

添加或更新与名称匹配的标题。

> 公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）

