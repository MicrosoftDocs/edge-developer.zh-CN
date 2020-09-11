---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: 0.9.579-WebView2 Win32 c + + ICoreWebView2WebResourceRequestedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2WebResourceRequestedEventArgs
ms.openlocfilehash: 2e55a43282a7548acefdb0b1ed1b8cac2254ef21
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11010388"
---
# 0.9.579-接口 ICoreWebView2WebResourceRequestedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2WebResourceRequestedEventArgs
  : public IUnknown
```

WebResourceRequested 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Request](#get_request) | Web 资源请求。
[get_ResourceContext](#get_resourcecontext) | Web 资源请求上下文。
[get_Response](#get_response) | Web 资源响应对象的占位符。
[GetDeferral](#getdeferral) | 获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。
[put_Response](#put_response) | 设置 Response 属性。

## 成员

#### get_Request 

Web 资源请求。

> 公共 HRESULT [get_Request](#get_request) ([ICoreWebView2WebResourceRequest](icorewebview2webresourcerequest.md) * * 请求) 

请求对象可能缺少某些标题，这些标题将在稍后的网络堆栈中添加。

#### get_ResourceContext 

Web 资源请求上下文。

> 公共 HRESULT [get_ResourceContext](#get_resourcecontext) (COREWEBVIEW2_WEB_RESOURCE_CONTEXT * 上下文) 

#### get_Response 

Web 资源响应对象的占位符。

> 公共 HRESULT [get_Response](#get_response) ([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) * * 响应) 

如果设置了此对象，将在此响应中完成 web 资源请求。

#### GetDeferral 

获取 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象并将事件置于延迟状态。

> 公共 HRESULT [GetDeferral](#getdeferral) ([ICoreWebView2Deferral](icorewebview2deferral.md) * * 延期) 

你可以使用 [ICoreWebView2Deferral](icorewebview2deferral.md) 对象在以后的时间完成该请求。

#### put_Response 

设置 Response 属性。

> 公共 HRESULT [put_Response](#put_response) ([ICoreWebView2WebResourceResponse](icorewebview2webresourceresponse.md) * Response) 

可以使用 CreateWebResourceResponse 创建空的 Web 资源响应对象，然后对其进行修改以构造响应。

