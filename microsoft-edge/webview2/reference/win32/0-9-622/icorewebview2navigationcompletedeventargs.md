---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2NavigationCompletedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2NavigationCompletedEventArgs
ms.openlocfilehash: b45920cfdab8a01d1288fbaf566748545b8a2c98
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011685"
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

> 公共 HRESULT [get_IsSuccess](#get_issuccess) (BOOL * IsSuccess) 

这对于在错误页面中结束的导航是错误的，因为没有网络、DNS 查找失败、HTTP 服务器通过 4xx) 做出响应，但对于诸如 window 之类的其他方案也可能是 false (。停止在导航页上调用 ( # A3。

#### get_NavigationId 

导航的 ID。

> 公共 HRESULT [get_NavigationId](#get_navigationid) (UINT64 * NavigationId) 

#### get_WebErrorStatus 

导航失败时的错误代码。

> 公共 HRESULT [get_WebErrorStatus](#get_weberrorstatus) (COREWEBVIEW2_WEB_ERROR_STATUS * WebErrorStatus) 

