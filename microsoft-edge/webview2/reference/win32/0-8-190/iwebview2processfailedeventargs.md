---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 748c4affa73001270e2cf97b3d19db8c8ed23686
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653191"
---
# interface IWebView2ProcessFailedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2ProcessFailedEventArgs
  : public IUnknown
```

ProcessFailed 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_ProcessFailedKind](#get_processfailedkind) | 已发生的进程失败的类型。

## 成员

#### get_ProcessFailedKind 

已发生的进程失败的类型。

> public HRESULT [get_ProcessFailedKind](#get_processfailedkind)（WEBVIEW2_PROCESS_FAILED_KIND * ProcessFailedKind）

