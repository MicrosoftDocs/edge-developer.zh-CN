---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Host、浏览器控件、边缘 html
ms.openlocfilehash: 77eb48773a963775e00d4dec50368564af5678b0
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10653225"
---
# <span data-ttu-id="e3835-104">interface ICoreWebView2</span><span class="sxs-lookup"><span data-stu-id="e3835-104">interface ICoreWebView2</span></span> 

> [!NOTE]
> <span data-ttu-id="e3835-105">此接口可能会在 SDK 版本0.9.430 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="e3835-105">This interface may be altered or unavailable for releases after SDK version 0.9.430.</span></span> <span data-ttu-id="e3835-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="e3835-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface ICoreWebView2
  : public IUnknown
```

<span data-ttu-id="e3835-107">WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="e3835-107">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="e3835-108">摘要</span><span class="sxs-lookup"><span data-stu-id="e3835-108">Summary</span></span>

 <span data-ttu-id="e3835-109">成员</span><span class="sxs-lookup"><span data-stu-id="e3835-109">Members</span></span>                        | <span data-ttu-id="e3835-110">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="e3835-111">get_Settings</span><span class="sxs-lookup"><span data-stu-id="e3835-111">get_Settings</span></span>](#get_settings) | <span data-ttu-id="e3835-112">ICoreWebView2Settings 对象包含运行的 Web 视图的各种可修改设置。</span><span class="sxs-lookup"><span data-stu-id="e3835-112">The ICoreWebView2Settings object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="e3835-113">get_Source</span><span class="sxs-lookup"><span data-stu-id="e3835-113">get_Source</span></span>](#get_source) | <span data-ttu-id="e3835-114">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="e3835-114">The URI of the current top level document.</span></span>
[<span data-ttu-id="e3835-115">导航</span><span class="sxs-lookup"><span data-stu-id="e3835-115">Navigate</span></span>](#navigate) | <span data-ttu-id="e3835-116">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="e3835-116">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="e3835-117">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="e3835-117">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="e3835-118">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="e3835-118">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="e3835-119">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-119">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="e3835-120">为 NavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-120">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="e3835-121">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-121">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="e3835-122">删除以前使用 add_NavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-122">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="e3835-123">add_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="e3835-123">add_ContentLoading</span></span>](#add_contentloading) | <span data-ttu-id="e3835-124">为 ContentLoading 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-124">Add an event handler for the ContentLoading event.</span></span>
[<span data-ttu-id="e3835-125">remove_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="e3835-125">remove_ContentLoading</span></span>](#remove_contentloading) | <span data-ttu-id="e3835-126">删除以前使用 add_ContentLoading 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-126">Remove an event handler previously added with add_ContentLoading.</span></span>
[<span data-ttu-id="e3835-127">add_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-127">add_SourceChanged</span></span>](#add_sourcechanged) | <span data-ttu-id="e3835-128">Source 属性更改时将触发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="e3835-128">SourceChanged fires when the Source property changes.</span></span>
[<span data-ttu-id="e3835-129">remove_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-129">remove_SourceChanged</span></span>](#remove_sourcechanged) | <span data-ttu-id="e3835-130">删除以前使用 add_SourceChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-130">Remove an event handler previously added with add_SourceChanged.</span></span>
[<span data-ttu-id="e3835-131">add_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-131">add_HistoryChanged</span></span>](#add_historychanged) | <span data-ttu-id="e3835-132">历史记录更改侦听顶级文档的导航历史记录更改。</span><span class="sxs-lookup"><span data-stu-id="e3835-132">HistoryChange listen to the change of navigation history for the top level document.</span></span>
[<span data-ttu-id="e3835-133">remove_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-133">remove_HistoryChanged</span></span>](#remove_historychanged) | <span data-ttu-id="e3835-134">删除以前使用 add_HistoryChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-134">Remove an event handler previously added with add_HistoryChanged.</span></span>
[<span data-ttu-id="e3835-135">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="e3835-135">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="e3835-136">为 NavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-136">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="e3835-137">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="e3835-137">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="e3835-138">删除以前使用 add_NavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-138">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="e3835-139">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-139">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="e3835-140">为 FrameNavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-140">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="e3835-141">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-141">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="e3835-142">删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-142">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="e3835-143">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="e3835-143">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="e3835-144">为 ScriptDialogOpening 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-144">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="e3835-145">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="e3835-145">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="e3835-146">删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-146">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="e3835-147">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-147">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="e3835-148">为 Webview.permissionrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-148">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="e3835-149">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-149">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="e3835-150">删除以前使用 add_PermissionRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-150">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="e3835-151">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="e3835-151">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="e3835-152">为 ProcessFailed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-152">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="e3835-153">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="e3835-153">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="e3835-154">删除以前使用 add_ProcessFailed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-154">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="e3835-155">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="e3835-155">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="e3835-156">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="e3835-156">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="e3835-157">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="e3835-157">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="e3835-158">删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="e3835-158">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="e3835-159">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="e3835-159">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="e3835-160">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="e3835-160">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="e3835-161">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="e3835-161">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="e3835-162">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="e3835-162">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="e3835-163">重载</span><span class="sxs-lookup"><span data-stu-id="e3835-163">Reload</span></span>](#reload) | <span data-ttu-id="e3835-164">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="e3835-164">Reload the current page.</span></span>
[<span data-ttu-id="e3835-165">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="e3835-165">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="e3835-166">将指定的 webMessage 发布到此 Web 视图中的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="e3835-166">Post the specified webMessage to the top level document in this WebView.</span></span>
[<span data-ttu-id="e3835-167">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="e3835-167">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="e3835-168">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e3835-168">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="e3835-169">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="e3835-169">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="e3835-170">当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-170">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="e3835-171">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="e3835-171">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="e3835-172">删除以前使用 add_WebMessageReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-172">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="e3835-173">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="e3835-173">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="e3835-174">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-174">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="e3835-175">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="e3835-175">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="e3835-176">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="e3835-176">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="e3835-177">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="e3835-177">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="e3835-178">如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="e3835-178">Returns true if the webview can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="e3835-179">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="e3835-179">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="e3835-180">如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="e3835-180">Returns true if the webview can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="e3835-181">GoBack</span><span class="sxs-lookup"><span data-stu-id="e3835-181">GoBack</span></span>](#goback) | <span data-ttu-id="e3835-182">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="e3835-182">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="e3835-183">GoForward</span><span class="sxs-lookup"><span data-stu-id="e3835-183">GoForward</span></span>](#goforward) | <span data-ttu-id="e3835-184">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="e3835-184">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="e3835-185">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="e3835-185">GetDevToolsProtocolEventReceiver</span></span>](#getdevtoolsprotocoleventreceiver) | <span data-ttu-id="e3835-186">获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。</span><span class="sxs-lookup"><span data-stu-id="e3835-186">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>
[<span data-ttu-id="e3835-187">停止</span><span class="sxs-lookup"><span data-stu-id="e3835-187">Stop</span></span>](#stop) | <span data-ttu-id="e3835-188">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="e3835-188">Stop all navigations and pending resource fetches.</span></span>
[<span data-ttu-id="e3835-189">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-189">add_NewWindowRequested</span></span>](#add_newwindowrequested) | <span data-ttu-id="e3835-190">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-190">Add an event handler for the NewWindowRequested event.</span></span>
[<span data-ttu-id="e3835-191">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-191">remove_NewWindowRequested</span></span>](#remove_newwindowrequested) | <span data-ttu-id="e3835-192">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-192">Remove an event handler previously added with add_NewWindowRequested.</span></span>
[<span data-ttu-id="e3835-193">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-193">add_DocumentTitleChanged</span></span>](#add_documenttitlechanged) | <span data-ttu-id="e3835-194">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-194">Add an event handler for the DocumentTitleChanged event.</span></span>
[<span data-ttu-id="e3835-195">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-195">remove_DocumentTitleChanged</span></span>](#remove_documenttitlechanged) | <span data-ttu-id="e3835-196">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-196">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>
[<span data-ttu-id="e3835-197">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="e3835-197">get_DocumentTitle</span></span>](#get_documenttitle) | <span data-ttu-id="e3835-198">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="e3835-198">The title for the current top level document.</span></span>
[<span data-ttu-id="e3835-199">AddRemoteObject</span><span class="sxs-lookup"><span data-stu-id="e3835-199">AddRemoteObject</span></span>](#addremoteobject) | <span data-ttu-id="e3835-200">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="e3835-200">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="e3835-201">RemoveRemoteObject</span><span class="sxs-lookup"><span data-stu-id="e3835-201">RemoveRemoteObject</span></span>](#removeremoteobject) | <span data-ttu-id="e3835-202">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="e3835-202">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="e3835-203">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="e3835-203">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="e3835-204">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="e3835-204">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="e3835-205">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-205">add_ContainsFullScreenElementChanged</span></span>](#add_containsfullscreenelementchanged) | <span data-ttu-id="e3835-206">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="e3835-206">Notifies when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="e3835-207">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-207">remove_ContainsFullScreenElementChanged</span></span>](#remove_containsfullscreenelementchanged) | <span data-ttu-id="e3835-208">删除以前使用相应的 add_ 事件方法添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-208">Remove an event handler previously added with the corresponding add_ event method.</span></span>
[<span data-ttu-id="e3835-209">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="e3835-209">get_ContainsFullScreenElement</span></span>](#get_containsfullscreenelement) | <span data-ttu-id="e3835-210">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="e3835-210">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="e3835-211">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-211">add_WebResourceRequested</span></span>](#add_webresourcerequested) | <span data-ttu-id="e3835-212">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-212">Add an event handler for the WebResourceRequested event.</span></span>
[<span data-ttu-id="e3835-213">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-213">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="e3835-214">删除以前使用 add_WebResourceRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-214">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="e3835-215">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="e3835-215">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="e3835-216">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-216">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="e3835-217">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="e3835-217">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="e3835-218">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="e3835-218">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>
[<span data-ttu-id="e3835-219">add_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-219">add_WindowCloseRequested</span></span>](#add_windowcloserequested) | <span data-ttu-id="e3835-220">为 WindowCloseRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-220">Add an event handler for the WindowCloseRequested event.</span></span>
[<span data-ttu-id="e3835-221">remove_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-221">remove_WindowCloseRequested</span></span>](#remove_windowcloserequested) | <span data-ttu-id="e3835-222">删除以前使用 add_WindowCloseRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-222">Remove an event handler previously added with add_WindowCloseRequested.</span></span>
[<span data-ttu-id="e3835-223">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="e3835-223">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#core_webview2_capture_preview_image_format) | <span data-ttu-id="e3835-224">ICoreWebView2：： CapturePreview 方法使用的图像格式。</span><span class="sxs-lookup"><span data-stu-id="e3835-224">Image format used by the ICoreWebView2::CapturePreview method.</span></span>
[<span data-ttu-id="e3835-225">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="e3835-225">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#core_webview2_script_dialog_kind) | <span data-ttu-id="e3835-226">ICoreWebView2ScriptDialogOpeningEventHandler 接口中使用的 JavaScript 对话框类型。</span><span class="sxs-lookup"><span data-stu-id="e3835-226">Kind of JavaScript dialog used in the ICoreWebView2ScriptDialogOpeningEventHandler interface.</span></span>
[<span data-ttu-id="e3835-227">CORE_WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="e3835-227">CORE_WEBVIEW2_PROCESS_FAILED_KIND</span></span>](#core_webview2_process_failed_kind) | <span data-ttu-id="e3835-228">ICoreWebView2ProcessFailedEventHandler 接口中使用的进程失败类型。</span><span class="sxs-lookup"><span data-stu-id="e3835-228">Kind of process failure used in the ICoreWebView2ProcessFailedEventHandler interface.</span></span>
[<span data-ttu-id="e3835-229">CORE_WEBVIEW2_PERMISSION_KIND</span><span class="sxs-lookup"><span data-stu-id="e3835-229">CORE_WEBVIEW2_PERMISSION_KIND</span></span>](#core_webview2_permission_kind) | <span data-ttu-id="e3835-230">权限请求的类型。</span><span class="sxs-lookup"><span data-stu-id="e3835-230">The type of a permission request.</span></span>
[<span data-ttu-id="e3835-231">CORE_WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="e3835-231">CORE_WEBVIEW2_PERMISSION_STATE</span></span>](#core_webview2_permission_state) | <span data-ttu-id="e3835-232">对权限请求的响应。</span><span class="sxs-lookup"><span data-stu-id="e3835-232">Response to a permission request.</span></span>
[<span data-ttu-id="e3835-233">CORE_WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="e3835-233">CORE_WEBVIEW2_WEB_ERROR_STATUS</span></span>](#core_webview2_web_error_status) | <span data-ttu-id="e3835-234">Web 导航的错误状态值。</span><span class="sxs-lookup"><span data-stu-id="e3835-234">Error status values for web navigations.</span></span>
[<span data-ttu-id="e3835-235">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="e3835-235">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#core_webview2_web_resource_context) | <span data-ttu-id="e3835-236">Web 资源请求上下文的枚举。</span><span class="sxs-lookup"><span data-stu-id="e3835-236">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="e3835-237">导航事件</span><span class="sxs-lookup"><span data-stu-id="e3835-237">Navigation events</span></span>

<span data-ttu-id="e3835-238">导航事件的常规序列为 NavigationStarting、SourceChanged、ContentLoading 和 NavigationCompleted。</span><span class="sxs-lookup"><span data-stu-id="e3835-238">The normal sequence of navigation events is NavigationStarting, SourceChanged, ContentLoading and then NavigationCompleted.</span></span>

![dot-inline-dotgraph-1](media/dot-inline-dotgraph-1.png)

<span data-ttu-id="e3835-240">请注意，这适用于具有相同的 NavigationId 事件参数的导航事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-240">Note that this is for navigation events with the same NavigationId event arg.</span></span> <span data-ttu-id="e3835-241">具有不同 NavigationId 事件参数的导航事件可能会重叠。</span><span class="sxs-lookup"><span data-stu-id="e3835-241">Navigations events with different NavigationId event args may overlap.</span></span> <span data-ttu-id="e3835-242">例如，如果你为其 NavigationStarting 事件启动导航等待，然后开始另一个导航，你将看到第一个导航的 NavigationStarting，后跟第二个导航的 NavigationStarting，然后是第一个导航的 NavigationCompleted 以及第二个导航的所有其余导航事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-242">For instance, if you start a navigation wait for its NavigationStarting event and then start another navigation you'll see the NavigationStarting for the first navigate followed by the NavigationStarting of the second navigate, followed by the NavigationCompleted for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span> <span data-ttu-id="e3835-243">在错误情况下，可能会有也可能不是 ContentLoading 事件，具体取决于导航是否转到错误页面。</span><span class="sxs-lookup"><span data-stu-id="e3835-243">In error cases there may or may not be a ContentLoading event depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="e3835-244">在 HTTP 重定向时，一行中将有多个 NavigationStarting 事件，并且第一个事件将设置其 IsRedirect 标志。</span><span class="sxs-lookup"><span data-stu-id="e3835-244">In case of an HTTP redirect, there will be multiple NavigationStarting events in a row, with ones following the first will have their IsRedirect flag set.</span></span>

<span data-ttu-id="e3835-245">若要在 Web 视图中的 subframes 内监视或取消导航，请使用 FrameNavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="e3835-245">To monitor or cancel navigations inside subframes in the WebView, use FrameNavigationStarting.</span></span>

## <span data-ttu-id="e3835-246">流程模型</span><span class="sxs-lookup"><span data-stu-id="e3835-246">Process model</span></span>

<span data-ttu-id="e3835-247">WebView2 使用与 Edge web 浏览器相同的进程模型。</span><span class="sxs-lookup"><span data-stu-id="e3835-247">WebView2 uses the same process model as the Edge web browser.</span></span> <span data-ttu-id="e3835-248">用户会话中每个指定的用户数据目录都有一个 Edge 浏览器进程，该进程将为指定用户数据目录的任何 WebView2 调用进程提供服务。</span><span class="sxs-lookup"><span data-stu-id="e3835-248">There is one Edge browser process per specified user data directory in a user session that will serve any WebView2 calling process that specifies that user data directory.</span></span> <span data-ttu-id="e3835-249">这意味着一个 Edge 浏览器进程可能正在为多个呼叫流程提供服务，并且一个呼叫进程可能正在使用多个 Edge 浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="e3835-249">This means one Edge browser process may be serving multiple calling processes and one calling process may be using multiple Edge browser processes.</span></span>

![dot-inline-dotgraph-2](media/dot-inline-dotgraph-2.png)

<span data-ttu-id="e3835-251">浏览器进程关闭时，将出现一些数量的呈现器进程。</span><span class="sxs-lookup"><span data-stu-id="e3835-251">Off of a browser process there will be some number of renderer processes.</span></span> <span data-ttu-id="e3835-252">根据需要创建这些类，以在不同的 WebViews 中服务潜在的多个帧。</span><span class="sxs-lookup"><span data-stu-id="e3835-252">These are created as necessary to service potentially multiple frames in different WebViews.</span></span> <span data-ttu-id="e3835-253">呈现器进程的数量因网站隔离浏览器功能和呈现在关联的 WebViews 中的独特断开的来源的数量而异。</span><span class="sxs-lookup"><span data-stu-id="e3835-253">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated WebViews.</span></span>

![dot-inline-dotgraph-3](media/dot-inline-dotgraph-3.png)

<span data-ttu-id="e3835-255">你可以使用 ProcessFailure 事件对这些浏览器和呈现器进程中的崩溃和挂起做出反应。</span><span class="sxs-lookup"><span data-stu-id="e3835-255">You can react to crashes and hangs in these browser and renderer processes using the ProcessFailure event.</span></span>

<span data-ttu-id="e3835-256">你可以使用 Close 方法安全地关闭关联的浏览器和呈现器进程。</span><span class="sxs-lookup"><span data-stu-id="e3835-256">You can safely shutdown associated browser and renderer processes using the Close method.</span></span>

## <span data-ttu-id="e3835-257">线程模型</span><span class="sxs-lookup"><span data-stu-id="e3835-257">Threading model</span></span>

<span data-ttu-id="e3835-258">WebView2 必须在 UI 线程上创建。</span><span class="sxs-lookup"><span data-stu-id="e3835-258">The WebView2 must be created on a UI thread.</span></span> <span data-ttu-id="e3835-259">专门使用消息泵的线程。</span><span class="sxs-lookup"><span data-stu-id="e3835-259">Specifically a thread with a message pump.</span></span> <span data-ttu-id="e3835-260">所有回调都将在该线程上发生，并且对 Web 视图的调用必须在该线程上完成。</span><span class="sxs-lookup"><span data-stu-id="e3835-260">All callbacks will occur on that thread and calls into the WebView must be done on that thread.</span></span> <span data-ttu-id="e3835-261">使用来自另一个线程的 Web 视图不安全。</span><span class="sxs-lookup"><span data-stu-id="e3835-261">It is not safe to use the WebView from another thread.</span></span>

<span data-ttu-id="e3835-262">回调包括事件处理程序和完成处理程序按顺序执行。</span><span class="sxs-lookup"><span data-stu-id="e3835-262">Callbacks including event handlers and completion handlers execute serially.</span></span> <span data-ttu-id="e3835-263">也就是说，如果你有一个事件处理程序正在运行并开始消息循环，则没有其他事件处理程序或完成回调将开始执行 reentrantly。</span><span class="sxs-lookup"><span data-stu-id="e3835-263">That is, if you have an event handler running and begin a message loop no other event handlers or completion callbacks will begin executing reentrantly.</span></span>

## <span data-ttu-id="e3835-264">安全</span><span class="sxs-lookup"><span data-stu-id="e3835-264">Security</span></span>

<span data-ttu-id="e3835-265">在使用 ExecuteScript、PostWebMessageAsJson、PostWebMessageAsString 或任何其他方法将信息发送到 Web 视图之前，请始终检查 Web 视图的 Source 属性。</span><span class="sxs-lookup"><span data-stu-id="e3835-265">Always check the Source property of the WebView before using ExecuteScript, PostWebMessageAsJson, PostWebMessageAsString, or any other method to send information into the WebView.</span></span> <span data-ttu-id="e3835-266">在导致导航的页面中，Web 视图可能会通过与页面或脚本交互的最终用户导航到另一个页面。</span><span class="sxs-lookup"><span data-stu-id="e3835-266">The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation.</span></span> <span data-ttu-id="e3835-267">同样，请小心处理 AddScriptToExecuteOnDocumentCreated。</span><span class="sxs-lookup"><span data-stu-id="e3835-267">Similarly, be very careful with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="e3835-268">所有将来的导航都将运行此脚本，如果它提供对仅适用于特定来源的信息的访问权限，则任何 HTML 文档都可能具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-268">All future navigations will run this script and if it provides access to information intended only for a certain origin, any HTML document may have access.</span></span>

<span data-ttu-id="e3835-269">检查 ExecuteScript 方法调用的结果（WebMessageReceived 事件）时，请始终检查发件人的源或从 Web 视图中的 HTML 文档接收信息的任何其他机制验证 HTML 文档的 URI 是否是你所期望的内容。</span><span class="sxs-lookup"><span data-stu-id="e3835-269">When examining the result of an ExecuteScript method call, a WebMessageReceived event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.</span></span>

<span data-ttu-id="e3835-270">构建要发送到 Web 视图的消息时，更喜欢使用 PostWebMessageAsJson 并使用 JSON 库构造 JSON 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="e3835-270">When constructing a message to send into a WebView, prefer using PostWebMessageAsJson and construct the JSON string parameter using a JSON library.</span></span> <span data-ttu-id="e3835-271">这将避免任何潜在的编码信息意外进入 JSON 字符串或脚本并确保任何攻击者控制的输入都不能修改 JSON 消息的其余部分或运行任意脚本。</span><span class="sxs-lookup"><span data-stu-id="e3835-271">This will avoid any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script.</span></span>

## <span data-ttu-id="e3835-272">字符串类型</span><span class="sxs-lookup"><span data-stu-id="e3835-272">String types</span></span>

<span data-ttu-id="e3835-273">字符串输出参数是 LPWSTR null 终止的字符串。</span><span class="sxs-lookup"><span data-stu-id="e3835-273">String out parameters are LPWSTR null terminated strings.</span></span> <span data-ttu-id="e3835-274">被调用方使用 CoTaskMemAlloc 分配字符串。</span><span class="sxs-lookup"><span data-stu-id="e3835-274">The callee allocates the string using CoTaskMemAlloc.</span></span> <span data-ttu-id="e3835-275">所有权转移到呼叫方，由呼叫方负责使用 CoTaskMemFree 释放内存。</span><span class="sxs-lookup"><span data-stu-id="e3835-275">Ownership is transferred to the caller and it is up to the caller to free the memory using CoTaskMemFree.</span></span>

<span data-ttu-id="e3835-276">参数中的字符串是 LPCWSTR null 终止的字符串。</span><span class="sxs-lookup"><span data-stu-id="e3835-276">String in parameters are LPCWSTR null terminated strings.</span></span> <span data-ttu-id="e3835-277">调用方确保字符串在同步函数调用期间有效。</span><span class="sxs-lookup"><span data-stu-id="e3835-277">The caller ensures the string is valid for the duration of the synchronous function call.</span></span> <span data-ttu-id="e3835-278">如果被调用方需要在函数调用完成后将该值保留到某个点，则被调用方必须分配其自己的字符串值副本。</span><span class="sxs-lookup"><span data-stu-id="e3835-278">If the callee needs to retain that value to some point after the function call completes, the callee must allocate its own copy of the string value.</span></span>

## <span data-ttu-id="e3835-279">URI 和 JSON 分析</span><span class="sxs-lookup"><span data-stu-id="e3835-279">URI and JSON parsing</span></span>

<span data-ttu-id="e3835-280">各种方法以字符串形式提供或接受 Uri 和 JSON。</span><span class="sxs-lookup"><span data-stu-id="e3835-280">Various methods provide or accept URIs and JSON as strings.</span></span> <span data-ttu-id="e3835-281">请使用你的首选库来分析和生成这些字符串。</span><span class="sxs-lookup"><span data-stu-id="e3835-281">Please use your own preferred library for parsing and generating these strings.</span></span>

<span data-ttu-id="e3835-282">如果 WinRT 适用于你的应用，则可以使用 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` 分析或生成 JSON 字符串， `RuntimeClass_Windows_Foundation_Uri` 或者 `IUriRuntimeClassFactory` 分析和生成 uri。</span><span class="sxs-lookup"><span data-stu-id="e3835-282">If WinRT is available for your app you can use `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` to parse and produce URIs.</span></span> <span data-ttu-id="e3835-283">这两个功能都在 Win32 应用中使用。</span><span class="sxs-lookup"><span data-stu-id="e3835-283">Both of these work in Win32 apps.</span></span>

