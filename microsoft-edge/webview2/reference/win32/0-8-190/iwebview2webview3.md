---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 0.8.355-WebView2 Win32 c + + IWebView2WebView3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/20/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: a095b1ed085cd49a597195e01da21cde53b9095d
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10884741"
---
# <span data-ttu-id="2e853-104">0.8.355-接口 IWebView2WebView3</span><span class="sxs-lookup"><span data-stu-id="2e853-104">0.8.355 - interface IWebView2WebView3</span></span> 

[!INCLUDE [deprecation-note](../../includes/deprecation-note.md)]

```
interface IWebView2WebView3
  : public IWebView2WebView
```

<span data-ttu-id="2e853-105">由主 Web 视图对象实现的附加功能。</span><span class="sxs-lookup"><span data-stu-id="2e853-105">Additional functionality implemented by the primary WebView object.</span></span>

## <span data-ttu-id="2e853-106">摘要</span><span class="sxs-lookup"><span data-stu-id="2e853-106">Summary</span></span>

 <span data-ttu-id="2e853-107">成员</span><span class="sxs-lookup"><span data-stu-id="2e853-107">Members</span></span>                        | <span data-ttu-id="2e853-108">描述</span><span class="sxs-lookup"><span data-stu-id="2e853-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="2e853-109">停止</span><span class="sxs-lookup"><span data-stu-id="2e853-109">Stop</span></span>](#stop) | <span data-ttu-id="2e853-110">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="2e853-110">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="2e853-111">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="2e853-111">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="2e853-112">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-112">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="2e853-113">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="2e853-113">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="2e853-114">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-114">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="2e853-115">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="2e853-115">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="2e853-116">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-116">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="2e853-117">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="2e853-117">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="2e853-118">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-118">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="2e853-119">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="2e853-119">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="2e853-120">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="2e853-120">The title for the current top level document.</span></span>

<span data-ttu-id="2e853-121">你可以从实现[IWebView2WebView](IWebView2WebView.md)的对象中为此接口执行 QueryInterface。</span><span class="sxs-lookup"><span data-stu-id="2e853-121">You can QueryInterface for this interface from the object that implements [IWebView2WebView](IWebView2WebView.md).</span></span> <span data-ttu-id="2e853-122">有关详细信息，请参阅[IWebView2WebView](IWebView2WebView.md)界面。</span><span class="sxs-lookup"><span data-stu-id="2e853-122">See the [IWebView2WebView](IWebView2WebView.md) interface for more details.</span></span>

## <span data-ttu-id="2e853-123">成员</span><span class="sxs-lookup"><span data-stu-id="2e853-123">Members</span></span>

#### <span data-ttu-id="2e853-124">停止</span><span class="sxs-lookup"><span data-stu-id="2e853-124">Stop</span></span> 

<span data-ttu-id="2e853-125">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="2e853-125">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="2e853-126">公共 HRESULT[停止](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="2e853-126">public HRESULT [Stop](#stop)()</span></span>

#### <span data-ttu-id="2e853-127">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="2e853-127">add_NewWindowRequested</span></span> 

<span data-ttu-id="2e853-128">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-128">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="2e853-129">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)（[IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="2e853-129">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([IWebView2NewWindowRequestedEventHandler](IWebView2NewWindowRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2e853-130">在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。</span><span class="sxs-lookup"><span data-stu-id="2e853-130">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span> <span data-ttu-id="2e853-131">应用可以传递将被视为打开的窗口的目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="2e853-131">The app can pass a target webview that will be considered the opened window.</span></span>

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

#### <span data-ttu-id="2e853-132">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="2e853-132">remove_NewWindowRequested</span></span> 

<span data-ttu-id="2e853-133">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-133">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="2e853-134">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="2e853-134">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2e853-135">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="2e853-135">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="2e853-136">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-136">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="2e853-137">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)（[IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="2e853-137">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([IWebView2DocumentTitleChangedEventHandler](IWebView2DocumentTitleChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="2e853-138">当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="2e853-138">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

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

#### <span data-ttu-id="2e853-139">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="2e853-139">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="2e853-140">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="2e853-140">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="2e853-141">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="2e853-141">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="2e853-142">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="2e853-142">get_DocumentTitle</span></span> 

<span data-ttu-id="2e853-143">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="2e853-143">The title for the current top level document.</span></span>

> <span data-ttu-id="2e853-144">公共 HRESULT [get_DocumentTitle](#get_documenttitle)（LPWSTR \* 标题）</span><span class="sxs-lookup"><span data-stu-id="2e853-144">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="2e853-145">如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。</span><span class="sxs-lookup"><span data-stu-id="2e853-145">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

