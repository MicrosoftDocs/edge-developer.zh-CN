---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2DocumentStateChangedEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 2ef38857b06c14eb9808452a33fa23b24855f055
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878559"
---
# 0.8.355-接口 IWebView2DocumentStateChangedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

