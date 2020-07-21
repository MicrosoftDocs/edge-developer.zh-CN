---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: e29765a4b8a3e620b8c627c7b05b9f0b4ff63f95
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886409"
---
# 0.9.430-接口 ICoreWebView2PermissionRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

Webview.permissionrequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 请求权限的 web 内容的来源。
[get_PermissionKind](#get_permissionkind) | 所请求权限的类型。
[get_IsUserInitiated](#get_isuserinitiated) | 当权限请求通过用户手势启动时为 True。
[get_State](#get_state) | 权限请求的状态，即
[put_State](#put_state) | 设置 State 属性。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。

## 成员

#### get_Uri 

请求权限的 web 内容的来源。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### get_PermissionKind 

所请求权限的类型。

> public HRESULT [get_PermissionKind](#get_permissionkind)（CORE_WEBVIEW2_PERMISSION_KIND * 值）

#### get_IsUserInitiated 

当权限请求通过用户手势启动时为 True。

> public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL * IsUserInitiated）

注意，通过用户手势启动并不意味着用户打算访问关联的资源。

#### get_State 

权限请求的状态，即

> public HRESULT [get_State](#get_state)（CORE_WEBVIEW2_PERMISSION_STATE * 值）

是否授予请求。 默认值为 CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT。

#### put_State 

设置 State 属性。

> public HRESULT [put_State](#put_state)（CORE_WEBVIEW2_PERMISSION_STATE 值）

#### GetDeferral 

可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。

> 公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延迟）

开发人员可以使用延迟对象在以后的时间做出权限决定。

