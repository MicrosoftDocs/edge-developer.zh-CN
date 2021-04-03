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
# <a name="win32-c-webview2-api-conventions"></a><span data-ttu-id="4d1ba-104">Win32 C++ WebView2 API 约定</span><span class="sxs-lookup"><span data-stu-id="4d1ba-104">Win32 C++ WebView2 API conventions</span></span>  

:::row:::
   :::column span="1":::
      <span data-ttu-id="4d1ba-105">支持的平台：</span><span class="sxs-lookup"><span data-stu-id="4d1ba-105">Supported platforms:</span></span>
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="4d1ba-106">Win32</span><span class="sxs-lookup"><span data-stu-id="4d1ba-106">Win32</span></span>
   :::column-end:::
:::row-end:::  

## <a name="prerequisites"></a><span data-ttu-id="4d1ba-107">必备条件</span><span class="sxs-lookup"><span data-stu-id="4d1ba-107">Prerequisites</span></span>  

*   <span data-ttu-id="4d1ba-108">使用 Win32 API 的体验</span><span class="sxs-lookup"><span data-stu-id="4d1ba-108">Experience using Win32 API</span></span>  

## <a name="async-methods"></a><span data-ttu-id="4d1ba-109">异步方法</span><span class="sxs-lookup"><span data-stu-id="4d1ba-109">Async methods</span></span>  

<span data-ttu-id="4d1ba-110">WebView2 Win32 C++ API 中的异步方法使用委托接口联系你，原因如下。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-110">Asynchronous methods in the WebView2 Win32 C++ API use a delegate interface to contact you for the following reasons.</span></span>  

*   <span data-ttu-id="4d1ba-111">异步方法已完成。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-111">The async method has completed.</span></span>  
*   <span data-ttu-id="4d1ba-112">成功或失败代码。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-112">The success or failure code.</span></span>  
*   <span data-ttu-id="4d1ba-113">异步方法的结果。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-113">The result of the asynchronous method.</span></span>  

<span data-ttu-id="4d1ba-114">所有异步方法的最后一个参数是指向你提供其实现的委托接口的指针。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-114">The final parameter for all asynchronous methods is a pointer to a delegate interface of which you provide an implementation.</span></span>  

<span data-ttu-id="4d1ba-115">委托接口具有一个方法，该方法将成功代码或失败代码的第一个参数 `Invoke` `HRESULT` 作为 。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-115">The delegate interface has a single `Invoke` method that takes as a first parameter an `HRESULT` of the success or failure code.</span></span>  <span data-ttu-id="4d1ba-116">此外，如果方法有结果，则可能有第二个参数是该方法的结果。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-116">Additionally, there may be a second parameter that is the result of the method if the method has a result.</span></span>  <span data-ttu-id="4d1ba-117">例如 [，ICoreWebView2：：CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] 方法将指针作为最后的参数 `ICoreWebView2CapturePreviewCompletedHandler` 。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-117">For example, the [ICoreWebView2::CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] method takes as the final parameter an `ICoreWebView2CapturePreviewCompletedHandler` pointer.</span></span>  <span data-ttu-id="4d1ba-118">若要发送 `CapturePreview` 方法请求，需要提供一个 `ICoreWebView2CapturePreviewCompletedHandler` 实现指针的实例。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-118">To send a `CapturePreview` method request, you provide an instance of the `ICoreWebView2CapturePreviewCompletedHandler` pointer that you implement.</span></span>  <span data-ttu-id="4d1ba-119">以下代码段使用一种方法来实现。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-119">The following code snippet uses one method to implement.</span></span>  

```cpp
HRESULT Invoke(HRESULT result)
```  

<span data-ttu-id="4d1ba-120">实现 `Invoke` 方法 `CoreWebView2` ，请求完成 `Invoke` 时请求 `CapturePreview` 方法。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-120">You implement the `Invoke` method and `CoreWebView2` requests your `Invoke` method when `CapturePreview` request completes.</span></span>  <span data-ttu-id="4d1ba-121">单个参数 `HRESULT` 用于描述请求的成功或失败 `CapturePreview` 代码。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-121">The single parameter is the `HRESULT` describing the success or failure code of the `CapturePreview` request.</span></span>  

<span data-ttu-id="4d1ba-122">或者，对于 ，您提供一个实例，该实例具有一个方法，用于提供 `ICoreWebView2::ExecuteScript` `Invoke` 请求的成功或失败 `ExecuteScript` 代码。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-122">Alternately, for `ICoreWebView2::ExecuteScript`, you provide an instance that has an `Invoke` method that provides you with the success or failure code of the `ExecuteScript` request.</span></span>  <span data-ttu-id="4d1ba-123">另外提供第二个参数，该参数是运行脚本的结果的 JSON。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-123">Also provide the second parameter that is the JSON of the result of running the script.</span></span>  

