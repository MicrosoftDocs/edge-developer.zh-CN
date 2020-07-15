---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2PermissionRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 92c08d199aa607dae9cc575955a1eb0bf016a9c0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878328"
---
# 0.8.355-接口 IWebView2PermissionRequestedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2PermissionRequestedEventArgs
  : public IUnknown
```

Webview.permissionrequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 请求权限的 web 内容的来源。
[get_PermissionType](#get_permissiontype) | 所请求权限的类型。
[get_IsUserInitiated](#get_isuserinitiated) | 当权限请求通过用户手势启动时为 True。
[get_State](#get_state) | 权限请求的状态，即
[put_State](#put_state) | 设置 State 属性。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。

## 成员

#### get_Uri 

请求权限的 web 内容的来源。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### get_PermissionType 

所请求权限的类型。

> public HRESULT [get_PermissionType](#get_permissiontype)（WEBVIEW2_PERMISSION_TYPE * 值）

#### get_IsUserInitiated 

当权限请求通过用户手势启动时为 True。

> public HRESULT [get_IsUserInitiated](#get_isuserinitiated)（BOOL * IsUserInitiated）

注意，通过用户手势启动并不意味着用户打算访问关联的资源。

#### get_State 

权限请求的状态，即

> public HRESULT [get_State](#get_state)（WEBVIEW2_PERMISSION_STATE * 值）

是否授予请求。 默认值为 WEBVIEW2_PERMISSION_STATE_DEFAULT。

#### put_State 

设置 State 属性。

> public HRESULT [put_State](#put_state)（WEBVIEW2_PERMISSION_STATE 值）

#### GetDeferral 

可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。

> 公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) * * 延迟）

开发人员可以使用延迟对象在以后的时间做出权限决定。

