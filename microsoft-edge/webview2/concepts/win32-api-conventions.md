---
description: Win32 c + + WebView2 API 约定
title: Win32 c + + WebView2 API 约定
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/14/2020
ms.topic: conceptual
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、wpf 应用、wpf、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 42f0b5c9970b2e4a6424eb70458c58a98ec8dbc7
ms.sourcegitcommit: 61cc15d2fc89aee3e09cec48ef1e0e5bbf8d289a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2020
ms.locfileid: "11118973"
---
# Win32 c + + WebView2 API 约定  

## 异步方法  

WebView2 Win32 c + + API 中的异步方法使用委托接口来回调你，以指示 async 方法已完成的时间、成功或失败代码以及异步方法的结果。  所有异步方法的最终参数都是一个指向你为其提供实现的委托接口的指针。  

委托接口具有一个 `Invoke` 方法，该方法作为第一个参数作为 `HRESULT` 成功或失败代码。  此外，如果方法具有结果，则可能会出现第二个参数，该参数是方法的结果。  例如， [ICoreWebView2：： CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] 方法作为最终参数接受 `ICoreWebView2CapturePreviewCompletedHandler` 指针。  若要发送 `CapturePreview` 方法请求，请提供 `ICoreWebView2CapturePreviewCompletedHandler` 你实现的指针的实例。  下面的代码片段使用一种方法实现。  

```cpp
HRESULT Invoke(HRESULT result)
```  

在 `Invoke` 请求完成后，实现该方法并 `CoreWebView2` 请求你的 `Invoke` 方法 `CapturePreview` 。  单个参数 `HRESULT` 描述请求的成功或失败代码 `CapturePreview` 。  

或者 `ICoreWebView2::ExecuteScript` ，你提供的实例 `ICoreWebView2ExecuteScriptCompletedHandler` 具有一个 `Invoke` 方法，该方法为你提供请求的成功或失败代码，以及 `ExecuteScript` 第二个参数， `resultObjectAsJson` 这是运行脚本的结果的 JSON。  

你可以手动实现 `CompleteHandler` 委托接口，也可以使用 [WRL 回调函数][CppCxWrlCallbackFunction]。  回调函数在以下 WebView2 代码段中使用。  

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

## 事件  

WebView2 Win32 c + + API 中的事件使用 `add_EventName` and `remove_EventName` 方法对来订阅和取消订阅事件。  该 `add_EventName` 方法采用事件处理程序委托接口，并返回一个 `EventRegistrationToken` 作为 out 参数。  该 `remove_EventName` 方法将接受 `EventRegistrationToken` 并取消预订相应的事件订阅。  

事件处理程序委托接口的工作非常类似于 async 方法完成的处理程序委托接口。  实现事件处理程序委托接口，并在 `CoreWebView2` 引发事件时发送回调。  每个事件处理程序委托接口都有一个 `Invoke` 方法，该方法具有一个发件人参数，后跟一个事件参数参数。  发件人是您为其订阅事件的对象的实例。  事件参数参数是一个接口，其中包含有关当前激发事件的信息。  

例如， `NavigationCompleted` 事件 `ICoreWebView2` 具有 `ICoreWebView2::add_NavigationCompleted` and `ICoreWebView2::remove_NavigationCompleted` 方法对。  请求 "添加" 时，你可以提供 `ICoreWebView2NavigationCompletedEventHandler` 你之前实现的方法的实例 `Invoke` 。  当 `NavigationCompleted` 引发该事件时， `Invoke` 将请求你的方法。  第一个参数是 `ICoreWebView2` 触发事件的参数 `NavigationCompleted` 。  第二个参数 `ICoreWebView2NavigationCompletedEventArgs` 包含有关导航是否已成功完成等的信息。  

与 async 方法完成的处理程序委托接口类似，你可以直接实现它，或者你可以使用在以下 WebView2 代码段中使用的 WRL 回调函数。  

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

## 字符串  

字符串输出参数为以 `LPWSTR` null 结尾的字符串。  请求者使用分配的字符串 `CoTaskMemAlloc` 。  所有权将转移到请求者，并由请求者使用释放内存 `CoTaskMemFree` 。  

参数中的字符串为以 `LPCWSTR` null 结尾的字符串。  请求者确保字符串在同步函数请求的持续时间内有效。  如果接收方必须在函数请求完成后将该值保留到某个点，则接收方必须分配该字符串值的关联副本。  

## URI 和 JSON 分析  

各种方法以字符串形式提供或接受 Uri 和 JSON。  请使用你的首选库来分析和生成字符串。  

如果 WinRT 适用于你的应用，你可以使用 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` 方法来分析或生成 JSON 字符串，或 `RuntimeClass_Windows_Foundation_Uri` 使用 `IUriRuntimeClassFactory` 方法来分析和生成 uri。  两种方法在 Win32 应用中均可使用。  

如果你使用 `IUri` 和 `CreateUri` 分析 uri，你可能希望使用以下 URI 创建标志使 `CreateUri` 行为与 web 视图中的 URI 分析更紧密。  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

<!-- links -->  

[Webview2ReferenceWin32Icorewebview2CapturePreview]: /microsoft-edge/webview2/reference/win32/icorewebview2#capturepreview "CapturePreview-接口 ICoreWebView2 |Microsoft 文档"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "回调函数 (WRL) |Microsoft 文档"  
