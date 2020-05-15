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
ms.openlocfilehash: 5292acf08102afdda33da43575b2e0e584247ecb
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652960"
---
# interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.9.430 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2DevToolsProtocolEventReceivedEventArgs
  : public IUnknown
```

DevToolsProtocolEventReceived 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_ParameterObjectAsJson](#get_parameterobjectasjson) | 以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。

## 成员

#### get_ParameterObjectAsJson 

以 JSON 字符串形式表示的相应 DevToolsProtocol 事件的参数对象。

> 公共 HRESULT [get_ParameterObjectAsJson](#get_parameterobjectasjson)（LPWSTR * ParameterObjectAsJson）

