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
# <span data-ttu-id="dc24d-104">Win32 c + + WebView2 API 约定</span><span class="sxs-lookup"><span data-stu-id="dc24d-104">Win32 C++ WebView2 API conventions</span></span>  

## <span data-ttu-id="dc24d-105">异步方法</span><span class="sxs-lookup"><span data-stu-id="dc24d-105">Async Methods</span></span>  

<span data-ttu-id="dc24d-106">WebView2 Win32 c + + API 中的异步方法使用委托接口来回调你，以指示 async 方法已完成的时间、成功或失败代码以及异步方法的结果。</span><span class="sxs-lookup"><span data-stu-id="dc24d-106">Asynchronous methods in the WebView2 Win32 C++ API use a delegate interface to callback to you to indicate when the async method has completed, the success or failure code, and for some, the result of the asynchronous method.</span></span>  <span data-ttu-id="dc24d-107">所有异步方法的最终参数都是一个指向你为其提供实现的委托接口的指针。</span><span class="sxs-lookup"><span data-stu-id="dc24d-107">The final parameter for all asynchronous methods is a pointer to a delegate interface of which you provide an implementation.</span></span>  

<span data-ttu-id="dc24d-108">委托接口具有一个 `Invoke` 方法，该方法作为第一个参数作为 `HRESULT` 成功或失败代码。</span><span class="sxs-lookup"><span data-stu-id="dc24d-108">The delegate interface has a single `Invoke` method that takes as a first parameter an `HRESULT` of the success or failure code.</span></span>  <span data-ttu-id="dc24d-109">此外，如果方法具有结果，则可能会出现第二个参数，该参数是方法的结果。</span><span class="sxs-lookup"><span data-stu-id="dc24d-109">Additionally there may be a second parameter that is the result of the method if the method has a result.</span></span>  <span data-ttu-id="dc24d-110">例如， [ICoreWebView2：： CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] 方法作为最终参数接受 `ICoreWebView2CapturePreviewCompletedHandler` 指针。</span><span class="sxs-lookup"><span data-stu-id="dc24d-110">For example, the [ICoreWebView2::CapturePreview][Webview2ReferenceWin32Icorewebview2CapturePreview] method takes as the final parameter an `ICoreWebView2CapturePreviewCompletedHandler` pointer.</span></span>  <span data-ttu-id="dc24d-111">若要发送 `CapturePreview` 方法请求，请提供 `ICoreWebView2CapturePreviewCompletedHandler` 你实现的指针的实例。</span><span class="sxs-lookup"><span data-stu-id="dc24d-111">To send a `CapturePreview` method request, you provide an instance of the `ICoreWebView2CapturePreviewCompletedHandler` pointer that you implement.</span></span>  <span data-ttu-id="dc24d-112">下面的代码片段使用一种方法实现。</span><span class="sxs-lookup"><span data-stu-id="dc24d-112">The following code snippet uses one method to implement.</span></span>  

```cpp
HRESULT Invoke(HRESULT result)
```  

<span data-ttu-id="dc24d-113">在 `Invoke` 请求完成后，实现该方法并 `CoreWebView2` 请求你的 `Invoke` 方法 `CapturePreview` 。</span><span class="sxs-lookup"><span data-stu-id="dc24d-113">You implement the `Invoke` method and `CoreWebView2` requests your `Invoke` method when `CapturePreview` request completes.</span></span>  <span data-ttu-id="dc24d-114">单个参数 `HRESULT` 描述请求的成功或失败代码 `CapturePreview` 。</span><span class="sxs-lookup"><span data-stu-id="dc24d-114">The single parameter is the `HRESULT` describing the success or failure code of the `CapturePreview` request.</span></span>  

<span data-ttu-id="dc24d-115">或者 `ICoreWebView2::ExecuteScript` ，你提供的实例 `ICoreWebView2ExecuteScriptCompletedHandler` 具有一个 `Invoke` 方法，该方法为你提供请求的成功或失败代码，以及 `ExecuteScript` 第二个参数， `resultObjectAsJson` 这是运行脚本的结果的 JSON。</span><span class="sxs-lookup"><span data-stu-id="dc24d-115">Or for `ICoreWebView2::ExecuteScript`, you provide an instance of `ICoreWebView2ExecuteScriptCompletedHandler` which has an `Invoke` method that provides you with the success or failure code of the `ExecuteScript` request as well as the second parameter `resultObjectAsJson` which is the JSON of the result of running the script.</span></span>  

