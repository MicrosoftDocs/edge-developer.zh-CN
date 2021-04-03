---
description: Win32 C++ WebView2 API 约定
title: Win32 C++ WebView2 API 约定
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/24/2021
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、webview、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: b47e53a4846d4bb662ae108c6445a6c2a615722a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11470856"
---
# <a name="win32-c-webview2-api-conventions"></a>Win32 C++ WebView2 API 约定  

:::row:::
   :::column span="1":::
      支持的平台：
   :::column-end:::
   :::column span="2":::
      Win32
   :::column-end:::
:::row-end:::  

## <a name="prerequisites"></a>必备条件  

*   使用 Win32 API 的体验  

## <a name="async-methods"></a>异步方法  

WebView2 Win32 C++ API 中的异步方法使用委托接口联系你，原因如下。  

*   异步方法已完成。  
*   成功或失败代码。  
*   异步方法的结果。  

所有异步方法的最后一个参数是指向你提供其实现的委托接口的指针。  

委托接口具有一个方法，该方法将成功代码或失败代码的第一个参数 `Invoke` `HRESULT` 作为 。  此外，如果方法有结果，则可能有第二个参数是该方法的结果。  例如 [，ICoreWebView2：：CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] 方法将指针作为最后的参数 `ICoreWebView2CapturePreviewCompletedHandler` 。  若要发送 `CapturePreview` 方法请求，需要提供一个 `ICoreWebView2CapturePreviewCompletedHandler` 实现指针的实例。  以下代码段使用一种方法来实现。  

```cpp
HRESULT Invoke(HRESULT result)
```  

实现 `Invoke` 方法 `CoreWebView2` ，请求完成 `Invoke` 时请求 `CapturePreview` 方法。  单个参数 `HRESULT` 用于描述请求的成功或失败 `CapturePreview` 代码。  

或者，对于 ，您提供一个实例，该实例具有一个方法，用于提供 `ICoreWebView2::ExecuteScript` `Invoke` 请求的成功或失败 `ExecuteScript` 代码。  另外提供第二个参数，该参数是运行脚本的结果的 JSON。  

可以手动实现委托接口，也可以将 Callback 函数 (`CompleteHandler` [WRL) ][CppCxWrlCallbackFunction]。  以下 [WebView2 (代码) 使用 WRL ][CppCxWrlCallbackFunction] 代码段中的 Callback 函数。  

```cpp
void ScriptComponent::InjectScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Inject Script",
        L"Enter script code:",
        L"Enter the JavaScript code to run in the webview.",
        L"window.getComputedStyle(document.body).backgroundColor");
    if (dialog.confirmed)
    {
        m_webView->ExecuteScript(dialog.input.c_str(),
            Callback<ICoreWebView2ExecuteScriptCompletedHandler>(
                [](HRESULT error, PCWSTR result) -> HRESULT
        {
            if (error != S_OK) {
                ShowFailure(error, L"ExecuteScript failed");
            }
            MessageBox(nullptr, result, L"ExecuteScript Result", MB_OK);
            return S_OK;
        }).Get());
    }
}
```  

## <a name="events"></a>事件  

WebView2 Win32 C++ API 中的事件使用 和 方法对订阅和 `add_EventName` `remove_EventName` 取消订阅事件。  `add_EventName`方法采用事件处理程序委托接口，并作为 `EventRegistrationToken` 输出参数返回令牌。  `remove_EventName`方法获取令牌 `EventRegistrationToken` 并取消订阅相应的事件订阅。  

事件处理程序委托接口与异步方法完成的处理程序委托接口类似。  实现事件处理程序委托接口， `CoreWebView2` 并每当事件运行时发送回调。  每个事件处理程序委托接口都有一个方法，该方法具有 `Invoke` 一个 sender 参数，后跟一个事件参数。  发件人是您为事件订阅的对象的实例。  事件参数是一个包含当前触发事件相关信息的接口。  

例如，上的 `NavigationCompleted` 事件 `ICoreWebView2` 具有 和 `ICoreWebView2::add_NavigationCompleted` `ICoreWebView2::remove_NavigationCompleted` 方法对。  发送请求时，提供之前实现 `ICoreWebView2NavigationCompletedEventHandler` 方法的实例 `Invoke` 。  当 `NavigationCompleted` 事件运行时， `Invoke` 将请求方法。  第一个参数运行 `NavigationCompleted` 事件。  第二个参数包含有关导航是否成功完成的信息，等等。  

与异步方法完成的处理程序委托接口类似，请使用以下操作之一进行设置。  

*   直接实现。  
*   将 [Callback 函数 (WebView2) ][CppCxWrlCallbackFunction] 代码段中使用的 WRL 对象函数。  

<!-- todo:  what is async method completed handler delegate interface?  Is there a shorter name for it?  -->  

```cpp
// Register a handler for the NavigationCompleted event.
// Check whether the navigation succeeded, and if not, do something.
// Also update the Cancel buttons.
CHECK_FAILURE(m_webView->add_NavigationCompleted(
    Callback<ICoreWebView2NavigationCompletedEventHandler>(
        [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
            -> HRESULT {
            BOOL success;
            CHECK_FAILURE(args->get_IsSuccess(&success));
            if (!success)
            {
                COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                {
                    // Do something here if you want to handle a specific error case.
                    // In most cases it is not necessary, because the WebView
                    // displays an error page automatically.
                }
            }
            m_toolbar->SetItemEnabled(Toolbar::Item_CancelButton, false);
            m_toolbar->SetItemEnabled(Toolbar::Item_ReloadButton, true);
            return S_OK;
        })
        .Get(),
    &m_navigationCompletedToken));
```  

## <a name="strings"></a>字符串  

字符串输出参数是 `LPWSTR` 以 null 结尾的字符串。  请求程序使用 提供字符串 `CoTaskMemAlloc` 。  所有权将传输到请求者，由请求者使用 释放内存 `CoTaskMemFree` 。  

字符串输入参数是 `LPCWSTR` 以 null 结尾的字符串。  请求者确保字符串在同步函数请求的持续时间内有效。  如果接收器必须在函数请求完成后将值存储到某一点，则接收器必须提供字符串值的关联副本。  

## <a name="uri-and-json-parsing"></a>URI 和 JSON 分析  

各种方法提供或接受 URI 和 JSON 作为字符串。  使用首选库分析和生成字符串。  

如果 WinRT 可用于你的应用，你可能会使用 和 方法来分析或生成 JSON 字符串或方法来 `RuntimeClass_Windows_Data_Json_JsonObject` `IJsonObjectStatics` `RuntimeClass_Windows_Foundation_Uri` `IUriRuntimeClassFactory` 分析和生成 URI。  这两种方法均在 Win32 应用中工作。  

如果使用 和 解析 URI，可能需要使用以下 URI 创建标志，使行为与 WebView 中的 URI 分析更 `IUri` `CreateUri` `CreateUri` 匹配。  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

## <a name="see-also"></a>另请参阅  

*   若要开始使用 WebView2 Win32 C/C++，请导航到 [WebView2 入门][Webview2IndexGettingStarted] 指南。  
*   有关 WebView2 API 的更多详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WpfWebview2]。  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a>与 Microsoft Edge WebView 团队联系  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2GettingstartedWin32]: ../gettingstarted/win32.md "WebView2 应用程序|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2CapturePreview]: /microsoft-edge/webview2/reference/win32/icorewebview2#capturepreview "CapturePreview - 接口 ICoreWebView2 |Microsoft Docs"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "WRL (回调) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  
