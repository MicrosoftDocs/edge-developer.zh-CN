---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 5b560cc0cd91c3445b539dbc6e317d6e6fe0c2d5
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880911"
---
# 0.9.515-接口 ICoreWebView2CapturePreviewCompletedHandler 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2CapturePreviewCompletedHandler
  : public IUnknown
```

调用方实现此方法以接收 CapturePreview 方法的结果。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[调用](#invoke) | 调用以向实施者提供相应异步方法调用的完成状态。

将结果写入 CapturePreview 方法调用中提供的流。

## 成员

#### 调用 

调用以向实施者提供相应异步方法调用的完成状态。

> 公共 HRESULT[调用](#invoke)（hresult 结果）

