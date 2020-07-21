---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.430-WebView2 Win32 c + + ICoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: cd8f96787d289ab0fe649244ce665445efdbcecf
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884041"
---
# 0.9.430-接口 ICoreWebView2ScriptDialogOpeningEventArgs 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

ScriptDialogOpening 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 请求对话框的页面的 URI。
[get_Kind](#get_kind) | "JavaScript 类型" 对话框。
[get_Message](#get_message) | 对话框的消息。
[接受](#accept) | 宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。
[get_DefaultText](#get_defaulttext) | 第二个参数传递到 JavaScript 提示对话框。
[get_ResultText](#get_resulttext) | 如果调用 Accept，则返回 JavaScript 提示函数的值。
[put_ResultText](#put_resulttext) | 设置 ResultText 属性。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。

## 成员

#### get_Uri 

请求对话框的页面的 URI。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### get_Kind 

"JavaScript 类型" 对话框。

> 公共 HRESULT [get_Kind](#get_kind)（CORE_WEBVIEW2_SCRIPT_DIALOG_KIND * 种类）

接受、确认、提示或 beforeunload。

#### get_Message 

对话框的消息。

> 公共 HRESULT [get_Message](#get_message)（LPWSTR * 消息）

从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。

#### 接受 

宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。

> public HRESULT [Accept](#accept)（）

从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。 对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。

#### get_DefaultText 

第二个参数传递到 JavaScript 提示对话框。

> 公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR * DefaultText）

这是提示 JavaScript 函数的结果所使用的默认值。

#### get_ResultText 

如果调用 Accept，则返回 JavaScript 提示函数的值。

> 公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR * ResultText）

对于除提示之外的对话框类型，忽略此操作。 如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。

#### put_ResultText 

设置 ResultText 属性。

> public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）

#### GetDeferral 

可调用 GetDeferral 以返回[ICoreWebView2Deferral](ICoreWebView2Deferral.md)对象。

> 公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](ICoreWebView2Deferral.md) * * 延迟）

稍后可使用此操作完成事件。

