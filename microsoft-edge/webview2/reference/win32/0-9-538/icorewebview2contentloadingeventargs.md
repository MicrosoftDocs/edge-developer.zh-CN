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
ms.openlocfilehash: 8acec97ec6060cd53adc3821f6a51db2048935fb
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698487"
---
# interface ICoreWebView2ContentLoadingEventArgs 

```
interface ICoreWebView2ContentLoadingEventArgs
  : public IUnknown
```

ContentLoading 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsErrorPage](#get_iserrorpage) | 如果加载的内容是错误页面，则为 True。
[get_NavigationId](#get_navigationid) | 导航的 ID。

## 成员

#### get_IsErrorPage 

如果加载的内容是错误页面，则为 True。

> public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL * IsErrorPage）

#### get_NavigationId 

导航的 ID。

> 公共 HRESULT [get_NavigationId](#get_navigationid)（UINT64 * navigation_id）

