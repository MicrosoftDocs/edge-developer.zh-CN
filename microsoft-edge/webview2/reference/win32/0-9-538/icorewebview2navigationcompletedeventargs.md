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
ms.openlocfilehash: 11d7e5ffef11a445c55cd4a9d70fcbbb8087c024
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698515"
---
# interface ICoreWebView2NavigationCompletedEventArgs 

```
interface ICoreWebView2NavigationCompletedEventArgs
  : public IUnknown
```

NavigationCompleted 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsSuccess](#get_issuccess) | 导航成功时为 True。
[get_NavigationId](#get_navigationid) | 导航的 ID。
[get_WebErrorStatus](#get_weberrorstatus) | 导航失败时的错误代码。

## 成员

#### get_IsSuccess 

导航成功时为 True。

> public HRESULT [get_IsSuccess](#get_issuccess)（BOOL * IsSuccess）

对于在错误页面中结束的导航（由于无网络、DNS 查找失败、HTTP 服务器通过4xx 响应），这是假，但也可能是 false，如在导航页面上调用的 window。 stop （）。

#### get_NavigationId 

导航的 ID。

> 公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 * navigation_id）

#### get_WebErrorStatus 

导航失败时的错误代码。

> public HRESULT [get_WebErrorStatus](#get_weberrorstatus)（COREWEBVIEW2_WEB_ERROR_STATUS * COREWEBVIEW2_WEB_ERROR_STATUS）

