---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.9.515-WebView2。 CoreWebView2ScriptDialogOpeningEventArgs
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b7071a312ce1fa3ca006a6805a1f712a51d0dab0
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10879112"
---
# 0.9.515-WebView2 的 CoreWebView2ScriptDialogOpeningEventArgs 类 

> [!NOTE]
> SDK 版本0.9.515 后，此参考可能会更改或不可用。 请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。

命名空间： Microsoft WebView2 \
程序集： Microsoft.Web.WebView2.Core.dll

ScriptDialogOpening 事件的事件参数。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[DefaultText](#defaulttext) | 第二个参数传递到 JavaScript 提示对话框。
[Kind](#kind) | "JavaScript 类型" 对话框。
[消息](#message) | 对话框的消息。
[ResultText](#resulttext) | 如果调用 Accept，则返回 JavaScript 提示函数的值。
[Uri](#uri) | 请求对话框的页面的 URI。
[接受](#accept) | 宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。
[GetDeferral](#getdeferral) | 可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。

## 成员

#### DefaultText 

第二个参数传递到 JavaScript 提示对话框。

> 公共字符串[DefaultText](#defaulttext)

这是提示 JavaScript 函数的结果所使用的默认值。

#### Kind 

"JavaScript 类型" 对话框。

> 公共 CoreWebView2ScriptDialogKind[种类](#kind)

接受、确认、提示或 beforeunload。

#### 消息 

对话框的消息。

> 公共字符串[消息](#message)

从 JavaScript 中，这是传递给 alert、confirm 和 prompt 的第一个参数，对于 beforeunload 是空的。

#### ResultText 

如果调用 Accept，则返回 JavaScript 提示函数的值。

> 公共字符串[ResultText](#resulttext)

对于除提示之外的对话框类型，忽略此操作。 如果未调用 "接受"，则忽略此值，并从 prompt 返回 false。

#### Uri 

请求对话框的页面的 URI。

> 公共字符串[Uri](#uri)

#### 接受 

宿主可以调用此方法来响应 "确定" 以确认、提示和 beforeunload 对话框，或者不调用此方法来指示 "取消"。

> 公共 void [Accept](#accept)（）

从 JavaScript 中，这意味着如果调用 Accept，则 confirm 函数和 beforeunload 函数将返回 true。 对于提示函数，如果 "接受" 被调用，则返回 ResultText 的值，否则返回 false。

#### GetDeferral 

可调用 GetDeferral 以返回 CoreWebView2Deferral 对象。

> 公共 CoreWebView2Deferral [GetDeferral](#getdeferral)（）

稍后可使用此操作完成事件。

