---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 3a15232a7fe2ddf230d0463069052c55f7abc843
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879133"
---
# 0.9.515-WebView2 的 CoreWebView2NavigationCompletedEventArgs 类 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

NavigationCompleted 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[IsSuccess](#issuccess) | 导航成功时为 True。
[NavigationId](#navigationid) | 导航的 ID。
[WebErrorStatus](#weberrorstatus) | 导航失败时的错误代码。

## 成员

#### IsSuccess 

导航成功时为 True。

> 公共 bool [IsSuccess](#issuccess)

对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。

#### NavigationId 

导航的 ID。

> 公共 ulong [NavigationId](#navigationid)

#### WebErrorStatus 

导航失败时的错误代码。

> 公共 CoreWebView2WebErrorStatus [WebErrorStatus](#weberrorstatus)

