---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/26/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 59557ca86e8b044fb937fe93b3060c0879abb6f1
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653133"
---
# interface ICoreWebView2WebResourceRequestedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

WebResourceRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Request](#get_request) | HTTP 请求。
[get_Response](#get_response) | HTTP 响应。
[put_Response](#put_response) | 设置 Response 属性。
[GetDeferral](#getdeferral) | 获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。
[get_ResourceContext](#get_resourcecontext) | Web 资源请求上下文。

## 成员

#### get_Request 

HTTP 请求。

> 公共 HRESULT [get_Request](#get_request)（[ICoreWebView2WebResourceRequest](ICoreWebView2WebResourceRequest.md) * * 请求）

#### get_Response 

HTTP 响应。

> 公共 HRESULT [get_Response](#get_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) * * Response）

#### put_Response 

设置 Response 属性。

> 公共 HRESULT [put_Response](#put_response)（[ICoreWebView2WebResourceResponse](ICoreWebView2WebResourceResponse.md) * Response）

#### GetDeferral 

获取[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象并将事件置于延迟状态。

> 公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延迟）

你可以使用[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象在以后的时间完成网络请求。

#### get_ResourceContext 

Web 资源请求上下文。

> 公共 HRESULT [get_ResourceContext](#get_resourcecontext)（CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT * 上下文）

