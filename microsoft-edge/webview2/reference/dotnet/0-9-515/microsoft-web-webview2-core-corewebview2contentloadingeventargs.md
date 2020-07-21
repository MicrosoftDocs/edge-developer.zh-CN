---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 6e2925583c4c3e9d207768c880c014ab1db23f7a
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885126"
---
# 0.9.515-WebView2 的 CoreWebView2ContentLoadingEventArgs 类 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

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

