---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/14/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: cfb99be772170ee458fa252133f90240d75af3db
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10878048"
---
# <span data-ttu-id="9cf75-104">0.8.355-接口 IWebView2WebView3</span><span class="sxs-lookup"><span data-stu-id="9cf75-104">0.8.355 - interface IWebView2WebView3</span></span> 

> [!NOTE]
> <span data-ttu-id="9cf75-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="9cf75-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="9cf75-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="9cf75-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView3
  : public IWebView2WebView
```

<span data-ttu-id="9cf75-107">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="9cf75-107">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="9cf75-108">摘要</span><span class="sxs-lookup"><span data-stu-id="9cf75-108">Summary</span></span>

 <span data-ttu-id="9cf75-109">成员</span><span class="sxs-lookup"><span data-stu-id="9cf75-109">Members</span></span>                        | <span data-ttu-id="9cf75-110">描述</span><span class="sxs-lookup"><span data-stu-id="9cf75-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="9cf75-111">停止</span><span class="sxs-lookup"><span data-stu-id="9cf75-111">Stop</span></span>](#stop) | <span data-ttu-id="9cf75-112">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="9cf75-112">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="9cf75-113">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="9cf75-113">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="9cf75-114">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-114">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="9cf75-115">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="9cf75-115">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="9cf75-116">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-116">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="9cf75-117">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="9cf75-117">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="9cf75-118">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-118">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="9cf75-119">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="9cf75-119">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="9cf75-120">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-120">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="9cf75-121">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="9cf75-121">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="9cf75-122">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="9cf75-122">The title for the current top level document.</span></span>

<span data-ttu-id="9cf75-123">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="9cf75-123">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="9cf75-124">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="9cf75-124">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="9cf75-125">成员</span><span class="sxs-lookup"><span data-stu-id="9cf75-125">Members</span></span>

#### <span data-ttu-id="9cf75-126">停止</span><span class="sxs-lookup"><span data-stu-id="9cf75-126">Stop</span></span> 

<span data-ttu-id="9cf75-127">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="9cf75-127">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="9cf75-128">公共 HRESULT[停止](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="9cf75-128">public HRESULT [Stop](#stop)()</span></span>

#### <span data-ttu-id="9cf75-129">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="9cf75-129">add_NewWindowRequested</span></span> 

<span data-ttu-id="9cf75-130">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-130">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="9cf75-131">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)（[IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="9cf75-131">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="9cf75-132">在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。</span><span class="sxs-lookup"><span data-stu-id="9cf75-132">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span> <span data-ttu-id="9cf75-133">应用可以传递将被视为打开的窗口的目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="9cf75-133">The app can pass a target webview that will be considered the opened window.</span></span>

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

#### <span data-ttu-id="9cf75-134">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="9cf75-134">remove_NewWindowRequested</span></span> 

<span data-ttu-id="9cf75-135">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-135">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="9cf75-136">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="9cf75-136">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="9cf75-137">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="9cf75-137">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="9cf75-138">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-138">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="9cf75-139">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)（[IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="9cf75-139">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="9cf75-140">当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="9cf75-140">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

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

#### <span data-ttu-id="9cf75-141">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="9cf75-141">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="9cf75-142">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="9cf75-142">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="9cf75-143">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="9cf75-143">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="9cf75-144">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="9cf75-144">get_DocumentTitle</span></span> 

<span data-ttu-id="9cf75-145">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="9cf75-145">The title for the current top level document.</span></span>

> <span data-ttu-id="9cf75-146">公共 HRESULT [get_DocumentTitle](#get_documenttitle)（LPWSTR \* 标题）</span><span class="sxs-lookup"><span data-stu-id="9cf75-146">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="9cf75-147">如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。</span><span class="sxs-lookup"><span data-stu-id="9cf75-147">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

