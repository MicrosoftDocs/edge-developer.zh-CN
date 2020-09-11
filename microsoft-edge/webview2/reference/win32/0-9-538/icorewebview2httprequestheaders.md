---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2HttpRequestHeaders
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2HttpRequestHeaders
ms.openlocfilehash: 7a59511e9d899fe4a66f2671f67f7c7cd7f101df
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011315"
---
# 0.9.579-接口 ICoreWebView2HttpRequestHeaders 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

> public HRESULT [包含](#contains) (LPCWSTR NAME，BOOL * 包含) 

#### GetHeader 

获取与名称匹配的标头值。

> public HRESULT [GetHeader](#getheader) (LPCWSTR NAME，LPWSTR * value) 

#### GetHeaders 

通过迭代器获取与名称匹配的标头值。

> 公共 HRESULT [GetHeaders](#getheaders) (LPCWSTR Name、 [ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * 迭代器) 

#### GetIterator 

获取请求标头集合上的迭代器。

> 公共 HRESULT [GetIterator](#getiterator) ([ICoreWebView2HttpHeadersCollectionIterator](icorewebview2httpheaderscollectioniterator.md) * * 迭代器) 

#### RemoveHeader 

删除与名称匹配的标题。

> 公共 HRESULT [RemoveHeader](#removeheader) (LPCWSTR 名称) 

#### SetHeader 

添加或更新与名称匹配的标题。

> public HRESULT [SetHeader](#setheader) (LPCWSTR NAME，LPCWSTR 值) 

