---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2HttpRequestHeaders 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 1441d5a45caf4e8f561de2487438b66e067760f6
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011636"
---
# CoreWebView2HttpRequestHeaders 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

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

> public bool [包含](#contains) (的字符串名称) 

#### GetHeader 

获取与名称匹配的标头值。

>  (字符串名称的公共字符串 [GetHeader](#getheader)) 

#### GetHeaders 

通过迭代器获取与名称匹配的标头值。

> public CoreWebView2HttpHeadersCollectionIterator [GetHeaders](#getheaders) (字符串名称) 

#### GetIterator 

获取请求标头集合上的迭代器。

> 公共 CoreWebView2HttpHeadersCollectionIterator [GetIterator](#getiterator) ( # A1

#### RemoveHeader 

删除与名称匹配的标题。

> public void [RemoveHeader](#removeheader) (字符串名称) 

#### SetHeader 

添加或更新与名称匹配的标题。

> public void [SetHeader](#setheader) (字符串名称，字符串值) 

