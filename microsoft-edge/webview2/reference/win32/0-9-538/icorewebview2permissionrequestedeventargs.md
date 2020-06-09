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
ms.openlocfilehash: bfc802d160f7516f5f65e5526fecfd9742504045
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698565"
---
# interface ICoreWebView2PermissionRequestedEventArgs 

```
interface ICoreWebView2PermissionRequestedEventArgs
  : public IUnknown
```

Webview.permissionrequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsUserInitiated](#get_isuserinitiated) | 当权限请求通过用户手势启动时为 True。
[get_PermissionKind](#get_permissionkind) | 所请求权限的类型。
[get_State](#get_state) | 权限请求的状态，即
[get_Uri](#get_uri) | 请求权限的 web 内容的来源。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。
[put_State](#put_state) | 设置 State 属性。

## 成员

#### get_IsUserInitiated 

当权限请求通过用户手势启动时为 True。

> public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL * IsUserInitiated）

注意，通过用户手势启动并不意味着用户打算访问关联的资源。

#### get_PermissionKind 

所请求权限的类型。

> public HRESULT [get_PermissionKind](#get_permissionkind)（COREWEBVIEW2_PERMISSION_KIND * 值）

#### get_State 

权限请求的状态，即

> public HRESULT [get_State](#get_state)（COREWEBVIEW2_PERMISSION_STATE * 值）

是否授予请求。 默认值为 COREWEBVIEW2_PERMISSION_STATE_DEFAULT。

#### get_Uri 

请求权限的 web 内容的来源。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### GetDeferral 

可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。

> 公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) * * 延迟）

开发人员可以使用延迟对象在以后的时间做出权限决定。

#### put_State 

设置 State 属性。

> public HRESULT [put_State](#put_state)（COREWEBVIEW2_PERMISSION_STATE 值）

