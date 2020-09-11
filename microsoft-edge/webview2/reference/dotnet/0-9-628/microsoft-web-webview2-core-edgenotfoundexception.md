---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: EdgeNotFoundException 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: f74e28eb206458525b0043023e80aea3ac368674
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011650"
---
# EdgeNotFoundException 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

```
class Microsoft.Web.WebView2.Core.EdgeNotFoundException
  : public Exception
```

缺少边缘安装时引发的异常。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[EdgeNotFoundException](#edgenotfoundexception) | 初始化 EdgeNotFoundException 类的新实例。
[EdgeNotFoundException](#edgenotfoundexception) | 使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。
[EdgeNotFoundException](#edgenotfoundexception) | 使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。
[EdgeNotFoundException](#edgenotfoundexception) | 使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。

## 成员

#### EdgeNotFoundException 

初始化 EdgeNotFoundException 类的新实例。

> 公共 [EdgeNotFoundException](#edgenotfoundexception) ( # A1

#### EdgeNotFoundException 

使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。

> 公共 [EdgeNotFoundException](#edgenotfoundexception) (异常内部) 

##### 参数
* `inner` 导致当前异常的异常。

#### EdgeNotFoundException 

使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。

> 公共 [EdgeNotFoundException](#edgenotfoundexception) (字符串消息) 

##### 参数
* `message` 解释异常原因的错误消息。

#### EdgeNotFoundException 

使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。

> 公共 [EdgeNotFoundException](#edgenotfoundexception) (字符串消息，内部) 异常

##### 参数
* `message` 解释异常原因的错误消息。 

* `inner` 导致当前异常的异常。

