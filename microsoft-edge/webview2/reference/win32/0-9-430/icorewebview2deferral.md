---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 4f7cf3b73e9f354d86e2595a4ed0d4bccda95285
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652964"
---
# interface ICoreWebView2Deferral 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

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

