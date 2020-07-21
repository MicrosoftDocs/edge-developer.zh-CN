---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/17/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、WebView2、浏览器控件、边缘 html、。 WebView2
ms.openlocfilehash: e7f5d11b540d1d7ad9630aa674ef5bc0073195c2
ms.sourcegitcommit: e0cb9e6f59f222fade6afa4829c59524a9a9b9ff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/20/2020
ms.locfileid: "10885294"
---
# <span data-ttu-id="b1977-104">WebView2 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="b1977-104">Microsoft.Web.WebView2.Wpf.WebView2 class</span></span> 

<span data-ttu-id="b1977-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="b1977-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="b1977-106">程序集： Microsoft.Web.WebView2.Wpf.dll</span><span class="sxs-lookup"><span data-stu-id="b1977-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

<span data-ttu-id="b1977-107">用于在 WPF 应用程序中嵌入 web 内容的控件。</span><span class="sxs-lookup"><span data-stu-id="b1977-107">A control to embed web content in a WPF application.</span></span>

## <span data-ttu-id="b1977-108">摘要</span><span class="sxs-lookup"><span data-stu-id="b1977-108">Summary</span></span>

 <span data-ttu-id="b1977-109">成员</span><span class="sxs-lookup"><span data-stu-id="b1977-109">Members</span></span>                        | <span data-ttu-id="b1977-110">描述</span><span class="sxs-lookup"><span data-stu-id="b1977-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="b1977-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="b1977-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="b1977-112">CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-112">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>
