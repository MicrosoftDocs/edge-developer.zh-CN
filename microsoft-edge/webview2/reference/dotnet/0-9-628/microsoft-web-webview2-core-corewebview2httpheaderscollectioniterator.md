---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: CoreWebView2HttpHeadersCollectionIterator 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/10/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、、浏览器控件、边缘 html、WebView2
ms.openlocfilehash: e7aad408372acbbd19ecab9d04312f21e2396e88
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011703"
---
# CoreWebView2HttpHeadersCollectionIterator 类的 WebView2 

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

HTTP 标头集合的迭代器。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[HasCurrentHeader](#hascurrentheader) | 当迭代器未用完标题时，则为 True。
[MoveNext](#movenext) | 将迭代器移动到集合中的下一个 HTTP 标头。

请参阅 CoreWebView2HttpRequestHeaders 和 CoreWebView2HttpResponseHeaders。

## 成员

#### HasCurrentHeader 

当迭代器未用完标题时，则为 True。

> 公共 bool [HasCurrentHeader](#hascurrentheader)

如果迭代器循环的目标集合为空或迭代程序已超过集合末尾，则为 false。

#### MoveNext 

将迭代器移动到集合中的下一个 HTTP 标头。

> 公共的 bool [MoveNext](#movenext) ( # A1

如果没有更多的 HTTP 标头，则 hasNext 参数将设置为 FALSE。 在此情况下，如果调用 GetCurrentHeader 方法，则该方法将失败。

