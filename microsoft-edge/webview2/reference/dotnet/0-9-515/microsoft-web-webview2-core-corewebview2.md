---
description: 通过 Microsoft Edge WebView2 控件在 Win32 应用中托管 web 内容
title: 适用于 Win32 应用的 Microsoft Edge WebView2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/12/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: IWebView2、IWebView2WebView、webview2、web 视图、win32 应用、win32、edge、ICoreWebView2、ICoreWebView2Controller、浏览器控件、边缘 html
ms.openlocfilehash: b45f672a6e06b1904ad28bad40317e4e827557b7
ms.sourcegitcommit: 8dca1c1367853e45a0a975bc89b1818adb117bd4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2020
ms.locfileid: "10697726"
---
# <span data-ttu-id="62ab9-104">CoreWebView2 类的 WebView2</span><span class="sxs-lookup"><span data-stu-id="62ab9-104">Microsoft.Web.WebView2.Core.CoreWebView2 class</span></span> 

> [!NOTE]
> <span data-ttu-id="62ab9-105">SDK 版本0.9.515 后，此参考可能会更改或不可用。</span><span class="sxs-lookup"><span data-stu-id="62ab9-105">This reference may be altered or unavailable for releases after SDK version 0.9.515.</span></span> <span data-ttu-id="62ab9-106">请参阅[WEBVIEW2 api 参考](../../../webview2-api-reference.md)了解最新的 API 参考。</span><span class="sxs-lookup"><span data-stu-id="62ab9-106">Please refer to [WebView2 API reference](../../../webview2-api-reference.md) for the latest API reference.</span></span>

<span data-ttu-id="62ab9-107">命名空间： Microsoft WebView2 </span><span class="sxs-lookup"><span data-stu-id="62ab9-107">Namespace: Microsoft.Web.WebView2.Core</span></span>\
<span data-ttu-id="62ab9-108">程序集： Microsoft WebView2</span><span class="sxs-lookup"><span data-stu-id="62ab9-108">Assembly: Microsoft.Web.WebView2.Core.dll</span></span>

<span data-ttu-id="62ab9-109">WebView2 使你能够使用最新的 Edge web 浏览器技术托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="62ab9-109">WebView2 enables you to host web content using the latest Edge web browser technology.</span></span>

## <span data-ttu-id="62ab9-110">摘要</span><span class="sxs-lookup"><span data-stu-id="62ab9-110">Summary</span></span>

 <span data-ttu-id="62ab9-111">成员</span><span class="sxs-lookup"><span data-stu-id="62ab9-111">Members</span></span>                        | <span data-ttu-id="62ab9-112">描述</span><span class="sxs-lookup"><span data-stu-id="62ab9-112">Descriptions</span></span>
