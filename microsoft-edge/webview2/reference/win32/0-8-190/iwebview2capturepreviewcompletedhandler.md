---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2CapturePreviewCompletedHandler
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 991c09167ba3fe382c74d6244c76ffae25d628a6
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886190"
---
# 0.8.355-接口 IWebView2CapturePreviewCompletedHandler 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2CapturePreviewCompletedHandler
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

