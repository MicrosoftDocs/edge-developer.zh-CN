---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/09/2019
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 436e0e33180c65afcce0487fffeff5f168dceab7
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652802"
---
# interface IWebView2WebView3 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2WebView3
  : public IWebView2WebView
```

由主 Web 视图对象实现的附加功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[停止](#stop) | 停止所有导航和挂起的资源提取。
[add_NewWindowRequested](#add_newwindowrequested) | 为 Webview.newwindowrequested 事件添加事件处理程序。
[remove_NewWindowRequested](#remove_newwindowrequested) | 删除以前使用 add_NewWindowRequested 添加的事件处理程序。
[add_DocumentTitleChanged](#add_documenttitlechanged) | 为 DocumentTitleChanged 事件添加事件处理程序。
[remove_DocumentTitleChanged](#remove_documenttitlechanged) | 删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。
[get_DocumentTitle](#get_documenttitle) | 当前顶级文档的标题。

你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。 有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。

## 成员

#### 停止 

停止所有导航和挂起的资源提取。

> 公共 HRESULT[停止](#stop)（）

#### add_NewWindowRequested 

为 Webview.newwindowrequested 事件添加事件处理程序。

> public HRESULT [add_NewWindowRequested](#add_newwindowrequested)（[IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。 应用可以传递将被视为打开的窗口的目标 web 视图。

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<IWebView2NewWindowRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<IWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));

                auto newAppWindow = new AppWindow(L"");
                newAppWindow->m_onWebViewFirstInitialized = [args, deferral, newAppWindow]() {
                    CHECK_FAILURE(args->put_NewWindow(newAppWindow->m_webView.get()));
                    CHECK_FAILURE(args->put_Handled(TRUE));
                    CHECK_FAILURE(deferral->Complete());
                };

                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_NewWindowRequested 

删除以前使用 add_NewWindowRequested 添加的事件处理程序。

> public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)（EventRegistrationToken 标记）

#### add_DocumentTitleChanged 

为 DocumentTitleChanged 事件添加事件处理程序。

> public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)（[IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) * eventHandler，EventRegistrationToken * token）

当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<IWebView2DocumentTitleChangedEventHandler>(
            [this](IWebView2WebView3* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### remove_DocumentTitleChanged 

删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。

> public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)（EventRegistrationToken 标记）

#### get_DocumentTitle 

当前顶级文档的标题。

> 公共 HRESULT [get_DocumentTitle](#get_documenttitle)（LPWSTR * 标题）

如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。