<span data-ttu-id="e3835-284">如果你使用 IUri 和 CreateUri 来分析 Uri，你可能希望使用以下 URI 创建标志使 CreateUri 行为与 Web 视图中的 URI 分析更密切匹配：</span><span class="sxs-lookup"><span data-stu-id="e3835-284">If you use IUri and CreateUri to parse URIs you may want to use the following URI creation flags to have CreateUri behavior more closely match the URI parsing in the WebView:</span></span> `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## <span data-ttu-id="e3835-285">调试</span><span class="sxs-lookup"><span data-stu-id="e3835-285">Debugging</span></span>

<span data-ttu-id="e3835-286">打开具有普通快捷方式的 DevTools： `F12` 或 `Ctrl+Shift+I` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-286">Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`.</span></span> <span data-ttu-id="e3835-287">在 `--auto-open-devtools-for-tabs` 首次创建 Web 视图时，可以使用 command 参数开关让 DevTools 窗口立即打开。</span><span class="sxs-lookup"><span data-stu-id="e3835-287">You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView.</span></span> <span data-ttu-id="e3835-288">有关如何向浏览器进程提供其他命令行参数，请参阅 CreateCoreWebView2Host 文档。</span><span class="sxs-lookup"><span data-stu-id="e3835-288">See CreateCoreWebView2Host documentation for how to provide additional command line arguments to the browser process.</span></span> <span data-ttu-id="e3835-289">签出 LoaderOverride 注册表项，在 CreateCoreWebView2Host 文档中无需修改你的应用程序，即可试用不同版本的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="e3835-289">Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateCoreWebView2Host documentation.</span></span>

