---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/13/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: f2c3bcb5334abc907a838971ebc1773b6485194f
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652879"
---
# <span data-ttu-id="5b338-104">WebView2 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-104">Microsoft.Web.WebView2.Wpf.WebView2 class</span></span> 

<span data-ttu-id="5b338-105">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="5b338-105">Namespace: Microsoft.Web.WebView2.Wpf</span></span>\
<span data-ttu-id="5b338-106">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-106">Assembly: Microsoft.Web.WebView2.Wpf.dll</span></span>

```
class Microsoft.Web.WebView2.Wpf.WebView2
  : public HwndHost
```

<span data-ttu-id="5b338-107">用于在 WPF 应用程序中嵌入 web 内容的控件。</span><span class="sxs-lookup"><span data-stu-id="5b338-107">A control to embed web content in a WPF application.</span></span>

## <span data-ttu-id="5b338-108">摘要</span><span class="sxs-lookup"><span data-stu-id="5b338-108">Summary</span></span>

 <span data-ttu-id="5b338-109">成员</span><span class="sxs-lookup"><span data-stu-id="5b338-109">Members</span></span>                        | <span data-ttu-id="5b338-110">描述</span><span class="sxs-lookup"><span data-stu-id="5b338-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="5b338-111">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="5b338-111">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="5b338-112">CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-112">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>
