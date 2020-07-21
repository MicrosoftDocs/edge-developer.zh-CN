---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: CoreWebView2CreationProperties 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/17/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、WebView2、浏览器控件、边缘 html、。 CoreWebView2CreationProperties
ms.openlocfilehash: 04c80d3319c74d3461666b6f35fadd0481b45207
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885532"
---
# CoreWebView2CreationProperties 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Wpf.dll

```
class Microsoft.Web.WebView2.Wpf.CoreWebView2CreationProperties
  : public DependencyObject
```

此类是用于创建 CoreWebView2Environment 的最常用参数的捆绑包。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[BrowserExecutableFolder](#browserexecutablefolder) | 获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 browserExecutableFolder 参数传递的值。
[语言](#language) | 获取或设置在使用此实例创建环境时，用于传递到 CoreWebView2Environment 的 CoreWebView2EnvironmentOptions 参数的 Language 属性的值。
[UserDataFolder](#userdatafolder) | 获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 userDataFolder 参数传递的值。
[CoreWebView2CreationProperties](#corewebview2creationproperties) | 使用所有属性的默认数据创建 CoreWebView2CreationProperties 的新实例。

它的主要用途是将 WebView2 设置为[CreationProperties](microsoft-web-webview2-wpf-webview2.md) ，以便在隐式初始化期间自定义[WebView2](microsoft-web-webview2-wpf-webview2.md)使用的环境。 它也是一个很好的 WPF 集成实用工具，它允许将常用的环境参数用作依赖属性并在标记中创建和使用。

此类不用于包含所有可能的环境自定义选项。 如果你需要对 WebView2 控件使用的环境进行完全控制，则需要通过创建你自己的具有 CoreWebView2Environment 的环境并将其传递到[WebView2](microsoft-web-webview2-wpf-webview2.md)来显式初始化控件，然后*再*将[EnsureCoreWebView2Async Source](microsoft-web-webview2-wpf-webview2.md)属性设置为任何内容。 有关初始化概述，请参阅[WebView2](microsoft-web-webview2-wpf-webview2.md)类文档。

## 成员

#### BrowserExecutableFolder 

获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 browserExecutableFolder 参数传递的值。

> 公共字符串[BrowserExecutableFolder](#browserexecutablefolder)

#### 语言 

获取或设置在使用此实例创建环境时，用于传递到 CoreWebView2Environment 的 CoreWebView2EnvironmentOptions 参数的 Language 属性的值。

> 公共字符串[语言](#language)

#### UserDataFolder 

获取或设置在使用此实例创建环境时要作为 CoreWebView2Environment 的 userDataFolder 参数传递的值。

> 公共字符串[UserDataFolder](#userdatafolder)

#### CoreWebView2CreationProperties 

使用所有属性的默认数据创建 CoreWebView2CreationProperties 的新实例。

> 公共[CoreWebView2CreationProperties](#corewebview2creationproperties)（）

