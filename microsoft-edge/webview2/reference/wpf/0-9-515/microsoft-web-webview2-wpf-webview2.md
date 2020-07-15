---
description: 通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术（HTML、CSS 和 JavaScript）
title: WebView2 中的 WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: WebView2、Core、WebView2、web 视图、新、wpf、winforms、app、edge、CoreWebView2、CoreWebView2Controller、浏览器控件、边缘 html、WebView2、浏览器控件、边缘 html、。 WebView2
ms.openlocfilehash: 2dd7bf1035cf5254f4668070d56d2bd2405f1276
ms.sourcegitcommit: f6764f57aed9ab7229e4eb6cc8851d0cea667403
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2020
ms.locfileid: "10880260"
---
# <span data-ttu-id="09e50-104">WebView2 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="09e50-104">Microsoft.Web.WebView2.Wpf.WebView2 class</span></span> 

<span data-ttu-id="09e50-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="09e50-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="09e50-106">程序集： Microsoft.Web.WebView2.Wpf.dll</span><span class="sxs-lookup"><span data-stu-id="09e50-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

<span data-ttu-id="09e50-107">用于在 WPF 应用程序中嵌入 web 内容的控件。</span><span class="sxs-lookup"><span data-stu-id="09e50-107">A control to embed web content in a WPF application.</span></span>

## <span data-ttu-id="09e50-108">摘要</span><span class="sxs-lookup"><span data-stu-id="09e50-108">Summary</span></span>

 <span data-ttu-id="09e50-109">成员</span><span class="sxs-lookup"><span data-stu-id="09e50-109">Members</span></span>                        | <span data-ttu-id="09e50-110">描述</span><span class="sxs-lookup"><span data-stu-id="09e50-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="09e50-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="09e50-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="09e50-112">CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-112">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>
