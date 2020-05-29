---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/27/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: 532c898845125564ad5af6460dc8d1ff6464abfb
ms.sourcegitcommit: 83efa259be89cc773a82751242495a0a919d54cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2020
ms.locfileid: "10687802"
---
# <span data-ttu-id="25877-104">WinForms 类 WebView2 WebView2</span><span class="sxs-lookup"><span data-stu-id="25877-104">Microsoft.Web.WebView2.WinForms.WebView2 class</span></span> 

<span data-ttu-id="25877-105">命名空间： WebView2 \ WinForms </span><span class="sxs-lookup"><span data-stu-id="25877-105">Namespace: Microsoft.Web.WebView2.WinForms</span></span>\
<span data-ttu-id="25877-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="25877-106">Assembly: Microsoft.Web.WebView2.WinForms.dll</span></span>

```
class Microsoft.Web.WebView2.WinForms.WebView2
  : public Control
```

<span data-ttu-id="25877-107">用于在 WinForms 中嵌入 WebView2 的控件。</span><span class="sxs-lookup"><span data-stu-id="25877-107">Control to embed WebView2 in WinForms.</span></span>

## <span data-ttu-id="25877-108">摘要</span><span class="sxs-lookup"><span data-stu-id="25877-108">Summary</span></span>

 <span data-ttu-id="25877-109">成员</span><span class="sxs-lookup"><span data-stu-id="25877-109">Members</span></span>                        | <span data-ttu-id="25877-110">描述</span><span class="sxs-lookup"><span data-stu-id="25877-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="25877-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="25877-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="25877-112">导航开始到新 URI 并开始呈现该 URI 的内容后，ContentLoading 调度。</span><span class="sxs-lookup"><span data-stu-id="25877-112">ContentLoading dispatches after a navigation begins to a new URI and the content of that URI begins to render.</span></span>
