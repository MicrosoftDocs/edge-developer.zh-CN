---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2HttpHeadersCollectionIterator
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: dbcc5b10ce1973df61554f3f27174f600fb25280
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885979"
---
# 0.8.355-接口 IWebView2HttpHeadersCollectionIterator 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2HttpHeadersCollectionIterator
  : public IUnknown
```

HTTP 标头集合的迭代器。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[GetCurrentHeader](#getcurrentheader) | 获取迭代器的当前 HTTP 标头的名称和值。
[MoveNext](#movenext) | 将迭代器移动到集合中的下一个 HTTP 标头。

请参阅[IWebView2HttpRequestHeaders](IWebView2HttpRequestHeaders.md)和[IWebView2HttpResponseHeaders](IWebView2HttpResponseHeaders.md)。

## 成员

#### GetCurrentHeader 

获取迭代器的当前 HTTP 标头的名称和值。

> 公共 HRESULT [GetCurrentHeader](#getcurrentheader)（LPWSTR * NAME，LPWSTR * value）

如果对 MoveNext 的最后一次调用设置 has_next 为 FALSE，此方法将失败。

#### MoveNext 

将迭代器移动到集合中的下一个 HTTP 标头。

> 公共 HRESULT [MoveNext](#movenext)（BOOL * has_next）

如果没有更多的 HTTP 标头，则 has_next 参数将设置为 FALSE。 在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。