[<span data-ttu-id="5b338-113">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="5b338-113">CoreWebView2Ready</span></span>](#corewebview2ready) | <span data-ttu-id="5b338-114">当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="5b338-114">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>
[<span data-ttu-id="5b338-115">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="5b338-115">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="5b338-116">CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-116">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>
[<span data-ttu-id="5b338-117">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="5b338-117">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="5b338-118">CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-118">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>
[<span data-ttu-id="5b338-119">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="5b338-119">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="5b338-120">CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-120">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>
[<span data-ttu-id="5b338-121">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="5b338-121">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="5b338-122">CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-122">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>
[<span data-ttu-id="5b338-123">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="5b338-123">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="5b338-124">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="5b338-124">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="5b338-125">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="5b338-125">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="5b338-126">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="5b338-126">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="5b338-127">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-127">CoreWebView2</span></span>](#corewebview2) | <span data-ttu-id="5b338-128">访问基础 Core CoreWebView2 COM API 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="5b338-128">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>
[<span data-ttu-id="5b338-129">CreationProperties</span><span class="sxs-lookup"><span data-stu-id="5b338-129">CreationProperties</span></span>](#creationproperties) | <span data-ttu-id="5b338-130">获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。</span><span class="sxs-lookup"><span data-stu-id="5b338-130">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="5b338-131">来源</span><span class="sxs-lookup"><span data-stu-id="5b338-131">Source</span></span>](#source) | <span data-ttu-id="5b338-132">Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。</span><span class="sxs-lookup"><span data-stu-id="5b338-132">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>
[<span data-ttu-id="5b338-133">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="5b338-133">EnsureCoreWebView2Async</span></span>](#ensurecorewebview2async) | <span data-ttu-id="5b338-134">显式触发控件的 CoreWebView2 的初始化。</span><span class="sxs-lookup"><span data-stu-id="5b338-134">Explicitly trigger initialization of the control's CoreWebView2.</span></span>
[<span data-ttu-id="5b338-135">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="5b338-135">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="5b338-136">通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="5b338-136">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="5b338-137">GoBack</span><span class="sxs-lookup"><span data-stu-id="5b338-137">GoBack</span></span>](#goback) | <span data-ttu-id="5b338-138">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="5b338-138">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="5b338-139">GoForward</span><span class="sxs-lookup"><span data-stu-id="5b338-139">GoForward</span></span>](#goforward) | <span data-ttu-id="5b338-140">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="5b338-140">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="5b338-141">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="5b338-141">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="5b338-142">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="5b338-142">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="5b338-143">重载</span><span class="sxs-lookup"><span data-stu-id="5b338-143">Reload</span></span>](#reload) | <span data-ttu-id="5b338-144">重新加载当前页。</span><span class="sxs-lookup"><span data-stu-id="5b338-144">Reloads the current page.</span></span>
[<span data-ttu-id="5b338-145">停止</span><span class="sxs-lookup"><span data-stu-id="5b338-145">Stop</span></span>](#stop) | <span data-ttu-id="5b338-146">停止所有导航和挂起的资源读取。</span><span class="sxs-lookup"><span data-stu-id="5b338-146">Stops all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="5b338-147">WebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-147">WebView2</span></span>](#webview2) | <span data-ttu-id="5b338-148">创建 WebView2 控件的新实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-148">Creates a new instance of a WebView2 control.</span></span>
[<span data-ttu-id="5b338-149">BuildWindowCore</span><span class="sxs-lookup"><span data-stu-id="5b338-149">BuildWindowCore</span></span>](#buildwindowcore) | <span data-ttu-id="5b338-150">这将从 HwndHost 重写，并将其调用以指示我们创建 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-150">This is overridden from HwndHost and is called to instruct us to create our HWND.</span></span>
[<span data-ttu-id="5b338-151">DestroyWindowCore</span><span class="sxs-lookup"><span data-stu-id="5b338-151">DestroyWindowCore</span></span>](#destroywindowcore) | <span data-ttu-id="5b338-152">这将从 HwndHost 重写，并被调用以指示我们销毁我们的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-152">This is overridden from HwndHost and is called to instruct us to destroy our HWND.</span></span>
[<span data-ttu-id="5b338-153">处置</span><span class="sxs-lookup"><span data-stu-id="5b338-153">Dispose</span></span>](#dispose) | <span data-ttu-id="5b338-154">根据 IDispose 模式的典型实现，我们的基类调用此类。</span><span class="sxs-lookup"><span data-stu-id="5b338-154">This is called by our base class according to the typical implementation of the IDispose pattern.</span></span>
[<span data-ttu-id="5b338-155">HasFocusWithinCore</span><span class="sxs-lookup"><span data-stu-id="5b338-155">HasFocusWithinCore</span></span>](#hasfocuswithincore) | <span data-ttu-id="5b338-156">这将从 HwndHost 重写，并且在 WPF 需要知道焦点是否位于我们的控件/窗口中时调用。</span><span class="sxs-lookup"><span data-stu-id="5b338-156">This is overridden from HwndHost and is called when WPF needs to know if the focus is in our control/window.</span></span>
[<span data-ttu-id="5b338-157">OnKeyDown</span><span class="sxs-lookup"><span data-stu-id="5b338-157">OnKeyDown</span></span>](#onkeydown) | <span data-ttu-id="5b338-158">这将从 UIElement 重写，并调用以允许我们处理按键输入。</span><span class="sxs-lookup"><span data-stu-id="5b338-158">This is overridden from UIElement and called to allow us to handle key press input.</span></span>
[<span data-ttu-id="5b338-159">OnKeyUp</span><span class="sxs-lookup"><span data-stu-id="5b338-159">OnKeyUp</span></span>](#onkeyup) | <span data-ttu-id="5b338-160">请参阅 OnKeyDown。</span><span class="sxs-lookup"><span data-stu-id="5b338-160">See OnKeyDown.</span></span>
[<span data-ttu-id="5b338-161">OnPreviewKeyDown</span><span class="sxs-lookup"><span data-stu-id="5b338-161">OnPreviewKeyDown</span></span>](#onpreviewkeydown) | <span data-ttu-id="5b338-162">这是 "预览" （例如，</span><span class="sxs-lookup"><span data-stu-id="5b338-162">This is the "Preview" (i.e.</span></span>
[<span data-ttu-id="5b338-163">OnPreviewKeyUp</span><span class="sxs-lookup"><span data-stu-id="5b338-163">OnPreviewKeyUp</span></span>](#onpreviewkeyup) | <span data-ttu-id="5b338-164">请参阅 OnPreviewKeyDown。</span><span class="sxs-lookup"><span data-stu-id="5b338-164">See OnPreviewKeyDown.</span></span>
[<span data-ttu-id="5b338-165">OnWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="5b338-165">OnWindowPositionChanged</span></span>](#onwindowpositionchanged) | <span data-ttu-id="5b338-166">这将从 HwndHost 重写，并在控件的位置更改时被调用。</span><span class="sxs-lookup"><span data-stu-id="5b338-166">This is overridden from HwndHost and called when our control's location has changed.</span></span>
[<span data-ttu-id="5b338-167">TabIntoCore</span><span class="sxs-lookup"><span data-stu-id="5b338-167">TabIntoCore</span></span>](#tabintocore) | <span data-ttu-id="5b338-168">这将从 HwndHost 重写，并被调用以通知我们按 tab 键使焦点移动到我们的控件/窗口中。</span><span class="sxs-lookup"><span data-stu-id="5b338-168">This is overridden from HwndHost and is called to inform us that tabbing has caused the focus to move into our control/window.</span></span>

<span data-ttu-id="5b338-169">此控件实际上是围绕 WebView2 COM API 的包装，你可以在此处找到文档： [https://aka.ms/webview2](https://aka.ms/webview2) 通过访问 CoreWebView2 属性，可以直接访问基础 ICoreWebView2 接口及其所有功能。</span><span class="sxs-lookup"><span data-stu-id="5b338-169">This control is effectively a wrapper around the WebView2 COM API, which you can find documentation for here: [https://aka.ms/webview2](https://aka.ms/webview2) You can directly access the underlying ICoreWebView2 interface and all of its functionality by accessing the CoreWebView2 property.</span></span> <span data-ttu-id="5b338-170">某些最常用的 COM 功能也可以通过控件上的包装方法/属性/事件直接访问。</span><span class="sxs-lookup"><span data-stu-id="5b338-170">Some of the most common COM functionality is also accessible directly through wrapper methods/properties/events on the control.</span></span>

<span data-ttu-id="5b338-171">在创建时，该控件的 CoreWebView2 属性将为 null。</span><span class="sxs-lookup"><span data-stu-id="5b338-171">Upon creation, the control's CoreWebView2 property will be null.</span></span> <span data-ttu-id="5b338-172">这是因为创建 CoreWebView2 是一个昂贵的操作，它涉及启动 Edge 浏览器进程之类的操作。</span><span class="sxs-lookup"><span data-stu-id="5b338-172">This is because creating the CoreWebView2 is an expensive operation which involves things like launching Edge browser processes.</span></span> <span data-ttu-id="5b338-173">有两种方法可导致创建 CoreWebView2：1）调用 EnsureCoreWebView2Async 方法。</span><span class="sxs-lookup"><span data-stu-id="5b338-173">There are two ways to cause the CoreWebView2 to be created: 1) Call the EnsureCoreWebView2Async method.</span></span> <span data-ttu-id="5b338-174">这称为显式初始化。</span><span class="sxs-lookup"><span data-stu-id="5b338-174">This is referred to as explicit initialization.</span></span> <span data-ttu-id="5b338-175">2）设置 Source 属性（例如，可以通过标记执行此操作）。</span><span class="sxs-lookup"><span data-stu-id="5b338-175">2) Set the Source property (which could be done from markup, for example).</span></span> <span data-ttu-id="5b338-176">这称为隐式初始化。</span><span class="sxs-lookup"><span data-stu-id="5b338-176">This is referred to as implicit initialization.</span></span> <span data-ttu-id="5b338-177">这两个选项都将开始在后台初始化，并返回到呼叫方，而无需等待它完成。</span><span class="sxs-lookup"><span data-stu-id="5b338-177">Either option will start initialization in the background and return back to the caller without waiting for it to finish.</span></span> <span data-ttu-id="5b338-178">若要指定有关初始化过程的选项，请将你自己的 CoreWebView2Environment 传递给 EnsureCoreWebView2Async，或在初始化之前设置控件的 CreationProperties 属性。</span><span class="sxs-lookup"><span data-stu-id="5b338-178">To specify options regarding the initialization process, either pass your own CoreWebView2Environment to EnsureCoreWebView2Async or set the control's CreationProperties property prior to initialization.</span></span>

<span data-ttu-id="5b338-179">初始化完成后（无论其触发方式如何），将按如下顺序发生以下情况：1）将调用控件的 CoreWebView2Ready 事件。</span><span class="sxs-lookup"><span data-stu-id="5b338-179">When initialization has finished (regardless of how it was triggered) then the following things will occur, in this order: 1) The control's CoreWebView2Ready event will be invoked.</span></span> <span data-ttu-id="5b338-180">如果你需要在其使用之前对 CoreWebView2 执行一次设置操作，则应在该事件的处理程序中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="5b338-180">If you need to perform one time setup operations on the CoreWebView2 prior to its use then you should do so in a handler for that event.</span></span> <span data-ttu-id="5b338-181">2）如果 Uri 已设置为 Source 属性，则控件将开始在后台导航到该属性（即，这些步骤将在不等待导航结束的情况下继续）。</span><span class="sxs-lookup"><span data-stu-id="5b338-181">2) If a Uri has been set to the Source property then the control will start navigating to it in the background (i.e. these steps will continue without waiting for the navigation to finish).</span></span> <span data-ttu-id="5b338-182">3）从 EnsureCoreWebView2Async 返回的任务将完成。</span><span class="sxs-lookup"><span data-stu-id="5b338-182">3) The Task returned from EnsureCoreWebView2Async will complete.</span></span>

<span data-ttu-id="5b338-183">有关初始化过程中涉及的任何方法/属性/事件的更多详细信息，请参阅其特定文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-183">For more details about any of the methods/properties/events involved in the initialization process, see its specific documentation.</span></span>

<span data-ttu-id="5b338-184">由于该控件的 CoreWebView2 是一个非常重量级的对象（有可能负责多个正在运行的进程和 mb 的磁盘空间），因此该控件实现 IDisposable 以提供用于释放它的显式方法。</span><span class="sxs-lookup"><span data-stu-id="5b338-184">Because the control's CoreWebView2 is a very heavyweight object (potentially responsible for multiple running processes and megabytes of disk space) the control implements IDisposable to provide an explicit means to free it.</span></span> <span data-ttu-id="5b338-185">调用 Dispose 将释放 CoreWebView2 及其基础资源（除其他 WebViews 还在使用的其他资源之外），并将 CoreWebView2 重置为 null。</span><span class="sxs-lookup"><span data-stu-id="5b338-185">Calling Dispose will release the CoreWebView2 and its underlying resources (except any that are also being used by other WebViews), and reset CoreWebView2 to null.</span></span> <span data-ttu-id="5b338-186">在 Dispose 调用后，CoreWebView2 无法重新初始化，并且尝试使用需要它的功能将引发 ObjectDisposedException。</span><span class="sxs-lookup"><span data-stu-id="5b338-186">After Dispose has been called the CoreWebView2 cannot be re-initialized, and any attempt to use functionality which requires it will throw an ObjectDisposedException.</span></span>

<span data-ttu-id="5b338-187">请注意，此控件扩展了 HwndHost，以便嵌入实时位于 WPF 生态系统之外的窗口。</span><span class="sxs-lookup"><span data-stu-id="5b338-187">Note that this control extends HwndHost in order to embed windows which live outside of the WPF ecosystem.</span></span> <span data-ttu-id="5b338-188">这对控件的输入和输出行为以及它从 UIElement 和 FrameworkElement 中 "继承" 的功能有一定的影响。</span><span class="sxs-lookup"><span data-stu-id="5b338-188">This has some implications regarding the control's input and output behavior as well as the functionality it "inherits" from UIElement and FrameworkElement.</span></span> <span data-ttu-id="5b338-189">有关详细信息，请参阅 HwndHost 和 WPF/Win32 互操作文档：</span><span class="sxs-lookup"><span data-stu-id="5b338-189">See the HwndHost and WPF/Win32 interop documentation for more info:</span></span>

* [https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost](https://docs.microsoft.com/dotnet/api/system.windows.interop.hwndhost)

* [https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf](https://docs.microsoft.com/dotnet/framework/wpf/advanced/wpf-and-win32-interoperation#hwnds-inside-wpf)

## <span data-ttu-id="5b338-190">成员</span><span class="sxs-lookup"><span data-stu-id="5b338-190">Members</span></span>

#### <span data-ttu-id="5b338-191">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="5b338-191">ContentLoading</span></span> 

<span data-ttu-id="5b338-192">CoreWebView2 的 CoreWebView2 ContentLoading 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-192">A wrapper around the CoreWebView2.ContentLoading event of CoreWebView2.</span></span>

> <span data-ttu-id="5b338-193">公共事件 EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="5b338-193">public event EventHandler< CoreWebView2ContentLoadingEventArgs > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="5b338-194">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5b338-194">The only difference between this event and CoreWebView2.ContentLoading is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="5b338-195">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-195">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.ContentLoading will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="5b338-196">CoreWebView2Ready</span><span class="sxs-lookup"><span data-stu-id="5b338-196">CoreWebView2Ready</span></span> 

<span data-ttu-id="5b338-197">当控件的 CoreWebView2 已完成初始化时（无论初始化的触发方式），但在将其用于任何内容之前，将触发此事件。</span><span class="sxs-lookup"><span data-stu-id="5b338-197">This event is triggered when the control's CoreWebView2 has finished being initialized (regardless of how initialization was triggered) but before it is used for anything.</span></span>

> <span data-ttu-id="5b338-198">公共事件 EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span><span class="sxs-lookup"><span data-stu-id="5b338-198">public event EventHandler< EventArgs > [CoreWebView2Ready](#corewebview2ready)</span></span>

<span data-ttu-id="5b338-199">如果你需要在要影响其所有使用情况的 CoreWebView2 上执行一次设置操作（例如，添加事件处理程序、配置设置、安装文档创建脚本、添加主机对象），你应该处理此事件。</span><span class="sxs-lookup"><span data-stu-id="5b338-199">You should handle this event if you need to perform one time setup operations on the CoreWebView2 which you want to affect all of its usages (e.g. adding event handlers, configuring settings, installing document creation scripts, adding host objects).</span></span> <span data-ttu-id="5b338-200">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-200">See the WebView2 class documentation for an initialization overview.</span></span>

<span data-ttu-id="5b338-201">此事件不提供任何参数，并且发件人将成为 WebView2 控件，它的 CoreWebView2 属性将在首次有效（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="5b338-201">This event doesn't provide any arguments, and the sender will be the WebView2 control, whose CoreWebView2 property will now be valid (i.e. non-null) for the first time.</span></span>

#### <span data-ttu-id="5b338-202">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="5b338-202">NavigationCompleted</span></span> 

<span data-ttu-id="5b338-203">CoreWebView2 的 CoreWebView2 NavigationCompleted 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-203">A wrapper around the CoreWebView2.NavigationCompleted event of CoreWebView2.</span></span>

> <span data-ttu-id="5b338-204">公共事件 EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="5b338-204">public event EventHandler< CoreWebView2NavigationCompletedEventArgs > [NavigationCompleted](#navigationcompleted)</span></span>

<span data-ttu-id="5b338-205">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5b338-205">The only difference between this event and CoreWebView2.NavigationCompleted is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="5b338-206">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-206">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationCompleted will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="5b338-207">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="5b338-207">NavigationStarting</span></span> 

<span data-ttu-id="5b338-208">CoreWebView2 的 CoreWebView2 NavigationStarting 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-208">A wrapper around the CoreWebView2.NavigationStarting event of CoreWebView2.</span></span>

> <span data-ttu-id="5b338-209">公共事件 EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="5b338-209">public event EventHandler< CoreWebView2NavigationStartingEventArgs > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="5b338-210">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5b338-210">The only difference between this event and CoreWebView2.NavigationStarting is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="5b338-211">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-211">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.NavigationStarting will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="5b338-212">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="5b338-212">SourceChanged</span></span> 

<span data-ttu-id="5b338-213">CoreWebView2 的 CoreWebView2 SourceChanged 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-213">A wrapper around the CoreWebView2.SourceChanged event of CoreWebView2.</span></span>

> <span data-ttu-id="5b338-214">公共事件 EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="5b338-214">public event EventHandler< CoreWebView2SourceChangedEventArgs > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="5b338-215">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5b338-215">The only difference between this event and CoreWebView2.SourceChanged is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="5b338-216">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-216">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.SourceChanged will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="5b338-217">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="5b338-217">WebMessageReceived</span></span> 

<span data-ttu-id="5b338-218">CoreWebView2 的 CoreWebView2 WebMessageReceived 事件周围的包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-218">A wrapper around the CoreWebView2.WebMessageReceived event of CoreWebView2.</span></span>

> <span data-ttu-id="5b338-219">公共事件 EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="5b338-219">public event EventHandler< CoreWebView2WebMessageReceivedEventArgs > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="5b338-220">此事件与 CoreWebView2 之间的唯一区别是传递给处理程序的第一个参数。</span><span class="sxs-lookup"><span data-stu-id="5b338-220">The only difference between this event and CoreWebView2.WebMessageReceived is the first parameter that's passed to handlers.</span></span> <span data-ttu-id="5b338-221">此事件的处理程序将收到 WebView2 控件，而 CoreWebView2 的处理程序将收到 CoreWebView2 实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-221">Handlers of this event will receive the WebView2 control, whereas handlers of CoreWebView2.WebMessageReceived will receive the CoreWebView2 instance.</span></span>

#### <span data-ttu-id="5b338-222">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="5b338-222">CanGoBack</span></span> 

<span data-ttu-id="5b338-223">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="5b338-223">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="5b338-224">公共 bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="5b338-224">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="5b338-225">CoreWebView2 的 CanGoBack 属性的 CoreWebView2 包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-225">Wrapper around the CoreWebView2.CanGoBack property of CoreWebView2.</span></span> <span data-ttu-id="5b338-226">如果 CoreWebView2 尚未初始化，则返回 false。</span><span class="sxs-lookup"><span data-stu-id="5b338-226">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="5b338-227">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="5b338-227">CanGoForward</span></span> 

<span data-ttu-id="5b338-228">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="5b338-228">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="5b338-229">公共 bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="5b338-229">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="5b338-230">CoreWebView2 的 CanGoForward 属性的 CoreWebView2 包装器。</span><span class="sxs-lookup"><span data-stu-id="5b338-230">Wrapper around the CoreWebView2.CanGoForward property of CoreWebView2.</span></span> <span data-ttu-id="5b338-231">如果 CoreWebView2 尚未初始化，则返回 false。</span><span class="sxs-lookup"><span data-stu-id="5b338-231">If CoreWebView2 isn't initialized yet then returns false.</span></span>

#### <span data-ttu-id="5b338-232">CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-232">CoreWebView2</span></span> 

<span data-ttu-id="5b338-233">访问基础 Core CoreWebView2 COM API 的完整功能。</span><span class="sxs-lookup"><span data-stu-id="5b338-233">Access the complete functionality of the underlying Core.CoreWebView2 COM API.</span></span>

> <span data-ttu-id="5b338-234">公共 CoreWebView2 [CoreWebView2](#corewebview2)</span><span class="sxs-lookup"><span data-stu-id="5b338-234">public CoreWebView2 [CoreWebView2](#corewebview2)</span></span>

<span data-ttu-id="5b338-235">返回 null，直到初始化完成。</span><span class="sxs-lookup"><span data-stu-id="5b338-235">Returns null until initialization has completed.</span></span> <span data-ttu-id="5b338-236">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-236">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="5b338-237">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-237">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-238">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-238">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="5b338-239">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="5b338-239">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="5b338-240">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-240">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-241">CreationProperties</span><span class="sxs-lookup"><span data-stu-id="5b338-241">CreationProperties</span></span> 

<span data-ttu-id="5b338-242">获取或设置在控件的 CoreWebView2 初始化期间使用的一袋选项。</span><span class="sxs-lookup"><span data-stu-id="5b338-242">Gets or sets a bag of options which are used during initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="5b338-243">公共 CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span><span class="sxs-lookup"><span data-stu-id="5b338-243">public CoreWebView2CreationProperties [CreationProperties](#creationproperties)</span></span>

<span data-ttu-id="5b338-244">在已开始控件的 CoreWebView2 初始化后，设置此属性将不起作用（将保留旧值）。</span><span class="sxs-lookup"><span data-stu-id="5b338-244">Setting this property won't work after initialization of the control's CoreWebView2 has started (the old value will be retained).</span></span> <span data-ttu-id="5b338-245">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-245">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="5b338-246">来源</span><span class="sxs-lookup"><span data-stu-id="5b338-246">Source</span></span> 

<span data-ttu-id="5b338-247">Web 视图当前正在显示的顶级 Uri （或将在其 CoreWebView2 的初始化完成后显示）。</span><span class="sxs-lookup"><span data-stu-id="5b338-247">The top-level Uri which the WebView is currently displaying (or will display once initialization of its CoreWebView2 is finished).</span></span>

> <span data-ttu-id="5b338-248">公共 Uri[源](#source)</span><span class="sxs-lookup"><span data-stu-id="5b338-248">public Uri [Source](#source)</span></span>

<span data-ttu-id="5b338-249">一般说来，获取此属性等效于获取 CoreWebView2 的 CoreWebView2 属性，并且设置此属性等效于在 CoreWebView2 上调用 CoreWebView2 方法。</span><span class="sxs-lookup"><span data-stu-id="5b338-249">Generally speaking, getting this property is equivalent to getting the CoreWebView2.Source property of CoreWebView2 and setting this property is equivalent to calling the CoreWebView2.Navigate method on CoreWebView2.</span></span> <span data-ttu-id="5b338-250">在 CoreWebView2 初始化之前获取此属性将检索已设置为其的最后一个 Uri。</span><span class="sxs-lookup"><span data-stu-id="5b338-250">Getting this property before the CoreWebView2 has been initialized will retrieve the last Uri which was set to it.</span></span> <span data-ttu-id="5b338-251">在 CoreWebView2 初始化之前设置此属性将导致在后台启动初始化（如果尚未进行），之后，WebView2 将导航到指定的 Uri。</span><span class="sxs-lookup"><span data-stu-id="5b338-251">Setting this property before the CoreWebView2 has been initialized will cause initialization to start in the background (if not already in progress), after which the WebView2 will navigate to the specified Uri.</span></span> <span data-ttu-id="5b338-252">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-252">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="5b338-253">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-253">Exceptions</span></span>
* `ObjectDisposedException` <span data-ttu-id="5b338-254">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-254">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-255">EnsureCoreWebView2Async</span><span class="sxs-lookup"><span data-stu-id="5b338-255">EnsureCoreWebView2Async</span></span> 

<span data-ttu-id="5b338-256">显式触发控件的 CoreWebView2 的初始化。</span><span class="sxs-lookup"><span data-stu-id="5b338-256">Explicitly trigger initialization of the control's CoreWebView2.</span></span>

> <span data-ttu-id="5b338-257">公共任务[EnsureCoreWebView2Async](#ensurecorewebview2async)（CoreWebView2Environment 环境）</span><span class="sxs-lookup"><span data-stu-id="5b338-257">public Task [EnsureCoreWebView2Async](#ensurecorewebview2async)(CoreWebView2Environment environment)</span></span>

<span data-ttu-id="5b338-258">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-258">See the WebView2 class documentation for an initialization overview.</span></span>

##### <span data-ttu-id="5b338-259">参数</span><span class="sxs-lookup"><span data-stu-id="5b338-259">Parameters</span></span>
* `environment` <span data-ttu-id="5b338-260">应用于创建 CoreWebView2 的预创建的 CoreWebView2Environment。</span><span class="sxs-lookup"><span data-stu-id="5b338-260">A pre-created CoreWebView2Environment that should be used to create the CoreWebView2.</span></span> <span data-ttu-id="5b338-261">创建自己的环境使你可以控制影响 CoreWebView2 初始化方式的多个选项。</span><span class="sxs-lookup"><span data-stu-id="5b338-261">Creating your own environment gives you control over several options that affect how the CoreWebView2 is initialized.</span></span> <span data-ttu-id="5b338-262">如果你将环境传递到此方法，则它将覆盖 CreationProperties 属性上指定的任何设置。</span><span class="sxs-lookup"><span data-stu-id="5b338-262">If you pass an environment to this method then it will override any settings specified on the CreationProperties property.</span></span> <span data-ttu-id="5b338-263">如果传递 null （默认值），并且未将任何值设置为 CreationProperties，则将自动创建和使用默认环境。</span><span class="sxs-lookup"><span data-stu-id="5b338-263">If you pass null (the default value) and no value has been set to CreationProperties then a default environment will be created and used automatically.</span></span> 

##### <span data-ttu-id="5b338-264">返回</span><span class="sxs-lookup"><span data-stu-id="5b338-264">Returns</span></span>
<span data-ttu-id="5b338-265">表示后台初始化进程的任务。</span><span class="sxs-lookup"><span data-stu-id="5b338-265">A Task that represents the background initialization process.</span></span> <span data-ttu-id="5b338-266">任务完成后，CoreWebView2 属性将可供使用（即非 null）。</span><span class="sxs-lookup"><span data-stu-id="5b338-266">When the task completes then the CoreWebView2 property will be available for use (i.e. non-null).</span></span> <span data-ttu-id="5b338-267">请注意，将在任务完成之前调用控件的 CoreWebView2Ready 事件。</span><span class="sxs-lookup"><span data-stu-id="5b338-267">Note that the control's CoreWebView2Ready event will be invoked before the task completes.</span></span> 

<span data-ttu-id="5b338-268">额外调用此方法将不起作用（忽略任何指定的环境），并返回与第一次调用相同的任务。</span><span class="sxs-lookup"><span data-stu-id="5b338-268">Calling this method additional times will have no effect (any specified environment is ignored) and return the same Task as the first call.</span></span> <span data-ttu-id="5b338-269">通过设置 Source 属性隐式触发初始化后调用此方法将不起作用（忽略任何指定的环境），而只是返回表示已在进行的初始化的任务。</span><span class="sxs-lookup"><span data-stu-id="5b338-269">Calling this method after initialization has been implicitly triggered by setting the Source property will have no effect (any specified environment is ignored) and simply return a Task representing that initialization already in progress.</span></span> <span data-ttu-id="5b338-270">请注意，即使此方法是异步的并返回任务，它仍必须在 UI 线程上调用，如大多数 UI 控件的大多数公共功能。</span><span class="sxs-lookup"><span data-stu-id="5b338-270">Note that even though this method is asynchronous and returns a Task, it still must be called on the UI thread like most public functionality of most UI controls.</span></span> 

##### <span data-ttu-id="5b338-271">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-271">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-272">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-272">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="5b338-273">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="5b338-273">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="5b338-274">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-274">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-275">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="5b338-275">ExecuteScriptAsync</span></span> 

<span data-ttu-id="5b338-276">通过在 Web 视图中呈现的当前顶级文档中的 javaScript 参数执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="5b338-276">Executes JavaScript code from the javaScript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="5b338-277">公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串 javaScript）</span><span class="sxs-lookup"><span data-stu-id="5b338-277">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="5b338-278">等同于在 CoreWebView2 上调用 CoreWebView2 ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="5b338-278">Equivalent to calling CoreWebView2.ExecuteScriptAsync on CoreWebView2</span></span>

##### <span data-ttu-id="5b338-279">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-279">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-280">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="5b338-280">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

* `InvalidOperationException` <span data-ttu-id="5b338-281">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-281">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="5b338-282">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="5b338-282">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="5b338-283">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-283">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-284">GoBack</span><span class="sxs-lookup"><span data-stu-id="5b338-284">GoBack</span></span> 

<span data-ttu-id="5b338-285">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="5b338-285">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="5b338-286">公共 void [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="5b338-286">public void [GoBack](#goback)()</span></span>

<span data-ttu-id="5b338-287">如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoBack，否则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b338-287">Equivalent to calling CoreWebView2.GoBack on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="5b338-288">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-288">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-289">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-289">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="5b338-290">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="5b338-290">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="5b338-291">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-291">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-292">GoForward</span><span class="sxs-lookup"><span data-stu-id="5b338-292">GoForward</span></span> 

<span data-ttu-id="5b338-293">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="5b338-293">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="5b338-294">公共 void [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="5b338-294">public void [GoForward](#goforward)()</span></span>

<span data-ttu-id="5b338-295">如果 CoreWebView2 尚未初始化，则等效于对 CoreWebView2 调用 CoreWebView2 GoForward，否则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="5b338-295">Equivalent to calling CoreWebView2.GoForward on CoreWebView2 If CoreWebView2 hasn't been initialized yet then does nothing.</span></span>

##### <span data-ttu-id="5b338-296">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-296">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-297">如果调用线程不是创建此对象的线程（通常为 UI 线程），则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-297">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span> <span data-ttu-id="5b338-298">有关详细信息，请参阅 DispatcherObject VerifyAccess。</span><span class="sxs-lookup"><span data-stu-id="5b338-298">See DispatcherObject.VerifyAccess for more info.</span></span>

* `ObjectDisposedException` <span data-ttu-id="5b338-299">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-299">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-300">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="5b338-300">NavigateToString</span></span> 

<span data-ttu-id="5b338-301">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="5b338-301">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="5b338-302">公共 void [NavigateToString](#navigatetostring)（string htmlContent）</span><span class="sxs-lookup"><span data-stu-id="5b338-302">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="5b338-303">等同于在 CoreWebView2 上调用 CoreWebView2 NavigateToString</span><span class="sxs-lookup"><span data-stu-id="5b338-303">Equivalent to calling CoreWebView2.NavigateToString on CoreWebView2</span></span>

##### <span data-ttu-id="5b338-304">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-304">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-305">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="5b338-305">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="5b338-306"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="5b338-306">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="5b338-307">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-307">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-308">重载</span><span class="sxs-lookup"><span data-stu-id="5b338-308">Reload</span></span> 

<span data-ttu-id="5b338-309">重新加载当前页。</span><span class="sxs-lookup"><span data-stu-id="5b338-309">Reloads the current page.</span></span>

> <span data-ttu-id="5b338-310">public void [Reload](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="5b338-310">public void [Reload](#reload)()</span></span>

<span data-ttu-id="5b338-311">等效于在 CoreWebView2 上调用 CoreWebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-311">Equivalent to calling CoreWebView2.Reload on CoreWebView2</span></span>

##### <span data-ttu-id="5b338-312">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-312">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-313">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="5b338-313">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="5b338-314"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="5b338-314">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="5b338-315">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-315">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-316">停止</span><span class="sxs-lookup"><span data-stu-id="5b338-316">Stop</span></span> 

<span data-ttu-id="5b338-317">停止所有导航和挂起的资源读取。</span><span class="sxs-lookup"><span data-stu-id="5b338-317">Stops all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="5b338-318">public void [Stop](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="5b338-318">public void [Stop](#stop)()</span></span>

<span data-ttu-id="5b338-319">等同于调用 CoreWebView2。在 CoreWebView2 上停止</span><span class="sxs-lookup"><span data-stu-id="5b338-319">Equivalent to calling CoreWebView2.Stop on CoreWebView2</span></span>

##### <span data-ttu-id="5b338-320">异常</span><span class="sxs-lookup"><span data-stu-id="5b338-320">Exceptions</span></span>
* `InvalidOperationException` <span data-ttu-id="5b338-321">如果 CoreWebView2 尚未初始化，则抛出。</span><span class="sxs-lookup"><span data-stu-id="5b338-321">Thrown if CoreWebView2 hasn't been initialized yet.</span></span>

<span data-ttu-id="5b338-322"><exception cref="InvalidOperationException">如果调用线程不是创建此对象（通常为 UI 线程）的线程，则引发。</span><span class="sxs-lookup"><span data-stu-id="5b338-322">" <exception cref="InvalidOperationException">Thrown if the calling thread isn't the thread which created this object (usually the UI thread).</span></span>  <span data-ttu-id="5b338-323">有关详细信息，请参阅 DispatcherObject VerifyAccess。 </exception>
<exception cref="ObjectDisposedException">如果已在该控件上调用 Dispose，则引发该异常。</span><span class="sxs-lookup"><span data-stu-id="5b338-323">See DispatcherObject.VerifyAccess for more info.</exception>
<exception cref="ObjectDisposedException">Thrown if Dispose has already been called on the control.</span></span>

#### <span data-ttu-id="5b338-324">WebView2</span><span class="sxs-lookup"><span data-stu-id="5b338-324">WebView2</span></span> 

<span data-ttu-id="5b338-325">创建 WebView2 控件的新实例。</span><span class="sxs-lookup"><span data-stu-id="5b338-325">Creates a new instance of a WebView2 control.</span></span>

> <span data-ttu-id="5b338-326">公共[WebView2](#webview2)（）</span><span class="sxs-lookup"><span data-stu-id="5b338-326">public [WebView2](#webview2)()</span></span>

<span data-ttu-id="5b338-327">请注意，在初始化之前，控件的 CoreWebView2 将为 null。</span><span class="sxs-lookup"><span data-stu-id="5b338-327">Note that the control's CoreWebView2 will be null until initialized.</span></span> <span data-ttu-id="5b338-328">有关初始化概述，请参阅 WebView2 类文档。</span><span class="sxs-lookup"><span data-stu-id="5b338-328">See the WebView2 class documentation for an initialization overview.</span></span>

#### <span data-ttu-id="5b338-329">BuildWindowCore</span><span class="sxs-lookup"><span data-stu-id="5b338-329">BuildWindowCore</span></span> 

<span data-ttu-id="5b338-330">这将从 HwndHost 重写，并将其调用以指示我们创建 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-330">This is overridden from HwndHost and is called to instruct us to create our HWND.</span></span>

> <span data-ttu-id="5b338-331">protected override HandleRef [BuildWindowCore](#buildwindowcore)（HandleRef hwndParent）</span><span class="sxs-lookup"><span data-stu-id="5b338-331">protected override HandleRef [BuildWindowCore](#buildwindowcore)(HandleRef hwndParent)</span></span>

##### <span data-ttu-id="5b338-332">参数</span><span class="sxs-lookup"><span data-stu-id="5b338-332">Parameters</span></span>
* `hwndParent` <span data-ttu-id="5b338-333">应用作我们创建的项的父项的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-333">The HWND that we should use as the parent of the one we create.</span></span>

##### <span data-ttu-id="5b338-334">返回</span><span class="sxs-lookup"><span data-stu-id="5b338-334">Returns</span></span>
<span data-ttu-id="5b338-335">我们创建的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-335">The HWND that we created.</span></span>

#### <span data-ttu-id="5b338-336">DestroyWindowCore</span><span class="sxs-lookup"><span data-stu-id="5b338-336">DestroyWindowCore</span></span> 

<span data-ttu-id="5b338-337">这将从 HwndHost 重写，并被调用以指示我们销毁我们的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-337">This is overridden from HwndHost and is called to instruct us to destroy our HWND.</span></span>

> <span data-ttu-id="5b338-338">protected override void [DestroyWindowCore](#destroywindowcore)（HandleRef hwnd）</span><span class="sxs-lookup"><span data-stu-id="5b338-338">protected override void [DestroyWindowCore](#destroywindowcore)(HandleRef hwnd)</span></span>

##### <span data-ttu-id="5b338-339">参数</span><span class="sxs-lookup"><span data-stu-id="5b338-339">Parameters</span></span>
* `hwnd` <span data-ttu-id="5b338-340">我们需要销毁的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-340">Our HWND that we need to destroy.</span></span>

#### <span data-ttu-id="5b338-341">处置</span><span class="sxs-lookup"><span data-stu-id="5b338-341">Dispose</span></span> 

<span data-ttu-id="5b338-342">根据 IDispose 模式的典型实现，我们的基类调用此类。</span><span class="sxs-lookup"><span data-stu-id="5b338-342">This is called by our base class according to the typical implementation of the IDispose pattern.</span></span>

> <span data-ttu-id="5b338-343">受保护替代 void [Dispose](#dispose)（bool 释放）</span><span class="sxs-lookup"><span data-stu-id="5b338-343">protected override void [Dispose](#dispose)(bool disposing)</span></span>

<span data-ttu-id="5b338-344">我们通过释放所有基础 COM 资源（包括我们的 CoreWebView2）来实现它。</span><span class="sxs-lookup"><span data-stu-id="5b338-344">We implement it by releasing all of our underlying COM resources, including our CoreWebView2.</span></span>

##### <span data-ttu-id="5b338-345">参数</span><span class="sxs-lookup"><span data-stu-id="5b338-345">Parameters</span></span>
* `disposing` <span data-ttu-id="5b338-346">如果调用方显式调用 Dispose，则为 True，如果是，则为 false。</span><span class="sxs-lookup"><span data-stu-id="5b338-346">True if a caller is explicitly calling Dispose, false if we're being finalized.</span></span>

#### <span data-ttu-id="5b338-347">HasFocusWithinCore</span><span class="sxs-lookup"><span data-stu-id="5b338-347">HasFocusWithinCore</span></span> 

<span data-ttu-id="5b338-348">这将从 HwndHost 重写，并且在 WPF 需要知道焦点是否位于我们的控件/窗口中时调用。</span><span class="sxs-lookup"><span data-stu-id="5b338-348">This is overridden from HwndHost and is called when WPF needs to know if the focus is in our control/window.</span></span>

> <span data-ttu-id="5b338-349">protected override bool [HasFocusWithinCore](#hasfocuswithincore)（）</span><span class="sxs-lookup"><span data-stu-id="5b338-349">protected override bool [HasFocusWithinCore](#hasfocuswithincore)()</span></span>

<span data-ttu-id="5b338-350">WPF 本身无法知道，因为我们托管的是非 WPF 窗口，因此它通过调用它来询问我们。</span><span class="sxs-lookup"><span data-stu-id="5b338-350">WPF can't know on its own since we're hosting a non-WPF window, so instead it asks us by calling this.</span></span> <span data-ttu-id="5b338-351">若要应答，我们只需基于在获得或失去焦点时激发的 CoreWebView2 事件来跟踪状态。</span><span class="sxs-lookup"><span data-stu-id="5b338-351">To answer, we just track state based on CoreWebView2 events that fire when it gains or loses focus.</span></span>

##### <span data-ttu-id="5b338-352">返回</span><span class="sxs-lookup"><span data-stu-id="5b338-352">Returns</span></span>
<span data-ttu-id="5b338-353">如果焦点位于我们的控件/窗口中，则为 True，否则为 false。</span><span class="sxs-lookup"><span data-stu-id="5b338-353">True if the focus is in our control/window, false if it isn't.</span></span>

#### <span data-ttu-id="5b338-354">OnKeyDown</span><span class="sxs-lookup"><span data-stu-id="5b338-354">OnKeyDown</span></span> 

<span data-ttu-id="5b338-355">这将从 UIElement 重写，并调用以允许我们处理按键输入。</span><span class="sxs-lookup"><span data-stu-id="5b338-355">This is overridden from UIElement and called to allow us to handle key press input.</span></span>

> <span data-ttu-id="5b338-356">protected override void [OnKeyDown](#onkeydown)（KeyEventArgs e）</span><span class="sxs-lookup"><span data-stu-id="5b338-356">protected override void [OnKeyDown](#onkeydown)(KeyEventArgs e)</span></span>

<span data-ttu-id="5b338-357">WPF 不应真正调用此操作来响应键盘事件，因为我们托管的是非 WPF 窗口。</span><span class="sxs-lookup"><span data-stu-id="5b338-357">WPF should never actually call this in response to keyboard events because we're hosting a non-WPF window.</span></span> <span data-ttu-id="5b338-358">当我们的窗口具有焦点时，Windows 会将输入直接发送给它，而不是 WPF 的顶级窗口和输入系统。</span><span class="sxs-lookup"><span data-stu-id="5b338-358">When our window has focus Windows will send the input directly to it rather than to WPF's top-level window and input system.</span></span> <span data-ttu-id="5b338-359">仅当我们显式将加速器密钥输入从 CoreWebView2 到 WPF （在 CoreWebView2Controller_AcceleratorKeyPressed 中）中时，才应调用此重写。</span><span class="sxs-lookup"><span data-stu-id="5b338-359">This override should only be called when we're explicitly forwarding accelerator key input from the CoreWebView2 to WPF (in CoreWebView2Controller_AcceleratorKeyPressed).</span></span> <span data-ttu-id="5b338-360">即使这样，此 KeyDownEvent 才会触发，因为我们的 PreviewKeyDownEvent 实现会显式触发它，匹配 WPF 的常规系统。</span><span class="sxs-lookup"><span data-stu-id="5b338-360">Even then, this KeyDownEvent is only triggered because our PreviewKeyDownEvent implementation explicitly triggers it, matching WPF's usual system.</span></span> <span data-ttu-id="5b338-361">因此，过程如下： CoreWebView2Controller_AcceleratorKeyPressed > 提升 PreviewKeyDownEvent-> OnPreviewKeyDown-> 提升 KeyDownEvent-> OnKeyDown</span><span class="sxs-lookup"><span data-stu-id="5b338-361">So the process is: CoreWebView2Controller_AcceleratorKeyPressed -> raise PreviewKeyDownEvent -> OnPreviewKeyDown -> raise KeyDownEvent -> OnKeyDown</span></span>

#### <span data-ttu-id="5b338-362">OnKeyUp</span><span class="sxs-lookup"><span data-stu-id="5b338-362">OnKeyUp</span></span> 

<span data-ttu-id="5b338-363">请参阅 OnKeyDown。</span><span class="sxs-lookup"><span data-stu-id="5b338-363">See OnKeyDown.</span></span>

> <span data-ttu-id="5b338-364">protected override void [OnKeyUp](#onkeyup)（KeyEventArgs e）</span><span class="sxs-lookup"><span data-stu-id="5b338-364">protected override void [OnKeyUp](#onkeyup)(KeyEventArgs e)</span></span>

#### <span data-ttu-id="5b338-365">OnPreviewKeyDown</span><span class="sxs-lookup"><span data-stu-id="5b338-365">OnPreviewKeyDown</span></span> 

<span data-ttu-id="5b338-366">这是 "预览" （例如，</span><span class="sxs-lookup"><span data-stu-id="5b338-366">This is the "Preview" (i.e.</span></span>

> <span data-ttu-id="5b338-367">protected override void [OnPreviewKeyDown](#onpreviewkeydown)（KeyEventArgs e）</span><span class="sxs-lookup"><span data-stu-id="5b338-367">protected override void [OnPreviewKeyDown](#onpreviewkeydown)(KeyEventArgs e)</span></span>

<span data-ttu-id="5b338-368">隧道）版本的 OnKeyDown，因此它实际上会首先发生。</span><span class="sxs-lookup"><span data-stu-id="5b338-368">tunneling) version of OnKeyDown, so it actually happens first.</span></span> <span data-ttu-id="5b338-369">与 OnKeyDown 一样，只有在从 CoreWebView2 显式转发按键时，才会调用此操作。</span><span class="sxs-lookup"><span data-stu-id="5b338-369">Like OnKeyDown, this will only ever be called if we're explicitly forwarding key presses from the CoreWebView2.</span></span> <span data-ttu-id="5b338-370">为了模仿 WPF 的标准输入处理，当我们收到这种情况时，我们将关闭并引发标准的冒泡 KeyDownEvent。</span><span class="sxs-lookup"><span data-stu-id="5b338-370">In order to mimic WPF's standard input handling, when we receive this we turn around and fire off the standard bubbling KeyDownEvent.</span></span> <span data-ttu-id="5b338-371">这样，WPF 树中的其他人可以看到 WPF 本身在处理按键时将触发的相同标准输入事件对。</span><span class="sxs-lookup"><span data-stu-id="5b338-371">That way others in the WPF tree see the same standard pair of input events that WPF itself would have triggered if it were handling the key press.</span></span>

#### <span data-ttu-id="5b338-372">OnPreviewKeyUp</span><span class="sxs-lookup"><span data-stu-id="5b338-372">OnPreviewKeyUp</span></span> 

<span data-ttu-id="5b338-373">请参阅 OnPreviewKeyDown。</span><span class="sxs-lookup"><span data-stu-id="5b338-373">See OnPreviewKeyDown.</span></span>

> <span data-ttu-id="5b338-374">protected override void [OnPreviewKeyUp](#onpreviewkeyup)（KeyEventArgs e）</span><span class="sxs-lookup"><span data-stu-id="5b338-374">protected override void [OnPreviewKeyUp](#onpreviewkeyup)(KeyEventArgs e)</span></span>

#### <span data-ttu-id="5b338-375">OnWindowPositionChanged</span><span class="sxs-lookup"><span data-stu-id="5b338-375">OnWindowPositionChanged</span></span> 

<span data-ttu-id="5b338-376">这将从 HwndHost 重写，并在控件的位置更改时被调用。</span><span class="sxs-lookup"><span data-stu-id="5b338-376">This is overridden from HwndHost and called when our control's location has changed.</span></span>

> <span data-ttu-id="5b338-377">protected override void [OnWindowPositionChanged](#onwindowpositionchanged)（Rect rcBoundingBox）</span><span class="sxs-lookup"><span data-stu-id="5b338-377">protected override void [OnWindowPositionChanged](#onwindowpositionchanged)(Rect rcBoundingBox)</span></span>

<span data-ttu-id="5b338-378">HwndHost 负责更新我们创建的 HWND。</span><span class="sxs-lookup"><span data-stu-id="5b338-378">The HwndHost takes care of updating the HWND we created.</span></span> <span data-ttu-id="5b338-379">我们需要做的就是将 CoreWebView2 移动到与新位置相匹配的位置。</span><span class="sxs-lookup"><span data-stu-id="5b338-379">What we need to do is move our CoreWebView2 to match the new location.</span></span>

#### <span data-ttu-id="5b338-380">TabIntoCore</span><span class="sxs-lookup"><span data-stu-id="5b338-380">TabIntoCore</span></span> 

<span data-ttu-id="5b338-381">这将从 HwndHost 重写，并被调用以通知我们按 tab 键使焦点移动到我们的控件/窗口中。</span><span class="sxs-lookup"><span data-stu-id="5b338-381">This is overridden from HwndHost and is called to inform us that tabbing has caused the focus to move into our control/window.</span></span>

> <span data-ttu-id="5b338-382">protected override bool [TabIntoCore](#tabintocore)（TraversalRequest 请求）</span><span class="sxs-lookup"><span data-stu-id="5b338-382">protected override bool [TabIntoCore](#tabintocore)(TraversalRequest request)</span></span>

<span data-ttu-id="5b338-383">由于 WPF 无法管理焦点到非 WPF HWND 的转换，因此它会将过渡委托给我们。</span><span class="sxs-lookup"><span data-stu-id="5b338-383">Since WPF can't manage the transition of focus to a non-WPF HWND, it delegates the transition to us here.</span></span> <span data-ttu-id="5b338-384">因此，我们的工作就是将焦点放在我们的外部 HWND 中。</span><span class="sxs-lookup"><span data-stu-id="5b338-384">So our job is just to place the focus in our external HWND.</span></span>

##### <span data-ttu-id="5b338-385">参数</span><span class="sxs-lookup"><span data-stu-id="5b338-385">Parameters</span></span>
* `request` <span data-ttu-id="5b338-386">有关如何移动焦点的信息。</span><span class="sxs-lookup"><span data-stu-id="5b338-386">Information about how the focus is moving.</span></span>

##### <span data-ttu-id="5b338-387">返回</span><span class="sxs-lookup"><span data-stu-id="5b338-387">Returns</span></span>
<span data-ttu-id="5b338-388">如果为 True，则表示已处理导航，或设置为 false 以指示我们未处理。</span><span class="sxs-lookup"><span data-stu-id="5b338-388">True to indicate that we handled the navigation, or false to indicate that we didn't.</span></span>

