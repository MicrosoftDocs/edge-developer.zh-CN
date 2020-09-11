---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceResponse 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 5359634d83717ce844d2c1604a2645ceffc477cc
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011653"
---
# CoreWebView2WebResourceResponse 类的 WebView2 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

与 WebResourceRequested 事件一起使用的 HTTP 响应。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[内容](#content) | 流形式的 HTTP 响应内容。
[标题](#headers) | 已重写 HTTP 响应标头。
[ReasonPhrase](#reasonphrase) | HTTP 响应原因短语。
[StatusCode](#statuscode) | HTTP 响应状态代码。

## 成员

#### 内容 

流形式的 HTTP 响应内容。

> 公共流 [内容](#content)

在此响应的 WebResourceRequested 事件延迟完成时，流必须具有所有可用的内容数据。 流应是敏捷的或从后台线程创建，以防止对 UI 线程执行性能影响。 Null 表示没有内容数据。 IStream 语义将应用 (返回 S_OK 以读取呼叫，直到所有数据用尽) 。

#### 标题 

已重写 HTTP 响应标头。

> 公共 [CoreWebView2HttpResponseHeaders](microsoft-web-webview2-core-corewebview2httpresponseheaders.md) [标题](#headers)

#### ReasonPhrase 

HTTP 响应原因短语。

> 公共字符串 [ReasonPhrase](#reasonphrase)

#### StatusCode 

HTTP 响应状态代码。

> 公共 int [StatusCode](#statuscode)