<span data-ttu-id="dc24d-116">你可以手动实现 `CompleteHandler` 委托接口，也可以使用 [WRL 回调函数][CppCxWrlCallbackFunction]。</span><span class="sxs-lookup"><span data-stu-id="dc24d-116">You may manually implement the `CompleteHandler` delegate interfaces, or you may use the [WRL Callback function][CppCxWrlCallbackFunction].</span></span>  <span data-ttu-id="dc24d-117">回调函数在以下 WebView2 代码段中使用。</span><span class="sxs-lookup"><span data-stu-id="dc24d-117">The Callback function is used throughout the following WebView2 code snippet.</span></span>  

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

## <span data-ttu-id="dc24d-118">事件</span><span class="sxs-lookup"><span data-stu-id="dc24d-118">Events</span></span>  

<span data-ttu-id="dc24d-119">WebView2 Win32 c + + API 中的事件使用 `add_EventName` and `remove_EventName` 方法对来订阅和取消订阅事件。</span><span class="sxs-lookup"><span data-stu-id="dc24d-119">Events in the WebView2 Win32 C++ API use the `add_EventName` and `remove_EventName` method pair to subscribe and unsubscribe from events.</span></span>  <span data-ttu-id="dc24d-120">该 `add_EventName` 方法采用事件处理程序委托接口，并返回一个 `EventRegistrationToken` 作为 out 参数。</span><span class="sxs-lookup"><span data-stu-id="dc24d-120">The `add_EventName` method takes an event handler delegate interface and gives back an `EventRegistrationToken` as an out parameter.</span></span>  <span data-ttu-id="dc24d-121">该 `remove_EventName` 方法将接受 `EventRegistrationToken` 并取消预订相应的事件订阅。</span><span class="sxs-lookup"><span data-stu-id="dc24d-121">The `remove_EventName` method takes an `EventRegistrationToken` and unsubscribes the corresponding event subscription.</span></span>  

<span data-ttu-id="dc24d-122">事件处理程序委托接口的工作非常类似于 async 方法完成的处理程序委托接口。</span><span class="sxs-lookup"><span data-stu-id="dc24d-122">Event handler delegate interfaces work very similarly to the async method completed handler delegate interfaces.</span></span>  <span data-ttu-id="dc24d-123">实现事件处理程序委托接口，并在 `CoreWebView2` 引发事件时发送回调。</span><span class="sxs-lookup"><span data-stu-id="dc24d-123">You implement the event handler delegate interface and `CoreWebView2` sends a callback whenever the event fires.</span></span>  <span data-ttu-id="dc24d-124">每个事件处理程序委托接口都有一个 `Invoke` 方法，该方法具有一个发件人参数，后跟一个事件参数参数。</span><span class="sxs-lookup"><span data-stu-id="dc24d-124">Every event handler delegate interface has a single `Invoke` method that has a sender parameter followed by an event args parameter.</span></span>  <span data-ttu-id="dc24d-125">发件人是您为其订阅事件的对象的实例。</span><span class="sxs-lookup"><span data-stu-id="dc24d-125">The sender is the instance of the object on which you subscribed for events.</span></span>  <span data-ttu-id="dc24d-126">事件参数参数是一个接口，其中包含有关当前激发事件的信息。</span><span class="sxs-lookup"><span data-stu-id="dc24d-126">The event args parameter is an interface that contains information about the currently firing event.</span></span>  

<span data-ttu-id="dc24d-127">例如， `NavigationCompleted` 事件 `ICoreWebView2` 具有 `ICoreWebView2::add_NavigationCompleted` and `ICoreWebView2::remove_NavigationCompleted` 方法对。</span><span class="sxs-lookup"><span data-stu-id="dc24d-127">For instance the `NavigationCompleted` event on `ICoreWebView2` has the `ICoreWebView2::add_NavigationCompleted` and `ICoreWebView2::remove_NavigationCompleted` method pair.</span></span>  <span data-ttu-id="dc24d-128">请求 "添加" 时，你可以提供 `ICoreWebView2NavigationCompletedEventHandler` 你之前实现的方法的实例 `Invoke` 。</span><span class="sxs-lookup"><span data-stu-id="dc24d-128">When you request add you provide an instance of `ICoreWebView2NavigationCompletedEventHandler` in which you previously implemented `Invoke` method.</span></span>  <span data-ttu-id="dc24d-129">当 `NavigationCompleted` 引发该事件时， `Invoke` 将请求你的方法。</span><span class="sxs-lookup"><span data-stu-id="dc24d-129">When the `NavigationCompleted` event fires, your `Invoke` method is requested.</span></span>  <span data-ttu-id="dc24d-130">第一个参数是 `ICoreWebView2` 触发事件的参数 `NavigationCompleted` 。</span><span class="sxs-lookup"><span data-stu-id="dc24d-130">The first parameter is the `ICoreWebView2` which is firing the `NavigationCompleted` event.</span></span>  <span data-ttu-id="dc24d-131">第二个参数 `ICoreWebView2NavigationCompletedEventArgs` 包含有关导航是否已成功完成等的信息。</span><span class="sxs-lookup"><span data-stu-id="dc24d-131">The second parameter is the `ICoreWebView2NavigationCompletedEventArgs` which contains information about if the navigation completed successfully and so on.</span></span>  

