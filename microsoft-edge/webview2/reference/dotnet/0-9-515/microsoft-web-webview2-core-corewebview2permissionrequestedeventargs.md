---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 5aeeebfc3d8434c096e6946e5161437809f207d3
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652825"
---
# CoreWebView2PermissionRequestedEventArgs 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft WebView2

Webview.permissionrequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[IsUserInitiated](#isuserinitiated) | 当权限请求通过用户手势启动时为 True。
[PermissionKind](#permissionkind) | 所请求权限的类型。
[State](#state) | 权限请求的状态，即
[Uri](#uri) | 请求权限的 web 内容的来源。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。

## 成员

#### IsUserInitiated 

当权限请求通过用户手势启动时为 True。

> 公共 bool [IsUserInitiated](#isuserinitiated)

注意，通过用户手势启动并不意味着用户打算访问关联的资源。

#### PermissionKind 

所请求权限的类型。

> 公共 CoreWebView2PermissionKind [PermissionKind](#permissionkind)

#### State 

权限请求的状态，即

> 公共 CoreWebView2PermissionState[状态](#state)

是否授予请求。

默认值为 CoreWebView2PermissionState。

#### Uri 

请求权限的 web 内容的来源。

> 公共字符串[Uri](#uri)

#### GetDeferral 

可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。

> 公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）

开发人员可以使用延迟对象在以后的时间做出权限决定。

