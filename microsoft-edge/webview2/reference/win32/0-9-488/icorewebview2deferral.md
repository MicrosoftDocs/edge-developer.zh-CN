---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2 Win32 c + + ICoreWebView2Deferral
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b30b6e35388ab01433b2c879db82d9c4136fae99
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885413"
---
# 0.9.515-接口 ICoreWebView2Deferral 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2Deferral
  : public IUnknown
```

此接口用于完成事件参数的延迟，该参数支持通过其 GetDeferral 方法获取延迟。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[完成](#complete) | 完成关联的延迟事件。

## 成员

#### 完成 

完成关联的延迟事件。

> 公共 HRESULT[完成](#complete)（）

对于每个延迟的延迟，只能调用一次完成。