## <span data-ttu-id="e3835-290">版本控制</span><span class="sxs-lookup"><span data-stu-id="e3835-290">Versioning</span></span>

<span data-ttu-id="e3835-291">在使用特定版本的 SDK 构建你的应用后，你的应用可能会使用已安装的旧版本或更高版本的浏览器二进制文件运行。</span><span class="sxs-lookup"><span data-stu-id="e3835-291">After you've used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.</span></span> <span data-ttu-id="e3835-292">在 WebView2 版本1.0.0.0 之前，可能会在更新期间发生中断更改，这些更改将阻止你的 SDK 使用安装的浏览器二进制文件的不同版本。</span><span class="sxs-lookup"><span data-stu-id="e3835-292">Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that will prevent your SDK from working with different versions of installed browser binaries.</span></span> <span data-ttu-id="e3835-293">在版本1.0.0.0 后，SDK 的不同版本可以按照以下最佳做法使用安装的浏览器的不同版本：</span><span class="sxs-lookup"><span data-stu-id="e3835-293">After version 1.0.0.0 different versions of the SDK can work with different versions of the installed browser by following these best practices:</span></span>

<span data-ttu-id="e3835-294">若要对 API 进行重大更改，请确保在调用 DLL 导出 CreateCoreWebView2Environment 时和在任何 CoreWebView2 对象上调用 QueryInterface 时检查是否失败。</span><span class="sxs-lookup"><span data-stu-id="e3835-294">To account for breaking changes to the API be sure to check for failure when calling the DLL export CreateCoreWebView2Environment and when calling QueryInterface on any CoreWebView2 object.</span></span> <span data-ttu-id="e3835-295">E_NOINTERFACE 的返回值可指示 SDK 与 Edge 浏览器二进制文件不兼容。</span><span class="sxs-lookup"><span data-stu-id="e3835-295">A return value of E_NOINTERFACE can indicate the SDK is not compatible with the Edge browser binaries.</span></span>

<span data-ttu-id="e3835-296">从 QueryInterface 检查失败还将考虑 SDK 比 Edge 浏览器的版本更新的情况，并且你的应用尝试使用 Edge 浏览器不兼容的接口。</span><span class="sxs-lookup"><span data-stu-id="e3835-296">Checking for failure from QueryInterface will also account for cases where the SDK is newer than the version of the Edge browser and your app attempts to use an interface of which the Edge browser is unaware.</span></span>

<span data-ttu-id="e3835-297">当接口不可用时，你可以考虑禁用关联的功能（如果可能），或者向最终用户通知他们需要更新其浏览器。</span><span class="sxs-lookup"><span data-stu-id="e3835-297">When an interface is unavailable, you can consider disabling the associated feature if possible, or otherwise informing the end user they need to update their browser.</span></span>

## <span data-ttu-id="e3835-298">成员</span><span class="sxs-lookup"><span data-stu-id="e3835-298">Members</span></span>

#### <span data-ttu-id="e3835-299">get_Settings</span><span class="sxs-lookup"><span data-stu-id="e3835-299">get_Settings</span></span> 

