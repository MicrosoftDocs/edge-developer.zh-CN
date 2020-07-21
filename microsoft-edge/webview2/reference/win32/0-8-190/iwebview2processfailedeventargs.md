---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ProcessFailedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 697a49bfe68f83085f6c961ee2cdd5ab21f3b59b
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885819"
---
# 0.8.355-接口 IWebView2ProcessFailedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

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

