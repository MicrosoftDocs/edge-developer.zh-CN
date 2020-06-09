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
ms.openlocfilehash: bf198781d67761e9d6c29ee9c6a274462e92a61d
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697670"
---
# CoreWebView2Deferral 类的 WebView2 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

