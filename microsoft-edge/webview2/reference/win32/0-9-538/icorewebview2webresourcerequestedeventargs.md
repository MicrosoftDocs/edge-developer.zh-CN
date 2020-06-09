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
ms.openlocfilehash: e83078b6ac45fbc0b479c5d6b0fde3263a8f34fd
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698500"
---
# interface ICoreWebView2WebResourceRequestedEventArgs 

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

WebResourceRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Request](#get_request) | HTTP 请求。
[get_ResourceContext](#get_resourcecontext) | Web 资源请求上下文。
[get_Response](#get_response) | HTTP 响应。
[GetDeferral](#getdeferral) | 获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。
[put_Response](#put_response) | 设置 Response 属性。

## 成员

#### get_Request 

HTTP 请求。

> 公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) * * 请求）

#### get_ResourceContext 

Web 资源请求上下文。

> 公共 HRESULT [get_ResourceContext](#get_resourcecontext)（COREWEBVIEW2_WEB_RESOURCE_CONTEXT * 上下文）

#### get_Response 

HTTP 响应。

> 公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) * * Response）

#### GetDeferral 

获取[ICoreWebView2Deferral](icorewebview2deferral.md)对象并将事件置于延迟状态。

> 公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) * * 延迟）

你可以使用[ICoreWebView2Deferral](icorewebview2deferral.md)对象在以后的时间完成网络请求。

#### put_Response 

设置 Response 属性。

> 公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) * Response）

