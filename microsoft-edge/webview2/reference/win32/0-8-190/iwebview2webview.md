---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge
ms.openlocfilehash: 5c84cfb703c8901560307b7bba8bc7887cb19377
ms.sourcegitcommit: 07cda56425e5fdf90eeb3972e17041261bf720cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/14/2020
ms.locfileid: "10652808"
---
# <span data-ttu-id="d2c20-104">interface IWebView2WebView</span><span class="sxs-lookup"><span data-stu-id="d2c20-104">interface IWebView2WebView</span></span> 

> [!NOTE]
> <span data-ttu-id="d2c20-105">此接口可能会在 SDK 版本0.8.355 后更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="d2c20-105">This interface may be altered or unavailable for releases after SDK version 0.8.355.</span></span> <span data-ttu-id="d2c20-106">请参阅[参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="d2c20-106">Please refer to [Reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

```
interface IWebView2WebView
  : public IUnknown
```

<span data-ttu-id="d2c20-107">WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="d2c20-107">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="d2c20-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d2c20-108">Summary</span></span>

 <span data-ttu-id="d2c20-109">成员</span><span class="sxs-lookup"><span data-stu-id="d2c20-109">Members</span></span>                        | <span data-ttu-id="d2c20-110">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-110">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="d2c20-111">get_Settings</span><span class="sxs-lookup"><span data-stu-id="d2c20-111">get_Settings</span></span>](#get_settings) | <span data-ttu-id="d2c20-112">[IWebView2Settings](IWebView2Settings.md)对象包含运行的 web 视图的各种可修改设置。</span><span class="sxs-lookup"><span data-stu-id="d2c20-112">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>
[<span data-ttu-id="d2c20-113">get_Source</span><span class="sxs-lookup"><span data-stu-id="d2c20-113">get_Source</span></span>](#get_source) | <span data-ttu-id="d2c20-114">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="d2c20-114">The URI of the current top level document.</span></span>
[<span data-ttu-id="d2c20-115">导航</span><span class="sxs-lookup"><span data-stu-id="d2c20-115">Navigate</span></span>](#navigate) | <span data-ttu-id="d2c20-116">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="d2c20-116">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="d2c20-117">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-117">MoveFocus</span></span>](#movefocus) | <span data-ttu-id="d2c20-118">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="d2c20-118">Move focus into WebView.</span></span>
[<span data-ttu-id="d2c20-119">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="d2c20-119">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="d2c20-120">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="d2c20-120">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="d2c20-121">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-121">add_NavigationStarting</span></span>](#add_navigationstarting) | <span data-ttu-id="d2c20-122">为 NavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-122">Add an event handler for the NavigationStarting event.</span></span>
[<span data-ttu-id="d2c20-123">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-123">remove_NavigationStarting</span></span>](#remove_navigationstarting) | <span data-ttu-id="d2c20-124">删除以前使用 add_NavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-124">Remove an event handler previously added with add_NavigationStarting.</span></span>
[<span data-ttu-id="d2c20-125">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-125">add_DocumentStateChanged</span></span>](#add_documentstatechanged) | <span data-ttu-id="d2c20-126">为 DocumentStateChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-126">Add an event handler for the DocumentStateChanged event.</span></span>
[<span data-ttu-id="d2c20-127">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-127">remove_DocumentStateChanged</span></span>](#remove_documentstatechanged) | <span data-ttu-id="d2c20-128">删除以前使用 add_DocumentStateChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-128">Remove an event handler previously added with add_DocumentStateChanged.</span></span>
[<span data-ttu-id="d2c20-129">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d2c20-129">add_NavigationCompleted</span></span>](#add_navigationcompleted) | <span data-ttu-id="d2c20-130">为 NavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-130">Add an event handler for the NavigationCompleted event.</span></span>
[<span data-ttu-id="d2c20-131">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d2c20-131">remove_NavigationCompleted</span></span>](#remove_navigationcompleted) | <span data-ttu-id="d2c20-132">删除以前使用 add_NavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-132">Remove an event handler previously added with add_NavigationCompleted.</span></span>
[<span data-ttu-id="d2c20-133">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-133">add_FrameNavigationStarting</span></span>](#add_framenavigationstarting) | <span data-ttu-id="d2c20-134">为 FrameNavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-134">Add an event handler for the FrameNavigationStarting event.</span></span>
[<span data-ttu-id="d2c20-135">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-135">remove_FrameNavigationStarting</span></span>](#remove_framenavigationstarting) | <span data-ttu-id="d2c20-136">删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-136">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>
[<span data-ttu-id="d2c20-137">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-137">add_MoveFocusRequested</span></span>](#add_movefocusrequested) | <span data-ttu-id="d2c20-138">为 MoveFocusRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-138">Add an event handler for the MoveFocusRequested event.</span></span>
[<span data-ttu-id="d2c20-139">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-139">remove_MoveFocusRequested</span></span>](#remove_movefocusrequested) | <span data-ttu-id="d2c20-140">删除以前使用 add_MoveFocusRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-140">Remove an event handler previously added with add_MoveFocusRequested.</span></span>
[<span data-ttu-id="d2c20-141">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-141">add_GotFocus</span></span>](#add_gotfocus) | <span data-ttu-id="d2c20-142">为 GotFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-142">Add an event handler for the GotFocus event.</span></span>
[<span data-ttu-id="d2c20-143">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-143">remove_GotFocus</span></span>](#remove_gotfocus) | <span data-ttu-id="d2c20-144">删除以前使用 add_GotFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-144">Remove an event handler previously added with add_GotFocus.</span></span>
[<span data-ttu-id="d2c20-145">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-145">add_LostFocus</span></span>](#add_lostfocus) | <span data-ttu-id="d2c20-146">为 LostFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-146">Add an event handler for the LostFocus event.</span></span>
[<span data-ttu-id="d2c20-147">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-147">remove_LostFocus</span></span>](#remove_lostfocus) | <span data-ttu-id="d2c20-148">删除以前使用 add_LostFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-148">Remove an event handler previously added with add_LostFocus.</span></span>
[<span data-ttu-id="d2c20-149">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="d2c20-149">add_WebResourceRequested_deprecated</span></span>](#add_webresourcerequested_deprecated) | <span data-ttu-id="d2c20-150">此 API 将被弃用，请使用新的 add_WebResourceRequested API。</span><span class="sxs-lookup"><span data-stu-id="d2c20-150">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>
[<span data-ttu-id="d2c20-151">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-151">remove_WebResourceRequested</span></span>](#remove_webresourcerequested) | <span data-ttu-id="d2c20-152">删除以前使用 add_WebResourceRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-152">Remove an event handler previously added with add_WebResourceRequested.</span></span>
[<span data-ttu-id="d2c20-153">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="d2c20-153">add_ScriptDialogOpening</span></span>](#add_scriptdialogopening) | <span data-ttu-id="d2c20-154">为 ScriptDialogOpening 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-154">Add an event handler for the ScriptDialogOpening event.</span></span>
[<span data-ttu-id="d2c20-155">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="d2c20-155">remove_ScriptDialogOpening</span></span>](#remove_scriptdialogopening) | <span data-ttu-id="d2c20-156">删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-156">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>
[<span data-ttu-id="d2c20-157">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-157">add_ZoomFactorChanged</span></span>](#add_zoomfactorchanged) | <span data-ttu-id="d2c20-158">为 ZoomFactorChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-158">Add an event handler for the ZoomFactorChanged event.</span></span>
[<span data-ttu-id="d2c20-159">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-159">remove_ZoomFactorChanged</span></span>](#remove_zoomfactorchanged) | <span data-ttu-id="d2c20-160">删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-160">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>
[<span data-ttu-id="d2c20-161">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-161">add_PermissionRequested</span></span>](#add_permissionrequested) | <span data-ttu-id="d2c20-162">为 Webview.permissionrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-162">Add an event handler for the PermissionRequested event.</span></span>
[<span data-ttu-id="d2c20-163">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-163">remove_PermissionRequested</span></span>](#remove_permissionrequested) | <span data-ttu-id="d2c20-164">删除以前使用 add_PermissionRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-164">Remove an event handler previously added with add_PermissionRequested.</span></span>
[<span data-ttu-id="d2c20-165">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="d2c20-165">add_ProcessFailed</span></span>](#add_processfailed) | <span data-ttu-id="d2c20-166">为 ProcessFailed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-166">Add an event handler for the ProcessFailed event.</span></span>
[<span data-ttu-id="d2c20-167">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="d2c20-167">remove_ProcessFailed</span></span>](#remove_processfailed) | <span data-ttu-id="d2c20-168">删除以前使用 add_ProcessFailed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-168">Remove an event handler previously added with add_ProcessFailed.</span></span>
[<span data-ttu-id="d2c20-169">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="d2c20-169">AddScriptToExecuteOnDocumentCreated</span></span>](#addscripttoexecuteondocumentcreated) | <span data-ttu-id="d2c20-170">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="d2c20-170">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="d2c20-171">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="d2c20-171">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="d2c20-172">删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="d2c20-172">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="d2c20-173">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="d2c20-173">ExecuteScript</span></span>](#executescript) | <span data-ttu-id="d2c20-174">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="d2c20-174">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="d2c20-175">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="d2c20-175">CapturePreview</span></span>](#capturepreview) | <span data-ttu-id="d2c20-176">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="d2c20-176">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="d2c20-177">重载</span><span class="sxs-lookup"><span data-stu-id="d2c20-177">Reload</span></span>](#reload) | <span data-ttu-id="d2c20-178">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="d2c20-178">Reload the current page.</span></span>
[<span data-ttu-id="d2c20-179">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="d2c20-179">get_Bounds</span></span>](#get_bounds) | <span data-ttu-id="d2c20-180">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="d2c20-180">The webview bounds.</span></span>
[<span data-ttu-id="d2c20-181">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="d2c20-181">put_Bounds</span></span>](#put_bounds) | <span data-ttu-id="d2c20-182">设置界限属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-182">Set the Bounds property.</span></span>
[<span data-ttu-id="d2c20-183">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="d2c20-183">get_ZoomFactor</span></span>](#get_zoomfactor) | <span data-ttu-id="d2c20-184">Web 视图中当前页面的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-184">The zoom factor for the current page in the WebView.</span></span>
[<span data-ttu-id="d2c20-185">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="d2c20-185">put_ZoomFactor</span></span>](#put_zoomfactor) | <span data-ttu-id="d2c20-186">设置 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-186">Set the ZoomFactor property.</span></span>
[<span data-ttu-id="d2c20-187">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="d2c20-187">get_IsVisible</span></span>](#get_isvisible) | <span data-ttu-id="d2c20-188">IsVisible 属性确定是显示还是隐藏 web 视图。</span><span class="sxs-lookup"><span data-stu-id="d2c20-188">The IsVisible property determines whether to show or hide the webview.</span></span>
[<span data-ttu-id="d2c20-189">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="d2c20-189">put_IsVisible</span></span>](#put_isvisible) | <span data-ttu-id="d2c20-190">设置 IsVisible 属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-190">Set the IsVisible property.</span></span>
[<span data-ttu-id="d2c20-191">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="d2c20-191">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="d2c20-192">将指定的 webMessage 发布到此[IWebView2WebView]()中的最高级别文档。</span><span class="sxs-lookup"><span data-stu-id="d2c20-192">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>
[<span data-ttu-id="d2c20-193">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="d2c20-193">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="d2c20-194">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-194">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="d2c20-195">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-195">add_WebMessageReceived</span></span>](#add_webmessagereceived) | <span data-ttu-id="d2c20-196">当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-196">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="d2c20-197">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-197">remove_WebMessageReceived</span></span>](#remove_webmessagereceived) | <span data-ttu-id="d2c20-198">删除以前使用 add_WebMessageReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-198">Remove an event handler previously added with add_WebMessageReceived.</span></span>
[<span data-ttu-id="d2c20-199">关闭</span><span class="sxs-lookup"><span data-stu-id="d2c20-199">Close</span></span>](#close) | <span data-ttu-id="d2c20-200">关闭 web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="d2c20-200">Closes the webview and cleans up the underlying browser instance.</span></span>
[<span data-ttu-id="d2c20-201">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="d2c20-201">CallDevToolsProtocolMethod</span></span>](#calldevtoolsprotocolmethod) | <span data-ttu-id="d2c20-202">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="d2c20-202">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="d2c20-203">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-203">add_DevToolsProtocolEventReceived</span></span>](#add_devtoolsprotocoleventreceived) | <span data-ttu-id="d2c20-204">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-204">Subscribe to a DevToolsProtocol event.</span></span>
[<span data-ttu-id="d2c20-205">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-205">remove_DevToolsProtocolEventReceived</span></span>](#remove_devtoolsprotocoleventreceived) | <span data-ttu-id="d2c20-206">删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-206">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>
[<span data-ttu-id="d2c20-207">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="d2c20-207">get_BrowserProcessId</span></span>](#get_browserprocessid) | <span data-ttu-id="d2c20-208">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="d2c20-208">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="d2c20-209">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="d2c20-209">get_CanGoBack</span></span>](#get_cangoback) | <span data-ttu-id="d2c20-210">可将 web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-210">Can navigate the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="d2c20-211">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="d2c20-211">get_CanGoForward</span></span>](#get_cangoforward) | <span data-ttu-id="d2c20-212">可将 web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-212">Can navigate the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="d2c20-213">GoBack</span><span class="sxs-lookup"><span data-stu-id="d2c20-213">GoBack</span></span>](#goback) | <span data-ttu-id="d2c20-214">将 web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-214">Navigates the webview to the previous page in the navigation history.</span></span>
[<span data-ttu-id="d2c20-215">GoForward</span><span class="sxs-lookup"><span data-stu-id="d2c20-215">GoForward</span></span>](#goforward) | <span data-ttu-id="d2c20-216">将 web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-216">Navigates the webview to the next page in the navigation history.</span></span>
[<span data-ttu-id="d2c20-217">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="d2c20-217">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span>](#webview2_capture_preview_image_format) | <span data-ttu-id="d2c20-218">[IWebView2WebView：： CapturePreview](#capturepreview)方法使用的图像格式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-218">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>
[<span data-ttu-id="d2c20-219">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="d2c20-219">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span>](#webview2_script_dialog_kind) | <span data-ttu-id="d2c20-220">[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)接口中使用的 JavaScript 对话框类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-220">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>
[<span data-ttu-id="d2c20-221">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="d2c20-221">WEBVIEW2_PROCESS_FAILED_KIND</span></span>](#webview2_process_failed_kind) | <span data-ttu-id="d2c20-222">[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)接口中使用的进程失败类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-222">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>
[<span data-ttu-id="d2c20-223">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="d2c20-223">WEBVIEW2_PERMISSION_TYPE</span></span>](#webview2_permission_type) | <span data-ttu-id="d2c20-224">权限请求的类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-224">The type of a permission request.</span></span>
[<span data-ttu-id="d2c20-225">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="d2c20-225">WEBVIEW2_PERMISSION_STATE</span></span>](#webview2_permission_state) | <span data-ttu-id="d2c20-226">对权限请求的响应。</span><span class="sxs-lookup"><span data-stu-id="d2c20-226">Response to a permission request.</span></span>
[<span data-ttu-id="d2c20-227">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="d2c20-227">WEBVIEW2_MOVE_FOCUS_REASON</span></span>](#webview2_move_focus_reason) | <span data-ttu-id="d2c20-228">移动焦点的原因。</span><span class="sxs-lookup"><span data-stu-id="d2c20-228">Reason for moving focus.</span></span>
[<span data-ttu-id="d2c20-229">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="d2c20-229">WEBVIEW2_WEB_ERROR_STATUS</span></span>](#webview2_web_error_status) | <span data-ttu-id="d2c20-230">Web 导航的错误状态值。</span><span class="sxs-lookup"><span data-stu-id="d2c20-230">Error status values for web navigations.</span></span>
[<span data-ttu-id="d2c20-231">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="d2c20-231">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span>](#webview2_web_resource_context) | <span data-ttu-id="d2c20-232">Web 资源请求上下文的枚举。</span><span class="sxs-lookup"><span data-stu-id="d2c20-232">Enum for web resource request contexts.</span></span>

## <span data-ttu-id="d2c20-233">导航事件</span><span class="sxs-lookup"><span data-stu-id="d2c20-233">Navigation events</span></span>

<span data-ttu-id="d2c20-234">导航事件的正常序列是 NavigationStarting、DocumentStateChanged 和 NavigationCompleted。</span><span class="sxs-lookup"><span data-stu-id="d2c20-234">The normal sequence of navigation events is NavigationStarting, DocumentStateChanged and then NavigationCompleted.</span></span>

![dot-inline-dotgraph-1](media/dot-inline-dotgraph-1.png)

<span data-ttu-id="d2c20-236">请注意，这适用于具有相同的 NavigationId 事件参数的导航事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-236">Note that this is for navigation events with the same NavigationId event arg.</span></span> <span data-ttu-id="d2c20-237">具有不同 NavigationId 事件参数的导航事件可能会重叠。</span><span class="sxs-lookup"><span data-stu-id="d2c20-237">Navigations events with different NavigationId event args may overlap.</span></span> <span data-ttu-id="d2c20-238">例如，如果你为其 NavigationStarting 事件启动导航等待，然后开始另一个导航，你将看到第一个导航的 NavigationStarting，后跟第二个导航的 NavigationStarting，然后是第一个导航的 NavigationCompleted 以及第二个导航的所有其余导航事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-238">For instance, if you start a navigation wait for its NavigationStarting event and then start another navigation you'll see the NavigationStarting for the first navigate followed by the NavigationStarting of the second navigate, followed by the NavigationCompleted for the first navigation and then all the rest of the appropriate navigation events for the second navigation.</span></span> <span data-ttu-id="d2c20-239">在错误情况下，可能会有也可能不是 DocumentStateChanged 事件，具体取决于导航是否转到错误页面。</span><span class="sxs-lookup"><span data-stu-id="d2c20-239">In error cases there may or may not be a DocumentStateChanged event depending on whether the navigation is continued to an error page.</span></span> <span data-ttu-id="d2c20-240">在 HTTP 重定向时，一行中将有多个 NavigationStarting 事件，并且第一个事件将设置其 IsRedirect 标志。</span><span class="sxs-lookup"><span data-stu-id="d2c20-240">In case of an HTTP redirect, there will be multiple NavigationStarting events in a row, with ones following the first will have their IsRedirect flag set.</span></span>

<span data-ttu-id="d2c20-241">对于 Web 视图内部的 subframes，引发的唯一导航事件是 NavigationStarting 事件，它使主机能够阻止 subframe 导航。</span><span class="sxs-lookup"><span data-stu-id="d2c20-241">For subframes inside WebView, the only navigation event fired is the NavigationStarting event which gives host the ability to block subframe navigations.</span></span>

## <span data-ttu-id="d2c20-242">流程模型</span><span class="sxs-lookup"><span data-stu-id="d2c20-242">Process model</span></span>

<span data-ttu-id="d2c20-243">WebView2 使用与 Edge web 浏览器相同的进程模型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-243">WebView2 uses the same process model as the Edge web browser.</span></span> <span data-ttu-id="d2c20-244">用户会话中每个指定的用户数据目录都有一个 Edge 浏览器进程，该进程将为指定用户数据目录的任何 WebView2 调用进程提供服务。</span><span class="sxs-lookup"><span data-stu-id="d2c20-244">There is one Edge browser process per specified user data directory in a user session that will serve any WebView2 calling process that specifies that user data directory.</span></span> <span data-ttu-id="d2c20-245">这意味着一个 Edge 浏览器进程可能正在为多个呼叫流程提供服务，并且一个呼叫进程可能正在使用多个 Edge 浏览器进程。</span><span class="sxs-lookup"><span data-stu-id="d2c20-245">This means one Edge browser process may be serving multiple calling processes and one calling process may be using multiple Edge browser processes.</span></span>

![dot-inline-dotgraph-2](media/dot-inline-dotgraph-2.png)

<span data-ttu-id="d2c20-247">浏览器进程关闭时，将出现一些数量的呈现器进程。</span><span class="sxs-lookup"><span data-stu-id="d2c20-247">Off of a browser process there will be some number of renderer processes.</span></span> <span data-ttu-id="d2c20-248">根据需要创建这些类，以在不同的 WebViews 中服务潜在的多个帧。</span><span class="sxs-lookup"><span data-stu-id="d2c20-248">These are created as necessary to service potentially multiple frames in different WebViews.</span></span> <span data-ttu-id="d2c20-249">呈现器进程的数量因网站隔离浏览器功能和呈现在关联的 WebViews 中的独特断开的来源的数量而异。</span><span class="sxs-lookup"><span data-stu-id="d2c20-249">The number of renderer processes varies based on the site isolation browser feature and the number of distinct disconnected origins rendered in associated WebViews.</span></span>

![dot-inline-dotgraph-3](media/dot-inline-dotgraph-3.png)

<span data-ttu-id="d2c20-251">你可以使用 ProcessFailure 事件对这些浏览器和呈现器进程中的崩溃和挂起做出反应。</span><span class="sxs-lookup"><span data-stu-id="d2c20-251">You can react to crashes and hangs in these browser and renderer processes using the ProcessFailure event.</span></span>

<span data-ttu-id="d2c20-252">你可以使用 Close 方法安全地关闭关联的浏览器和呈现器进程。</span><span class="sxs-lookup"><span data-stu-id="d2c20-252">You can safely shutdown associated browser and renderer processes using the Close method.</span></span>

## <span data-ttu-id="d2c20-253">线程模型</span><span class="sxs-lookup"><span data-stu-id="d2c20-253">Threading model</span></span>

<span data-ttu-id="d2c20-254">WebView2 必须在 UI 线程上创建。</span><span class="sxs-lookup"><span data-stu-id="d2c20-254">The WebView2 must be created on a UI thread.</span></span> <span data-ttu-id="d2c20-255">专门使用消息泵的线程。</span><span class="sxs-lookup"><span data-stu-id="d2c20-255">Specifically a thread with a message pump.</span></span> <span data-ttu-id="d2c20-256">所有回调都将在该线程上发生，并且对 Web 视图的调用必须在该线程上完成。</span><span class="sxs-lookup"><span data-stu-id="d2c20-256">All callbacks will occur on that thread and calls into the WebView must be done on that thread.</span></span> <span data-ttu-id="d2c20-257">使用来自另一个线程的 Web 视图不安全。</span><span class="sxs-lookup"><span data-stu-id="d2c20-257">It is not safe to use the WebView from another thread.</span></span>

<span data-ttu-id="d2c20-258">回调包括事件处理程序和完成处理程序按顺序执行。</span><span class="sxs-lookup"><span data-stu-id="d2c20-258">Callbacks including event handlers and completion handlers execute serially.</span></span> <span data-ttu-id="d2c20-259">也就是说，如果你有一个事件处理程序正在运行并开始消息循环，则没有其他事件处理程序或完成回调将开始执行 reentrantly。</span><span class="sxs-lookup"><span data-stu-id="d2c20-259">That is, if you have an event handler running and begin a message loop no other event handlers or completion callbacks will begin executing reentrantly.</span></span>

## <span data-ttu-id="d2c20-260">安全</span><span class="sxs-lookup"><span data-stu-id="d2c20-260">Security</span></span>

<span data-ttu-id="d2c20-261">在使用 ExecuteScript、PostWebMessageAsJson、PostWebMessageAsString 或任何其他方法将信息发送到 Web 视图之前，请始终检查 Web 视图的 Source 属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-261">Always check the Source property of the WebView before using ExecuteScript, PostWebMessageAsJson, PostWebMessageAsString, or any other method to send information into the WebView.</span></span> <span data-ttu-id="d2c20-262">在导致导航的页面中，Web 视图可能会通过与页面或脚本交互的最终用户导航到另一个页面。</span><span class="sxs-lookup"><span data-stu-id="d2c20-262">The WebView may have navigated to another page via the end user interacting with the page or script in the page causing navigation.</span></span> <span data-ttu-id="d2c20-263">同样，请小心处理 AddScriptToExecuteOnDocumentCreated。</span><span class="sxs-lookup"><span data-stu-id="d2c20-263">Similarly, be very careful with AddScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="d2c20-264">所有将来的导航都将运行此脚本，如果它提供对仅适用于特定来源的信息的访问权限，则任何 HTML 文档都可能具有访问权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-264">All future navigations will run this script and if it provides access to information intended only for a certain origin, any HTML document may have access.</span></span>

<span data-ttu-id="d2c20-265">检查 ExecuteScript 方法调用的结果（WebMessageReceived 事件）时，请始终检查发件人的源或从 Web 视图中的 HTML 文档接收信息的任何其他机制验证 HTML 文档的 URI 是否是你所期望的内容。</span><span class="sxs-lookup"><span data-stu-id="d2c20-265">When examining the result of an ExecuteScript method call, a WebMessageReceived event, always check the Source of the sender, or any other mechanism of receiving information from an HTML document in a WebView validate the URI of the HTML document is what you expect.</span></span>

<span data-ttu-id="d2c20-266">构建要发送到 Web 视图的消息时，更喜欢使用 PostWebMessageAsJson 并使用 JSON 库构造 JSON 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-266">When constructing a message to send into a WebView, prefer using PostWebMessageAsJson and construct the JSON string parameter using a JSON library.</span></span> <span data-ttu-id="d2c20-267">这将避免任何潜在的编码信息意外进入 JSON 字符串或脚本并确保任何攻击者控制的输入都不能修改 JSON 消息的其余部分或运行任意脚本。</span><span class="sxs-lookup"><span data-stu-id="d2c20-267">This will avoid any potential accidents of encoding information into a JSON string or script and ensure no attacker controlled input can modify the rest of the JSON message or run arbitrary script.</span></span>

## <span data-ttu-id="d2c20-268">字符串类型</span><span class="sxs-lookup"><span data-stu-id="d2c20-268">String types</span></span>

<span data-ttu-id="d2c20-269">字符串输出参数是 LPWSTR null 终止的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2c20-269">String out parameters are LPWSTR null terminated strings.</span></span> <span data-ttu-id="d2c20-270">被调用方使用 CoTaskMemAlloc 分配字符串。</span><span class="sxs-lookup"><span data-stu-id="d2c20-270">The callee allocates the string using CoTaskMemAlloc.</span></span> <span data-ttu-id="d2c20-271">所有权转移到呼叫方，由呼叫方负责使用 CoTaskMemFree 释放内存。</span><span class="sxs-lookup"><span data-stu-id="d2c20-271">Ownership is transferred to the caller and it is up to the caller to free the memory using CoTaskMemFree.</span></span>

<span data-ttu-id="d2c20-272">参数中的字符串是 LPCWSTR null 终止的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2c20-272">String in parameters are LPCWSTR null terminated strings.</span></span> <span data-ttu-id="d2c20-273">调用方确保字符串在同步函数调用期间有效。</span><span class="sxs-lookup"><span data-stu-id="d2c20-273">The caller ensures the string is valid for the duration of the synchronous function call.</span></span> <span data-ttu-id="d2c20-274">如果被调用方需要在函数调用完成后将该值保留到某个点，则被调用方必须分配其自己的字符串值副本。</span><span class="sxs-lookup"><span data-stu-id="d2c20-274">If the callee needs to retain that value to some point after the function call completes, the callee must allocate its own copy of the string value.</span></span>

## <span data-ttu-id="d2c20-275">URI 和 JSON 分析</span><span class="sxs-lookup"><span data-stu-id="d2c20-275">URI and JSON parsing</span></span>

<span data-ttu-id="d2c20-276">各种方法以字符串形式提供或接受 Uri 和 JSON。</span><span class="sxs-lookup"><span data-stu-id="d2c20-276">Various methods provide or accept URIs and JSON as strings.</span></span> <span data-ttu-id="d2c20-277">请使用你的首选库来分析和生成这些字符串。</span><span class="sxs-lookup"><span data-stu-id="d2c20-277">Please use your own preferred library for parsing and generating these strings.</span></span>

<span data-ttu-id="d2c20-278">如果 WinRT 适用于你的应用，则可以使用 `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` 分析或生成 JSON 字符串， `RuntimeClass_Windows_Foundation_Uri` 或者 `IUriRuntimeClassFactory` 分析和生成 uri。</span><span class="sxs-lookup"><span data-stu-id="d2c20-278">If WinRT is available for your app you can use `RuntimeClass_Windows_Data_Json_JsonObject` and `IJsonObjectStatics` to parse or produce JSON strings or `RuntimeClass_Windows_Foundation_Uri` and `IUriRuntimeClassFactory` to parse and produce URIs.</span></span> <span data-ttu-id="d2c20-279">这两个功能都在 Win32 应用中使用。</span><span class="sxs-lookup"><span data-stu-id="d2c20-279">Both of these work in Win32 apps.</span></span>

<span data-ttu-id="d2c20-280">如果你使用 IUri 和 CreateUri 来分析 Uri，你可能希望使用以下 URI 创建标志使 CreateUri 行为与 Web 视图中的 URI 分析更密切匹配：</span><span class="sxs-lookup"><span data-stu-id="d2c20-280">If you use IUri and CreateUri to parse URIs you may want to use the following URI creation flags to have CreateUri behavior more closely match the URI parsing in the WebView:</span></span> `Uri_CREATE_ALLOW_IMPLICIT_FILE_SCHEME | Uri_CREATE_NO_DECODE_EXTRA_INFO`

## <span data-ttu-id="d2c20-281">调试</span><span class="sxs-lookup"><span data-stu-id="d2c20-281">Debugging</span></span>

<span data-ttu-id="d2c20-282">打开具有普通快捷方式的 DevTools： `F12` 或 `Ctrl+Shift+I` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-282">Open DevTools with the normal shortcuts: `F12` or `Ctrl+Shift+I`.</span></span> <span data-ttu-id="d2c20-283">在 `--auto-open-devtools-for-tabs` 首次创建 Web 视图时，可以使用 command 参数开关让 DevTools 窗口立即打开。</span><span class="sxs-lookup"><span data-stu-id="d2c20-283">You can use the `--auto-open-devtools-for-tabs` command argument switch to have the DevTools window open immediately when first creating a WebView.</span></span> <span data-ttu-id="d2c20-284">有关如何向浏览器进程提供其他命令行参数，请参阅 CreateWebView 文档。</span><span class="sxs-lookup"><span data-stu-id="d2c20-284">See CreateWebView documentation for how to provide additional command line arguments to the browser process.</span></span> <span data-ttu-id="d2c20-285">签出 LoaderOverride 注册表项，在 CreateWebView 文档中无需修改你的应用程序，即可试用不同版本的 WebView2。</span><span class="sxs-lookup"><span data-stu-id="d2c20-285">Check out the LoaderOverride registry key for trying out different builds of WebView2 without modifying your application in the CreateWebView documentation.</span></span>

## <span data-ttu-id="d2c20-286">版本控制</span><span class="sxs-lookup"><span data-stu-id="d2c20-286">Versioning</span></span>

<span data-ttu-id="d2c20-287">在使用特定版本的 SDK 构建你的应用后，你的应用可能会使用已安装的旧版本或更高版本的浏览器二进制文件运行。</span><span class="sxs-lookup"><span data-stu-id="d2c20-287">After you've used a particular version of the SDK to build your app, your app may end up running with an older or newer version of installed browser binaries.</span></span> <span data-ttu-id="d2c20-288">在 WebView2 版本1.0.0.0 之前，可能会在更新期间发生中断更改，这些更改将阻止你的 SDK 使用安装的浏览器二进制文件的不同版本。</span><span class="sxs-lookup"><span data-stu-id="d2c20-288">Until version 1.0.0.0 of WebView2 there may be breaking changes during updates that will prevent your SDK from working with different versions of installed browser binaries.</span></span> <span data-ttu-id="d2c20-289">在版本1.0.0.0 后，SDK 的不同版本可以按照以下最佳做法使用安装的浏览器的不同版本：</span><span class="sxs-lookup"><span data-stu-id="d2c20-289">After version 1.0.0.0 different versions of the SDK can work with different versions of the installed browser by following these best practices:</span></span>

<span data-ttu-id="d2c20-290">若要对 API 进行重大更改，请确保在调用 DLL 导出 CreateWebView2Environment 时和在任何 WebView2 对象上调用 QueryInterface 时检查是否失败。</span><span class="sxs-lookup"><span data-stu-id="d2c20-290">To account for breaking changes to the API be sure to check for failure when calling the DLL export CreateWebView2Environment and when calling QueryInterface on any WebView2 object.</span></span> <span data-ttu-id="d2c20-291">E_NOINTERFACE 的返回值可指示 SDK 与 Edge 浏览器二进制文件不兼容。</span><span class="sxs-lookup"><span data-stu-id="d2c20-291">A return value of E_NOINTERFACE can indicate the SDK is not compatible with the Edge browser binaries.</span></span>

<span data-ttu-id="d2c20-292">从 QueryInterface 检查失败还将考虑 SDK 比 Edge 浏览器的版本更新的情况，并且你的应用尝试使用 Edge 浏览器不兼容的接口。</span><span class="sxs-lookup"><span data-stu-id="d2c20-292">Checking for failure from QueryInterface will also account for cases where the SDK is newer than the version of the Edge browser and your app attempts to use an interface of which the Edge browser is unaware.</span></span>

<span data-ttu-id="d2c20-293">当接口不可用时，你可以考虑禁用关联的功能（如果可能），或者向最终用户通知他们需要更新其浏览器。</span><span class="sxs-lookup"><span data-stu-id="d2c20-293">When an interface is unavailable, you can consider disabling the associated feature if possible, or otherwise informing the end user they need to update their browser.</span></span>

## <span data-ttu-id="d2c20-294">成员</span><span class="sxs-lookup"><span data-stu-id="d2c20-294">Members</span></span>

#### <span data-ttu-id="d2c20-295">get_Settings</span><span class="sxs-lookup"><span data-stu-id="d2c20-295">get_Settings</span></span> 

<span data-ttu-id="d2c20-296">[IWebView2Settings](IWebView2Settings.md)对象包含运行的 web 视图的各种可修改设置。</span><span class="sxs-lookup"><span data-stu-id="d2c20-296">The [IWebView2Settings](IWebView2Settings.md) object contains various modifiable settings for the running WebView.</span></span>

> <span data-ttu-id="d2c20-297">公共 HRESULT [get_Settings](#get_settings)（[IWebView2Settings](IWebView2Settings.md) \* \* 设置）</span><span class="sxs-lookup"><span data-stu-id="d2c20-297">public HRESULT [get_Settings](#get_settings)([IWebView2Settings](IWebView2Settings.md) \*\* settings)</span></span>

#### <span data-ttu-id="d2c20-298">get_Source</span><span class="sxs-lookup"><span data-stu-id="d2c20-298">get_Source</span></span> 

<span data-ttu-id="d2c20-299">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="d2c20-299">The URI of the current top level document.</span></span>

> <span data-ttu-id="d2c20-300">公共 HRESULT [get_Source](#get_source)（LPWSTR \* uri）</span><span class="sxs-lookup"><span data-stu-id="d2c20-300">public HRESULT [get_Source](#get_source)(LPWSTR \* uri)</span></span>

<span data-ttu-id="d2c20-301">在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 DocumentStateChanged 事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="d2c20-301">This value potentially changes as a part of the DocumentStateChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="d2c20-302">它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。</span><span class="sxs-lookup"><span data-stu-id="d2c20-302">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
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
        &m_documentStateChangedToken));
```

#### <span data-ttu-id="d2c20-303">导航</span><span class="sxs-lookup"><span data-stu-id="d2c20-303">Navigate</span></span> 

<span data-ttu-id="d2c20-304">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="d2c20-304">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="d2c20-305">公共 HRESULT[导航](#navigate)（LPCWSTR uri）</span><span class="sxs-lookup"><span data-stu-id="d2c20-305">public HRESULT [Navigate](#navigate)(LPCWSTR uri)</span></span>

<span data-ttu-id="d2c20-306">有关详细信息，请参阅导航事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-306">See the navigation events for more information.</span></span> <span data-ttu-id="d2c20-307">请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-307">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

```cpp
void ControlComponent::NavigateToAddressBar()
{
    WCHAR uri[2048] = L"";
    GetWindowText(m_toolbar->addressBarWindow, uri, ARRAYSIZE(uri));
    CHECK_FAILURE(m_webView->Navigate(uri));
}
```

#### <span data-ttu-id="d2c20-308">MoveFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-308">MoveFocus</span></span> 

<span data-ttu-id="d2c20-309">将焦点移动到 Web 视图中。</span><span class="sxs-lookup"><span data-stu-id="d2c20-309">Move focus into WebView.</span></span>

> <span data-ttu-id="d2c20-310">公共 HRESULT [MoveFocus](#movefocus)（[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)原因）</span><span class="sxs-lookup"><span data-stu-id="d2c20-310">public HRESULT [MoveFocus](#movefocus)([WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason) reason)</span></span>

<span data-ttu-id="d2c20-311">在 Web 视图中托管的页面中，Web 视图将获得焦点，并且焦点将被设置为通信元素。</span><span class="sxs-lookup"><span data-stu-id="d2c20-311">WebView will get focus and focus will be set to correspondent element in the page hosted in the WebView.</span></span> <span data-ttu-id="d2c20-312">出于编程原因，焦点设置为以前具有焦点的元素，如果没有以前具有焦点的元素，则设置为默认元素。</span><span class="sxs-lookup"><span data-stu-id="d2c20-312">For Programmatic reason, focus is set to previously focused element or the default element if there is no previously focused element.</span></span> <span data-ttu-id="d2c20-313">出于下一个原因，焦点设置为第一个元素。</span><span class="sxs-lookup"><span data-stu-id="d2c20-313">For Next reason, focus is set to the first element.</span></span> <span data-ttu-id="d2c20-314">对于上一个原因，焦点设置为最后一个元素。</span><span class="sxs-lookup"><span data-stu-id="d2c20-314">For Previous reason, focus is set to the last element.</span></span> <span data-ttu-id="d2c20-315">Web 视图还可以通过用户交互获得焦点，例如单击 "在 Web 视图中" 或 "Tab"。</span><span class="sxs-lookup"><span data-stu-id="d2c20-315">WebView can also got focus through user interaction like clicking into WebView or Tab into it.</span></span> <span data-ttu-id="d2c20-316">对于 "按 tab 键"，应用可以调用 MoveFocus 和 "下一个" 或 "上一步"，以便在确定 Web 视图是下一个 tabbable 元素时，分别与 tab 和 shift + tab 对齐。</span><span class="sxs-lookup"><span data-stu-id="d2c20-316">For tabbing, the app can call MoveFocus with Next or Previous to align with tab and shift+tab respectively when it decides the WebView is the next tabbable element.</span></span> <span data-ttu-id="d2c20-317">或者，应用可以将 IsDialogMessage 作为其消息循环的一部分进行调用，以允许平台自动处理 tab 键切换。</span><span class="sxs-lookup"><span data-stu-id="d2c20-317">Or, the app can call IsDialogMessage as part of its message loop to allow the platform to auto handle tabbing.</span></span> <span data-ttu-id="d2c20-318">平台将通过 WS_TABSTOP 旋转所有窗口。</span><span class="sxs-lookup"><span data-stu-id="d2c20-318">The platform will rotate through all windows with WS_TABSTOP.</span></span> <span data-ttu-id="d2c20-319">当 Web 视图从 IsDialogMessage 获取焦点时，它将分别在 tab 和 shift + tab 的第一个或最后一个元素上放置焦点。</span><span class="sxs-lookup"><span data-stu-id="d2c20-319">When the WebView gets focus from IsDialogMessage, it will internally put the focus on the first or last element for tab and shift+tab respectively.</span></span>

```cpp
    while (GetMessage(&msg, nullptr, 0, 0))
    {
        if (!TranslateAccelerator(msg.hwnd, hAccelTable, &msg))
        {
            // Calling IsDialogMessage handles Tab traversal automatically. If the
            // app wants the platform to auto handle tab, then call IsDialogMessage
            // before calling TranslateMessage/DispatchMessage. If the app wants to
            // handle tabbing itself, then skip calling IsDialogMessage and call
            // TranslateMessage/DispatchMessage directly.
            if (!g_autoTabHandle || !IsDialogMessage(GetAncestor(msg.hwnd, GA_ROOT), &msg))
            {
                TranslateMessage(&msg);
                DispatchMessage(&msg);
            }
        }
    }
```

```cpp
        if (wParam == VK_TAB)
        {
            // Find out if the window is one we've customized for tab handling
            for (int i = 0; i < m_tabbableWindows.size(); i++)
            {
                if (m_tabbableWindows[i].first == hWnd)
                {
                    if (GetKeyState(VK_SHIFT) < 0)
                    {
                        TabBackwards(i);
                    }
                    else
                    {
                        TabForwards(i);
                    }
                    return true;
                }
            }
        }
```

```cpp
void ControlComponent::TabForwards(int currentIndex)
{
    // Find first enabled window after the active one
    for (int i = currentIndex + 1; i < m_tabbableWindows.size(); i++)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_NEXT);
}

void ControlComponent::TabBackwards(int currentIndex)
{
    // Find first enabled window before the active one
    for (int i = currentIndex - 1; i >= 0; i--)
    {
        HWND hwnd = m_tabbableWindows.at(i).first;
        if (IsWindowEnabled(hwnd))
        {
            SetFocus(hwnd);
            return;
        }
    }
    // If this is the last enabled window, tab forwards into the WebView.
    CHECK_FAILURE(m_webView->MoveFocus(WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS));
}
```

#### <span data-ttu-id="d2c20-320">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="d2c20-320">NavigateToString</span></span> 

<span data-ttu-id="d2c20-321">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="d2c20-321">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="d2c20-322">公共 HRESULT [NavigateToString](#navigatetostring)（LPCWSTR htmlContent）</span><span class="sxs-lookup"><span data-stu-id="d2c20-322">public HRESULT [NavigateToString](#navigatetostring)(LPCWSTR htmlContent)</span></span>

<span data-ttu-id="d2c20-323">HtmlContent 参数不能大于 2 MB 的字符。</span><span class="sxs-lookup"><span data-stu-id="d2c20-323">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="d2c20-324">新页面的来源将显示为 "空白"。</span><span class="sxs-lookup"><span data-stu-id="d2c20-324">The origin of the new page will be about:blank.</span></span>

```cpp
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
```

#### <span data-ttu-id="d2c20-325">add_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-325">add_NavigationStarting</span></span> 

<span data-ttu-id="d2c20-326">为 NavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-326">Add an event handler for the NavigationStarting event.</span></span>

> <span data-ttu-id="d2c20-327">public HRESULT [add_NavigationStarting](#add_navigationstarting)（[IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-327">public HRESULT [add_NavigationStarting](#add_navigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-328">当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="d2c20-328">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="d2c20-329">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="d2c20-329">This will fire for redirects as well.</span></span>

```cpp
    // Register a handler for the NavigationStarting event.
    // This handler will check the domain being navigated to, and if the domain
    // matches a list of blocked sites, it will cancel the navigation and
    // possibly display a warning page.  It will also disable JavaScript on
    // selected websites.
    CHECK_FAILURE(m_webView->add_NavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Uri(&uri));

        if (ShouldBlockUri(uri.get()))
        {
            CHECK_FAILURE(args->put_Cancel(true));

            // If the user clicked a link to navigate, show a warning page.
            BOOL userInitiated;
            CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));
            if (userInitiated)
            {
                static const PCWSTR htmlContent =
                    L"<h1>Domain Blocked</h1>"
                    L"<p>You've attempted to navigate to a domain in the blocked "
                    L"sites list. Press back to return to the previous page.</p>";
                CHECK_FAILURE(sender->NavigateToString(htmlContent));
            }
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

#### <span data-ttu-id="d2c20-330">remove_NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-330">remove_NavigationStarting</span></span> 

<span data-ttu-id="d2c20-331">删除以前使用 add_NavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-331">Remove an event handler previously added with add_NavigationStarting.</span></span>

> <span data-ttu-id="d2c20-332">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-332">public HRESULT [remove_NavigationStarting](#remove_navigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-333">add_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-333">add_DocumentStateChanged</span></span> 

<span data-ttu-id="d2c20-334">为 DocumentStateChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-334">Add an event handler for the DocumentStateChanged event.</span></span>

> <span data-ttu-id="d2c20-335">public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)（[IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-335">public HRESULT [add_DocumentStateChanged](#add_documentstatechanged)([IWebView2DocumentStateChangedEventHandler](IWebView2DocumentStateChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-336">当新内容在 web 视图的主框架上开始加载或出现相同的页面导航时（例如通过片段导航或 pushState 导航），将触发 DocumentStateChanged。</span><span class="sxs-lookup"><span data-stu-id="d2c20-336">DocumentStateChanged fires when new content has started loading on the webview's main frame or if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span> <span data-ttu-id="d2c20-337">这将遵循 NavigationStarting 事件，并在 NavigationCompleted 事件之前。</span><span class="sxs-lookup"><span data-stu-id="d2c20-337">This follows the NavigationStarting event and precedes the NavigationCompleted event.</span></span>

```cpp
    // Register a handler for the DocumentStateChanged event.
    // This handler will read the webview's source URI and update
    // the app's address bar.
    CHECK_FAILURE(m_webView->add_DocumentStateChanged(
        Callback<IWebView2DocumentStateChangedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2DocumentStateChangedEventArgs* args)
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
        &m_documentStateChangedToken));
```

#### <span data-ttu-id="d2c20-338">remove_DocumentStateChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-338">remove_DocumentStateChanged</span></span> 

<span data-ttu-id="d2c20-339">删除以前使用 add_DocumentStateChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-339">Remove an event handler previously added with add_DocumentStateChanged.</span></span>

> <span data-ttu-id="d2c20-340">public HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-340">public HRESULT [remove_DocumentStateChanged](#remove_documentstatechanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-341">add_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d2c20-341">add_NavigationCompleted</span></span> 

<span data-ttu-id="d2c20-342">为 NavigationCompleted 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-342">Add an event handler for the NavigationCompleted event.</span></span>

> <span data-ttu-id="d2c20-343">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)（[IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-343">public HRESULT [add_NavigationCompleted](#add_navigationcompleted)([IWebView2NavigationCompletedEventHandler](IWebView2NavigationCompletedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-344">当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-344">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

```cpp
    // Register a handler for the NavigationCompleted event.
    // Check whether the navigation succeeded, and if not, do something.
    // Also update the Back, Forward, and Cancel buttons.
    CHECK_FAILURE(m_webView->add_NavigationCompleted(
        Callback<IWebView2NavigationCompletedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2NavigationCompletedEventArgs* args)
                -> HRESULT {
                BOOL success;
                CHECK_FAILURE(args->get_IsSuccess(&success));
                if (!success)
                {
                    WEBVIEW2_WEB_ERROR_STATUS webErrorStatus;
                    CHECK_FAILURE(args->get_WebErrorStatus(&webErrorStatus));
                    if (webErrorStatus == WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED)
                    {
                        // Do something here if you want to handle a specific error case.
                        // In most cases this isn't necessary, because the WebView will
                        // display its own error page automatically.
                    }
                }

                BOOL canGoBack;
                BOOL canGoForward;
                sender->get_CanGoBack(&canGoBack);
                sender->get_CanGoForward(&canGoForward);
                EnableWindow(m_toolbar->backWindow, canGoBack);
                EnableWindow(m_toolbar->forwardWindow, canGoForward);
                EnableWindow(m_toolbar->cancelWindow, FALSE);
                return S_OK;
            })
            .Get(),
        &m_navigationCompletedToken));
```

#### <span data-ttu-id="d2c20-345">remove_NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="d2c20-345">remove_NavigationCompleted</span></span> 

<span data-ttu-id="d2c20-346">删除以前使用 add_NavigationCompleted 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-346">Remove an event handler previously added with add_NavigationCompleted.</span></span>

> <span data-ttu-id="d2c20-347">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-347">public HRESULT [remove_NavigationCompleted](#remove_navigationcompleted)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-348">add_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-348">add_FrameNavigationStarting</span></span> 

<span data-ttu-id="d2c20-349">为 FrameNavigationStarting 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-349">Add an event handler for the FrameNavigationStarting event.</span></span>

> <span data-ttu-id="d2c20-350">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)（[IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-350">public HRESULT [add_FrameNavigationStarting](#add_framenavigationstarting)([IWebView2NavigationStartingEventHandler](IWebView2NavigationStartingEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-351">当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="d2c20-351">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span> <span data-ttu-id="d2c20-352">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="d2c20-352">This will fire for redirects as well.</span></span>

```cpp
    // Register a handler for the FrameNavigationStarting event.
    // This handler will prevent a frame from navigating to a blocked domain.
    CHECK_FAILURE(m_webView->add_FrameNavigationStarting(
        Callback<IWebView2NavigationStartingEventHandler>(
            [this](IWebView2WebView* sender,
                   IWebView2NavigationStartingEventArgs* args) -> HRESULT
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

#### <span data-ttu-id="d2c20-353">remove_FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="d2c20-353">remove_FrameNavigationStarting</span></span> 

<span data-ttu-id="d2c20-354">删除以前使用 add_FrameNavigationStarting 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-354">Remove an event handler previously added with add_FrameNavigationStarting.</span></span>

> <span data-ttu-id="d2c20-355">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-355">public HRESULT [remove_FrameNavigationStarting](#remove_framenavigationstarting)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-356">add_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-356">add_MoveFocusRequested</span></span> 

<span data-ttu-id="d2c20-357">为 MoveFocusRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-357">Add an event handler for the MoveFocusRequested event.</span></span>

> <span data-ttu-id="d2c20-358">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)（[IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-358">public HRESULT [add_MoveFocusRequested](#add_movefocusrequested)([IWebView2MoveFocusRequestedEventHandler](IWebView2MoveFocusRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-359">当用户尝试注销 Web 视图时，将触发 MoveFocusRequested。</span><span class="sxs-lookup"><span data-stu-id="d2c20-359">MoveFocusRequested fires when user tries to tab out of the WebView.</span></span> <span data-ttu-id="d2c20-360">激发此事件时，Web 视图的焦点未发生更改。</span><span class="sxs-lookup"><span data-stu-id="d2c20-360">The WebView's focus has not changed when this event is fired.</span></span>

```cpp
    // Register a handler for the MoveFocusRequested event.
    // This event will be fired when the user tabs out of the webview.
    // The handler will focus another window in the app, depending on which
    // direction the focus is being shifted.
    CHECK_FAILURE(m_webView->add_MoveFocusRequested(
        Callback<IWebView2MoveFocusRequestedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2MoveFocusRequestedEventArgs* args)
                -> HRESULT {
                if (!g_autoTabHandle)
                {
                    WEBVIEW2_MOVE_FOCUS_REASON reason;
                    CHECK_FAILURE(args->get_Reason(&reason));

                    if (reason == WEBVIEW2_MOVE_FOCUS_REASON_NEXT)
                    {
                        TabForwards(-1);
                    }
                    else if (reason == WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS)
                    {
                        TabBackwards(int(m_tabbableWindows.size()));
                    }
                    CHECK_FAILURE(args->put_Handled(TRUE));
                }
                return S_OK;
            })
            .Get(),
        &m_moveFocusRequestedToken));
```

#### <span data-ttu-id="d2c20-361">remove_MoveFocusRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-361">remove_MoveFocusRequested</span></span> 

<span data-ttu-id="d2c20-362">删除以前使用 add_MoveFocusRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-362">Remove an event handler previously added with add_MoveFocusRequested.</span></span>

> <span data-ttu-id="d2c20-363">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-363">public HRESULT [remove_MoveFocusRequested](#remove_movefocusrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-364">add_GotFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-364">add_GotFocus</span></span> 

<span data-ttu-id="d2c20-365">为 GotFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-365">Add an event handler for the GotFocus event.</span></span>

> <span data-ttu-id="d2c20-366">public HRESULT [add_GotFocus](#add_gotfocus)（[IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-366">public HRESULT [add_GotFocus](#add_gotfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-367">当 Web 视图获得焦点时，将引发 GotFocus。</span><span class="sxs-lookup"><span data-stu-id="d2c20-367">GotFocus fires when WebView got focus.</span></span>

#### <span data-ttu-id="d2c20-368">remove_GotFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-368">remove_GotFocus</span></span> 

<span data-ttu-id="d2c20-369">删除以前使用 add_GotFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-369">Remove an event handler previously added with add_GotFocus.</span></span>

> <span data-ttu-id="d2c20-370">public HRESULT [remove_GotFocus](#remove_gotfocus)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-370">public HRESULT [remove_GotFocus](#remove_gotfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-371">add_LostFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-371">add_LostFocus</span></span> 

<span data-ttu-id="d2c20-372">为 LostFocus 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-372">Add an event handler for the LostFocus event.</span></span>

> <span data-ttu-id="d2c20-373">public HRESULT [add_LostFocus](#add_lostfocus)（[IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-373">public HRESULT [add_LostFocus](#add_lostfocus)([IWebView2FocusChangedEventHandler](IWebView2FocusChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-374">当 Web 视图失去焦点时，将激发 LostFocus。</span><span class="sxs-lookup"><span data-stu-id="d2c20-374">LostFocus fires when WebView lost focus.</span></span> <span data-ttu-id="d2c20-375">在引发 MoveFocusRequested 事件的情况下，当 MoveFocusRequested 事件引发时，焦点仍在 Web 视图上。</span><span class="sxs-lookup"><span data-stu-id="d2c20-375">In the case where MoveFocusRequested event is fired, the focus is still on WebView when MoveFocusRequested event fires.</span></span> <span data-ttu-id="d2c20-376">只有在应用的 MoveFocusRequested 事件或从 Web 视图中设置焦点的情况下，才会在应用的代码或默认操作时引发丢失焦点。</span><span class="sxs-lookup"><span data-stu-id="d2c20-376">Lost focus only fires afterwards when app's code or default action of MoveFocusRequested event set focus away from WebView.</span></span>

#### <span data-ttu-id="d2c20-377">remove_LostFocus</span><span class="sxs-lookup"><span data-stu-id="d2c20-377">remove_LostFocus</span></span> 

<span data-ttu-id="d2c20-378">删除以前使用 add_LostFocus 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-378">Remove an event handler previously added with add_LostFocus.</span></span>

> <span data-ttu-id="d2c20-379">public HRESULT [remove_LostFocus](#remove_lostfocus)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-379">public HRESULT [remove_LostFocus](#remove_lostfocus)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-380">add_WebResourceRequested_deprecated</span><span class="sxs-lookup"><span data-stu-id="d2c20-380">add_WebResourceRequested_deprecated</span></span> 

<span data-ttu-id="d2c20-381">此 API 将被弃用，请使用新的 add_WebResourceRequested API。</span><span class="sxs-lookup"><span data-stu-id="d2c20-381">This API will be deprecated, please use the new add_WebResourceRequested API.</span></span>

> <span data-ttu-id="d2c20-382">public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)（LPCWSTR \* const urlFilter，[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \* Const resourceContextFilter，SIZE_T filterLength，[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-382">public HRESULT [add_WebResourceRequested_deprecated](#add_webresourcerequested_deprecated)(LPCWSTR \*const urlFilter,[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context) \*const resourceContextFilter,SIZE_T filterLength,[IWebView2WebResourceRequestedEventHandler](IWebView2WebResourceRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-383">为 WebResourceRequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-383">Add an event handler for the WebResourceRequested event.</span></span> <span data-ttu-id="d2c20-384">在 Web 视图执行任何 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-384">Fires when the WebView has performs any HTTP request.</span></span> <span data-ttu-id="d2c20-385">使用 urlFilter 将列表传递到要侦听的 url 的大小 filterLength。</span><span class="sxs-lookup"><span data-stu-id="d2c20-385">Use urlFilter to pass in a list with size filterLength of urls to listen for.</span></span> <span data-ttu-id="d2c20-386">每个 url 条目还支持通配符： "\*" 匹配零个或多个字符，"？" 与一个字符完全匹配。</span><span class="sxs-lookup"><span data-stu-id="d2c20-386">Each url entry also supports wildcards: '\*' matches zero or more characters, and '?' matches exactly one character.</span></span> <span data-ttu-id="d2c20-387">对于每个 urlFilter 条目，提供匹配的 resourceContextFilter，表示 WebResourceRequested 应触发的资源类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-387">For each urlFilter entry, provide a matching resourceContextFilter representing the types of resources for which WebResourceRequested should fire.</span></span> <span data-ttu-id="d2c20-388">如果 filterLength 为0，则将针对所有网络请求触发该事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-388">If filterLength is 0, the event will fire for all network requests.</span></span> <span data-ttu-id="d2c20-389">受支持的资源上下文包括：文档、样式表、图像、媒体、字体、脚本、XHR、Fetch。</span><span class="sxs-lookup"><span data-stu-id="d2c20-389">The supported resource contexts are: Document, Stylesheet, Image, Media, Font, Script, XHR, Fetch.</span></span>

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

#### <span data-ttu-id="d2c20-390">remove_WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-390">remove_WebResourceRequested</span></span> 

<span data-ttu-id="d2c20-391">删除以前使用 add_WebResourceRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-391">Remove an event handler previously added with add_WebResourceRequested.</span></span>

> <span data-ttu-id="d2c20-392">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-392">public HRESULT [remove_WebResourceRequested](#remove_webresourcerequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-393">add_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="d2c20-393">add_ScriptDialogOpening</span></span> 

<span data-ttu-id="d2c20-394">为 ScriptDialogOpening 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-394">Add an event handler for the ScriptDialogOpening event.</span></span>

> <span data-ttu-id="d2c20-395">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)（[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-395">public HRESULT [add_ScriptDialogOpening](#add_scriptdialogopening)([IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-396">将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-396">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span> <span data-ttu-id="d2c20-397">仅当 IWebView2Settings：： AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-397">This event only fires if the IWebView2Settings::AreDefaultScriptDialogsEnabled property is set to false.</span></span>

```cpp
    // Register a handler for the ScriptDialogOpening event.
    // This handler will set up a custom prompt dialog for the user,
    // and may defer the event if the setting to defer dialogs is enabled.
    CHECK_FAILURE(m_webView->add_ScriptDialogOpening(
        Callback<IWebView2ScriptDialogOpeningEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2ScriptDialogOpeningEventArgs* args) -> HRESULT
    {
        wil::com_ptr<IWebView2ScriptDialogOpeningEventArgs> eventArgs = args;
        auto showDialog = [this, eventArgs]
        {
            wil::unique_cotaskmem_string uri;
            WEBVIEW2_SCRIPT_DIALOG_KIND type;
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
                /* readonly */ type != WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT);
            if (dialog.confirmed)
            {
                CHECK_FAILURE(eventArgs->put_ResultText(dialog.input.c_str()));
                CHECK_FAILURE(eventArgs->Accept());
            }
        };

        if (m_deferScriptDialogs)
        {
            wil::com_ptr<IWebView2Deferral> deferral;
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

#### <span data-ttu-id="d2c20-398">remove_ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="d2c20-398">remove_ScriptDialogOpening</span></span> 

<span data-ttu-id="d2c20-399">删除以前使用 add_ScriptDialogOpening 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-399">Remove an event handler previously added with add_ScriptDialogOpening.</span></span>

> <span data-ttu-id="d2c20-400">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-400">public HRESULT [remove_ScriptDialogOpening](#remove_scriptdialogopening)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-401">add_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-401">add_ZoomFactorChanged</span></span> 

<span data-ttu-id="d2c20-402">为 ZoomFactorChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-402">Add an event handler for the ZoomFactorChanged event.</span></span>

> <span data-ttu-id="d2c20-403">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)（[IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-403">public HRESULT [add_ZoomFactorChanged](#add_zoomfactorchanged)([IWebView2ZoomFactorChangedEventHandler](IWebView2ZoomFactorChangedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-404">当 Web 视图的 ZoomFactor 属性更改时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-404">The event fires when the ZoomFactor property of the WebView changes.</span></span> <span data-ttu-id="d2c20-405">由于调用方修改了 ZoomFactor 属性，或者由于用户手动修改缩放，因此可能会激发该事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-405">The event could fire because the caller modified the ZoomFactor property, or due to the user manually modifying the zoom.</span></span> <span data-ttu-id="d2c20-406">当调用方通过 ZoomFactor 属性对其进行修改时，内部缩放系数将立即更新，并且将不会出现 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-406">When it is modified by the caller via the ZoomFactor property, the internal zoom factor is updated immediately and there will be no ZoomFactorChanged event.</span></span> <span data-ttu-id="d2c20-407">Web 视图将每个网站的上次使用的缩放系数相关联。</span><span class="sxs-lookup"><span data-stu-id="d2c20-407">WebView associates the last used zoom factor for each site.</span></span> <span data-ttu-id="d2c20-408">因此，在导航到其他页面时，可以更改缩放系数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-408">Therefore, it is possible for the zoom factor to change when navigating to a different page.</span></span> <span data-ttu-id="d2c20-409">当缩放系数因此而更改时，ZoomFactorChanged 事件将在 DocumentStateChanged 事件后立即触发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-409">When the zoom factor changes due to this, the ZoomFactorChanged event fires right after the DocumentStateChanged event.</span></span>

```cpp
    // Register a handler for the ZoomFactorChanged event.
    // This handler just announces the new level of zoom on the window's title bar.
    CHECK_FAILURE(m_webView->add_ZoomFactorChanged(
        Callback<IWebView2ZoomFactorChangedEventHandler>(
            [this](IWebView2WebView* sender, IUnknown* args) -> HRESULT {
                double zoomFactor;
                CHECK_FAILURE(sender->get_ZoomFactor(&zoomFactor));

                std::wstring message = L"WebView2APISample (Zoom: " +
                                       std::to_wstring(int(zoomFactor * 100)) + L"%)";
                SetWindowText(m_appWindow->GetMainWindow(), message.c_str());
                return S_OK;
            })
            .Get(),
        &m_zoomFactorChangedToken));
```

#### <span data-ttu-id="d2c20-410">remove_ZoomFactorChanged</span><span class="sxs-lookup"><span data-stu-id="d2c20-410">remove_ZoomFactorChanged</span></span> 

<span data-ttu-id="d2c20-411">删除以前使用 add_ZoomFactorChanged 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-411">Remove an event handler previously added with add_ZoomFactorChanged.</span></span>

> <span data-ttu-id="d2c20-412">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-412">public HRESULT [remove_ZoomFactorChanged](#remove_zoomfactorchanged)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-413">add_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-413">add_PermissionRequested</span></span> 

<span data-ttu-id="d2c20-414">为 Webview.permissionrequested 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-414">Add an event handler for the PermissionRequested event.</span></span>

> <span data-ttu-id="d2c20-415">public HRESULT [add_PermissionRequested](#add_permissionrequested)（[IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-415">public HRESULT [add_PermissionRequested](#add_permissionrequested)([IWebView2PermissionRequestedEventHandler](IWebView2PermissionRequestedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-416">在 Web 视图中的内容请求访问某些权限资源的权限时引发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-416">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

```cpp
    // Register a handler for the PermissionRequested event.
    // This handler prompts the user to allow or deny the request.
    CHECK_FAILURE(m_webView->add_PermissionRequested(
        Callback<IWebView2PermissionRequestedEventHandler>(
            [this](
                IWebView2WebView* sender,
                IWebView2PermissionRequestedEventArgs* args) -> HRESULT
    {
        wil::unique_cotaskmem_string uri;
        WEBVIEW2_PERMISSION_TYPE type = WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION;
        BOOL userInitiated = FALSE;

        CHECK_FAILURE(args->get_Uri(&uri));
        CHECK_FAILURE(args->get_PermissionType(&type));
        CHECK_FAILURE(args->get_IsUserInitiated(&userInitiated));

        std::wstring message = L"Do you want to grant permission for ";
        message += NameOfPermissionType(type);
        message += L" to the website at ";
        message += uri.get();
        message += L"?\n\n";
        message += (userInitiated
            ? L"This request came from a user gesture."
            : L"This request did not come from a user gesture.");

        int response = MessageBox(nullptr, message.c_str(), L"Permission Request",
                                   MB_YESNOCANCEL | MB_ICONWARNING);

        WEBVIEW2_PERMISSION_STATE state =
              response == IDYES ? WEBVIEW2_PERMISSION_STATE_ALLOW
            : response == IDNO  ? WEBVIEW2_PERMISSION_STATE_DENY
            :                     WEBVIEW2_PERMISSION_STATE_DEFAULT;
        CHECK_FAILURE(args->put_State(state));

        return S_OK;
    }).Get(), &m_permissionRequestedToken));
```

#### <span data-ttu-id="d2c20-417">remove_PermissionRequested</span><span class="sxs-lookup"><span data-stu-id="d2c20-417">remove_PermissionRequested</span></span> 

<span data-ttu-id="d2c20-418">删除以前使用 add_PermissionRequested 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-418">Remove an event handler previously added with add_PermissionRequested.</span></span>

> <span data-ttu-id="d2c20-419">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-419">public HRESULT [remove_PermissionRequested](#remove_permissionrequested)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-420">add_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="d2c20-420">add_ProcessFailed</span></span> 

<span data-ttu-id="d2c20-421">为 ProcessFailed 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-421">Add an event handler for the ProcessFailed event.</span></span>

> <span data-ttu-id="d2c20-422">public HRESULT [add_ProcessFailed](#add_processfailed)（[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-422">public HRESULT [add_ProcessFailed](#add_processfailed)([IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) \* eventHandler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-423">当 Web 视图进程意外终止或停止响应时激发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-423">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

```cpp
    // Register a handler for the ProcessFailed event.
    // This handler checks if the browser process failed, and asks the user if
    // they want to recreate the webview.
    CHECK_FAILURE(m_webView->add_ProcessFailed(
        Callback<IWebView2ProcessFailedEventHandler>(
            [this](IWebView2WebView* sender,
                IWebView2ProcessFailedEventArgs* args) -> HRESULT
    {
        WEBVIEW2_PROCESS_FAILED_KIND failureType;
        CHECK_FAILURE(args->get_ProcessFailedKind(&failureType));
        if (failureType == WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED)
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
        return S_OK;
    }).Get(), &m_processFailedToken));
```

#### <span data-ttu-id="d2c20-424">remove_ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="d2c20-424">remove_ProcessFailed</span></span> 

<span data-ttu-id="d2c20-425">删除以前使用 add_ProcessFailed 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-425">Remove an event handler previously added with add_ProcessFailed.</span></span>

> <span data-ttu-id="d2c20-426">public HRESULT [remove_ProcessFailed](#remove_processfailed)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-426">public HRESULT [remove_ProcessFailed](#remove_processfailed)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-427">AddScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="d2c20-427">AddScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="d2c20-428">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="d2c20-428">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="d2c20-429">公共 HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)（LPCWSTR JavaScript，[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="d2c20-429">public HRESULT [AddScriptToExecuteOnDocumentCreated](#addscripttoexecuteondocumentcreated)(LPCWSTR javaScript,[IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler](IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="d2c20-430">插入的脚本将应用于所有未来的顶级文档和子框架导航，直到使用 RemoveScriptToExecuteOnDocumentCreated 删除。</span><span class="sxs-lookup"><span data-stu-id="d2c20-430">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="d2c20-431">这是异步应用的，你必须等待完成处理程序运行，然后才能确保脚本已准备好在将来的导航上执行。</span><span class="sxs-lookup"><span data-stu-id="d2c20-431">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="d2c20-432">请注意，如果 HTML 文档通过[沙盒](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)属性或[内容安全策略 HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)进行了某种类型的沙盒，则会影响在此处运行脚本。</span><span class="sxs-lookup"><span data-stu-id="d2c20-432">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="d2c20-433">例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-433">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

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
            Callback<IWebView2AddScriptToExecuteOnDocumentCreatedCompletedHandler>(
                [this](HRESULT error, PCWSTR id) -> HRESULT
        {
            m_lastInitializeScriptId = id;
            MessageBox(nullptr, id, L"AddScriptToExecuteOnDocumentCreated Id", MB_OK);
            return S_OK;
        }).Get());

    }
}
```

#### <span data-ttu-id="d2c20-434">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="d2c20-434">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="d2c20-435">删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="d2c20-435">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="d2c20-436">公共 HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)（LPCWSTR id）</span><span class="sxs-lookup"><span data-stu-id="d2c20-436">public HRESULT [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(LPCWSTR id)</span></span>

#### <span data-ttu-id="d2c20-437">ExecuteScript</span><span class="sxs-lookup"><span data-stu-id="d2c20-437">ExecuteScript</span></span> 

<span data-ttu-id="d2c20-438">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="d2c20-438">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="d2c20-439">公共 HRESULT [ExecuteScript](#executescript)（LPCWSTR JavaScript，[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="d2c20-439">public HRESULT [ExecuteScript](#executescript)(LPCWSTR javaScript,[IWebView2ExecuteScriptCompletedHandler](IWebView2ExecuteScriptCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="d2c20-440">这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="d2c20-440">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="d2c20-441">结果值是一个 JSON 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2c20-441">The result value is a JSON encoded string.</span></span> <span data-ttu-id="d2c20-442">如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。</span><span class="sxs-lookup"><span data-stu-id="d2c20-442">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="d2c20-443">请注意，没有显式返回值的函数将返回 undefined。</span><span class="sxs-lookup"><span data-stu-id="d2c20-443">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="d2c20-444">如果执行的脚本引发了未处理的异常，则结果也为 "null"。</span><span class="sxs-lookup"><span data-stu-id="d2c20-444">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="d2c20-445">此方法是异步应用的。</span><span class="sxs-lookup"><span data-stu-id="d2c20-445">This method is applied asynchronously.</span></span> <span data-ttu-id="d2c20-446">如果在 web 视图位于一个文档上时进行调用，并且在执行该调用之后但在执行 JavaScript 之前发生导航，则不会执行该脚本，并且将使用 E_FAIL 的 errorCode 参数调用该处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-446">If the call is made while the webview is on one document, and a navigation occurs after the call is made but before the JavaScript is executed, then the script will not be executed and the handler will be called with E_FAIL for its errorCode parameter.</span></span> <span data-ttu-id="d2c20-447">即使 IsScriptEnabled 设置为 FALSE，ExecuteScript 仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="d2c20-447">ExecuteScript will work even if IsScriptEnabled is set to FALSE.</span></span>

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
            Callback<IWebView2ExecuteScriptCompletedHandler>(
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

#### <span data-ttu-id="d2c20-448">CapturePreview</span><span class="sxs-lookup"><span data-stu-id="d2c20-448">CapturePreview</span></span> 

<span data-ttu-id="d2c20-449">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="d2c20-449">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="d2c20-450">public HRESULT [CapturePreview](#capturepreview)（[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) ImageFormat、IStream \* imageStream、[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="d2c20-450">public HRESULT [CapturePreview](#capturepreview)([WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format) imageFormat,IStream \* imageStream,[IWebView2CapturePreviewCompletedHandler](IWebView2CapturePreviewCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="d2c20-451">指定具有 imageFormat 参数的图像的格式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-451">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="d2c20-452">生成的图像二进制数据将写入所提供的 imageStream 参数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-452">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="d2c20-453">当 CapturePreview 完成写入流时，将调用所提供的处理程序参数上的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="d2c20-453">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

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
            WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG, stream.get(),
            Callback<IWebView2CapturePreviewCompletedHandler>(
                [mainWindow](HRESULT error_code) -> HRESULT {
                    CHECK_FAILURE(error_code);

                    MessageBox(mainWindow, L"Preview Captured", L"Preview Captured", MB_OK);
                    return S_OK;
                })
                .Get()));
    }
}
```

#### <span data-ttu-id="d2c20-454">重载</span><span class="sxs-lookup"><span data-stu-id="d2c20-454">Reload</span></span> 

<span data-ttu-id="d2c20-455">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="d2c20-455">Reload the current page.</span></span>

> <span data-ttu-id="d2c20-456">公共 HRESULT[重装](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="d2c20-456">public HRESULT [Reload](#reload)()</span></span>

<span data-ttu-id="d2c20-457">这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-457">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="d2c20-458">但是，将不会修改后退/前进历史记录。</span><span class="sxs-lookup"><span data-stu-id="d2c20-458">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="d2c20-459">get_Bounds</span><span class="sxs-lookup"><span data-stu-id="d2c20-459">get_Bounds</span></span> 

<span data-ttu-id="d2c20-460">Web 视图边界。</span><span class="sxs-lookup"><span data-stu-id="d2c20-460">The webview bounds.</span></span>

> <span data-ttu-id="d2c20-461">public HRESULT [get_Bounds](#get_bounds)（RECT \* 界限）</span><span class="sxs-lookup"><span data-stu-id="d2c20-461">public HRESULT [get_Bounds](#get_bounds)(RECT \* bounds)</span></span>

<span data-ttu-id="d2c20-462">界限相对于父 HWND。</span><span class="sxs-lookup"><span data-stu-id="d2c20-462">Bounds are relative to the parent HWND.</span></span> <span data-ttu-id="d2c20-463">应用有两种方法可以放置 Web 视图：</span><span class="sxs-lookup"><span data-stu-id="d2c20-463">The app has two ways it can position a WebView:</span></span>

1. <span data-ttu-id="d2c20-464">创建作为 Web 视图父 HWND 的子 HWND。</span><span class="sxs-lookup"><span data-stu-id="d2c20-464">Create a child HWND that is the WebView parent HWND.</span></span> <span data-ttu-id="d2c20-465">将此窗口放置在 Web 视图应位于的位置。</span><span class="sxs-lookup"><span data-stu-id="d2c20-465">Position this window where the WebView should be.</span></span> <span data-ttu-id="d2c20-466">在这种情况下，对 Web 视图的 Bound's 左上角（偏移）使用（0，0）。</span><span class="sxs-lookup"><span data-stu-id="d2c20-466">In this case, use (0, 0) for the WebView's Bound's top left corner (the offset).</span></span>

1. <span data-ttu-id="d2c20-467">将应用最顶部的窗口用作 Web 视图父 HWND。</span><span class="sxs-lookup"><span data-stu-id="d2c20-467">Use the app's top most window as the WebView parent HWND.</span></span> <span data-ttu-id="d2c20-468">设置 Web 视图的 Bound's 左上角，以便 Web 视图正确地放置在应用中。</span><span class="sxs-lookup"><span data-stu-id="d2c20-468">Set the WebView's Bound's top left corner so that the WebView is positioned correctly in the app.</span></span> <span data-ttu-id="d2c20-469">绑定的值位于主机的坐标空间中。</span><span class="sxs-lookup"><span data-stu-id="d2c20-469">The Bound's values are in the host's coordinate space.</span></span>

#### <span data-ttu-id="d2c20-470">put_Bounds</span><span class="sxs-lookup"><span data-stu-id="d2c20-470">put_Bounds</span></span> 

<span data-ttu-id="d2c20-471">设置界限属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-471">Set the Bounds property.</span></span>

> <span data-ttu-id="d2c20-472">public HRESULT [put_Bounds](#put_bounds)（RECT 界限）</span><span class="sxs-lookup"><span data-stu-id="d2c20-472">public HRESULT [put_Bounds](#put_bounds)(RECT bounds)</span></span>

```cpp
// Update the bounds of the WebView window to fit available space.
void ViewComponent::ResizeWebView()
{
    RECT desiredBounds = m_webViewBounds;
    desiredBounds.bottom = LONG(
        (m_webViewBounds.bottom - m_webViewBounds.top) * m_webViewRatio + m_webViewBounds.top);
    desiredBounds.right = LONG(
        (m_webViewBounds.right - m_webViewBounds.left) * m_webViewRatio + m_webViewBounds.left);

    m_webView->put_Bounds(desiredBounds);
}
```

#### <span data-ttu-id="d2c20-473">get_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="d2c20-473">get_ZoomFactor</span></span> 

<span data-ttu-id="d2c20-474">Web 视图中当前页面的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-474">The zoom factor for the current page in the WebView.</span></span>

> <span data-ttu-id="d2c20-475">公共 HRESULT [get_ZoomFactor](#get_zoomfactor)（Double \* ZoomFactor）</span><span class="sxs-lookup"><span data-stu-id="d2c20-475">public HRESULT [get_ZoomFactor](#get_zoomfactor)(double \* zoomFactor)</span></span>

<span data-ttu-id="d2c20-476">缩放系数按网站保持。</span><span class="sxs-lookup"><span data-stu-id="d2c20-476">The zoom factor is persisted per site.</span></span> <span data-ttu-id="d2c20-477">请注意，更改缩放系数可能会导致 `window.innerWidth/innerHeight` 页面布局和页面布局的更改。</span><span class="sxs-lookup"><span data-stu-id="d2c20-477">Note that changing zoom factor could cause `window.innerWidth/innerHeight` and page layout to change.</span></span> <span data-ttu-id="d2c20-478">当 Web 视图导航到来自不同网站的页面时，将不会应用上一页面的缩放系数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-478">When WebView navigates to a page from a different site, the zoom factor set for the previous page will not be applied.</span></span> <span data-ttu-id="d2c20-479">如果应用要设置特定页面的缩放系数，则执行该操作的最早位置是在 DocumentStateChanged 事件处理程序中。</span><span class="sxs-lookup"><span data-stu-id="d2c20-479">If the app wants to set the zoom factor for a certain page, the earliest place to do it is in the DocumentStateChanged event handler.</span></span> <span data-ttu-id="d2c20-480">请注意，如果它执行此操作，则在针对指定的缩放系数接收 ZoomFactorChanged 事件之前，它可能会收到持续缩放系数的 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-480">Note that if it does that, it might receive a ZoomFactorChanged event for the persisted zoom factor before receiving the ZoomFactorChanged event for the specified zoom factor.</span></span> <span data-ttu-id="d2c20-481">不允许指定小于或等于0的 zoomFactor。</span><span class="sxs-lookup"><span data-stu-id="d2c20-481">Specifying a zoomFactor less than or equal to 0 is not allowed.</span></span> <span data-ttu-id="d2c20-482">Web 视图也具有内部受支持的缩放系数范围。</span><span class="sxs-lookup"><span data-stu-id="d2c20-482">WebView also has an internal supported zoom factor range.</span></span> <span data-ttu-id="d2c20-483">当指定的缩放系数超出该范围时，它将规范化为在范围内，并且将针对应用的已应用的缩放系数引发 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-483">When a specified zoom factor is out of that range, it will be normalized to be within the range, and a ZoomFactorChanged event will be fired for the real applied zoom factor.</span></span> <span data-ttu-id="d2c20-484">当此范围规范化发生时，ZoomFactor 属性将报告在 ZoomFactor 属性的以前修改期间指定的缩放系数，直到在 web 视图应用标准化的缩放系数后收到 ZoomFactorChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-484">When this range normalization happens, the ZoomFactor property will report the zoom factor specified during the previous modification of the ZoomFactor property until the ZoomFactorChanged event is received after webview applies the normalized zoom factor.</span></span>

#### <span data-ttu-id="d2c20-485">put_ZoomFactor</span><span class="sxs-lookup"><span data-stu-id="d2c20-485">put_ZoomFactor</span></span> 

<span data-ttu-id="d2c20-486">设置 ZoomFactor 属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-486">Set the ZoomFactor property.</span></span>

> <span data-ttu-id="d2c20-487">公共 HRESULT [put_ZoomFactor](#put_zoomfactor)（double ZoomFactor）</span><span class="sxs-lookup"><span data-stu-id="d2c20-487">public HRESULT [put_ZoomFactor](#put_zoomfactor)(double zoomFactor)</span></span>

#### <span data-ttu-id="d2c20-488">get_IsVisible</span><span class="sxs-lookup"><span data-stu-id="d2c20-488">get_IsVisible</span></span> 

<span data-ttu-id="d2c20-489">IsVisible 属性确定是显示还是隐藏 web 视图。</span><span class="sxs-lookup"><span data-stu-id="d2c20-489">The IsVisible property determines whether to show or hide the webview.</span></span>

> <span data-ttu-id="d2c20-490">public HRESULT [get_IsVisible](#get_isvisible)（BOOL \* IsVisible）</span><span class="sxs-lookup"><span data-stu-id="d2c20-490">public HRESULT [get_IsVisible](#get_isvisible)(BOOL \* isVisible)</span></span>

<span data-ttu-id="d2c20-491">如果 IsVisible 设置为 false，则 web 视图将是透明的，不会呈现。</span><span class="sxs-lookup"><span data-stu-id="d2c20-491">If IsVisible is set to false, the webview will be transparent and will not be rendered.</span></span> <span data-ttu-id="d2c20-492">但是，这不会影响包含 web 视图的窗口（传递到 CreateWebView 的 HWND 参数）。</span><span class="sxs-lookup"><span data-stu-id="d2c20-492">However, this will not affect the window containing the webview (the HWND parameter that was passed to CreateWebView).</span></span> <span data-ttu-id="d2c20-493">如果你希望该窗口也消失，除了修改 IsVisible 属性外，还可直接对其调用 ShowWindow。</span><span class="sxs-lookup"><span data-stu-id="d2c20-493">If you want that window to disappear too, call ShowWindow on it directly in addition to modifying the IsVisible property.</span></span> <span data-ttu-id="d2c20-494">在最小化或还原顶级窗口时，Web 视图作为子窗口不会收到窗口消息。</span><span class="sxs-lookup"><span data-stu-id="d2c20-494">WebView as a child window won't get window messages when the top window is minimized or restored.</span></span> <span data-ttu-id="d2c20-495">出于性能原因，开发人员应在应用窗口最小化时将 Web 视图的 IsVisible 属性设置为 false，并在还原应用窗口时将其设置为 false。</span><span class="sxs-lookup"><span data-stu-id="d2c20-495">For performance reason, developer should set IsVisible property of the WebView to false when the app window is minimized and back to true when app window is restored.</span></span> <span data-ttu-id="d2c20-496">应用窗口可通过在接收 WM_SYSCOMMAND 消息时处理 SC_MINIMIZE 和 SC_RESTORE 命令来执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d2c20-496">App window can do this by handling SC_MINIMIZE and SC_RESTORE command upon receiving WM_SYSCOMMAND message.</span></span>

```cpp
void ViewComponent::ToggleVisibility()
{
    BOOL visible;
    m_webView->get_IsVisible(&visible);
    m_isVisible = !visible;
    m_webView->put_IsVisible(m_isVisible);
}
```

#### <span data-ttu-id="d2c20-497">put_IsVisible</span><span class="sxs-lookup"><span data-stu-id="d2c20-497">put_IsVisible</span></span> 

<span data-ttu-id="d2c20-498">设置 IsVisible 属性。</span><span class="sxs-lookup"><span data-stu-id="d2c20-498">Set the IsVisible property.</span></span>

> <span data-ttu-id="d2c20-499">公共 HRESULT [put_IsVisible](#put_isvisible)（布尔值 IsVisible）</span><span class="sxs-lookup"><span data-stu-id="d2c20-499">public HRESULT [put_IsVisible](#put_isvisible)(BOOL isVisible)</span></span>

```cpp
    if (message == WM_SYSCOMMAND)
    {
        if (wParam == SC_MINIMIZE)
        {
            // Hide the webview when the app window is minimized.
            m_webView->put_IsVisible(FALSE);
        }
        else if (wParam == SC_RESTORE)
        {
            // When the app window is restored, show the webview
            // (unless the user has toggle visibility off).
            if (m_isVisible)
            {
                m_webView->put_IsVisible(TRUE);
            }
        }
    }
```

#### <span data-ttu-id="d2c20-500">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="d2c20-500">PostWebMessageAsJson</span></span> 

<span data-ttu-id="d2c20-501">将指定的 webMessage 发布到此[IWebView2WebView]()中的最高级别文档。</span><span class="sxs-lookup"><span data-stu-id="d2c20-501">Post the specified webMessage to the top level document in this [IWebView2WebView]().</span></span>

> <span data-ttu-id="d2c20-502">公共 HRESULT [PostWebMessageAsJson](#postwebmessageasjson)（LPCWSTR webMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="d2c20-502">public HRESULT [PostWebMessageAsJson](#postwebmessageasjson)(LPCWSTR webMessageAsJson)</span></span>

<span data-ttu-id="d2c20-503">将激发顶级文档的 "chrome" 消息事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-503">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="d2c20-504">该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件：</span><span class="sxs-lookup"><span data-stu-id="d2c20-504">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span> 

```cpp
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

 <span data-ttu-id="d2c20-505">事件参数是的实例 `MessageEvent` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-505">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="d2c20-506">IWebView2Settings：： IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并显示 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="d2c20-506">The IWebView2Settings::IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="d2c20-507">事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-507">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="d2c20-508">事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-508">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="d2c20-509">有关从 web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 SetWebMessageReceivedEventHandler。</span><span class="sxs-lookup"><span data-stu-id="d2c20-509">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="d2c20-510">此消息将异步发送。</span><span class="sxs-lookup"><span data-stu-id="d2c20-510">This message is sent asynchronously.</span></span> <span data-ttu-id="d2c20-511">如果在将邮件发布到页面之前发生导航，则不会发送邮件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-511">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
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

#### <span data-ttu-id="d2c20-512">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="d2c20-512">PostWebMessageAsString</span></span> 

<span data-ttu-id="d2c20-513">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-513">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="d2c20-514">公共 HRESULT [PostWebMessageAsString](#postwebmessageasstring)（LPCWSTR webMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="d2c20-514">public HRESULT [PostWebMessageAsString](#postwebmessageasstring)(LPCWSTR webMessageAsString)</span></span>

<span data-ttu-id="d2c20-515">此行为与 PostWebMessageAsJson 完全相同，但 `window.chrome.webview` 消息事件参数的 data 属性将是与 webMessageAsString 具有相同值的字符串。</span><span class="sxs-lookup"><span data-stu-id="d2c20-515">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="d2c20-516">如果想要通过简单的字符串而不是 JSON 对象进行通信，请使用此操作，而不是 PostWebMessageAsJson。</span><span class="sxs-lookup"><span data-stu-id="d2c20-516">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="d2c20-517">add_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-517">add_WebMessageReceived</span></span> 

<span data-ttu-id="d2c20-518">当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-518">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="d2c20-519">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)（[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* 处理程序，EventRegistrationToken \* token）</span><span class="sxs-lookup"><span data-stu-id="d2c20-519">public HRESULT [add_WebMessageReceived](#add_webmessagereceived)([IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-520">PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。</span><span class="sxs-lookup"><span data-stu-id="d2c20-520">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span>

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

 <span data-ttu-id="d2c20-521">调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 的对象参数调用通过此 SetWebMessageReceivedEventHandler 方法设置的[IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-521">When postMessage is called, the [IWebView2WebMessageReceivedEventHandler](IWebView2WebMessageReceivedEventHandler.md) set via this SetWebMessageReceivedEventHandler method will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

```cpp
    // Setup the web message received event handler before navigating to
    // ensure we don't miss any messages.
    CHECK_FAILURE(m_webView->add_WebMessageReceived(
        Microsoft::WRL::Callback<IWebView2WebMessageReceivedEventHandler>(
            [this](IWebView2WebView* sender, IWebView2WebMessageReceivedEventArgs* args)
    {
        wil::unique_cotaskmem_string uri;
        CHECK_FAILURE(args->get_Source(&uri));

        // Always validate that the origin of the message is what you expect.
        if (uri.get() != m_sampleUri)
        {
            return S_OK;
        }
        wil::unique_cotaskmem_string messageRaw;
        CHECK_FAILURE(args->get_WebMessageAsString(&messageRaw));
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

#### <span data-ttu-id="d2c20-522">remove_WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-522">remove_WebMessageReceived</span></span> 

<span data-ttu-id="d2c20-523">删除以前使用 add_WebMessageReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-523">Remove an event handler previously added with add_WebMessageReceived.</span></span>

> <span data-ttu-id="d2c20-524">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)（EventRegistrationToken 标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-524">public HRESULT [remove_WebMessageReceived](#remove_webmessagereceived)(EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-525">关闭</span><span class="sxs-lookup"><span data-stu-id="d2c20-525">Close</span></span> 

<span data-ttu-id="d2c20-526">关闭 web 视图并清理基础浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="d2c20-526">Closes the webview and cleans up the underlying browser instance.</span></span>

> <span data-ttu-id="d2c20-527">公共 HRESULT [Close](#close)（）</span><span class="sxs-lookup"><span data-stu-id="d2c20-527">public HRESULT [Close](#close)()</span></span>

<span data-ttu-id="d2c20-528">清理浏览器 instace 将释放为 web 视图供电的资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-528">Cleaning up the browser instace will release the resources powering the webview.</span></span> <span data-ttu-id="d2c20-529">如果没有其他 webviews 使用浏览器实例，则将关闭该浏览器实例。</span><span class="sxs-lookup"><span data-stu-id="d2c20-529">The browser instance will be shut down if there are no other webviews using it.</span></span>

<span data-ttu-id="d2c20-530">调用 Close 后，所有方法调用都将失败，事件处理程序将停止触发。</span><span class="sxs-lookup"><span data-stu-id="d2c20-530">After calling Close, all method calls will fail and event handlers will stop firing.</span></span> <span data-ttu-id="d2c20-531">具体说来，当调用 Close 时，Web 视图将释放其对其事件处理程序的引用。</span><span class="sxs-lookup"><span data-stu-id="d2c20-531">Specifically, the WebView will release its references to its event handlers when Close is called.</span></span>

<span data-ttu-id="d2c20-532">当 Web 视图失去其最终引用且为 destructed 时，将隐式调用 Close。</span><span class="sxs-lookup"><span data-stu-id="d2c20-532">Close is implicitly called when the WebView loses its final reference and is destructed.</span></span> <span data-ttu-id="d2c20-533">但最佳做法是显式调用 Close 以避免 Web 视图和应用代码之间任何意外的引用循环。</span><span class="sxs-lookup"><span data-stu-id="d2c20-533">But it is best practice to explicitly call Close to avoid any accidental cycle of references between the WebView and the app code.</span></span> <span data-ttu-id="d2c20-534">尤其是，如果你在事件处理程序中捕获对 Web 视图的引用，你将在 Web 视图和事件处理程序之间创建引用循环。</span><span class="sxs-lookup"><span data-stu-id="d2c20-534">Specifically, if you capture a reference to the WebView in an event handler you will create a reference cycle between the WebView and the event handler.</span></span> <span data-ttu-id="d2c20-535">关闭将通过释放所有事件处理程序来中断此循环。</span><span class="sxs-lookup"><span data-stu-id="d2c20-535">Close will break this cycle by releasing all event handlers.</span></span> <span data-ttu-id="d2c20-536">但是，为了避免这种情况，最佳做法是在 Web 视图上显式调用 Close，而不捕获对 Web 视图的引用，以确保可正确清理 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="d2c20-536">But to avoid this situation it is best practice to both explicitly call Close on the WebView and to not capture a reference to the WebView to ensure the WebView can be cleaned up correctly.</span></span>

```cpp
// Close the WebView and deinitialize related state. This doesn't close the app window.
void AppWindow::CloseWebView()
{
    DeleteAllComponents();
    if (m_webView)
    {
        m_webView->Close();
        m_webView = nullptr;
    }
    m_webViewEnvironment = nullptr;
}
```

#### <span data-ttu-id="d2c20-537">CallDevToolsProtocolMethod</span><span class="sxs-lookup"><span data-stu-id="d2c20-537">CallDevToolsProtocolMethod</span></span> 

<span data-ttu-id="d2c20-538">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="d2c20-538">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="d2c20-539">公共 HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)（LPCWSTR 方法，LPCWSTR ParametersAsJson，[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* 处理程序）</span><span class="sxs-lookup"><span data-stu-id="d2c20-539">public HRESULT [CallDevToolsProtocolMethod](#calldevtoolsprotocolmethod)(LPCWSTR methodName,LPCWSTR parametersAsJson,[IWebView2CallDevToolsProtocolMethodCompletedHandler](IWebView2CallDevToolsProtocolMethodCompletedHandler.md) \* handler)</span></span>

<span data-ttu-id="d2c20-540">有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。</span><span class="sxs-lookup"><span data-stu-id="d2c20-540">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="d2c20-541">"方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-541">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="d2c20-542">ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-542">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="d2c20-543">当方法异步完成时，将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="d2c20-543">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="d2c20-544">将使用方法的返回对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="d2c20-544">Invoke will be called with the method's return object as a JSON string.</span></span>

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
            Callback<IWebView2CallDevToolsProtocolMethodCompletedHandler>(
                [](HRESULT error, PCWSTR resultJson) -> HRESULT
                {
                    MessageBox(nullptr, resultJson, L"CDP Method Result", MB_OK);
                    return S_OK;
                }).Get());
    }
}
```

#### <span data-ttu-id="d2c20-545">add_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-545">add_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="d2c20-546">订阅 DevToolsProtocol 事件。</span><span class="sxs-lookup"><span data-stu-id="d2c20-546">Subscribe to a DevToolsProtocol event.</span></span>

> <span data-ttu-id="d2c20-547">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)（LPCWSTR 事件，[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* 处理程序，EventRegistrationToken \* 令牌）</span><span class="sxs-lookup"><span data-stu-id="d2c20-547">public HRESULT [add_DevToolsProtocolEventReceived](#add_devtoolsprotocoleventreceived)(LPCWSTR eventName,[IWebView2DevToolsProtocolEventReceivedEventHandler](IWebView2DevToolsProtocolEventReceivedEventHandler.md) \* handler,EventRegistrationToken \* token)</span></span>

<span data-ttu-id="d2c20-548">有关可用事件的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。</span><span class="sxs-lookup"><span data-stu-id="d2c20-548">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available events.</span></span> <span data-ttu-id="d2c20-549">事件名称参数是该事件的格式的完整名称 `{domain}.{event}` 。</span><span class="sxs-lookup"><span data-stu-id="d2c20-549">The eventName parameter is the full name of the event in the format `{domain}.{event}`.</span></span> <span data-ttu-id="d2c20-550">每当引发相应的 DevToolsProtocol 事件时，都将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="d2c20-550">The handler's Invoke method will be called whenever the corresponding DevToolsProtocol event fires.</span></span> <span data-ttu-id="d2c20-551">将使用包含 CDP 事件的参数对象的事件参数对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="d2c20-551">Invoke will be called with the an event args object containing the CDP event's parameter object as a JSON string.</span></span>

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
        // If we are already subscribed to this event, unsubscribe first.
        auto preexistingToken = m_devToolsProtocolEventReceivedTokenMap.find(eventName);
        if (preexistingToken != m_devToolsProtocolEventReceivedTokenMap.end())
        {
            CHECK_FAILURE(m_webView->remove_DevToolsProtocolEventReceived(
                eventName.c_str(),
                preexistingToken->second));
        }

        CHECK_FAILURE(m_webView->add_DevToolsProtocolEventReceived(
            eventName.c_str(),
            Callback<IWebView2DevToolsProtocolEventReceivedEventHandler>(
                [eventName](IWebView2WebView* sender,
                            IWebView2DevToolsProtocolEventReceivedEventArgs* args)
                -> HRESULT
        {
            wil::unique_cotaskmem_string parameterObjectAsJson;
            CHECK_FAILURE(args->get_ParameterObjectAsJson(&parameterObjectAsJson));
            MessageBox(nullptr, parameterObjectAsJson.get(),
                       (L"CDP Event Fired: " + eventName).c_str(), MB_OK);
            return S_OK;
        }).Get(), &m_devToolsProtocolEventReceivedTokenMap[eventName]));
    }
}
```

#### <span data-ttu-id="d2c20-552">remove_DevToolsProtocolEventReceived</span><span class="sxs-lookup"><span data-stu-id="d2c20-552">remove_DevToolsProtocolEventReceived</span></span> 

<span data-ttu-id="d2c20-553">删除以前使用 add_DevToolsProtocolEventReceived 添加的事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="d2c20-553">Remove an event handler previously added with add_DevToolsProtocolEventReceived.</span></span>

> <span data-ttu-id="d2c20-554">公共 HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)（LPCWSTR EventRegistrationToken、标记）</span><span class="sxs-lookup"><span data-stu-id="d2c20-554">public HRESULT [remove_DevToolsProtocolEventReceived](#remove_devtoolsprotocoleventreceived)(LPCWSTR eventName,EventRegistrationToken token)</span></span>

#### <span data-ttu-id="d2c20-555">get_BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="d2c20-555">get_BrowserProcessId</span></span> 

<span data-ttu-id="d2c20-556">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="d2c20-556">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="d2c20-557">公共 HRESULT [get_BrowserProcessId](#get_browserprocessid)（UINT32 \* 值）</span><span class="sxs-lookup"><span data-stu-id="d2c20-557">public HRESULT [get_BrowserProcessId](#get_browserprocessid)(UINT32 \* value)</span></span>

#### <span data-ttu-id="d2c20-558">get_CanGoBack</span><span class="sxs-lookup"><span data-stu-id="d2c20-558">get_CanGoBack</span></span> 

<span data-ttu-id="d2c20-559">可将 web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-559">Can navigate the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="d2c20-560">public HRESULT [get_CanGoBack](#get_cangoback)（BOOL \* CanGoBack）</span><span class="sxs-lookup"><span data-stu-id="d2c20-560">public HRESULT [get_CanGoBack](#get_cangoback)(BOOL \* canGoBack)</span></span>

<span data-ttu-id="d2c20-561">get_CanGoBack DocumentStateChanged 事件更改值。</span><span class="sxs-lookup"><span data-stu-id="d2c20-561">get_CanGoBack change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="d2c20-562">get_CanGoForward</span><span class="sxs-lookup"><span data-stu-id="d2c20-562">get_CanGoForward</span></span> 

<span data-ttu-id="d2c20-563">可将 web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-563">Can navigate the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="d2c20-564">public HRESULT [get_CanGoForward](#get_cangoforward)（BOOL \* CanGoForward）</span><span class="sxs-lookup"><span data-stu-id="d2c20-564">public HRESULT [get_CanGoForward](#get_cangoforward)(BOOL \* canGoForward)</span></span>

<span data-ttu-id="d2c20-565">get_CanGoForward DocumentStateChanged 事件更改值。</span><span class="sxs-lookup"><span data-stu-id="d2c20-565">get_CanGoForward change value with the DocumentStateChanged event.</span></span>

#### <span data-ttu-id="d2c20-566">GoBack</span><span class="sxs-lookup"><span data-stu-id="d2c20-566">GoBack</span></span> 

<span data-ttu-id="d2c20-567">将 web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-567">Navigates the webview to the previous page in the navigation history.</span></span>

> <span data-ttu-id="d2c20-568">公共 HRESULT [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="d2c20-568">public HRESULT [GoBack](#goback)()</span></span>

#### <span data-ttu-id="d2c20-569">GoForward</span><span class="sxs-lookup"><span data-stu-id="d2c20-569">GoForward</span></span> 

<span data-ttu-id="d2c20-570">将 web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="d2c20-570">Navigates the webview to the next page in the navigation history.</span></span>

> <span data-ttu-id="d2c20-571">公共 HRESULT [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="d2c20-571">public HRESULT [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="d2c20-572">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span><span class="sxs-lookup"><span data-stu-id="d2c20-572">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT</span></span> 

<span data-ttu-id="d2c20-573">[IWebView2WebView：： CapturePreview](#capturepreview)方法使用的图像格式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-573">Image format used by the [IWebView2WebView::CapturePreview](#capturepreview) method.</span></span>

> <span data-ttu-id="d2c20-574">枚举[WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span><span class="sxs-lookup"><span data-stu-id="d2c20-574">enum [WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT](#webview2_capture_preview_image_format)</span></span>

 <span data-ttu-id="d2c20-575">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-575">Values</span></span>                         | <span data-ttu-id="d2c20-576">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-576">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span><span class="sxs-lookup"><span data-stu-id="d2c20-577">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_PNG</span></span>            | <span data-ttu-id="d2c20-578">PNG 图像格式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-578">PNG image format.</span></span>
<span data-ttu-id="d2c20-579">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span><span class="sxs-lookup"><span data-stu-id="d2c20-579">WEBVIEW2_CAPTURE_PREVIEW_IMAGE_FORMAT_JPEG</span></span>            | <span data-ttu-id="d2c20-580">JPEG 图像格式。</span><span class="sxs-lookup"><span data-stu-id="d2c20-580">JPEG image format.</span></span>

#### <span data-ttu-id="d2c20-581">WEBVIEW2_SCRIPT_DIALOG_KIND</span><span class="sxs-lookup"><span data-stu-id="d2c20-581">WEBVIEW2_SCRIPT_DIALOG_KIND</span></span> 

<span data-ttu-id="d2c20-582">[IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md)接口中使用的 JavaScript 对话框类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-582">Kind of JavaScript dialog used in the [IWebView2ScriptDialogOpeningEventHandler](IWebView2ScriptDialogOpeningEventHandler.md) interface.</span></span>

> <span data-ttu-id="d2c20-583">枚举[WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span><span class="sxs-lookup"><span data-stu-id="d2c20-583">enum [WEBVIEW2_SCRIPT_DIALOG_KIND](#webview2_script_dialog_kind)</span></span>

 <span data-ttu-id="d2c20-584">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-584">Values</span></span>                         | <span data-ttu-id="d2c20-585">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-585">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-586">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span><span class="sxs-lookup"><span data-stu-id="d2c20-586">WEBVIEW2_SCRIPT_DIALOG_KIND_ALERT</span></span>            | <span data-ttu-id="d2c20-587">通过窗口调用的对话框。警报 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-587">A dialog invoked via the window.alert JavaScript function.</span></span>
<span data-ttu-id="d2c20-588">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span><span class="sxs-lookup"><span data-stu-id="d2c20-588">WEBVIEW2_SCRIPT_DIALOG_KIND_CONFIRM</span></span>            | <span data-ttu-id="d2c20-589">通过窗口调用的对话框。确认 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-589">A dialog invoked via the window.confirm JavaScript function.</span></span>
<span data-ttu-id="d2c20-590">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span><span class="sxs-lookup"><span data-stu-id="d2c20-590">WEBVIEW2_SCRIPT_DIALOG_KIND_PROMPT</span></span>            | <span data-ttu-id="d2c20-591">通过窗口调用的对话框。提示 JavaScript 函数。</span><span class="sxs-lookup"><span data-stu-id="d2c20-591">A dialog invoked via the window.prompt JavaScript function.</span></span>

#### <span data-ttu-id="d2c20-592">WEBVIEW2_PROCESS_FAILED_KIND</span><span class="sxs-lookup"><span data-stu-id="d2c20-592">WEBVIEW2_PROCESS_FAILED_KIND</span></span> 

<span data-ttu-id="d2c20-593">[IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md)接口中使用的进程失败类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-593">Kind of process failure used in the [IWebView2ProcessFailedEventHandler](IWebView2ProcessFailedEventHandler.md) interface.</span></span>

> <span data-ttu-id="d2c20-594">枚举[WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span><span class="sxs-lookup"><span data-stu-id="d2c20-594">enum [WEBVIEW2_PROCESS_FAILED_KIND](#webview2_process_failed_kind)</span></span>

 <span data-ttu-id="d2c20-595">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-595">Values</span></span>                         | <span data-ttu-id="d2c20-596">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-596">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-597">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="d2c20-597">WEBVIEW2_PROCESS_FAILED_KIND_BROWSER_PROCESS_EXITED</span></span>            | <span data-ttu-id="d2c20-598">指示浏览器进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="d2c20-598">Indicates the browser process terminated unexpectedly.</span></span>
<span data-ttu-id="d2c20-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span><span class="sxs-lookup"><span data-stu-id="d2c20-599">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_EXITED</span></span>            | <span data-ttu-id="d2c20-600">指示呈现进程意外终止。</span><span class="sxs-lookup"><span data-stu-id="d2c20-600">Indicates the render process terminated unexpectedly.</span></span>
<span data-ttu-id="d2c20-601">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span><span class="sxs-lookup"><span data-stu-id="d2c20-601">WEBVIEW2_PROCESS_FAILED_KIND_RENDER_PROCESS_UNRESPONSIVE</span></span>            | <span data-ttu-id="d2c20-602">指示呈现过程变得无响应。</span><span class="sxs-lookup"><span data-stu-id="d2c20-602">Indicates the render process becomes unresponsive.</span></span>

#### <span data-ttu-id="d2c20-603">WEBVIEW2_PERMISSION_TYPE</span><span class="sxs-lookup"><span data-stu-id="d2c20-603">WEBVIEW2_PERMISSION_TYPE</span></span> 

<span data-ttu-id="d2c20-604">权限请求的类型。</span><span class="sxs-lookup"><span data-stu-id="d2c20-604">The type of a permission request.</span></span>

> <span data-ttu-id="d2c20-605">枚举[WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span><span class="sxs-lookup"><span data-stu-id="d2c20-605">enum [WEBVIEW2_PERMISSION_TYPE](#webview2_permission_type)</span></span>

 <span data-ttu-id="d2c20-606">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-606">Values</span></span>                         | <span data-ttu-id="d2c20-607">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-607">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-608">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span><span class="sxs-lookup"><span data-stu-id="d2c20-608">WEBVIEW2_PERMISSION_TYPE_UNKNOWN_PERMISSION</span></span>            | <span data-ttu-id="d2c20-609">未知权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-609">Unknown permission.</span></span>
<span data-ttu-id="d2c20-610">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span><span class="sxs-lookup"><span data-stu-id="d2c20-610">WEBVIEW2_PERMISSION_TYPE_MICROPHONE</span></span>            | <span data-ttu-id="d2c20-611">捕获音频的权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-611">Permission to capture audio.</span></span>
<span data-ttu-id="d2c20-612">WEBVIEW2_PERMISSION_TYPE_CAMERA</span><span class="sxs-lookup"><span data-stu-id="d2c20-612">WEBVIEW2_PERMISSION_TYPE_CAMERA</span></span>            | <span data-ttu-id="d2c20-613">捕获视频的权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-613">Permission to capture video.</span></span>
<span data-ttu-id="d2c20-614">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span><span class="sxs-lookup"><span data-stu-id="d2c20-614">WEBVIEW2_PERMISSION_TYPE_GEOLOCATION</span></span>            | <span data-ttu-id="d2c20-615">访问地理位置的权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-615">Permission to access geolocation.</span></span>
<span data-ttu-id="d2c20-616">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span><span class="sxs-lookup"><span data-stu-id="d2c20-616">WEBVIEW2_PERMISSION_TYPE_NOTIFICATIONS</span></span>            | <span data-ttu-id="d2c20-617">发送 web 通知的权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-617">Permission to send web notifications.</span></span>
<span data-ttu-id="d2c20-618">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span><span class="sxs-lookup"><span data-stu-id="d2c20-618">WEBVIEW2_PERMISSION_TYPE_OTHER_SENSORS</span></span>            | <span data-ttu-id="d2c20-619">访问通用传感器的权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-619">Permission to access generic sensor.</span></span>
<span data-ttu-id="d2c20-620">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span><span class="sxs-lookup"><span data-stu-id="d2c20-620">WEBVIEW2_PERMISSION_TYPE_CLIPBOARD_READ</span></span>            | <span data-ttu-id="d2c20-621">在没有用户手势的情况下读取系统剪贴板的权限。</span><span class="sxs-lookup"><span data-stu-id="d2c20-621">Permission to read system clipboard without a user gesture.</span></span>

#### <span data-ttu-id="d2c20-622">WEBVIEW2_PERMISSION_STATE</span><span class="sxs-lookup"><span data-stu-id="d2c20-622">WEBVIEW2_PERMISSION_STATE</span></span> 

<span data-ttu-id="d2c20-623">对权限请求的响应。</span><span class="sxs-lookup"><span data-stu-id="d2c20-623">Response to a permission request.</span></span>

> <span data-ttu-id="d2c20-624">枚举[WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span><span class="sxs-lookup"><span data-stu-id="d2c20-624">enum [WEBVIEW2_PERMISSION_STATE](#webview2_permission_state)</span></span>

 <span data-ttu-id="d2c20-625">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-625">Values</span></span>                         | <span data-ttu-id="d2c20-626">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-626">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-627">WEBVIEW2_PERMISSION_STATE_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="d2c20-627">WEBVIEW2_PERMISSION_STATE_DEFAULT</span></span>            | <span data-ttu-id="d2c20-628">使用默认的浏览器行为，这通常会提示用户做出决策。</span><span class="sxs-lookup"><span data-stu-id="d2c20-628">Use default browser behavior, which normally prompt users for decision.</span></span>
<span data-ttu-id="d2c20-629">WEBVIEW2_PERMISSION_STATE_ALLOW</span><span class="sxs-lookup"><span data-stu-id="d2c20-629">WEBVIEW2_PERMISSION_STATE_ALLOW</span></span>            | <span data-ttu-id="d2c20-630">授予权限请求。</span><span class="sxs-lookup"><span data-stu-id="d2c20-630">Grant the permission request.</span></span>
<span data-ttu-id="d2c20-631">WEBVIEW2_PERMISSION_STATE_DENY</span><span class="sxs-lookup"><span data-stu-id="d2c20-631">WEBVIEW2_PERMISSION_STATE_DENY</span></span>            | <span data-ttu-id="d2c20-632">拒绝权限请求。</span><span class="sxs-lookup"><span data-stu-id="d2c20-632">Deny the permission request.</span></span>

#### <span data-ttu-id="d2c20-633">WEBVIEW2_MOVE_FOCUS_REASON</span><span class="sxs-lookup"><span data-stu-id="d2c20-633">WEBVIEW2_MOVE_FOCUS_REASON</span></span> 

<span data-ttu-id="d2c20-634">移动焦点的原因。</span><span class="sxs-lookup"><span data-stu-id="d2c20-634">Reason for moving focus.</span></span>

> <span data-ttu-id="d2c20-635">枚举[WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span><span class="sxs-lookup"><span data-stu-id="d2c20-635">enum [WEBVIEW2_MOVE_FOCUS_REASON](#webview2_move_focus_reason)</span></span>

 <span data-ttu-id="d2c20-636">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-636">Values</span></span>                         | <span data-ttu-id="d2c20-637">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-637">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-638">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span><span class="sxs-lookup"><span data-stu-id="d2c20-638">WEBVIEW2_MOVE_FOCUS_REASON_PROGRAMMATIC</span></span>            | <span data-ttu-id="d2c20-639">将焦点放入 Web 视图中的代码。</span><span class="sxs-lookup"><span data-stu-id="d2c20-639">Code setting focus into WebView.</span></span>
<span data-ttu-id="d2c20-640">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span><span class="sxs-lookup"><span data-stu-id="d2c20-640">WEBVIEW2_MOVE_FOCUS_REASON_NEXT</span></span>            | <span data-ttu-id="d2c20-641">由于向前遍历 Tab 遍历，移动焦点。</span><span class="sxs-lookup"><span data-stu-id="d2c20-641">Moving focus due to Tab traversal forward.</span></span>
<span data-ttu-id="d2c20-642">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span><span class="sxs-lookup"><span data-stu-id="d2c20-642">WEBVIEW2_MOVE_FOCUS_REASON_PREVIOUS</span></span>            | <span data-ttu-id="d2c20-643">由于 Tab 向后移动焦点。</span><span class="sxs-lookup"><span data-stu-id="d2c20-643">Moving focus due to Tab traversal backward.</span></span>

#### <span data-ttu-id="d2c20-644">WEBVIEW2_WEB_ERROR_STATUS</span><span class="sxs-lookup"><span data-stu-id="d2c20-644">WEBVIEW2_WEB_ERROR_STATUS</span></span> 

<span data-ttu-id="d2c20-645">Web 导航的错误状态值。</span><span class="sxs-lookup"><span data-stu-id="d2c20-645">Error status values for web navigations.</span></span>

> <span data-ttu-id="d2c20-646">枚举[WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span><span class="sxs-lookup"><span data-stu-id="d2c20-646">enum [WEBVIEW2_WEB_ERROR_STATUS](#webview2_web_error_status)</span></span>

 <span data-ttu-id="d2c20-647">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-647">Values</span></span>                         | <span data-ttu-id="d2c20-648">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-648">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-649">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span><span class="sxs-lookup"><span data-stu-id="d2c20-649">WEBVIEW2_WEB_ERROR_STATUS_UNKNOWN</span></span>            | <span data-ttu-id="d2c20-650">出现未知错误。</span><span class="sxs-lookup"><span data-stu-id="d2c20-650">An unknown error occurred.</span></span>
<span data-ttu-id="d2c20-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span><span class="sxs-lookup"><span data-stu-id="d2c20-651">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_COMMON_NAME_IS_INCORRECT</span></span>            | <span data-ttu-id="d2c20-652">SSL 证书公用名与 web 地址不匹配。</span><span class="sxs-lookup"><span data-stu-id="d2c20-652">The SSL certificate common name does not match the web address.</span></span>
<span data-ttu-id="d2c20-653">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span><span class="sxs-lookup"><span data-stu-id="d2c20-653">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_EXPIRED</span></span>            | <span data-ttu-id="d2c20-654">SSL 证书已过期。</span><span class="sxs-lookup"><span data-stu-id="d2c20-654">The SSL certificate has expired.</span></span>
<span data-ttu-id="d2c20-655">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span><span class="sxs-lookup"><span data-stu-id="d2c20-655">WEBVIEW2_WEB_ERROR_STATUS_CLIENT_CERTIFICATE_CONTAINS_ERRORS</span></span>            | <span data-ttu-id="d2c20-656">SSL 客户端证书包含错误。</span><span class="sxs-lookup"><span data-stu-id="d2c20-656">The SSL client certificate contains errors.</span></span>
<span data-ttu-id="d2c20-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span><span class="sxs-lookup"><span data-stu-id="d2c20-657">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_REVOKED</span></span>            | <span data-ttu-id="d2c20-658">SSL 证书已被吊销。</span><span class="sxs-lookup"><span data-stu-id="d2c20-658">The SSL certificate has been revoked.</span></span>
<span data-ttu-id="d2c20-659">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span><span class="sxs-lookup"><span data-stu-id="d2c20-659">WEBVIEW2_WEB_ERROR_STATUS_CERTIFICATE_IS_INVALID</span></span>            | <span data-ttu-id="d2c20-660">SSL 证书无效。</span><span class="sxs-lookup"><span data-stu-id="d2c20-660">The SSL certificate is invalid.</span></span>
<span data-ttu-id="d2c20-661">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="d2c20-661">WEBVIEW2_WEB_ERROR_STATUS_SERVER_UNREACHABLE</span></span>            | <span data-ttu-id="d2c20-662">无法访问主机。</span><span class="sxs-lookup"><span data-stu-id="d2c20-662">The host is unreachable.</span></span>
<span data-ttu-id="d2c20-663">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span><span class="sxs-lookup"><span data-stu-id="d2c20-663">WEBVIEW2_WEB_ERROR_STATUS_TIMEOUT</span></span>            | <span data-ttu-id="d2c20-664">连接超时。</span><span class="sxs-lookup"><span data-stu-id="d2c20-664">The connection has timed out.</span></span>
<span data-ttu-id="d2c20-665">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span><span class="sxs-lookup"><span data-stu-id="d2c20-665">WEBVIEW2_WEB_ERROR_STATUS_ERROR_HTTP_INVALID_SERVER_RESPONSE</span></span>            | <span data-ttu-id="d2c20-666">服务器返回了无效或无法识别的响应。</span><span class="sxs-lookup"><span data-stu-id="d2c20-666">The server returned an invalid or unrecognized response.</span></span>
<span data-ttu-id="d2c20-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span><span class="sxs-lookup"><span data-stu-id="d2c20-667">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_ABORTED</span></span>            | <span data-ttu-id="d2c20-668">连接已中止。</span><span class="sxs-lookup"><span data-stu-id="d2c20-668">The connection was aborted.</span></span>
<span data-ttu-id="d2c20-669">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span><span class="sxs-lookup"><span data-stu-id="d2c20-669">WEBVIEW2_WEB_ERROR_STATUS_CONNECTION_RESET</span></span>            | <span data-ttu-id="d2c20-670">已重置连接。</span><span class="sxs-lookup"><span data-stu-id="d2c20-670">The connection was reset.</span></span>
<span data-ttu-id="d2c20-671">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span><span class="sxs-lookup"><span data-stu-id="d2c20-671">WEBVIEW2_WEB_ERROR_STATUS_DISCONNECTED</span></span>            | <span data-ttu-id="d2c20-672">互联网连接已丢失。</span><span class="sxs-lookup"><span data-stu-id="d2c20-672">The Internet connection has been lost.</span></span>
<span data-ttu-id="d2c20-673">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span><span class="sxs-lookup"><span data-stu-id="d2c20-673">WEBVIEW2_WEB_ERROR_STATUS_CANNOT_CONNECT</span></span>            | <span data-ttu-id="d2c20-674">无法连接到目标。</span><span class="sxs-lookup"><span data-stu-id="d2c20-674">Cannot connect to destination.</span></span>
<span data-ttu-id="d2c20-675">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span><span class="sxs-lookup"><span data-stu-id="d2c20-675">WEBVIEW2_WEB_ERROR_STATUS_HOST_NAME_NOT_RESOLVED</span></span>            | <span data-ttu-id="d2c20-676">无法解析提供的主机名。</span><span class="sxs-lookup"><span data-stu-id="d2c20-676">Could not resolve provided host name.</span></span>
<span data-ttu-id="d2c20-677">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span><span class="sxs-lookup"><span data-stu-id="d2c20-677">WEBVIEW2_WEB_ERROR_STATUS_OPERATION_CANCELED</span></span>            | <span data-ttu-id="d2c20-678">操作已取消。</span><span class="sxs-lookup"><span data-stu-id="d2c20-678">The operation was canceled.</span></span>
<span data-ttu-id="d2c20-679">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span><span class="sxs-lookup"><span data-stu-id="d2c20-679">WEBVIEW2_WEB_ERROR_STATUS_REDIRECT_FAILED</span></span>            | <span data-ttu-id="d2c20-680">请求重定向失败。</span><span class="sxs-lookup"><span data-stu-id="d2c20-680">The request redirect failed.</span></span>
<span data-ttu-id="d2c20-681">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span><span class="sxs-lookup"><span data-stu-id="d2c20-681">WEBVIEW2_WEB_ERROR_STATUS_UNEXPECTED_ERROR</span></span>            | <span data-ttu-id="d2c20-682">出现意外错误。</span><span class="sxs-lookup"><span data-stu-id="d2c20-682">An unexpected error occurred.</span></span>

#### <span data-ttu-id="d2c20-683">WEBVIEW2_WEB_RESOURCE_CONTEXT</span><span class="sxs-lookup"><span data-stu-id="d2c20-683">WEBVIEW2_WEB_RESOURCE_CONTEXT</span></span> 

<span data-ttu-id="d2c20-684">Web 资源请求上下文的枚举。</span><span class="sxs-lookup"><span data-stu-id="d2c20-684">Enum for web resource request contexts.</span></span>

> <span data-ttu-id="d2c20-685">枚举[WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span><span class="sxs-lookup"><span data-stu-id="d2c20-685">enum [WEBVIEW2_WEB_RESOURCE_CONTEXT](#webview2_web_resource_context)</span></span>

 <span data-ttu-id="d2c20-686">值</span><span class="sxs-lookup"><span data-stu-id="d2c20-686">Values</span></span>                         | <span data-ttu-id="d2c20-687">描述</span><span class="sxs-lookup"><span data-stu-id="d2c20-687">Descriptions</span></span>
--------------------------------|---------------------------------------------
<span data-ttu-id="d2c20-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span><span class="sxs-lookup"><span data-stu-id="d2c20-688">WEBVIEW2_WEB_RESOURCE_CONTEXT_ALL</span></span>            | <span data-ttu-id="d2c20-689">所有资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-689">All resources.</span></span>
<span data-ttu-id="d2c20-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span><span class="sxs-lookup"><span data-stu-id="d2c20-690">WEBVIEW2_WEB_RESOURCE_CONTEXT_DOCUMENT</span></span>            | <span data-ttu-id="d2c20-691">文档资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-691">Document resources.</span></span>
<span data-ttu-id="d2c20-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span><span class="sxs-lookup"><span data-stu-id="d2c20-692">WEBVIEW2_WEB_RESOURCE_CONTEXT_STYLESHEET</span></span>            | <span data-ttu-id="d2c20-693">CSS 资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-693">CSS resources.</span></span>
<span data-ttu-id="d2c20-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span><span class="sxs-lookup"><span data-stu-id="d2c20-694">WEBVIEW2_WEB_RESOURCE_CONTEXT_IMAGE</span></span>            | <span data-ttu-id="d2c20-695">图像资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-695">Image resources.</span></span>
<span data-ttu-id="d2c20-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span><span class="sxs-lookup"><span data-stu-id="d2c20-696">WEBVIEW2_WEB_RESOURCE_CONTEXT_MEDIA</span></span>            | <span data-ttu-id="d2c20-697">其他媒体资源（如视频）。</span><span class="sxs-lookup"><span data-stu-id="d2c20-697">Other media resources such as videos.</span></span>
<span data-ttu-id="d2c20-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span><span class="sxs-lookup"><span data-stu-id="d2c20-698">WEBVIEW2_WEB_RESOURCE_CONTEXT_FONT</span></span>            | <span data-ttu-id="d2c20-699">字体资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-699">Font resources.</span></span>
<span data-ttu-id="d2c20-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span><span class="sxs-lookup"><span data-stu-id="d2c20-700">WEBVIEW2_WEB_RESOURCE_CONTEXT_SCRIPT</span></span>            | <span data-ttu-id="d2c20-701">脚本资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-701">Script resources.</span></span>
<span data-ttu-id="d2c20-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span><span class="sxs-lookup"><span data-stu-id="d2c20-702">WEBVIEW2_WEB_RESOURCE_CONTEXT_XML_HTTP_REQUEST</span></span>            | <span data-ttu-id="d2c20-703">XML HTTP 请求。</span><span class="sxs-lookup"><span data-stu-id="d2c20-703">XML HTTP requests.</span></span>
<span data-ttu-id="d2c20-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span><span class="sxs-lookup"><span data-stu-id="d2c20-704">WEBVIEW2_WEB_RESOURCE_CONTEXT_FETCH</span></span>            | <span data-ttu-id="d2c20-705">获取 API 通信。</span><span class="sxs-lookup"><span data-stu-id="d2c20-705">Fetch API communication.</span></span>
<span data-ttu-id="d2c20-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span><span class="sxs-lookup"><span data-stu-id="d2c20-706">WEBVIEW2_WEB_RESOURCE_CONTEXT_TEXT_TRACK</span></span>            | <span data-ttu-id="d2c20-707">TextTrack 资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-707">TextTrack resources.</span></span>
<span data-ttu-id="d2c20-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span><span class="sxs-lookup"><span data-stu-id="d2c20-708">WEBVIEW2_WEB_RESOURCE_CONTEXT_EVENT_SOURCE</span></span>            | 
<span data-ttu-id="d2c20-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span><span class="sxs-lookup"><span data-stu-id="d2c20-709">WEBVIEW2_WEB_RESOURCE_CONTEXT_WEBSOCKET</span></span>            | 
<span data-ttu-id="d2c20-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span><span class="sxs-lookup"><span data-stu-id="d2c20-710">WEBVIEW2_WEB_RESOURCE_CONTEXT_MANIFEST</span></span>            | 
<span data-ttu-id="d2c20-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span><span class="sxs-lookup"><span data-stu-id="d2c20-711">WEBVIEW2_WEB_RESOURCE_CONTEXT_SIGNED_EXCHANGE</span></span>            | 
<span data-ttu-id="d2c20-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span><span class="sxs-lookup"><span data-stu-id="d2c20-712">WEBVIEW2_WEB_RESOURCE_CONTEXT_PING</span></span>            | 
<span data-ttu-id="d2c20-713">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span><span class="sxs-lookup"><span data-stu-id="d2c20-713">WEBVIEW2_WEB_RESOURCE_CONTEXT_CSP_VIOLATION_REPORT</span></span>            | 
<span data-ttu-id="d2c20-714">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span><span class="sxs-lookup"><span data-stu-id="d2c20-714">WEBVIEW2_WEB_RESOURCE_CONTEXT_OTHER</span></span>            | <span data-ttu-id="d2c20-715">其他资源。</span><span class="sxs-lookup"><span data-stu-id="d2c20-715">Other resources.</span></span>
