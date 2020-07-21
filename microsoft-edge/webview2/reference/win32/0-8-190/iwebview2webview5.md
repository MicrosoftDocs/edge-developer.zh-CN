---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: bc48c5d495c2182ba39b867fdb46ce7af503f5ba
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884685"
---
# <span data-ttu-id="b6904-104">0.8.355-接口 IWebView2WebView5</span><span class="sxs-lookup"><span data-stu-id="b6904-104">0.8.355 - interface IWebView2WebView5</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView5
  : public IWebView2WebView4
```

<span data-ttu-id="b6904-105">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="b6904-105">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="b6904-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b6904-106">Summary</span></span>

 <span data-ttu-id="b6904-107">成员</span><span class="sxs-lookup"><span data-stu-id="b6904-107">Members</span></span>                        | <span data-ttu-id="b6904-108">描述</span><span class="sxs-lookup"><span data-stu-id="b6904-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b6904-109">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="b6904-109">add_ContainsFullScreenElementChanged</span></span>](#add_containsfullscreenelementchanged) | <span data-ttu-id="b6904-110">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="b6904-110">Notifies when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="b6904-111">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="b6904-111">remove_ContainsFullScreenElementChanged</span></span>](#remove_containsfullscreenelementchanged) | <span data-ttu-id="b6904-112">删除以前使用相应的 add_ 事件方法添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b6904-112">Remove an event handler previously added with the corresponding add_ event method.</span></span>
[<span data-ttu-id="b6904-113">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="b6904-113">get_ContainsFullScreenElement</span></span>](#get_containsfullscreenelement) | <span data-ttu-id="b6904-114">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="b6904-114">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="b6904-115">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="b6904-115">add_WebResourceRequested</span></span>](#add_webresourcerequested) | <span data-ttu-id="b6904-116">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b6904-116">Add an event handler for the WebResourceRequested event.</span></span>
[<span data-ttu-id="b6904-117">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="b6904-117">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="b6904-118">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="b6904-118">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="b6904-119">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="b6904-119">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="b6904-120">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="b6904-120">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

<span data-ttu-id="b6904-121">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="b6904-121">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="b6904-122">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="b6904-122">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="b6904-123">成员</span><span class="sxs-lookup"><span data-stu-id="b6904-123">Members</span></span>

#### <span data-ttu-id="b6904-124">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="b6904-124">add_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="b6904-125">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="b6904-125">Notifies when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="b6904-126">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)（[IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="b6904-126">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([IWebView2ContainsFullScreenElementChangedEventHandler](IWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="b6904-127">这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。</span><span class="sxs-lookup"><span data-stu-id="b6904-127">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="b6904-128">例如，当视频元素请求进入全屏时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="b6904-128">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="b6904-129">然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="b6904-129">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

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

#### <span data-ttu-id="b6904-130">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="b6904-130">remove_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="b6904-131">删除以前使用相应的 add_ 事件方法添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b6904-131">Remove an event handler previously added with the corresponding add_ event method.</span></span>

> <span data-ttu-id="b6904-132">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="b6904-132">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="b6904-133">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="b6904-133">get_ContainsFullScreenElement</span></span> 

<span data-ttu-id="b6904-134">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="b6904-134">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="b6904-135">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)（BOOL \* ContainsFullScreenElement）</span><span class="sxs-lookup"><span data-stu-id="b6904-135">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* containsFullScreenElement)</span></span>

#### <span data-ttu-id="b6904-136">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="b6904-136">add_WebResourceRequested</span></span> 

<span data-ttu-id="b6904-137">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="b6904-137">Add an event handler for the WebResourceRequested event.</span></span>

> <span data-ttu-id="b6904-138">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)（[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="b6904-138">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)([IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="b6904-139">在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="b6904-139">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span> <span data-ttu-id="b6904-140">必须至少添加一个筛选器，才能触发该事件。</span><span class="sxs-lookup"><span data-stu-id="b6904-140">At least one filter must be added for the event to fire.</span></span>

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

#### <span data-ttu-id="b6904-141">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="b6904-141">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="b6904-142">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="b6904-142">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="b6904-143">公共 HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（LPCWSTR const uri，[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext）</span><span class="sxs-lookup"><span data-stu-id="b6904-143">public HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri,[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="b6904-144">URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。</span><span class="sxs-lookup"><span data-stu-id="b6904-144">URI parameter can be a wildcard string ('': zero or more, '?': exactly one).</span></span> <span data-ttu-id="b6904-145">nullptr 等效于 L ""。</span><span class="sxs-lookup"><span data-stu-id="b6904-145">nullptr is equivalent to L"".</span></span> <span data-ttu-id="b6904-146">有关资源上下文筛选器的说明，请参阅 WEBVIEW2_WEB_RESOURCE_CONTEXT enum。</span><span class="sxs-lookup"><span data-stu-id="b6904-146">See WEBVIEW2_WEB_RESOURCE_CONTEXT enum for description of resource context filters.</span></span>

#### <span data-ttu-id="b6904-147">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="b6904-147">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="b6904-148">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="b6904-148">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="b6904-149">公共 HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（LPCWSTR const uri，[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext）</span><span class="sxs-lookup"><span data-stu-id="b6904-149">public HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri,[WEBVIEW2_WEB_RESOURCE_CONTEXT](IWebView2WebView.md#webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="b6904-150">如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。</span><span class="sxs-lookup"><span data-stu-id="b6904-150">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="b6904-151">返回从未添加的筛选器 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="b6904-151">Returns E_INVALIDARG for a filter that was never added.</span></span>