<span data-ttu-id="e3835-300">ICoreWebView2Settings 对象包含运行的 Web 视图的各种可修改设置。</span><span class="sxs-lookup"><span data-stu-id="e3835-300">The ICoreWebView2Settings object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="e3835-301">公共 HRESULT [get_Settings](#get_settings)（ICoreWebView2Settings \* \* 设置）</span><span class="sxs-lookup"><span data-stu-id="e3835-301">public HRESULT [get_Settings](#get_settings)(ICoreWebView2Settings \*\* settings)</span></span>

#### <span data-ttu-id="e3835-302">get_Source</span><span class="sxs-lookup"><span data-stu-id="e3835-302">get_Source</span></span> 

<span data-ttu-id="e3835-303">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="e3835-303">The URI of the current top level document.</span></span>

> <span data-ttu-id="e3835-304">公共 HRESULT [get_Source](#get_source)（LPWSTR \* uri）</span><span class="sxs-lookup"><span data-stu-id="e3835-304">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="e3835-305">在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 SourceChanged 事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="e3835-305">This value potentially changes as a part of the SourceChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="e3835-306">它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。</span><span class="sxs-lookup"><span data-stu-id="e3835-306">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

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
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### <span data-ttu-id="e3835-307">导航</span><span class="sxs-lookup"><span data-stu-id="e3835-307">Navigate</span></span> 

<span data-ttu-id="e3835-308">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="e3835-308">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="e3835-309">公共 HRESULT[导航](#navigate)（LPCWSTR uri）</span><span class="sxs-lookup"><span data-stu-id="e3835-309">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="e3835-310">有关详细信息，请参阅导航事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-310">See the navigation events for more information.</span></span> <span data-ttu-id="e3835-311">请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。</span><span class="sxs-lookup"><span data-stu-id="e3835-311">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    int length = GetWindowTextLength(m_toolbar->addressBarWindow);
    std::wstring uri(length, 0);
    PWSTR buffer = const_cast<PWSTR>(uri.data());
    GetWindowText(m_toolbar->addressBarWindow, buffer, length + 1);

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

#### <span data-ttu-id="e3835-312">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="e3835-312">NavigateToString</span></span> 

<span data-ttu-id="e3835-313">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="e3835-313">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="e3835-314">公共 HRESULT [NavigateToString](#navigatetostring)（LPCWSTR htmlContent）</span><span class="sxs-lookup"><span data-stu-id="e3835-314">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="e3835-315">HtmlContent 参数不能大于 2 MB 的字符。</span><span class="sxs-lookup"><span data-stu-id="e3835-315">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="e3835-316">新页面的来源将显示为 "空白"。</span><span class="sxs-lookup"><span data-stu-id="e3835-316">The origin of the new page will be about:blank.</span></span>

```cpp
            static const PCWSTR htmlContent =
              L"<h1>Domain Blocked</h1>"
              L"<p>You've attempted to navigate to a domain in the blocked "
              L"sites list. Press back to return to the previous page.</p>";
            CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="e3835-317">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-317">add_NavigationStarting</span></span> 

<span data-ttu-id="e3835-318">为 NavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-318">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="e3835-319">public HRESULT [add_NavigationStarting](#add_navigationstarting)（[ICoreWebView2NavigationStartingEventHandler](ICoreWebView2NavigationStartingEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-319">public HRESULT [add_NavigationStarting](#add_navigationstarting)([ICoreWebView2NavigationStartingEventHandler](ICoreWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-320">当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="e3835-320">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="e3835-321">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="e3835-321">This will fire for redirects as well.</span></span>

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

#### <span data-ttu-id="e3835-322">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-322">remove_NavigationStarting</span></span> 

<span data-ttu-id="e3835-323">删除以前使用 add_NavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-323">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="e3835-324">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-324">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-325">add_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="e3835-325">add_ContentLoading</span></span> 

<span data-ttu-id="e3835-326">为 ContentLoading 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-326">Add an event handler for the ContentLoading event.</span></span>

> <span data-ttu-id="e3835-327">public HRESULT [add_ContentLoading](#add_contentloading)（[ICoreWebView2ContentLoadingEventHandler](ICoreWebView2ContentLoadingEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-327">public HRESULT [add_ContentLoading](#add_contentloading)([ICoreWebView2ContentLoadingEventHandler](ICoreWebView2ContentLoadingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-328">ContentLoading 在加载任何内容之前激发，包括使用 AddScriptToExecuteOnDocumentCreated ContentLoading 添加的脚本在同一页面导航（如通过片段导航或历史记录）发生时不会触发。</span><span class="sxs-lookup"><span data-stu-id="e3835-328">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="e3835-329">这将遵循 NavigationStarting 和 SourceChanged 事件，并在 HistoryChanged 和 NavigationCompleted 事件之前。</span><span class="sxs-lookup"><span data-stu-id="e3835-329">This follows the NavigationStarting and SourceChanged events and precedes the HistoryChanged and NavigationCompleted events.</span></span>

#### <span data-ttu-id="e3835-330">remove_ContentLoading</span><span class="sxs-lookup"><span data-stu-id="e3835-330">remove_ContentLoading</span></span> 

<span data-ttu-id="e3835-331">删除以前使用 add_ContentLoading 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-331">Remove an event handler previously added with add_ContentLoading.</span></span>

> <span data-ttu-id="e3835-332">public HRESULT [remove_ContentLoading](#remove_contentloading)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-332">public HRESULT [remove_ContentLoading](#remove_contentloading)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-333">add_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-333">add_SourceChanged</span></span> 

<span data-ttu-id="e3835-334">Source 属性更改时将触发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="e3835-334">SourceChanged fires when the Source property changes.</span></span>

> <span data-ttu-id="e3835-335">public HRESULT [add_SourceChanged](#add_sourcechanged)（[ICoreWebView2SourceChangedEventHandler](ICoreWebView2SourceChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-335">public HRESULT [add_SourceChanged](#add_sourcechanged)([ICoreWebView2SourceChangedEventHandler](ICoreWebView2SourceChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-336">导航到其他网站或片段导航时，将引发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="e3835-336">SourceChanged fires for navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="e3835-337">对于其他类型的导航（如页面重新加载或 pushState，其 URL 与当前页面相同），不会引发此类导航。</span><span class="sxs-lookup"><span data-stu-id="e3835-337">It will not fires for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span> <span data-ttu-id="e3835-338">SourceChanged 将在 ContentLoading 之前激发，以便导航到新文档。</span><span class="sxs-lookup"><span data-stu-id="e3835-338">SourceChanged fires before ContentLoading for navigation to a new document.</span></span> <span data-ttu-id="e3835-339">为 SourceChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-339">Add an event handler for the SourceChanged event.</span></span> 

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
                SetWindowText(m_toolbar->addressBarWindow, uri.get());

                return S_OK;
            })
            .Get(),
        &m_sourceChangedToken));
```

#### <span data-ttu-id="e3835-340">remove_SourceChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-340">remove_SourceChanged</span></span> 

<span data-ttu-id="e3835-341">删除以前使用 add_SourceChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-341">Remove an event handler previously added with add_SourceChanged.</span></span>

> <span data-ttu-id="e3835-342">public HRESULT [remove_SourceChanged](#remove_sourcechanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-342">public HRESULT [remove_SourceChanged](#remove_sourcechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-343">add_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-343">add_HistoryChanged</span></span> 

<span data-ttu-id="e3835-344">历史记录更改侦听顶级文档的导航历史记录更改。</span><span class="sxs-lookup"><span data-stu-id="e3835-344">HistoryChange listen to the change of navigation history for the top level document.</span></span>

> <span data-ttu-id="e3835-345">public HRESULT [add_HistoryChanged](#add_historychanged)（[ICoreWebView2HistoryChangedEventHandler](ICoreWebView2HistoryChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-345">public HRESULT [add_HistoryChanged](#add_historychanged)([ICoreWebView2HistoryChangedEventHandler](ICoreWebView2HistoryChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-346">使用历史记录更改检查 get_CanGoBack/get_CanGoForward 值是否已更改。</span><span class="sxs-lookup"><span data-stu-id="e3835-346">Use HistoryChange to check if get_CanGoBack/get_CanGoForward value has changed.</span></span> <span data-ttu-id="e3835-347">使用 GoBack/GoForward 时也会触发 HistoryChanged。</span><span class="sxs-lookup"><span data-stu-id="e3835-347">HistoryChanged also fires for using GoBack/GoForward.</span></span> <span data-ttu-id="e3835-348">HistoryChanged 在 SourceChanged 和 ContentLoading 后激发。</span><span class="sxs-lookup"><span data-stu-id="e3835-348">HistoryChanged fires after SourceChanged and ContentLoading.</span></span> <span data-ttu-id="e3835-349">为 HistoryChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-349">Add an event handler for the HistoryChanged event.</span></span> 

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
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);

                return S_OK;
            })
            .Get(),
        &m_historyChangedToken));
```

#### <span data-ttu-id="e3835-350">remove_HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-350">remove_HistoryChanged</span></span> 

<span data-ttu-id="e3835-351">删除以前使用 add_HistoryChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-351">Remove an event handler previously added with add_HistoryChanged.</span></span>

> <span data-ttu-id="e3835-352">public HRESULT [remove_HistoryChanged](#remove_historychanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-352">public HRESULT [remove_HistoryChanged](#remove_historychanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-353">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="e3835-353">add_NavigationCompleted</span></span> 

<span data-ttu-id="e3835-354">为 NavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-354">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="e3835-355">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)（[ICoreWebView2NavigationCompletedEventHandler](ICoreWebView2NavigationCompletedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-355">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([ICoreWebView2NavigationCompletedEventHandler](ICoreWebView2NavigationCompletedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-356">当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-356">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

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
                    CORE_WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == CORE_WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### <span data-ttu-id="e3835-357">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="e3835-357">remove_NavigationCompleted</span></span> 

<span data-ttu-id="e3835-358">删除以前使用 add_NavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-358">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="e3835-359">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-359">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-360">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-360">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="e3835-361">为 FrameNavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-361">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="e3835-362">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)（[ICoreWebView2NavigationStartingEventHandler](ICoreWebView2NavigationStartingEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-362">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([ICoreWebView2NavigationStartingEventHandler](ICoreWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-363">当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="e3835-363">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="e3835-364">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="e3835-364">This will fire for redirects as well.</span></span>

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

#### <span data-ttu-id="e3835-365">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="e3835-365">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="e3835-366">删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-366">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="e3835-367">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-367">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-368">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="e3835-368">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="e3835-369">为 ScriptDialogOpening 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-369">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="e3835-370">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)（[ICoreWebView2ScriptDialogOpeningEventHandler](ICoreWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-370">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([ICoreWebView2ScriptDialogOpeningEventHandler](ICoreWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-371">将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-371">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span> <span data-ttu-id="e3835-372">仅当 ICoreWebView2Settings：： AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发。</span><span class="sxs-lookup"><span data-stu-id="e3835-372">This event only fires if the ICoreWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span> <span data-ttu-id="e3835-373">ScriptDialogOpening 事件可用于取消对话框或使用自定义对话框替换默认对话框。</span><span class="sxs-lookup"><span data-stu-id="e3835-373">The ScriptDialogOpening event can be used to suppress dialogs or replace default dialogs with custom dialogs.</span></span>

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
            CORE_WEBVIEW2_SCRIPT_DIALOG_KIND type;
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
                /* readonly */ type != CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
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

#### <span data-ttu-id="e3835-374">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="e3835-374">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="e3835-375">删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-375">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="e3835-376">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-376">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-377">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-377">add_PermissionRequested</span></span> 

<span data-ttu-id="e3835-378">为 Webview.permissionrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-378">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="e3835-379">public HRESULT [add_PermissionRequested](#add_permissionrequested)（[ICoreWebView2PermissionRequestedEventHandler](ICoreWebView2PermissionRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-379">public HRESULT [add_PermissionRequested](#add_permissionrequested)([ICoreWebView2PermissionRequestedEventHandler](ICoreWebView2PermissionRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-380">在 Web 视图中的内容请求访问某些权限资源的权限时引发。</span><span class="sxs-lookup"><span data-stu-id="e3835-380">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

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
        CORE_WEBVIEW2_PERMISSION_KIND kind = CORE_WEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION;
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

        CORE_WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? CORE_WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? CORE_WEBVIEW2_PERMISSION_STATE_DENY
            :                     CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### <span data-ttu-id="e3835-381">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-381">remove_PermissionRequested</span></span> 

<span data-ttu-id="e3835-382">删除以前使用 add_PermissionRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-382">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="e3835-383">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-383">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-384">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="e3835-384">add_ProcessFailed</span></span> 

<span data-ttu-id="e3835-385">为 ProcessFailed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-385">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="e3835-386">public HRESULT [add_ProcessFailed](#add_processfailed)（[ICoreWebView2ProcessFailedEventHandler](ICoreWebView2ProcessFailedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-386">public HRESULT [add_ProcessFailed](#add_processfailed)([ICoreWebView2ProcessFailedEventHandler](ICoreWebView2ProcessFailedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-387">当 Web 视图进程意外终止或停止响应时激发。</span><span class="sxs-lookup"><span data-stu-id="e3835-387">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<ICoreWebView2ProcessFailedEventHandler>(
            [this](ICoreWebView2* sender,
                ICoreWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        CORE_WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == CORE_WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
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
        else if (failureType == CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE)
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
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### <span data-ttu-id="e3835-388">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="e3835-388">remove_ProcessFailed</span></span> 

<span data-ttu-id="e3835-389">删除以前使用 add_ProcessFailed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-389">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="e3835-390">public HRESULT [remove_ProcessFailed](#remove_processfailed)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-390">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-391">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="e3835-391">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="e3835-392">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="e3835-392">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="e3835-393">公共 HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)（LPCWSTR JavaScript，[ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="e3835-393">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript,[ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](ICoreWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="e3835-394">插入的脚本将应用于所有未来的顶级文档和子框架导航，直到使用 RemoveScriptToExecuteOnDocumentCreated 删除。</span><span class="sxs-lookup"><span data-stu-id="e3835-394">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="e3835-395">这是异步应用的，你必须等待完成处理程序运行，然后才能确保脚本已准备好在将来的导航上执行。</span><span class="sxs-lookup"><span data-stu-id="e3835-395">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="e3835-396">请注意，如果 HTML 文档通过[沙盒](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)属性或[内容安全策略 HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)进行了某种类型的沙盒，则会影响在此处运行脚本。</span><span class="sxs-lookup"><span data-stu-id="e3835-396">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="e3835-397">例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-397">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

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

#### <span data-ttu-id="e3835-398">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="e3835-398">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="e3835-399">删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="e3835-399">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="e3835-400">公共 HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)（LPCWSTR id）</span><span class="sxs-lookup"><span data-stu-id="e3835-400">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="e3835-401">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="e3835-401">ExecuteScript</span></span> 

<span data-ttu-id="e3835-402">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="e3835-402">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="e3835-403">公共 HRESULT [ExecuteScript](#executescript)（LPCWSTR JavaScript，[ICoreWebView2ExecuteScriptCompletedHandler](ICoreWebView2ExecuteScriptCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="e3835-403">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript,[ICoreWebView2ExecuteScriptCompletedHandler](ICoreWebView2ExecuteScriptCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="e3835-404">这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-404">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="e3835-405">结果值是一个 JSON 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="e3835-405">The result value is a JSON encoded string.</span></span> <span data-ttu-id="e3835-406">如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。</span><span class="sxs-lookup"><span data-stu-id="e3835-406">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="e3835-407">请注意，没有显式返回值的函数将返回 undefined。</span><span class="sxs-lookup"><span data-stu-id="e3835-407">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="e3835-408">如果执行的脚本引发了未处理的异常，则结果也为 "null"。</span><span class="sxs-lookup"><span data-stu-id="e3835-408">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="e3835-409">此方法是异步应用的。</span><span class="sxs-lookup"><span data-stu-id="e3835-409">This method is applied asynchronously.</span></span> <span data-ttu-id="e3835-410">如果在 web 视图位于一个文档上时进行调用，并且在执行该调用之后但在执行 JavaScript 之前发生导航，则不会执行该脚本，并且将使用 E_FAIL 的 errorCode 参数调用该处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-410">If the call is made while the webview is on one document, and a navigation occurs after the call is made but before the JavaScript is executed, then the script will not be executed and the handler will be called with E_FAIL for its errorCode parameter.</span></span> <span data-ttu-id="e3835-411">即使 IsScriptEnabled 设置为 FALSE，ExecuteScript 仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="e3835-411">ExecuteScript will work even if IsScriptEnabled is set to FALSE.</span></span>

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

#### <span data-ttu-id="e3835-412">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="e3835-412">CapturePreview</span></span> 

<span data-ttu-id="e3835-413">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="e3835-413">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="e3835-414">public HRESULT [CapturePreview](#capturepreview)（[CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format) ImageFormat、IStream \* imageStream、[ICoreWebView2CapturePreviewCompletedHandler](ICoreWebView2CapturePreviewCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="e3835-414">public HRESULT [CapturePreview](#capturepreview)([CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format) imageFormat,IStream \* imageStream,[ICoreWebView2CapturePreviewCompletedHandler](ICoreWebView2CapturePreviewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="e3835-415">指定具有 imageFormat 参数的图像的格式。</span><span class="sxs-lookup"><span data-stu-id="e3835-415">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="e3835-416">生成的图像二进制数据将写入所提供的 imageStream 参数。</span><span class="sxs-lookup"><span data-stu-id="e3835-416">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="e3835-417">当 CapturePreview 完成写入流时，将调用所提供的处理程序参数上的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-417">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

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
            CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
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

#### <span data-ttu-id="e3835-418">重载</span><span class="sxs-lookup"><span data-stu-id="e3835-418">Reload</span></span> 

<span data-ttu-id="e3835-419">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="e3835-419">Reload the current page.</span></span>

> <span data-ttu-id="e3835-420">公共 HRESULT[重装](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="e3835-420">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="e3835-421">这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-421">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="e3835-422">但是，将不会修改后退/前进历史记录。</span><span class="sxs-lookup"><span data-stu-id="e3835-422">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="e3835-423">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="e3835-423">PostWebMessageAsJson</span></span> 

<span data-ttu-id="e3835-424">将指定的 webMessage 发布到此 Web 视图中的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="e3835-424">Post the specified webMessage to the top level document in this WebView.</span></span>

> <span data-ttu-id="e3835-425">公共 HRESULT [PostWebMessageAsJson](#postwebmessageasjson)（LPCWSTR webMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="e3835-425">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="e3835-426">将激发顶级文档的 "chrome" 消息事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-426">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="e3835-427">该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件：</span><span class="sxs-lookup"><span data-stu-id="e3835-427">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span> 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 <span data-ttu-id="e3835-428">事件参数是的实例 `MessageEvent` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-428">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="e3835-429">ICoreWebView2Settings：： IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并显示 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="e3835-429">The ICoreWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="e3835-430">事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="e3835-430">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="e3835-431">事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-431">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="e3835-432">有关从 web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 SetWebMessageReceivedEventHandler。</span><span class="sxs-lookup"><span data-stu-id="e3835-432">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="e3835-433">此消息将异步发送。</span><span class="sxs-lookup"><span data-stu-id="e3835-433">This message is sent asynchronously.</span></span> <span data-ttu-id="e3835-434">如果在将邮件发布到页面之前发生导航，则不会发送邮件。</span><span class="sxs-lookup"><span data-stu-id="e3835-434">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

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

#### <span data-ttu-id="e3835-435">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="e3835-435">PostWebMessageAsString</span></span> 

<span data-ttu-id="e3835-436">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e3835-436">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="e3835-437">公共 HRESULT [PostWebMessageAsString](#postwebmessageasstring)（LPCWSTR webMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="e3835-437">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="e3835-438">此行为与 PostWebMessageAsJson 完全相同，但 `window.chrome.webview` 消息事件参数的 data 属性将是与 webMessageAsString 具有相同值的字符串。</span><span class="sxs-lookup"><span data-stu-id="e3835-438">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="e3835-439">如果想要通过简单的字符串而不是 JSON 对象进行通信，请使用此操作，而不是 PostWebMessageAsJson。</span><span class="sxs-lookup"><span data-stu-id="e3835-439">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="e3835-440">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="e3835-440">add_WebMessageReceived</span></span> 

<span data-ttu-id="e3835-441">当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-441">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="e3835-442">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)（[ICoreWebView2WebMessageReceivedEventHandler](ICoreWebView2WebMessageReceivedEventHandler.md) \* 处理程序，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-442">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([ICoreWebView2WebMessageReceivedEventHandler](ICoreWebView2WebMessageReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-443">PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。</span><span class="sxs-lookup"><span data-stu-id="e3835-443">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

```cpp
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

 <span data-ttu-id="e3835-444">调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 的对象参数调用通过此 SetWebMessageReceivedEventHandler 方法设置的[ICoreWebView2WebMessageReceivedEventHandler](ICoreWebView2WebMessageReceivedEventHandler.md) 。</span><span class="sxs-lookup"><span data-stu-id="e3835-444">When postMessage is called, the [ICoreWebView2WebMessageReceivedEventHandler](ICoreWebView2WebMessageReceivedEventHandler.md) set via this SetWebMessageReceivedEventHandler method will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

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

#### <span data-ttu-id="e3835-445">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="e3835-445">remove_WebMessageReceived</span></span> 

<span data-ttu-id="e3835-446">删除以前使用 add_WebMessageReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-446">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="e3835-447">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-447">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-448">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="e3835-448">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="e3835-449">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-449">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="e3835-450">公共 HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)（LPCWSTR 方法，LPCWSTR ParametersAsJson，[ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](ICoreWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="e3835-450">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName,LPCWSTR parametersAsJson,[ICoreWebView2CallDevToolsProtocolMethodCompletedHandler](ICoreWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="e3835-451">有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。</span><span class="sxs-lookup"><span data-stu-id="e3835-451">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="e3835-452">"方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-452">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="e3835-453">ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。</span><span class="sxs-lookup"><span data-stu-id="e3835-453">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="e3835-454">当方法异步完成时，将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-454">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="e3835-455">将使用方法的返回对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="e3835-455">Invoke will be called with the method's return object as a JSON string.</span></span>

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

#### <span data-ttu-id="e3835-456">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="e3835-456">get_BrowserProcessId</span></span> 

<span data-ttu-id="e3835-457">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="e3835-457">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="e3835-458">公共 HRESULT [get_BrowserProcessId](#get_browserprocessid)（UINT32 \* 值）</span><span class="sxs-lookup"><span data-stu-id="e3835-458">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="e3835-459">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="e3835-459">get_CanGoBack</span></span> 

<span data-ttu-id="e3835-460">如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="e3835-460">Returns true if the webview can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="e3835-461">public HRESULT [get_CanGoBack](#get_cangoback)（BOOL \* CanGoBack）</span><span class="sxs-lookup"><span data-stu-id="e3835-461">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="e3835-462">如果 get_CanGoBack 更改值，将引发 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-462">The HistoryChanged event will fire if get_CanGoBack changes value.</span></span>

#### <span data-ttu-id="e3835-463">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="e3835-463">get_CanGoForward</span></span> 

<span data-ttu-id="e3835-464">如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="e3835-464">Returns true if the webview can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="e3835-465">public HRESULT [get_CanGoForward](#get_cangoforward)（BOOL \* CanGoForward）</span><span class="sxs-lookup"><span data-stu-id="e3835-465">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="e3835-466">如果 get_CanGoForward 更改值，将引发 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-466">The HistoryChanged event will fire if get_CanGoForward changes value.</span></span>

#### <span data-ttu-id="e3835-467">GoBack</span><span class="sxs-lookup"><span data-stu-id="e3835-467">GoBack</span></span> 

<span data-ttu-id="e3835-468">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="e3835-468">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="e3835-469">公共 HRESULT [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="e3835-469">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="e3835-470">GoForward</span><span class="sxs-lookup"><span data-stu-id="e3835-470">GoForward</span></span> 

<span data-ttu-id="e3835-471">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="e3835-471">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="e3835-472">公共 HRESULT [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="e3835-472">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="e3835-473">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="e3835-473">GetDevToolsProtocolEventReceiver</span></span> 

<span data-ttu-id="e3835-474">获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。</span><span class="sxs-lookup"><span data-stu-id="e3835-474">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>

> <span data-ttu-id="e3835-475">public HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)（LPCWSTR 名称 =[ICoreWebView2DevToolsProtocolEventReceiver](ICoreWebView2DevToolsProtocolEventReceiver.md) \* \* 接收器）</span><span class="sxs-lookup"><span data-stu-id="e3835-475">public HRESULT [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(LPCWSTR eventName,[ICoreWebView2DevToolsProtocolEventReceiver](ICoreWebView2DevToolsProtocolEventReceiver.md) \*\* receiver)</span></span>

<span data-ttu-id="e3835-476">事件名称参数是该事件的格式的完整名称 `{domain}.{event}` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-476">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="e3835-477">有关 DevTools 协议事件描述和事件参数的列表，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。</span><span class="sxs-lookup"><span data-stu-id="e3835-477">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list of DevTools Protocol events description, and event args.</span></span>

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

#### <span data-ttu-id="e3835-478">停止</span><span class="sxs-lookup"><span data-stu-id="e3835-478">Stop</span></span> 

<span data-ttu-id="e3835-479">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="e3835-479">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="e3835-480">公共 HRESULT[停止](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="e3835-480">public HRESULT [Stop](#stop)()</span></span>

<span data-ttu-id="e3835-481">不会停止脚本。</span><span class="sxs-lookup"><span data-stu-id="e3835-481">Does not stop scripts.</span></span>

#### <span data-ttu-id="e3835-482">add_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-482">add_NewWindowRequested</span></span> 

<span data-ttu-id="e3835-483">为 Webview.newwindowrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-483">Add an event handler for the NewWindowRequested event.</span></span>

> <span data-ttu-id="e3835-484">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)（[ICoreWebView2NewWindowRequestedEventHandler](ICoreWebView2NewWindowRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-484">public HRESULT [add_NewWindowRequested](#add_newwindowrequested)([ICoreWebView2NewWindowRequestedEventHandler](ICoreWebView2NewWindowRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-485">在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。</span><span class="sxs-lookup"><span data-stu-id="e3835-485">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span> <span data-ttu-id="e3835-486">应用可以传递将被视为打开的窗口的目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="e3835-486">The app can pass a target webview that will be considered the opened window.</span></span>

```cpp
    // Register a handler for the NewWindowRequested event.
    // This handler will defer the event, create a new app window, and then once the
    // new window is ready, it'll provide that new window's WebView as the response to
    // the request.
    CHECK_FAILURE(m_webView->add_NewWindowRequested(
        Callback<ICoreWebView2NewWindowRequestedEventHandler>(
            [this](
                ICoreWebView2* sender,
                ICoreWebView2NewWindowRequestedEventArgs* args) {
                wil::com_ptr<ICoreWebView2Deferral> deferral;
                CHECK_FAILURE(args->GetDeferral(&deferral));

                auto newAppWindow = new AppWindow(L"");
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

#### <span data-ttu-id="e3835-487">remove_NewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-487">remove_NewWindowRequested</span></span> 

<span data-ttu-id="e3835-488">删除以前使用 add_NewWindowRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-488">Remove an event handler previously added with add_NewWindowRequested.</span></span>

> <span data-ttu-id="e3835-489">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-489">public HRESULT [remove_NewWindowRequested](#remove_newwindowrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-490">add_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-490">add_DocumentTitleChanged</span></span> 

<span data-ttu-id="e3835-491">为 DocumentTitleChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-491">Add an event handler for the DocumentTitleChanged event.</span></span>

> <span data-ttu-id="e3835-492">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)（[ICoreWebView2DocumentTitleChangedEventHandler](ICoreWebView2DocumentTitleChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-492">public HRESULT [add_DocumentTitleChanged](#add_documenttitlechanged)([ICoreWebView2DocumentTitleChangedEventHandler](ICoreWebView2DocumentTitleChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-493">当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-493">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

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

#### <span data-ttu-id="e3835-494">remove_DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-494">remove_DocumentTitleChanged</span></span> 

<span data-ttu-id="e3835-495">删除以前使用 add_DocumentTitleChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-495">Remove an event handler previously added with add_DocumentTitleChanged.</span></span>

> <span data-ttu-id="e3835-496">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-496">public HRESULT [remove_DocumentTitleChanged](#remove_documenttitlechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-497">get_DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="e3835-497">get_DocumentTitle</span></span> 

<span data-ttu-id="e3835-498">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="e3835-498">The title for the current top level document.</span></span>

> <span data-ttu-id="e3835-499">公共 HRESULT [get_DocumentTitle](#get_documenttitle)（LPWSTR \* 标题）</span><span class="sxs-lookup"><span data-stu-id="e3835-499">public HRESULT [get_DocumentTitle](#get_documenttitle)(LPWSTR \* title)</span></span>

<span data-ttu-id="e3835-500">如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。</span><span class="sxs-lookup"><span data-stu-id="e3835-500">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

#### <span data-ttu-id="e3835-501">AddRemoteObject</span><span class="sxs-lookup"><span data-stu-id="e3835-501">AddRemoteObject</span></span> 

<span data-ttu-id="e3835-502">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="e3835-502">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="e3835-503">public HRESULT [AddRemoteObject](#addremoteobject)（LPCWSTR NAME，VARIANT \* object）</span><span class="sxs-lookup"><span data-stu-id="e3835-503">public HRESULT [AddRemoteObject](#addremoteobject)(LPCWSTR name,VARIANT \* object)</span></span>

<span data-ttu-id="e3835-504">通过将主机对象作为远程对象代理公开 `window.chrome.webview.remoteObjects.<name>` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-504">Host objects are exposed as remote object proxies via `window.chrome.webview.remoteObjects.<name>`.</span></span> <span data-ttu-id="e3835-505">远程对象代理承诺并将解析为表示主机对象的对象。</span><span class="sxs-lookup"><span data-stu-id="e3835-505">Remote object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="e3835-506">如果应用未添加具有名称的对象，则该承诺将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e3835-506">The promise is rejected if the app has not added an object with the name.</span></span> <span data-ttu-id="e3835-507">当 JavaScript 代码访问对象的属性或方法时，承诺将返回，它将解析为属性或方法从主机返回的值，或者在出现错误时被拒绝，例如在对象上没有此类属性或参数无效的情况下被拒绝。</span><span class="sxs-lookup"><span data-stu-id="e3835-507">When JavaScript code access a property or method of the object, a promise is return, which will resolve to the value returned from the host for the property or method, or rejected in case of error such as there is no such property or method on the object or parameters are invalid.</span></span> <span data-ttu-id="e3835-508">例如，当应用程序代码执行以下操作时：</span><span class="sxs-lookup"><span data-stu-id="e3835-508">For example, when the application code does the following:</span></span> 

```cpp
VARIANT object;
object.vt = VT_DISPATCH;
object.pdispVal = appObject;
webview->AddRemoteObject(L"host_object", &host);
```

 <span data-ttu-id="e3835-509">Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法：</span><span class="sxs-lookup"><span data-stu-id="e3835-509">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span> 

```js
let app_object = await window.chrome.webview.remoteObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```

 <span data-ttu-id="e3835-510">请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。</span><span class="sxs-lookup"><span data-stu-id="e3835-510">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="e3835-511">远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。</span><span class="sxs-lookup"><span data-stu-id="e3835-511">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="e3835-512">可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-512">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="e3835-513">嵌套数组的支持深度为3。</span><span class="sxs-lookup"><span data-stu-id="e3835-513">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="e3835-514">不支持按引用类型的数组。</span><span class="sxs-lookup"><span data-stu-id="e3835-514">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="e3835-515">VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="e3835-515">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="e3835-516">在 JavaScript null 中，未定义映射到 VT_EMPTY。</span><span class="sxs-lookup"><span data-stu-id="e3835-516">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="e3835-517">此外，所有远程对象均公开为 `window.chrome.webview.remoteObjects.sync.<name>` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-517">Additionally, all remote objects are exposed as `window.chrome.webview.remoteObjects.sync.<name>`.</span></span> <span data-ttu-id="e3835-518">此处的主机对象公开为同步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="e3835-518">Here the host objects are exposed as synchronous remote object proxies.</span></span> <span data-ttu-id="e3835-519">这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。</span><span class="sxs-lookup"><span data-stu-id="e3835-519">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="e3835-520">因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.remoteObjects.<name>` API。</span><span class="sxs-lookup"><span data-stu-id="e3835-520">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.remoteObjects.<name>` API described above.</span></span>

<span data-ttu-id="e3835-521">同步远程对象代理和异步远程对象代理都可以代理同一远程对象。</span><span class="sxs-lookup"><span data-stu-id="e3835-521">Synchronous remote object proxies and asynchronous remote object proxies can both proxy the same remote object.</span></span> <span data-ttu-id="e3835-522">一个代理所做的远程更改将反映在该远程对象的任何其他代理中，无论其他代理和同步还是异步。</span><span class="sxs-lookup"><span data-stu-id="e3835-522">Remote changes made by one proxy will be reflected in any other proxy of that same remote object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="e3835-523">虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="e3835-523">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="e3835-524">尝试执行此操作将失败，并 HRESULT_FROM_WIN32 （ERROR_POSSIBLE_DEADLOCK）。</span><span class="sxs-lookup"><span data-stu-id="e3835-524">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="e3835-525">远程对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。</span><span class="sxs-lookup"><span data-stu-id="e3835-525">Remote object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="e3835-526">作为函数或对象原型一部分的属性或方法在本地运行。</span><span class="sxs-lookup"><span data-stu-id="e3835-526">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="e3835-527">此外，数组中的任何属性或方法 `chrome.webview.remoteObjects.options.forceLocalProperties` 也将在本地运行。</span><span class="sxs-lookup"><span data-stu-id="e3835-527">Additionally any property or method in the array `chrome.webview.remoteObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="e3835-528">这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-528">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="e3835-529">你可以根据需要向此数组添加更多。</span><span class="sxs-lookup"><span data-stu-id="e3835-529">You can add more to this array as required.</span></span>

<span data-ttu-id="e3835-530">有一种方法 `chrome.webview.remoteObjects.cleanupSome` 可以最大程度地垃圾回收远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="e3835-530">There's a method `chrome.webview.remoteObjects.cleanupSome` that will best effort garbage collect remote object proxies.</span></span>

<span data-ttu-id="e3835-531">远程对象代理还具有以下可在本地运行的方法：</span><span class="sxs-lookup"><span data-stu-id="e3835-531">Remote object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="e3835-532">applyRemote、getRemote、setRemote：对远程对象执行方法调用、属性获取或属性设置。</span><span class="sxs-lookup"><span data-stu-id="e3835-532">applyRemote, getRemote, setRemote: Perform a method invocation, property get, or property set on the remote object.</span></span> <span data-ttu-id="e3835-533">如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。</span><span class="sxs-lookup"><span data-stu-id="e3835-533">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="e3835-534">例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-534">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="e3835-535">而 `proxy.applyRemote('toString')` `toString` 是在远程代理对象上运行。</span><span class="sxs-lookup"><span data-stu-id="e3835-535">But `proxy.applyRemote('toString')` runs `toString` on the remote proxied object instead.</span></span>

* <span data-ttu-id="e3835-536">getLocal，setLocal：执行属性 get 或本地设置属性。</span><span class="sxs-lookup"><span data-stu-id="e3835-536">getLocal, setLocal: Perform property get, or property set locally.</span></span> <span data-ttu-id="e3835-537">可以使用这些方法强制在远程对象代理本身（而不是在它表示的远程对象）上获取或设置属性。</span><span class="sxs-lookup"><span data-stu-id="e3835-537">You can use these methods to force getting or setting a property on the remote object proxy itself rather than on the remote object it represents.</span></span> <span data-ttu-id="e3835-538">例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从远程代理对象命名的属性。</span><span class="sxs-lookup"><span data-stu-id="e3835-538">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the remote proxied object.</span></span> <span data-ttu-id="e3835-539">但 `proxy.getLocal('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。</span><span class="sxs-lookup"><span data-stu-id="e3835-539">But `proxy.getLocal('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="e3835-540">同步：异步远程对象代理公开同步方法，该方法可为同一远程对象返回同步远程对象代理的承诺。</span><span class="sxs-lookup"><span data-stu-id="e3835-540">sync: Asynchronous remote object proxies expose a sync method which returns a promise for a synchronous remote object proxy for the same remote object.</span></span> <span data-ttu-id="e3835-541">例如， `chrome.webview.remoteObjects.sample.methodCall()` 返回一个异步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="e3835-541">For example, `chrome.webview.remoteObjects.sample.methodCall()` returns an asynchronous remote object proxy.</span></span> <span data-ttu-id="e3835-542">你可以改用此 `sync` 方法获取同步远程对象代理：</span><span class="sxs-lookup"><span data-stu-id="e3835-542">You can use the `sync` method to obtain a synchronous remote object proxy instead:</span></span> `const syncProxy = await chrome.webview.remoteObjects.sample.methodCall().sync()`

* <span data-ttu-id="e3835-543">异步：同步远程对象代理公开一个 async 方法，该方法会阻止并返回同一远程对象的异步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="e3835-543">async: Synchronous remote object proxies expose an async method which blocks and returns an asynchronous remote object proxy for the same remote object.</span></span> <span data-ttu-id="e3835-544">例如， `chrome.webview.remoteObjects.sync.sample.methodCall()` 返回同步远程对象代理。</span><span class="sxs-lookup"><span data-stu-id="e3835-544">For example, `chrome.webview.remoteObjects.sync.sample.methodCall()` returns a synchronous remote object proxy.</span></span> <span data-ttu-id="e3835-545">`async`在此块上调用该方法，然后返回同一远程对象的异步远程对象代理：</span><span class="sxs-lookup"><span data-stu-id="e3835-545">Calling the `async` method on this blocks and then returns an asynchronous remote object proxy for the same remote object:</span></span> `const asyncProxy = chrome.webview.remoteObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="e3835-546">然后：异步远程对象代理具有 then 方法。</span><span class="sxs-lookup"><span data-stu-id="e3835-546">then: Asynchronous remote object proxies have a then method.</span></span> <span data-ttu-id="e3835-547">这使它们能够可等待。</span><span class="sxs-lookup"><span data-stu-id="e3835-547">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="e3835-548">将返回使用远程对象的表示形式解析的承诺。</span><span class="sxs-lookup"><span data-stu-id="e3835-548">will return a promise that resolves with a representation of the remote object.</span></span> <span data-ttu-id="e3835-549">如果代理表示 JavaScript 文本，则会在本地返回一个副本。</span><span class="sxs-lookup"><span data-stu-id="e3835-549">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="e3835-550">如果代理表示一个函数，则返回非可等待代理。</span><span class="sxs-lookup"><span data-stu-id="e3835-550">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="e3835-551">如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为远程对象代理返回该对象的副本。</span><span class="sxs-lookup"><span data-stu-id="e3835-551">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as remote object proxies.</span></span>

<span data-ttu-id="e3835-552">所有其他属性和方法调用（除了上述远程对象代理方法、forceLocalProperties 列表和函数和对象原型上的属性）都是远程运行的。</span><span class="sxs-lookup"><span data-stu-id="e3835-552">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="e3835-553">异步远程对象代理返回表示异步完成调用该方法或获取属性的异步完成的承诺。</span><span class="sxs-lookup"><span data-stu-id="e3835-553">Asynchronous remote object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="e3835-554">在远程操作完成后，承诺将解决该操作的结果值。</span><span class="sxs-lookup"><span data-stu-id="e3835-554">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="e3835-555">同步远程对象代理的工作方式类似，但阻止了 JavaScript 执行并等待远程操作完成。</span><span class="sxs-lookup"><span data-stu-id="e3835-555">Synchronous remote object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="e3835-556">在异步远程对象代理上设置属性的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="e3835-556">Setting a property on an asynchronous remote object proxy works slightly differently.</span></span> <span data-ttu-id="e3835-557">Set 将立即返回，返回值为将设置的值。</span><span class="sxs-lookup"><span data-stu-id="e3835-557">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="e3835-558">这是 JavaScript 代理对象的要求。</span><span class="sxs-lookup"><span data-stu-id="e3835-558">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="e3835-559">如果需要异步等待属性设置为 "完成"，请使用 setRemote 方法，该方法将返回上述承诺。</span><span class="sxs-lookup"><span data-stu-id="e3835-559">If you need to asynchronously wait for the property set to complete, use the setRemote method which returns a promise as described above.</span></span> <span data-ttu-id="e3835-560">同步对象属性 set 属性在设置该属性之前同步地阻止。</span><span class="sxs-lookup"><span data-stu-id="e3835-560">Synchronous object property set property synchronously blocks until the property is set.</span></span>

<span data-ttu-id="e3835-561">例如，假设你有一个具有以下接口的 COM 对象</span><span class="sxs-lookup"><span data-stu-id="e3835-561">For example, suppose you have a COM object with the following interface</span></span>

```IDL
    [uuid(3a14c9c0-bc3e-453f-a314-4ce4a0ec81d8), object, local]
    interface IRemoteObjectSample : IUnknown
    {
        // Demonstrate basic method call with some parameters and a return value.
        HRESULT MethodWithParametersAndReturnValue([in] BSTR stringParameter, [in] INT integerParameter, [out, retval] BSTR* stringResult);

        // Demonstrate getting and setting a property.
        [propget] HRESULT Property([out, retval] BSTR* stringResult);
        [propput] HRESULT Property([in] BSTR stringValue);

        // Demonstrate native calling back into JavaScript.
        HRESULT CallCallbackAsynchronously([in] IDispatch* callbackParameter);
    };
```

 <span data-ttu-id="e3835-562">我们可以将此接口的实例添加到我们的 JavaScript 中 `AddRemoteObject` 。</span><span class="sxs-lookup"><span data-stu-id="e3835-562">We can add an instance of this interface into our JavaScript with `AddRemoteObject`.</span></span> <span data-ttu-id="e3835-563">在这种情况下，我们将其命名 `sample` 为：</span><span class="sxs-lookup"><span data-stu-id="e3835-563">In this case we name it `sample`:</span></span>

```cpp
            VARIANT remoteObjectAsVariant = {};
            m_remoteObject.query_to<IDispatch>(&remoteObjectAsVariant.pdispVal);
            remoteObjectAsVariant.vt = VT_DISPATCH;

            // We can call AddRemoteObject multiple times in a row without
            // calling RemoveRemoteObject first. This will replace the previous object
            // with the new object. In our case this is the same object and everything
            // is fine.
            CHECK_FAILURE(m_webView->AddRemoteObject(L"sample", &remoteObjectAsVariant));
            remoteObjectAsVariant.pdispVal->Release();
```

 <span data-ttu-id="e3835-564">然后，在 HTML 文档中，我们可以通过以下方式使用该 COM 对象 `chrome.webview.remoteObjects.sample` ：</span><span class="sxs-lookup"><span data-stu-id="e3835-564">Then in the HTML document we can use this COM object via `chrome.webview.remoteObjects.sample`:</span></span>

```js
        document.getElementById("getPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = await chrome.webview.remoteObjects.sample.property;
            document.getElementById("getPropertyAsyncOutput").textContent = propertyValue;
        });

        document.getElementById("getPropertySyncButton").addEventListener("click", () => {
            const propertyValue = chrome.webview.remoteObjects.sync.sample.property;
            document.getElementById("getPropertySyncOutput").textContent = propertyValue;
        });

        document.getElementById("setPropertyAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyAsyncInput").value;
            // The following line will work but it will return immediately before the property value has actually been set.
            // If you need to set the property and wait for the property to change value, use the setRemote function.
            chrome.webview.remoteObjects.sample.property = propertyValue;
            document.getElementById("setPropertyAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertyExplicitAsyncButton").addEventListener("click", async () => {
            const propertyValue = document.getElementById("setPropertyExplicitAsyncInput").value;
            // If you care about waiting until the property has actually changed value use the setRemote function.
            await chrome.webview.remoteObjects.sample.setRemote("property", propertyValue);
            document.getElementById("setPropertyExplicitAsyncOutput").textContent = "Set";
        });

        document.getElementById("setPropertySyncButton").addEventListener("click", () => {
            const propertyValue = document.getElementById("setPropertySyncInput").value;
            chrome.webview.remoteObjects.sync.sample.property = propertyValue;
            document.getElementById("setPropertySyncOutput").textContent = "Set";
        });

        document.getElementById("invokeMethodAsyncButton").addEventListener("click", async () => {
            const paramValue1 = document.getElementById("invokeMethodAsyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodAsyncParam2").value);
            const resultValue = await chrome.webview.remoteObjects.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodAsyncOutput").textContent = resultValue;
        });

        document.getElementById("invokeMethodSyncButton").addEventListener("click", () => {
            const paramValue1 = document.getElementById("invokeMethodSyncParam1").value;
            const paramValue2 = parseInt(document.getElementById("invokeMethodSyncParam2").value);
            const resultValue = chrome.webview.remoteObjects.sync.sample.MethodWithParametersAndReturnValue(paramValue1, paramValue2);
            document.getElementById("invokeMethodSyncOutput").textContent = resultValue;
        });

        let callbackCount = 0;
        document.getElementById("invokeCallbackButton").addEventListener("click", async () => {
            chrome.webview.remoteObjects.sample.CallCallbackAsynchronously(() => {
                document.getElementById("invokeCallbackOutput").textContent = "Native object called the callback " + (++callbackCount) + " time(s).";
            });
        });
```

#### <span data-ttu-id="e3835-565">RemoveRemoteObject</span><span class="sxs-lookup"><span data-stu-id="e3835-565">RemoveRemoteObject</span></span> 

<span data-ttu-id="e3835-566">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="e3835-566">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="e3835-567">公共 HRESULT [RemoveRemoteObject](#removeremoteobject)（LPCWSTR name）</span><span class="sxs-lookup"><span data-stu-id="e3835-567">public HRESULT [RemoveRemoteObject](#removeremoteobject)(LPCWSTR name)</span></span>

<span data-ttu-id="e3835-568">当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-568">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="e3835-569">为已删除或从未添加的名称调用此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="e3835-569">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="e3835-570">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="e3835-570">OpenDevToolsWindow</span></span> 

<span data-ttu-id="e3835-571">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="e3835-571">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="e3835-572">公共 HRESULT [OpenDevToolsWindow](#opendevtoolswindow)（）</span><span class="sxs-lookup"><span data-stu-id="e3835-572">public HRESULT [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="e3835-573">如果在 DevTools 窗口已打开时调用，则不执行任何操作</span><span class="sxs-lookup"><span data-stu-id="e3835-573">Does nothing if called when the DevTools window is already open</span></span>

#### <span data-ttu-id="e3835-574">add_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-574">add_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="e3835-575">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="e3835-575">Notifies when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="e3835-576">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)（[ICoreWebView2ContainsFullScreenElementChangedEventHandler](ICoreWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-576">public HRESULT [add_ContainsFullScreenElementChanged](#add_containsfullscreenelementchanged)([ICoreWebView2ContainsFullScreenElementChangedEventHandler](ICoreWebView2ContainsFullScreenElementChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-577">这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。</span><span class="sxs-lookup"><span data-stu-id="e3835-577">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="e3835-578">例如，当视频元素请求进入全屏时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="e3835-578">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="e3835-579">然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="e3835-579">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

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

#### <span data-ttu-id="e3835-580">remove_ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="e3835-580">remove_ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="e3835-581">删除以前使用相应的 add_ 事件方法添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-581">Remove an event handler previously added with the corresponding add_ event method.</span></span>

> <span data-ttu-id="e3835-582">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-582">public HRESULT [remove_ContainsFullScreenElementChanged](#remove_containsfullscreenelementchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-583">get_ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="e3835-583">get_ContainsFullScreenElement</span></span> 

<span data-ttu-id="e3835-584">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="e3835-584">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="e3835-585">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)（BOOL \* ContainsFullScreenElement）</span><span class="sxs-lookup"><span data-stu-id="e3835-585">public HRESULT [get_ContainsFullScreenElement](#get_containsfullscreenelement)(BOOL \* containsFullScreenElement)</span></span>

#### <span data-ttu-id="e3835-586">add_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-586">add_WebResourceRequested</span></span> 

<span data-ttu-id="e3835-587">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-587">Add an event handler for the WebResourceRequested event.</span></span>

> <span data-ttu-id="e3835-588">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)（[ICoreWebView2WebResourceRequestedEventHandler](ICoreWebView2WebResourceRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-588">public HRESULT [add_WebResourceRequested](#add_webresourcerequested)([ICoreWebView2WebResourceRequestedEventHandler](ICoreWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-589">在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="e3835-589">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span> <span data-ttu-id="e3835-590">必须至少添加一个筛选器，才能触发该事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-590">At least one filter must be added for the event to fire.</span></span>

```cpp
        if (m_blockImages)
        {
            m_webView->AddWebResourceRequestedFilter(L"*", CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE);
            CHECK_FAILURE(m_webView->add_WebResourceRequested(
                Callback<ICoreWebView2WebResourceRequestedEventHandler>(
                    [this](
                        ICoreWebView2* sender,
                        ICoreWebView2WebResourceRequestedEventArgs* args) {
                        CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT resourceContext;
                        CHECK_FAILURE(
                            args->get_ResourceContext(&resourceContext));
                        // Ensure that the type is image
                        if (resourceContext != CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE)
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

#### <span data-ttu-id="e3835-591">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-591">remove_WebResourceRequested</span></span> 

<span data-ttu-id="e3835-592">删除以前使用 add_WebResourceRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-592">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="e3835-593">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-593">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-594">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="e3835-594">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="e3835-595">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="e3835-595">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="e3835-596">公共 HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（LPCWSTR const uri，[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) const resourceContext）</span><span class="sxs-lookup"><span data-stu-id="e3835-596">public HRESULT [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(LPCWSTR const uri,[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="e3835-597">URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。</span><span class="sxs-lookup"><span data-stu-id="e3835-597">URI parameter can be a wildcard string ('': zero or more, '?': exactly one).</span></span> <span data-ttu-id="e3835-598">nullptr 等效于 L ""。</span><span class="sxs-lookup"><span data-stu-id="e3835-598">nullptr is equivalent to L"".</span></span> <span data-ttu-id="e3835-599">有关资源上下文筛选器的说明，请参阅 CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT enum。</span><span class="sxs-lookup"><span data-stu-id="e3835-599">See CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT enum for description of resource context filters.</span></span>

#### <span data-ttu-id="e3835-600">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="e3835-600">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="e3835-601">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="e3835-601">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="e3835-602">公共 HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（LPCWSTR const uri，[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) const resourceContext）</span><span class="sxs-lookup"><span data-stu-id="e3835-602">public HRESULT [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(LPCWSTR const uri,[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context) const resourceContext)</span></span>

<span data-ttu-id="e3835-603">如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。</span><span class="sxs-lookup"><span data-stu-id="e3835-603">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="e3835-604">返回从未添加的筛选器 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="e3835-604">Returns E_INVALIDARG for a filter that was never added.</span></span>

#### <span data-ttu-id="e3835-605">add_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-605">add_WindowCloseRequested</span></span> 

<span data-ttu-id="e3835-606">为 WindowCloseRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-606">Add an event handler for the WindowCloseRequested event.</span></span>

> <span data-ttu-id="e3835-607">public HRESULT [add_WindowCloseRequested](#add_windowcloserequested)（[ICoreWebView2WindowCloseRequestedEventHandler](ICoreWebView2WindowCloseRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="e3835-607">public HRESULT [add_WindowCloseRequested](#add_windowcloserequested)([ICoreWebView2WindowCloseRequestedEventHandler](ICoreWebView2WindowCloseRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="e3835-608">在 Web 视图中请求关闭窗口的内容（如在窗口后）关闭窗口时激发。调用 close。</span><span class="sxs-lookup"><span data-stu-id="e3835-608">Fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span> <span data-ttu-id="e3835-609">如果应用程序有意义，则应用应关闭 Web 视图和相关应用窗口。</span><span class="sxs-lookup"><span data-stu-id="e3835-609">The app should close the WebView and related app window if that makes sense to the app.</span></span>

```cpp
    // Register a handler for the WindowCloseRequested event.
    // This handler will close the app window if it is not the main window.
    CHECK_FAILURE(m_webView->add_WindowCloseRequested(
        Callback<ICoreWebView2WindowCloseRequestedEventHandler>(
            [this](ICoreWebView2* sender, IUnknown* args) {
                if (m_isPopupWindow)
                {
                    CloseAppWindow();
                }
                return S_OK;
            })
            .Get(),
        nullptr));
```

#### <span data-ttu-id="e3835-610">remove_WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="e3835-610">remove_WindowCloseRequested</span></span> 

<span data-ttu-id="e3835-611">删除以前使用 add_WindowCloseRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="e3835-611">Remove an event handler previously added with add_WindowCloseRequested.</span></span>

> <span data-ttu-id="e3835-612">public HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="e3835-612">public HRESULT [remove_WindowCloseRequested](#remove_windowcloserequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="e3835-613">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="e3835-613">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="e3835-614">ICoreWebView2：： CapturePreview 方法使用的图像格式。</span><span class="sxs-lookup"><span data-stu-id="e3835-614">Image format used by the ICoreWebView2::CapturePreview method.</span></span>

> <span data-ttu-id="e3835-615">枚举[CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="e3835-615">enum [CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#core_webview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="e3835-616">值</span><span class="sxs-lookup"><span data-stu-id="e3835-616">Values</span></span>                         | <span data-ttu-id="e3835-617">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-617">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-618">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="e3835-618">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="e3835-619">PNG 图像格式。</span><span class="sxs-lookup"><span data-stu-id="e3835-619">PNG image format.</span></span>
<span data-ttu-id="e3835-620">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="e3835-620">CORE_WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="e3835-621">JPEG 图像格式。</span><span class="sxs-lookup"><span data-stu-id="e3835-621">JPEG image format.</span></span>

#### <span data-ttu-id="e3835-622">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="e3835-622">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="e3835-623">ICoreWebView2ScriptDialogOpeningEventHandler 接口中使用的 JavaScript 对话框类型。</span><span class="sxs-lookup"><span data-stu-id="e3835-623">Kind of JavaScript dialog used in the ICoreWebView2ScriptDialogOpeningEventHandler interface.</span></span>

> <span data-ttu-id="e3835-624">枚举[CORE_WEBVIEW2_SCRIPT_DIALOG_KIND](#core_webview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="e3835-624">enum [CORE_WEBVIEW2_SCRIPT_DIALOG_KIND](#core_webview2_script_dialog_kind)</span></span>

 <span data-ttu-id="e3835-625">值</span><span class="sxs-lookup"><span data-stu-id="e3835-625">Values</span></span>                         | <span data-ttu-id="e3835-626">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-626">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-627">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="e3835-627">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="e3835-628">通过窗口调用的对话框。警报 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="e3835-628">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="e3835-629">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="e3835-629">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="e3835-630">通过窗口调用的对话框。确认 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="e3835-630">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="e3835-631">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="e3835-631">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="e3835-632">通过窗口调用的对话框。提示 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="e3835-632">A dialog invoked via the window.prompt JavaScript function.</span></span>
<span data-ttu-id="e3835-633">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD</span><span class="sxs-lookup"><span data-stu-id="e3835-633">CORE_WEBVIEW2_SCRIPT_DIALOG_KIND_BEFOREUNLOAD</span></span>            | <span data-ttu-id="e3835-634">通过 beforeunload JavaScript 事件调用的对话框。</span><span class="sxs-lookup"><span data-stu-id="e3835-634">A dialog invoked via the beforeunload JavaScript event.</span></span>

#### <span data-ttu-id="e3835-635">CORE_WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="e3835-635">CORE_WEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="e3835-636">ICoreWebView2ProcessFailedEventHandler 接口中使用的进程失败类型。</span><span class="sxs-lookup"><span data-stu-id="e3835-636">Kind of process failure used in the ICoreWebView2ProcessFailedEventHandler interface.</span></span>

> <span data-ttu-id="e3835-637">枚举[CORE_WEBVIEW2_PROCESS_FAILED_KIND](#core_webview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="e3835-637">enum [CORE_WEBVIEW2_PROCESS_FAILED_KIND](#core_webview2_process_failed_kind)</span></span>

 <span data-ttu-id="e3835-638">值</span><span class="sxs-lookup"><span data-stu-id="e3835-638">Values</span></span>                         | <span data-ttu-id="e3835-639">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-639">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-640">CORE_WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="e3835-640">CORE_WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="e3835-641">指示浏览器进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="e3835-641">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="e3835-642">CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="e3835-642">CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="e3835-643">指示呈现进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="e3835-643">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="e3835-644">CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="e3835-644">CORE_WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="e3835-645">指示呈现过程变得无响应。</span><span class="sxs-lookup"><span data-stu-id="e3835-645">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="e3835-646">CORE_WEBVIEW2_PERMISSION_KIND</span><span class="sxs-lookup"><span data-stu-id="e3835-646">CORE_WEBVIEW2_PERMISSION_KIND</span></span> 

<span data-ttu-id="e3835-647">权限请求的类型。</span><span class="sxs-lookup"><span data-stu-id="e3835-647">The type of a permission request.</span></span>

> <span data-ttu-id="e3835-648">枚举[CORE_WEBVIEW2_PERMISSION_KIND](#core_webview2_permission_kind)</span><span class="sxs-lookup"><span data-stu-id="e3835-648">enum [CORE_WEBVIEW2_PERMISSION_KIND](#core_webview2_permission_kind)</span></span>

 <span data-ttu-id="e3835-649">值</span><span class="sxs-lookup"><span data-stu-id="e3835-649">Values</span></span>                         | <span data-ttu-id="e3835-650">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-650">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-651">CORE_WEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="e3835-651">CORE_WEBVIEW2_PERMISSION_KIND_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="e3835-652">未知权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-652">Unknown permission.</span></span>
<span data-ttu-id="e3835-653">CORE_WEBVIEW2_PERMISSION_KIND_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="e3835-653">CORE_WEBVIEW2_PERMISSION_KIND_MICROPHONE</span></span>            | <span data-ttu-id="e3835-654">捕获音频的权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-654">Permission to capture audio.</span></span>
<span data-ttu-id="e3835-655">CORE_WEBVIEW2_PERMISSION_KIND_CAMERA</span><span class="sxs-lookup"><span data-stu-id="e3835-655">CORE_WEBVIEW2_PERMISSION_KIND_CAMERA</span></span>            | <span data-ttu-id="e3835-656">捕获视频的权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-656">Permission to capture video.</span></span>
<span data-ttu-id="e3835-657">CORE_WEBVIEW2_PERMISSION_KIND_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="e3835-657">CORE_WEBVIEW2_PERMISSION_KIND_GEOLOCATION</span></span>            | <span data-ttu-id="e3835-658">访问地理位置的权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-658">Permission to access geolocation.</span></span>
<span data-ttu-id="e3835-659">CORE_WEBVIEW2_PERMISSION_KIND_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="e3835-659">CORE_WEBVIEW2_PERMISSION_KIND_NOTIFICATIONS</span></span>            | <span data-ttu-id="e3835-660">发送 web 通知的权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-660">Permission to send web notifications.</span></span>
<span data-ttu-id="e3835-661">CORE_WEBVIEW2_PERMISSION_KIND_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="e3835-661">CORE_WEBVIEW2_PERMISSION_KIND_OTHER_SENSORS</span></span>            | <span data-ttu-id="e3835-662">访问通用传感器的权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-662">Permission to access generic sensor.</span></span>
<span data-ttu-id="e3835-663">CORE_WEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="e3835-663">CORE_WEBVIEW2_PERMISSION_KIND_CLIPBOARD_READ</span></span>            | <span data-ttu-id="e3835-664">在没有用户手势的情况下读取系统剪贴板的权限。</span><span class="sxs-lookup"><span data-stu-id="e3835-664">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="e3835-665">CORE_WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="e3835-665">CORE_WEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="e3835-666">对权限请求的响应。</span><span class="sxs-lookup"><span data-stu-id="e3835-666">Response to a permission request.</span></span>

> <span data-ttu-id="e3835-667">枚举[CORE_WEBVIEW2_PERMISSION_STATE](#core_webview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="e3835-667">enum [CORE_WEBVIEW2_PERMISSION_STATE](#core_webview2_permission_state)</span></span>

 <span data-ttu-id="e3835-668">值</span><span class="sxs-lookup"><span data-stu-id="e3835-668">Values</span></span>                         | <span data-ttu-id="e3835-669">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-669">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-670">CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="e3835-670">CORE_WEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="e3835-671">使用默认的浏览器行为，这通常会提示用户做出决策。</span><span class="sxs-lookup"><span data-stu-id="e3835-671">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="e3835-672">CORE_WEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="e3835-672">CORE_WEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="e3835-673">授予权限请求。</span><span class="sxs-lookup"><span data-stu-id="e3835-673">Grant the permission request.</span></span>
<span data-ttu-id="e3835-674">CORE_WEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="e3835-674">CORE_WEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="e3835-675">拒绝权限请求。</span><span class="sxs-lookup"><span data-stu-id="e3835-675">Deny the permission request.</span></span>

#### <span data-ttu-id="e3835-676">CORE_WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="e3835-676">CORE_WEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="e3835-677">Web 导航的错误状态值。</span><span class="sxs-lookup"><span data-stu-id="e3835-677">Error status values for web navigations.</span></span>

> <span data-ttu-id="e3835-678">枚举[CORE_WEBVIEW2_WEB_ERROR_STATUS](#core_webview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="e3835-678">enum [CORE_WEBVIEW2_WEB_ERROR_STATUS](#core_webview2_web_error_status)</span></span>

 <span data-ttu-id="e3835-679">值</span><span class="sxs-lookup"><span data-stu-id="e3835-679">Values</span></span>                         | <span data-ttu-id="e3835-680">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-680">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-681">CORE_WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="e3835-681">CORE_WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="e3835-682">出现未知错误。</span><span class="sxs-lookup"><span data-stu-id="e3835-682">An unknown error occurred.</span></span>
<span data-ttu-id="e3835-683">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="e3835-683">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="e3835-684">SSL 证书公用名与 web 地址不匹配。</span><span class="sxs-lookup"><span data-stu-id="e3835-684">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="e3835-685">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="e3835-685">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="e3835-686">SSL 证书已过期。</span><span class="sxs-lookup"><span data-stu-id="e3835-686">The SSL certificate has expired.</span></span>
<span data-ttu-id="e3835-687">CORE_WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="e3835-687">CORE_WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="e3835-688">SSL 客户端证书包含错误。</span><span class="sxs-lookup"><span data-stu-id="e3835-688">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="e3835-689">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="e3835-689">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="e3835-690">SSL 证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="e3835-690">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="e3835-691">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="e3835-691">CORE_WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="e3835-692">SSL 证书无效 &ndash; 这可能意味着证书与主机名的公钥 pin 不匹配，证书由不受信任的颁发机构或使用弱标志算法签名，证书声明的 DNS 名称违反了名称约束，证书包含弱密钥，证书的有效期太长，缺少吊销信息或吊销机制、非唯一的主机名、缺少证书透明信息，或者证书被链接到[旧版 Symantec 根](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html)。</span><span class="sxs-lookup"><span data-stu-id="e3835-692">The SSL certificate is invalid &ndash; this could mean the certificate did not match the public key pins for the host name, the certificate is signed by an untrusted authority or using a weak sign algorithm, the certificate claimed DNS names violate name constraints, the certificate contains a weak key, the certificate's validity period is too long, lack of revocation information or revocation mechanism, non-unique host name, lack of certificate transparency information, or the certificate is chained to a [legacy Symantec root](https://security.googleblog.com/2018/03/distrust-of-symantec-pki-immediate.html).</span></span>
<span data-ttu-id="e3835-693">CORE_WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="e3835-693">CORE_WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="e3835-694">无法访问主机。</span><span class="sxs-lookup"><span data-stu-id="e3835-694">The host is unreachable.</span></span>
<span data-ttu-id="e3835-695">CORE_WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="e3835-695">CORE_WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="e3835-696">连接超时。</span><span class="sxs-lookup"><span data-stu-id="e3835-696">The connection has timed out.</span></span>
<span data-ttu-id="e3835-697">CORE_WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="e3835-697">CORE_WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="e3835-698">服务器返回了无效或无法识别的响应。</span><span class="sxs-lookup"><span data-stu-id="e3835-698">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="e3835-699">CORE_WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="e3835-699">CORE_WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="e3835-700">连接已中止。</span><span class="sxs-lookup"><span data-stu-id="e3835-700">The connection was aborted.</span></span>
<span data-ttu-id="e3835-701">CORE_WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="e3835-701">CORE_WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="e3835-702">已重置连接。</span><span class="sxs-lookup"><span data-stu-id="e3835-702">The connection was reset.</span></span>
<span data-ttu-id="e3835-703">CORE_WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="e3835-703">CORE_WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="e3835-704">互联网连接已丢失。</span><span class="sxs-lookup"><span data-stu-id="e3835-704">The Internet connection has been lost.</span></span>
<span data-ttu-id="e3835-705">CORE_WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="e3835-705">CORE_WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="e3835-706">无法连接到目标。</span><span class="sxs-lookup"><span data-stu-id="e3835-706">Cannot connect to destination.</span></span>
<span data-ttu-id="e3835-707">CORE_WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="e3835-707">CORE_WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="e3835-708">无法解析提供的主机名。</span><span class="sxs-lookup"><span data-stu-id="e3835-708">Could not resolve provided host name.</span></span>
<span data-ttu-id="e3835-709">CORE_WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="e3835-709">CORE_WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="e3835-710">操作已取消。</span><span class="sxs-lookup"><span data-stu-id="e3835-710">The operation was canceled.</span></span>
<span data-ttu-id="e3835-711">CORE_WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="e3835-711">CORE_WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="e3835-712">请求重定向失败。</span><span class="sxs-lookup"><span data-stu-id="e3835-712">The request redirect failed.</span></span>
<span data-ttu-id="e3835-713">CORE_WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="e3835-713">CORE_WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="e3835-714">出现意外错误。</span><span class="sxs-lookup"><span data-stu-id="e3835-714">An unexpected error occurred.</span></span>

#### <span data-ttu-id="e3835-715">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="e3835-715">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="e3835-716">Web 资源请求上下文的枚举。</span><span class="sxs-lookup"><span data-stu-id="e3835-716">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="e3835-717">枚举[CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="e3835-717">enum [CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT](#core_webview2_web_resource_context)</span></span>

 <span data-ttu-id="e3835-718">值</span><span class="sxs-lookup"><span data-stu-id="e3835-718">Values</span></span>                         | <span data-ttu-id="e3835-719">描述</span><span class="sxs-lookup"><span data-stu-id="e3835-719">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="e3835-720">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="e3835-720">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="e3835-721">所有资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-721">All resources.</span></span>
<span data-ttu-id="e3835-722">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="e3835-722">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="e3835-723">文档资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-723">Document resources.</span></span>
<span data-ttu-id="e3835-724">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="e3835-724">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="e3835-725">CSS 资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-725">CSS resources.</span></span>
<span data-ttu-id="e3835-726">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="e3835-726">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="e3835-727">图像资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-727">Image resources.</span></span>
<span data-ttu-id="e3835-728">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="e3835-728">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="e3835-729">其他媒体资源（如视频）。</span><span class="sxs-lookup"><span data-stu-id="e3835-729">Other media resources such as videos.</span></span>
<span data-ttu-id="e3835-730">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="e3835-730">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="e3835-731">字体资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-731">Font resources.</span></span>
<span data-ttu-id="e3835-732">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="e3835-732">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="e3835-733">脚本资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-733">Script resources.</span></span>
<span data-ttu-id="e3835-734">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="e3835-734">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="e3835-735">XML HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="e3835-735">XML HTTP requests.</span></span>
<span data-ttu-id="e3835-736">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="e3835-736">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="e3835-737">获取 API 通信。</span><span class="sxs-lookup"><span data-stu-id="e3835-737">Fetch API communication.</span></span>
<span data-ttu-id="e3835-738">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="e3835-738">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="e3835-739">TextTrack 资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-739">TextTrack resources.</span></span>
<span data-ttu-id="e3835-740">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="e3835-740">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | <span data-ttu-id="e3835-741">EventSource API 通信。</span><span class="sxs-lookup"><span data-stu-id="e3835-741">EventSource API communication.</span></span>
<span data-ttu-id="e3835-742">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="e3835-742">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | <span data-ttu-id="e3835-743">WebSocket API 通信。</span><span class="sxs-lookup"><span data-stu-id="e3835-743">WebSocket API communication.</span></span>
<span data-ttu-id="e3835-744">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="e3835-744">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | <span data-ttu-id="e3835-745">Web 应用清单。</span><span class="sxs-lookup"><span data-stu-id="e3835-745">Web App Manifests.</span></span>
<span data-ttu-id="e3835-746">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="e3835-746">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | <span data-ttu-id="e3835-747">已签名的 HTTP 交换。</span><span class="sxs-lookup"><span data-stu-id="e3835-747">Signed HTTP Exchanges.</span></span>
<span data-ttu-id="e3835-748">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="e3835-748">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | <span data-ttu-id="e3835-749">Ping 请求。</span><span class="sxs-lookup"><span data-stu-id="e3835-749">Ping requests.</span></span>
<span data-ttu-id="e3835-750">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="e3835-750">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | <span data-ttu-id="e3835-751">CSP 冲突报告。</span><span class="sxs-lookup"><span data-stu-id="e3835-751">CSP Violation Reports.</span></span>
<span data-ttu-id="e3835-752">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="e3835-752">CORE_WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="e3835-753">其他资源。</span><span class="sxs-lookup"><span data-stu-id="e3835-753">Other resources.</span></span>