[<span data-ttu-id="b1977-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="b1977-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="b1977-114">当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-114">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="b1977-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="b1977-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="b1977-116">CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-116">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>
[<span data-ttu-id="b1977-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="b1977-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="b1977-118">CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-118">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>
[<span data-ttu-id="b1977-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="b1977-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="b1977-120">CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-120">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>
[<span data-ttu-id="b1977-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="b1977-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="b1977-122">CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-122">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>
[<span data-ttu-id="b1977-123">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="b1977-123">ZoomFactorChanged</span></span>](#zoomfactorchanged) | <span data-ttu-id="b1977-124">当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-124">The event fires when the ZoomFactor property of the WebView changes.</span></span>
[<span data-ttu-id="b1977-125">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="b1977-125">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="b1977-126">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="b1977-126">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="b1977-127">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="b1977-127">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="b1977-128">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="b1977-128">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="b1977-129">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="b1977-129">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="b1977-130">访问基础 Core CoreWebView2 COM API 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="b1977-130">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>
[<span data-ttu-id="b1977-131">CreationProperties</span><span class="sxs-lookup"><span data-stu-id="b1977-131">CreationProperties</span></span>](#creationproperties) | <span data-ttu-id="b1977-132">获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。</span><span class="sxs-lookup"><span data-stu-id="b1977-132">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="b1977-133">来源</span><span class="sxs-lookup"><span data-stu-id="b1977-133">Source</span></span>](#source) | <span data-ttu-id="b1977-134">Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。</span><span class="sxs-lookup"><span data-stu-id="b1977-134">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>
[<span data-ttu-id="b1977-135">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="b1977-135">ZoomFactor</span></span>](#zoomfactor) | <span data-ttu-id="b1977-136">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="b1977-136">The zoom factor for the WebView.</span></span>
[<span data-ttu-id="b1977-137">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="b1977-137">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="b1977-138">显式触发控件的 CoreWebView2 的初始化。</span><span class="sxs-lookup"><span data-stu-id="b1977-138">Explicitly trigger initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="b1977-139">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="b1977-139">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="b1977-140">通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="b1977-140">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="b1977-141">GoBack</span><span class="sxs-lookup"><span data-stu-id="b1977-141">GoBack</span></span>](#goback) | <span data-ttu-id="b1977-142">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="b1977-142">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="b1977-143">GoForward</span><span class="sxs-lookup"><span data-stu-id="b1977-143">GoForward</span></span>](#goforward) | <span data-ttu-id="b1977-144">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="b1977-144">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="b1977-145">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="b1977-145">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="b1977-146">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="b1977-146">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="b1977-147">重载</span><span class="sxs-lookup"><span data-stu-id="b1977-147">Reload</span></span>](#reload) | <span data-ttu-id="b1977-148">重新加载当前页。</span><span class="sxs-lookup"><span data-stu-id="b1977-148">Reloads the current page.</span></span>
[<span data-ttu-id="b1977-149">停止</span><span class="sxs-lookup"><span data-stu-id="b1977-149">Stop</span></span>](#stop) | <span data-ttu-id="b1977-150">停止所有导航和挂起的资源读取。</span><span class="sxs-lookup"><span data-stu-id="b1977-150">Stops all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="b1977-151">WebView2</span><span class="sxs-lookup"><span data-stu-id="b1977-151">WebView2</span></span>](#webview2) | <span data-ttu-id="b1977-152">创建 WebView2 控件的新实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-152">Creates a new instance of a WebView2 control.</span></span>

<span data-ttu-id="b1977-153">此控件实际上是围绕 WebView2 COM API 的包装，你可以在此处找到文档： [https://aka.ms/webview2](https://aka.ms/webview2) 通过访问 CoreWebView2 属性，可以直接访问基础 ICoreWebView2 接口及其所有功能。</span><span class="sxs-lookup"><span data-stu-id="b1977-153">This control is effectively a wrapper around the WebView2 COM API, which you can find documentation for here: [https://aka.ms/webview2](https://aka.ms/webview2) You can directly access the underlying ICoreWebView2 interface and all of its functionality by accessing the CoreWebView2 property.</span></span> <span data-ttu-id="b1977-154">某些最常用的 COM 功能也可以通过控件上的包装方法/属性/事件直接访问。</span><span class="sxs-lookup"><span data-stu-id="b1977-154">Some of the most common COM functionality is also accessible directly through wrapper methods/properties/events on the control.</span></span>

<span data-ttu-id="b1977-155">在创建时，该控件的 CoreWebView2 属性将为 null。</span><span class="sxs-lookup"><span data-stu-id="b1977-155">Upon creation, the control's CoreWebView2 property will be null.</span></span> <span data-ttu-id="b1977-156">这是因为创建 CoreWebView2 是一个昂贵的操作，它涉及启动 Edge 浏览器进程之类的操作。</span><span class="sxs-lookup"><span data-stu-id="b1977-156">This is because creating the CoreWebView2 is an expensive operation which involves things like launching Edge browser processes.</span></span> <span data-ttu-id="b1977-157">有两种方法可导致创建 CoreWebView2：1）调用 EnsureCoreWebView2Async 方法。</span><span class="sxs-lookup"><span data-stu-id="b1977-157">There are two ways to cause the CoreWebView2 to be created: 1) Call the EnsureCoreWebView2Async method.</span></span> <span data-ttu-id="b1977-158">这称为显式初始化。</span><span class="sxs-lookup"><span data-stu-id="b1977-158">This is referred to as explicit initialization.</span></span> <span data-ttu-id="b1977-159">2）设置 Source 属性（例如，可以通过标记执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="b1977-159">2) Set the Source property (which could be done from markup, for example).</span></span> <span data-ttu-id="b1977-160">这称为隐式初始化。</span><span class="sxs-lookup"><span data-stu-id="b1977-160">This is referred to as implicit initialization.</span></span> <span data-ttu-id="b1977-161">这两个选项都将开始在后台初始化，并返回到呼叫方，而无需等待它完成。</span><span class="sxs-lookup"><span data-stu-id="b1977-161">Either option will start initialization in the background and return back to the caller without waiting for it to finish.</span></span> <span data-ttu-id="b1977-162">若要指定有关初始化过程的选项，请将你自己的 CoreWebView2Environment 传递给 EnsureCoreWebView2Async，或在初始化之前设置控件的 CreationProperties 属性。</span><span class="sxs-lookup"><span data-stu-id="b1977-162">To specify options regarding the initialization process, either pass your own CoreWebView2Environment to EnsureCoreWebView2Async or set the control's CreationProperties property prior to initialization.</span></span>

<span data-ttu-id="b1977-163">初始化完成后（无论其触发方式如何），将按如下顺序发生以下情况：1）将调用控件的 CoreWebView2Ready 事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-163">When initialization has finished (regardless of how it was triggered) then the following things will occur, in this order: 1) The control's CoreWebView2Ready event will be invoked.</span></span> <span data-ttu-id="b1977-164">如果你需要在其使用之前对 CoreWebView2 执行一次设置操作，则应在该事件的处理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="b1977-164">If you need to perform one time setup operations on the CoreWebView2 prior to its use then you should do so in a handler for that event.</span></span> <span data-ttu-id="b1977-165">2）如果 Uri 已设置为 Source 属性，则控件将开始在后台导航到该属性（即，这些步骤将在不等待导航结束的情况下继续）。</span><span class="sxs-lookup"><span data-stu-id="b1977-165">2) If a Uri has been set to the Source property then the control will start navigating to it in the background (i.e. these steps will continue without waiting for the navigation to finish).</span></span> <span data-ttu-id="b1977-166">3）从 EnsureCoreWebView2Async 返回的任务将完成。</span><span class="sxs-lookup"><span data-stu-id="b1977-166">3) The Task returned from EnsureCoreWebView2Async will complete.</span></span>

<span data-ttu-id="b1977-167">有关初始化过程中涉及的任何方法/属性/事件的更多详细信息，请参阅其特定文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-167">For more details about any of the methods/properties/events involved in the initialization process, see its specific documentation.</span></span>

<span data-ttu-id="b1977-168">由于该控件的 CoreWebView2 是一个非常重量级的对象（有可能负责多个正在运行的进程和 mb 的磁盘空间），因此该控件实现 IDisposable 以提供用于释放它的显式方法。</span><span class="sxs-lookup"><span data-stu-id="b1977-168">Because the control's CoreWebView2 is a very heavyweight object (potentially responsible for multiple running processes and megabytes of disk space) the control implements IDisposable to provide an explicit means to free it.</span></span> <span data-ttu-id="b1977-169">调用 Dispose 将释放 CoreWebView2 及其基础资源（除其他 WebViews 还在使用的其他资源之外），并将 CoreWebView2 重置为 null。</span><span class="sxs-lookup"><span data-stu-id="b1977-169">Calling Dispose will release the CoreWebView2 and its underlying resources (except any that are also being used by other WebViews), and reset CoreWebView2 to null.</span></span> <span data-ttu-id="b1977-170">在 Dispose 调用后，CoreWebView2 无法重新初始化，并且尝试使用需要它的功能将引发 ObjectDisposedException。</span><span class="sxs-lookup"><span data-stu-id="b1977-170">After Dispose has been called the CoreWebView2 cannot be re-initialized, and any attempt to use functionality which requires it will throw an ObjectDisposedException.</span></span>

<span data-ttu-id="b1977-171">请注意，此控件扩展了 HwndHost，以便嵌入实时位于 WPF 生态系统之外的窗口。</span><span class="sxs-lookup"><span data-stu-id="b1977-171">Note that this control extends HwndHost in order to embed windows which live outside of the WPF ecosystem.</span></span> <span data-ttu-id="b1977-172">这对控件的输入和输出行为以及它从 UIElement 和 FrameworkElement 中 "继承" 的功能有一定的影响。</span><span class="sxs-lookup"><span data-stu-id="b1977-172">This has some implications regarding the control's input and output behavior as well as the functionality it "inherits" from UIElement and FrameworkElement.</span></span> <span data-ttu-id="b1977-173">有关详细信息，请参阅 HwndHost 和 WPF/Win32 互操作文档：</span><span class="sxs-lookup"><span data-stu-id="b1977-173">See the HwndHost and WPF/Win32 interop documentation for more info:</span></span>

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## <span data-ttu-id="b1977-174">成员</span><span class="sxs-lookup"><span data-stu-id="b1977-174">Members</span></span>

#### <span data-ttu-id="b1977-175">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="b1977-175">ContentLoading</span></span> 

<span data-ttu-id="b1977-176">CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-176">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>

> <span data-ttu-id="b1977-177">公共事件 EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="b1977-177">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="b1977-178">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b1977-178">The only difference between this event and CoreWebView2.ContentLoading is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="b1977-179">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-179">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.ContentLoading will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="b1977-180">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="b1977-180">CoreWebView2Ready</span></span> 

<span data-ttu-id="b1977-181">当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-181">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="b1977-182">公共事件 EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="b1977-182">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="b1977-183">如果你需要在要影响其所有使用情况的 CoreWebView2 上执行一次设置操作（例如，添加事件处理程序、配置设置、安装文档创建脚本、添加主机对象），你应该处理此事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-183">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span> <span data-ttu-id="b1977-184">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-184">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="b1977-185">此事件不提供任何参数，并且发件人将成为 WebView2 控件，它的 CoreWebView2 属性将在首次有效（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="b1977-185">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="b1977-186">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="b1977-186">NavigationCompleted</span></span> 

<span data-ttu-id="b1977-187">CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-187">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>

> <span data-ttu-id="b1977-188">公共事件 EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="b1977-188">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="b1977-189">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b1977-189">The only difference between this event and CoreWebView2.NavigationCompleted is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="b1977-190">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-190">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationCompleted will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="b1977-191">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="b1977-191">NavigationStarting</span></span> 

<span data-ttu-id="b1977-192">CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-192">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>

> <span data-ttu-id="b1977-193">公共事件 EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="b1977-193">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="b1977-194">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b1977-194">The only difference between this event and CoreWebView2.NavigationStarting is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="b1977-195">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-195">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationStarting will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="b1977-196">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="b1977-196">SourceChanged</span></span> 

<span data-ttu-id="b1977-197">CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-197">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>

> <span data-ttu-id="b1977-198">公共事件 EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="b1977-198">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="b1977-199">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b1977-199">The only difference between this event and CoreWebView2.SourceChanged is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="b1977-200">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-200">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.SourceChanged will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="b1977-201">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="b1977-201">WebMessageReceived</span></span> 

<span data-ttu-id="b1977-202">CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-202">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>

> <span data-ttu-id="b1977-203">公共事件 EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="b1977-203">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="b1977-204">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="b1977-204">The only difference between this event and CoreWebView2.WebMessageReceived is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="b1977-205">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-205">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.WebMessageReceived will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="b1977-206">ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="b1977-206">ZoomFactorChanged</span></span> 

<span data-ttu-id="b1977-207">当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-207">The event fires when the ZoomFactor property of the WebView changes.</span></span>

> <span data-ttu-id="b1977-208">公共事件 EventHandler< EventArgs > [ZoomFactorChanged](#zoomfactorchanged)</span><span class="sxs-lookup"><span data-stu-id="b1977-208">public event EventHandler< EventArgs > [ZoomFactorChanged](#zoomfactorchanged)</span></span>

<span data-ttu-id="b1977-209">此事件直接公开 CoreWebView2Controller ZoomFactorChanged，请参阅其文档以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1977-209">This event directly exposes CoreWebView2Controller.ZoomFactorChanged, see its documentation for more info.</span></span>

#### <span data-ttu-id="b1977-210">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="b1977-210">CanGoBack</span></span> 

<span data-ttu-id="b1977-211">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="b1977-211">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="b1977-212">公共 bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="b1977-212">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="b1977-213">CoreWebView2 的 CanGoBack 属性的 CoreWebView2 包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-213">Wrapper around the CoreWebView2.CanGoBack property of CoreWebView2.</span></span> <span data-ttu-id="b1977-214">如果 CoreWebView2 尚未初始化，则返回 false。</span><span class="sxs-lookup"><span data-stu-id="b1977-214">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="b1977-215">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="b1977-215">CanGoForward</span></span> 

<span data-ttu-id="b1977-216">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="b1977-216">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="b1977-217">公共 bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="b1977-217">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="b1977-218">CoreWebView2 的 CanGoForward 属性的 CoreWebView2 包装器。</span><span class="sxs-lookup"><span data-stu-id="b1977-218">Wrapper around the CoreWebView2.CanGoForward property of CoreWebView2.</span></span> <span data-ttu-id="b1977-219">如果 CoreWebView2 尚未初始化，则返回 false。</span><span class="sxs-lookup"><span data-stu-id="b1977-219">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="b1977-220">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="b1977-220">CoreWebView2</span></span> 

<span data-ttu-id="b1977-221">访问基础 Core CoreWebView2 COM API 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="b1977-221">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>

> <span data-ttu-id="b1977-222">公共 CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="b1977-222">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="b1977-223">返回 null，直到初始化完成。</span><span class="sxs-lookup"><span data-stu-id="b1977-223">Returns null until initialization has completed.</span></span> <span data-ttu-id="b1977-224">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-224">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="b1977-225">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-225">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-226">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-226">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="b1977-227">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="b1977-227">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="b1977-228">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-228">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-229">CreationProperties</span><span class="sxs-lookup"><span data-stu-id="b1977-229">CreationProperties</span></span> 

<span data-ttu-id="b1977-230">获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。</span><span class="sxs-lookup"><span data-stu-id="b1977-230">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="b1977-231">公共 CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span><span class="sxs-lookup"><span data-stu-id="b1977-231">public CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span></span>

<span data-ttu-id="b1977-232">在已开始控件的 CoreWebView2 初始化后，设置此属性将不起作用（将保留旧值）。</span><span class="sxs-lookup"><span data-stu-id="b1977-232">Setting this property won't work after initialization of the control's CoreWebView2 has started (the old value will be retained).</span></span> <span data-ttu-id="b1977-233">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-233">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="b1977-234">来源</span><span class="sxs-lookup"><span data-stu-id="b1977-234">Source</span></span> 

<span data-ttu-id="b1977-235">Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。</span><span class="sxs-lookup"><span data-stu-id="b1977-235">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>

> <span data-ttu-id="b1977-236">公共 Uri[源](#source)</span><span class="sxs-lookup"><span data-stu-id="b1977-236">public Uri [Source](#source)</span></span>

<span data-ttu-id="b1977-237">一般说来，获取此属性等效于获取 CoreWebView2 的 CoreWebView2 属性，并将此属性设置为不同的值，这等效于在 CoreWebView2 上调用 CoreWebView2 方法。</span><span class="sxs-lookup"><span data-stu-id="b1977-237">Generally speaking, getting this property is equivalent to getting the CoreWebView2.Source property of CoreWebView2 and setting this property (to a different value) is equivalent to calling the CoreWebView2.Navigate method on CoreWebView2.</span></span> <span data-ttu-id="b1977-238">Null 值具有与 "关于：空白" 相同的含义（有关详细信息，请参阅说明）。</span><span class="sxs-lookup"><span data-stu-id="b1977-238">A value of null has the same meaning as "about:blank" (see remarks for more info).</span></span> <span data-ttu-id="b1977-239">在 CoreWebView2 初始化之前获取此属性将检索设置为其的最后一个 Uri，如果没有任何 Uri，则为 null （默认值）。</span><span class="sxs-lookup"><span data-stu-id="b1977-239">Getting this property before the CoreWebView2 has been initialized will retrieve the last Uri which was set to it, or null (the default) if none has been.</span></span> <span data-ttu-id="b1977-240">在 CoreWebView2 初始化之前设置此属性将导致在后台启动初始化（如果尚未进行），之后，WebView2 将导航到指定的 Uri。</span><span class="sxs-lookup"><span data-stu-id="b1977-240">Setting this property before the CoreWebView2 has been initialized will cause initialization to start in the background (if not already in progress), after which the WebView2 will navigate to the specified Uri.</span></span> <span data-ttu-id="b1977-241">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-241">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="b1977-242">如果此属性为 null，则 CoreWebView2 将显示 "关于：空白" （或者如果设置为 null，则 CoreWebView2 将导航到 "关于：空白"）。</span><span class="sxs-lookup"><span data-stu-id="b1977-242">If this property is null then the CoreWebView2 will be showing "about:blank" (or if set to null then the CoreWebView2 will be navigated to "about:blank").</span></span> <span data-ttu-id="b1977-243">也可以将此属性包含（或设置为） "关于：空白" 的显式值，这对 CoreWebView2 具有相同的效果。</span><span class="sxs-lookup"><span data-stu-id="b1977-243">It is also possible for this property to have (or be set to) the explicit value "about:blank", which has the same effect on the CoreWebView2.</span></span> <span data-ttu-id="b1977-244">换言之，如果 CoreWebView2 显示 "关于：空白"，则此属性的值可能为 null 或 "关于：空白"。</span><span class="sxs-lookup"><span data-stu-id="b1977-244">In other words, if the CoreWebView2 is showing "about:blank", then this property's value might be either null or "about:blank".</span></span> <span data-ttu-id="b1977-245">但是，null 和 "关于：空白" 是此属性的非重复值，并且不被视为相等。</span><span class="sxs-lookup"><span data-stu-id="b1977-245">However, null and "about:blank" are distinct values of this property and not treated as equal to each other.</span></span> <span data-ttu-id="b1977-246">这对于控件初始化非常重要，因为这意味着将值从 null （默认值）更改为 "关于：空白" 仍为更改，仍将触发隐式初始化。</span><span class="sxs-lookup"><span data-stu-id="b1977-246">This is important for control initialization because it means that changing the value from null (its default) to "about:blank" is still a change and will still trigger implicit initialization.</span></span> 

##### <span data-ttu-id="b1977-247">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-247">Exceptions</span></span>
* `ObjectDisposedException` <span data-ttu-id="b1977-248">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-248">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-249">ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="b1977-249">ZoomFactor</span></span> 

<span data-ttu-id="b1977-250">Web 视图的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="b1977-250">The zoom factor for the WebView.</span></span>

> <span data-ttu-id="b1977-251">公共双[ZoomFactor](#zoomfactor)</span><span class="sxs-lookup"><span data-stu-id="b1977-251">public double [ZoomFactor](#zoomfactor)</span></span>

<span data-ttu-id="b1977-252">此属性直接公开 CoreWebView2Controller ZoomFactor，请参阅其文档以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="b1977-252">This property directly exposes CoreWebView2Controller.ZoomFactor, see its documentation for more info.</span></span> <span data-ttu-id="b1977-253">如果在 CoreWebView2 初始化之前获取此属性，将检索为其设置的最后一个值，如果没有任何值，则为1.0 （默认值）。</span><span class="sxs-lookup"><span data-stu-id="b1977-253">Getting this property before the CoreWebView2 has been initialized will retrieve the last value which was set to it, or 1.0 (the default) if none has been.</span></span> <span data-ttu-id="b1977-254">初始化后，将在 CoreWebView2 初始化之前设置为此属性的最新值。</span><span class="sxs-lookup"><span data-stu-id="b1977-254">The most recent value set to this property before the CoreWebView2 has been initialized will be set on it after initialization.</span></span>

#### <span data-ttu-id="b1977-255">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="b1977-255">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="b1977-256">显式触发控件的 CoreWebView2 的初始化。</span><span class="sxs-lookup"><span data-stu-id="b1977-256">Explicitly trigger initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="b1977-257">公共任务[EnsureCoreWebView2Async](#ensurecorewebview2async)（CoreWebView2Environment 环境）</span><span class="sxs-lookup"><span data-stu-id="b1977-257">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

<span data-ttu-id="b1977-258">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-258">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="b1977-259">参数</span><span class="sxs-lookup"><span data-stu-id="b1977-259">Parameters</span></span>
* `environment` <span data-ttu-id="b1977-260">应用于创建 CoreWebView2 的预创建的 CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="b1977-260">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="b1977-261">创建自己的环境使你可以控制影响 CoreWebView2 初始化方式的多个选项。</span><span class="sxs-lookup"><span data-stu-id="b1977-261">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="b1977-262">如果你将环境传递到此方法，则它将覆盖 CreationProperties 属性上指定的任何设置。</span><span class="sxs-lookup"><span data-stu-id="b1977-262">If you pass an environment to this method then it will override any settings specified on the CreationProperties property.</span></span> <span data-ttu-id="b1977-263">如果传递 null （默认值），并且未将任何值设置为 CreationProperties，则将自动创建和使用默认环境。</span><span class="sxs-lookup"><span data-stu-id="b1977-263">If you pass null (the default value) and no value has been set to CreationProperties then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="b1977-264">返回</span><span class="sxs-lookup"><span data-stu-id="b1977-264">Returns</span></span>
<span data-ttu-id="b1977-265">表示后台初始化进程的任务。</span><span class="sxs-lookup"><span data-stu-id="b1977-265">A Task that represents the background initialization process.</span></span> <span data-ttu-id="b1977-266">任务完成后，CoreWebView2 属性将可供使用（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="b1977-266">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="b1977-267">请注意，将在任务完成之前调用控件的 CoreWebView2Ready 事件。</span><span class="sxs-lookup"><span data-stu-id="b1977-267">Note that the control's CoreWebView2Ready event will be invoked before the task completes.</span></span> 

<span data-ttu-id="b1977-268">额外调用此方法将不起作用（忽略任何指定的环境），并返回与第一次调用相同的任务。</span><span class="sxs-lookup"><span data-stu-id="b1977-268">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="b1977-269">通过设置 Source 属性隐式触发初始化后调用此方法将不起作用（忽略任何指定的环境），而只是返回表示已在进行的初始化的任务。</span><span class="sxs-lookup"><span data-stu-id="b1977-269">Calling this method after initialization has been implicitly triggered by setting the Source property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> <span data-ttu-id="b1977-270">请注意，即使此方法是异步的并返回任务，它仍必须在 UI 线程上调用，如大多数 UI 控件的大多数公共功能。</span><span class="sxs-lookup"><span data-stu-id="b1977-270">Note that even though this method is asynchronous and returns a Task, it still must be called on the UI thread like most public functionality of most UI controls.</span></span> 

##### <span data-ttu-id="b1977-271">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-271">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-272">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-272">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="b1977-273">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="b1977-273">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="b1977-274">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-274">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-275">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="b1977-275">ExecuteScriptAsync</span></span> 

<span data-ttu-id="b1977-276">通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="b1977-276">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="b1977-277">公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串 javaScript）</span><span class="sxs-lookup"><span data-stu-id="b1977-277">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="b1977-278">等效于在 CoreWebView2 上调用 CoreWebView2.ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="b1977-278">Equivalent to calling CoreWebView2.ExecuteScriptAsync on CoreWebView2</span></span>

##### <span data-ttu-id="b1977-279">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-279">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-280">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="b1977-280">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

* `InvalidOperationException` <span data-ttu-id="b1977-281">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-281">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="b1977-282">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="b1977-282">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="b1977-283">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-283">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-284">GoBack</span><span class="sxs-lookup"><span data-stu-id="b1977-284">GoBack</span></span> 

<span data-ttu-id="b1977-285">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="b1977-285">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="b1977-286">公共 void [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="b1977-286">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="b1977-287">如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoBack，否则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b1977-287">Equivalent to calling CoreWebView2.GoBack on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="b1977-288">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-288">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-289">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-289">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="b1977-290">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="b1977-290">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="b1977-291">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-291">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-292">GoForward</span><span class="sxs-lookup"><span data-stu-id="b1977-292">GoForward</span></span> 

<span data-ttu-id="b1977-293">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="b1977-293">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="b1977-294">公共 void [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="b1977-294">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="b1977-295">如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoForward，否则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="b1977-295">Equivalent to calling CoreWebView2.GoForward on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="b1977-296">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-296">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-297">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-297">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="b1977-298">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="b1977-298">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="b1977-299">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-299">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-300">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="b1977-300">NavigateToString</span></span> 

<span data-ttu-id="b1977-301">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="b1977-301">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="b1977-302">公共 void [NavigateToString](#navigatetostring)（string htmlContent）</span><span class="sxs-lookup"><span data-stu-id="b1977-302">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="b1977-303">等同于在 CoreWebView2 上调用 CoreWebView2 NavigateToString</span><span class="sxs-lookup"><span data-stu-id="b1977-303">Equivalent to calling CoreWebView2.NavigateToString on CoreWebView2</span></span>

##### <span data-ttu-id="b1977-304">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-304">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-305">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="b1977-305">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="b1977-306"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="b1977-306">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="b1977-307">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-307">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-308">重载</span><span class="sxs-lookup"><span data-stu-id="b1977-308">Reload</span></span> 

<span data-ttu-id="b1977-309">重新加载当前页。</span><span class="sxs-lookup"><span data-stu-id="b1977-309">Reloads the current page.</span></span>

> <span data-ttu-id="b1977-310">public void [Reload](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="b1977-310">public void [Reload](#reload)()</span></span>

<span data-ttu-id="b1977-311">等效于在 CoreWebView2 上调用 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="b1977-311">Equivalent to calling CoreWebView2.Reload on CoreWebView2</span></span>

##### <span data-ttu-id="b1977-312">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-312">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-313">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="b1977-313">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="b1977-314"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="b1977-314">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="b1977-315">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-315">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-316">停止</span><span class="sxs-lookup"><span data-stu-id="b1977-316">Stop</span></span> 

<span data-ttu-id="b1977-317">停止所有导航和挂起的资源读取。</span><span class="sxs-lookup"><span data-stu-id="b1977-317">Stops all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="b1977-318">public void [Stop](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="b1977-318">public void [Stop](#stop)()</span></span>

<span data-ttu-id="b1977-319">等同于调用 CoreWebView2。在 CoreWebView2 上停止</span><span class="sxs-lookup"><span data-stu-id="b1977-319">Equivalent to calling CoreWebView2.Stop on CoreWebView2</span></span>

##### <span data-ttu-id="b1977-320">异常</span><span class="sxs-lookup"><span data-stu-id="b1977-320">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="b1977-321">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="b1977-321">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="b1977-322"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="b1977-322">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="b1977-323">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="b1977-323">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="b1977-324">WebView2</span><span class="sxs-lookup"><span data-stu-id="b1977-324">WebView2</span></span> 

<span data-ttu-id="b1977-325">创建 WebView2 控件的新实例。</span><span class="sxs-lookup"><span data-stu-id="b1977-325">Creates a new instance of a WebView2 control.</span></span>

> <span data-ttu-id="b1977-326">公共[WebView2](#webview2)（）</span><span class="sxs-lookup"><span data-stu-id="b1977-326">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="b1977-327">请注意，在初始化之前，控件的 CoreWebView2 将为 null。</span><span class="sxs-lookup"><span data-stu-id="b1977-327">Note that the control's CoreWebView2 will be null until initialized.</span></span> <span data-ttu-id="b1977-328">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="b1977-328">See the WebView2 class documentation for an initialization overview.</span></span>