<span data-ttu-id="dc24d-132">与 async 方法完成的处理程序委托接口类似，你可以直接实现它，或者你可以使用在以下 WebView2 代码段中使用的 WRL 回调函数。</span><span class="sxs-lookup"><span data-stu-id="dc24d-132">Similarly to the async method completed handler delegate interface you are able to implement it yourself directly, or you may use the WRL Callback function that is used in the following WebView2 code snippet.</span></span>  

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

## <span data-ttu-id="dc24d-133">字符串</span><span class="sxs-lookup"><span data-stu-id="dc24d-133">Strings</span></span>  

<span data-ttu-id="dc24d-134">字符串输出参数为以 `LPWSTR` null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="dc24d-134">String out parameters are `LPWSTR` null-terminated strings.</span></span>  <span data-ttu-id="dc24d-135">请求者使用分配的字符串 `CoTaskMemAlloc` 。</span><span class="sxs-lookup"><span data-stu-id="dc24d-135">The requester allocates the string using `CoTaskMemAlloc`.</span></span>  <span data-ttu-id="dc24d-136">所有权将转移到请求者，并由请求者使用释放内存 `CoTaskMemFree` 。</span><span class="sxs-lookup"><span data-stu-id="dc24d-136">Ownership is transferred to the requester and it is up to the requester to free the memory using `CoTaskMemFree`.</span></span>  

<span data-ttu-id="dc24d-137">参数中的字符串为以 `LPCWSTR` null 结尾的字符串。</span><span class="sxs-lookup"><span data-stu-id="dc24d-137">String in parameters are `LPCWSTR` null-terminated strings.</span></span>  <span data-ttu-id="dc24d-138">请求者确保字符串在同步函数请求的持续时间内有效。</span><span class="sxs-lookup"><span data-stu-id="dc24d-138">The requester ensures the string is valid for the duration of the synchronous function request.</span></span>  <span data-ttu-id="dc24d-139">如果接收方必须在函数请求完成后将该值保留到某个点，则接收方必须分配该字符串值的关联副本。</span><span class="sxs-lookup"><span data-stu-id="dc24d-139">If the receiver must retain that value to some point after the function request completes, the receiver must allocate an associated copy of the string value.</span></span>  

## <span data-ttu-id="dc24d-140">URI 和 JSON 分析</span><span class="sxs-lookup"><span data-stu-id="dc24d-140">URI and JSON parsing</span></span>  

<span data-ttu-id="dc24d-141">各种方法以字符串形式提供或接受 Uri 和 JSON。</span><span class="sxs-lookup"><span data-stu-id="dc24d-141">Various methods provide or accept URIs and JSON as strings.</span></span>  <span data-ttu-id="dc24d-142">请使用你的首选库来分析和生成字符串。</span><span class="sxs-lookup"><span data-stu-id="dc24d-142">Please use your own preferred library for parsing and generating the strings.</span></span>  

<span data-ttu-id="dc24d-143">如果 WinRT 适用于你的应用，你可以使用 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` 方法来分析或生成 JSON 字符串，或 `RuntimeClass_Windows_Foundation_Uri` 使用 `IUriRuntimeClassFactory` 方法来分析和生成 uri。</span><span class="sxs-lookup"><span data-stu-id="dc24d-143">If WinRT is available for your app, you may use the `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` methods to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` methods to parse and produce URIs.</span></span>  <span data-ttu-id="dc24d-144">两种方法在 Win32 应用中均可使用。</span><span class="sxs-lookup"><span data-stu-id="dc24d-144">Both of methods work in Win32 apps.</span></span>  

<span data-ttu-id="dc24d-145">如果你使用 `IUri` 和 `CreateUri` 分析 uri，你可能希望使用以下 URI 创建标志使 `CreateUri` 行为与 web 视图中的 URI 分析更紧密。</span><span class="sxs-lookup"><span data-stu-id="dc24d-145">If you use `IUri` and `CreateUri` to parse URIs, you may want to use the following URI creation flags to have `CreateUri` behavior more closely match the URI parsing in the WebView.</span></span>  

```json
Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO
```  

<!-- links -->  

[Webview2ReferenceWin32Icorewebview2CapturePreview]: /microsoft-edge/webview2/reference/win32/icorewebview2#capturepreview "CapturePreview-接口 ICoreWebView2 |Microsoft 文档"  

[CppCxWrlCallbackFunction]: /cpp/cppcx/wrl/callback-function-wrl "回调函数 (WRL) |Microsoft 文档"  
