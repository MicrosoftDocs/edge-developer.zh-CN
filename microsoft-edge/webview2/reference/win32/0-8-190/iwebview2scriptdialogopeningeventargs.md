---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 052f380caadf08814cc9364f3ccfbb5251fa7c7e
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878195"
---
# 0.8.355-接口 IWebView2ScriptDialogOpeningEventArgs 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2ScriptDialogOpeningEventArgs
  : public IUnknown
```

[IWebView2WebView：： add_ScriptDialogOpening](IWebView2WebView.md#add_scriptdialogopening)事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[get_Uri](#get_uri) | 请求对话框的页面的 URI。
[get_Kind](#get_kind) | "JavaScript 类型" 对话框。
[get_Message](#get_message) | 对话框的消息。
[接受](#accept) | 宿主可以调用此方法来响应 "确定" 以确认和提示对话框，或者不调用此方法来指示 "取消"。
[get_DefaultText](#get_defaulttext) | 第二个参数传递到 JavaScript 提示对话框。
[get_ResultText](#get_resulttext) | 如果调用 Accept，则返回 JavaScript 提示函数的值。
[put_ResultText](#put_resulttext) | 设置 ResultText 属性。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。

## 成员

#### get_Uri 

请求对话框的页面的 URI。

> 公共 HRESULT [get_Uri](#get_uri)（LPWSTR * Uri）

#### get_Kind 

"JavaScript 类型" 对话框。

> 公共 HRESULT [get_Kind](#get_kind)（WEBVIEW2_SCRIPT_DIALOG_KIND * 种类）

#### get_Message 

对话框的消息。

> 公共 HRESULT [get_Message](#get_message)（LPWSTR * 消息）

从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数。

#### 接受 

宿主可以调用此方法来响应 "确定" 以确认和提示对话框，或者不调用此方法来指示 "取消"。

> public HRESULT [Accept](#accept)（）

从 JavaScript 中，这意味着确认函数在调用 Accept 时返回 true。 对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。

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

可调用 GetDeferral 以返回[IWebView2Deferral](IWebView2Deferral.md)对象。

> 公共 HRESULT [GetDeferral](#getdeferral)（[IWebView2Deferral](IWebView2Deferral.md) * * 延迟）

稍后可使用此操作完成事件。

