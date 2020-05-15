---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: fec7fd7399222d8223d1022cd1e528bc9ed0d161
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653118"
---
# CoreWebView2Deferral 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

此类用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[完成](#complete) | 完成关联的延迟事件。

## 成员

#### 完成 

完成关联的延迟事件。

> 公共失效[完整](#complete)（）

对于每个延迟的延迟，只能调用一次完成。

