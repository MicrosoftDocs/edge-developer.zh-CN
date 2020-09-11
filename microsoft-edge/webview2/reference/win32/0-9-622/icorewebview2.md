---
description: '通过 Microsoft Edge WebView2 控件在本机应用程序中嵌入 web 技术 (HTML、CSS 和 JavaScript) '
title: WebView2 Win32 c + + ICoreWebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/09/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html、ICoreWebView2
ms.openlocfilehash: 6717542349cff327875b609168dff0b82a933668
ms.sourcegitcommit: 0faf538d5033508af4320b9b89c4ed99872f0574
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/10/2020
ms.locfileid: "11011775"
---
# <span data-ttu-id="35452-104">interface ICoreWebView2</span><span class="sxs-lookup"><span data-stu-id="35452-104">interface ICoreWebView2</span></span> 

```
interface ICoreWebView2
  : public IUnknown
```

<span data-ttu-id="35452-105">WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="35452-105">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="35452-106">摘要</span><span class="sxs-lookup"><span data-stu-id="35452-106">Summary</span></span>

 <span data-ttu-id="35452-107">成员</span><span class="sxs-lookup"><span data-stu-id="35452-107">Members</span></span>                        | <span data-ttu-id="35452-108">描述</span><span class="sxs-lookup"><span data-stu-id="35452-108">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="35452-109">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="35452-109">add_ContainsFullScreenElementChanged</span></span>](#add_containsfullscreenelementchanged) | <span data-ttu-id="35452-110">为 ContainsFullScreenElementChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-110">Add an event handler for the ContainsFullScreenElementChanged event.</span></span>
[<span data-ttu-id="35452-111">add_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="35452-111">add_ContentLoading</span></span>](#add_contentloading) | <span data-ttu-id="35452-112">为 ContentLoading 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-112">Add an event handler for the ContentLoading event.</span></span>
[<span data-ttu-id="35452-113">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="35452-113">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="35452-114">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-114">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="35452-115">add_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-115">add_FrameNavigationCompleted</span></span>](#add_framenavigationcompleted) | <span data-ttu-id="35452-116">为 FrameNavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-116">Add an event handler for the FrameNavigationCompleted event.</span></span>
[<span data-ttu-id="35452-117">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-117">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="35452-118">为 FrameNavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-118">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="35452-119">add_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="35452-119">add_HistoryChanged</span></span>](#add_historychanged) | <span data-ttu-id="35452-120">为 HistoryChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-120">Add an event handler for the HistoryChanged event.</span></span>
[<span data-ttu-id="35452-121">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-121">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="35452-122">为 NavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-122">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="35452-123">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-123">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="35452-124">为 NavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-124">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="35452-125">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="35452-125">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="35452-126">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-126">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="35452-127">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="35452-127">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="35452-128">为 Webview.permissionrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-128">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="35452-129">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="35452-129">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="35452-130">为 ProcessFailed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-130">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="35452-131">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="35452-131">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="35452-132">为 ScriptDialogOpening 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-132">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="35452-133">add_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="35452-133">add_SourceChanged</span></span>](#add_sourcechanged) | <span data-ttu-id="35452-134">为 SourceChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-134">Add an event handler for the SourceChanged event.</span></span>
[<span data-ttu-id="35452-135">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="35452-135">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="35452-136">为 WebMessageReceived 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-136">Add an event handler for the WebMessageReceived event.</span></span>
[<span data-ttu-id="35452-137">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="35452-137">add_WebResourceRequested</span></span>](#add_webresourcerequested) | <span data-ttu-id="35452-138">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-138">Add an event handler for the WebResourceRequested event.</span></span>
[<span data-ttu-id="35452-139">add_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="35452-139">add_WindowCloseRequested</span></span>](#add_windowcloserequested) | <span data-ttu-id="35452-140">为 WindowCloseRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-140">Add an event handler for the WindowCloseRequested event.</span></span>
[<span data-ttu-id="35452-141">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="35452-141">AddHostObjectToScript</span></span>](#addhostobjecttoscript) | <span data-ttu-id="35452-142">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-142">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="35452-143">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="35452-143">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="35452-144">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="35452-144">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="35452-145">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="35452-145">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="35452-146">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="35452-146">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="35452-147">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="35452-147">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="35452-148">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-148">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="35452-149">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="35452-149">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="35452-150">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="35452-150">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="35452-151">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="35452-151">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="35452-152">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="35452-152">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="35452-153">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="35452-153">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="35452-154">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="35452-154">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="35452-155">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="35452-155">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="35452-156">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="35452-156">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="35452-157">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="35452-157">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="35452-158">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="35452-158">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="35452-159">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="35452-159">get_ContainsFullScreenElement</span></span>](#get_containsfullscreenelement) | <span data-ttu-id="35452-160">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="35452-160">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="35452-161">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="35452-161">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="35452-162">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="35452-162">The title for the current top level document.</span></span>
[<span data-ttu-id="35452-163">get_Settings</span><span class="sxs-lookup"><span data-stu-id="35452-163">get_Settings</span></span>](#get_settings) | <span data-ttu-id="35452-164">[ICoreWebView2Settings](icorewebview2settings.md)对象包含运行的 web 视图的各种可修改设置。</span><span class="sxs-lookup"><span data-stu-id="35452-164">The [ICoreWebView2Settings](icorewebview2settings.md) object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="35452-165">get_Source</span><span class="sxs-lookup"><span data-stu-id="35452-165">get_Source</span></span>](#get_source) | <span data-ttu-id="35452-166">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="35452-166">The URI of the current top level document.</span></span>
[<span data-ttu-id="35452-167">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="35452-167">GetDevToolsProtocolEventReceiver</span></span>](#getdevtoolsprotocoleventreceiver) | <span data-ttu-id="35452-168">获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。</span><span class="sxs-lookup"><span data-stu-id="35452-168">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>
[<span data-ttu-id="35452-169">GoBack</span><span class="sxs-lookup"><span data-stu-id="35452-169">GoBack</span></span>](#goback) | <span data-ttu-id="35452-170">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="35452-170">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="35452-171">GoForward</span><span class="sxs-lookup"><span data-stu-id="35452-171">GoForward</span></span>](#goforward) | <span data-ttu-id="35452-172">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="35452-172">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="35452-173">导航</span><span class="sxs-lookup"><span data-stu-id="35452-173">Navigate</span></span>](#navigate) | <span data-ttu-id="35452-174">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="35452-174">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="35452-175">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="35452-175">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="35452-176">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="35452-176">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="35452-177">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="35452-177">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="35452-178">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="35452-178">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="35452-179">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="35452-179">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="35452-180">将指定的 webMessage 发布到此 Web 视图中的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="35452-180">Post the specified webMessage to the top level document in this WebView.</span></span>
[<span data-ttu-id="35452-181">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="35452-181">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="35452-182">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="35452-182">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="35452-183">重载</span><span class="sxs-lookup"><span data-stu-id="35452-183">Reload</span></span>](#reload) | <span data-ttu-id="35452-184">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="35452-184">Reload the current page.</span></span>
[<span data-ttu-id="35452-185">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="35452-185">remove_ContainsFullScreenElementChanged</span></span>](#remove_containsfullscreenelementchanged) | <span data-ttu-id="35452-186">删除以前使用 add_ContainsFullScreenElementChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-186">Remove an event handler previously added with add_ContainsFullScreenElementChanged.</span></span>
[<span data-ttu-id="35452-187">remove_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="35452-187">remove_ContentLoading</span></span>](#remove_contentloading) | <span data-ttu-id="35452-188">删除以前使用 add_ContentLoading 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-188">Remove an event handler previously added with add_ContentLoading.</span></span>
[<span data-ttu-id="35452-189">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="35452-189">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="35452-190">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-190">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="35452-191">remove_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-191">remove_FrameNavigationCompleted</span></span>](#remove_framenavigationcompleted) | <span data-ttu-id="35452-192">删除以前使用 add_FrameNavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-192">Remove an event handler previously added with add_FrameNavigationCompleted.</span></span>
[<span data-ttu-id="35452-193">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-193">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="35452-194">删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-194">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="35452-195">remove_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="35452-195">remove_HistoryChanged</span></span>](#remove_historychanged) | <span data-ttu-id="35452-196">删除以前使用 add_HistoryChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-196">Remove an event handler previously added with add_HistoryChanged.</span></span>
[<span data-ttu-id="35452-197">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-197">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="35452-198">删除以前使用 add_NavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-198">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="35452-199">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-199">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="35452-200">删除以前使用 add_NavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-200">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="35452-201">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="35452-201">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="35452-202">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-202">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="35452-203">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="35452-203">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="35452-204">删除以前使用 add_PermissionRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-204">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="35452-205">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="35452-205">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="35452-206">删除以前使用 add_ProcessFailed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-206">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="35452-207">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="35452-207">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="35452-208">删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-208">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="35452-209">remove_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="35452-209">remove_SourceChanged</span></span>](#remove_sourcechanged) | <span data-ttu-id="35452-210">删除以前使用 add_SourceChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-210">Remove an event handler previously added with add_SourceChanged.</span></span>
[<span data-ttu-id="35452-211">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="35452-211">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="35452-212">删除以前使用 add_WebMessageReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-212">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="35452-213">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="35452-213">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="35452-214">删除以前使用 add_WebResourceRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-214">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="35452-215">remove_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="35452-215">remove_WindowCloseRequested</span></span>](#remove_windowcloserequested) | <span data-ttu-id="35452-216">删除以前使用 add_WindowCloseRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-216">Remove an event handler previously added with add_WindowCloseRequested.</span></span>
[<span data-ttu-id="35452-217">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="35452-217">RemoveHostObjectFromScript</span></span>](#removehostobjectfromscript) | <span data-ttu-id="35452-218">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="35452-218">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="35452-219">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="35452-219">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="35452-220">删除使用指定脚本 id 添加的相应 JavaScript `AddScriptToExecuteOnDocumentCreated` 。</span><span class="sxs-lookup"><span data-stu-id="35452-220">Remove the corresponding JavaScript added using `AddScriptToExecuteOnDocumentCreated` with the specified script id.</span></span>
[<span data-ttu-id="35452-221">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="35452-221">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="35452-222">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="35452-222">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>
[<span data-ttu-id="35452-223">停止</span><span class="sxs-lookup"><span data-stu-id="35452-223">Stop</span></span>](#stop) | <span data-ttu-id="35452-224">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="35452-224">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="35452-225">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="35452-225">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#corewebview2_capture_preview_image_format) | <span data-ttu-id="35452-226">ICoreWebView2：： CapturePreview 方法使用的图像格式。</span><span class="sxs-lookup"><span data-stu-id="35452-226">Image format used by the ICoreWebView2::CapturePreview method.</span></span>
[<span data-ttu-id="35452-227">COREWEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-227">COREWEBVIEW2_KEY_EVENT_KIND</span></span>](#corewebview2_key_event_kind) | <span data-ttu-id="35452-228">触发 AcceleratorKeyPressed 事件的键事件的类型。</span><span class="sxs-lookup"><span data-stu-id="35452-228">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>
[<span data-ttu-id="35452-229">COREWEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="35452-229">COREWEBVIEW2_MOVE_FOCUS_REASON</span></span>](#corewebview2_move_focus_reason) | <span data-ttu-id="35452-230">移动焦点的原因。</span><span class="sxs-lookup"><span data-stu-id="35452-230">Reason for moving focus.</span></span>
[<span data-ttu-id="35452-231">COREWEBVIEW2_PERMISSION_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-231">COREWEBVIEW2_PERMISSION_KIND</span></span>](#corewebview2_permission_kind) | <span data-ttu-id="35452-232">权限请求的类型。</span><span class="sxs-lookup"><span data-stu-id="35452-232">The type of a permission request.</span></span>
[<span data-ttu-id="35452-233">COREWEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="35452-233">COREWEBVIEW2_PERMISSION_STATE</span></span>](#corewebview2_permission_state) | <span data-ttu-id="35452-234">对权限请求的响应。</span><span class="sxs-lookup"><span data-stu-id="35452-234">Response to a permission request.</span></span>
[<span data-ttu-id="35452-235">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="35452-235">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span></span>](#corewebview2_physical_key_status) | <span data-ttu-id="35452-236">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="35452-236">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>
[<span data-ttu-id="35452-237">COREWEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-237">COREWEBVIEW2_PROCESS_FAILED_KIND</span></span>](#corewebview2_process_failed_kind) | <span data-ttu-id="35452-238">ICoreWebView2ProcessFailedEventHandler 接口中使用的进程失败类型。</span><span class="sxs-lookup"><span data-stu-id="35452-238">Kind of process failure used in the ICoreWebView2ProcessFailedEventHandler interface.</span></span>
[<span data-ttu-id="35452-239">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-239">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#corewebview2_script_dialog_kind) | <span data-ttu-id="35452-240">ICoreWebView2ScriptDialogOpeningEventHandler 接口中使用的 JavaScript 对话框类型。</span><span class="sxs-lookup"><span data-stu-id="35452-240">Kind of JavaScript dialog used in the ICoreWebView2ScriptDialogOpeningEventHandler interface.</span></span>
[<span data-ttu-id="35452-241">COREWEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="35452-241">COREWEBVIEW2_WEB_ERROR_STATUS</span></span>](#corewebview2_web_error_status) | <span data-ttu-id="35452-242">Web 导航的错误状态值。</span><span class="sxs-lookup"><span data-stu-id="35452-242">Error status values for web navigations.</span></span>
[<span data-ttu-id="35452-243">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="35452-243">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#corewebview2_web_resource_context) | <span data-ttu-id="35452-244">Web 资源请求上下文的枚举。</span><span class="sxs-lookup"><span data-stu-id="35452-244">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="35452-245">成员</span><span class="sxs-lookup"><span data-stu-id="35452-245">Members</span></span>

#### <span data-ttu-id="35452-246">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="35452-246">add_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="35452-247">为 ContainsFullScreenElementChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-247">Add an event handler for the ContainsFullScreenElementChanged event.</span></span>

> <span data-ttu-id="35452-248">公共 HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged) ([ICoreWebView2ContainsFullScreenElementChangedEventHandler](icorewebview2containsfullscreenelementchangedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-248">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([ICoreWebView2ContainsFullScreenElementChangedEventHandler](icorewebview2containsfullscreenelementchangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-249">当 ContainsFullScreenElement 属性更改时，将触发 ContainsFullScreenElementChanged。</span><span class="sxs-lookup"><span data-stu-id="35452-249">ContainsFullScreenElementChanged fires when the ContainsFullScreenElement property changes.</span></span> <span data-ttu-id="35452-250">这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。</span><span class="sxs-lookup"><span data-stu-id="35452-250">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="35452-251">例如，当视频元素请求进入全屏时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="35452-251">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="35452-252">然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="35452-252">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

```cpp
    // Register a handler for the ContainsFullScreenChanged event.
    CHECK_FAILURE(m_webView->add_ContainsFullScreenElementChanged(
        Callback<ICoreWebView2ContainsFullScreenElementChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                if (m_fullScreenAllowed)
                {
                    CHECK_FAILURE(
                        sender->get_ContainsFullScreenElement(&m_containsFullscreenElement));
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

#### <span data-ttu-id="35452-253">add_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="35452-253">add_ContentLoading</span></span> 

<span data-ttu-id="35452-254">为 ContentLoading 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-254">Add an event handler for the ContentLoading event.</span></span>

> <span data-ttu-id="35452-255">公共 HRESULT [add_ContentLoading](#add_contentloading) ([ICoreWebView2ContentLoadingEventHandler](icorewebview2contentloadingeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-255">public HRESULT [add_ContentLoading](#add_contentloading)([ICoreWebView2ContentLoadingEventHandler](icorewebview2contentloadingeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-256">ContentLoading 在加载任何内容之前激发，包括通过 AddScriptToExecuteOnDocumentCreated 添加的脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-256">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="35452-257">如果发生相同的页面导航 (例如通过片段导航或 pushState 导航) ，将不会触发 ContentLoading。</span><span class="sxs-lookup"><span data-stu-id="35452-257">ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="35452-258">这将遵循 NavigationStarting 和 SourceChanged 事件，并在 HistoryChanged 和 NavigationCompleted 事件之前。</span><span class="sxs-lookup"><span data-stu-id="35452-258">This follows the NavigationStarting and SourceChanged events and precedes the HistoryChanged and NavigationCompleted events.</span></span>

#### <span data-ttu-id="35452-259">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="35452-259">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="35452-260">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-260">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="35452-261">公共 HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged) ([ICoreWebView2DocumentTitleChangedEventHandler](icorewebview2documenttitlechangedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-261">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([ICoreWebView2DocumentTitleChangedEventHandler](icorewebview2documenttitlechangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-262">当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，DocumentTitleChanged 会引发此事件。</span><span class="sxs-lookup"><span data-stu-id="35452-262">DocumentTitleChanged fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

```cpp
    // Register a handler for the DocumentTitleChanged event.
    // This handler just announces the new title on the window's title bar.
    CHECK_FAILURE(m_webView->add_DocumentTitleChanged(
        Callback<ICoreWebView2DocumentTitleChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                wil::unique_cotaskmem_string title;
                CHECK_FAILURE(sender->get_DocumentTitle(&title));
                SetWindowText(m_appWindow->GetMainWindow(), title.get());
                return S_OK;
            })
            .Get(),
        &m_documentTitleChangedToken));
```

#### <span data-ttu-id="35452-263">add_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-263">add_FrameNavigationCompleted</span></span> 

<span data-ttu-id="35452-264">为 FrameNavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-264">Add an event handler for the FrameNavigationCompleted event.</span></span>

> <span data-ttu-id="35452-265">公共 HRESULT [add_FrameNavigationCompleted](#add_framenavigationcompleted) ([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-265">public HRESULT [add_FrameNavigationCompleted](#add_framenavigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-266">当子框架已完全加载 (正文中时，FrameNavigationCompleted 引发) 或加载已停止，但出现错误。</span><span class="sxs-lookup"><span data-stu-id="35452-266">FrameNavigationCompleted fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

```cpp
    // Register a handler for the FrameNavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    CHECK_FAILURE(m_webView->add_FrameNavigationCompleted(
        Callback<ICoreWebView2NavigationCompletedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    COREWEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    std::wstring error_msg = WebErrorStatusToString(webErrorStatus);
                    MessageBox(nullptr,
                       (std::wstring(L"IFrame navigation failed with the ") +
                         L"give in error " + error_msg).c_str(),
                       L"Navigation Failure", MB_OK);
                    if (webErrorStatus == COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                return S_OK;
            })
            .Get(),
        &m_frameNavigationCompletedToken));
```

#### <span data-ttu-id="35452-267">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-267">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="35452-268">为 FrameNavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-268">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="35452-269">公共 HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting) ([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-269">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-270">当 Web 视图中的子框架请求导航到其他 URI 的权限时，将触发 FrameNavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="35452-270">FrameNavigationStarting fires when a child frame in the WebView requests permission to navigate to a different URI.</span></span> <span data-ttu-id="35452-271">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="35452-271">This will fire for redirects as well.</span></span>

<span data-ttu-id="35452-272">在事件处理程序返回之前，可以阻止相应的导航。</span><span class="sxs-lookup"><span data-stu-id="35452-272">Corresponding navigations can be blocked until the event handler returns.</span></span>

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));
        }
        return S_OK;
    }).Get(), &m_frameNavigationStartingToken));
```

#### <span data-ttu-id="35452-273">add_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="35452-273">add_HistoryChanged</span></span> 

<span data-ttu-id="35452-274">为 HistoryChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-274">Add an event handler for the HistoryChanged event.</span></span>

> <span data-ttu-id="35452-275">公共 HRESULT [add_HistoryChanged](#add_historychanged) ([ICoreWebView2HistoryChangedEventHandler](icorewebview2historychangedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-275">public HRESULT [add_HistoryChanged](#add_historychanged)([ICoreWebView2HistoryChangedEventHandler](icorewebview2historychangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-276">HistoryChanged 侦听顶级文档的导航历史记录更改。</span><span class="sxs-lookup"><span data-stu-id="35452-276">HistoryChanged listens to the change of navigation history for the top level document.</span></span> <span data-ttu-id="35452-277">使用 HistoryChanged 检查 CanGoBack/CanGoForward 值是否已更改。</span><span class="sxs-lookup"><span data-stu-id="35452-277">Use HistoryChanged to check if CanGoBack/CanGoForward value has changed.</span></span> <span data-ttu-id="35452-278">使用 GoBack/GoForward 时也会触发 HistoryChanged。</span><span class="sxs-lookup"><span data-stu-id="35452-278">HistoryChanged also fires for using GoBack/GoForward.</span></span> <span data-ttu-id="35452-279">HistoryChanged 在 SourceChanged 和 ContentLoading 后激发。</span><span class="sxs-lookup"><span data-stu-id="35452-279">HistoryChanged fires after SourceChanged and ContentLoading.</span></span>

```cpp
    // Register a handler for the HistoryChanged event.
    // Update the Back, Forward buttons.
    CHECK_FAILURE(m_webView->add_HistoryChanged(
        Callback<ICoreWebView2HistoryChangedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) -> HRESULT {
                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                m_toolbar->SetItemEnabled(Toolbar::Item_BackButton, canGoBack);
                m_toolbar->SetItemEnabled(Toolbar::Item_ForwardButton, canGoForward);

                return S_OK;
            })
            .Get(),
        &m_historyChangedToken));
```

#### <span data-ttu-id="35452-280">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-280">add_NavigationCompleted</span></span> 

<span data-ttu-id="35452-281">为 NavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-281">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="35452-282">公共 HRESULT [add_NavigationCompleted](#add_navigationcompleted) ([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-282">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](icorewebview2navigationcompletedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-283">当 Web 视图已完全加载 (正文时，NavigationCompleted 激发) 或加载时已停止，但出现错误。</span><span class="sxs-lookup"><span data-stu-id="35452-283">NavigationCompleted fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

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
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                m_toolbar->SetItemEnabled(Toolbar::Item_CancelButton, false);
                m_toolbar->SetItemEnabled(Toolbar::Item_ReloadButton, true);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### <span data-ttu-id="35452-284">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-284">add_NavigationStarting</span></span> 

<span data-ttu-id="35452-285">为 NavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-285">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="35452-286">公共 HRESULT [add_NavigationStarting](#add_navigationstarting) ([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-286">public HRESULT [add_NavigationStarting](#add_navigationstarting)([ICoreWebView2NavigationStartingEventHandler](icorewebview2navigationstartingeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-287">当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="35452-287">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="35452-288">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="35452-288">This will fire for redirects as well.</span></span>

<span data-ttu-id="35452-289">在事件处理程序返回之前，可以阻止相应的导航。</span><span class="sxs-lookup"><span data-stu-id="35452-289">Corresponding navigations can be blocked until the event handler returns.</span></span>

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<ICoreWebView2NavigationStartingEventHandler>(
            [this](ICoreWebView2* sender,
                   ICoreWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
        }
        // Changes to settings will apply at the next navigation, which includes the
        // navigation after a NavigationStarting event.  We can use this to change
        // settings according to what site we're visiting.
        if (ShouldBlockScriptForUri(uri.get()))
        {
            m_settings->put_IsScriptEnabled(FALSE);
        }
        else
        {
            m_settings->put_IsScriptEnabled(m_isScriptEnabled);
        }
        return S_OK;
    }).Get(), &m_navigationStartingToken));
```

#### <span data-ttu-id="35452-290">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="35452-290">add_NewWindowRequested</span></span> 

<span data-ttu-id="35452-291">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-291">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="35452-292">公共 HRESULT [add_NewWindowRequested](#add_newwindowrequested) ([ICoreWebView2NewWindowRequestedEventHandler](icorewebview2newwindowrequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-292">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([ICoreWebView2NewWindowRequestedEventHandler](icorewebview2newwindowrequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-293">当 Web 视图中的内容请求打开新窗口（如通过 window）时，将触发 Webview.newwindowrequested。</span><span class="sxs-lookup"><span data-stu-id="35452-293">NewWindowRequested fires when content inside the WebView requests to open a new window, such as through window.open.</span></span> <span data-ttu-id="35452-294">应用可以传递将被视为打开的窗口的目标 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="35452-294">The app can pass a target WebView that will be considered the opened window.</span></span>

<span data-ttu-id="35452-295">如果未在事件参数上获取延迟，则请求的新窗口可能会被阻止，直到事件处理程序返回。</span><span class="sxs-lookup"><span data-stu-id="35452-295">Scripts resulted in the new window requested can be blocked until the event handler returns if a deferral is not taken on the event args.</span></span> <span data-ttu-id="35452-296">如果采取延迟，将阻止脚本，直到完成延期。</span><span class="sxs-lookup"><span data-stu-id="35452-296">If a deferral is taken, then scripts are blocked until the deferral is completed.</span></span>

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<ICoreWebView2NewWindowRequestedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<ICoreWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));
                AppWindow* newAppWindow;

                wil::com_ptr<ICoreWebView2WindowFeatures> windowFeatures;
                CHECK_FAILURE(args->get_WindowFeatures(&windowFeatures));

                RECT windowRect = {0};
                UINT32 left = 0;
                UINT32 top = 0;
                UINT32 height = 0;
                UINT32 width = 0;
                BOOL shouldHaveToolbar = true;

                BOOL hasPosition = FALSE;
                BOOL hasSize = FALSE;
                CHECK_FAILURE(windowFeatures->HasPosition(&hasPosition));
                CHECK_FAILURE(windowFeatures->HasSize(&hasSize));

                bool useDefaultWindow = true;

                if (!!hasPosition && !!hasSize)
                {
                    CHECK_FAILURE(windowFeatures->get_Left(&left));
                    CHECK_FAILURE(windowFeatures->get_Top(&top));
                    CHECK_FAILURE(windowFeatures->get_Height(&height));
                    CHECK_FAILURE(windowFeatures->get_Width(&width));
                    useDefaultWindow = false;
                }
                CHECK_FAILURE(windowFeatures->get_Toolbar(&shouldHaveToolbar));

                windowRect.left = left;
                windowRect.right = left + (width < s_minNewWindowSize ? s_minNewWindowSize : width);
                windowRect.top = top;
                windowRect.bottom = top + (height < s_minNewWindowSize ? s_minNewWindowSize : height);

                if (!useDefaultWindow)
                {
                  newAppWindow = new AppWindow(m_creationModeId, L"", false, nullptr, true, windowRect, !!shouldHaveToolbar);
                }
                else
                {
                  newAppWindow = new AppWindow(m_creationModeId, L"");
                }
                newAppWindow->m_isPopupWindow = true;
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

#### <span data-ttu-id="35452-297">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="35452-297">add_PermissionRequested</span></span> 

<span data-ttu-id="35452-298">为 Webview.permissionrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-298">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="35452-299">公共 HRESULT [add_PermissionRequested](#add_permissionrequested) ([ICoreWebView2PermissionRequestedEventHandler](icorewebview2permissionrequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-299">public HRESULT [add_PermissionRequested](#add_permissionrequested)([ICoreWebView2PermissionRequestedEventHandler](icorewebview2permissionrequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-300">当 Web 视图中的内容请求访问某些特权资源的权限时，将触发 Webview.permissionrequested。</span><span class="sxs-lookup"><span data-stu-id="35452-300">PermissionRequested fires when content in a WebView requests permission to access some privileged resources.</span></span>

<span data-ttu-id="35452-301">如果未对事件参数执行延迟，则可以阻止后续脚本，直到事件处理程序返回。</span><span class="sxs-lookup"><span data-stu-id="35452-301">If a deferral is not taken on the event args, the subsequent scripts can be blocked until the event handler returns.</span></span> <span data-ttu-id="35452-302">如果采取延迟，将阻止脚本，直到完成延期。</span><span class="sxs-lookup"><span data-stu-id="35452-302">If a deferral is taken, then the scripts are blocked until the deferral is completed.</span></span>

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<ICoreWebView2PermissionRequestedEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        COREWEBVIEW2_PERMISSION_KIND kind = COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionKind(&kind));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionKind(kind);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        COREWEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? COREWEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? COREWEBVIEW2_PERMISSION_STATE_DENY
            :                     COREWEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### <span data-ttu-id="35452-303">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="35452-303">add_ProcessFailed</span></span> 

<span data-ttu-id="35452-304">为 ProcessFailed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-304">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="35452-305">公共 HRESULT [add_ProcessFailed](#add_processfailed) ([ICoreWebView2ProcessFailedEventHandler](icorewebview2processfailedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-305">public HRESULT [add_ProcessFailed](#add_processfailed)([ICoreWebView2ProcessFailedEventHandler](icorewebview2processfailedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-306">当 Web 视图进程意外终止或变得不响应时，ProcessFailed 将激发。</span><span class="sxs-lookup"><span data-stu-id="35452-306">ProcessFailed fires when a WebView process is terminated unexpectedly or becomes unresponsive.</span></span>

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<ICoreWebView2ProcessFailedEventHandler>(
            [this](ICoreWebView2* sender,
                ICoreWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        COREWEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser process exited unexpectedly.  Recreate webview?",
                L"Browser process exited",
                MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process has stopped responding.  Recreate webview?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                m_appWindow->ReinitializeWebView();
            }
        }
        else if (failureType == COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED)
        {
            int button = MessageBox(
                m_appWindow->GetMainWindow(),
                L"Browser render process exited unexpectedly. Reload page?",
                L"Web page unresponsive", MB_YESNO);
            if (button == IDYES)
            {
                CHECK_FAILURE(m_webView->Reload());
            }
        }
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### <span data-ttu-id="35452-307">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="35452-307">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="35452-308">为 ScriptDialogOpening 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-308">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="35452-309">公共 HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening) ([ICoreWebView2ScriptDialogOpeningEventHandler](icorewebview2scriptdialogopeningeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-309">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([ICoreWebView2ScriptDialogOpeningEventHandler](icorewebview2scriptdialogopeningeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-310">当将显示 web 视图的 JavaScript 对话框 (警报、确认、提示或 beforeunload) 时，将引发 ScriptDialogOpening。</span><span class="sxs-lookup"><span data-stu-id="35452-310">ScriptDialogOpening fires when a JavaScript dialog (alert, confirm, prompt, or beforeunload) will show for the webview.</span></span> <span data-ttu-id="35452-311">仅当 ICoreWebView2Settings：： AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发。</span><span class="sxs-lookup"><span data-stu-id="35452-311">This event only fires if the ICoreWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span> <span data-ttu-id="35452-312">ScriptDialogOpening 事件可用于取消对话框或使用自定义对话框替换默认对话框。</span><span class="sxs-lookup"><span data-stu-id="35452-312">The ScriptDialogOpening event can be used to suppress dialogs or replace default dialogs with custom dialogs.</span></span>

<span data-ttu-id="35452-313">如果未对事件参数执行延迟，则可以阻止后续脚本，直到事件处理程序返回。</span><span class="sxs-lookup"><span data-stu-id="35452-313">If a deferral is not taken on the event args, the subsequent scripts can be blocked until the event handler returns.</span></span> <span data-ttu-id="35452-314">如果采取延迟，将阻止脚本，直到完成延期。</span><span class="sxs-lookup"><span data-stu-id="35452-314">If a deferral is taken, then the scripts are blocked until the deferral is completed.</span></span>

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<ICoreWebView2ScriptDialogOpeningEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<ICoreWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            COREWEBVIEW2_SCRIPT_DIALOG_KIND type;
            wil::unique_cotaskmem_string message;
            wil::unique_cotaskmem_string defaultText;

            CHECK_FAILURE(eventArgs->get_Uri(&uri));
            CHECK_FAILURE(eventArgs->get_Kind(&type));
            CHECK_FAILURE(eventArgs->get_Message(&message));
            CHECK_FAILURE(eventArgs->get_DefaultText(&defaultText));

            std::wstring promptString = std::wstring(L"The page at '")
                + uri.get() + L"' says:";
            TextInputDialog dialog(
                m_appWindow->GetMainWindow(),
                L"Script Dialog",
                promptString.c_str(),
                message.get(),
                defaultText.get(),
                /* readonly */ type != COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<ICoreWebView2Deferral> deferral;
            CHECK_FAILURE(args->GetDeferral(&deferral));
            m_completeDeferredDialog = [showDialog, deferral]
            {
                showDialog();
                CHECK_FAILURE(deferral->Complete());
            };
        }
        else
        {
            showDialog();
        }

        return S_OK;
    }).Get(), &m_scriptDialogOpeningToken));
```

#### <span data-ttu-id="35452-315">add_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="35452-315">add_SourceChanged</span></span> 

<span data-ttu-id="35452-316">为 SourceChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-316">Add an event handler for the SourceChanged event.</span></span>

> <span data-ttu-id="35452-317">公共 HRESULT [add_SourceChanged](#add_sourcechanged) ([ICoreWebView2SourceChangedEventHandler](icorewebview2sourcechangedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-317">public HRESULT [add_SourceChanged](#add_sourcechanged)([ICoreWebView2SourceChangedEventHandler](icorewebview2sourcechangedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-318">Source 属性更改时将触发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="35452-318">SourceChanged fires when the Source property changes.</span></span> <span data-ttu-id="35452-319">导航到其他网站或片段导航时，将引发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="35452-319">SourceChanged fires for navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="35452-320">不会为其他类型的导航（如页面重新加载或 pushState 与当前页面相同的 URL）触发。</span><span class="sxs-lookup"><span data-stu-id="35452-320">It will not fire for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span> <span data-ttu-id="35452-321">SourceChanged 将在 ContentLoading 之前激发，以便导航到新文档。</span><span class="sxs-lookup"><span data-stu-id="35452-321">SourceChanged fires before ContentLoading for navigation to a new document.</span></span>

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(GetAddressBar(), uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### <span data-ttu-id="35452-322">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="35452-322">add_WebMessageReceived</span></span> 

<span data-ttu-id="35452-323">为 WebMessageReceived 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-323">Add an event handler for the WebMessageReceived event.</span></span>

> <span data-ttu-id="35452-324">公共 HRESULT [add_WebMessageReceived](#add_webmessagereceived) ([ICoreWebView2WebMessageReceivedEventHandler](icorewebview2webmessagereceivedeventhandler.md) \* 处理程序、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-324">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([ICoreWebView2WebMessageReceivedEventHandler](icorewebview2webmessagereceivedeventhandler.md) \* handler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-325">当设置 ICoreWebView2Settings：： IsWebMessageEnabled 设置和 Web 视图调用的顶级文档时，将触发 WebMessageReceived `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="35452-325">WebMessageReceived fires when the ICoreWebView2Settings::IsWebMessageEnabled setting is set and the top level document of the WebView calls `window.chrome.webview.postMessage`.</span></span> <span data-ttu-id="35452-326">PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。</span><span class="sxs-lookup"><span data-stu-id="35452-326">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

```html
        window.chrome.webview.addEventListener('message', arg => {
            if ("SetColor" in arg.data) {
                document.getElementById("colorable").style.color = arg.data.SetColor;
            }
            if ("WindowBounds" in arg.data) {
                document.getElementById("window-bounds").value = arg.data.WindowBounds;
            }
        });

        function SetTitleText() {
            let titleText = document.getElementById("title-text");
            window.chrome.webview.postMessage(`SetTitleText ${titleText.value}`);
        }
        function GetWindowBounds() {
            window.chrome.webview.postMessage("GetWindowBounds");
        }
```
 <span data-ttu-id="35452-327">调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 对象参数调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-327">When postMessage is called, the handler's Invoke method will be called with the postMessage's object parameter converted to a JSON string.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### <span data-ttu-id="35452-328">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="35452-328">add_WebResourceRequested</span></span> 

<span data-ttu-id="35452-329">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-329">Add an event handler for the WebResourceRequested event.</span></span>

> <span data-ttu-id="35452-330">公共 HRESULT [add_WebResourceRequested](#add_webresourcerequested) ([ICoreWebView2WebResourceRequestedEventHandler](icorewebview2webresourcerequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-330">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)([ICoreWebView2WebResourceRequestedEventHandler](icorewebview2webresourcerequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-331">当 Web 视图正在对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 URL 请求时，将触发 WebResourceRequested。</span><span class="sxs-lookup"><span data-stu-id="35452-331">WebResourceRequested fires when the WebView is performing a URL request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span> <span data-ttu-id="35452-332">必须至少添加一个筛选器，才能触发该事件。</span><span class="sxs-lookup"><span data-stu-id="35452-332">At least one filter must be added for the event to fire.</span></span>

<span data-ttu-id="35452-333">请求的 web 资源可以在事件处理程序返回之前被阻止，直到未对事件参数执行延迟。</span><span class="sxs-lookup"><span data-stu-id="35452-333">The web resource requested can be blocked until the event handler returns if a deferral is not taken on the event args.</span></span> <span data-ttu-id="35452-334">如果获取延迟，则将阻止请求的 web 资源，直到延期完成。</span><span class="sxs-lookup"><span data-stu-id="35452-334">If a deferral is taken, then the web resource requested is blocked until the deferral is completed.</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        COREWEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
                        {
                            return E_INVALIDARG;
                        }
                        // Override the response with an empty one to block the image.
                        // If put_Response is not called, the request will continue as normal.
                        wil::com_ptr<ICoreWebView2WebResourceResponse> response;
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

#### <span data-ttu-id="35452-335">add_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="35452-335">add_WindowCloseRequested</span></span> 

<span data-ttu-id="35452-336">为 WindowCloseRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-336">Add an event handler for the WindowCloseRequested event.</span></span>

> <span data-ttu-id="35452-337">公共 HRESULT [add_WindowCloseRequested](#add_windowcloserequested) ([ICoreWebView2WindowCloseRequestedEventHandler](icorewebview2windowcloserequestedeventhandler.md) \* eventHandler、EventRegistrationToken \* 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-337">public HRESULT [add_WindowCloseRequested](#add_windowcloserequested)([ICoreWebView2WindowCloseRequestedEventHandler](icorewebview2windowcloserequestedeventhandler.md) \* eventHandler, EventRegistrationToken \* token)</span></span>

<span data-ttu-id="35452-338">当 Web 视图中的内容请求关闭窗口时（例如，在窗口后关闭窗口）时，将触发 WindowCloseRequested。调用 close。</span><span class="sxs-lookup"><span data-stu-id="35452-338">WindowCloseRequested fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span> <span data-ttu-id="35452-339">如果应用程序有意义，则应用应关闭 Web 视图和相关应用窗口。</span><span class="sxs-lookup"><span data-stu-id="35452-339">The app should close the WebView and related app window if that makes sense to the app.</span></span>

```cpp
    // Register a handler for the WindowCloseRequested event.
    // This handler will close the app window if it is not the main window.
    CHECK_FAILURE(m_webView->add_WindowCloseRequested(
        Callback<ICoreWebView2WindowCloseRequestedEventHandler>([this](
                                                                    ICoreWebView2* sender,
                                                                    IUnknown* args) {
            if (m_isPopupWindow)
            {
                CloseAppWindow();
            }
            return S_OK;
        }).Get(),
        nullptr));
```

#### <span data-ttu-id="35452-340">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="35452-340">AddHostObjectToScript</span></span> 

<span data-ttu-id="35452-341">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-341">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="35452-342">public HRESULT [AddHostObjectToScript](#addhostobjecttoscript) (LPCWSTR NAME，VARIANT \* object) </span><span class="sxs-lookup"><span data-stu-id="35452-342">public HRESULT [AddHostObjectToScript](#addhostobjecttoscript)(LPCWSTR name, VARIANT \* object)</span></span>

<span data-ttu-id="35452-343">主机对象通过来公开为主机对象代理 `window.chrome.webview.hostObjects.<name>` 。</span><span class="sxs-lookup"><span data-stu-id="35452-343">Host objects are exposed as host object proxies via `window.chrome.webview.hostObjects.<name>`.</span></span> <span data-ttu-id="35452-344">主机对象代理承诺并将解析为表示主机对象的对象。</span><span class="sxs-lookup"><span data-stu-id="35452-344">Host object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="35452-345">如果应用未添加具有名称的对象，则该承诺将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="35452-345">The promise is rejected if the app has not added an object with the name.</span></span> <span data-ttu-id="35452-346">当 JavaScript 代码访问对象的属性或方法时，承诺将返回，它将解析为属性或方法从主机返回的值，或者在出现错误时被拒绝，例如在对象上没有此类属性或参数无效的情况下被拒绝。</span><span class="sxs-lookup"><span data-stu-id="35452-346">When JavaScript code access a property or method of the object, a promise is return, which will resolve to the value returned from the host for the property or method, or rejected in case of error such as there is no such property or method on the object or parameters are invalid.</span></span> <span data-ttu-id="35452-347">例如，当应用程序代码执行以下操作时：</span><span class="sxs-lookup"><span data-stu-id="35452-347">For example, when the application code does the following:</span></span>

```
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddHostObjectToScript(L"host_object", &host);
```

<span data-ttu-id="35452-348">Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法：</span><span class="sxs-lookup"><span data-stu-id="35452-348">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span>

```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

<span data-ttu-id="35452-349">请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。</span><span class="sxs-lookup"><span data-stu-id="35452-349">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="35452-350">远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。</span><span class="sxs-lookup"><span data-stu-id="35452-350">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="35452-351">可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。</span><span class="sxs-lookup"><span data-stu-id="35452-351">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="35452-352">嵌套数组的支持深度为3。</span><span class="sxs-lookup"><span data-stu-id="35452-352">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="35452-353">不支持按引用类型的数组。</span><span class="sxs-lookup"><span data-stu-id="35452-353">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="35452-354">VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="35452-354">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="35452-355">在 JavaScript null 中，未定义映射到 VT_EMPTY。</span><span class="sxs-lookup"><span data-stu-id="35452-355">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="35452-356">此外，所有主机对象都公开为 `window.chrome.webview.hostObjects.sync.<name>` 。</span><span class="sxs-lookup"><span data-stu-id="35452-356">Additionally, all host objects are exposed as `window.chrome.webview.hostObjects.sync.<name>`.</span></span> <span data-ttu-id="35452-357">此处，主机对象作为同步主机对象代理公开。</span><span class="sxs-lookup"><span data-stu-id="35452-357">Here the host objects are exposed as synchronous host object proxies.</span></span> <span data-ttu-id="35452-358">这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。</span><span class="sxs-lookup"><span data-stu-id="35452-358">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="35452-359">因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.hostObjects.<name>` API。</span><span class="sxs-lookup"><span data-stu-id="35452-359">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.hostObjects.<name>` API described above.</span></span>

<span data-ttu-id="35452-360">同步主机对象代理和异步主机对象代理都可以代理相同的主机对象。</span><span class="sxs-lookup"><span data-stu-id="35452-360">Synchronous host object proxies and asynchronous host object proxies can both proxy the same host object.</span></span> <span data-ttu-id="35452-361">一个代理所做的远程更改将反映在同一主机对象的任何其他代理中，无论其他代理和同步还是异步。</span><span class="sxs-lookup"><span data-stu-id="35452-361">Remote changes made by one proxy will be reflected in any other proxy of that same host object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="35452-362">虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="35452-362">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="35452-363">尝试执行此操作将失败，并 HRESULT_FROM_WIN32 (ERROR_POSSIBLE_DEADLOCK) 。</span><span class="sxs-lookup"><span data-stu-id="35452-363">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="35452-364">主机对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。</span><span class="sxs-lookup"><span data-stu-id="35452-364">Host object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="35452-365">作为函数或对象原型一部分的属性或方法在本地运行。</span><span class="sxs-lookup"><span data-stu-id="35452-365">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="35452-366">此外，数组中的任何属性或方法 `chrome.webview.hostObjects.options.forceLocalProperties` 也将在本地运行。</span><span class="sxs-lookup"><span data-stu-id="35452-366">Additionally any property or method in the array `chrome.webview.hostObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="35452-367">这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。</span><span class="sxs-lookup"><span data-stu-id="35452-367">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="35452-368">你可以根据需要向此数组添加更多。</span><span class="sxs-lookup"><span data-stu-id="35452-368">You can add more to this array as required.</span></span>

<span data-ttu-id="35452-369">有一种方法 `chrome.webview.hostObjects.cleanupSome` 可以最大努力垃圾回收主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="35452-369">There's a method `chrome.webview.hostObjects.cleanupSome` that will best effort garbage collect host object proxies.</span></span>

<span data-ttu-id="35452-370">宿主对象代理还具有以下可在本地运行的方法：</span><span class="sxs-lookup"><span data-stu-id="35452-370">Host object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="35452-371">applyHostFunction、getHostProperty、setHostProperty：对主机对象执行方法调用、属性获取或属性设置。</span><span class="sxs-lookup"><span data-stu-id="35452-371">applyHostFunction, getHostProperty, setHostProperty: Perform a method invocation, property get, or property set on the host object.</span></span> <span data-ttu-id="35452-372">如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。</span><span class="sxs-lookup"><span data-stu-id="35452-372">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="35452-373">例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-373">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="35452-374">而 `proxy.applyHostFunction('toString')` `toString` 是在主机代理对象上运行。</span><span class="sxs-lookup"><span data-stu-id="35452-374">But `proxy.applyHostFunction('toString')` runs `toString` on the host proxied object instead.</span></span>

* <span data-ttu-id="35452-375">getLocalProperty、setLocalProperty：执行属性 get 或本地设置属性。</span><span class="sxs-lookup"><span data-stu-id="35452-375">getLocalProperty, setLocalProperty: Perform property get, or property set locally.</span></span> <span data-ttu-id="35452-376">你可以使用这些方法强制获取或设置主机对象代理本身的属性，而不是它所表示的主机对象上的属性。</span><span class="sxs-lookup"><span data-stu-id="35452-376">You can use these methods to force getting or setting a property on the host object proxy itself rather than on the host object it represents.</span></span> <span data-ttu-id="35452-377">例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从 host 代理对象命名的属性。</span><span class="sxs-lookup"><span data-stu-id="35452-377">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the host proxied object.</span></span> <span data-ttu-id="35452-378">但 `proxy.getLocalProperty('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。</span><span class="sxs-lookup"><span data-stu-id="35452-378">But `proxy.getLocalProperty('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="35452-379">同步：异步主机对象代理公开同步方法，该方法可为同一主机对象的同步主机对象代理返回承诺。</span><span class="sxs-lookup"><span data-stu-id="35452-379">sync: Asynchronous host object proxies expose a sync method which returns a promise for a synchronous host object proxy for the same host object.</span></span> <span data-ttu-id="35452-380">例如， `chrome.webview.hostObjects.sample.methodCall()` 返回一个异步主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="35452-380">For example, `chrome.webview.hostObjects.sample.methodCall()` returns an asynchronous host object proxy.</span></span> <span data-ttu-id="35452-381">可以 `sync` 改为使用该方法获取同步主机对象代理：</span><span class="sxs-lookup"><span data-stu-id="35452-381">You can use the `sync` method to obtain a synchronous host object proxy instead:</span></span> `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* <span data-ttu-id="35452-382">异步：同步主机对象代理公开一个 async 方法，该方法会阻止并返回同一主机对象的异步主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="35452-382">async: Synchronous host object proxies expose an async method which blocks and returns an asynchronous host object proxy for the same host object.</span></span> <span data-ttu-id="35452-383">例如， `chrome.webview.hostObjects.sync.sample.methodCall()` 返回同步主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="35452-383">For example, `chrome.webview.hostObjects.sync.sample.methodCall()` returns a synchronous host object proxy.</span></span> <span data-ttu-id="35452-384">`async`在此块上调用该方法，然后返回同一 host 对象的异步主机对象代理：</span><span class="sxs-lookup"><span data-stu-id="35452-384">Calling the `async` method on this blocks and then returns an asynchronous host object proxy for the same host object:</span></span> `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="35452-385">然后：异步主机对象代理具有 then 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-385">then: Asynchronous host object proxies have a then method.</span></span> <span data-ttu-id="35452-386">这使它们能够可等待。</span><span class="sxs-lookup"><span data-stu-id="35452-386">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="35452-387">将返回通过主机对象的表示形式解析的承诺。</span><span class="sxs-lookup"><span data-stu-id="35452-387">will return a promise that resolves with a representation of the host object.</span></span> <span data-ttu-id="35452-388">如果代理表示 JavaScript 文本，则会在本地返回一个副本。</span><span class="sxs-lookup"><span data-stu-id="35452-388">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="35452-389">如果代理表示一个函数，则返回非可等待代理。</span><span class="sxs-lookup"><span data-stu-id="35452-389">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="35452-390">如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为主机对象代理返回该对象的副本。</span><span class="sxs-lookup"><span data-stu-id="35452-390">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as host object proxies.</span></span>

<span data-ttu-id="35452-391">除了上述远程对象代理方法、forceLocalProperties 列表以及函数和对象原型) 上的属性之外，其他所有属性和方法 (调用都将远程运行。</span><span class="sxs-lookup"><span data-stu-id="35452-391">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="35452-392">异步主机对象代理返回表示异步完成远程调用该方法或获取属性的一种承诺。</span><span class="sxs-lookup"><span data-stu-id="35452-392">Asynchronous host object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="35452-393">在远程操作完成后，承诺将解决该操作的结果值。</span><span class="sxs-lookup"><span data-stu-id="35452-393">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="35452-394">同步主机对象代理的工作方式类似，但阻止了 JavaScript 执行，并等待远程操作完成。</span><span class="sxs-lookup"><span data-stu-id="35452-394">Synchronous host object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="35452-395">在异步主机对象代理上设置属性的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="35452-395">Setting a property on an asynchronous host object proxy works slightly differently.</span></span> <span data-ttu-id="35452-396">Set 将立即返回，返回值为将设置的值。</span><span class="sxs-lookup"><span data-stu-id="35452-396">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="35452-397">这是 JavaScript 代理对象的要求。</span><span class="sxs-lookup"><span data-stu-id="35452-397">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="35452-398">如果需要异步等待属性设置为 "完成"，请使用 setHostProperty 方法，该方法将返回上述承诺。</span><span class="sxs-lookup"><span data-stu-id="35452-398">If you need to asynchronously wait for the property set to complete, use the setHostProperty method which returns a promise as described above.</span></span> <span data-ttu-id="35452-399">同步对象属性 set 属性在设置该属性之前同步地阻止。</span><span class="sxs-lookup"><span data-stu-id="35452-399">Synchronous object property set property synchronously blocks until the property is set.</span></span>

<span data-ttu-id="35452-400">例如，假设你有一个具有以下接口的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="35452-400">For example, suppose you have a COM object with the following interface</span></span>

```idl
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IHostObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        [propget] HRESULT IndexedProperty(INT index, [out, retval] BSTR * stringResult);
        [propput] HRESULT IndexedProperty(INT index, [in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);

    };
```
 <span data-ttu-id="35452-401">我们可以将此接口的实例添加到我们的 JavaScript 中 `AddHostObjectToScript` 。</span><span class="sxs-lookup"><span data-stu-id="35452-401">We can add an instance of this interface into our JavaScript with `AddHostObjectToScript`.</span></span> <span data-ttu-id="35452-402">在这种情况下，我们将其命名 `sample` 为：</span><span class="sxs-lookup"><span data-stu-id="35452-402">In this case we name it `sample`:</span></span>

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_hostObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddHostObjectToScript multiple times in a row without
            // calling RemoveHostObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(
                m_webView->AddHostObjectToScript(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```
 <span data-ttu-id="35452-403">然后，在 HTML 文档中，我们可以通过以下方式使用该 COM 对象 `chrome.webview.hostObjects.sample` ：</span><span class="sxs-lookup"><span data-stu-id="35452-403">Then in the HTML document we can use this COM object via `chrome.webview.hostObjects.sample`:</span></span>

```html
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
        const propertyValue = await chrome.webview.hostObjects.sample.property;
        document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
        const propertyValue = chrome.webview.hostObjects.sync.sample.property;
        document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
        const propertyValue = document.getElementById("setPropertyAsyncInput").value;
        // The following line will work but it will return immediately before the property value has actually been set.
        // If you need to set the property and wait for the property to change value, use the setHostProperty function.
        chrome.webview.hostObjects.sample.property = propertyValue;
        document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
        const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
        // If you care about waiting until the property has actually changed value use the setHostProperty function.
        await chrome.webview.hostObjects.sample.setHostProperty("property", propertyValue);
        document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
        const propertyValue = document.getElementById("setPropertySyncInput").value;
        chrome.webview.hostObjects.sync.sample.property = propertyValue;
        document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("getIndexedPropertyAsyncButton").addEventListener("click", async () => {
        const index = parseInt(document.getElementById("getIndexedPropertyAsyncParam").value);
        const resultValue = await chrome.webview.hostObjects.sample.IndexedProperty[index];
        document.getElementById("getIndexedPropertyAsyncOutput").textContent = resultValue;
        });
        document.getElementById("setIndexedPropertyAsyncButton").addEventListener("click", async () => {
        const index = parseInt(document.getElementById("setIndexedPropertyAsyncParam1").value);
        const value = document.getElementById("setIndexedPropertyAsyncParam2").value;;
        chrome.webview.hostObjects.sample.IndexedProperty[index] = value;
        document.getElementById("setIndexedPropertyAsyncOutput").textContent = "Set";
        });
        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
        const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
        const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
        const resultValue = await chrome.webview.hostObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
        document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
        const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
        const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
        const resultValue = chrome.webview.hostObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
        document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
        chrome.webview.hostObjects.sample.CallCallbackAsynchronously(() => {
        document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
        });
        });
```
<span data-ttu-id="35452-404">向脚本公开主机对象有安全风险。</span><span class="sxs-lookup"><span data-stu-id="35452-404">Exposing host objects to script has security risk.</span></span> <span data-ttu-id="35452-405">请遵循 [最佳做法](https://docs.microsoft.com/microsoft-edge/webview2/concepts/security)。</span><span class="sxs-lookup"><span data-stu-id="35452-405">Please follow [best practices](https://docs.microsoft.com/microsoft-edge/webview2/concepts/security).</span></span>

#### <span data-ttu-id="35452-406">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="35452-406">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="35452-407">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="35452-407">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="35452-408">公共的 HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated) (LPCWSTR JavaScript、 [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="35452-408">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript, [ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](icorewebview2addscripttoexecuteondocumentcreatedcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="35452-409">此方法会插入一个在所有顶级文档和子框架页面导航上运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-409">This method injects a script that runs on all top-level document and child frame page navigations.</span></span> <span data-ttu-id="35452-410">此方法异步运行，并且你必须等待完成处理程序完成，然后才可以运行插入的脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-410">This method runs asynchronously, and you must wait for the completion handler to finish before the injected script is ready to run.</span></span> <span data-ttu-id="35452-411">此方法完成后，将 `Invoke` 通过 `id` 插入的脚本调用处理程序的方法。</span><span class="sxs-lookup"><span data-stu-id="35452-411">When this method completes, the handler's `Invoke` method is called with the `id` of the injected script.</span></span> `id` <span data-ttu-id="35452-412">是字符串。</span><span class="sxs-lookup"><span data-stu-id="35452-412">is a string.</span></span> <span data-ttu-id="35452-413">若要删除插入的脚本，请使用 `RemoveScriptToExecuteOnDocumentCreated` 。</span><span class="sxs-lookup"><span data-stu-id="35452-413">To remove the injected script, use `RemoveScriptToExecuteOnDocumentCreated`.</span></span>

<span data-ttu-id="35452-414">请注意，如果 HTML 文档通过 [沙盒](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) 属性或 [内容安全策略 HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) 进行了某种类型的沙盒，则会影响在此处运行脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-414">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="35452-415">例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。</span><span class="sxs-lookup"><span data-stu-id="35452-415">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

```cpp
// Prompt the user for some script and register it to execute whenever a new page loads.
void ScriptComponent::AddInitializeScript()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Add Initialize Script",
        L"Initialization Script:",
        L"Enter the JavaScript code to run as the initialization script that "
            L"runs before any script in the HTML document.",
    // This example script stops child frames from opening new windows.  Because
    // the initialization script runs before any script in the HTML document, we
    // can trust the results of our checks on window.parent and window.top.
        L"if (window.parent !== window.top) {\r\n"
        L"    delete window.open;\r\n"
        L"}");
    if (dialog.confirmed)
    {
        m_webView->AddScriptToExecuteOnDocumentCreated(
            dialog.input.c_str(),
            Callback<ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### <span data-ttu-id="35452-416">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="35452-416">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="35452-417">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="35452-417">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="35452-418">公共 HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter) (LPCWSTR const uri， [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext) </span><span class="sxs-lookup"><span data-stu-id="35452-418">public HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri, [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="35452-419">URI 参数可以是 ( "\*" 的通配符字符串：零或更多，'？ '：正好是一个) 。</span><span class="sxs-lookup"><span data-stu-id="35452-419">The URI parameter can be a wildcard string ('\*': zero or more, '?': exactly one).</span></span> <span data-ttu-id="35452-420">nullptr 等效于 L ""。</span><span class="sxs-lookup"><span data-stu-id="35452-420">nullptr is equivalent to L"".</span></span> <span data-ttu-id="35452-421">有关资源上下文筛选器的说明，请参阅 COREWEBVIEW2_WEB_RESOURCE_CONTEXT enum。</span><span class="sxs-lookup"><span data-stu-id="35452-421">See COREWEBVIEW2_WEB_RESOURCE_CONTEXT enum for description of resource context filters.</span></span>

#### <span data-ttu-id="35452-422">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="35452-422">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="35452-423">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-423">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="35452-424">公共 HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod) (LPCWSTR 方法、LPCWSTR ParametersAsJson、 [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](icorewebview2calldevtoolsprotocolmethodcompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="35452-424">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName, LPCWSTR parametersAsJson, [ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](icorewebview2calldevtoolsprotocolmethodcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="35452-425">有关可用方法的列表和说明，请参阅 [DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs) 。</span><span class="sxs-lookup"><span data-stu-id="35452-425">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="35452-426">"方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="35452-426">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="35452-427">ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。</span><span class="sxs-lookup"><span data-stu-id="35452-427">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="35452-428">当方法异步完成时，将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-428">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="35452-429">将使用方法的返回对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="35452-429">Invoke will be called with the method's return object as a JSON string.</span></span>

```cpp
// Prompt the user for the name and parameters of a CDP method, then call it.
void ScriptComponent::CallCdpMethod()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Call CDP Method",
        L"CDP method name:",
        L"Enter the CDP method name to call, followed by a space,\r\n"
            L"followed by the parameters in JSON format.",
        L"Runtime.evaluate {\"expression\":\"alert(\\\"test\\\")\"}");
    if (dialog.confirmed)
    {
        size_t delimiterPos = dialog.input.find(L' ');
        std::wstring methodName = dialog.input.substr(0, delimiterPos);
        std::wstring methodParams =
            (delimiterPos < dialog.input.size()
                ? dialog.input.substr(delimiterPos + 1)
                : L"{}");

        m_webView->CallDevToolsProtocolMethod(
            methodName.c_str(),
            methodParams.c_str(),
            Callback<ICoreWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### <span data-ttu-id="35452-430">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="35452-430">CapturePreview</span></span> 

<span data-ttu-id="35452-431">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="35452-431">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="35452-432">公共的 HRESULT [CapturePreview](#capturepreview) ([COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format) ImageFormat、IStream \* imageStream、 [ICoreWebView2CapturePreviewCompletedHandler](icorewebview2capturepreviewcompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="35452-432">public HRESULT [CapturePreview](#capturepreview)([COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format) imageFormat, IStream \* imageStream, [ICoreWebView2CapturePreviewCompletedHandler](icorewebview2capturepreviewcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="35452-433">指定具有 imageFormat 参数的图像的格式。</span><span class="sxs-lookup"><span data-stu-id="35452-433">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="35452-434">生成的图像二进制数据将写入所提供的 imageStream 参数。</span><span class="sxs-lookup"><span data-stu-id="35452-434">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="35452-435">当 CapturePreview 完成写入流时，将调用所提供的处理程序参数上的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-435">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

```cpp
// Show the user a file selection dialog, then save a screenshot of the WebView
// to the selected file.
void FileComponent::SaveScreenshot()
{
    OPENFILENAME openFileName = {};
    openFileName.lStructSize = sizeof(openFileName);
    openFileName.hwndOwner = nullptr;
    openFileName.hInstance = nullptr;
    WCHAR fileName[MAX_PATH] = L"WebView2_Screenshot.png";
    openFileName.lpstrFile = fileName;
    openFileName.lpstrFilter = L"PNG File\0*.png\0";
    openFileName.nMaxFile = ARRAYSIZE(fileName);
    openFileName.Flags = OFN_OVERWRITEPROMPT;

    if (GetSaveFileName(&openFileName))
    {
        wil::com_ptr<IStream> stream;
        CHECK_FAILURE(SHCreateStreamOnFileEx(
            fileName, STGM_READWRITE | STGM_CREATE, FILE_ATTRIBUTE_NORMAL, TRUE, nullptr,
            &stream));

        HWND mainWindow = m_appWindow->GetMainWindow();

        CHECK_FAILURE(m_webView->CapturePreview(
            COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<ICoreWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### <span data-ttu-id="35452-436">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="35452-436">ExecuteScript</span></span> 

<span data-ttu-id="35452-437">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="35452-437">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="35452-438">公共的 HRESULT [ExecuteScript](#executescript) (LPCWSTR JavaScript、 [ICoreWebView2ExecuteScriptCompletedHandler](icorewebview2executescriptcompletedhandler.md) \* 处理程序) </span><span class="sxs-lookup"><span data-stu-id="35452-438">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript, [ICoreWebView2ExecuteScriptCompletedHandler](icorewebview2executescriptcompletedhandler.md) \* handler)</span></span>

<span data-ttu-id="35452-439">这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="35452-439">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="35452-440">结果值是一个 JSON 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="35452-440">The result value is a JSON encoded string.</span></span> <span data-ttu-id="35452-441">如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。</span><span class="sxs-lookup"><span data-stu-id="35452-441">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="35452-442">请注意，没有显式返回值的函数将返回 undefined。</span><span class="sxs-lookup"><span data-stu-id="35452-442">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="35452-443">如果执行的脚本引发了未处理的异常，则结果也为 "null"。</span><span class="sxs-lookup"><span data-stu-id="35452-443">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="35452-444">此方法是异步应用的。</span><span class="sxs-lookup"><span data-stu-id="35452-444">This method is applied asynchronously.</span></span> <span data-ttu-id="35452-445">如果在导航过程中 NavigationStarting 事件后调用该方法，则会在加载新文档时在新文档中执行该脚本，同时引发 ContentLoading。</span><span class="sxs-lookup"><span data-stu-id="35452-445">If the method is called after NavigationStarting event during a navigation, the script will be executed in the new document when loading it, around the time ContentLoading is fired.</span></span> <span data-ttu-id="35452-446">即使 ICoreWebView2Settings：： IsScriptEnabled 设置为 FALSE，ExecuteScript 也可以正常工作。</span><span class="sxs-lookup"><span data-stu-id="35452-446">ExecuteScript will work even if ICoreWebView2Settings::IsScriptEnabled is set to FALSE.</span></span>

```cpp
// Prompt the user for some script and then execute it.
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

#### <span data-ttu-id="35452-447">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="35452-447">get_BrowserProcessId</span></span> 

<span data-ttu-id="35452-448">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="35452-448">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="35452-449">公共 HRESULT [get_BrowserProcessId](#get_browserprocessid) (UINT32 \* 值) </span><span class="sxs-lookup"><span data-stu-id="35452-449">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="35452-450">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="35452-450">get_CanGoBack</span></span> 

<span data-ttu-id="35452-451">如果 Web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="35452-451">Returns true if the WebView can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="35452-452">公共 HRESULT [get_CanGoBack](#get_cangoback) (BOOL \* CanGoBack) </span><span class="sxs-lookup"><span data-stu-id="35452-452">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="35452-453">如果 CanGoBack 更改值，将引发 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="35452-453">The HistoryChanged event will fire if CanGoBack changes value.</span></span>

#### <span data-ttu-id="35452-454">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="35452-454">get_CanGoForward</span></span> 

<span data-ttu-id="35452-455">如果 Web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="35452-455">Returns true if the WebView can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="35452-456">公共 HRESULT [get_CanGoForward](#get_cangoforward) (BOOL \* CanGoForward) </span><span class="sxs-lookup"><span data-stu-id="35452-456">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="35452-457">如果 CanGoForward 更改值，将引发 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="35452-457">The HistoryChanged event will fire if CanGoForward changes value.</span></span>

#### <span data-ttu-id="35452-458">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="35452-458">get_ContainsFullScreenElement</span></span> 

<span data-ttu-id="35452-459">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="35452-459">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="35452-460">公共 HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement) (BOOL \* ContainsFullScreenElement) </span><span class="sxs-lookup"><span data-stu-id="35452-460">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* containsFullScreenElement)</span></span>

#### <span data-ttu-id="35452-461">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="35452-461">get_DocumentTitle</span></span> 

<span data-ttu-id="35452-462">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="35452-462">The title for the current top level document.</span></span>

> <span data-ttu-id="35452-463">公共 HRESULT [get_DocumentTitle](#get_documenttitle) (LPWSTR \* 标题) </span><span class="sxs-lookup"><span data-stu-id="35452-463">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="35452-464">如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。</span><span class="sxs-lookup"><span data-stu-id="35452-464">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

#### <span data-ttu-id="35452-465">get_Settings</span><span class="sxs-lookup"><span data-stu-id="35452-465">get_Settings</span></span> 

<span data-ttu-id="35452-466">[ICoreWebView2Settings](icorewebview2settings.md)对象包含运行的 web 视图的各种可修改设置。</span><span class="sxs-lookup"><span data-stu-id="35452-466">The [ICoreWebView2Settings](icorewebview2settings.md) object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="35452-467">公共 HRESULT [get_Settings](#get_settings) ([ICoreWebView2Settings](icorewebview2settings.md) \* \* 设置) </span><span class="sxs-lookup"><span data-stu-id="35452-467">public HRESULT [get_Settings](#get_settings)([ICoreWebView2Settings](icorewebview2settings.md) \*\* settings)</span></span>

#### <span data-ttu-id="35452-468">get_Source</span><span class="sxs-lookup"><span data-stu-id="35452-468">get_Source</span></span> 

<span data-ttu-id="35452-469">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="35452-469">The URI of the current top level document.</span></span>

> <span data-ttu-id="35452-470">公共 HRESULT [get_Source](#get_source) (LPWSTR \* uri) </span><span class="sxs-lookup"><span data-stu-id="35452-470">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="35452-471">在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 SourceChanged 事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="35452-471">This value potentially changes as a part of the SourceChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="35452-472">它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。</span><span class="sxs-lookup"><span data-stu-id="35452-472">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

```cpp
    // Register a handler for the SourceChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_SourceChanged(
        Callback<ICoreWebView2SourceChangedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2SourceChangedEventArgs* args)
                -> HRESULT {
                wil::unique_cotaskmem_string uri;
                sender->get_Source(&uri);
                if (wcscmp(uri.get(), L"about:blank") == 0)
                {
                    uri = wil::make_cotaskmem_string(L"");
                }
                SetWindowText(GetAddressBar(), uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### <span data-ttu-id="35452-473">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="35452-473">GetDevToolsProtocolEventReceiver</span></span> 

<span data-ttu-id="35452-474">获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。</span><span class="sxs-lookup"><span data-stu-id="35452-474">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>

> <span data-ttu-id="35452-475">public HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver) (LPCWSTR 事件名称， [ICoreWebView2DevToolsProtocolEventReceiver](icorewebview2devtoolsprotocoleventreceiver.md) \* \* 接收器) </span><span class="sxs-lookup"><span data-stu-id="35452-475">public HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(LPCWSTR eventName, [ICoreWebView2DevToolsProtocolEventReceiver](icorewebview2devtoolsprotocoleventreceiver.md) \*\* receiver)</span></span>

<span data-ttu-id="35452-476">事件名称参数是该事件的格式的完整名称 `{domain}.{event}` 。</span><span class="sxs-lookup"><span data-stu-id="35452-476">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="35452-477">有关 DevTools 协议事件描述和事件参数的列表，请参阅 [DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs) 。</span><span class="sxs-lookup"><span data-stu-id="35452-477">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list of DevTools Protocol events description, and event args.</span></span>

```cpp
// Prompt the user to name a CDP event, and then subscribe to that event.
void ScriptComponent::SubscribeToCdpEvent()
{
    TextInputDialog dialog(
        m_appWindow->GetMainWindow(),
        L"Subscribe to CDP Event",
        L"CDP event name:",
        L"Enter the name of the CDP event to subscribe to.\r\n"
            L"You may also have to call the \"enable\" method of the\r\n"
            L"event's domain to receive events (for example \"Log.enable\").\r\n",
        L"Log.entryAdded");
    if (dialog.confirmed)
    {
        std::wstring eventName = dialog.input;
        wil::com_ptr<ICoreWebView2DevToolsProtocolEventReceiver> receiver;
        CHECK_FAILURE(
            m_webView->GetDevToolsProtocolEventReceiver(eventName.c_str(), &receiver));

        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(receiver->remove_DevToolsProtocolEventReceived(
                preexistingToken->second));
        }

        CHECK_FAILURE(receiver->add_DevToolsProtocolEventReceived(
            Callback<ICoreWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](
                    ICoreWebView2* sender,
                    ICoreWebView2DevToolsProtocolEventReceivedEventArgs* args) -> HRESULT {
                    wil::unique_cotaskmem_string parameterObjectAsJson;
                    CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
                    MessageBox(
                        nullptr, parameterObjectAsJson.get(),
                        (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
                    return S_OK;
                })
                .Get(),
            &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="35452-478">GoBack</span><span class="sxs-lookup"><span data-stu-id="35452-478">GoBack</span></span> 

<span data-ttu-id="35452-479">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="35452-479">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="35452-480">公共 HRESULT [GoBack](#goback) ( # A1</span><span class="sxs-lookup"><span data-stu-id="35452-480">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="35452-481">GoForward</span><span class="sxs-lookup"><span data-stu-id="35452-481">GoForward</span></span> 

<span data-ttu-id="35452-482">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="35452-482">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="35452-483">公共 HRESULT [GoForward](#goforward) ( # A1</span><span class="sxs-lookup"><span data-stu-id="35452-483">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="35452-484">导航</span><span class="sxs-lookup"><span data-stu-id="35452-484">Navigate</span></span> 

<span data-ttu-id="35452-485">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="35452-485">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="35452-486">public HRESULT [导航](#navigate) (LPCWSTR uri) </span><span class="sxs-lookup"><span data-stu-id="35452-486">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="35452-487">有关详细信息，请参阅导航事件。</span><span class="sxs-lookup"><span data-stu-id="35452-487">See the navigation events for more information.</span></span> <span data-ttu-id="35452-488">请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。</span><span class="sxs-lookup"><span data-stu-id="35452-488">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    int length = GetWindowTextLength(GetAddressBar());
    std::wstring uri(length, 0);
    PWSTR buffer = const_cast<PWSTR>(uri.data());
    GetWindowText(GetAddressBar(), buffer, length + 1);

    HRESULT hr = m_webView->Navigate(uri.c_str());
    if (hr == E_INVALIDARG)
    {
        // An invalid URI was provided.
        if (uri.find(L' ') == std::wstring::npos
            && uri.find(L'.') != std::wstring::npos)
        {
            // If it contains a dot and no spaces, try tacking http:// on the front.
            hr = m_webView->Navigate((L"http://" + uri).c_str());
        }
        else
        {
            // Otherwise treat it as a web search. We aren't bothering to escape
            // URL syntax characters such as & and #
            hr = m_webView->Navigate((L"https://bing.com/search?q=" + uri).c_str());
        }
    }
    if (hr != E_INVALIDARG) {
        CHECK_FAILURE(hr);
    }
}
```

#### <span data-ttu-id="35452-489">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="35452-489">NavigateToString</span></span> 

<span data-ttu-id="35452-490">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="35452-490">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="35452-491">公共的 HRESULT [NavigateToString](#navigatetostring) (LPCWSTR htmlContent) </span><span class="sxs-lookup"><span data-stu-id="35452-491">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="35452-492">HtmlContent 参数的总大小不得大于 2 MB。</span><span class="sxs-lookup"><span data-stu-id="35452-492">The htmlContent parameter may not be larger than 2 MB in total size.</span></span> <span data-ttu-id="35452-493">新页面的来源将显示为 "空白"。</span><span class="sxs-lookup"><span data-stu-id="35452-493">The origin of the new page will be about:blank.</span></span>

```cpp
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="35452-494">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="35452-494">OpenDevToolsWindow</span></span> 

<span data-ttu-id="35452-495">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="35452-495">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="35452-496">公共 HRESULT [OpenDevToolsWindow](#opendevtoolswindow) ( # A1</span><span class="sxs-lookup"><span data-stu-id="35452-496">public HRESULT [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="35452-497">如果在 DevTools 窗口已打开时调用，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="35452-497">Does nothing if called when the DevTools window is already open.</span></span>

#### <span data-ttu-id="35452-498">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="35452-498">PostWebMessageAsJson</span></span> 

<span data-ttu-id="35452-499">将指定的 webMessage 发布到此 Web 视图中的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="35452-499">Post the specified webMessage to the top level document in this WebView.</span></span>

> <span data-ttu-id="35452-500">公共的 HRESULT [PostWebMessageAsJson](#postwebmessageasjson) (LPCWSTR webMessageAsJson) </span><span class="sxs-lookup"><span data-stu-id="35452-500">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="35452-501">将激发顶级文档的 "chrome" 消息事件。</span><span class="sxs-lookup"><span data-stu-id="35452-501">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="35452-502">该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件：</span><span class="sxs-lookup"><span data-stu-id="35452-502">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span>

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

<span data-ttu-id="35452-503">事件参数是的实例 `MessageEvent` 。</span><span class="sxs-lookup"><span data-stu-id="35452-503">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="35452-504">ICoreWebView2Settings：： IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并显示 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="35452-504">The ICoreWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="35452-505">事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="35452-505">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="35452-506">事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="35452-506">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="35452-507">有关从 Web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 add_WebMessageReceived。</span><span class="sxs-lookup"><span data-stu-id="35452-507">See add_WebMessageReceived for information on sending messages from the HTML document in the WebView to the host.</span></span> <span data-ttu-id="35452-508">此消息将异步发送。</span><span class="sxs-lookup"><span data-stu-id="35452-508">This message is sent asynchronously.</span></span> <span data-ttu-id="35452-509">如果在将邮件发布到页面之前发生导航，则不会发送邮件。</span><span class="sxs-lookup"><span data-stu-id="35452-509">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<ICoreWebView2WebMessageReceivedEventHandler>(
            [this](ICoreWebView2* sender, ICoreWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->TryGetWebMessageAsString(&messageRaw));
        std::wstring message = messageRaw.get();

        if (message.compare(0, 13, L"SetTitleText ") == 0)
        {
            m_appWindow->SetTitleText(message.substr(13).c_str());
        }
        else if (message.compare(L"GetWindowBounds") == 0)
        {
            RECT bounds = m_appWindow->GetWindowBounds();
            std::wstring reply =
                L"{\"WindowBounds\":\"Left:" + std::to_wstring(bounds.left)
                + L"\\nTop:" + std::to_wstring(bounds.top)
                + L"\\nRight:" + std::to_wstring(bounds.right)
                + L"\\nBottom:" + std::to_wstring(bounds.bottom)
                + L"\"}";
            CHECK_FAILURE(sender->PostWebMessageAsJson(reply.c_str()));
        }
        return S_OK;
    }).Get(), &m_webMessageReceivedToken));
```

#### <span data-ttu-id="35452-510">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="35452-510">PostWebMessageAsString</span></span> 

<span data-ttu-id="35452-511">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="35452-511">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="35452-512">公共的 HRESULT [PostWebMessageAsString](#postwebmessageasstring) (LPCWSTR webMessageAsString) </span><span class="sxs-lookup"><span data-stu-id="35452-512">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="35452-513">此行为与 PostWebMessageAsJson 完全相同，但 `window.chrome.webview` 消息事件参数的 data 属性将是与 webMessageAsString 具有相同值的字符串。</span><span class="sxs-lookup"><span data-stu-id="35452-513">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="35452-514">如果想要通过简单的字符串而不是 JSON 对象进行通信，请使用此操作，而不是 PostWebMessageAsJson。</span><span class="sxs-lookup"><span data-stu-id="35452-514">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="35452-515">重载</span><span class="sxs-lookup"><span data-stu-id="35452-515">Reload</span></span> 

<span data-ttu-id="35452-516">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="35452-516">Reload the current page.</span></span>

> <span data-ttu-id="35452-517">公共 HRESULT [重新加载](#reload) ( # A1</span><span class="sxs-lookup"><span data-stu-id="35452-517">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="35452-518">这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。</span><span class="sxs-lookup"><span data-stu-id="35452-518">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="35452-519">但是，将不会修改后退/前进历史记录。</span><span class="sxs-lookup"><span data-stu-id="35452-519">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="35452-520">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="35452-520">remove_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="35452-521">删除以前使用 add_ContainsFullScreenElementChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-521">Remove an event handler previously added with add_ContainsFullScreenElementChanged.</span></span>

> <span data-ttu-id="35452-522">公共 HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-522">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-523">remove_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="35452-523">remove_ContentLoading</span></span> 

<span data-ttu-id="35452-524">删除以前使用 add_ContentLoading 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-524">Remove an event handler previously added with add_ContentLoading.</span></span>

> <span data-ttu-id="35452-525">公共 HRESULT [remove_ContentLoading](#remove_contentloading) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-525">public HRESULT [remove_ContentLoading](#remove_contentloading)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-526">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="35452-526">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="35452-527">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-527">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="35452-528">公共 HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-528">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-529">remove_FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-529">remove_FrameNavigationCompleted</span></span> 

<span data-ttu-id="35452-530">删除以前使用 add_FrameNavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-530">Remove an event handler previously added with add_FrameNavigationCompleted.</span></span>

> <span data-ttu-id="35452-531">公共 HRESULT [remove_FrameNavigationCompleted](#remove_framenavigationcompleted) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-531">public HRESULT [remove_FrameNavigationCompleted](#remove_framenavigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-532">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-532">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="35452-533">删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-533">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="35452-534">公共 HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-534">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-535">remove_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="35452-535">remove_HistoryChanged</span></span> 

<span data-ttu-id="35452-536">删除以前使用 add_HistoryChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-536">Remove an event handler previously added with add_HistoryChanged.</span></span>

> <span data-ttu-id="35452-537">公共 HRESULT [remove_HistoryChanged](#remove_historychanged) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-537">public HRESULT [remove_HistoryChanged](#remove_historychanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-538">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="35452-538">remove_NavigationCompleted</span></span> 

<span data-ttu-id="35452-539">删除以前使用 add_NavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-539">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="35452-540">公共 HRESULT [remove_NavigationCompleted](#remove_navigationcompleted) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-540">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-541">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="35452-541">remove_NavigationStarting</span></span> 

<span data-ttu-id="35452-542">删除以前使用 add_NavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-542">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="35452-543">公共 HRESULT [remove_NavigationStarting](#remove_navigationstarting) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-543">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-544">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="35452-544">remove_NewWindowRequested</span></span> 

<span data-ttu-id="35452-545">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-545">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="35452-546">公共 HRESULT [remove_NewWindowRequested](#remove_newwindowrequested) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-546">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-547">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="35452-547">remove_PermissionRequested</span></span> 

<span data-ttu-id="35452-548">删除以前使用 add_PermissionRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-548">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="35452-549">公共 HRESULT [remove_PermissionRequested](#remove_permissionrequested) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-549">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-550">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="35452-550">remove_ProcessFailed</span></span> 

<span data-ttu-id="35452-551">删除以前使用 add_ProcessFailed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-551">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="35452-552">公共 HRESULT [remove_ProcessFailed](#remove_processfailed) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-552">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-553">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="35452-553">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="35452-554">删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-554">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="35452-555">公共 HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-555">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-556">remove_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="35452-556">remove_SourceChanged</span></span> 

<span data-ttu-id="35452-557">删除以前使用 add_SourceChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-557">Remove an event handler previously added with add_SourceChanged.</span></span>

> <span data-ttu-id="35452-558">公共 HRESULT [remove_SourceChanged](#remove_sourcechanged) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-558">public HRESULT [remove_SourceChanged](#remove_sourcechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-559">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="35452-559">remove_WebMessageReceived</span></span> 

<span data-ttu-id="35452-560">删除以前使用 add_WebMessageReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-560">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="35452-561">公共 HRESULT [remove_WebMessageReceived](#remove_webmessagereceived) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-561">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-562">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="35452-562">remove_WebResourceRequested</span></span> 

<span data-ttu-id="35452-563">删除以前使用 add_WebResourceRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-563">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="35452-564">公共 HRESULT [remove_WebResourceRequested](#remove_webresourcerequested) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-564">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-565">remove_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="35452-565">remove_WindowCloseRequested</span></span> 

<span data-ttu-id="35452-566">删除以前使用 add_WindowCloseRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="35452-566">Remove an event handler previously added with add_WindowCloseRequested.</span></span>

> <span data-ttu-id="35452-567">公共 HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested) (EventRegistrationToken 令牌) </span><span class="sxs-lookup"><span data-stu-id="35452-567">public HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="35452-568">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="35452-568">RemoveHostObjectFromScript</span></span> 

<span data-ttu-id="35452-569">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="35452-569">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="35452-570">公共 HRESULT [RemoveHostObjectFromScript](#removehostobjectfromscript) (LPCWSTR 名称) </span><span class="sxs-lookup"><span data-stu-id="35452-570">public HRESULT [RemoveHostObjectFromScript](#removehostobjectfromscript)(LPCWSTR name)</span></span>

<span data-ttu-id="35452-571">当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="35452-571">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="35452-572">为已删除或从未添加的名称调用此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="35452-572">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="35452-573">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="35452-573">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="35452-574">删除使用指定脚本 id 添加的相应 JavaScript `AddScriptToExecuteOnDocumentCreated` 。</span><span class="sxs-lookup"><span data-stu-id="35452-574">Remove the corresponding JavaScript added using `AddScriptToExecuteOnDocumentCreated` with the specified script id.</span></span>

> <span data-ttu-id="35452-575">公共 HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated) (LPCWSTR id) </span><span class="sxs-lookup"><span data-stu-id="35452-575">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="35452-576">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="35452-576">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="35452-577">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="35452-577">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="35452-578">公共 HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter) (LPCWSTR const uri， [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext) </span><span class="sxs-lookup"><span data-stu-id="35452-578">public HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri, [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="35452-579">如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。</span><span class="sxs-lookup"><span data-stu-id="35452-579">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="35452-580">返回从未添加的筛选器 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="35452-580">Returns E_INVALIDARG for a filter that was never added.</span></span>

#### <span data-ttu-id="35452-581">停止</span><span class="sxs-lookup"><span data-stu-id="35452-581">Stop</span></span> 

<span data-ttu-id="35452-582">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="35452-582">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="35452-583">public HRESULT [Stop](#stop) ( # A1</span><span class="sxs-lookup"><span data-stu-id="35452-583">public HRESULT [Stop](#stop)()</span></span>

<span data-ttu-id="35452-584">不会停止脚本。</span><span class="sxs-lookup"><span data-stu-id="35452-584">Does not stop scripts.</span></span>

#### <span data-ttu-id="35452-585">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="35452-585">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="35452-586">ICoreWebView2：： CapturePreview 方法使用的图像格式。</span><span class="sxs-lookup"><span data-stu-id="35452-586">Image format used by the ICoreWebView2::CapturePreview method.</span></span>

> <span data-ttu-id="35452-587">枚举 [COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="35452-587">enum [COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#corewebview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="35452-588">值</span><span class="sxs-lookup"><span data-stu-id="35452-588">Values</span></span>                         | <span data-ttu-id="35452-589">描述</span><span class="sxs-lookup"><span data-stu-id="35452-589">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-590">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="35452-590">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="35452-591">PNG 图像格式。</span><span class="sxs-lookup"><span data-stu-id="35452-591">PNG image format.</span></span>
<span data-ttu-id="35452-592">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="35452-592">COREWEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="35452-593">JPEG 图像格式。</span><span class="sxs-lookup"><span data-stu-id="35452-593">JPEG image format.</span></span>

#### <span data-ttu-id="35452-594">COREWEBVIEW2_KEY_EVENT_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-594">COREWEBVIEW2_KEY_EVENT_KIND</span></span> 

<span data-ttu-id="35452-595">触发 AcceleratorKeyPressed 事件的键事件的类型。</span><span class="sxs-lookup"><span data-stu-id="35452-595">The type of key event that triggered an AcceleratorKeyPressed event.</span></span>

> <span data-ttu-id="35452-596">枚举 [COREWEBVIEW2_KEY_EVENT_KIND](#corewebview2_key_event_kind)</span><span class="sxs-lookup"><span data-stu-id="35452-596">enum [COREWEBVIEW2_KEY_EVENT_KIND](#corewebview2_key_event_kind)</span></span>

 <span data-ttu-id="35452-597">值</span><span class="sxs-lookup"><span data-stu-id="35452-597">Values</span></span>                         | <span data-ttu-id="35452-598">描述</span><span class="sxs-lookup"><span data-stu-id="35452-598">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-599">COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="35452-599">COREWEBVIEW2_KEY_EVENT_KIND_KEY_DOWN</span></span>            | <span data-ttu-id="35452-600">对应于窗口消息 WM_KEYDOWN。</span><span class="sxs-lookup"><span data-stu-id="35452-600">Correspond to window message WM_KEYDOWN.</span></span>
<span data-ttu-id="35452-601">COREWEBVIEW2_KEY_EVENT_KIND_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="35452-601">COREWEBVIEW2_KEY_EVENT_KIND_KEY_UP</span></span>            | <span data-ttu-id="35452-602">对应于窗口消息 WM_KEYUP。</span><span class="sxs-lookup"><span data-stu-id="35452-602">Correspond to window message WM_KEYUP.</span></span>
<span data-ttu-id="35452-603">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span><span class="sxs-lookup"><span data-stu-id="35452-603">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_DOWN</span></span>            | <span data-ttu-id="35452-604">对应于窗口消息 WM_SYSKEYDOWN。</span><span class="sxs-lookup"><span data-stu-id="35452-604">Correspond to window message WM_SYSKEYDOWN.</span></span>
<span data-ttu-id="35452-605">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span><span class="sxs-lookup"><span data-stu-id="35452-605">COREWEBVIEW2_KEY_EVENT_KIND_SYSTEM_KEY_UP</span></span>            | <span data-ttu-id="35452-606">对应于窗口消息 WM_SYSKEYUP。</span><span class="sxs-lookup"><span data-stu-id="35452-606">Correspond to window message WM_SYSKEYUP.</span></span>

#### <span data-ttu-id="35452-607">COREWEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="35452-607">COREWEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="35452-608">移动焦点的原因。</span><span class="sxs-lookup"><span data-stu-id="35452-608">Reason for moving focus.</span></span>

> <span data-ttu-id="35452-609">枚举 [COREWEBVIEW2_MOVE_FOCUS_REASON](#corewebview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="35452-609">enum [COREWEBVIEW2_MOVE_FOCUS_REASON](#corewebview2_move_focus_reason)</span></span>

 <span data-ttu-id="35452-610">值</span><span class="sxs-lookup"><span data-stu-id="35452-610">Values</span></span>                         | <span data-ttu-id="35452-611">描述</span><span class="sxs-lookup"><span data-stu-id="35452-611">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-612">COREWEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="35452-612">COREWEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="35452-613">将焦点放入 Web 视图中的代码。</span><span class="sxs-lookup"><span data-stu-id="35452-613">Code setting focus into WebView.</span></span>
<span data-ttu-id="35452-614">COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="35452-614">COREWEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="35452-615">由于向前遍历 Tab 遍历，移动焦点。</span><span class="sxs-lookup"><span data-stu-id="35452-615">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="35452-616">COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="35452-616">COREWEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="35452-617">由于 Tab 向后移动焦点。</span><span class="sxs-lookup"><span data-stu-id="35452-617">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="35452-618">COREWEBVIEW2_PERMISSION_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-618">COREWEBVIEW2_PERMISSION_KIND</span></span> 

<span data-ttu-id="35452-619">权限请求的类型。</span><span class="sxs-lookup"><span data-stu-id="35452-619">The type of a permission request.</span></span>

> <span data-ttu-id="35452-620">枚举 [COREWEBVIEW2_PERMISSION_KIND](#corewebview2_permission_kind)</span><span class="sxs-lookup"><span data-stu-id="35452-620">enum [COREWEBVIEW2_PERMISSION_KIND](#corewebview2_permission_kind)</span></span>

 <span data-ttu-id="35452-621">值</span><span class="sxs-lookup"><span data-stu-id="35452-621">Values</span></span>                         | <span data-ttu-id="35452-622">描述</span><span class="sxs-lookup"><span data-stu-id="35452-622">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-623">COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="35452-623">COREWEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="35452-624">未知权限。</span><span class="sxs-lookup"><span data-stu-id="35452-624">Unknown permission.</span></span>
<span data-ttu-id="35452-625">COREWEBVIEW2_PERMISSION_KIND_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="35452-625">COREWEBVIEW2_PERMISSION_KIND_MICROPHONE</span></span>            | <span data-ttu-id="35452-626">捕获音频的权限。</span><span class="sxs-lookup"><span data-stu-id="35452-626">Permission to capture audio.</span></span>
<span data-ttu-id="35452-627">COREWEBVIEW2_PERMISSION_KIND_CAMERA</span><span class="sxs-lookup"><span data-stu-id="35452-627">COREWEBVIEW2_PERMISSION_KIND_CAMERA</span></span>            | <span data-ttu-id="35452-628">捕获视频的权限。</span><span class="sxs-lookup"><span data-stu-id="35452-628">Permission to capture video.</span></span>
<span data-ttu-id="35452-629">COREWEBVIEW2_PERMISSION_KIND_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="35452-629">COREWEBVIEW2_PERMISSION_KIND_GEOLOCATION</span></span>            | <span data-ttu-id="35452-630">访问地理位置的权限。</span><span class="sxs-lookup"><span data-stu-id="35452-630">Permission to access geolocation.</span></span>
<span data-ttu-id="35452-631">COREWEBVIEW2_PERMISSION_KIND_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="35452-631">COREWEBVIEW2_PERMISSION_KIND_NOTIFICATIONS</span></span>            | <span data-ttu-id="35452-632">发送 web 通知的权限。</span><span class="sxs-lookup"><span data-stu-id="35452-632">Permission to send web notifications.</span></span>
<span data-ttu-id="35452-633">COREWEBVIEW2_PERMISSION_KIND_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="35452-633">COREWEBVIEW2_PERMISSION_KIND_OTHER_SENSORS</span></span>            | <span data-ttu-id="35452-634">访问通用传感器的权限。</span><span class="sxs-lookup"><span data-stu-id="35452-634">Permission to access generic sensor.</span></span>
<span data-ttu-id="35452-635">COREWEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="35452-635">COREWEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ</span></span>            | <span data-ttu-id="35452-636">在没有用户手势的情况下读取系统剪贴板的权限。</span><span class="sxs-lookup"><span data-stu-id="35452-636">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="35452-637">COREWEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="35452-637">COREWEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="35452-638">对权限请求的响应。</span><span class="sxs-lookup"><span data-stu-id="35452-638">Response to a permission request.</span></span>

> <span data-ttu-id="35452-639">枚举 [COREWEBVIEW2_PERMISSION_STATE](#corewebview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="35452-639">enum [COREWEBVIEW2_PERMISSION_STATE](#corewebview2_permission_state)</span></span>

 <span data-ttu-id="35452-640">值</span><span class="sxs-lookup"><span data-stu-id="35452-640">Values</span></span>                         | <span data-ttu-id="35452-641">描述</span><span class="sxs-lookup"><span data-stu-id="35452-641">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-642">COREWEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="35452-642">COREWEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="35452-643">使用默认的浏览器行为，这通常会提示用户做出决策。</span><span class="sxs-lookup"><span data-stu-id="35452-643">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="35452-644">COREWEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="35452-644">COREWEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="35452-645">授予权限请求。</span><span class="sxs-lookup"><span data-stu-id="35452-645">Grant the permission request.</span></span>
<span data-ttu-id="35452-646">COREWEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="35452-646">COREWEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="35452-647">拒绝权限请求。</span><span class="sxs-lookup"><span data-stu-id="35452-647">Deny the permission request.</span></span>

#### <span data-ttu-id="35452-648">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span><span class="sxs-lookup"><span data-stu-id="35452-648">COREWEBVIEW2_PHYSICAL_KEY_STATUS</span></span> 

<span data-ttu-id="35452-649">一个结构，表示打包到给定给 Win32 键事件的 LPARAM 中的信息。</span><span class="sxs-lookup"><span data-stu-id="35452-649">A structure representing the information packed into the LPARAM given to a Win32 key event.</span></span>

> <span data-ttu-id="35452-650">typedef [COREWEBVIEW2_PHYSICAL_KEY_STATUS](#corewebview2_physical_key_status)</span><span class="sxs-lookup"><span data-stu-id="35452-650">typedef [COREWEBVIEW2_PHYSICAL_KEY_STATUS](#corewebview2_physical_key_status)</span></span>

<span data-ttu-id="35452-651">有关详细信息，请参阅 WM_KEYDOWN 的文档 [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span><span class="sxs-lookup"><span data-stu-id="35452-651">See the documentation for WM_KEYDOWN for details at [https://docs.microsoft.com/windows/win32/inputdev/wm-keydown](https://docs.microsoft.com/windows/win32/inputdev/wm-keydown)</span></span>

#### <span data-ttu-id="35452-652">COREWEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-652">COREWEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="35452-653">ICoreWebView2ProcessFailedEventHandler 接口中使用的进程失败类型。</span><span class="sxs-lookup"><span data-stu-id="35452-653">Kind of process failure used in the ICoreWebView2ProcessFailedEventHandler interface.</span></span>

> <span data-ttu-id="35452-654">枚举 [COREWEBVIEW2_PROCESS_FAILED_KIND](#corewebview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="35452-654">enum [COREWEBVIEW2_PROCESS_FAILED_KIND](#corewebview2_process_failed_kind)</span></span>

 <span data-ttu-id="35452-655">值</span><span class="sxs-lookup"><span data-stu-id="35452-655">Values</span></span>                         | <span data-ttu-id="35452-656">描述</span><span class="sxs-lookup"><span data-stu-id="35452-656">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-657">COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="35452-657">COREWEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="35452-658">指示浏览器进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="35452-658">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="35452-659">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="35452-659">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="35452-660">指示呈现进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="35452-660">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="35452-661">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="35452-661">COREWEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="35452-662">指示呈现过程变得无响应。</span><span class="sxs-lookup"><span data-stu-id="35452-662">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="35452-663">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="35452-663">COREWEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="35452-664">ICoreWebView2ScriptDialogOpeningEventHandler 接口中使用的 JavaScript 对话框类型。</span><span class="sxs-lookup"><span data-stu-id="35452-664">Kind of JavaScript dialog used in the ICoreWebView2ScriptDialogOpeningEventHandler interface.</span></span>

> <span data-ttu-id="35452-665">枚举 [COREWEBVIEW2_SCRIPT_DIALOG_KIND](#corewebview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="35452-665">enum [COREWEBVIEW2_SCRIPT_DIALOG_KIND](#corewebview2_script_dialog_kind)</span></span>

 <span data-ttu-id="35452-666">值</span><span class="sxs-lookup"><span data-stu-id="35452-666">Values</span></span>                         | <span data-ttu-id="35452-667">描述</span><span class="sxs-lookup"><span data-stu-id="35452-667">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-668">COREWEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="35452-668">COREWEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="35452-669">通过窗口调用的对话框。警报 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="35452-669">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="35452-670">COREWEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="35452-670">COREWEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="35452-671">通过窗口调用的对话框。确认 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="35452-671">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="35452-672">COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="35452-672">COREWEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="35452-673">通过窗口调用的对话框。提示 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="35452-673">A dialog invoked via the window.prompt JavaScript function.</span></span>
<span data-ttu-id="35452-674">COREWEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD</span><span class="sxs-lookup"><span data-stu-id="35452-674">COREWEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD</span></span>            | <span data-ttu-id="35452-675">通过 beforeunload JavaScript 事件调用的对话框。</span><span class="sxs-lookup"><span data-stu-id="35452-675">A dialog invoked via the beforeunload JavaScript event.</span></span>

#### <span data-ttu-id="35452-676">COREWEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="35452-676">COREWEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="35452-677">Web 导航的错误状态值。</span><span class="sxs-lookup"><span data-stu-id="35452-677">Error status values for web navigations.</span></span>

> <span data-ttu-id="35452-678">枚举 [COREWEBVIEW2_WEB_ERROR_STATUS](#corewebview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="35452-678">enum [COREWEBVIEW2_WEB_ERROR_STATUS](#corewebview2_web_error_status)</span></span>

 <span data-ttu-id="35452-679">值</span><span class="sxs-lookup"><span data-stu-id="35452-679">Values</span></span>                         | <span data-ttu-id="35452-680">描述</span><span class="sxs-lookup"><span data-stu-id="35452-680">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-681">COREWEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="35452-681">COREWEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="35452-682">出现未知错误。</span><span class="sxs-lookup"><span data-stu-id="35452-682">An unknown error occurred.</span></span>
<span data-ttu-id="35452-683">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="35452-683">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="35452-684">SSL 证书公用名与 web 地址不匹配。</span><span class="sxs-lookup"><span data-stu-id="35452-684">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="35452-685">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="35452-685">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="35452-686">SSL 证书已过期。</span><span class="sxs-lookup"><span data-stu-id="35452-686">The SSL certificate has expired.</span></span>
<span data-ttu-id="35452-687">COREWEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="35452-687">COREWEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="35452-688">SSL 客户端证书包含错误。</span><span class="sxs-lookup"><span data-stu-id="35452-688">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="35452-689">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="35452-689">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="35452-690">SSL 证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="35452-690">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="35452-691">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="35452-691">COREWEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="35452-692">SSL 证书无效 &ndash; 这可能意味着证书与主机名的公钥 pin 不匹配，证书由不受信任的颁发机构或使用弱标志算法签名，证书声明的 DNS 名称违反了名称约束，证书包含弱密钥，证书的有效期太长，缺少吊销信息或吊销机制、非唯一的主机名、缺少证书透明信息，或者证书被链接到 [旧版 Symantec 根](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)。</span><span class="sxs-lookup"><span data-stu-id="35452-692">The SSL certificate is invalid &ndash; this could mean the certificate did not match the public key pins for the host name, the certificate is signed by an untrusted authority or using a weak sign algorithm, the certificate claimed DNS names violate name constraints, the certificate contains a weak key, the certificate's validity period is too long, lack of revocation information or revocation mechanism, non-unique host name, lack of certificate transparency information, or the certificate is chained to a [legacy Symantec root](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html).</span></span>
<span data-ttu-id="35452-693">COREWEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="35452-693">COREWEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="35452-694">无法访问主机。</span><span class="sxs-lookup"><span data-stu-id="35452-694">The host is unreachable.</span></span>
<span data-ttu-id="35452-695">COREWEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="35452-695">COREWEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="35452-696">连接超时。</span><span class="sxs-lookup"><span data-stu-id="35452-696">The connection has timed out.</span></span>
<span data-ttu-id="35452-697">COREWEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="35452-697">COREWEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="35452-698">服务器返回了无效或无法识别的响应。</span><span class="sxs-lookup"><span data-stu-id="35452-698">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="35452-699">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="35452-699">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="35452-700">连接已中止。</span><span class="sxs-lookup"><span data-stu-id="35452-700">The connection was aborted.</span></span>
<span data-ttu-id="35452-701">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="35452-701">COREWEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="35452-702">已重置连接。</span><span class="sxs-lookup"><span data-stu-id="35452-702">The connection was reset.</span></span>
<span data-ttu-id="35452-703">COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="35452-703">COREWEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="35452-704">互联网连接已丢失。</span><span class="sxs-lookup"><span data-stu-id="35452-704">The Internet connection has been lost.</span></span>
<span data-ttu-id="35452-705">COREWEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="35452-705">COREWEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="35452-706">无法连接到目标。</span><span class="sxs-lookup"><span data-stu-id="35452-706">Cannot connect to destination.</span></span>
<span data-ttu-id="35452-707">COREWEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="35452-707">COREWEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="35452-708">无法解析提供的主机名。</span><span class="sxs-lookup"><span data-stu-id="35452-708">Could not resolve provided host name.</span></span>
<span data-ttu-id="35452-709">COREWEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="35452-709">COREWEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="35452-710">操作已取消。</span><span class="sxs-lookup"><span data-stu-id="35452-710">The operation was canceled.</span></span>
<span data-ttu-id="35452-711">COREWEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="35452-711">COREWEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="35452-712">请求重定向失败。</span><span class="sxs-lookup"><span data-stu-id="35452-712">The request redirect failed.</span></span>
<span data-ttu-id="35452-713">COREWEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="35452-713">COREWEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="35452-714">出现意外错误。</span><span class="sxs-lookup"><span data-stu-id="35452-714">An unexpected error occurred.</span></span>

#### <span data-ttu-id="35452-715">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="35452-715">COREWEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="35452-716">Web 资源请求上下文的枚举。</span><span class="sxs-lookup"><span data-stu-id="35452-716">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="35452-717">枚举 [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="35452-717">enum [COREWEBVIEW2_WEB_RESOURCE_CONTEXT](#corewebview2_web_resource_context)</span></span>

 <span data-ttu-id="35452-718">值</span><span class="sxs-lookup"><span data-stu-id="35452-718">Values</span></span>                         | <span data-ttu-id="35452-719">描述</span><span class="sxs-lookup"><span data-stu-id="35452-719">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="35452-720">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="35452-720">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="35452-721">所有资源。</span><span class="sxs-lookup"><span data-stu-id="35452-721">All resources.</span></span>
<span data-ttu-id="35452-722">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="35452-722">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="35452-723">文档资源。</span><span class="sxs-lookup"><span data-stu-id="35452-723">Document resources.</span></span>
<span data-ttu-id="35452-724">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="35452-724">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="35452-725">CSS 资源。</span><span class="sxs-lookup"><span data-stu-id="35452-725">CSS resources.</span></span>
<span data-ttu-id="35452-726">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="35452-726">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="35452-727">图像资源。</span><span class="sxs-lookup"><span data-stu-id="35452-727">Image resources.</span></span>
<span data-ttu-id="35452-728">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="35452-728">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="35452-729">其他媒体资源（如视频）。</span><span class="sxs-lookup"><span data-stu-id="35452-729">Other media resources such as videos.</span></span>
<span data-ttu-id="35452-730">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="35452-730">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="35452-731">字体资源。</span><span class="sxs-lookup"><span data-stu-id="35452-731">Font resources.</span></span>
<span data-ttu-id="35452-732">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="35452-732">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="35452-733">脚本资源。</span><span class="sxs-lookup"><span data-stu-id="35452-733">Script resources.</span></span>
<span data-ttu-id="35452-734">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="35452-734">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="35452-735">XML HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="35452-735">XML HTTP requests.</span></span>
<span data-ttu-id="35452-736">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="35452-736">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="35452-737">获取 API 通信。</span><span class="sxs-lookup"><span data-stu-id="35452-737">Fetch API communication.</span></span>
<span data-ttu-id="35452-738">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="35452-738">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="35452-739">TextTrack 资源。</span><span class="sxs-lookup"><span data-stu-id="35452-739">TextTrack resources.</span></span>
<span data-ttu-id="35452-740">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="35452-740">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | <span data-ttu-id="35452-741">EventSource API 通信。</span><span class="sxs-lookup"><span data-stu-id="35452-741">EventSource API communication.</span></span>
<span data-ttu-id="35452-742">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="35452-742">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | <span data-ttu-id="35452-743">WebSocket API 通信。</span><span class="sxs-lookup"><span data-stu-id="35452-743">WebSocket API communication.</span></span>
<span data-ttu-id="35452-744">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="35452-744">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | <span data-ttu-id="35452-745">Web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="35452-745">Web App Manifests.</span></span>
<span data-ttu-id="35452-746">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="35452-746">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | <span data-ttu-id="35452-747">已签名的 HTTP 交换。</span><span class="sxs-lookup"><span data-stu-id="35452-747">Signed HTTP Exchanges.</span></span>
<span data-ttu-id="35452-748">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="35452-748">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | <span data-ttu-id="35452-749">Ping 请求。</span><span class="sxs-lookup"><span data-stu-id="35452-749">Ping requests.</span></span>
<span data-ttu-id="35452-750">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="35452-750">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | <span data-ttu-id="35452-751">CSP 冲突报告。</span><span class="sxs-lookup"><span data-stu-id="35452-751">CSP Violation Reports.</span></span>
<span data-ttu-id="35452-752">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="35452-752">COREWEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="35452-753">其他资源。</span><span class="sxs-lookup"><span data-stu-id="35452-753">Other resources.</span></span>

