---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ContentLoadingEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 899adcb7cfa171e8c1f6cb9693092e36f2e41a5f
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10877761"
---
# 0.9.515-WebView2 的 CoreWebView2ContentLoadingEventArgs 类 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

