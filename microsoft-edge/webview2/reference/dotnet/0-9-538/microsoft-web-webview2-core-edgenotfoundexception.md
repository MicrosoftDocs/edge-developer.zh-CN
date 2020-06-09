---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b7d738628d6627232780e003f126b45c0421d6f0
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698411"
---
# EdgeNotFoundException 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

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

