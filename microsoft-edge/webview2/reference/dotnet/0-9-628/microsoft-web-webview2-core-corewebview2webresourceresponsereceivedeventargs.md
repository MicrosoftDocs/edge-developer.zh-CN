---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2WebResourceResponseReceivedEventArgs 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: 2d0660616de0c234b1535b2af127843fea3a3a53
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011651"
---
# CoreWebView2WebResourceResponseReceivedEventArgs 类的 WebView2 

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

> 公共 [CoreWebView2WebResourceRequest](microsoft-web-webview2-core-corewebview2webresourcerequest.md) [请求](#request)

对此对象所做的任何修改都将被忽略。

#### 响应 

Web 资源响应对象。

> 公共 [CoreWebView2WebResourceResponse](microsoft-web-webview2-core-corewebview2webresourceresponse.md) [响应](#response)

对此对象所做的任何修改都将被忽略。

#### PopulateResponseContentAsync 

请求响应的内容流的异步方法。

> 公共异步任务 [PopulateResponseContentAsync](#populateresponsecontentasync) ( # A1