[<span data-ttu-id="25877-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="25877-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="25877-114">当控件的[CoreWebView2](#corewebview2)已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="25877-114">This event is triggered when the control's [CoreWebView2](#corewebview2) has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="25877-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="25877-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="25877-116">在顶级文档导航完成后，NavigationCompleted 派单已成功呈现。</span><span class="sxs-lookup"><span data-stu-id="25877-116">NavigationCompleted dispatches after a navigate of the top level document completes rendering either successfully or not.</span></span>
[<span data-ttu-id="25877-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="25877-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="25877-118">新导航开始前一级文档的 NavigationStarting 调度 WebView2。</span><span class="sxs-lookup"><span data-stu-id="25877-118">NavigationStarting dispatches before a new navigate starts for the top level document of the WebView2.</span></span>
[<span data-ttu-id="25877-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="25877-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="25877-120">源属性更改后的 SourceChanged 调度。</span><span class="sxs-lookup"><span data-stu-id="25877-120">SourceChanged dispatches after the Source property changes.</span></span>
[<span data-ttu-id="25877-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="25877-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="25877-122">WebMessageReceived web 内容向应用主机发送一条消息至应用主机后的调度 `chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="25877-122">WebMessageReceived dispatches after web content sends a message to the app host via `chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="25877-123">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="25877-123">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="25877-124">基础 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="25877-124">The underlying CoreWebView2.</span></span>
[<span data-ttu-id="25877-125">来源</span><span class="sxs-lookup"><span data-stu-id="25877-125">Source</span></span>](#source) | <span data-ttu-id="25877-126">Source 属性是 WebView2 的顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="25877-126">The Source property is the URI of the top level document of the WebView2.</span></span>
[<span data-ttu-id="25877-127">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="25877-127">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="25877-128">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="25877-128">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="25877-129">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="25877-129">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="25877-130">如果 web 视图可以通过 GoBack 方法导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="25877-130">Returns true if the webview can navigate to a previous page in the navigation history via the GoBack method.</span></span>
[<span data-ttu-id="25877-131">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="25877-131">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="25877-132">如果 web 视图可通过 GoForward 方法导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="25877-132">Returns true if the webview can navigate to a next page in the navigation history via the GoForward method.</span></span>
[<span data-ttu-id="25877-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="25877-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="25877-134">显式触发控件的[CoreWebView2](#corewebview2)的初始化。</span><span class="sxs-lookup"><span data-stu-id="25877-134">Explicitly trigger initialization of the control's [CoreWebView2](#corewebview2).</span></span>
[<span data-ttu-id="25877-135">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="25877-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="25877-136">在 WebView2 的顶级文档中执行提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="25877-136">Executes the provided script in the top level document of the WebView2.</span></span>
[<span data-ttu-id="25877-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="25877-137">GoBack</span></span>](#goback) | <span data-ttu-id="25877-138">导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="25877-138">Navigate to the previous page in navigation history.</span></span>
[<span data-ttu-id="25877-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="25877-139">GoForward</span></span>](#goforward) | <span data-ttu-id="25877-140">导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="25877-140">Navigate to the next page in navigation history.</span></span>
[<span data-ttu-id="25877-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="25877-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="25877-142">将所提供的 HTML 呈现为 WebView2 的顶层文档。</span><span class="sxs-lookup"><span data-stu-id="25877-142">Render the provided HTML as the top level document of the WebView2.</span></span>
[<span data-ttu-id="25877-143">重载</span><span class="sxs-lookup"><span data-stu-id="25877-143">Reload</span></span>](#reload) | <span data-ttu-id="25877-144">重新加载 WebView2 的顶层文档。</span><span class="sxs-lookup"><span data-stu-id="25877-144">Reload the top level document of the WebView2.</span></span>
[<span data-ttu-id="25877-145">停止</span><span class="sxs-lookup"><span data-stu-id="25877-145">Stop</span></span>](#stop) | <span data-ttu-id="25877-146">停止 WebView2 中的任何正在进行的导航。</span><span class="sxs-lookup"><span data-stu-id="25877-146">Stop any in progress navigation in the WebView2.</span></span>
[<span data-ttu-id="25877-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="25877-147">WebView2</span></span>](#webview2) | <span data-ttu-id="25877-148">创建新的 WebView2 WinForms 控件。</span><span class="sxs-lookup"><span data-stu-id="25877-148">Create a new WebView2 WinForms control.</span></span>

## <span data-ttu-id="25877-149">成员</span><span class="sxs-lookup"><span data-stu-id="25877-149">Members</span></span>

#### <span data-ttu-id="25877-150">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="25877-150">ContentLoading</span></span> 

<span data-ttu-id="25877-151">导航开始到新 URI 并开始呈现该 URI 的内容后，ContentLoading 调度。</span><span class="sxs-lookup"><span data-stu-id="25877-151">ContentLoading dispatches after a navigation begins to a new URI and the content of that URI begins to render.</span></span>

> <span data-ttu-id="25877-152">公共事件 EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="25877-152">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="25877-153">这等效于 CoreWebView2 上的 ContentLoading 事件。</span><span class="sxs-lookup"><span data-stu-id="25877-153">This is equivalent to the ContentLoading event on the CoreWebView2.</span></span> <span data-ttu-id="25877-154">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-154">See CoreWebView2.ContentLoading documentation for more information.</span></span>

#### <span data-ttu-id="25877-155">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="25877-155">CoreWebView2Ready</span></span> 

<span data-ttu-id="25877-156">当控件的[CoreWebView2](#corewebview2)已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="25877-156">This event is triggered when the control's [CoreWebView2](#corewebview2) has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="25877-157">公共事件 EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="25877-157">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="25877-158">如果你需要在要影响其所有使用情况的 CoreWebView2 上执行一次设置操作（例如，添加事件处理程序、配置设置、安装文档创建脚本、添加主机对象），你应该处理此事件。</span><span class="sxs-lookup"><span data-stu-id="25877-158">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span>

<span data-ttu-id="25877-159">此事件不提供任何参数，并且发件人将成为 WebView2 控件，它的 CoreWebView2 属性将在首次有效（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="25877-159">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="25877-160">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="25877-160">NavigationCompleted</span></span> 

<span data-ttu-id="25877-161">在顶级文档导航完成后，NavigationCompleted 派单已成功呈现。</span><span class="sxs-lookup"><span data-stu-id="25877-161">NavigationCompleted dispatches after a navigate of the top level document completes rendering either successfully or not.</span></span>

> <span data-ttu-id="25877-162">公共事件 EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="25877-162">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="25877-163">这等效于 CoreWebView2 上的 NavigationCompleted 事件。</span><span class="sxs-lookup"><span data-stu-id="25877-163">This is equivalent to the NavigationCompleted event on the CoreWebView2.</span></span> <span data-ttu-id="25877-164">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-164">See CoreWebView2.NavigationCompleted documentation for more information.</span></span>

#### <span data-ttu-id="25877-165">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="25877-165">NavigationStarting</span></span> 

<span data-ttu-id="25877-166">新导航开始前一级文档的 NavigationStarting 调度 WebView2。</span><span class="sxs-lookup"><span data-stu-id="25877-166">NavigationStarting dispatches before a new navigate starts for the top level document of the WebView2.</span></span>

> <span data-ttu-id="25877-167">公共事件 EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="25877-167">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="25877-168">这等效于 CoreWebView2 上的 NavigationStarting 事件。</span><span class="sxs-lookup"><span data-stu-id="25877-168">This is equivalent to the NavigationStarting event on the CoreWebView2.</span></span> <span data-ttu-id="25877-169">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-169">See CoreWebView2.NavigationStarting documentation for more information.</span></span>

#### <span data-ttu-id="25877-170">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="25877-170">SourceChanged</span></span> 

<span data-ttu-id="25877-171">源属性更改后的 SourceChanged 调度。</span><span class="sxs-lookup"><span data-stu-id="25877-171">SourceChanged dispatches after the Source property changes.</span></span>

> <span data-ttu-id="25877-172">公共事件 EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="25877-172">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="25877-173">这可能会在导航期间发生，或者如果页面中的脚本更改了文档的 URI，则可能会发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="25877-173">This may happen during a navigation or if otherwise the script in the page changes the URI of the document.</span></span> <span data-ttu-id="25877-174">这等效于 CoreWebView2 上的 SourceChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="25877-174">This is equivalent to the SourceChanged event on the CoreWebView2.</span></span> <span data-ttu-id="25877-175">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-175">See CoreWebView2.SourceChanged documentation for more information.</span></span>

#### <span data-ttu-id="25877-176">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="25877-176">WebMessageReceived</span></span> 

<span data-ttu-id="25877-177">WebMessageReceived web 内容向应用主机发送一条消息至应用主机后的调度 `chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="25877-177">WebMessageReceived dispatches after web content sends a message to the app host via `chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="25877-178">公共事件 EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="25877-178">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="25877-179">这等效于 CoreWebView2 上的 WebMessageReceived 事件。</span><span class="sxs-lookup"><span data-stu-id="25877-179">This is equivalent to the WebMessageReceived event on the CoreWebView2.</span></span> <span data-ttu-id="25877-180">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-180">See CoreWebView2.WebMessageReceived documentation for more information.</span></span>

#### <span data-ttu-id="25877-181">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="25877-181">CoreWebView2</span></span> 

<span data-ttu-id="25877-182">基础 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="25877-182">The underlying CoreWebView2.</span></span>

> <span data-ttu-id="25877-183">公共 CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="25877-183">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="25877-184">使用此属性对 WebView2 内容执行比在 WebView2 上公开的更多操作。</span><span class="sxs-lookup"><span data-stu-id="25877-184">Use this property to perform more operations on the WebView2 content than is exposed on the WebView2.</span></span> <span data-ttu-id="25877-185">此值为 null，直到初始化。</span><span class="sxs-lookup"><span data-stu-id="25877-185">This value is null until it is initialized.</span></span> <span data-ttu-id="25877-186">你可以强制基础 CoreWebView2 通过 InitializeAsync 方法进行初始化。</span><span class="sxs-lookup"><span data-stu-id="25877-186">You can force the underlying CoreWebView2 to initialize via the InitializeAsync method.</span></span>

#### <span data-ttu-id="25877-187">来源</span><span class="sxs-lookup"><span data-stu-id="25877-187">Source</span></span> 

<span data-ttu-id="25877-188">Source 属性是 WebView2 的顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="25877-188">The Source property is the URI of the top level document of the WebView2.</span></span>

> <span data-ttu-id="25877-189">公共 Uri[源](#source)</span><span class="sxs-lookup"><span data-stu-id="25877-189">public Uri [Source](#source)</span></span>

<span data-ttu-id="25877-190">设置源等效于调用 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="25877-190">Setting the Source is equivalent to calling CoreWebView2.Navigate.</span></span> <span data-ttu-id="25877-191">如果基础 CoreWebView2 尚未初始化，则此属性为 "关于：空白"。</span><span class="sxs-lookup"><span data-stu-id="25877-191">If the underlying CoreWebView2 is not yet initialized, this property is "about:blank".</span></span> <span data-ttu-id="25877-192">如果属性设置为非绝对 URI 或 null，则属性保持不变。</span><span class="sxs-lookup"><span data-stu-id="25877-192">If the property is set to a non-absolute URI or null, the property remains unchanged.</span></span> <span data-ttu-id="25877-193">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-193">See CoreWebView2.Navigate documentation for more information.</span></span>

#### <span data-ttu-id="25877-194">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="25877-194">ZoomFactor</span></span> 

<span data-ttu-id="25877-195">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="25877-195">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="25877-196">公共双[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="25877-196">public double [ZoomFactor](#zoomfactor)</span></span>

#### <span data-ttu-id="25877-197">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="25877-197">CanGoBack</span></span> 

<span data-ttu-id="25877-198">如果 web 视图可以通过 GoBack 方法导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="25877-198">Returns true if the webview can navigate to a previous page in the navigation history via the GoBack method.</span></span>

> <span data-ttu-id="25877-199">公共 bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="25877-199">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="25877-200">这等效于 CoreWebView2 上的 CanGoBack 属性。</span><span class="sxs-lookup"><span data-stu-id="25877-200">This is equivalent to the CanGoBack property on the CoreWebView2.</span></span> <span data-ttu-id="25877-201">如果基础 CoreWebView2 尚未初始化，则此属性为 false。</span><span class="sxs-lookup"><span data-stu-id="25877-201">If the underlying CoreWebView2 is not yet initialized, this property is false.</span></span> <span data-ttu-id="25877-202">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-202">See CoreWebView2.CanGoBack documentation for more information.</span></span>

#### <span data-ttu-id="25877-203">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="25877-203">CanGoForward</span></span> 

<span data-ttu-id="25877-204">如果 web 视图可通过 GoForward 方法导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="25877-204">Returns true if the webview can navigate to a next page in the navigation history via the GoForward method.</span></span>

> <span data-ttu-id="25877-205">公共 bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="25877-205">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="25877-206">这等效于 CoreWebView2 上的 CanGoForward 属性。</span><span class="sxs-lookup"><span data-stu-id="25877-206">This is equivalent to the CanGoForward property on the CoreWebView2.</span></span> <span data-ttu-id="25877-207">如果基础 CoreWebView2 尚未初始化，则此属性为 false。</span><span class="sxs-lookup"><span data-stu-id="25877-207">If the underlying CoreWebView2 is not yet initialized, this property is false.</span></span> <span data-ttu-id="25877-208">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-208">See CoreWebView2.CanGoForward documentation for more information.</span></span>

#### <span data-ttu-id="25877-209">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="25877-209">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="25877-210">显式触发控件的[CoreWebView2](#corewebview2)的初始化。</span><span class="sxs-lookup"><span data-stu-id="25877-210">Explicitly trigger initialization of the control's [CoreWebView2](#corewebview2).</span></span>

> <span data-ttu-id="25877-211">公共任务[EnsureCoreWebView2Async](#ensurecorewebview2async)（CoreWebView2Environment 环境）</span><span class="sxs-lookup"><span data-stu-id="25877-211">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

##### <span data-ttu-id="25877-212">参数</span><span class="sxs-lookup"><span data-stu-id="25877-212">Parameters</span></span>
* `environment` <span data-ttu-id="25877-213">应用于创建 CoreWebView2 的预创建的 CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="25877-213">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="25877-214">创建自己的环境使你可以控制影响 CoreWebView2 初始化方式的多个选项。</span><span class="sxs-lookup"><span data-stu-id="25877-214">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="25877-215">如果传递 null （默认值），则将自动创建并使用默认环境。</span><span class="sxs-lookup"><span data-stu-id="25877-215">If you pass null (the default value) then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="25877-216">返回</span><span class="sxs-lookup"><span data-stu-id="25877-216">Returns</span></span>
<span data-ttu-id="25877-217">表示后台初始化进程的任务。</span><span class="sxs-lookup"><span data-stu-id="25877-217">A Task that represents the background initialization process.</span></span> <span data-ttu-id="25877-218">任务完成后，CoreWebView2 属性将可供使用（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="25877-218">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="25877-219">请注意，将在任务完成之前调用控件的[CoreWebView2Ready](#corewebview2ready)事件。</span><span class="sxs-lookup"><span data-stu-id="25877-219">Note that the control's [CoreWebView2Ready](#corewebview2ready) event will be invoked before the task completes.</span></span> 

<span data-ttu-id="25877-220">额外调用此方法将不起作用（忽略任何指定的环境），并返回与第一次调用相同的任务。</span><span class="sxs-lookup"><span data-stu-id="25877-220">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="25877-221">通过设置[Source](#source)属性隐式触发初始化后调用此方法将不起作用（忽略任何指定的环境），而只是返回表示已在进行的初始化的任务。</span><span class="sxs-lookup"><span data-stu-id="25877-221">Calling this method after initialization has been implicitly triggered by setting the [Source](#source) property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> 

##### <span data-ttu-id="25877-222">异常</span><span class="sxs-lookup"><span data-stu-id="25877-222">Exceptions</span></span>
* `System.InvalidOperationException` <span data-ttu-id="25877-223">从非 UI 线程调用时引发。</span><span class="sxs-lookup"><span data-stu-id="25877-223">Thrown when invoked from non-UI thread.</span></span>

#### <span data-ttu-id="25877-224">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="25877-224">ExecuteScriptAsync</span></span> 

<span data-ttu-id="25877-225">在 WebView2 的顶级文档中执行提供的脚本。</span><span class="sxs-lookup"><span data-stu-id="25877-225">Executes the provided script in the top level document of the WebView2.</span></span>

> <span data-ttu-id="25877-226">公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串脚本）</span><span class="sxs-lookup"><span data-stu-id="25877-226">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string script)</span></span>

<span data-ttu-id="25877-227">这等效于 CoreWebView2 上的 ExecuteScriptAsync 方法。</span><span class="sxs-lookup"><span data-stu-id="25877-227">This is equivalent to the ExecuteScriptAsync method on the CoreWebView2.</span></span> <span data-ttu-id="25877-228">如果基础 CoreWebView2 尚未初始化，此方法将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="25877-228">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="25877-229">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-229">See CoreWebView2.ExecuteScriptAsync documentation for more information.</span></span>

#### <span data-ttu-id="25877-230">GoBack</span><span class="sxs-lookup"><span data-stu-id="25877-230">GoBack</span></span> 

<span data-ttu-id="25877-231">导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="25877-231">Navigate to the previous page in navigation history.</span></span>

> <span data-ttu-id="25877-232">公共 void [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="25877-232">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="25877-233">这等效于 CoreWebView2 上的 GoBack 方法。</span><span class="sxs-lookup"><span data-stu-id="25877-233">This is equivalent to the GoBack method on the CoreWebView2.</span></span> <span data-ttu-id="25877-234">如果基础 CoreWebView2 尚未初始化，此方法将不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="25877-234">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="25877-235">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-235">See CoreWebView2.GoBack documentation for more information.</span></span>

#### <span data-ttu-id="25877-236">GoForward</span><span class="sxs-lookup"><span data-stu-id="25877-236">GoForward</span></span> 

<span data-ttu-id="25877-237">导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="25877-237">Navigate to the next page in navigation history.</span></span>

> <span data-ttu-id="25877-238">公共 void [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="25877-238">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="25877-239">这等效于 CoreWebView2 上的 GoForward 方法。</span><span class="sxs-lookup"><span data-stu-id="25877-239">This is equivalent to the GoForward method on the CoreWebView2.</span></span> <span data-ttu-id="25877-240">如果基础 CoreWebView2 尚未初始化，此方法将不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="25877-240">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="25877-241">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-241">See CoreWebView2.GoForward documentation for more information.</span></span>

#### <span data-ttu-id="25877-242">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="25877-242">NavigateToString</span></span> 

<span data-ttu-id="25877-243">将所提供的 HTML 呈现为 WebView2 的顶层文档。</span><span class="sxs-lookup"><span data-stu-id="25877-243">Render the provided HTML as the top level document of the WebView2.</span></span>

> <span data-ttu-id="25877-244">公共 void [NavigateToString](#navigatetostring)（string htmlContent）</span><span class="sxs-lookup"><span data-stu-id="25877-244">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="25877-245">这等效于 CoreWebView2 上的 NavigateToString 方法。</span><span class="sxs-lookup"><span data-stu-id="25877-245">This is equivalent to the NavigateToString method on the CoreWebView2.</span></span> <span data-ttu-id="25877-246">如果基础 CoreWebView2 尚未初始化，此方法将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="25877-246">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="25877-247">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-247">See CoreWebView2.NavigateToString documentation for more information.</span></span>

#### <span data-ttu-id="25877-248">重载</span><span class="sxs-lookup"><span data-stu-id="25877-248">Reload</span></span> 

<span data-ttu-id="25877-249">重新加载 WebView2 的顶层文档。</span><span class="sxs-lookup"><span data-stu-id="25877-249">Reload the top level document of the WebView2.</span></span>

> <span data-ttu-id="25877-250">public void [Reload](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="25877-250">public void [Reload](#reload)()</span></span>

<span data-ttu-id="25877-251">这等效于 CoreWebView2 上的 Reload 方法。</span><span class="sxs-lookup"><span data-stu-id="25877-251">This is equivalent to the Reload method on the CoreWebView2.</span></span> <span data-ttu-id="25877-252">如果基础 CoreWebView2 尚未初始化，此方法将引发 InvalidOperationException。</span><span class="sxs-lookup"><span data-stu-id="25877-252">If the underlying CoreWebView2 is not yet initialized, this method throws an InvalidOperationException.</span></span> <span data-ttu-id="25877-253">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-253">See CoreWebView2.Reload documentation for more information.</span></span>

#### <span data-ttu-id="25877-254">停止</span><span class="sxs-lookup"><span data-stu-id="25877-254">Stop</span></span> 

<span data-ttu-id="25877-255">停止 WebView2 中的任何正在进行的导航。</span><span class="sxs-lookup"><span data-stu-id="25877-255">Stop any in progress navigation in the WebView2.</span></span>

> <span data-ttu-id="25877-256">public void [Stop](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="25877-256">public void [Stop](#stop)()</span></span>

<span data-ttu-id="25877-257">这等效于 CoreWebView2 上的 Stop 方法。</span><span class="sxs-lookup"><span data-stu-id="25877-257">This is equivalent to the Stop method on the CoreWebView2.</span></span> <span data-ttu-id="25877-258">如果基础 CoreWebView2 尚未初始化，此方法将不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="25877-258">If the underlying CoreWebView2 is not yet initialized, this method does nothing.</span></span> <span data-ttu-id="25877-259">有关详细信息，请参阅 CoreWebView2 文档。</span><span class="sxs-lookup"><span data-stu-id="25877-259">See CoreWebView2.Stop documentation for more information.</span></span>

#### <span data-ttu-id="25877-260">WebView2</span><span class="sxs-lookup"><span data-stu-id="25877-260">WebView2</span></span> 

<span data-ttu-id="25877-261">创建新的 WebView2 WinForms 控件。</span><span class="sxs-lookup"><span data-stu-id="25877-261">Create a new WebView2 WinForms control.</span></span>

> <span data-ttu-id="25877-262">公共[WebView2](#webview2)（）</span><span class="sxs-lookup"><span data-stu-id="25877-262">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="25877-263">构造后，CoreWebView2 属性为 null。</span><span class="sxs-lookup"><span data-stu-id="25877-263">After construction the CoreWebView2 property is null.</span></span> <span data-ttu-id="25877-264">调用[EnsureCoreWebView2Async](#ensurecorewebview2async)以初始化基础 CoreWebView2。</span><span class="sxs-lookup"><span data-stu-id="25877-264">Call [EnsureCoreWebView2Async](#ensurecorewebview2async) to initialize the underlying CoreWebView2.</span></span>