<span data-ttu-id="4d1ba-124">可以手动实现委托接口，也可以将 Callback 函数 (`CompleteHandler` [WRL) ][CppCxWrlCallbackFunction]。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-124">You may manually implement the `CompleteHandler` delegate interfaces, or you may use the [Callback function (WRL)][CppCxWrlCallbackFunction].</span></span>  <span data-ttu-id="4d1ba-125">以下 [WebView2 (代码) 使用 WRL ][CppCxWrlCallbackFunction] 代码段中的 Callback 函数。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-125">The [Callback function (WRL)][CppCxWrlCallbackFunction] is used throughout the following WebView2 code snippet.</span></span>  

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

## <a name="events"></a><span data-ttu-id="4d1ba-126">事件</span><span class="sxs-lookup"><span data-stu-id="4d1ba-126">Events</span></span>  

<span data-ttu-id="4d1ba-127">WebView2 Win32 C++ API 中的事件使用 和 方法对订阅和 `add_EventName` `remove_EventName` 取消订阅事件。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-127">Events in the WebView2 Win32 C++ API use the `add_EventName` and `remove_EventName` method pair to subscribe and unsubscribe from events.</span></span>  <span data-ttu-id="4d1ba-128">`add_EventName`方法采用事件处理程序委托接口，并作为 `EventRegistrationToken` 输出参数返回令牌。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-128">The `add_EventName` method takes an event handler delegate interface and gives back an `EventRegistrationToken` token as an output parameter.</span></span>  <span data-ttu-id="4d1ba-129">`remove_EventName`方法获取令牌 `EventRegistrationToken` 并取消订阅相应的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-129">The `remove_EventName` method takes an `EventRegistrationToken` token and unsubscribes the corresponding event subscription.</span></span>  

<span data-ttu-id="4d1ba-130">事件处理程序委托接口与异步方法完成的处理程序委托接口类似。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-130">Event handler delegate interfaces work similarly to the async method completed handler delegate interfaces.</span></span>  <span data-ttu-id="4d1ba-131">实现事件处理程序委托接口， `CoreWebView2` 并每当事件运行时发送回调。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-131">You implement the event handler delegate interface and `CoreWebView2` sends a callback whenever the event runs.</span></span>  <span data-ttu-id="4d1ba-132">每个事件处理程序委托接口都有一个方法，该方法具有 `Invoke` 一个 sender 参数，后跟一个事件参数。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-132">Every event handler delegate interface has a single `Invoke` method that has a sender parameter followed by an event args parameter.</span></span>  <span data-ttu-id="4d1ba-133">发件人是您为事件订阅的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-133">The sender is the instance of the object on which you subscribed for events.</span></span>  <span data-ttu-id="4d1ba-134">事件参数是一个包含当前触发事件相关信息的接口。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-134">The event args parameter is an interface that contains information about the currently firing event.</span></span>  

<span data-ttu-id="4d1ba-135">例如，上的 `NavigationCompleted` 事件 `ICoreWebView2` 具有 和 `ICoreWebView2::add_NavigationCompleted` `ICoreWebView2::remove_NavigationCompleted` 方法对。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-135">For instance, the `NavigationCompleted` event on `ICoreWebView2` has the `ICoreWebView2::add_NavigationCompleted` and `ICoreWebView2::remove_NavigationCompleted` method pair.</span></span>  <span data-ttu-id="4d1ba-136">发送请求时，提供之前实现 `ICoreWebView2NavigationCompletedEventHandler` 方法的实例 `Invoke` 。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-136">When you send a request, you provide an instance of `ICoreWebView2NavigationCompletedEventHandler` in which you previously implemented `Invoke` method.</span></span>  <span data-ttu-id="4d1ba-137">当 `NavigationCompleted` 事件运行时， `Invoke` 将请求方法。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-137">When the `NavigationCompleted` event runs, your `Invoke` method is requested.</span></span>  <span data-ttu-id="4d1ba-138">第一个参数运行 `NavigationCompleted` 事件。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-138">The first parameter runs the `NavigationCompleted` event.</span></span>  <span data-ttu-id="4d1ba-139">第二个参数包含有关导航是否成功完成的信息，等等。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-139">The second parameter contains information about if the navigation completed successfully and so on.</span></span>  

<span data-ttu-id="4d1ba-140">与异步方法完成的处理程序委托接口类似，请使用以下操作之一进行设置。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-140">Similar to the async method completed handler delegate interface, use one of the following actions to set it up.</span></span>  

*   <span data-ttu-id="4d1ba-141">直接实现。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-141">Implement it directly.</span></span>  
*   <span data-ttu-id="4d1ba-142">将 [Callback 函数 (WebView2) ][CppCxWrlCallbackFunction] 代码段中使用的 WRL 对象函数。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-142">Use the [Callback function (WRL)][CppCxWrlCallbackFunction] function that is used in the following WebView2 code snippet.</span></span>  

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

