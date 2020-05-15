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
ms.openlocfilehash: 3c32cd59e75eb81bf69661d01f6044a0628ba35d
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652797"
---
# interface IWebView2WebView5 

> [!NOTE]
> 此接口可能会在 SDK 版本0.8.355 后更改或不可用。 请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。

```
interface IWebView2WebView5
  : public IWebView2WebView4
```

由主 Web 视图对象实现的附加功能。

## 摘要

 成员                        | 描述
--------------------------------|---------------------------------------------
[add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged) | ContainsFullScreenElement 属性更改时通知。
[remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged) | 删除以前使用相应的 add_ 事件方法添加的事件处理程序。
[get_ContainsFullScreenElement](#get_containsfullscreenelement) | 指示 Web 视图是否包含全屏 HTML 元素。
[add_WebResourceRequested](#add_webresourcerequested) | 为 WebResourceRequested 事件添加事件处理程序。
[AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) | 将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。
[RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) | 删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。

你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。 有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。

## 成员

#### add_ContainsFullScreenElementChanged 

ContainsFullScreenElement 属性更改时通知。

> public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)（[IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) * eventHandler，EventRegistrationToken * token）

这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。 例如，当视频元素请求进入全屏时，此事件非常有用。 然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<IWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](IWebView2WebView5* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
                    if (m_containsFullscreenElement)
                    {
                        EnterFullScreen();
                    }
                    else
                    {
                        ExitFullScreen();
                    }
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### remove_ContainsFullScreenElementChanged 

删除以前使用相应的 add_ 事件方法添加的事件处理程序。

> public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)（EventRegistrationToken 标记）

#### get_ContainsFullScreenElement 

指示 Web 视图是否包含全屏 HTML 元素。

> public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)（BOOL * ContainsFullScreenElement）

#### add_WebResourceRequested 

为 WebResourceRequested 事件添加事件处理程序。

> public HRESULT [add_WebResourceRequested](#add_webresourcerequested)（[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) * eventHandler，EventRegistrationToken * token）

在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。 必须至少添加一个筛选器，才能触发该事件。

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<IWebView2WebResourceRequestedEventHandler>(
                    [this](
                        IWebView2WebView* sender,
                        IWebView2WebResourceRequestedEventArgs* args) {
                        wil::com_ptr<IWebView2WebResourceRequestedEventArgs2>
                            webResourceEventArgs2;
                        args->QueryInterface(IID_PPV_ARGS(&webResourceEventArgs2));
                        WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            webResourceEventArgs2->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<IWebView2WebResourceResponse> response;
                        CHECK_FAILURE(m_webViewEnvironment->CreateWebResourceResponse(
                            nullptr, 403 /*NoContent*/, L"Blocked", L"", &response));
                        CHECK_FAILURE(args->put_Response(response.get()));
                        return S_OK;
                    })
                    .Get(),
                &m_webResourceRequestedTokenForImageBlocking));
        }
        else
        {
            CHECK_FAILURE(m_webView->remove_WebResourceRequested(
                m_webResourceRequestedTokenForImageBlocking));
        }
```

#### AddWebResourceRequestedFilter 

将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。

> 公共 HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（LPCWSTR const uri，[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext）

URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。 nullptr 等效于 L ""。 有关资源上下文筛选器的说明，请参阅 WEBVIEW2_WEB_RESOURCE_CONTEXT enum。

#### RemoveWebResourceRequestedFilter 

删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。

> 公共 HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（LPCWSTR const uri，[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext）

如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。 返回从未添加的筛选器 E_INVALIDARG。

