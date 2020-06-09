---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/07/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 33450805c7f5117806feb1fb561cd7e0c364f00e
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10698097"
---
# interface ICoreWebView2ScriptDialogOpeningEventArgs 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface ICoreWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

ScriptDialogOpening 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[接受](#accept) | 宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。
[get_DefaultText](#get_defaulttext) | 第二个参数传递到 JavaScript 提示对话框。
[get_Kind](#get_kind) | "JavaScript 类型" 对话框。
[get_Message](#get_message) | 对话框的消息。
[get_ResultText](#get_resulttext) | 如果调用 Accept，则返回 JavaScript 提示函数的值。
[get_Uri](#get_uri) | 请求对话框的页面的 URI。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。
[put_ResultText](#put_resulttext) | 设置 ResultText 属性。

## 成员

#### 接受 

宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。

> public HRESULT [Accept](#accept)（）

从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。 对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。

#### get_DefaultText 

第二个参数传递到 JavaScript 提示对话框。

> 公共 HRESULT [get_DefaultText](#get_defaulttext)（LPWSTR * DefaultText）

这是提示 JavaScript 函数的结果所使用的默认值。

#### get_Kind 

"JavaScript 类型" 对话框。

> 公共 HRESULT [get_Kind](#get_kind)（COREWEBVIEW2_SCRIPT_DIALOG_KIND * 种类）

接受、确认、提示或 beforeunload。

#### get_Message 

对话框的消息。

> 公共 HRESULT [get_Message](#get_message)（LPWSTR * 消息）

从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。

#### get_ResultText 

如果调用 Accept，则返回 JavaScript 提示函数的值。

> 公共 HRESULT [get_ResultText](#get_resulttext)（LPWSTR * ResultText）

对于除提示之外的对话框类型，忽略此操作。 如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。

#### get_Uri 

请求对话框的页面的 URI。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### GetDeferral 

可调用 GetDeferral 以返回[ICoreWebView2Deferral](icorewebview2deferral.md)对象。

> 公共 HRESULT [GetDeferral](#getdeferral)（[ICoreWebView2Deferral](icorewebview2deferral.md) * * 延迟）

稍后可使用此操作完成事件。

#### put_ResultText 

设置 ResultText 属性。

> public HRESULT [put_ResultText](#put_resulttext)（LPCWSTR ResultText）

