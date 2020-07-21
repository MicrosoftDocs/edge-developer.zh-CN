---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 Win32 c + + ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
ms.openlocfilehash: 9447420abddfdb44394042d6742ed1dafd299adf
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886518"
---
# interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler 

[!INCLUDE [prerelease-note](../../includes/prerelease-note.md)]

```
interface ICoreWebView2ExperimentalWebResourceResponseReceivedEventHandler
  : public IUnknown
```

在 Web 资源在 Web 资源中收到请求的响应时激发。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[调用](#invoke) | 调用以向实施者提供对应事件的事件参数。

Host 可以使用此事件查看 Web 资源的实际请求和响应。 这包括在已触发关联请求的 WebResourceRequested 事件之后，网络堆栈所做的任何请求或响应修改（如添加授权标头）。 忽略对请求或响应对象所做的更改。

## 成员

#### 调用 

调用以向实施者提供对应事件的事件参数。

> 公共 HRESULT[调用](#invoke)（[ICoreWebView2Experimental](icorewebview2experimental.md) * sender、 [ICoreWebView2ExperimentalWebResourceResponseReceivedEventArgs](icorewebview2experimentalwebresourceresponsereceivedeventargs.md) * 参数）

