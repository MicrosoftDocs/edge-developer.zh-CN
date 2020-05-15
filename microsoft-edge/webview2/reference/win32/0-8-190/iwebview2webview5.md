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
# <span data-ttu-id="7b1b8-104">interface IWebView2WebView5</span><span class="sxs-lookup"><span data-stu-id="7b1b8-104">interface IWebView2WebView5</span></span> 

> [!NOTE]
> <span data-ttu-id="7b1b8-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="7b1b8-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView5
  : public IWebView2WebView4
```

<span data-ttu-id="7b1b8-107">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="7b1b8-108">摘要</span><span class="sxs-lookup"><span data-stu-id="7b1b8-108">Summary</span></span>

 <span data-ttu-id="7b1b8-109">成员</span><span class="sxs-lookup"><span data-stu-id="7b1b8-109">Members</span></span>                        | <span data-ttu-id="7b1b8-110">描述</span><span class="sxs-lookup"><span data-stu-id="7b1b8-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="7b1b8-111">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="7b1b8-111">add_ContainsFullScreenElementChanged</span></span>](#add_containsfullscreenelementchanged) | <span data-ttu-id="7b1b8-112">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-112">Notifies when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="7b1b8-113">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="7b1b8-113">remove_ContainsFullScreenElementChanged</span></span>](#remove_containsfullscreenelementchanged) | <span data-ttu-id="7b1b8-114">删除以前使用相应的 add_ 事件方法添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-114">Remove an event handler previously added with the corresponding add_ event method.</span></span>
[<span data-ttu-id="7b1b8-115">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="7b1b8-115">get_ContainsFullScreenElement</span></span>](#get_containsfullscreenelement) | <span data-ttu-id="7b1b8-116">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-116">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="7b1b8-117">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="7b1b8-117">add_WebResourceRequested</span></span>](#add_webresourcerequested) | <span data-ttu-id="7b1b8-118">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-118">Add an event handler for the WebResourceRequested event.</span></span>
[<span data-ttu-id="7b1b8-119">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="7b1b8-119">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="7b1b8-120">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-120">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="7b1b8-121">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="7b1b8-121">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="7b1b8-122">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-122">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

<span data-ttu-id="7b1b8-123">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-123">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="7b1b8-124">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-124">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="7b1b8-125">成员</span><span class="sxs-lookup"><span data-stu-id="7b1b8-125">Members</span></span>

#### <span data-ttu-id="7b1b8-126">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="7b1b8-126">add_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="7b1b8-127">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-127">Notifies when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="7b1b8-128">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)（[IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="7b1b8-128">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="7b1b8-129">这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-129">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="7b1b8-130">例如，当视频元素请求进入全屏时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-130">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="7b1b8-131">然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-131">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

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

#### <span data-ttu-id="7b1b8-132">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="7b1b8-132">remove_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="7b1b8-133">删除以前使用相应的 add_ 事件方法添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-133">Remove an event handler previously added with the corresponding add_ event method.</span></span>

> <span data-ttu-id="7b1b8-134">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="7b1b8-134">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="7b1b8-135">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="7b1b8-135">get_ContainsFullScreenElement</span></span> 

<span data-ttu-id="7b1b8-136">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-136">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="7b1b8-137">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)（BOOL \* ContainsFullScreenElement）</span><span class="sxs-lookup"><span data-stu-id="7b1b8-137">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* containsFullScreenElement)</span></span>

#### <span data-ttu-id="7b1b8-138">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="7b1b8-138">add_WebResourceRequested</span></span> 

<span data-ttu-id="7b1b8-139">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-139">Add an event handler for the WebResourceRequested event.</span></span>

> <span data-ttu-id="7b1b8-140">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)（[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="7b1b8-140">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)([IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="7b1b8-141">在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-141">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span> <span data-ttu-id="7b1b8-142">必须至少添加一个筛选器，才能触发该事件。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-142">At least one filter must be added for the event to fire.</span></span>

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

#### <span data-ttu-id="7b1b8-143">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="7b1b8-143">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="7b1b8-144">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-144">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="7b1b8-145">公共 HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（LPCWSTR const uri，[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext）</span><span class="sxs-lookup"><span data-stu-id="7b1b8-145">public HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri,[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="7b1b8-146">URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-146">URI parameter can be a wildcard string ('': zero or more, '?': exactly one).</span></span> <span data-ttu-id="7b1b8-147">nullptr 等效于 L ""。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-147">nullptr is equivalent to L"".</span></span> <span data-ttu-id="7b1b8-148">有关资源上下文筛选器的说明，请参阅 WEBVIEW2_WEB_RESOURCE_CONTEXT enum。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-148">See WEBVIEW2_WEB_RESOURCE_CONTEXT enum for description of resource context filters.</span></span>

#### <span data-ttu-id="7b1b8-149">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="7b1b8-149">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="7b1b8-150">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-150">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="7b1b8-151">公共 HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（LPCWSTR const uri，[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext）</span><span class="sxs-lookup"><span data-stu-id="7b1b8-151">public HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri,[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="7b1b8-152">如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-152">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="7b1b8-153">返回从未添加的筛选器 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="7b1b8-153">Returns E_INVALIDARG for a filter that was never added.</span></span>

