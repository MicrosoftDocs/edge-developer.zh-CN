---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 EdgeNotFoundException
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: fc65d857f11a77a1d3629d40266f0453acadaa7b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886309"
---
# 0.9.515-WebView2 的 EdgeNotFoundException 类 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

> 公共[EdgeNotFoundException](#edgenotfoundexception)（）

#### EdgeNotFoundException 

使用对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。

> 公共[EdgeNotFoundException](#edgenotfoundexception)（异常内部）

##### 参数
* `inner` 导致当前异常的异常。

#### EdgeNotFoundException 

使用指定的错误消息初始化 EdgeNotFoundException 类的新实例。

> 公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息）

##### 参数
* `message` 解释异常原因的错误消息。

#### EdgeNotFoundException 

使用指定的错误消息和对导致此异常的内部异常的引用，初始化 EdgeNotFoundException 类的新实例。

> 公共[EdgeNotFoundException](#edgenotfoundexception)（字符串消息，内部异常内部）

##### 参数
* `message` 解释异常原因的错误消息。 

* `inner` 导致当前异常的异常。