[<span data-ttu-id="09e50-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="09e50-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="09e50-114">当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="09e50-114">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="09e50-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="09e50-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="09e50-116">CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-116">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>
[<span data-ttu-id="09e50-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="09e50-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="09e50-118">CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-118">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>
[<span data-ttu-id="09e50-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="09e50-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="09e50-120">CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-120">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>
[<span data-ttu-id="09e50-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="09e50-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="09e50-122">CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-122">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>
[<span data-ttu-id="09e50-123">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="09e50-123">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="09e50-124">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="09e50-124">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="09e50-125">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="09e50-125">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="09e50-126">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="09e50-126">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="09e50-127">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="09e50-127">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="09e50-128">访问基础 Core CoreWebView2 COM API 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="09e50-128">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>
[<span data-ttu-id="09e50-129">CreationProperties</span><span class="sxs-lookup"><span data-stu-id="09e50-129">CreationProperties</span></span>](#creationproperties) | <span data-ttu-id="09e50-130">获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。</span><span class="sxs-lookup"><span data-stu-id="09e50-130">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="09e50-131">来源</span><span class="sxs-lookup"><span data-stu-id="09e50-131">Source</span></span>](#source) | <span data-ttu-id="09e50-132">Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。</span><span class="sxs-lookup"><span data-stu-id="09e50-132">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>
[<span data-ttu-id="09e50-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="09e50-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="09e50-134">显式触发控件的 CoreWebView2 的初始化。</span><span class="sxs-lookup"><span data-stu-id="09e50-134">Explicitly trigger initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="09e50-135">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="09e50-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="09e50-136">通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="09e50-136">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="09e50-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="09e50-137">GoBack</span></span>](#goback) | <span data-ttu-id="09e50-138">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="09e50-138">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="09e50-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="09e50-139">GoForward</span></span>](#goforward) | <span data-ttu-id="09e50-140">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="09e50-140">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="09e50-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="09e50-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="09e50-142">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="09e50-142">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="09e50-143">重载</span><span class="sxs-lookup"><span data-stu-id="09e50-143">Reload</span></span>](#reload) | <span data-ttu-id="09e50-144">重新加载当前页。</span><span class="sxs-lookup"><span data-stu-id="09e50-144">Reloads the current page.</span></span>
[<span data-ttu-id="09e50-145">停止</span><span class="sxs-lookup"><span data-stu-id="09e50-145">Stop</span></span>](#stop) | <span data-ttu-id="09e50-146">停止所有导航和挂起的资源读取。</span><span class="sxs-lookup"><span data-stu-id="09e50-146">Stops all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="09e50-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="09e50-147">WebView2</span></span>](#webview2) | <span data-ttu-id="09e50-148">创建 WebView2 控件的新实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-148">Creates a new instance of a WebView2 control.</span></span>

<span data-ttu-id="09e50-149">此控件实际上是围绕 WebView2 COM API 的包装，你可以在此处找到文档： [https://aka.ms/webview2](https://aka.ms/webview2) 通过访问 CoreWebView2 属性，可以直接访问基础 ICoreWebView2 接口及其所有功能。</span><span class="sxs-lookup"><span data-stu-id="09e50-149">This control is effectively a wrapper around the WebView2 COM API, which you can find documentation for here: [https://aka.ms/webview2](https://aka.ms/webview2) You can directly access the underlying ICoreWebView2 interface and all of its functionality by accessing the CoreWebView2 property.</span></span> <span data-ttu-id="09e50-150">某些最常用的 COM 功能也可以通过控件上的包装方法/属性/事件直接访问。</span><span class="sxs-lookup"><span data-stu-id="09e50-150">Some of the most common COM functionality is also accessible directly through wrapper methods/properties/events on the control.</span></span>

<span data-ttu-id="09e50-151">在创建时，该控件的 CoreWebView2 属性将为 null。</span><span class="sxs-lookup"><span data-stu-id="09e50-151">Upon creation, the control's CoreWebView2 property will be null.</span></span> <span data-ttu-id="09e50-152">这是因为创建 CoreWebView2 是一个昂贵的操作，它涉及启动 Edge 浏览器进程之类的操作。</span><span class="sxs-lookup"><span data-stu-id="09e50-152">This is because creating the CoreWebView2 is an expensive operation which involves things like launching Edge browser processes.</span></span> <span data-ttu-id="09e50-153">有两种方法可导致创建 CoreWebView2：1）调用 EnsureCoreWebView2Async 方法。</span><span class="sxs-lookup"><span data-stu-id="09e50-153">There are two ways to cause the CoreWebView2 to be created: 1) Call the EnsureCoreWebView2Async method.</span></span> <span data-ttu-id="09e50-154">这称为显式初始化。</span><span class="sxs-lookup"><span data-stu-id="09e50-154">This is referred to as explicit initialization.</span></span> <span data-ttu-id="09e50-155">2）设置 Source 属性（例如，可以通过标记执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="09e50-155">2) Set the Source property (which could be done from markup, for example).</span></span> <span data-ttu-id="09e50-156">这称为隐式初始化。</span><span class="sxs-lookup"><span data-stu-id="09e50-156">This is referred to as implicit initialization.</span></span> <span data-ttu-id="09e50-157">这两个选项都将开始在后台初始化，并返回到呼叫方，而无需等待它完成。</span><span class="sxs-lookup"><span data-stu-id="09e50-157">Either option will start initialization in the background and return back to the caller without waiting for it to finish.</span></span> <span data-ttu-id="09e50-158">若要指定有关初始化过程的选项，请将你自己的 CoreWebView2Environment 传递给 EnsureCoreWebView2Async，或在初始化之前设置控件的 CreationProperties 属性。</span><span class="sxs-lookup"><span data-stu-id="09e50-158">To specify options regarding the initialization process, either pass your own CoreWebView2Environment to EnsureCoreWebView2Async or set the control's CreationProperties property prior to initialization.</span></span>

<span data-ttu-id="09e50-159">初始化完成后（无论其触发方式如何），将按如下顺序发生以下情况：1）将调用控件的 CoreWebView2Ready 事件。</span><span class="sxs-lookup"><span data-stu-id="09e50-159">When initialization has finished (regardless of how it was triggered) then the following things will occur, in this order: 1) The control's CoreWebView2Ready event will be invoked.</span></span> <span data-ttu-id="09e50-160">如果你需要在其使用之前对 CoreWebView2 执行一次设置操作，则应在该事件的处理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="09e50-160">If you need to perform one time setup operations on the CoreWebView2 prior to its use then you should do so in a handler for that event.</span></span> <span data-ttu-id="09e50-161">2）如果 Uri 已设置为 Source 属性，则控件将开始在后台导航到该属性（即，这些步骤将在不等待导航结束的情况下继续）。</span><span class="sxs-lookup"><span data-stu-id="09e50-161">2) If a Uri has been set to the Source property then the control will start navigating to it in the background (i.e. these steps will continue without waiting for the navigation to finish).</span></span> <span data-ttu-id="09e50-162">3）从 EnsureCoreWebView2Async 返回的任务将完成。</span><span class="sxs-lookup"><span data-stu-id="09e50-162">3) The Task returned from EnsureCoreWebView2Async will complete.</span></span>

<span data-ttu-id="09e50-163">有关初始化过程中涉及的任何方法/属性/事件的更多详细信息，请参阅其特定文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-163">For more details about any of the methods/properties/events involved in the initialization process, see its specific documentation.</span></span>

<span data-ttu-id="09e50-164">由于该控件的 CoreWebView2 是一个非常重量级的对象（有可能负责多个正在运行的进程和 mb 的磁盘空间），因此该控件实现 IDisposable 以提供用于释放它的显式方法。</span><span class="sxs-lookup"><span data-stu-id="09e50-164">Because the control's CoreWebView2 is a very heavyweight object (potentially responsible for multiple running processes and megabytes of disk space) the control implements IDisposable to provide an explicit means to free it.</span></span> <span data-ttu-id="09e50-165">调用 Dispose 将释放 CoreWebView2 及其基础资源（除其他 WebViews 还在使用的其他资源之外），并将 CoreWebView2 重置为 null。</span><span class="sxs-lookup"><span data-stu-id="09e50-165">Calling Dispose will release the CoreWebView2 and its underlying resources (except any that are also being used by other WebViews), and reset CoreWebView2 to null.</span></span> <span data-ttu-id="09e50-166">在 Dispose 调用后，CoreWebView2 无法重新初始化，并且尝试使用需要它的功能将引发 ObjectDisposedException。</span><span class="sxs-lookup"><span data-stu-id="09e50-166">After Dispose has been called the CoreWebView2 cannot be re-initialized, and any attempt to use functionality which requires it will throw an ObjectDisposedException.</span></span>

<span data-ttu-id="09e50-167">请注意，此控件扩展了 HwndHost，以便嵌入实时位于 WPF 生态系统之外的窗口。</span><span class="sxs-lookup"><span data-stu-id="09e50-167">Note that this control extends HwndHost in order to embed windows which live outside of the WPF ecosystem.</span></span> <span data-ttu-id="09e50-168">这对控件的输入和输出行为以及它从 UIElement 和 FrameworkElement 中 "继承" 的功能有一定的影响。</span><span class="sxs-lookup"><span data-stu-id="09e50-168">This has some implications regarding the control's input and output behavior as well as the functionality it "inherits" from UIElement and FrameworkElement.</span></span> <span data-ttu-id="09e50-169">有关详细信息，请参阅 HwndHost 和 WPF/Win32 互操作文档：</span><span class="sxs-lookup"><span data-stu-id="09e50-169">See the HwndHost and WPF/Win32 interop documentation for more info:</span></span>

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## <span data-ttu-id="09e50-170">成员</span><span class="sxs-lookup"><span data-stu-id="09e50-170">Members</span></span>

#### <span data-ttu-id="09e50-171">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="09e50-171">ContentLoading</span></span> 

<span data-ttu-id="09e50-172">CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-172">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>

> <span data-ttu-id="09e50-173">公共事件 EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="09e50-173">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="09e50-174">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="09e50-174">The only difference between this event and CoreWebView2.ContentLoading is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="09e50-175">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-175">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.ContentLoading will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="09e50-176">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="09e50-176">CoreWebView2Ready</span></span> 

<span data-ttu-id="09e50-177">当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="09e50-177">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="09e50-178">公共事件 EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="09e50-178">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="09e50-179">如果你需要在要影响其所有使用情况的 CoreWebView2 上执行一次设置操作（例如，添加事件处理程序、配置设置、安装文档创建脚本、添加主机对象），你应该处理此事件。</span><span class="sxs-lookup"><span data-stu-id="09e50-179">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span> <span data-ttu-id="09e50-180">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-180">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="09e50-181">此事件不提供任何参数，并且发件人将成为 WebView2 控件，它的 CoreWebView2 属性将在首次有效（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="09e50-181">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="09e50-182">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="09e50-182">NavigationCompleted</span></span> 

<span data-ttu-id="09e50-183">CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-183">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>

> <span data-ttu-id="09e50-184">公共事件 EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="09e50-184">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="09e50-185">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="09e50-185">The only difference between this event and CoreWebView2.NavigationCompleted is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="09e50-186">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-186">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationCompleted will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="09e50-187">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="09e50-187">NavigationStarting</span></span> 

<span data-ttu-id="09e50-188">CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-188">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>

> <span data-ttu-id="09e50-189">公共事件 EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="09e50-189">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="09e50-190">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="09e50-190">The only difference between this event and CoreWebView2.NavigationStarting is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="09e50-191">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-191">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationStarting will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="09e50-192">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="09e50-192">SourceChanged</span></span> 

<span data-ttu-id="09e50-193">CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-193">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>

> <span data-ttu-id="09e50-194">公共事件 EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="09e50-194">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="09e50-195">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="09e50-195">The only difference between this event and CoreWebView2.SourceChanged is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="09e50-196">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-196">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.SourceChanged will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="09e50-197">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="09e50-197">WebMessageReceived</span></span> 

<span data-ttu-id="09e50-198">CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-198">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>

> <span data-ttu-id="09e50-199">公共事件 EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="09e50-199">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="09e50-200">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="09e50-200">The only difference between this event and CoreWebView2.WebMessageReceived is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="09e50-201">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-201">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.WebMessageReceived will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="09e50-202">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="09e50-202">CanGoBack</span></span> 

<span data-ttu-id="09e50-203">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="09e50-203">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="09e50-204">公共 bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="09e50-204">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="09e50-205">CoreWebView2 的 CanGoBack 属性的 CoreWebView2 包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-205">Wrapper around the CoreWebView2.CanGoBack property of CoreWebView2.</span></span> <span data-ttu-id="09e50-206">如果 CoreWebView2 尚未初始化，则返回 false。</span><span class="sxs-lookup"><span data-stu-id="09e50-206">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="09e50-207">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="09e50-207">CanGoForward</span></span> 

<span data-ttu-id="09e50-208">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="09e50-208">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="09e50-209">公共 bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="09e50-209">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="09e50-210">CoreWebView2 的 CanGoForward 属性的 CoreWebView2 包装器。</span><span class="sxs-lookup"><span data-stu-id="09e50-210">Wrapper around the CoreWebView2.CanGoForward property of CoreWebView2.</span></span> <span data-ttu-id="09e50-211">如果 CoreWebView2 尚未初始化，则返回 false。</span><span class="sxs-lookup"><span data-stu-id="09e50-211">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="09e50-212">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="09e50-212">CoreWebView2</span></span> 

<span data-ttu-id="09e50-213">访问基础 Core CoreWebView2 COM API 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="09e50-213">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>

> <span data-ttu-id="09e50-214">公共 CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="09e50-214">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="09e50-215">返回 null，直到初始化完成。</span><span class="sxs-lookup"><span data-stu-id="09e50-215">Returns null until initialization has completed.</span></span> <span data-ttu-id="09e50-216">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-216">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="09e50-217">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-217">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-218">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-218">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="09e50-219">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="09e50-219">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="09e50-220">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-220">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-221">CreationProperties</span><span class="sxs-lookup"><span data-stu-id="09e50-221">CreationProperties</span></span> 

<span data-ttu-id="09e50-222">获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。</span><span class="sxs-lookup"><span data-stu-id="09e50-222">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="09e50-223">公共 CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span><span class="sxs-lookup"><span data-stu-id="09e50-223">public CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span></span>

<span data-ttu-id="09e50-224">在已开始控件的 CoreWebView2 初始化后，设置此属性将不起作用（将保留旧值）。</span><span class="sxs-lookup"><span data-stu-id="09e50-224">Setting this property won't work after initialization of the control's CoreWebView2 has started (the old value will be retained).</span></span> <span data-ttu-id="09e50-225">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-225">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="09e50-226">来源</span><span class="sxs-lookup"><span data-stu-id="09e50-226">Source</span></span> 

<span data-ttu-id="09e50-227">Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。</span><span class="sxs-lookup"><span data-stu-id="09e50-227">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>

> <span data-ttu-id="09e50-228">公共 Uri[源](#source)</span><span class="sxs-lookup"><span data-stu-id="09e50-228">public Uri [Source](#source)</span></span>

<span data-ttu-id="09e50-229">一般说来，获取此属性等效于获取 CoreWebView2 的 CoreWebView2 属性，并且设置此属性等效于在 CoreWebView2 上调用 CoreWebView2 方法。</span><span class="sxs-lookup"><span data-stu-id="09e50-229">Generally speaking, getting this property is equivalent to getting the CoreWebView2.Source property of CoreWebView2 and setting this property is equivalent to calling the CoreWebView2.Navigate method on CoreWebView2.</span></span> <span data-ttu-id="09e50-230">在 CoreWebView2 初始化之前获取此属性将检索已设置为其的最后一个 Uri。</span><span class="sxs-lookup"><span data-stu-id="09e50-230">Getting this property before the CoreWebView2 has been initialized will retrieve the last Uri which was set to it.</span></span> <span data-ttu-id="09e50-231">在 CoreWebView2 初始化之前设置此属性将导致在后台启动初始化（如果尚未进行），之后，WebView2 将导航到指定的 Uri。</span><span class="sxs-lookup"><span data-stu-id="09e50-231">Setting this property before the CoreWebView2 has been initialized will cause initialization to start in the background (if not already in progress), after which the WebView2 will navigate to the specified Uri.</span></span> <span data-ttu-id="09e50-232">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-232">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="09e50-233">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-233">Exceptions</span></span>
* `ObjectDisposedException` <span data-ttu-id="09e50-234">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-234">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-235">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="09e50-235">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="09e50-236">显式触发控件的 CoreWebView2 的初始化。</span><span class="sxs-lookup"><span data-stu-id="09e50-236">Explicitly trigger initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="09e50-237">公共任务[EnsureCoreWebView2Async](#ensurecorewebview2async)（CoreWebView2Environment 环境）</span><span class="sxs-lookup"><span data-stu-id="09e50-237">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

<span data-ttu-id="09e50-238">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-238">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="09e50-239">参数</span><span class="sxs-lookup"><span data-stu-id="09e50-239">Parameters</span></span>
* `environment` <span data-ttu-id="09e50-240">应用于创建 CoreWebView2 的预创建的 CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="09e50-240">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="09e50-241">创建自己的环境使你可以控制影响 CoreWebView2 初始化方式的多个选项。</span><span class="sxs-lookup"><span data-stu-id="09e50-241">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="09e50-242">如果你将环境传递到此方法，则它将覆盖 CreationProperties 属性上指定的任何设置。</span><span class="sxs-lookup"><span data-stu-id="09e50-242">If you pass an environment to this method then it will override any settings specified on the CreationProperties property.</span></span> <span data-ttu-id="09e50-243">如果传递 null （默认值），并且未将任何值设置为 CreationProperties，则将自动创建和使用默认环境。</span><span class="sxs-lookup"><span data-stu-id="09e50-243">If you pass null (the default value) and no value has been set to CreationProperties then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="09e50-244">返回</span><span class="sxs-lookup"><span data-stu-id="09e50-244">Returns</span></span>
<span data-ttu-id="09e50-245">表示后台初始化进程的任务。</span><span class="sxs-lookup"><span data-stu-id="09e50-245">A Task that represents the background initialization process.</span></span> <span data-ttu-id="09e50-246">任务完成后，CoreWebView2 属性将可供使用（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="09e50-246">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="09e50-247">请注意，将在任务完成之前调用控件的 CoreWebView2Ready 事件。</span><span class="sxs-lookup"><span data-stu-id="09e50-247">Note that the control's CoreWebView2Ready event will be invoked before the task completes.</span></span> 

<span data-ttu-id="09e50-248">额外调用此方法将不起作用（忽略任何指定的环境），并返回与第一次调用相同的任务。</span><span class="sxs-lookup"><span data-stu-id="09e50-248">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="09e50-249">通过设置 Source 属性隐式触发初始化后调用此方法将不起作用（忽略任何指定的环境），而只是返回表示已在进行的初始化的任务。</span><span class="sxs-lookup"><span data-stu-id="09e50-249">Calling this method after initialization has been implicitly triggered by setting the Source property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> <span data-ttu-id="09e50-250">请注意，即使此方法是异步的并返回任务，它仍必须在 UI 线程上调用，如大多数 UI 控件的大多数公共功能。</span><span class="sxs-lookup"><span data-stu-id="09e50-250">Note that even though this method is asynchronous and returns a Task, it still must be called on the UI thread like most public functionality of most UI controls.</span></span> 

##### <span data-ttu-id="09e50-251">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-251">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-252">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-252">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="09e50-253">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="09e50-253">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="09e50-254">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-254">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-255">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="09e50-255">ExecuteScriptAsync</span></span> 

<span data-ttu-id="09e50-256">通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="09e50-256">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="09e50-257">公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串 javaScript）</span><span class="sxs-lookup"><span data-stu-id="09e50-257">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="09e50-258">等效于在 CoreWebView2 上调用 CoreWebView2.ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="09e50-258">Equivalent to calling CoreWebView2.ExecuteScriptAsync on CoreWebView2</span></span>

##### <span data-ttu-id="09e50-259">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-259">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-260">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="09e50-260">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

* `InvalidOperationException` <span data-ttu-id="09e50-261">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-261">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="09e50-262">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="09e50-262">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="09e50-263">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-263">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-264">GoBack</span><span class="sxs-lookup"><span data-stu-id="09e50-264">GoBack</span></span> 

<span data-ttu-id="09e50-265">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="09e50-265">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="09e50-266">公共 void [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="09e50-266">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="09e50-267">如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoBack，否则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="09e50-267">Equivalent to calling CoreWebView2.GoBack on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="09e50-268">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-268">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-269">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-269">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="09e50-270">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="09e50-270">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="09e50-271">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-271">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-272">GoForward</span><span class="sxs-lookup"><span data-stu-id="09e50-272">GoForward</span></span> 

<span data-ttu-id="09e50-273">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="09e50-273">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="09e50-274">公共 void [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="09e50-274">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="09e50-275">如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoForward，否则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="09e50-275">Equivalent to calling CoreWebView2.GoForward on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="09e50-276">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-276">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-277">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-277">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="09e50-278">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="09e50-278">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="09e50-279">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-279">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-280">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="09e50-280">NavigateToString</span></span> 

<span data-ttu-id="09e50-281">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="09e50-281">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="09e50-282">公共 void [NavigateToString](#navigatetostring)（string htmlContent）</span><span class="sxs-lookup"><span data-stu-id="09e50-282">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="09e50-283">等同于在 CoreWebView2 上调用 CoreWebView2 NavigateToString</span><span class="sxs-lookup"><span data-stu-id="09e50-283">Equivalent to calling CoreWebView2.NavigateToString on CoreWebView2</span></span>

##### <span data-ttu-id="09e50-284">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-284">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-285">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="09e50-285">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="09e50-286"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="09e50-286">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="09e50-287">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-287">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-288">重载</span><span class="sxs-lookup"><span data-stu-id="09e50-288">Reload</span></span> 

<span data-ttu-id="09e50-289">重新加载当前页。</span><span class="sxs-lookup"><span data-stu-id="09e50-289">Reloads the current page.</span></span>

> <span data-ttu-id="09e50-290">public void [Reload](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="09e50-290">public void [Reload](#reload)()</span></span>

<span data-ttu-id="09e50-291">等效于在 CoreWebView2 上调用 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="09e50-291">Equivalent to calling CoreWebView2.Reload on CoreWebView2</span></span>

##### <span data-ttu-id="09e50-292">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-292">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-293">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="09e50-293">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="09e50-294"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="09e50-294">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="09e50-295">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-295">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-296">停止</span><span class="sxs-lookup"><span data-stu-id="09e50-296">Stop</span></span> 

<span data-ttu-id="09e50-297">停止所有导航和挂起的资源读取。</span><span class="sxs-lookup"><span data-stu-id="09e50-297">Stops all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="09e50-298">public void [Stop](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="09e50-298">public void [Stop](#stop)()</span></span>

<span data-ttu-id="09e50-299">等同于调用 CoreWebView2。在 CoreWebView2 上停止</span><span class="sxs-lookup"><span data-stu-id="09e50-299">Equivalent to calling CoreWebView2.Stop on CoreWebView2</span></span>

##### <span data-ttu-id="09e50-300">异常</span><span class="sxs-lookup"><span data-stu-id="09e50-300">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="09e50-301">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="09e50-301">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="09e50-302"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="09e50-302">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="09e50-303">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="09e50-303">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="09e50-304">WebView2</span><span class="sxs-lookup"><span data-stu-id="09e50-304">WebView2</span></span> 

<span data-ttu-id="09e50-305">创建 WebView2 控件的新实例。</span><span class="sxs-lookup"><span data-stu-id="09e50-305">Creates a new instance of a WebView2 control.</span></span>

> <span data-ttu-id="09e50-306">公共[WebView2](#webview2)（）</span><span class="sxs-lookup"><span data-stu-id="09e50-306">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="09e50-307">请注意，在初始化之前，控件的 CoreWebView2 将为 null。</span><span class="sxs-lookup"><span data-stu-id="09e50-307">Note that the control's CoreWebView2 will be null until initialized.</span></span> <span data-ttu-id="09e50-308">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="09e50-308">See the WebView2 class documentation for an initialization overview.</span></span>

