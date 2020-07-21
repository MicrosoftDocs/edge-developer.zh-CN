---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2WebResourceResponseReceivedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 44fc4f47aa10a7e409ac584cb75b750048056e47
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886503"
---
# CoreWebView2WebResourceResponseReceivedEventArgs 类的 WebView2 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

WebResourceResponseReceived 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[请求](#request) | Web 资源请求对象。
[响应](#response) | Web 资源响应对象。
[PopulateResponseContentAsync](#populateresponsecontentasync) | 请求响应的内容流的异步方法。

## 成员

#### 请求 

Web 资源请求对象。

> 公共 HttpRequestMessage[请求](#request)

对此对象所做的任何修改都将被忽略。

#### 响应 

Web 资源响应对象。

> 公共 HttpResponseMessage[响应](#response)

对此对象所做的任何修改都将被忽略。

#### PopulateResponseContentAsync 

请求响应的内容流的异步方法。

> 公共异步任务[PopulateResponseContentAsync](#populateresponsecontentasync)（）

