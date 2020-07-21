---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 1e0148c0d1e27cb4f1c52fb6ad55cc2e7613a94b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885966"
---
# 0.8.355-接口 IWebView2HttpRequestHeaders 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpRequestHeaders
  : public IUnknown
```

HTTP 请求标头。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[GetHeader](#getheader) | 获取与名称匹配的标头值。
[Contains](#contains) | 检查标题是否包含与标头名称匹配的条目。
[SetHeader](#setheader) | 添加或更新与名称匹配的标题。
[RemoveHeader](#removeheader) | 删除与名称匹配的标题。
[GetIterator](#getiterator) | 获取请求标头集合上的迭代器。

用于检查 WebResourceRequested 事件和 NavigationStarting 事件上的 HTTP 请求。 注意，你可以从 WebResourceRequested 事件（而不是从 NavigationStarting 事件）修改 HTTP 请求标头。

## 成员

#### GetHeader 

获取与名称匹配的标头值。

> 公共 HRESULT [GetHeader](#getheader)（LPCWSTR NAME，LPWSTR * value）

#### Contains 

检查标题是否包含与标头名称匹配的条目。

> public HRESULT[包含](#contains)（LPCWSTR NAME，BOOL * 包含）

#### SetHeader 

添加或更新与名称匹配的标题。

> 公共 HRESULT [SetHeader](#setheader)（LPCWSTR NAME，LPCWSTR 值）

#### RemoveHeader 

删除与名称匹配的标题。

> 公共 HRESULT [RemoveHeader](#removeheader)（LPCWSTR name）

#### GetIterator 

获取请求标头集合上的迭代器。

> 公共 HRESULT [GetIterator](#getiterator)（[IWebView2HttpHeadersCollectionIterator](IWebView2HttpHeadersCollectionIterator.md) * * 迭代器）

