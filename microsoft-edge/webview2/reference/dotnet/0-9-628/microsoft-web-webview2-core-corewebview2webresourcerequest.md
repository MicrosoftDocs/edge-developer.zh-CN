---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceRequest 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5c8d164b24995cc31070232dd9b1a2d88fc16cec
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011657"
---
# CoreWebView2WebResourceRequest 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

与 WebResourceRequested 事件一起使用的 HTTP 请求。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[内容](#content) | 作为流的 HTTP 请求消息正文。
[标题](#headers) | 可变 HTTP 请求标头。
[方法](#method) | HTTP 请求方法。
[Uri](#uri) | 请求 URI。

## 成员

#### 内容 

作为流的 HTTP 请求消息正文。

> 公共流 [内容](#content)

发布数据将在此处显示。 如果设置了一个流，该流将覆盖邮件正文，则该流必须具有在此响应的 WebResourceRequested 事件延迟完成时可用的所有内容数据。 流应是敏捷的或从后台 STA 创建，以防止对 UI 线程的性能影响。 Null 表示没有内容数据。 IStream 语义将应用 (返回 S_OK 以读取呼叫，直到所有数据用尽) 。

#### 标题 

可变 HTTP 请求标头。

> 公共 [CoreWebView2HttpRequestHeaders](microsoft-web-webview2-core-corewebview2httprequestheaders.md) [标题](#headers)

#### 方法 

HTTP 请求方法。

> 公共字符串 [方法](#method)

#### Uri 

请求 URI。

> 公共字符串 [Uri](#uri)