--------------------------------|---------------------------------------------
[<span data-ttu-id="62ab9-113">BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="62ab9-113">BrowserProcessId</span></span>](#browserprocessid) | <span data-ttu-id="62ab9-114">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="62ab9-114">The process id of the browser process that hosts the WebView.</span></span>
[<span data-ttu-id="62ab9-115">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="62ab9-115">CanGoBack</span></span>](#cangoback) | <span data-ttu-id="62ab9-116">如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="62ab9-116">Returns true if the webview can navigate to a previous page in the navigation history.</span></span>
[<span data-ttu-id="62ab9-117">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="62ab9-117">CanGoForward</span></span>](#cangoforward) | <span data-ttu-id="62ab9-118">如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="62ab9-118">Returns true if the webview can navigate to a next page in the navigation history.</span></span>
[<span data-ttu-id="62ab9-119">ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="62ab9-119">ContainsFullScreenElement</span></span>](#containsfullscreenelement) | <span data-ttu-id="62ab9-120">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="62ab9-120">Indicates if the WebView contains a fullscreen HTML element.</span></span>
[<span data-ttu-id="62ab9-121">ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-121">ContainsFullScreenElementChanged</span></span>](#containsfullscreenelementchanged) | <span data-ttu-id="62ab9-122">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="62ab9-122">Notifies when the ContainsFullScreenElement property changes.</span></span>
[<span data-ttu-id="62ab9-123">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="62ab9-123">ContentLoading</span></span>](#contentloading) | <span data-ttu-id="62ab9-124">ContentLoading 在加载任何内容之前激发，包括使用 AddScriptToExecuteOnDocumentCreated ContentLoading 添加的脚本在同一页面导航（如通过片段导航或历史记录）发生时不会触发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-124">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span>
[<span data-ttu-id="62ab9-125">DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="62ab9-125">DocumentTitle</span></span>](#documenttitle) | <span data-ttu-id="62ab9-126">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="62ab9-126">The title for the current top level document.</span></span>
[<span data-ttu-id="62ab9-127">DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-127">DocumentTitleChanged</span></span>](#documenttitlechanged) | <span data-ttu-id="62ab9-128">当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-128">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>
[<span data-ttu-id="62ab9-129">FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="62ab9-129">FrameNavigationCompleted</span></span>](#framenavigationcompleted) | <span data-ttu-id="62ab9-130">当子框架已完全加载（已激发了 FrameNavigationCompleted）或加载时出错，已停止加载时，将引发事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-130">FrameNavigationCompleted event fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>
[<span data-ttu-id="62ab9-131">FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="62ab9-131">FrameNavigationStarting</span></span>](#framenavigationstarting) | <span data-ttu-id="62ab9-132">当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="62ab9-132">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span>
[<span data-ttu-id="62ab9-133">HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-133">HistoryChanged</span></span>](#historychanged) | <span data-ttu-id="62ab9-134">历史记录更改侦听顶级文档的导航历史记录更改。</span><span class="sxs-lookup"><span data-stu-id="62ab9-134">HistoryChange listen to the change of navigation history for the top level document.</span></span>
[<span data-ttu-id="62ab9-135">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="62ab9-135">NavigationCompleted</span></span>](#navigationcompleted) | <span data-ttu-id="62ab9-136">当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-136">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>
[<span data-ttu-id="62ab9-137">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="62ab9-137">NavigationStarting</span></span>](#navigationstarting) | <span data-ttu-id="62ab9-138">当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="62ab9-138">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span>
[<span data-ttu-id="62ab9-139">Webview.newwindowrequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-139">NewWindowRequested</span></span>](#newwindowrequested) | <span data-ttu-id="62ab9-140">在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-140">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span>
[<span data-ttu-id="62ab9-141">Webview.permissionrequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-141">PermissionRequested</span></span>](#permissionrequested) | <span data-ttu-id="62ab9-142">在 Web 视图中的内容请求访问某些权限资源的权限时引发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-142">Fires when content in a WebView requests permission to access some privileged resources.</span></span>
[<span data-ttu-id="62ab9-143">ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="62ab9-143">ProcessFailed</span></span>](#processfailed) | <span data-ttu-id="62ab9-144">当 Web 视图进程意外终止或停止响应时激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-144">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>
[<span data-ttu-id="62ab9-145">ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="62ab9-145">ScriptDialogOpening</span></span>](#scriptdialogopening) | <span data-ttu-id="62ab9-146">将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-146">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span>
[<span data-ttu-id="62ab9-147">设置</span><span class="sxs-lookup"><span data-stu-id="62ab9-147">Settings</span></span>](#settings) | <span data-ttu-id="62ab9-148">CoreWebView2Settings 对象包含适用于运行的的各种可修改设置</span><span class="sxs-lookup"><span data-stu-id="62ab9-148">The CoreWebView2Settings object contains various modifiable settings for the running</span></span>
[<span data-ttu-id="62ab9-149">来源</span><span class="sxs-lookup"><span data-stu-id="62ab9-149">Source</span></span>](#source) | <span data-ttu-id="62ab9-150">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="62ab9-150">The URI of the current top level document.</span></span>
[<span data-ttu-id="62ab9-151">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-151">SourceChanged</span></span>](#sourcechanged) | <span data-ttu-id="62ab9-152">Source 属性更改时将触发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="62ab9-152">SourceChanged fires when the Source property changes.</span></span>
[<span data-ttu-id="62ab9-153">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="62ab9-153">WebMessageReceived</span></span>](#webmessagereceived) | <span data-ttu-id="62ab9-154">当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-154">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>
[<span data-ttu-id="62ab9-155">WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-155">WebResourceRequested</span></span>](#webresourcerequested) | <span data-ttu-id="62ab9-156">在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-156">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span>
[<span data-ttu-id="62ab9-157">WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-157">WindowCloseRequested</span></span>](#windowcloserequested) | <span data-ttu-id="62ab9-158">在 Web 视图中请求关闭窗口的内容（如在窗口后）关闭窗口时激发。调用 close。</span><span class="sxs-lookup"><span data-stu-id="62ab9-158">Fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span>
[<span data-ttu-id="62ab9-159">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="62ab9-159">AddHostObjectToScript</span></span>](#addhostobjecttoscript) | <span data-ttu-id="62ab9-160">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="62ab9-160">Add the provided host object to script running in the WebView with the specified name.</span></span>
[<span data-ttu-id="62ab9-161">AddScriptToExecuteOnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-161">AddScriptToExecuteOnDocumentCreatedAsync</span></span>](#addscripttoexecuteondocumentcreatedasync) | <span data-ttu-id="62ab9-162">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="62ab9-162">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>
[<span data-ttu-id="62ab9-163">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="62ab9-163">AddWebResourceRequestedFilter</span></span>](#addwebresourcerequestedfilter) | <span data-ttu-id="62ab9-164">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-164">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>
[<span data-ttu-id="62ab9-165">CallDevToolsProtocolMethodAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-165">CallDevToolsProtocolMethodAsync</span></span>](#calldevtoolsprotocolmethodasync) | <span data-ttu-id="62ab9-166">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-166">Call an asynchronous DevToolsProtocol method.</span></span>
[<span data-ttu-id="62ab9-167">CapturePreviewAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-167">CapturePreviewAsync</span></span>](#capturepreviewasync) | <span data-ttu-id="62ab9-168">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="62ab9-168">Capture an image of what WebView is displaying.</span></span>
[<span data-ttu-id="62ab9-169">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-169">ExecuteScriptAsync</span></span>](#executescriptasync) | <span data-ttu-id="62ab9-170">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="62ab9-170">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>
[<span data-ttu-id="62ab9-171">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="62ab9-171">GetDevToolsProtocolEventReceiver</span></span>](#getdevtoolsprotocoleventreceiver) | <span data-ttu-id="62ab9-172">获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。</span><span class="sxs-lookup"><span data-stu-id="62ab9-172">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>
[<span data-ttu-id="62ab9-173">GoBack</span><span class="sxs-lookup"><span data-stu-id="62ab9-173">GoBack</span></span>](#goback) | <span data-ttu-id="62ab9-174">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="62ab9-174">Navigates the WebView to the previous page in the navigation history.</span></span>
[<span data-ttu-id="62ab9-175">GoForward</span><span class="sxs-lookup"><span data-stu-id="62ab9-175">GoForward</span></span>](#goforward) | <span data-ttu-id="62ab9-176">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="62ab9-176">Navigates the WebView to the next page in the navigation history.</span></span>
[<span data-ttu-id="62ab9-177">导航</span><span class="sxs-lookup"><span data-stu-id="62ab9-177">Navigate</span></span>](#navigate) | <span data-ttu-id="62ab9-178">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="62ab9-178">Cause a navigation of the top level document to the specified URI.</span></span>
[<span data-ttu-id="62ab9-179">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="62ab9-179">NavigateToString</span></span>](#navigatetostring) | <span data-ttu-id="62ab9-180">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="62ab9-180">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>
[<span data-ttu-id="62ab9-181">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="62ab9-181">OpenDevToolsWindow</span></span>](#opendevtoolswindow) | <span data-ttu-id="62ab9-182">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="62ab9-182">Opens the DevTools window for the current document in the WebView.</span></span>
[<span data-ttu-id="62ab9-183">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="62ab9-183">PostWebMessageAsJson</span></span>](#postwebmessageasjson) | <span data-ttu-id="62ab9-184">将指定的 webMessage 发布到此 Web 视图中的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="62ab9-184">Post the specified webMessage to the top level document in this WebView.</span></span>
[<span data-ttu-id="62ab9-185">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="62ab9-185">PostWebMessageAsString</span></span>](#postwebmessageasstring) | <span data-ttu-id="62ab9-186">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="62ab9-186">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>
[<span data-ttu-id="62ab9-187">重载</span><span class="sxs-lookup"><span data-stu-id="62ab9-187">Reload</span></span>](#reload) | <span data-ttu-id="62ab9-188">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="62ab9-188">Reload the current page.</span></span>
[<span data-ttu-id="62ab9-189">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="62ab9-189">RemoveHostObjectFromScript</span></span>](#removehostobjectfromscript) | <span data-ttu-id="62ab9-190">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="62ab9-190">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>
[<span data-ttu-id="62ab9-191">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="62ab9-191">RemoveScriptToExecuteOnDocumentCreated</span></span>](#removescripttoexecuteondocumentcreated) | <span data-ttu-id="62ab9-192">删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="62ab9-192">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>
[<span data-ttu-id="62ab9-193">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="62ab9-193">RemoveWebResourceRequestedFilter</span></span>](#removewebresourcerequestedfilter) | <span data-ttu-id="62ab9-194">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="62ab9-194">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>
[<span data-ttu-id="62ab9-195">停止</span><span class="sxs-lookup"><span data-stu-id="62ab9-195">Stop</span></span>](#stop) | <span data-ttu-id="62ab9-196">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="62ab9-196">Stop all navigations and pending resource fetches.</span></span>

## <span data-ttu-id="62ab9-197">成员</span><span class="sxs-lookup"><span data-stu-id="62ab9-197">Members</span></span>

#### <span data-ttu-id="62ab9-198">BrowserProcessId</span><span class="sxs-lookup"><span data-stu-id="62ab9-198">BrowserProcessId</span></span> 

<span data-ttu-id="62ab9-199">托管 Web 视图的浏览器进程的进程 id。</span><span class="sxs-lookup"><span data-stu-id="62ab9-199">The process id of the browser process that hosts the WebView.</span></span>

> <span data-ttu-id="62ab9-200">公共 uint [BrowserProcessId](#browserprocessid)</span><span class="sxs-lookup"><span data-stu-id="62ab9-200">public uint [BrowserProcessId](#browserprocessid)</span></span>

#### <span data-ttu-id="62ab9-201">CanGoBack</span><span class="sxs-lookup"><span data-stu-id="62ab9-201">CanGoBack</span></span> 

<span data-ttu-id="62ab9-202">如果 web 视图可以导航到导航历史记录中的上一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="62ab9-202">Returns true if the webview can navigate to a previous page in the navigation history.</span></span>

> <span data-ttu-id="62ab9-203">公共 bool [CanGoBack](#cangoback)</span><span class="sxs-lookup"><span data-stu-id="62ab9-203">public bool [CanGoBack](#cangoback)</span></span>

<span data-ttu-id="62ab9-204">如果 CanGoBack 更改值，将引发 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-204">The HistoryChanged event will fire if CanGoBack changes value.</span></span>

#### <span data-ttu-id="62ab9-205">CanGoForward</span><span class="sxs-lookup"><span data-stu-id="62ab9-205">CanGoForward</span></span> 

<span data-ttu-id="62ab9-206">如果 web 视图可以导航到导航历史记录中的下一页，则返回 true。</span><span class="sxs-lookup"><span data-stu-id="62ab9-206">Returns true if the webview can navigate to a next page in the navigation history.</span></span>

> <span data-ttu-id="62ab9-207">公共 bool [CanGoForward](#cangoforward)</span><span class="sxs-lookup"><span data-stu-id="62ab9-207">public bool [CanGoForward](#cangoforward)</span></span>

<span data-ttu-id="62ab9-208">如果 CanGoForward 更改值，将引发 HistoryChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-208">The HistoryChanged event will fire if CanGoForward changes value.</span></span>

#### <span data-ttu-id="62ab9-209">ContainsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="62ab9-209">ContainsFullScreenElement</span></span> 

<span data-ttu-id="62ab9-210">指示 Web 视图是否包含全屏 HTML 元素。</span><span class="sxs-lookup"><span data-stu-id="62ab9-210">Indicates if the WebView contains a fullscreen HTML element.</span></span>

> <span data-ttu-id="62ab9-211">公共 bool [ContainsFullScreenElement](#containsfullscreenelement)</span><span class="sxs-lookup"><span data-stu-id="62ab9-211">public bool [ContainsFullScreenElement](#containsfullscreenelement)</span></span>

#### <span data-ttu-id="62ab9-212">ContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-212">ContainsFullScreenElementChanged</span></span> 

<span data-ttu-id="62ab9-213">ContainsFullScreenElement 属性更改时通知。</span><span class="sxs-lookup"><span data-stu-id="62ab9-213">Notifies when the ContainsFullScreenElement property changes.</span></span>

> <span data-ttu-id="62ab9-214">公共事件 EventHandler< 对象 > [ContainsFullScreenElementChanged](#containsfullscreenelementchanged)</span><span class="sxs-lookup"><span data-stu-id="62ab9-214">public event EventHandler< object > [ContainsFullScreenElementChanged](#containsfullscreenelementchanged)</span></span>

<span data-ttu-id="62ab9-215">这意味着 Web 视图中的 HTML 元素正在将全屏输入到 Web 视图的大小或离开全屏。</span><span class="sxs-lookup"><span data-stu-id="62ab9-215">This means that an HTML element inside the WebView is entering fullscreen to the size of the WebView or leaving fullscreen.</span></span> <span data-ttu-id="62ab9-216">例如，当视频元素请求进入全屏时，此事件非常有用。</span><span class="sxs-lookup"><span data-stu-id="62ab9-216">This event is useful when, for example, a video element requests to go fullscreen.</span></span> <span data-ttu-id="62ab9-217">然后，ContainsFullScreenElementChanged 的侦听器可以在响应中调整 Web 视图的大小。</span><span class="sxs-lookup"><span data-stu-id="62ab9-217">The listener of ContainsFullScreenElementChanged can then resize the WebView in response.</span></span>

#### <span data-ttu-id="62ab9-218">ContentLoading</span><span class="sxs-lookup"><span data-stu-id="62ab9-218">ContentLoading</span></span> 

<span data-ttu-id="62ab9-219">ContentLoading 在加载任何内容之前激发，包括使用 AddScriptToExecuteOnDocumentCreated ContentLoading 添加的脚本在同一页面导航（如通过片段导航或历史记录）发生时不会触发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-219">ContentLoading fires before any content is loaded, including scripts added with AddScriptToExecuteOnDocumentCreated ContentLoading will not fire if a same page navigation occurs (such as through fragment navigations or history.pushState navigations).</span></span>

> <span data-ttu-id="62ab9-220">公共事件 EventHandler< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md)  >  [ContentLoading](#contentloading)</span><span class="sxs-lookup"><span data-stu-id="62ab9-220">public event EventHandler< [CoreWebView2ContentLoadingEventArgs](microsoft-web-webview2-core-corewebview2contentloadingeventargs.md) > [ContentLoading](#contentloading)</span></span>

<span data-ttu-id="62ab9-221">这将遵循 NavigationStarting 和 SourceChanged 事件，并在 HistoryChanged 和 NavigationCompleted 事件之前。</span><span class="sxs-lookup"><span data-stu-id="62ab9-221">This follows the NavigationStarting and SourceChanged events and precedes the HistoryChanged and NavigationCompleted events.</span></span>

#### <span data-ttu-id="62ab9-222">DocumentTitle</span><span class="sxs-lookup"><span data-stu-id="62ab9-222">DocumentTitle</span></span> 

<span data-ttu-id="62ab9-223">当前顶级文档的标题。</span><span class="sxs-lookup"><span data-stu-id="62ab9-223">The title for the current top level document.</span></span>

> <span data-ttu-id="62ab9-224">公共字符串[DocumentTitle](#documenttitle)</span><span class="sxs-lookup"><span data-stu-id="62ab9-224">public string [DocumentTitle](#documenttitle)</span></span>

<span data-ttu-id="62ab9-225">如果文档没有显式标题或为空，则将使用与文档的 URI 相匹配或可能不匹配的默认值。</span><span class="sxs-lookup"><span data-stu-id="62ab9-225">If the document has no explicit title or is otherwise empty, a default that may or may not match the URI of the document will be used.</span></span>

#### <span data-ttu-id="62ab9-226">DocumentTitleChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-226">DocumentTitleChanged</span></span> 

<span data-ttu-id="62ab9-227">当 Web 视图的 DocumentTitle 属性发生更改，并且可能会在 NavigationCompleted 事件之前或之后出现时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-227">The event fires when the DocumentTitle property of the WebView changes and may fire before or after the NavigationCompleted event.</span></span>

> <span data-ttu-id="62ab9-228">公共事件 EventHandler< 对象 > [DocumentTitleChanged](#documenttitlechanged)</span><span class="sxs-lookup"><span data-stu-id="62ab9-228">public event EventHandler< object > [DocumentTitleChanged](#documenttitlechanged)</span></span>

#### <span data-ttu-id="62ab9-229">FrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="62ab9-229">FrameNavigationCompleted</span></span> 

<span data-ttu-id="62ab9-230">当子框架已完全加载（已激发了 FrameNavigationCompleted）或加载时出错，已停止加载时，将引发事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-230">FrameNavigationCompleted event fires when a child frame has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

> <span data-ttu-id="62ab9-231">公共事件 EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [FrameNavigationCompleted](#framenavigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="62ab9-231">public event EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md) > [FrameNavigationCompleted](#framenavigationcompleted)</span></span>

#### <span data-ttu-id="62ab9-232">FrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="62ab9-232">FrameNavigationStarting</span></span> 

<span data-ttu-id="62ab9-233">当 Web 视图中请求权限导航到其他 URI 的子帧时，将触发 FrameNavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="62ab9-233">FrameNavigationStarting fires when a child frame in the WebView requesting permission to navigate to a different URI.</span></span>

> <span data-ttu-id="62ab9-234">公共事件 EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [FrameNavigationStarting](#framenavigationstarting)</span><span class="sxs-lookup"><span data-stu-id="62ab9-234">public event EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md) > [FrameNavigationStarting](#framenavigationstarting)</span></span>

<span data-ttu-id="62ab9-235">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="62ab9-235">This will fire for redirects as well.</span></span>

#### <span data-ttu-id="62ab9-236">HistoryChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-236">HistoryChanged</span></span> 

<span data-ttu-id="62ab9-237">历史记录更改侦听顶级文档的导航历史记录更改。</span><span class="sxs-lookup"><span data-stu-id="62ab9-237">HistoryChange listen to the change of navigation history for the top level document.</span></span>

> <span data-ttu-id="62ab9-238">公共事件 EventHandler< 对象 > [HistoryChanged](#historychanged)</span><span class="sxs-lookup"><span data-stu-id="62ab9-238">public event EventHandler< object > [HistoryChanged](#historychanged)</span></span>

<span data-ttu-id="62ab9-239">使用历史记录更改检查 CanGoBack/CanGoForward 值是否已更改。</span><span class="sxs-lookup"><span data-stu-id="62ab9-239">Use HistoryChange to check if CanGoBack/CanGoForward value has changed.</span></span> <span data-ttu-id="62ab9-240">使用 GoBack/GoForward 时也会触发 HistoryChanged。</span><span class="sxs-lookup"><span data-stu-id="62ab9-240">HistoryChanged also fires for using GoBack/GoForward.</span></span> <span data-ttu-id="62ab9-241">HistoryChanged 在 SourceChanged 和 ContentLoading 后激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-241">HistoryChanged fires after SourceChanged and ContentLoading.</span></span> <span data-ttu-id="62ab9-242">为 HistoryChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="62ab9-242">Add an event handler for the HistoryChanged event.</span></span>

#### <span data-ttu-id="62ab9-243">NavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="62ab9-243">NavigationCompleted</span></span> 

<span data-ttu-id="62ab9-244">当 Web 视图已完全加载（NavigationCompleted 已激发）或加载时出现错误，将引发事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-244">NavigationCompleted event fires when the WebView has completely loaded (body.onload has fired) or loading stopped with error.</span></span>

> <span data-ttu-id="62ab9-245">公共事件 EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md)  >  [NavigationCompleted](#navigationcompleted)</span><span class="sxs-lookup"><span data-stu-id="62ab9-245">public event EventHandler< [CoreWebView2NavigationCompletedEventArgs](microsoft-web-webview2-core-corewebview2navigationcompletedeventargs.md) > [NavigationCompleted](#navigationcompleted)</span></span>

#### <span data-ttu-id="62ab9-246">NavigationStarting</span><span class="sxs-lookup"><span data-stu-id="62ab9-246">NavigationStarting</span></span> 

<span data-ttu-id="62ab9-247">当 Web 视图主框架请求导航到其他 URI 的权限时，将触发 NavigationStarting。</span><span class="sxs-lookup"><span data-stu-id="62ab9-247">NavigationStarting fires when the WebView main frame is requesting permission to navigate to a different URI.</span></span>

> <span data-ttu-id="62ab9-248">公共事件 EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md)  >  [NavigationStarting](#navigationstarting)</span><span class="sxs-lookup"><span data-stu-id="62ab9-248">public event EventHandler< [CoreWebView2NavigationStartingEventArgs](microsoft-web-webview2-core-corewebview2navigationstartingeventargs.md) > [NavigationStarting](#navigationstarting)</span></span>

<span data-ttu-id="62ab9-249">这也会引发重定向。</span><span class="sxs-lookup"><span data-stu-id="62ab9-249">This will fire for redirects as well.</span></span>

#### <span data-ttu-id="62ab9-250">Webview.newwindowrequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-250">NewWindowRequested</span></span> 

<span data-ttu-id="62ab9-251">在 Web 视图中请求打开新窗口（如通过 window）的内容时激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-251">Fires when content inside the WebView requested to open a new window, such as through window.open.</span></span>

> <span data-ttu-id="62ab9-252">公共事件 EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md)  >  [webview.newwindowrequested](#newwindowrequested)</span><span class="sxs-lookup"><span data-stu-id="62ab9-252">public event EventHandler< [CoreWebView2NewWindowRequestedEventArgs](microsoft-web-webview2-core-corewebview2newwindowrequestedeventargs.md) > [NewWindowRequested](#newwindowrequested)</span></span>

<span data-ttu-id="62ab9-253">应用可以传递将被视为打开的窗口的目标 web 视图。</span><span class="sxs-lookup"><span data-stu-id="62ab9-253">The app can pass a target webview that will be considered the opened window.</span></span>

#### <span data-ttu-id="62ab9-254">Webview.permissionrequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-254">PermissionRequested</span></span> 

<span data-ttu-id="62ab9-255">在 Web 视图中的内容请求访问某些权限资源的权限时引发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-255">Fires when content in a WebView requests permission to access some privileged resources.</span></span>

> <span data-ttu-id="62ab9-256">公共事件 EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md)  >  [webview.permissionrequested](#permissionrequested)</span><span class="sxs-lookup"><span data-stu-id="62ab9-256">public event EventHandler< [CoreWebView2PermissionRequestedEventArgs](microsoft-web-webview2-core-corewebview2permissionrequestedeventargs.md) > [PermissionRequested](#permissionrequested)</span></span>

#### <span data-ttu-id="62ab9-257">ProcessFailed</span><span class="sxs-lookup"><span data-stu-id="62ab9-257">ProcessFailed</span></span> 

<span data-ttu-id="62ab9-258">当 Web 视图进程意外终止或停止响应时激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-258">Fires when a WebView process terminated unexpectedly or become unresponsive.</span></span>

> <span data-ttu-id="62ab9-259">公共事件 EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md)  >  [ProcessFailed](#processfailed)</span><span class="sxs-lookup"><span data-stu-id="62ab9-259">public event EventHandler< [CoreWebView2ProcessFailedEventArgs](microsoft-web-webview2-core-corewebview2processfailedeventargs.md) > [ProcessFailed](#processfailed)</span></span>

#### <span data-ttu-id="62ab9-260">ScriptDialogOpening</span><span class="sxs-lookup"><span data-stu-id="62ab9-260">ScriptDialogOpening</span></span> 

<span data-ttu-id="62ab9-261">将针对 web 视图显示 JavaScript 对话框（警报、确认或提示）时，将引发此事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-261">The event fires when a JavaScript dialog (alert, confirm, or prompt) will show for the webview.</span></span>

> <span data-ttu-id="62ab9-262">公共事件 EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md)  >  [ScriptDialogOpening](#scriptdialogopening)</span><span class="sxs-lookup"><span data-stu-id="62ab9-262">public event EventHandler< [CoreWebView2ScriptDialogOpeningEventArgs](microsoft-web-webview2-core-corewebview2scriptdialogopeningeventargs.md) > [ScriptDialogOpening](#scriptdialogopening)</span></span>

<span data-ttu-id="62ab9-263">仅当 AreDefaultScriptDialogsEnabled 属性设置为 false 时，此事件才会触发 CoreWebView2Settings。</span><span class="sxs-lookup"><span data-stu-id="62ab9-263">This event only fires if the CoreWebView2Settings.AreDefaultScriptDialogsEnabled property is set to false.</span></span> <span data-ttu-id="62ab9-264">ScriptDialogOpening 事件可用于取消对话框或使用自定义对话框替换默认对话框。</span><span class="sxs-lookup"><span data-stu-id="62ab9-264">The ScriptDialogOpening event can be used to suppress dialogs or replace default dialogs with custom dialogs.</span></span>

#### <span data-ttu-id="62ab9-265">设置</span><span class="sxs-lookup"><span data-stu-id="62ab9-265">Settings</span></span> 

<span data-ttu-id="62ab9-266">CoreWebView2Settings 对象包含适用于运行的的各种可修改设置</span><span class="sxs-lookup"><span data-stu-id="62ab9-266">The CoreWebView2Settings object contains various modifiable settings for the running</span></span>

> <span data-ttu-id="62ab9-267">公共[CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md) [设置](#settings)</span><span class="sxs-lookup"><span data-stu-id="62ab9-267">public [CoreWebView2Settings](microsoft-web-webview2-core-corewebview2settings.md) [Settings](#settings)</span></span>

#### <span data-ttu-id="62ab9-268">来源</span><span class="sxs-lookup"><span data-stu-id="62ab9-268">Source</span></span> 

<span data-ttu-id="62ab9-269">当前顶级文档的 URI。</span><span class="sxs-lookup"><span data-stu-id="62ab9-269">The URI of the current top level document.</span></span>

> <span data-ttu-id="62ab9-270">公共字符串[源](#source)</span><span class="sxs-lookup"><span data-stu-id="62ab9-270">public string [Source](#source)</span></span>

<span data-ttu-id="62ab9-271">在某些情况下（例如导航到不同的网站或片段导航），此值可能会更改 SourceChanged 事件的一部分。</span><span class="sxs-lookup"><span data-stu-id="62ab9-271">This value potentially changes as a part of the SourceChanged event firing for some cases such as navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="62ab9-272">它对于其他类型的导航（如页面重新加载或 pushState 与当前页面具有相同的 URL）保持不变。</span><span class="sxs-lookup"><span data-stu-id="62ab9-272">It will remain the same for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span>

#### <span data-ttu-id="62ab9-273">SourceChanged</span><span class="sxs-lookup"><span data-stu-id="62ab9-273">SourceChanged</span></span> 

<span data-ttu-id="62ab9-274">Source 属性更改时将触发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="62ab9-274">SourceChanged fires when the Source property changes.</span></span>

> <span data-ttu-id="62ab9-275">公共事件 EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md)  >  [SourceChanged](#sourcechanged)</span><span class="sxs-lookup"><span data-stu-id="62ab9-275">public event EventHandler< [CoreWebView2SourceChangedEventArgs](microsoft-web-webview2-core-corewebview2sourcechangedeventargs.md) > [SourceChanged](#sourcechanged)</span></span>

<span data-ttu-id="62ab9-276">导航到其他网站或片段导航时，将引发 SourceChanged。</span><span class="sxs-lookup"><span data-stu-id="62ab9-276">SourceChanged fires for navigating to a different site or fragment navigations.</span></span> <span data-ttu-id="62ab9-277">对于其他类型的导航（如页面重新加载或 pushState，其 URL 与当前页面相同），不会引发此类导航。</span><span class="sxs-lookup"><span data-stu-id="62ab9-277">It will not fires for other types of navigations such as page reloads or history.pushState with the same URL as the current page.</span></span> <span data-ttu-id="62ab9-278">SourceChanged 将在 ContentLoading 之前激发，以便导航到新文档。</span><span class="sxs-lookup"><span data-stu-id="62ab9-278">SourceChanged fires before ContentLoading for navigation to a new document.</span></span> <span data-ttu-id="62ab9-279">为 SourceChanged 事件添加事件处理程序。</span><span class="sxs-lookup"><span data-stu-id="62ab9-279">Add an event handler for the SourceChanged event.</span></span>

#### <span data-ttu-id="62ab9-280">WebMessageReceived</span><span class="sxs-lookup"><span data-stu-id="62ab9-280">WebMessageReceived</span></span> 

<span data-ttu-id="62ab9-281">当设置 IsWebMessageEnabled 设置和 web 视图调用的顶级文档时，将引发此事件 `window.chrome.webview.postMessage` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-281">This event fires when the IsWebMessageEnabled setting is set and the top level document of the webview calls `window.chrome.webview.postMessage`.</span></span>

> <span data-ttu-id="62ab9-282">公共事件 EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md)  >  [WebMessageReceived](#webmessagereceived)</span><span class="sxs-lookup"><span data-stu-id="62ab9-282">public event EventHandler< [CoreWebView2WebMessageReceivedEventArgs](microsoft-web-webview2-core-corewebview2webmessagereceivedeventargs.md) > [WebMessageReceived](#webmessagereceived)</span></span>

<span data-ttu-id="62ab9-283">PostMessage 函数是 `void postMessage(object)` 对象是 JSON 转换支持的任何对象。</span><span class="sxs-lookup"><span data-stu-id="62ab9-283">The postMessage function is `void postMessage(object)` where object is any object supported by JSON conversion.</span></span> <span data-ttu-id="62ab9-284">当调用 postMessage 时，将使用转换为 JSON 字符串的 postMessage 对象参数来调用 CoreWebView2WebMessageReceivedEventHandler 集。</span><span class="sxs-lookup"><span data-stu-id="62ab9-284">When postMessage is called, the CoreWebView2WebMessageReceivedEventHandler set will be invoked with the postMessage's object parameter converted to a JSON string.</span></span>

#### <span data-ttu-id="62ab9-285">WebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-285">WebResourceRequested</span></span> 

<span data-ttu-id="62ab9-286">在 Web 视图对使用 AddWebResourceRequestedFilter 添加的匹配 URL 和资源上下文筛选器执行 HTTP 请求时激发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-286">Fires when the WebView is performing an HTTP request to a matching URL and resource context filter that was added with AddWebResourceRequestedFilter.</span></span>

> <span data-ttu-id="62ab9-287">公共事件 EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md)  >  [WebResourceRequested](#webresourcerequested)</span><span class="sxs-lookup"><span data-stu-id="62ab9-287">public event EventHandler< [CoreWebView2WebResourceRequestedEventArgs](microsoft-web-webview2-core-corewebview2webresourcerequestedeventargs.md) > [WebResourceRequested](#webresourcerequested)</span></span>

<span data-ttu-id="62ab9-288">必须至少添加一个筛选器，才能触发该事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-288">At least one filter must be added for the event to fire.</span></span>

#### <span data-ttu-id="62ab9-289">WindowCloseRequested</span><span class="sxs-lookup"><span data-stu-id="62ab9-289">WindowCloseRequested</span></span> 

<span data-ttu-id="62ab9-290">在 Web 视图中请求关闭窗口的内容（如在窗口后）关闭窗口时激发。调用 close。</span><span class="sxs-lookup"><span data-stu-id="62ab9-290">Fires when content inside the WebView requested to close the window, such as after window.close is called.</span></span>

> <span data-ttu-id="62ab9-291">公共事件 EventHandler< 对象 > [WindowCloseRequested](#windowcloserequested)</span><span class="sxs-lookup"><span data-stu-id="62ab9-291">public event EventHandler< object > [WindowCloseRequested](#windowcloserequested)</span></span>

<span data-ttu-id="62ab9-292">如果应用程序有意义，则应用应关闭 Web 视图和相关应用窗口。</span><span class="sxs-lookup"><span data-stu-id="62ab9-292">The app should close the WebView and related app window if that makes sense to the app.</span></span>

#### <span data-ttu-id="62ab9-293">AddHostObjectToScript</span><span class="sxs-lookup"><span data-stu-id="62ab9-293">AddHostObjectToScript</span></span> 

<span data-ttu-id="62ab9-294">将所提供的主机对象添加到在具有指定名称的 Web 视图中运行的脚本。</span><span class="sxs-lookup"><span data-stu-id="62ab9-294">Add the provided host object to script running in the WebView with the specified name.</span></span>

> <span data-ttu-id="62ab9-295">公共 void [AddHostObjectToScript](#addhostobjecttoscript)（字符串名称、对象 rawObject）</span><span class="sxs-lookup"><span data-stu-id="62ab9-295">public void [AddHostObjectToScript](#addhostobjecttoscript)(string name, object rawObject)</span></span>

<span data-ttu-id="62ab9-296">主机对象通过来公开为主机对象代理 `window.chrome.webview.hostObjects.{name}` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-296">Host objects are exposed as host object proxies via `window.chrome.webview.hostObjects.{name}`.</span></span> <span data-ttu-id="62ab9-297">主机对象代理承诺并将解析为表示主机对象的对象。</span><span class="sxs-lookup"><span data-stu-id="62ab9-297">Host object proxies are promises and will resolve to an object representing the host object.</span></span> <span data-ttu-id="62ab9-298">Web 视图中的 JavaScript 代码将能够按如下方式访问 appObject，然后访问 appObject 的属性和方法：</span><span class="sxs-lookup"><span data-stu-id="62ab9-298">JavaScript code in the WebView will be able to access appObject as following and then access attributes and methods of appObject:</span></span> 
```
let app_object = await window.chrome.webview.hostObjects.host_object;
let attr1 = await app_object.attr1;
let result = await app_object.method1(parameters);
```
 <span data-ttu-id="62ab9-299">请注意，虽然简单类型、IDispatch 和数组受支持、泛型 IUnknown、VT_DECIMAL 或 VT_RECORD 变体不受支持。</span><span class="sxs-lookup"><span data-stu-id="62ab9-299">Note that while simple types, IDispatch and array are supported, generic IUnknown, VT_DECIMAL, or VT_RECORD variant is not supported.</span></span> <span data-ttu-id="62ab9-300">远程 JavaScript 对象（如回调函数）使用实现 IDispatch 的对象表示为 VT_DISPATCH 变体。</span><span class="sxs-lookup"><span data-stu-id="62ab9-300">Remote JavaScript objects like callback functions are represented as an VT_DISPATCH VARIANT with the object implementing IDispatch.</span></span> <span data-ttu-id="62ab9-301">可以使用 DISPID 的 DISPID_VALUE 调用 JavaScript 回调方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-301">The JavaScript callback method may be invoked using DISPID_VALUE for the DISPID.</span></span> <span data-ttu-id="62ab9-302">嵌套数组的支持深度为3。</span><span class="sxs-lookup"><span data-stu-id="62ab9-302">Nested arrays are supported up to a depth of 3.</span></span> <span data-ttu-id="62ab9-303">不支持按引用类型的数组。</span><span class="sxs-lookup"><span data-stu-id="62ab9-303">Arrays of by reference types are not supported.</span></span> <span data-ttu-id="62ab9-304">VT_EMPTY 和 VT_NULL 以 NULL 的形式映射到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="62ab9-304">VT_EMPTY and VT_NULL are mapped into JavaScript as null.</span></span> <span data-ttu-id="62ab9-305">在 JavaScript null 中，未定义映射到 VT_EMPTY。</span><span class="sxs-lookup"><span data-stu-id="62ab9-305">In JavaScript null and undefined are mapped to VT_EMPTY.</span></span>

<span data-ttu-id="62ab9-306">此外，所有主机对象都公开为 `window.chrome.webview.hostObjects.sync.{name}` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-306">Additionally, all host objects are exposed as `window.chrome.webview.hostObjects.sync.{name}`.</span></span> <span data-ttu-id="62ab9-307">此处，主机对象作为同步主机对象代理公开。</span><span class="sxs-lookup"><span data-stu-id="62ab9-307">Here the host objects are exposed as synchronous host object proxies.</span></span> <span data-ttu-id="62ab9-308">这些不承诺且对函数或属性访问的调用会同步阻止正在等待通信的运行脚本，以便主机代码运行。</span><span class="sxs-lookup"><span data-stu-id="62ab9-308">These are not promises and calls to functions or property access synchronously block running script waiting to communicate cross process for the host code to run.</span></span> <span data-ttu-id="62ab9-309">因此，可能会导致可靠性问题，建议使用上述基于承诺的异步 `window.chrome.webview.hostObjects.{name}` API。</span><span class="sxs-lookup"><span data-stu-id="62ab9-309">Accordingly this can result in reliability issues and it is recommended that you use the promise based asynchronous `window.chrome.webview.hostObjects.{name}` API described above.</span></span>

<span data-ttu-id="62ab9-310">同步主机对象代理和异步主机对象代理都可以代理相同的主机对象。</span><span class="sxs-lookup"><span data-stu-id="62ab9-310">Synchronous host object proxies and asynchronous host object proxies can both proxy the same host object.</span></span> <span data-ttu-id="62ab9-311">一个代理所做的远程更改将反映在同一主机对象的任何其他代理中，无论其他代理和同步还是异步。</span><span class="sxs-lookup"><span data-stu-id="62ab9-311">Remote changes made by one proxy will be reflected in any other proxy of that same host object whether the other proxies and synchronous or asynchronous.</span></span>

<span data-ttu-id="62ab9-312">虽然 JavaScript 在对本机代码的同步调用上被阻止，但该本机代码无法回调到 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="62ab9-312">While JavaScript is blocked on a synchronous call to native code, that native code is unable to call back to JavaScript.</span></span> <span data-ttu-id="62ab9-313">尝试执行此操作将失败，并 HRESULT_FROM_WIN32 （ERROR_POSSIBLE_DEADLOCK）。</span><span class="sxs-lookup"><span data-stu-id="62ab9-313">Attempts to do so will fail with HRESULT_FROM_WIN32(ERROR_POSSIBLE_DEADLOCK).</span></span>

<span data-ttu-id="62ab9-314">主机对象代理是截取所有属性获取、属性集和方法调用的 JavaScript 代理对象。</span><span class="sxs-lookup"><span data-stu-id="62ab9-314">Host object proxies are JavaScript Proxy objects that intercept all property get, property set, and method invocations.</span></span> <span data-ttu-id="62ab9-315">作为函数或对象原型一部分的属性或方法在本地运行。</span><span class="sxs-lookup"><span data-stu-id="62ab9-315">Properties or methods that are a part of the Function or Object prototype are run locally.</span></span> <span data-ttu-id="62ab9-316">此外，数组中的任何属性或方法 `chrome.webview.hostObjects.options.forceLocalProperties` 也将在本地运行。</span><span class="sxs-lookup"><span data-stu-id="62ab9-316">Additionally any property or method in the array `chrome.webview.hostObjects.options.forceLocalProperties` will also be run locally.</span></span> <span data-ttu-id="62ab9-317">这是默认设置，包括在 JavaScript 中具有含义的可选方法 `toJSON` ，如和 `Symbol.toPrimitive` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-317">This defaults to including optional methods that have meaning in JavaScript like `toJSON` and `Symbol.toPrimitive`.</span></span> <span data-ttu-id="62ab9-318">你可以根据需要向此数组添加更多。</span><span class="sxs-lookup"><span data-stu-id="62ab9-318">You can add more to this array as required.</span></span>

<span data-ttu-id="62ab9-319">有一种方法 `chrome.webview.hostObjects.cleanupSome` 可以最大努力垃圾回收主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="62ab9-319">There's a method `chrome.webview.hostObjects.cleanupSome` that will best effort garbage collect host object proxies.</span></span>

<span data-ttu-id="62ab9-320">宿主对象代理还具有以下可在本地运行的方法：</span><span class="sxs-lookup"><span data-stu-id="62ab9-320">Host object proxies additionally have the following methods which run locally:</span></span>

* <span data-ttu-id="62ab9-321">applyHostFunction、getHostProperty、setHostProperty：对主机对象执行方法调用、属性获取或属性设置。</span><span class="sxs-lookup"><span data-stu-id="62ab9-321">applyHostFunction, getHostProperty, setHostProperty: Perform a method invocation, property get, or property set on the host object.</span></span> <span data-ttu-id="62ab9-322">如果存在冲突的本地方法或属性，则可以使用这些属性显式强制在远程运行某个方法或属性。</span><span class="sxs-lookup"><span data-stu-id="62ab9-322">You can use these to explicitly force a method or property to run remotely if there is a conflicting local method or property.</span></span> <span data-ttu-id="62ab9-323">例如， `proxy.toString()` 将对代理对象运行本地 toString 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-323">For instance, `proxy.toString()` will run the local toString method on the proxy object.</span></span> <span data-ttu-id="62ab9-324">而 `proxy.applyHostFunction('toString')` `toString` 是在主机代理对象上运行。</span><span class="sxs-lookup"><span data-stu-id="62ab9-324">But `proxy.applyHostFunction('toString')` runs `toString` on the host proxied object instead.</span></span>

* <span data-ttu-id="62ab9-325">getLocalProperty、setLocalProperty：执行属性 get 或本地设置属性。</span><span class="sxs-lookup"><span data-stu-id="62ab9-325">getLocalProperty, setLocalProperty: Perform property get, or property set locally.</span></span> <span data-ttu-id="62ab9-326">你可以使用这些方法强制获取或设置主机对象代理本身的属性，而不是它所表示的主机对象上的属性。</span><span class="sxs-lookup"><span data-stu-id="62ab9-326">You can use these methods to force getting or setting a property on the host object proxy itself rather than on the host object it represents.</span></span> <span data-ttu-id="62ab9-327">例如， `proxy.unknownProperty` 将获取 `unknownProperty` 从 host 代理对象命名的属性。</span><span class="sxs-lookup"><span data-stu-id="62ab9-327">For instance, `proxy.unknownProperty` will get the property named `unknownProperty` from the host proxied object.</span></span> <span data-ttu-id="62ab9-328">但 `proxy.getLocalProperty('unknownProperty')` 将获取 `unknownProperty` 代理对象本身的属性值。</span><span class="sxs-lookup"><span data-stu-id="62ab9-328">But `proxy.getLocalProperty('unknownProperty')` will get the value of the property `unknownProperty` on the proxy object itself.</span></span>

* <span data-ttu-id="62ab9-329">同步：异步主机对象代理公开同步方法，该方法可为同一主机对象的同步主机对象代理返回承诺。</span><span class="sxs-lookup"><span data-stu-id="62ab9-329">sync: Asynchronous host object proxies expose a sync method which returns a promise for a synchronous host object proxy for the same host object.</span></span> <span data-ttu-id="62ab9-330">例如， `chrome.webview.hostObjects.sample.methodCall()` 返回一个异步主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="62ab9-330">For example, `chrome.webview.hostObjects.sample.methodCall()` returns an asynchronous host object proxy.</span></span> <span data-ttu-id="62ab9-331">可以 `sync` 改为使用该方法获取同步主机对象代理：</span><span class="sxs-lookup"><span data-stu-id="62ab9-331">You can use the `sync` method to obtain a synchronous host object proxy instead:</span></span> `const syncProxy = await chrome.webview.hostObjects.sample.methodCall().sync()`

* <span data-ttu-id="62ab9-332">异步：同步主机对象代理公开一个 async 方法，该方法会阻止并返回同一主机对象的异步主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="62ab9-332">async: Synchronous host object proxies expose an async method which blocks and returns an asynchronous host object proxy for the same host object.</span></span> <span data-ttu-id="62ab9-333">例如， `chrome.webview.hostObjects.sync.sample.methodCall()` 返回同步主机对象代理。</span><span class="sxs-lookup"><span data-stu-id="62ab9-333">For example, `chrome.webview.hostObjects.sync.sample.methodCall()` returns a synchronous host object proxy.</span></span> <span data-ttu-id="62ab9-334">`async`在此块上调用该方法，然后返回同一 host 对象的异步主机对象代理：</span><span class="sxs-lookup"><span data-stu-id="62ab9-334">Calling the `async` method on this blocks and then returns an asynchronous host object proxy for the same host object:</span></span> `const asyncProxy = chrome.webview.hostObjects.sync.sample.methodCall().async()`

* <span data-ttu-id="62ab9-335">然后：异步主机对象代理具有 then 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-335">then: Asynchronous host object proxies have a then method.</span></span> <span data-ttu-id="62ab9-336">这使它们能够可等待。</span><span class="sxs-lookup"><span data-stu-id="62ab9-336">This allows them to be awaitable.</span></span> `then` <span data-ttu-id="62ab9-337">将返回通过主机对象的表示形式解析的承诺。</span><span class="sxs-lookup"><span data-stu-id="62ab9-337">will return a promise that resolves with a representation of the host object.</span></span> <span data-ttu-id="62ab9-338">如果代理表示 JavaScript 文本，则会在本地返回一个副本。</span><span class="sxs-lookup"><span data-stu-id="62ab9-338">If the proxy represents a JavaScript literal then a copy of that is returned locally.</span></span> <span data-ttu-id="62ab9-339">如果代理表示一个函数，则返回非可等待代理。</span><span class="sxs-lookup"><span data-stu-id="62ab9-339">If the proxy represents a function then a non-awaitable proxy is returned.</span></span> <span data-ttu-id="62ab9-340">如果代理表示的 JavaScript 对象混合了文本属性和函数属性，则会将某些属性作为主机对象代理返回该对象的副本。</span><span class="sxs-lookup"><span data-stu-id="62ab9-340">If the proxy represents a JavaScript object with a mix of literal properties and function properties, then the a copy of the object is returned with some properties as host object proxies.</span></span>

<span data-ttu-id="62ab9-341">所有其他属性和方法调用（除了上述远程对象代理方法、forceLocalProperties 列表和函数和对象原型上的属性）都是远程运行的。</span><span class="sxs-lookup"><span data-stu-id="62ab9-341">All other property and method invocations (other than the above Remote object proxy methods, forceLocalProperties list, and properties on Function and Object prototypes) are run remotely.</span></span> <span data-ttu-id="62ab9-342">异步主机对象代理返回表示异步完成远程调用该方法或获取属性的一种承诺。</span><span class="sxs-lookup"><span data-stu-id="62ab9-342">Asynchronous host object proxies return a promise representing asynchronous completion of remotely invoking the method, or getting the property.</span></span> <span data-ttu-id="62ab9-343">在远程操作完成后，承诺将解决该操作的结果值。</span><span class="sxs-lookup"><span data-stu-id="62ab9-343">The promise resolves after the remote operations complete and the promises resolve to the resulting value of the operation.</span></span> <span data-ttu-id="62ab9-344">同步主机对象代理的工作方式类似，但阻止了 JavaScript 执行，并等待远程操作完成。</span><span class="sxs-lookup"><span data-stu-id="62ab9-344">Synchronous host object proxies work similarly but block JavaScript execution and wait for the remote operation to complete.</span></span>

<span data-ttu-id="62ab9-345">在异步主机对象代理上设置属性的工作方式略有不同。</span><span class="sxs-lookup"><span data-stu-id="62ab9-345">Setting a property on an asynchronous host object proxy works slightly differently.</span></span> <span data-ttu-id="62ab9-346">Set 将立即返回，返回值为将设置的值。</span><span class="sxs-lookup"><span data-stu-id="62ab9-346">The set returns immediately and the return value is the value that will be set.</span></span> <span data-ttu-id="62ab9-347">这是 JavaScript 代理对象的要求。</span><span class="sxs-lookup"><span data-stu-id="62ab9-347">This is a requirement of the JavaScript Proxy object.</span></span> <span data-ttu-id="62ab9-348">如果需要异步等待属性设置为 "完成"，请使用 setHostProperty 方法，该方法将返回上述承诺。</span><span class="sxs-lookup"><span data-stu-id="62ab9-348">If you need to asynchronously wait for the property set to complete, use the setHostProperty method which returns a promise as described above.</span></span> <span data-ttu-id="62ab9-349">同步对象属性 set 属性在设置该属性之前同步地阻止。</span><span class="sxs-lookup"><span data-stu-id="62ab9-349">Synchronous object property set property synchronously blocks until the property is set.</span></span>

#### <span data-ttu-id="62ab9-350">AddScriptToExecuteOnDocumentCreatedAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-350">AddScriptToExecuteOnDocumentCreatedAsync</span></span> 

<span data-ttu-id="62ab9-351">将提供的 JavaScript 添加到应在创建全局对象后执行的脚本列表，但在分析 HTML 文档之前和执行 HTML 文档所包含的任何其他脚本之前。</span><span class="sxs-lookup"><span data-stu-id="62ab9-351">Add the provided JavaScript to a list of scripts that should be executed after the global object has been created, but before the HTML document has been parsed and before any other script included by the HTML document is executed.</span></span>

> <span data-ttu-id="62ab9-352">公共异步任务< 字符串 > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)（字符串 javaScript）</span><span class="sxs-lookup"><span data-stu-id="62ab9-352">public async Task< string > [AddScriptToExecuteOnDocumentCreatedAsync](#addscripttoexecuteondocumentcreatedasync)(string javaScript)</span></span>

<span data-ttu-id="62ab9-353">插入的脚本将应用于所有未来的顶级文档和子框架导航，直到使用 RemoveScriptToExecuteOnDocumentCreated 删除。</span><span class="sxs-lookup"><span data-stu-id="62ab9-353">The injected script will apply to all future top level document and child frame navigations until removed with RemoveScriptToExecuteOnDocumentCreated.</span></span> <span data-ttu-id="62ab9-354">这是异步应用的，你必须等待完成处理程序运行，然后才能确保脚本已准备好在将来的导航上执行。</span><span class="sxs-lookup"><span data-stu-id="62ab9-354">This is applied asynchronously and you must wait for the completion handler to run before you can be sure that the script is ready to execute on future navigations.</span></span>

<span data-ttu-id="62ab9-355">请注意，如果 HTML 文档通过[沙盒](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox)属性或[内容安全策略 HTTP 标头](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy)进行了某种类型的沙盒，则会影响在此处运行脚本。</span><span class="sxs-lookup"><span data-stu-id="62ab9-355">Note that if an HTML document has sandboxing of some kind via [sandbox](https://developer.mozilla.org/docs/Web/HTML/Element/iframe#attr-sandbox) properties or the [Content-Security-Policy HTTP header](https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Security-Policy) this will affect the script run here.</span></span> <span data-ttu-id="62ab9-356">例如，如果未设置 "allow-modals" 关键字，则将忽略对该函数的调用 `alert` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-356">So, for example, if the 'allow-modals' keyword is not set then calls to the `alert` function will be ignored.</span></span>

#### <span data-ttu-id="62ab9-357">AddWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="62ab9-357">AddWebResourceRequestedFilter</span></span> 

<span data-ttu-id="62ab9-358">将 URI 和资源上下文筛选器添加到 WebResourceRequested 事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-358">Adds a URI and resource context filter to the WebResourceRequested event.</span></span>

> <span data-ttu-id="62ab9-359">公共 void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)（string Uri，CoreWebView2WebResourceContext ResourceContext）</span><span class="sxs-lookup"><span data-stu-id="62ab9-359">public void [AddWebResourceRequestedFilter](#addwebresourcerequestedfilter)(string uri, CoreWebView2WebResourceContext ResourceContext)</span></span>

<span data-ttu-id="62ab9-360">URI 参数可以是通配符字符串（""：零或更多，'？ '：正好是一）。</span><span class="sxs-lookup"><span data-stu-id="62ab9-360">URI parameter can be a wildcard string ('': zero or more, '?': exactly one).</span></span> <span data-ttu-id="62ab9-361">nullptr 等效于 L ""。</span><span class="sxs-lookup"><span data-stu-id="62ab9-361">nullptr is equivalent to L"".</span></span> <span data-ttu-id="62ab9-362">有关资源上下文筛选器的说明，请参阅 CoreWebView2WebResourceContext enum。</span><span class="sxs-lookup"><span data-stu-id="62ab9-362">See CoreWebView2WebResourceContext enum for description of resource context filters.</span></span>

#### <span data-ttu-id="62ab9-363">CallDevToolsProtocolMethodAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-363">CallDevToolsProtocolMethodAsync</span></span> 

<span data-ttu-id="62ab9-364">调用异步 DevToolsProtocol 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-364">Call an asynchronous DevToolsProtocol method.</span></span>

> <span data-ttu-id="62ab9-365">公共异步任务< 字符串 > [CallDevToolsProtocolMethodAsync](#calldevtoolsprotocolmethodasync)（String 方法名称、字符串 parametersAsJson）</span><span class="sxs-lookup"><span data-stu-id="62ab9-365">public async Task< string > [CallDevToolsProtocolMethodAsync](#calldevtoolsprotocolmethodasync)(string methodName, string parametersAsJson)</span></span>

<span data-ttu-id="62ab9-366">有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。</span><span class="sxs-lookup"><span data-stu-id="62ab9-366">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="62ab9-367">"方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-367">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="62ab9-368">ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。</span><span class="sxs-lookup"><span data-stu-id="62ab9-368">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="62ab9-369">当方法异步完成时，将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-369">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="62ab9-370">将使用方法的返回对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="62ab9-370">Invoke will be called with the method's return object as a JSON string.</span></span>

#### <span data-ttu-id="62ab9-371">CapturePreviewAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-371">CapturePreviewAsync</span></span> 

<span data-ttu-id="62ab9-372">捕获 Web 视图显示的图像。</span><span class="sxs-lookup"><span data-stu-id="62ab9-372">Capture an image of what WebView is displaying.</span></span>

> <span data-ttu-id="62ab9-373">公共异步任务[CapturePreviewAsync](#capturepreviewasync)（CoreWebView2CapturePreviewImageFormat ImageFormat，Stream imageStream）</span><span class="sxs-lookup"><span data-stu-id="62ab9-373">public async Task [CapturePreviewAsync](#capturepreviewasync)(CoreWebView2CapturePreviewImageFormat imageFormat, Stream imageStream)</span></span>

<span data-ttu-id="62ab9-374">指定具有 imageFormat 参数的图像的格式。</span><span class="sxs-lookup"><span data-stu-id="62ab9-374">Specify the format of the image with the imageFormat parameter.</span></span> <span data-ttu-id="62ab9-375">生成的图像二进制数据将写入所提供的 imageStream 参数。</span><span class="sxs-lookup"><span data-stu-id="62ab9-375">The resulting image binary data is written to the provided imageStream parameter.</span></span> <span data-ttu-id="62ab9-376">当 CapturePreview 完成写入流时，将调用所提供的处理程序参数上的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-376">When CapturePreview finishes writing to the stream, the Invoke method on the provided handler parameter is called.</span></span>

#### <span data-ttu-id="62ab9-377">ExecuteScriptAsync</span><span class="sxs-lookup"><span data-stu-id="62ab9-377">ExecuteScriptAsync</span></span> 

<span data-ttu-id="62ab9-378">从在 Web 视图中呈现的当前顶级文档的 javascript 参数中执行 JavaScript 代码。</span><span class="sxs-lookup"><span data-stu-id="62ab9-378">Execute JavaScript code from the javascript parameter in the current top level document rendered in the WebView.</span></span>

> <span data-ttu-id="62ab9-379">公共异步任务< 字符串 > [ExecuteScriptAsync](#executescriptasync)（字符串 javaScript）</span><span class="sxs-lookup"><span data-stu-id="62ab9-379">public async Task< string > [ExecuteScriptAsync](#executescriptasync)(string javaScript)</span></span>

<span data-ttu-id="62ab9-380">这将异步执行，并且在完成后，如果 ExecuteScriptCompletedHandler 参数中提供了处理程序，则将通过评估所提供的 JavaScript 的结果调用其 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-380">This will execute asynchronously and when complete, if a handler is provided in the ExecuteScriptCompletedHandler parameter, its Invoke method will be called with the result of evaluating the provided JavaScript.</span></span> <span data-ttu-id="62ab9-381">结果值是一个 JSON 编码的字符串。</span><span class="sxs-lookup"><span data-stu-id="62ab9-381">The result value is a JSON encoded string.</span></span> <span data-ttu-id="62ab9-382">如果结果未定义、包含引用循环或者其他无法编码到 JSON，则将以字符串 "null" 形式返回 JSON null 值。</span><span class="sxs-lookup"><span data-stu-id="62ab9-382">If the result is undefined, contains a reference cycle, or otherwise cannot be encoded into JSON, the JSON null value will be returned as the string 'null'.</span></span> <span data-ttu-id="62ab9-383">请注意，没有显式返回值的函数将返回 undefined。</span><span class="sxs-lookup"><span data-stu-id="62ab9-383">Note that a function that has no explicit return value returns undefined.</span></span> <span data-ttu-id="62ab9-384">如果执行的脚本引发了未处理的异常，则结果也为 "null"。</span><span class="sxs-lookup"><span data-stu-id="62ab9-384">If the executed script throws an unhandled exception, then the result is also 'null'.</span></span> <span data-ttu-id="62ab9-385">此方法是异步应用的。</span><span class="sxs-lookup"><span data-stu-id="62ab9-385">This method is applied asynchronously.</span></span> <span data-ttu-id="62ab9-386">如果在导航过程中 NavigationStarting 事件后调用该方法，则会在加载新文档时在新文档中执行该脚本，同时引发 ContentLoading。</span><span class="sxs-lookup"><span data-stu-id="62ab9-386">If the method is called after NavigationStarting event during a navigation, the script will be executed in the new document when loading it, around the time ContentLoading is fired.</span></span> <span data-ttu-id="62ab9-387">即使 IsScriptEnabled 设置为 FALSE，ExecuteScript 仍可正常工作。</span><span class="sxs-lookup"><span data-stu-id="62ab9-387">ExecuteScript will work even if IsScriptEnabled is set to FALSE.</span></span>

#### <span data-ttu-id="62ab9-388">GetDevToolsProtocolEventReceiver</span><span class="sxs-lookup"><span data-stu-id="62ab9-388">GetDevToolsProtocolEventReceiver</span></span> 

<span data-ttu-id="62ab9-389">获取允许你订阅 DevTools 协议事件的 DevTools 协议事件接收器。</span><span class="sxs-lookup"><span data-stu-id="62ab9-389">Get a DevTools Protocol event receiver that allows you to subscribe to a DevTools Protocol event.</span></span>

> <span data-ttu-id="62ab9-390">公共 CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)（string 事件）</span><span class="sxs-lookup"><span data-stu-id="62ab9-390">public CoreWebView2DevToolsProtocolEventReceiver [GetDevToolsProtocolEventReceiver](#getdevtoolsprotocoleventreceiver)(string eventName)</span></span>

<span data-ttu-id="62ab9-391">有关可用方法的列表和说明，请参阅[DevTools 协议查看器](https://aka.ms/DevToolsProtocolDocs)。</span><span class="sxs-lookup"><span data-stu-id="62ab9-391">See the [DevTools Protocol Viewer](https://aka.ms/DevToolsProtocolDocs) for a list and description of available methods.</span></span> <span data-ttu-id="62ab9-392">"方法名称" 参数是采用格式的方法的完整名称 `{domain}.{method}` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-392">The methodName parameter is the full name of the method in the format `{domain}.{method}`.</span></span> <span data-ttu-id="62ab9-393">ParametersAsJson 参数是一个 JSON 格式的字符串，其中包含对应方法的参数。</span><span class="sxs-lookup"><span data-stu-id="62ab9-393">The parametersAsJson parameter is a JSON formatted string containing the parameters for the corresponding method.</span></span> <span data-ttu-id="62ab9-394">当方法异步完成时，将调用处理程序的 Invoke 方法。</span><span class="sxs-lookup"><span data-stu-id="62ab9-394">The handler's Invoke method will be called when the method asynchronously completes.</span></span> <span data-ttu-id="62ab9-395">将使用方法的返回对象作为 JSON 字符串调用调用。</span><span class="sxs-lookup"><span data-stu-id="62ab9-395">Invoke will be called with the method's return object as a JSON string.</span></span>

#### <span data-ttu-id="62ab9-396">GoBack</span><span class="sxs-lookup"><span data-stu-id="62ab9-396">GoBack</span></span> 

<span data-ttu-id="62ab9-397">将 Web 视图导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="62ab9-397">Navigates the WebView to the previous page in the navigation history.</span></span>

> <span data-ttu-id="62ab9-398">公共 void [GoBack](#goback)（）</span><span class="sxs-lookup"><span data-stu-id="62ab9-398">public void [GoBack](#goback)()</span></span>

#### <span data-ttu-id="62ab9-399">GoForward</span><span class="sxs-lookup"><span data-stu-id="62ab9-399">GoForward</span></span> 

<span data-ttu-id="62ab9-400">将 Web 视图导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="62ab9-400">Navigates the WebView to the next page in the navigation history.</span></span>

> <span data-ttu-id="62ab9-401">公共 void [GoForward](#goforward)（）</span><span class="sxs-lookup"><span data-stu-id="62ab9-401">public void [GoForward](#goforward)()</span></span>

#### <span data-ttu-id="62ab9-402">导航</span><span class="sxs-lookup"><span data-stu-id="62ab9-402">Navigate</span></span> 

<span data-ttu-id="62ab9-403">导致将顶级文档导航到指定的 URI。</span><span class="sxs-lookup"><span data-stu-id="62ab9-403">Cause a navigation of the top level document to the specified URI.</span></span>

> <span data-ttu-id="62ab9-404">公共 void[导航](#navigate)（字符串 uri）</span><span class="sxs-lookup"><span data-stu-id="62ab9-404">public void [Navigate](#navigate)(string uri)</span></span>

<span data-ttu-id="62ab9-405">有关详细信息，请参阅导航事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-405">See the navigation events for more information.</span></span> <span data-ttu-id="62ab9-406">请注意，这将启动导航，并且相应的 NavigationStarting 事件将在此导航调用完成后的某个时间触发。</span><span class="sxs-lookup"><span data-stu-id="62ab9-406">Note that this starts a navigation and the corresponding NavigationStarting event will fire sometime after this Navigate call completes.</span></span>

#### <span data-ttu-id="62ab9-407">NavigateToString</span><span class="sxs-lookup"><span data-stu-id="62ab9-407">NavigateToString</span></span> 

<span data-ttu-id="62ab9-408">启动作为新文档的源 HTML 的 htmlContent 导航。</span><span class="sxs-lookup"><span data-stu-id="62ab9-408">Initiates a navigation to htmlContent as source HTML of a new document.</span></span>

> <span data-ttu-id="62ab9-409">公共 void [NavigateToString](#navigatetostring)（string htmlContent）</span><span class="sxs-lookup"><span data-stu-id="62ab9-409">public void [NavigateToString](#navigatetostring)(string htmlContent)</span></span>

<span data-ttu-id="62ab9-410">HtmlContent 参数不能大于 2 MB 的字符。</span><span class="sxs-lookup"><span data-stu-id="62ab9-410">The htmlContent parameter may not be larger than 2 MB of characters.</span></span> <span data-ttu-id="62ab9-411">新页面的来源将显示为 "空白"。</span><span class="sxs-lookup"><span data-stu-id="62ab9-411">The origin of the new page will be about:blank.</span></span>

#### <span data-ttu-id="62ab9-412">OpenDevToolsWindow</span><span class="sxs-lookup"><span data-stu-id="62ab9-412">OpenDevToolsWindow</span></span> 

<span data-ttu-id="62ab9-413">在 Web 视图中打开当前文档的 DevTools 窗口。</span><span class="sxs-lookup"><span data-stu-id="62ab9-413">Opens the DevTools window for the current document in the WebView.</span></span>

> <span data-ttu-id="62ab9-414">公共 void [OpenDevToolsWindow](#opendevtoolswindow)（）</span><span class="sxs-lookup"><span data-stu-id="62ab9-414">public void [OpenDevToolsWindow](#opendevtoolswindow)()</span></span>

<span data-ttu-id="62ab9-415">如果在 DevTools 窗口已打开时调用，则不执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="62ab9-415">Does nothing if called when the DevTools window is already open.</span></span>

#### <span data-ttu-id="62ab9-416">PostWebMessageAsJson</span><span class="sxs-lookup"><span data-stu-id="62ab9-416">PostWebMessageAsJson</span></span> 

<span data-ttu-id="62ab9-417">将指定的 webMessage 发布到此 Web 视图中的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="62ab9-417">Post the specified webMessage to the top level document in this WebView.</span></span>

> <span data-ttu-id="62ab9-418">公共 void [PostWebMessageAsJson](#postwebmessageasjson)（string webMessageAsJson）</span><span class="sxs-lookup"><span data-stu-id="62ab9-418">public void [PostWebMessageAsJson](#postwebmessageasjson)(string webMessageAsJson)</span></span>

<span data-ttu-id="62ab9-419">将激发顶级文档的 "chrome" 消息事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-419">The top level document's window.chrome.webview's message event fires.</span></span> <span data-ttu-id="62ab9-420">该文档中的 JavaScript 可以通过以下方式订阅和取消订阅该事件：</span><span class="sxs-lookup"><span data-stu-id="62ab9-420">JavaScript in that document may subscribe and unsubscribe to the event via the following:</span></span>

```
window.chrome.webview.addEventListener('message', handler)
window.chrome.webview.removeEventListener('message', handler)
```

<span data-ttu-id="62ab9-421">事件参数是的实例 `MessageEvent` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-421">The event args is an instance of `MessageEvent`.</span></span> <span data-ttu-id="62ab9-422">CoreWebView2Settings IsWebMessageEnabled 设置必须为 true，否则此方法将失败，并 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="62ab9-422">The CoreWebView2Settings.IsWebMessageEnabled setting must be true or this method will fail with E_INVALIDARG.</span></span> <span data-ttu-id="62ab9-423">事件参数的数据属性是将其作为 JSON 字符串分析到 JavaScript 对象中的 webMessage 字符串参数。</span><span class="sxs-lookup"><span data-stu-id="62ab9-423">The event arg's data property is the webMessage string parameter parsed as a JSON string into a JavaScript object.</span></span> <span data-ttu-id="62ab9-424">事件 arg 的 source 属性是对该对象的引用 `window.chrome.webview` 。</span><span class="sxs-lookup"><span data-stu-id="62ab9-424">The event arg's source property is a reference to the `window.chrome.webview` object.</span></span> <span data-ttu-id="62ab9-425">有关从 web 视图中的 HTML 文档发送邮件到主机的信息，请参阅 SetWebMessageReceivedEventHandler。</span><span class="sxs-lookup"><span data-stu-id="62ab9-425">See SetWebMessageReceivedEventHandler for information on sending messages from the HTML document in the webview to the host.</span></span> <span data-ttu-id="62ab9-426">此消息将异步发送。</span><span class="sxs-lookup"><span data-stu-id="62ab9-426">This message is sent asynchronously.</span></span> <span data-ttu-id="62ab9-427">如果在将邮件发布到页面之前发生导航，则不会发送邮件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-427">If a navigation occurs before the message is posted to the page, then the message will not be sent.</span></span>

#### <span data-ttu-id="62ab9-428">PostWebMessageAsString</span><span class="sxs-lookup"><span data-stu-id="62ab9-428">PostWebMessageAsString</span></span> 

<span data-ttu-id="62ab9-429">这是一个帮助程序，用于发布一个简单字符串的消息，而不是 JavaScript 对象的 JSON 字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="62ab9-429">This is a helper for posting a message that is a simple string rather than a JSON string representation of a JavaScript object.</span></span>

> <span data-ttu-id="62ab9-430">公共 void [PostWebMessageAsString](#postwebmessageasstring)（string webMessageAsString）</span><span class="sxs-lookup"><span data-stu-id="62ab9-430">public void [PostWebMessageAsString](#postwebmessageasstring)(string webMessageAsString)</span></span>

<span data-ttu-id="62ab9-431">此行为与 PostWebMessageAsJson 完全相同，但 `window.chrome.webview` 消息事件参数的 data 属性将是与 webMessageAsString 具有相同值的字符串。</span><span class="sxs-lookup"><span data-stu-id="62ab9-431">This behaves in exactly the same manner as PostWebMessageAsJson but the `window.chrome.webview` message event arg's data property will be a string with the same value as webMessageAsString.</span></span> <span data-ttu-id="62ab9-432">如果想要通过简单的字符串而不是 JSON 对象进行通信，请使用此操作，而不是 PostWebMessageAsJson。</span><span class="sxs-lookup"><span data-stu-id="62ab9-432">Use this instead of PostWebMessageAsJson if you want to communicate via simple strings rather than JSON objects.</span></span>

#### <span data-ttu-id="62ab9-433">重载</span><span class="sxs-lookup"><span data-stu-id="62ab9-433">Reload</span></span> 

<span data-ttu-id="62ab9-434">重新加载当前页面。</span><span class="sxs-lookup"><span data-stu-id="62ab9-434">Reload the current page.</span></span>

> <span data-ttu-id="62ab9-435">public void [Reload](#reload)（）</span><span class="sxs-lookup"><span data-stu-id="62ab9-435">public void [Reload](#reload)()</span></span>

<span data-ttu-id="62ab9-436">这类似于导航到当前顶级文档的 URI，包括触发和遵从 HTTP 缓存中任何条目的所有导航事件。</span><span class="sxs-lookup"><span data-stu-id="62ab9-436">This is similar to navigating to the URI of current top level document including all navigation events firing and respecting any entries in the HTTP cache.</span></span> <span data-ttu-id="62ab9-437">但是，将不会修改后退/前进历史记录。</span><span class="sxs-lookup"><span data-stu-id="62ab9-437">But, the back/forward history will not be modified.</span></span>

#### <span data-ttu-id="62ab9-438">RemoveHostObjectFromScript</span><span class="sxs-lookup"><span data-stu-id="62ab9-438">RemoveHostObjectFromScript</span></span> 

<span data-ttu-id="62ab9-439">删除名称指定的主机对象，以便从 Web 视图中的 JavaScript 代码无法再访问该对象。</span><span class="sxs-lookup"><span data-stu-id="62ab9-439">Remove the host object specified by the name so that it is no longer accessible from JavaScript code in the WebView.</span></span>

> <span data-ttu-id="62ab9-440">公共 void [RemoveHostObjectFromScript](#removehostobjectfromscript)（字符串名称）</span><span class="sxs-lookup"><span data-stu-id="62ab9-440">public void [RemoveHostObjectFromScript](#removehostobjectfromscript)(string name)</span></span>

<span data-ttu-id="62ab9-441">当新的访问尝试将被拒绝时，如果 Web 视图中的 JavaScript 代码已获得该对象，则 JavaScript 代码将继续具有对该对象的访问权限。</span><span class="sxs-lookup"><span data-stu-id="62ab9-441">While new access attempts will be denied, if the object is already obtained by JavaScript code in the WebView, the JavaScript code will continue to have access to that object.</span></span> <span data-ttu-id="62ab9-442">为已删除或从未添加的名称调用此方法将失败。</span><span class="sxs-lookup"><span data-stu-id="62ab9-442">Calling this method for a name that is already removed or never added will fail.</span></span>

#### <span data-ttu-id="62ab9-443">RemoveScriptToExecuteOnDocumentCreated</span><span class="sxs-lookup"><span data-stu-id="62ab9-443">RemoveScriptToExecuteOnDocumentCreated</span></span> 

<span data-ttu-id="62ab9-444">删除通过 AddScriptToExecuteOnDocumentCreated 添加的相应 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="62ab9-444">Remove the corresponding JavaScript added via AddScriptToExecuteOnDocumentCreated.</span></span>

> <span data-ttu-id="62ab9-445">公共 void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)（字符串 id）</span><span class="sxs-lookup"><span data-stu-id="62ab9-445">public void [RemoveScriptToExecuteOnDocumentCreated](#removescripttoexecuteondocumentcreated)(string id)</span></span>

#### <span data-ttu-id="62ab9-446">RemoveWebResourceRequestedFilter</span><span class="sxs-lookup"><span data-stu-id="62ab9-446">RemoveWebResourceRequestedFilter</span></span> 

<span data-ttu-id="62ab9-447">删除以前为 WebResourceRequested 事件添加的匹配 WebResource 筛选器。</span><span class="sxs-lookup"><span data-stu-id="62ab9-447">Removes a matching WebResource filter that was previously added for the WebResourceRequested event.</span></span>

> <span data-ttu-id="62ab9-448">公共 void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)（string Uri， [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) ResourceContext）</span><span class="sxs-lookup"><span data-stu-id="62ab9-448">public void [RemoveWebResourceRequestedFilter](#removewebresourcerequestedfilter)(string uri, [CoreWebView2WebResourceContext](./namespace-microsoft-web-webview2-core.md) ResourceContext)</span></span>

<span data-ttu-id="62ab9-449">如果多次添加相同的筛选器，则需要将其删除多次，才能使删除生效。</span><span class="sxs-lookup"><span data-stu-id="62ab9-449">If the same filter was added multiple times, then it will need to be removed as many times as it was added for the removal to be effective.</span></span> <span data-ttu-id="62ab9-450">返回从未添加的筛选器 E_INVALIDARG。</span><span class="sxs-lookup"><span data-stu-id="62ab9-450">Returns E_INVALIDARG for a filter that was never added.</span></span>

#### <span data-ttu-id="62ab9-451">停止</span><span class="sxs-lookup"><span data-stu-id="62ab9-451">Stop</span></span> 

<span data-ttu-id="62ab9-452">停止所有导航和挂起的资源提取。</span><span class="sxs-lookup"><span data-stu-id="62ab9-452">Stop all navigations and pending resource fetches.</span></span>

> <span data-ttu-id="62ab9-453">public void [Stop](#stop)（）</span><span class="sxs-lookup"><span data-stu-id="62ab9-453">public void [Stop](#stop)()</span></span>

<span data-ttu-id="62ab9-454">不会停止脚本。</span><span class="sxs-lookup"><span data-stu-id="62ab9-454">Does not stop scripts.</span></span>

