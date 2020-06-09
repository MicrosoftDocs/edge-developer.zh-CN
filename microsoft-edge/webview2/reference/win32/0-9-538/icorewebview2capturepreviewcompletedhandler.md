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
ms.openlocfilehash: 290d82666e5b9c5062132e1eb7515e39e2deb978
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698486"
---
# interface ICoreWebView2CapturePreviewCompletedHandler 

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

