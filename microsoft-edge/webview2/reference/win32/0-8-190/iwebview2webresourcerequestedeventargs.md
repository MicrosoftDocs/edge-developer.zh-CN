---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 40474d6b1169467022e5bb47e82eba3883edc2aa
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878097"
---
# 0.8.355-接口 IWebView2WebResourceRequestedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

WebResourceRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Request](#get_request) | HTTP 请求。
[get_Response](#get_response) | HTTP 响应。
[put_Response](#put_response) | 设置 Response 属性。
[GetDeferral](#getdeferral) | 获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。

## 成员

#### get_Request 

HTTP 请求。

> 公共 HRESULT [get_Request](#get_request)（[IWebView2WebResourceRequest](IWebView2WebResourceRequest.md) * * 请求）

#### get_Response 

HTTP 响应。

> 公共 HRESULT [get_Response](#get_response)（[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) * * Response）

#### put_Response 

设置 Response 属性。

> 公共 HRESULT [put_Response](#put_response)（[IWebView2WebResourceResponse](IWebView2WebResourceResponse.md) * Response）

#### GetDeferral 

获取[IWebView2Deferral](IWebView2Deferral.md)对象并将事件置于延迟状态。

> 公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) * * 延迟）

你可以使用[IWebView2Deferral](IWebView2Deferral.md)对象在以后的时间完成网络请求。

