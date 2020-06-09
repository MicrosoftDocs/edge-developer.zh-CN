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
ms.openlocfilehash: abe167548b7e604bd60c792660ea5b52dec9b848
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697299"
---
# CoreWebView2ContentLoadingEventArgs 类的 WebView2 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

ContentLoading 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[IsErrorPage](#iserrorpage) | 如果加载的内容是错误页面，则为 True。
[NavigationId](#navigationid) | 导航的 ID。

## 成员

#### IsErrorPage 

如果加载的内容是错误页面，则为 True。

> 公共 bool [IsErrorPage](#iserrorpage)

#### NavigationId 

导航的 ID。

> 公共 ulong [NavigationId](#navigationid)

