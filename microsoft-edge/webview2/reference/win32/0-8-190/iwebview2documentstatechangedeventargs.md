---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2DocumentStateChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 75741c1ba1d835d1c26c7d1db0845071216e0705
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10886120"
---
# 0.8.355-接口 IWebView2DocumentStateChangedEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2DocumentStateChangedEventArgs
  : public IUnknown
```

DocumentStateChanged 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_IsNewDocument](#get_isnewdocument) | 如果要导航到的页面是新文档，则为 True。
[get_IsErrorPage](#get_iserrorpage) | 如果加载的内容是错误页面，则为 True。

## 成员

#### get_IsNewDocument 

如果要导航到的页面是新文档，则为 True。

> public HRESULT [get_IsNewDocument](#get_isnewdocument)（BOOL * IsNewDocument）

#### get_IsErrorPage 

如果加载的内容是错误页面，则为 True。

> public HRESULT [get_IsErrorPage](#get_iserrorpage)（BOOL * IsErrorPage）

