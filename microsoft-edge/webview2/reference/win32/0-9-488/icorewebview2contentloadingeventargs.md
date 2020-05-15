---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: c6bb99078b5574ba89c0d66b49e2c63cd6888d28
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653084"
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