## <a name="strings"></a><span data-ttu-id="4d1ba-143">字符串</span><span class="sxs-lookup"><span data-stu-id="4d1ba-143">Strings</span></span>  

<span data-ttu-id="4d1ba-144">字符串输出参数是 `LPWSTR` 以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-144">String output parameters are `LPWSTR` null-terminated strings.</span></span>  <span data-ttu-id="4d1ba-145">请求程序使用 提供字符串 `CoTaskMemAlloc` 。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-145">The requester provides the string using `CoTaskMemAlloc`.</span></span>  <span data-ttu-id="4d1ba-146">所有权将传输到请求者，由请求者使用 释放内存 `CoTaskMemFree` 。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-146">Ownership is transferred to the requester and it is up to the requester to free the memory using `CoTaskMemFree`.</span></span>  

<span data-ttu-id="4d1ba-147">字符串输入参数是 `LPCWSTR` 以 null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-147">String input parameters are `LPCWSTR` null-terminated strings.</span></span>  <span data-ttu-id="4d1ba-148">请求者确保字符串在同步函数请求的持续时间内有效。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-148">The requester ensures the string is valid for the duration of the synchronous function request.</span></span>  <span data-ttu-id="4d1ba-149">如果接收器必须在函数请求完成后将值存储到某一点，则接收器必须提供字符串值的关联副本。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-149">If the receiver must store the value to some point after the function request completes, the receiver must give an associated copy of the string value.</span></span>  

## <a name="uri-and-json-parsing"></a><span data-ttu-id="4d1ba-150">URI 和 JSON 分析</span><span class="sxs-lookup"><span data-stu-id="4d1ba-150">URI and JSON parsing</span></span>  

<span data-ttu-id="4d1ba-151">各种方法提供或接受 URI 和 JSON 作为字符串。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-151">Various methods provide or accept URIs and JSON as strings.</span></span>  <span data-ttu-id="4d1ba-152">使用首选库分析和生成字符串。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-152">Use your preferred library for parsing and generating the strings.</span></span>  

<span data-ttu-id="4d1ba-153">如果 WinRT 可用于你的应用，你可能会使用 和 方法来分析或生成 JSON 字符串或方法来 `RuntimeClass_Windows_Data_Json_JsonObject` `IJsonObjectStatics` `RuntimeClass_Windows_Foundation_Uri` `IUriRuntimeClassFactory` 分析和生成 URI。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-153">If WinRT is available for your app, you may use the `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` methods to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` methods to parse and produce URIs.</span></span>  <span data-ttu-id="4d1ba-154">这两种方法均在 Win32 应用中工作。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-154">Both of methods work in Win32 apps.</span></span>  

<span data-ttu-id="4d1ba-155">如果使用 和 解析 URI，可能需要使用以下 URI 创建标志，使行为与 WebView 中的 URI 分析更 `IUri` `CreateUri` `CreateUri` 匹配。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-155">If you use `IUri` and `CreateUri` to parse URIs, you may want to use the following URI creation flags to have `CreateUri` behavior more closely match the URI parsing in the WebView.</span></span>  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

## <a name="see-also"></a><span data-ttu-id="4d1ba-156">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4d1ba-156">See also</span></span>  

*   <span data-ttu-id="4d1ba-157">若要开始使用 WebView2 Win32 C/C++，请导航到 [WebView2 入门][Webview2IndexGettingStarted] 指南。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-157">To get started using WebView2 Win32 C/C++, navigate to [Getting started with WebView2][Webview2IndexGettingStarted] guides.</span></span>  
*   <span data-ttu-id="4d1ba-158">有关 WebView2 API 的更多详细信息，请导航到 [API 参考][DotnetApiMicrosoftWebWebview2WpfWebview2]。</span><span class="sxs-lookup"><span data-stu-id="4d1ba-158">For more detailed information about WebView2 APIs, navigate to [API reference][DotnetApiMicrosoftWebWebview2WpfWebview2].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-webview-team"></a><span data-ttu-id="4d1ba-159">与 Microsoft Edge WebView 团队联系</span><span class="sxs-lookup"><span data-stu-id="4d1ba-159">Getting in touch with the Microsoft Edge WebView team</span></span>  

[!INCLUDE [contact WebView team note](../includes/contact-webview-team-note.md)]  

<!-- links -->  

[Webview2GettingstartedWin32]: ../gettingstarted/win32.md "WebView2 应用程序|Microsoft Docs"  

[Webview2ReferenceWin32Icorewebview2CapturePreview]: /microsoft-edge/webview2/reference/win32/icorewebview2#capturepreview "CapturePreview - 接口 ICoreWebView2 |Microsoft Docs"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "WRL (回调) |Microsoft Docs"  

[DotnetApiMicrosoftWebWebview2WpfWebview2]: /dotnet/api/microsoft.web.webview2.wpf.webview2 "WebView2 类|Microsoft Docs"  
