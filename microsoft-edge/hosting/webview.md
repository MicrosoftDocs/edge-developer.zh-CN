---
description: 通过 web 视图（EdgeHTML）控件在 Windows 10 应用中托管 web 内容
title: 适用于 Windows 10 应用的 Microsoft Edge Web 视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: x-ms-web 视图、MSHTMLWebViewElement、web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: 08efb1bb87877e0b11cbc3bee1061f9be6c9ab3f
ms.sourcegitcommit: 831fc41ea347e2d1160b1804fb5e5a427dc3070d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "10629547"
---
# <span data-ttu-id="f17f5-104">适用于 Windows 10 应用的 Web 视图（EdgeHTML）</span><span class="sxs-lookup"><span data-stu-id="f17f5-104">WebView (EdgeHTML) for Windows 10 apps</span></span>

<span data-ttu-id="f17f5-105">Web 视图（EdgeHTML）控件使你能够在 Windows 10 应用中托管 web 内容。</span><span class="sxs-lookup"><span data-stu-id="f17f5-105">The WebView (EdgeHTML) control enables you to host web content in your Windows 10 app.</span></span> 

<span data-ttu-id="f17f5-106">对于基于 JavaScript 的 Windows 10 应用，你可以将其用作 XAML 元素（对于[通用 Windows 平台（UWP）应用](/uwp/api/Windows.UI.Xaml.Controls.WebView)和[Windows 窗体和 WPF 桌面应用程序](/windows/communitytoolkit/controls/wpf-winforms/webview)）或 HTML 元素（x ms-web 视图）/dom 对象（MSHTMLWebViewElement），如下所述。</span><span class="sxs-lookup"><span data-stu-id="f17f5-106">You can use it as a XAML element (for [Universal Windows Platform (UWP) apps](/uwp/api/Windows.UI.Xaml.Controls.WebView) and [Windows Forms and WPF desktop applications](/windows/communitytoolkit/controls/wpf-winforms/webview)), or an HTML element (x-ms-webview)/DOM object (MSHTMLWebViewElement) for JavaScript-based Windows 10 apps, as described here.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="f17f5-107">事件</span><span class="sxs-lookup"><span data-stu-id="f17f5-107">Events</span></span>**](#events) | <span data-ttu-id="f17f5-108">[departingFocus](#departingfocus)、 [MSWebViewContainsFullScreenElementChanged](#mswebviewcontainsfullscreenelementchanged)、 [MSWebViewContentLoading](#mswebviewcontentloading)、 [MSWebViewDOMContentLoaded](#mswebviewdomcontentloaded)、 [MSWebViewFrameContentLoading](#mswebviewframecontentloading)、 [MSWebViewFrameDOMContentLoaded](#mswebviewframedomcontentloaded)、 [MSWebViewFrameNavigationCompleted、MSWebViewFrameNavigationStarting](#mswebviewframenavigationcompleted) [、MSWebViewLongRunningScriptDetected](#mswebviewframenavigationstarting)、 [MSWebViewNavigationCompleted](#mswebviewnavigationcompleted)、 [MSWebViewNavigationStarting](#mswebviewnavigationstarting)、 [MSWebViewNewWindowRequested](#mswebviewnewwindowrequested)、 [MSWebViewPermissionRequested](#mswebviewpermissionrequested)、 [MSWebViewProcessExited、MSWebViewWebResourceRequested](#mswebviewprocessexited) [、MSWebViewScriptNotify](#mswebviewwebresourcerequested) [、MSWebViewUnsafeContentWarningDisplaying](#mswebviewscriptnotify) [、MSWebViewUnsupportedUriSchemeIdentified](#mswebviewunsafecontentwarningdisplaying) [、MSWebViewUnviewableContentIdentified](#mswebviewunsupportedurischemeidentified)、、、 [、、](#mswebviewunviewablecontentidentified) 、 [MSWebViewLongRunningScriptDetected](#mswebviewlongrunningscriptdetected)</span><span class="sxs-lookup"><span data-stu-id="f17f5-108">[departingFocus](#departingfocus), [MSWebViewContainsFullScreenElementChanged](#mswebviewcontainsfullscreenelementchanged), [MSWebViewContentLoading](#mswebviewcontentloading), [MSWebViewDOMContentLoaded](#mswebviewdomcontentloaded), [MSWebViewFrameContentLoading](#mswebviewframecontentloading), [MSWebViewFrameDOMContentLoaded](#mswebviewframedomcontentloaded), [MSWebViewFrameNavigationCompleted](#mswebviewframenavigationcompleted), [MSWebViewFrameNavigationStarting](#mswebviewframenavigationstarting), [MSWebViewLongRunningScriptDetected](#mswebviewlongrunningscriptdetected), [MSWebViewNavigationCompleted](#mswebviewnavigationcompleted), [MSWebViewNavigationStarting](#mswebviewnavigationstarting), [MSWebViewNewWindowRequested](#mswebviewnewwindowrequested), [MSWebViewPermissionRequested](#mswebviewpermissionrequested), [MSWebViewProcessExited](#mswebviewprocessexited), [MSWebViewWebResourceRequested](#mswebviewwebresourcerequested), [MSWebViewScriptNotify](#mswebviewscriptnotify), [MSWebViewUnsafeContentWarningDisplaying](#mswebviewunsafecontentwarningdisplaying), [MSWebViewUnsupportedUriSchemeIdentified](#mswebviewunsupportedurischemeidentified), [MSWebViewUnviewableContentIdentified](#mswebviewunviewablecontentidentified)</span></span>
| [**<span data-ttu-id="f17f5-109">方法</span><span class="sxs-lookup"><span data-stu-id="f17f5-109">Methods</span></span>**](#methods) | <span data-ttu-id="f17f5-110">[webview.addweballowedobject](#addweballowedobject)、 [buildlocalStreamUri](#buildlocalstreamuri)、 [capturePreviewToBlobAsync](#capturepreviewtoblobasync)、 [captureSelectedContentToDataPackageAsync](#captureselectedcontenttodatapackageasync)、 [invokeScriptAsync](#invokescriptasync)、 [getDeferredPermissionRequests](#getdeferredpermissionrequests)、 [getDeferredPermissionRequestById](#getdeferredpermissionrequestbyid)、 [goBack](#goback)、 [goForward](#goforward)、[导航](#navigate)、 [navigateFocus](#navigatefocus)、 [navigateTolocalStreamUri](#navigatetolocalstreamuri)、 [navigateToString](#navigatetostring)、 [navigateWithHttpRequestMessage](#navigatewithhttprequestmessage)、 [refresh](#refresh)、 [stop](#stop)</span><span class="sxs-lookup"><span data-stu-id="f17f5-110">[addWebAllowedObject](#addweballowedobject), [buildlocalStreamUri](#buildlocalstreamuri), [capturePreviewToBlobAsync](#capturepreviewtoblobasync), [captureSelectedContentToDataPackageAsync](#captureselectedcontenttodatapackageasync), [invokeScriptAsync](#invokescriptasync), [getDeferredPermissionRequests](#getdeferredpermissionrequests), [getDeferredPermissionRequestById](#getdeferredpermissionrequestbyid), [goBack](#goback), [goForward](#goforward), [navigate](#navigate), [navigateFocus](#navigatefocus), [navigateTolocalStreamUri](#navigatetolocalstreamuri), [navigateToString](#navigatetostring), [navigateWithHttpRequestMessage](#navigatewithhttprequestmessage), [refresh](#refresh), [stop](#stop)</span></span> |
| [**<span data-ttu-id="f17f5-111">属性</span><span class="sxs-lookup"><span data-stu-id="f17f5-111">Properties</span></span>**](#properties) | <span data-ttu-id="f17f5-112">[canGoBack](#cangoback)、 [canGoForward](#cangoforward)、 [containsFullScreenElement](#containsfullscreenelement)、 [documentTitle](#documenttitle)、 [height](#height)、 [process](#process)、 [settings](#settings)、 [src](#src)、 [width](#width)</span><span class="sxs-lookup"><span data-stu-id="f17f5-112">[canGoBack](#cangoback), [canGoForward](#cangoforward), [containsFullScreenElement](#containsfullscreenelement), [documentTitle](#documenttitle), [height](#height), [process](#process), [settings](#settings), [src](#src), [width](#width)</span></span> |

## <span data-ttu-id="f17f5-113">语法</span><span class="sxs-lookup"><span data-stu-id="f17f5-113">Syntax</span></span>

```js
// Feature detect for webview support
if (MSHTMLWebViewElement) {
    let wv = document.createElement('x-ms-webview'); // Use CSS to set width, height and other styles
    wv.navigate("https://www.example.com");
    document.body.appendChild(wv);
}
```

## <span data-ttu-id="f17f5-114">备注</span><span class="sxs-lookup"><span data-stu-id="f17f5-114">Remarks</span></span>

### <span data-ttu-id="f17f5-115">Web 视图与 iframe</span><span class="sxs-lookup"><span data-stu-id="f17f5-115">WebView versus iframe</span></span>

<span data-ttu-id="f17f5-116">与标准 HTML [iframe](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)元素一样，你可以使用 web 视图通过来自你的应用包的 HTTP 和本地页面（*ms-appx-web//*）加载远程页面。</span><span class="sxs-lookup"><span data-stu-id="f17f5-116">Like a standard HTML [iframe](https://developer.mozilla.org/docs/Web/HTML/Element/iframe) element,  you can use WebView to load remote pages over HTTP and local pages (*ms-appx-web:///*) from your app package.</span></span> <span data-ttu-id="f17f5-117">但是，Web 视图还可以：</span><span class="sxs-lookup"><span data-stu-id="f17f5-117">However, the WebView can also:</span></span>

 - <span data-ttu-id="f17f5-118">从你的[ApplicationData](/uwp/api/Windows.Storage.ApplicationData) （本地、漫游、临时）文件夹（*ms-appdata///*）和[内存中流](/microsoft-edge/hosting/webview#buildlocalstreamuri)（*ms-stream*：///）加载页面和资源</span><span class="sxs-lookup"><span data-stu-id="f17f5-118">Load pages and resources from your [ApplicationData](/uwp/api/Windows.Storage.ApplicationData) (local, roaming, temp) folders (*ms-appdata:///*) and [in-memory streams](/microsoft-edge/hosting/webview#buildlocalstreamuri) (*ms-local-stream:///*)</span></span>

 - <span data-ttu-id="f17f5-119">提供类似浏览器的控件：用于在导航历史记录中[后退](#goback)和[前进](#goforward)以及[停止](#stop)或[刷新](#refresh)当前页。</span><span class="sxs-lookup"><span data-stu-id="f17f5-119">Provide browser-like controls: for going [back](#goback) and [forward](#goforward) in navigation history, and [stopping](#stop) or [refreshing](#refresh) the current page.</span></span> 

 - <span data-ttu-id="f17f5-120">[捕获 web 内容的屏幕截图](#capturepreviewtoblobasync)，以便轻松实现 Windows 10 应用[共享](/windows/uwp/app-to-app/share-data)合约。</span><span class="sxs-lookup"><span data-stu-id="f17f5-120">[Capture screenshots of web content](#capturepreviewtoblobasync) making it easy to implement the Windows 10 app [Share](/windows/uwp/app-to-app/share-data) contract.</span></span>

 - <span data-ttu-id="f17f5-121">允许在 web 视图内运行的 JavaScript 代码将自定义事件（[MSWebViewScriptNotify](#mswebviewscriptnotify)）提升到你的应用，并允许你的应用在 web 视图（[invokeScriptAsync](#invokescriptasync)）内运行 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="f17f5-121">Allow JavaScript code running within a webview to raise custom events ([MSWebViewScriptNotify](#mswebviewscriptnotify)) to your app, and allow your app to run JavaScript within the webview ([invokeScriptAsync](#invokescriptasync)).</span></span>

 - <span data-ttu-id="f17f5-122">向您提供微调的 web 视图内容事件：</span><span class="sxs-lookup"><span data-stu-id="f17f5-122">Provide you with fine-tuned webview content events:</span></span>
    
    <span data-ttu-id="f17f5-123">Web 视图 DOM 事件</span><span class="sxs-lookup"><span data-stu-id="f17f5-123">WebView DOM event</span></span> | <span data-ttu-id="f17f5-124">描述</span><span class="sxs-lookup"><span data-stu-id="f17f5-124">Description</span></span>
    --------- | ------
    [<span data-ttu-id="f17f5-125">MSWebViewNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="f17f5-125">MSWebViewNavigationStarting</span></span>](#mswebviewnavigationstarting) | <span data-ttu-id="f17f5-126">指示 Web 视图正在开始导航</span><span class="sxs-lookup"><span data-stu-id="f17f5-126">Indicates the WebView is starting to navigate</span></span>
    [<span data-ttu-id="f17f5-127">MSWebViewContentLoading</span><span class="sxs-lookup"><span data-stu-id="f17f5-127">MSWebViewContentLoading</span></span>](#mswebviewcontentloading) | <span data-ttu-id="f17f5-128">HTML 内容已下载并正在加载到控件中</span><span class="sxs-lookup"><span data-stu-id="f17f5-128">The HTML content is downloaded and is being loaded into the control</span></span>
    [<span data-ttu-id="f17f5-129">MSWebViewDOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="f17f5-129">MSWebViewDOMContentLoaded</span></span>](#mswebviewdomcontentloaded) | <span data-ttu-id="f17f5-130">指示主 DOM 元素已完成加载</span><span class="sxs-lookup"><span data-stu-id="f17f5-130">Indicates that the main DOM elements have finished loading</span></span>
    [<span data-ttu-id="f17f5-131">MSWebViewNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="f17f5-131">MSWebViewNavigationCompleted</span></span>](#mswebviewnavigationcompleted) | <span data-ttu-id="f17f5-132">指示导航已完成，并呈现所有媒体元素</span><span class="sxs-lookup"><span data-stu-id="f17f5-132">Indicates the navigation is complete, and all media elements are rendered</span></span>
    [<span data-ttu-id="f17f5-133">MSWebViewUnviewableContentIdentified</span><span class="sxs-lookup"><span data-stu-id="f17f5-133">MSWebViewUnviewableContentIdentified</span></span>](#mswebviewunviewablecontentidentified) | <span data-ttu-id="f17f5-134">Web 视图发现内容不是 HTML</span><span class="sxs-lookup"><span data-stu-id="f17f5-134">The WebView found the content was not HTML</span></span>
    [<span data-ttu-id="f17f5-135">UnsafeContentWarningDisplaying</span><span class="sxs-lookup"><span data-stu-id="f17f5-135">UnsafeContentWarningDisplaying</span></span>](#mswebviewunsafecontentwarningdisplaying) | <span data-ttu-id="f17f5-136">Web 视图将显示一个警告页面，显示 Windows *SmartScreen 筛选器*报告为不安全的内容。</span><span class="sxs-lookup"><span data-stu-id="f17f5-136">The WebView shows a warning page for content that was reported as unsafe by Windows *SmartScreen Filter*.</span></span>

    <span data-ttu-id="f17f5-137">...包括在 Web 视图内加载的 iframe 内容的相应[事件](#events)（如[MSWebView**Frame**NavigationStarting](#mswebviewframenavigationstarting)等。）</span><span class="sxs-lookup"><span data-stu-id="f17f5-137">...including corresponding [events](#events) for iframe content loaded within a WebView (such as [MSWebView**Frame**NavigationStarting](#mswebviewframenavigationstarting) and so on.)</span></span>

### <span data-ttu-id="f17f5-138">打印</span><span class="sxs-lookup"><span data-stu-id="f17f5-138">Printing</span></span>

<span data-ttu-id="f17f5-139">打印使用 JavaScript 的 Windows 应用时，将在 `<x-ms-webview>` 打印之前将标记转换为 `<iframe>` 标记。</span><span class="sxs-lookup"><span data-stu-id="f17f5-139">When a Windows app using JavaScript is printed, the `<x-ms-webview>` tags are transformed into `<iframe>` tags before printing.</span></span> <span data-ttu-id="f17f5-140">除了屏幕上显示屏幕和为打印呈现的一般区别之外，应用于元素的 CSS 样式 `<iframe>` 也适用于 `<iframe>` 转换的 `<x-ms-webview>` 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-140">Besides the normal difference between displaying on screen and rendered for print, CSS styles applied to `<iframe>` elements are then applicable to the `<iframe>` transformed from `<x-ms-webview>`.</span></span>

### <span data-ttu-id="f17f5-141">服务工作人员</span><span class="sxs-lookup"><span data-stu-id="f17f5-141">Service workers</span></span>

<span data-ttu-id="f17f5-142">从[2018 年10月的更新](/windows/uwp/whats-new/windows-10-build-17763)（EdgeHTML 18）开始， [web 视图控件支持服务工作人员](/microsoft-edge/dev-guide#service-workers)（除了 Microsoft Edge 浏览器和带有 JavaScript 的 Windows 10 应用）。</span><span class="sxs-lookup"><span data-stu-id="f17f5-142">Starting with the [Windows 10 October 2018 Update](/windows/uwp/whats-new/windows-10-build-17763) (EdgeHTML 18), [service workers are supported in the WebView control](/microsoft-edge/dev-guide#service-workers) (in addition to the Microsoft Edge browser and Windows 10 apps with JavaScript).</span></span>

<span data-ttu-id="f17f5-143">x64 应用体系结构需要中立（任何 CPU）或 x64 程序包，因为 WoW64 进程不支持服务工作人员。</span><span class="sxs-lookup"><span data-stu-id="f17f5-143">x64 app architectures require Neutral (Any CPU) or x64 packages, as service workers are not supported in WoW64 processes.</span></span> <span data-ttu-id="f17f5-144">（为节省磁盘空间，所需 Dll 的 WoW 版本不是本机包含在 Windows 中。）</span><span class="sxs-lookup"><span data-stu-id="f17f5-144">(To conserve disk space, the WoW version of the required DLLs are not natively included in Windows.)</span></span>

### <span data-ttu-id="f17f5-145">线程模型和可靠性</span><span class="sxs-lookup"><span data-stu-id="f17f5-145">Threading model and reliability</span></span>

<span data-ttu-id="f17f5-146">通过标记创建 Web 视图 `document.createElement("x-ms-webview")` 或通过标记创建 web 视图 `<x-ms-webview>` 在应用进程中的新唯一线程上创建 web 视图。</span><span class="sxs-lookup"><span data-stu-id="f17f5-146">Creating a WebView via `document.createElement("x-ms-webview")` or via `<x-ms-webview>` markup creates a WebView on a new unique thread in the app's process.</span></span> <span data-ttu-id="f17f5-147">在新的唯一线程上运行意味着来自一个 Web 视图的长时间运行脚本无法挂起应用或其他 WebViews。</span><span class="sxs-lookup"><span data-stu-id="f17f5-147">Running on a new unique thread means that long running script from one WebView is unable to hang the app or other WebViews.</span></span> <span data-ttu-id="f17f5-148">通过构造函数创建 Web 视图 `new MSWebView()` 在单独的 Web 视图进程中创建 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="f17f5-148">Creating a WebView via the `new MSWebView()` constructor creates a WebView in a separate WebView process.</span></span> <span data-ttu-id="f17f5-149">在唯一进程中运行意味着除了对长时间运行的脚本进行保护之外，应用还会受到阻止 web 视图进程的 web 内容的保护。</span><span class="sxs-lookup"><span data-stu-id="f17f5-149">Running in a unique process means that in addition to protection from long running script, the app is also protected from web content that crashes the WebView process.</span></span> <span data-ttu-id="f17f5-150">通过该方法创建 Web 视图 [`MSWebViewProcess.createWebViewAsync`](./webview/MSWebViewProcess.md#createwebviewasync) 还会在单独的进程中创建 Web 视图，但允许调用方更好地控制进程设置和在 Web 视图进程中分组 WebViews。</span><span class="sxs-lookup"><span data-stu-id="f17f5-150">Creating a WebView via the [`MSWebViewProcess.createWebViewAsync`](./webview/MSWebViewProcess.md#createwebviewasync) method also creates a WebView in a separate process but allows the caller more control over process settings and grouping WebViews in WebView processes.</span></span> <span data-ttu-id="f17f5-151">有关详细信息，请参阅 `MSWebViewProcess`。</span><span class="sxs-lookup"><span data-stu-id="f17f5-151">See `MSWebViewProcess` for more information.</span></span> 

### <span data-ttu-id="f17f5-152">WinRT API 访问</span><span class="sxs-lookup"><span data-stu-id="f17f5-152">WinRT API access</span></span>

<span data-ttu-id="f17f5-153">UWP 应用可能允许 WebViews 中的 HTML 文档具有对 WinRT Api 的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f17f5-153">A UWP app may allow HTML documents inside WebViews to have access to WinRT APIs.</span></span> <span data-ttu-id="f17f5-154">这是通过 UWP 应用 Package.appxmanifest 的 ApplicationContentUriRules 元素的规则子元素的 WindowsRuntimeAccess 属性。</span><span class="sxs-lookup"><span data-stu-id="f17f5-154">This is via the WindowsRuntimeAccess attribute of the Rule child elements of the ApplicationContentUriRules element of the AppxManifest.xml of the UWP app.</span></span> <span data-ttu-id="f17f5-155">将 WindowsRuntimeAccess 设置为 "all"，允许使用匹配 Uri 的 HTML 文档使用 WinRT。</span><span class="sxs-lookup"><span data-stu-id="f17f5-155">Set WindowsRuntimeAccess to 'all' and HTML documents with matching URIs will be allowed to use WinRT.</span></span> <span data-ttu-id="f17f5-156">这与在 JavaScript UWP 应用中为 HTML 内容提供 WinRT 访问的方式相同，因此请参阅[PWA 中的调用 WinRT api](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#call-winrt-apis-from-your-pwa)了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="f17f5-156">This is the same as providing WinRT access to HTML content in JavaScript UWP apps so see [Call WinRT APIs from your PWA](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#call-winrt-apis-from-your-pwa) for more information.</span></span>

<span data-ttu-id="f17f5-157">从运行在其自己的线程上的 Web 视图调用时，与 UI 相关的 WinRT Api 可能不起作用，但在从单独的 Web 源进程中运行的 Web 视图调用时可能会运行。</span><span class="sxs-lookup"><span data-stu-id="f17f5-157">UI related WinRT APIs may not work when called from a WebView running on its own thread but may work when called from a WebView running in a separate WebView process.</span></span> <span data-ttu-id="f17f5-158">在其自己的唯一线程上使用 Web 视图时，该线程不是应用的视图线程。</span><span class="sxs-lookup"><span data-stu-id="f17f5-158">When using a WebView on its own unique thread, that thread is not the app's view thread.</span></span> <span data-ttu-id="f17f5-159">需要从应用的视图线程调用某些与 UI 相关的 WinRT Api。</span><span class="sxs-lookup"><span data-stu-id="f17f5-159">Some UI related WinRT APIs require to be called from the app's view thread.</span></span> <span data-ttu-id="f17f5-160">在单独的 Web 视图进程中创建的 WebViews 在视图线程上运行，因此不应面临与在其自己的唯一线程上运行 Web 视图时相同的限制。</span><span class="sxs-lookup"><span data-stu-id="f17f5-160">WebViews created in a separate WebView process do run on a view thread and so should not face the same restrictions as WebView's running on their own unique thread.</span></span> <span data-ttu-id="f17f5-161">如果在 Web 视图中使用与 UI 相关的 WinRT Api 时遇到问题，请确保你在其自己的 Web 视图进程中使用 Web 视图（如上所述）。</span><span class="sxs-lookup"><span data-stu-id="f17f5-161">If you have trouble with UI related WinRT APIs in a WebView ensure that you're using a WebView in its own WebView process as described above.</span></span>

### <span data-ttu-id="f17f5-162">AppCache 存储限制</span><span class="sxs-lookup"><span data-stu-id="f17f5-162">AppCache storage limitations</span></span>

<span data-ttu-id="f17f5-163">使用 JavaScript[规范](https://go.microsoft.com/fwlink/p/?LinkId=228542)中定义的应用程序缓存 API （或 AppCache）的 JavaScript 支持应用程序，创建脱机 web 应用程序必须遵守可用的存储限制。</span><span class="sxs-lookup"><span data-stu-id="f17f5-163">Applications using JavaScript support of the Application Cache API (or AppCache), as defined in the [HTML5 specification](https://go.microsoft.com/fwlink/p/?LinkId=228542), to create offline web applications must observe available storage limitations.</span></span> <span data-ttu-id="f17f5-164">这在内存空间有限的设备中尤其如此。</span><span class="sxs-lookup"><span data-stu-id="f17f5-164">This is especially true in devices with limited memory space.</span></span> <span data-ttu-id="f17f5-165">对 AppCache 大小的实际限制始终是可用磁盘存储空间的功能。</span><span class="sxs-lookup"><span data-stu-id="f17f5-165">The practical limits on the size of the AppCache are always a function of available disk storage space.</span></span> <span data-ttu-id="f17f5-166">下面显示了一般指南。</span><span class="sxs-lookup"><span data-stu-id="f17f5-166">The general guidelines are shown below.</span></span>

| <span data-ttu-id="f17f5-167">卷大小</span><span class="sxs-lookup"><span data-stu-id="f17f5-167">Volume size</span></span>         |<span data-ttu-id="f17f5-168">每个域的 AppCache</span><span class="sxs-lookup"><span data-stu-id="f17f5-168">AppCache per domain</span></span> | <span data-ttu-id="f17f5-169">AppCache 每位用户</span><span class="sxs-lookup"><span data-stu-id="f17f5-169">AppCache per user</span></span>   | 
|---------------|---------------|-------------------------|
<span data-ttu-id="f17f5-170">高达4GB</span><span class="sxs-lookup"><span data-stu-id="f17f5-170">Up to 4GB</span></span> | <span data-ttu-id="f17f5-171">10MB</span><span class="sxs-lookup"><span data-stu-id="f17f5-171">10MB</span></span> | <span data-ttu-id="f17f5-172">50MB</span><span class="sxs-lookup"><span data-stu-id="f17f5-172">50MB</span></span> |
<span data-ttu-id="f17f5-173">4GB 到 4 GB</span><span class="sxs-lookup"><span data-stu-id="f17f5-173">4GB to 16GB</span></span> | <span data-ttu-id="f17f5-174">50MB</span><span class="sxs-lookup"><span data-stu-id="f17f5-174">50MB</span></span> | <span data-ttu-id="f17f5-175">500MB</span><span class="sxs-lookup"><span data-stu-id="f17f5-175">500MB</span></span> | 
<span data-ttu-id="f17f5-176">达 32 GB</span><span class="sxs-lookup"><span data-stu-id="f17f5-176">16GB to 32 GB</span></span> | <span data-ttu-id="f17f5-177">50MB</span><span class="sxs-lookup"><span data-stu-id="f17f5-177">50MB</span></span> | <span data-ttu-id="f17f5-178">甚至</span><span class="sxs-lookup"><span data-stu-id="f17f5-178">1GB</span></span> |

<span data-ttu-id="f17f5-179">所有 Windows10 应用都旨在使用相同的 AppCache 配额模型，因此可用磁盘存储限制适用于桌面和手机应用。</span><span class="sxs-lookup"><span data-stu-id="f17f5-179">All Windows10 apps are intended to use the same AppCache quota model, so the available disk storage limitation applies to both desktop and phone apps.</span></span> <span data-ttu-id="f17f5-180">在**Web 视图**内加载的页面已占用 1 GB 的*AppCache*空间后，也会出现硬限制;超过此限额的其他*AppCache*存储的请求将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="f17f5-180">The is also a hard limit after pages loaded inside **WebView** together have consumed 1 GB of *AppCache* space; requests for additional *AppCache* storage above this limit will be denied.</span></span> 

<span data-ttu-id="f17f5-181">有关详细信息，请参阅[HTML Web 视图控件示例](https://go.microsoft.com/fwlink/p/?linkid=309825)和 JSBrowser 的[web 视图控制](https://github.com/MicrosoftEdge/JSBrowser#harnessing-the-webview-control)文档。</span><span class="sxs-lookup"><span data-stu-id="f17f5-181">For more information, see the [HTML WebView control sample](https://go.microsoft.com/fwlink/p/?linkid=309825) and the JSBrowser's [Harnessing the WebView control](https://github.com/MicrosoftEdge/JSBrowser#harnessing-the-webview-control) documentation.</span></span>

## <span data-ttu-id="f17f5-182">事件</span><span class="sxs-lookup"><span data-stu-id="f17f5-182">Events</span></span>

### <span data-ttu-id="f17f5-183">departingFocus</span><span class="sxs-lookup"><span data-stu-id="f17f5-183">departingFocus</span></span>

<span data-ttu-id="f17f5-184">指示焦点从**web 视图**转到应用中。</span><span class="sxs-lookup"><span data-stu-id="f17f5-184">Indicates focus departing from the **webview** into the app.</span></span> <span data-ttu-id="f17f5-185">在 web 视图的顶级文档调用 departFocus 时激发。</span><span class="sxs-lookup"><span data-stu-id="f17f5-185">Fires when the webview's top level document calls window.departFocus.</span></span> <span data-ttu-id="f17f5-186">DepartingFocus 事件中的 FocusNavigationEvent 参数与提供给 departFocus 的参数相匹配，除了来源参数从 web 视图的 document's 坐标空间转换到 web 视图主机文档的坐标空间。</span><span class="sxs-lookup"><span data-stu-id="f17f5-186">The FocusNavigationEvent args in the departingFocus event match the parameters provided to departFocus except the origin parameters are translated from the webview's document's coordinate space to the coordinate space of the webview host document.</span></span> <span data-ttu-id="f17f5-187">请参阅 navigateFocus 方法和相应的窗口 navigatingFocus 将焦点从主机转移到 web 视图的事件。</span><span class="sxs-lookup"><span data-stu-id="f17f5-187">See the webview.navigateFocus method and corresponding window navigatingFocus event for transferring focus from host to webview.</span></span> <span data-ttu-id="f17f5-188">请参阅[TVJS 的方向导航库](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)，以获取通过键盘或处理此事件的游戏板实现焦点导航的示例。</span><span class="sxs-lookup"><span data-stu-id="f17f5-188">See the [TVJS's Direction Navigation library](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) for an example of an implementation of focus navigation via keyboard or gamepad that handles this event.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("departingFocus", handler);
webview.removeEventListener("departingFocus", handler);
```

#### <span data-ttu-id="f17f5-189">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-189">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-190">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-190">Interface</span></span>** | [<span data-ttu-id="f17f5-191">FocusNavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-191">FocusNavigationEvent</span></span>](./webview/FocusNavigationEvent.md) |
|**<span data-ttu-id="f17f5-192">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-192">Synchronous</span></span>** |<span data-ttu-id="f17f5-193">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-193">Yes</span></span> |    
|**<span data-ttu-id="f17f5-194">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-194">Bubbles</span></span>**     |<span data-ttu-id="f17f5-195">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-195">Yes</span></span> |   
|**<span data-ttu-id="f17f5-196">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-196">Cancelable</span></span>**  |<span data-ttu-id="f17f5-197">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-197">No</span></span> |            

### <span data-ttu-id="f17f5-198">MSWebViewContainsFullScreenElementChanged</span><span class="sxs-lookup"><span data-stu-id="f17f5-198">MSWebViewContainsFullScreenElementChanged</span></span>

<span data-ttu-id="f17f5-199">当**web 视图**当前是否包含全屏元素时发生的状态更改时发生。</span><span class="sxs-lookup"><span data-stu-id="f17f5-199">Occurs when the status changes of whether or not the **webview** currently contains a full screen element.</span></span> <span data-ttu-id="f17f5-200">将 containsFullScreenElement 属性用于当前值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-200">Use the containsFullScreenElement property to the current value.</span></span> <span data-ttu-id="f17f5-201">此处的全屏元素指通过 requestFullScreen 和 exitFullScreen DOM 函数的全屏元素的全屏[DOM api](https://developer.mozilla.org/docs/Web/API/Fullscreen_API)概念。</span><span class="sxs-lookup"><span data-stu-id="f17f5-201">Full screen element here refers to the [Fullscreen DOM APIs](https://developer.mozilla.org/docs/Web/API/Fullscreen_API) notion of a full screen element via the element.requestFullScreen and document.exitFullScreen DOM functions.</span></span>

```js
function containsFullScreenElementChangedHandler(eventInfo) {
    const applicationView = Windows.UI.ViewManagement.ApplicationView.getForCurrentView();
    if (webview.containsFullScreenElement) {
        webview.classList.add("fullscreen"); // Have the webview fill the app view
        applicationView.tryEnterFullScreenMode(); // Have the app view fill the screen
    }
    else {
        webview.classList.remove("fullscreen"); // Return webview to normal
        applicationView.exitFullScreenMode(); // Return app view to normal
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewContainsFullScreenElementChanged", containsFullScreenElementChangedHandler);
webview.removeEventListener("MSWebViewContainsFullScreenElementChanged", containsFullScreenElementChangedHandler);
```

#### <span data-ttu-id="f17f5-202">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-202">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-203">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-203">Interface</span></span>** | **<span data-ttu-id="f17f5-204">事件</span><span class="sxs-lookup"><span data-stu-id="f17f5-204">Event</span></span>** |
|**<span data-ttu-id="f17f5-205">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-205">Synchronous</span></span>** |<span data-ttu-id="f17f5-206">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-206">Yes</span></span> |    
|**<span data-ttu-id="f17f5-207">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-207">Bubbles</span></span>**     |<span data-ttu-id="f17f5-208">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-208">No</span></span> |   
|**<span data-ttu-id="f17f5-209">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-209">Cancelable</span></span>**  |<span data-ttu-id="f17f5-210">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-210">No</span></span> |  

### <span data-ttu-id="f17f5-211">MSWebViewContentLoading</span><span class="sxs-lookup"><span data-stu-id="f17f5-211">MSWebViewContentLoading</span></span>

<span data-ttu-id="f17f5-212">指示 HTML 内容已下载并正在加载到控件中。</span><span class="sxs-lookup"><span data-stu-id="f17f5-212">Indicates that the HTML content is downloaded and is being loaded into the control.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewContentLoading", handler);
webview.removeEventListener("MSWebViewContentLoading", handler);
```

#### <span data-ttu-id="f17f5-213">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-213">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-214">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-214">Interface</span></span>** | [<span data-ttu-id="f17f5-215">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-215">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-216">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-216">Synchronous</span></span>** |<span data-ttu-id="f17f5-217">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-217">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-218">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-218">Bubbles</span></span>**     |<span data-ttu-id="f17f5-219">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-219">No</span></span> |   
|**<span data-ttu-id="f17f5-220">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-220">Cancelable</span></span>**  |<span data-ttu-id="f17f5-221">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-221">No</span></span> |    

### <span data-ttu-id="f17f5-222">MSWebViewDOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="f17f5-222">MSWebViewDOMContentLoaded</span></span>

<span data-ttu-id="f17f5-223">指示主 DOM 元素已完成加载。</span><span class="sxs-lookup"><span data-stu-id="f17f5-223">Indicates that the main DOM elements have finished loading.</span></span>


```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewDOMContentLoaded", handler);
```

#### <span data-ttu-id="f17f5-224">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-224">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-225">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-225">Interface</span></span>** | [<span data-ttu-id="f17f5-226">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-226">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-227">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-227">Synchronous</span></span>** |<span data-ttu-id="f17f5-228">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-228">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-229">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-229">Bubbles</span></span>**     |<span data-ttu-id="f17f5-230">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-230">No</span></span> |   
|**<span data-ttu-id="f17f5-231">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-231">Cancelable</span></span>**  |<span data-ttu-id="f17f5-232">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-232">No</span></span> |                 

### <span data-ttu-id="f17f5-233">MSWebViewFrameContentLoading</span><span class="sxs-lookup"><span data-stu-id="f17f5-233">MSWebViewFrameContentLoading</span></span>

<span data-ttu-id="f17f5-234">指示下载并加载到控件中的 HTML 内容 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-234">Indicates that the HTML content downloaded and is being loaded into the `<iframe>` control.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameContentLoading", handler);
webview.removeEventListener("MSWebViewFrameContentLoading", handler);
```

#### <span data-ttu-id="f17f5-235">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-235">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-236">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-236">Interface</span></span>** | [<span data-ttu-id="f17f5-237">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-237">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-238">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-238">Synchronous</span></span>** |<span data-ttu-id="f17f5-239">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-239">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-240">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-240">Bubbles</span></span>**     |<span data-ttu-id="f17f5-241">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-241">No</span></span> |   
|**<span data-ttu-id="f17f5-242">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-242">Cancelable</span></span>**  |<span data-ttu-id="f17f5-243">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-243">No</span></span> |                 

### <span data-ttu-id="f17f5-244">MSWebViewFrameDOMContentLoaded</span><span class="sxs-lookup"><span data-stu-id="f17f5-244">MSWebViewFrameDOMContentLoaded</span></span>

<span data-ttu-id="f17f5-245">指示主 DOM 元素已在中完成加载 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-245">Indicates that the main DOM elements have finished loading in the `<iframe>`.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewFrameDOMContentLoaded", handler);
```

#### <span data-ttu-id="f17f5-246">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-246">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-247">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-247">Interface</span></span>** | [<span data-ttu-id="f17f5-248">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-248">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-249">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-249">Synchronous</span></span>** |<span data-ttu-id="f17f5-250">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-250">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-251">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-251">Bubbles</span></span>**     |<span data-ttu-id="f17f5-252">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-252">No</span></span> |   
|**<span data-ttu-id="f17f5-253">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-253">Cancelable</span></span>**  |<span data-ttu-id="f17f5-254">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-254">No</span></span> |    


### <span data-ttu-id="f17f5-255">MSWebViewFrameNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="f17f5-255">MSWebViewFrameNavigationCompleted</span></span>

<span data-ttu-id="f17f5-256">指示导航已完成，并且所有媒体元素都将呈现在中 `<iframe>` 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-256">Indicates the navigation is complete, and all media elements are rendered in the `<iframe>`.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameNavigationCompleted", handler);
webview.removeEventListener("MSWebViewFrameNavigationCompleted", handler);
```

#### <span data-ttu-id="f17f5-257">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-257">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-258">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-258">Interface</span></span>** | [<span data-ttu-id="f17f5-259">NavigationCompletedEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-259">NavigationCompletedEvent</span></span>](./webview/NavigationCompletedEvent.md) |
|**<span data-ttu-id="f17f5-260">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-260">Synchronous</span></span>** |<span data-ttu-id="f17f5-261">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-261">Yes</span></span> |    
|**<span data-ttu-id="f17f5-262">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-262">Bubbles</span></span>**     |<span data-ttu-id="f17f5-263">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-263">No</span></span> |   
|**<span data-ttu-id="f17f5-264">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-264">Cancelable</span></span>**  |<span data-ttu-id="f17f5-265">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-265">No</span></span> |       

### <span data-ttu-id="f17f5-266">MSWebViewFrameNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="f17f5-266">MSWebViewFrameNavigationStarting</span></span>

<span data-ttu-id="f17f5-267">指示 `<iframe>` **web 视图**内的 a 正在开始导航。</span><span class="sxs-lookup"><span data-stu-id="f17f5-267">Indicates a `<iframe>` within a **webview** is starting to navigate.</span></span> <span data-ttu-id="f17f5-268">在从网络获取导航的任何资源之前，将引发此情况。</span><span class="sxs-lookup"><span data-stu-id="f17f5-268">This is fired before obtaining any resources from the network for the navigation.</span></span> <span data-ttu-id="f17f5-269">在所有 MSWebViewFrameNavigationStarting 事件处理程序完成之前，导航不会启动。</span><span class="sxs-lookup"><span data-stu-id="f17f5-269">The navigation is not started until all MSWebViewFrameNavigationStarting event handlers complete.</span></span> <span data-ttu-id="f17f5-270">通过调用 cancellable 此事件 `eventArgs.preventDefault()` 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-270">This event is cancellable via calling `eventArgs.preventDefault()`.</span></span> <span data-ttu-id="f17f5-271">如果取消，则 Web 视图将不会执行导航。</span><span class="sxs-lookup"><span data-stu-id="f17f5-271">If cancelled, the WebView will not perform the navigation.</span></span>


```js
function frameNavigationStartingHandler(navigationEventArgs) {
    // Cancel all navigations that don't meet some criteria.
    if (!navigationEventArgs.uri.startsWith("https://example.com/")) {
        navigationEventArgs.preventDefault();
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameNavigationStarting", frameNavigationStartingHandler);
webview.removeEventListener("MSWebViewFrameNavigationStarting", frameNavigationStartingHandler);
```

#### <span data-ttu-id="f17f5-272">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-272">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-273">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-273">Interface</span></span>** | [<span data-ttu-id="f17f5-274">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-274">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-275">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-275">Synchronous</span></span>** |<span data-ttu-id="f17f5-276">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-276">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-277">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-277">Bubbles</span></span>**     |<span data-ttu-id="f17f5-278">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-278">No</span></span> |   
|**<span data-ttu-id="f17f5-279">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-279">Cancelable</span></span>**  |<span data-ttu-id="f17f5-280">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-280">Yes</span></span> |                 
          
### <span data-ttu-id="f17f5-281">MSWebViewLongRunningScriptDetected</span><span class="sxs-lookup"><span data-stu-id="f17f5-281">MSWebViewLongRunningScriptDetected</span></span>

<span data-ttu-id="f17f5-282">在**web 视图**中不中断的脚本执行期间定期发生，让你停止脚本。</span><span class="sxs-lookup"><span data-stu-id="f17f5-282">Occurs periodically during uninterrupted script execution in the **webview**, letting you halt the script.</span></span>

```js
function handler(eventInfo) {
    const stopPageScriptThreshold = 5 * 1000;
    if (eventInfo.executionTime > stopPageScriptThreshold) {
        eventInfo.stopPageScriptExecution = true; // Stop the long running script if it goes over our threshold
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewLongRunningScriptDetected", handler);
webview.removeEventListener("MSWebViewLongRunningScriptDetected", handler);
```

#### <span data-ttu-id="f17f5-283">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-283">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-284">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-284">Interface</span></span>** | [<span data-ttu-id="f17f5-285">LongRunningScriptDetectedEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-285">LongRunningScriptDetectedEvent</span></span>](./webview/LongRunningScriptDetectedEvent.md) |
|**<span data-ttu-id="f17f5-286">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-286">Synchronous</span></span>** |<span data-ttu-id="f17f5-287">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-287">Yes</span></span> |    
|**<span data-ttu-id="f17f5-288">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-288">Bubbles</span></span>**     |<span data-ttu-id="f17f5-289">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-289">No</span></span> |   
|**<span data-ttu-id="f17f5-290">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-290">Cancelable</span></span>**  |<span data-ttu-id="f17f5-291">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-291">No</span></span> |            

### <span data-ttu-id="f17f5-292">MSWebViewNavigationCompleted</span><span class="sxs-lookup"><span data-stu-id="f17f5-292">MSWebViewNavigationCompleted</span></span>

<span data-ttu-id="f17f5-293">指示导航已完成，将呈现所有媒体元素或出现导航错误。</span><span class="sxs-lookup"><span data-stu-id="f17f5-293">Indicates the navigation is complete, and all media elements are rendered or there was a navigation error.</span></span> <span data-ttu-id="f17f5-294">检查事件参数 isSuccess 属性以判断导航是否成功，并检查 webErrorStatus 属性以获取有关导航错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f17f5-294">Check the event args isSuccess property to tell if the navigation was successful and the webErrorStatus property for details on the navigation error.</span></span> <span data-ttu-id="f17f5-295">在从网络获取任何内容之前，如果 URI 的主机名未解析，在这种情况下将在该情况下引发 MSWebViewNavigationStarted 事件后跟 MSWebViewNavigationCompleted 事件，则会出现导航错误。</span><span class="sxs-lookup"><span data-stu-id="f17f5-295">Navigation errors can occur before obtaining any content from the network for instance if the hostname of a URI does not resolve in which case the MSWebViewNavigationStarted event will fire followed by the MSWebViewNavigationCompleted event.</span></span> <span data-ttu-id="f17f5-296">导航错误可能还会在从 web 服务器收到错误页面后出现，例如，从 HTTP 服务器收到一个404页面，在这种情况下，所有导航事件都将引发、MSWebViewNavigationStarting、MSWebViewContentLoading、MSWebViewDOMContentLoaded 和 MSWebViewNavigationCompleted。</span><span class="sxs-lookup"><span data-stu-id="f17f5-296">Navigation errors may also occur after receiving an error page from a web server, for instance a 404 page from an HTTP server in which case all navigation events will fire, MSWebViewNavigationStarting, MSWebViewContentLoading, MSWebViewDOMContentLoaded, and then MSWebViewNavigationCompleted.</span></span> <span data-ttu-id="f17f5-297">若要为 web 服务器未提供错误页面的情况提供应用导航错误页面，你需要检查 MSWebViewContentLoading 是否未触发失败的导航，这表示没有服务器提供错误页面。</span><span class="sxs-lookup"><span data-stu-id="f17f5-297">To provide an app navigation error page for cases where the web server hasn't provided an error page, you'll need to check if MSWebViewContentLoading hasn't fired for a failed navigation which indicates there is no server provided error page.</span></span>

```js
let hasContent = false;
webview.addEventListener("MSWebViewNavigationStarting", () => { hasContent = false; });
webview.addEventListener("MSWebViewContentLoading", () => { hasContent = true; });

webview.addEventListener("MSWebViewNavigationCompleted", navigationCompletedEventArgs => {
    // Navigation failures may or may not come after getting an error page from the web server.
    // We keep track of the ContentLoading event with hasContent to tell if we have an error page from the server.
    // So we only navigate to our app error page when there's no server provided error page.
    if (!navigationCompletedEventArgs.isSuccess && !hasContent) {
        // Pass our failed URI and error details in the query and the error page script can read it as appropriate.
        webview.navigate("ms-appx-web:///appErrorPage.html?" + 
            "uri=" + encodeURIComponent(navigationCompletedEventArgs.uri) + "&" +
            "webErrorStatus=" + encodeURIComponent(navigationCompletedEventArgs.webErrorStatus));
    }
});
 
// addEventListener syntax
webview.addEventListener("MSWebViewNavigationCompleted", handler);
webview.removeEventListener("MSWebViewNavigationCompleted", handler);
```

#### <span data-ttu-id="f17f5-298">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-298">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-299">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-299">Interface</span></span>** | [<span data-ttu-id="f17f5-300">NavigationCompletedEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-300">NavigationCompletedEvent</span></span>](./webview/NavigationCompletedEvent.md) |
|**<span data-ttu-id="f17f5-301">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-301">Synchronous</span></span>** |<span data-ttu-id="f17f5-302">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-302">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-303">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-303">Bubbles</span></span>**     |<span data-ttu-id="f17f5-304">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-304">No</span></span> |   
|**<span data-ttu-id="f17f5-305">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-305">Cancelable</span></span>**  |<span data-ttu-id="f17f5-306">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-306">No</span></span> |                 
         

### <span data-ttu-id="f17f5-307">MSWebViewNavigationStarting</span><span class="sxs-lookup"><span data-stu-id="f17f5-307">MSWebViewNavigationStarting</span></span>

<span data-ttu-id="f17f5-308">指示**web 视图**正在开始导航。</span><span class="sxs-lookup"><span data-stu-id="f17f5-308">Indicates the **webview** is starting to navigate.</span></span> <span data-ttu-id="f17f5-309">在从网络获取导航的任何资源之前，将引发此情况。</span><span class="sxs-lookup"><span data-stu-id="f17f5-309">This is fired before obtaining any resources from the network for the navigation.</span></span> <span data-ttu-id="f17f5-310">在所有 MSWebViewNavigationStarting 事件处理程序完成之前，导航不会启动。</span><span class="sxs-lookup"><span data-stu-id="f17f5-310">The navigation is not started until all MSWebViewNavigationStarting event handlers complete.</span></span> <span data-ttu-id="f17f5-311">通过调用 cancellable 此事件 `eventArgs.preventDefault()` 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-311">This event is cancellable via calling `eventArgs.preventDefault()`.</span></span> <span data-ttu-id="f17f5-312">如果取消，则 Web 视图将不会执行导航。</span><span class="sxs-lookup"><span data-stu-id="f17f5-312">If cancelled, the WebView will not perform the navigation.</span></span>


```js
function navigationStartingHandler(navigationEventArgs) {
    // Cancel all navigations that don't meet some criteria.
    if (!navigationEventArgs.uri.startsWith("https://example.com/")) {
        navigationEventArgs.preventDefault();
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewNavigationStarting", navigationStartingHandler);
webview.removeEventListener("MSWebViewNavigationStarting", navigationStartingHandler);
```

#### <span data-ttu-id="f17f5-313">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-313">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-314">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-314">Interface</span></span>** | [<span data-ttu-id="f17f5-315">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-315">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-316">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-316">Synchronous</span></span>** |<span data-ttu-id="f17f5-317">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-317">No</span></span>  |    
|**<span data-ttu-id="f17f5-318">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-318">Bubbles</span></span>**     |<span data-ttu-id="f17f5-319">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-319">Yes</span></span> |   
|**<span data-ttu-id="f17f5-320">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-320">Cancelable</span></span>**  |<span data-ttu-id="f17f5-321">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-321">Yes</span></span> |      

### <span data-ttu-id="f17f5-322">MSWebViewNewWindowRequested</span><span class="sxs-lookup"><span data-stu-id="f17f5-322">MSWebViewNewWindowRequested</span></span>

<span data-ttu-id="f17f5-323">在**web 视图**中的内容尝试打开新窗口时引发。</span><span class="sxs-lookup"><span data-stu-id="f17f5-323">Raised when content in **webview** is trying to open a new window.</span></span> <span data-ttu-id="f17f5-324">如果事件未取消，则 web 视图将在用户的默认浏览器中启动新窗口请求的 URI。</span><span class="sxs-lookup"><span data-stu-id="f17f5-324">If the event isn't cancelled the webview will launch the URI of the new window request in the user's default browser.</span></span>

```js
function handler(eventInfo) {
    // Prevent the webview from opening URIs in the default browser.
    eventInfo.preventDefault();
    
    // Only allow https://example.com/ to open new windows.
    if (eventInfo.referer === "https://example.com/") {
        // Perform some custom handling of the URI.
        openUri(eventInfo.uri);
    }
}
 
// addEventListener syntax
webview.addEventListener("MSWebViewNewWindowRequested", handler);
webview.removeEventListener("MSWebViewNewWindowRequested", handler);
```

#### <span data-ttu-id="f17f5-325">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-325">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-326">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-326">Interface</span></span>** | [<span data-ttu-id="f17f5-327">NavigationEventWithReferrer</span><span class="sxs-lookup"><span data-stu-id="f17f5-327">NavigationEventWithReferrer</span></span>](./webview/NavigationEventWithReferrer.md) |
|**<span data-ttu-id="f17f5-328">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-328">Synchronous</span></span>** |<span data-ttu-id="f17f5-329">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-329">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-330">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-330">Bubbles</span></span>**     |<span data-ttu-id="f17f5-331">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-331">No</span></span> |   
|**<span data-ttu-id="f17f5-332">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-332">Cancelable</span></span>**  |<span data-ttu-id="f17f5-333">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-333">Yes</span></span> |                 
           

### <span data-ttu-id="f17f5-334">MSWebViewPermissionRequested</span><span class="sxs-lookup"><span data-stu-id="f17f5-334">MSWebViewPermissionRequested</span></span>

<span data-ttu-id="f17f5-335">指示**web 视图**中的内容尝试访问通常需要最终用户权限的功能（如地理位置或指针锁定访问）。</span><span class="sxs-lookup"><span data-stu-id="f17f5-335">Indicates that content in the **webview**  is trying to access functionality (such as geolocation, or pointer lock access) that normally requires end-user permissions.</span></span> <span data-ttu-id="f17f5-336">如果未注册任何事件处理程序，或者事件处理程序没有调用 permissionRequest （）、defer （）或 deny （），则权限请求将被拒绝。</span><span class="sxs-lookup"><span data-stu-id="f17f5-336">If no event handler is registered or if the event handler doesn't call eventArgs.permissionRequest.allow(), defer(), or deny(), then by default the permission request will be denied.</span></span> <span data-ttu-id="f17f5-337">如果你需要确定是否为实例异步允许或拒绝权限（如果你需要提示用户），请使用 permissionRequest （）。</span><span class="sxs-lookup"><span data-stu-id="f17f5-337">If you need to decide if permission is allowed or denied asynchronously for instance if you need to prompt the user, use eventArgs.permissionRequest.defer().</span></span> <span data-ttu-id="f17f5-338">将延迟权限请求，直到你使用 getDeferredPermissionRequestById 或 web web getDeferredPermissionRequests，并使用对应的 id 值在 DeferredPermissionRequest 上调用 allow （）或 deny （）。</span><span class="sxs-lookup"><span data-stu-id="f17f5-338">The permission request will be deferred until you use webview.getDeferredPermissionRequestById or webview.getDeferredPermissionRequests and call allow() or deny() on the DeferredPermissionRequest with the corresponding id value.</span></span>

```js
webview.addEventListener("MSWebViewPermissionRequested", permissionRequestedEventArgs => {
    const permissionRequest = permissionRequestedEventArgs.permissionRequest;
    switch (permissionRequest.type) {
        case "geolocation":
        case "media":
        case "pointerlock":
        case "webnotifications":
        case "screen":
        case "immersiveview":
            if (permissionRequest.uri.startsWith("https://www.example.com/")) {
                // Implicitly trust particular URI
                permissionRequest.allow();
            }
            else if (permissionRequest.uri.startsWith("https://")) {
                // Defer the request so we can ask the user to allow or deny the request
                permissionRequest.defer();
                // Later we'll need to use webview.getDeferredPermissionRequestById for this
                // request and call allow or deny.
                promptUserForDeferredPermissionRequest(
                    permissionRequest.id,
                    permissionRequest.uri,
                    permissionRequest.type);
            }
            else {
                // Implicitly deny non-https URIs
                permissionRequest.deny();
            }
            break;

        case "unlimitedIndexedDBQuota":
        default:
            permissionRequest.deny();
            break;
    }
});

// addEventListener syntax
webview.addEventListener("MSWebViewPermissionRequested", handler);
webview.removeEventListener("MSWebViewPermissionRequested", handler);
```

#### <span data-ttu-id="f17f5-339">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-339">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-340">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-340">Interface</span></span>** | [<span data-ttu-id="f17f5-341">PermissionRequestedEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-341">PermissionRequestedEvent</span></span>](./webview/PermissionRequestedEvent.md) |
|**<span data-ttu-id="f17f5-342">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-342">Synchronous</span></span>** |<span data-ttu-id="f17f5-343">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-343">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-344">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-344">Bubbles</span></span>**     |<span data-ttu-id="f17f5-345">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-345">No</span></span> |   
|**<span data-ttu-id="f17f5-346">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-346">Cancelable</span></span>**  |<span data-ttu-id="f17f5-347">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-347">No</span></span> |    


### <span data-ttu-id="f17f5-348">MSWebViewProcessExited</span><span class="sxs-lookup"><span data-stu-id="f17f5-348">MSWebViewProcessExited</span></span>

<span data-ttu-id="f17f5-349">指示**web 视图**组件进程 crashsed。</span><span class="sxs-lookup"><span data-stu-id="f17f5-349">Indicates that the **webview** component process crashsed.</span></span> <span data-ttu-id="f17f5-350">这仅适用于进程外的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="f17f5-350">This is only relevant for an out-of-process WebView.</span></span> <span data-ttu-id="f17f5-351">有关如何创建进程内 web 视图（相对于进程内 Web 视图）的说明，请参阅备注部分。</span><span class="sxs-lookup"><span data-stu-id="f17f5-351">See the Remarks section for how to create an out-of-process WebView as opposed to an in-process WebView.</span></span> <span data-ttu-id="f17f5-352">此事件引发后，相应的 Web 视图将置于崩溃状态。</span><span class="sxs-lookup"><span data-stu-id="f17f5-352">After this event fires, the corresponding WebView is put into a crashed state.</span></span> <span data-ttu-id="f17f5-353">在崩溃的 Web 视图上调用大多数 Web 视图特定的方法或访问大多数 Web 视图特定的属性将引发异常。</span><span class="sxs-lookup"><span data-stu-id="f17f5-353">Calling most WebView specific methods or accessing most WebView specific properties on a crashed WebView will throw an exception.</span></span> <span data-ttu-id="f17f5-354">若要从此事件中恢复，请从 DOM 中删除崩溃的 Web 视图并将其替换为新的 Web 视图。</span><span class="sxs-lookup"><span data-stu-id="f17f5-354">To recover from this event, remove the crashed WebView from the DOM and replace it with a new WebView.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewProcessExited", handler);
webview.removeEventListener("MSWebViewProcessExited", handler);
```

#### <span data-ttu-id="f17f5-355">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-355">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-356">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-356">Interface</span></span>** | **<span data-ttu-id="f17f5-357">事件</span><span class="sxs-lookup"><span data-stu-id="f17f5-357">Event</span></span>** |
|**<span data-ttu-id="f17f5-358">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-358">Synchronous</span></span>** |<span data-ttu-id="f17f5-359">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-359">Yes</span></span> |    
|**<span data-ttu-id="f17f5-360">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-360">Bubbles</span></span>**     |<span data-ttu-id="f17f5-361">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-361">No</span></span> |   
|**<span data-ttu-id="f17f5-362">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-362">Cancelable</span></span>**  |<span data-ttu-id="f17f5-363">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-363">No</span></span> |      


### <span data-ttu-id="f17f5-364">MSWebViewWebResourceRequested</span><span class="sxs-lookup"><span data-stu-id="f17f5-364">MSWebViewWebResourceRequested</span></span>

<span data-ttu-id="f17f5-365">在**web 视图**元素内的页面请求资源时引发。</span><span class="sxs-lookup"><span data-stu-id="f17f5-365">Raised when a page inside the **webview** element requests a resource.</span></span>

```js
// A handler that completes synchronously with a custom HTTP response built from a string.
function handlerWithSyncString(webResourceRequestedEventArgs) {
    // Only provide custom HTTP responses for particular HTTP requests
    if (webResourceRequestedEventArgs.args.request.requestUri.absoluteUri === "https://www.bing.com/") {
        const Http = Windows.Web.Http;
        // Create the custom response using a string
        webResourceRequestedEventArgs.args.response = new Http.HttpResponseMessage(Http.HttpStatusCode.ok);
        webResourceRequestedEventArgs.args.response.content = new Http.HttpStringContent("<H1>Example</H1>");
    }
});

// A more complicated handler that completes asynchronously with a custom HTTP response built from a stream.
function handlerWithAsyncStream(webResourceRequestedEventArgs) {
    // Only provide custom HTTP responses for particular HTTP requests
    if (webResourceRequestedEventArgs.args.request.requestUri.absoluteUri === "https://www.bing.com/") {
        // Take a deferral on the WebResourceRequested event so that we can create the custom HTTP response asynchronously.
        const deferral = webResourceRequestedEventArgs.args.getDeferral();

        // Use fetch to get a Blob of the content of the URI
        fetch("ms-appx:///replacement.html").then(fetchResponse => {
            return fetchResponse.blob();
        }).then(fetchResponseBlob => {
            const Http = Windows.Web.Http;
            webResourceRequestedEventArgs.args.response = new Http.HttpResponseMessage(
                Http.HttpStatusCode.ok);

            // Use Blob.msDetachStream to convert the Blob to a Windows.Storage.Streams.IInputStream
            webResourceRequestedEventArgs.args.response.content = new Http.HttpStreamContent(
                fetchResponseBlob.msDetachStream());

        }).finally(() => {
            // Use a finally call to complete the deferral so even if there is an error we will unblock the event.
            deferral.complete();
        });
    }
});
 
// addEventListener syntax
webview.addEventListener("MSWebViewWebResourceRequested", handler);
webview.removeEventListener("MSWebViewWebResourceRequested", handler);
```

#### <span data-ttu-id="f17f5-366">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-366">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-367">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-367">Interface</span></span>** | [<span data-ttu-id="f17f5-368">WebResourceRequestedEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-368">WebResourceRequestedEvent</span></span>](./webview/WebResourceRequestedEvent.md) |
|**<span data-ttu-id="f17f5-369">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-369">Synchronous</span></span>** |<span data-ttu-id="f17f5-370">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-370">Yes</span></span> |    
|**<span data-ttu-id="f17f5-371">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-371">Bubbles</span></span>**     |<span data-ttu-id="f17f5-372">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-372">No</span></span> |   
|**<span data-ttu-id="f17f5-373">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-373">Cancelable</span></span>**  |<span data-ttu-id="f17f5-374">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-374">No</span></span> |      


### <span data-ttu-id="f17f5-375">MSWebViewScriptNotify</span><span class="sxs-lookup"><span data-stu-id="f17f5-375">MSWebViewScriptNotify</span></span>

<span data-ttu-id="f17f5-376">在**web 视图**内的页面调用**window 外部通知**方法时引发。</span><span class="sxs-lookup"><span data-stu-id="f17f5-376">Raised when a page inside the **webview** element calls the **window.external.notify** method.</span></span> <span data-ttu-id="f17f5-377">只有 Uri 与应用的 manifest's ApplicationContentUriRules 中的规则匹配的文档或通过将 web 视图设置为 true 的文档才可用。 isScriptNotifyAllowed 设置为 true。</span><span class="sxs-lookup"><span data-stu-id="f17f5-377">The window.external.notify method is only available to documents with URIs that match rules in the app's manifest's ApplicationContentUriRules or that has been programatically allowed via setting webview.settings.isScriptNotifyAllowed to true.</span></span> <span data-ttu-id="f17f5-378">此外，"外部" 通知仅适用于 web 视图的顶级文档。</span><span class="sxs-lookup"><span data-stu-id="f17f5-378">Additionally window.external.notify is only available to the webview's top level document.</span></span>

```js
webview.addEventListener("MSWebViewScriptNotify", eventInfo => {
    console.log("The URI " + eventInfo.callingUri + 
        " has sent notification " + eventInfo.value);
});

// Allow the next URI to which we navigate access to window.external.notify
webview.settings.isScriptNotifyAllowed = true;
webview.navigate("https://example.com/");

webview.addEventListener("MSWebViewNavigationCompleted", () => {
    // Inject script to the webview that will send a notification back.
    const asyncOp = webview.invokeScriptAsync("eval", "window.external.notify('example notification')");
    asyncOp.start();
});
```

#### <span data-ttu-id="f17f5-379">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-379">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-380">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-380">Interface</span></span>** | [<span data-ttu-id="f17f5-381">ScriptNotifyEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-381">ScriptNotifyEvent</span></span>](./webview/ScriptNotifyEvent.md) |
|**<span data-ttu-id="f17f5-382">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-382">Synchronous</span></span>** |<span data-ttu-id="f17f5-383">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-383">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-384">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-384">Bubbles</span></span>**     |<span data-ttu-id="f17f5-385">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-385">No</span></span> |   
|**<span data-ttu-id="f17f5-386">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-386">Cancelable</span></span>**  |<span data-ttu-id="f17f5-387">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-387">No</span></span> |      

### <span data-ttu-id="f17f5-388">MSWebViewUnsafeContentWarningDisplaying</span><span class="sxs-lookup"><span data-stu-id="f17f5-388">MSWebViewUnsafeContentWarningDisplaying</span></span>

<span data-ttu-id="f17f5-389">在**web 视图**显示针对 SmartScreen 筛选器被报告为不安全的内容时出现的警告页面时发生。</span><span class="sxs-lookup"><span data-stu-id="f17f5-389">Occurs when the **webview** shows a warning page for content that was reported as unsafe by SmartScreen Filter.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
webview.removeEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
```

#### <span data-ttu-id="f17f5-390">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-390">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-391">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-391">Interface</span></span>** | **<span data-ttu-id="f17f5-392">事件</span><span class="sxs-lookup"><span data-stu-id="f17f5-392">Event</span></span>** |
|**<span data-ttu-id="f17f5-393">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-393">Synchronous</span></span>** |<span data-ttu-id="f17f5-394">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-394">Yes</span></span> |    
|**<span data-ttu-id="f17f5-395">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-395">Bubbles</span></span>**     |<span data-ttu-id="f17f5-396">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-396">No</span></span> |   
|**<span data-ttu-id="f17f5-397">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-397">Cancelable</span></span>**  |<span data-ttu-id="f17f5-398">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-398">No</span></span> |    

### <span data-ttu-id="f17f5-399">MSWebViewUnsupportedUriSchemeIdentified</span><span class="sxs-lookup"><span data-stu-id="f17f5-399">MSWebViewUnsupportedUriSchemeIdentified</span></span>

<span data-ttu-id="f17f5-400">当导航到**web 视图**不支持的统一资源标识符（URI）时引发。</span><span class="sxs-lookup"><span data-stu-id="f17f5-400">Raised when there is navigation to an Uniform Resource Identifier (URI) that the **webview** does not support.</span></span>

```js
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
webview.removeEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
```

#### <span data-ttu-id="f17f5-401">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-401">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-402">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-402">Interface</span></span>** | [<span data-ttu-id="f17f5-403">NavigationEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-403">NavigationEvent</span></span>](./webview/NavigationEvent.md) |
|**<span data-ttu-id="f17f5-404">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-404">Synchronous</span></span>** |<span data-ttu-id="f17f5-405">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-405">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-406">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-406">Bubbles</span></span>**     |<span data-ttu-id="f17f5-407">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-407">No</span></span> |   
|**<span data-ttu-id="f17f5-408">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-408">Cancelable</span></span>**  |<span data-ttu-id="f17f5-409">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-409">Yes</span></span> |     

### <span data-ttu-id="f17f5-410">MSWebViewUnviewableContentIdentified</span><span class="sxs-lookup"><span data-stu-id="f17f5-410">MSWebViewUnviewableContentIdentified</span></span>

<span data-ttu-id="f17f5-411">在**web 视图**尝试导航到具有不受支持的内容类型的 web 内容时引发。</span><span class="sxs-lookup"><span data-stu-id="f17f5-411">Raised when the **webview** attempts to navigate to web content with an unsupported content type.</span></span> <span data-ttu-id="f17f5-412">例如，web 视图当前不支持 Pdf，并且 PDF 文档的导航不受支持，而是会引发此事件。</span><span class="sxs-lookup"><span data-stu-id="f17f5-412">For example, PDFs are currently not supported by webview and navigations to PDF documents will not navigate and instead raise this event.</span></span>

```js
function handler(args) {
    if (args.mediaType === "application/pdf") {
        Windows.System.Launcher.launchUriAsync(new Windows.Foundation.Uri(args.uri));
    }
}

// addEventListener syntax
webview.addEventListener("MSWebViewUnviewableContentIdentified", handler);
webview.removeEventListener("MSWebViewUnviewableContentIdentified", handler);
```

#### <span data-ttu-id="f17f5-413">事件信息</span><span class="sxs-lookup"><span data-stu-id="f17f5-413">Event Information</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-414">接口</span><span class="sxs-lookup"><span data-stu-id="f17f5-414">Interface</span></span>** | [<span data-ttu-id="f17f5-415">UnviewableContentIdentifiedEvent</span><span class="sxs-lookup"><span data-stu-id="f17f5-415">UnviewableContentIdentifiedEvent</span></span>](./webview/UnviewableContentIdentifiedEvent.md) |
|**<span data-ttu-id="f17f5-416">同步</span><span class="sxs-lookup"><span data-stu-id="f17f5-416">Synchronous</span></span>** |<span data-ttu-id="f17f5-417">是</span><span class="sxs-lookup"><span data-stu-id="f17f5-417">Yes</span></span>  |    
|**<span data-ttu-id="f17f5-418">气泡</span><span class="sxs-lookup"><span data-stu-id="f17f5-418">Bubbles</span></span>**     |<span data-ttu-id="f17f5-419">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-419">No</span></span> |   
|**<span data-ttu-id="f17f5-420">可取消</span><span class="sxs-lookup"><span data-stu-id="f17f5-420">Cancelable</span></span>**  |<span data-ttu-id="f17f5-421">否</span><span class="sxs-lookup"><span data-stu-id="f17f5-421">No</span></span> |                 
         

## <span data-ttu-id="f17f5-422">方法</span><span class="sxs-lookup"><span data-stu-id="f17f5-422">Methods</span></span>

### <span data-ttu-id="f17f5-423">Webview.addweballowedobject</span><span class="sxs-lookup"><span data-stu-id="f17f5-423">addWebAllowedObject</span></span>

<span data-ttu-id="f17f5-424">将本机 Windows 运行时对象作为全局参数添加到**web 视图**内的顶级文档中。</span><span class="sxs-lookup"><span data-stu-id="f17f5-424">Adds a native Windows Runtime object as a global parameter to the top-level document inside of a **webview**.</span></span>

<span data-ttu-id="f17f5-425">该对象不会插入到当前文档中，而是指向 web 视图导航到的下一个顶级文档。</span><span class="sxs-lookup"><span data-stu-id="f17f5-425">The object is not injected into the current document, but rather the next top-level document to which the webview navigates.</span></span> <span data-ttu-id="f17f5-426">在运行 HTML 文档中的任何脚本之前插入对象，以便你可以在文档的全局脚本中依赖该对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-426">The object is injected before any script from the HTML document runs so you can rely on the object in your document's global script.</span></span>

<span data-ttu-id="f17f5-427">在 MSWebViewNavigationStarting 事件期间或显式调用导航方法之前，应使用 Webview.addweballowedobject。</span><span class="sxs-lookup"><span data-stu-id="f17f5-427">You should use addWebAllowedObject either during an MSWebViewNavigationStarting event or before explicitly calling a navigate method.</span></span> <span data-ttu-id="f17f5-428">在这些情况下，对象将被插入到相应导航的文档中。</span><span class="sxs-lookup"><span data-stu-id="f17f5-428">In these cases the object is injected into the document of the corresponding navigation.</span></span> <span data-ttu-id="f17f5-429">在某些其他上下文中调用它时，你无法确定要插入对象的文档。</span><span class="sxs-lookup"><span data-stu-id="f17f5-429">Calling it in some other context, you don't have a way to be certain into what document you'll inject your object.</span></span>

<span data-ttu-id="f17f5-430">在一行中多次调用 Webview.addweballowedobject 将在文档中插入多个对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-430">Calling addWebAllowedObject multiple times in a row will inject multiple objects into the document.</span></span> <span data-ttu-id="f17f5-431">如果在显式导航调用之前和在相应的 MSWebViewNavigationStarting 事件期间再次调用它，则两个调用都将成功，并且你将插入多个对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-431">If you call it both before an explicit navigate call and then again during the corresponding MSWebViewNavigationStarting event, both calls will succeed and you'll have multiple objects injected.</span></span> <span data-ttu-id="f17f5-432">如果用相同名称参数调用多次，则将忽略最后一个通话的 wins 和以前与该名称的通话。</span><span class="sxs-lookup"><span data-stu-id="f17f5-432">If you call multiple times with the same name parameter, the last call wins and the previous calls with that name are ignored.</span></span>

<span data-ttu-id="f17f5-433">如果导航失败或被重定向，则将忽略该导航的 Webview.addweballowedobject 调用。</span><span class="sxs-lookup"><span data-stu-id="f17f5-433">If a navigate fails or is redirected, the addWebAllowedObject calls for that navigation are ignored.</span></span> <span data-ttu-id="f17f5-434">如果你想要处理重定向，你可以按照适用于你的应用程序的任何条件，为重定向和调用 Webview.addweballowedobject 订阅 MSWebViewNavigationStarting 事件监视。</span><span class="sxs-lookup"><span data-stu-id="f17f5-434">If you want to handle redirects you can subscribe to the MSWebViewNavigationStarting event watch for redirects and call addWebAllowedObject again according to whatever criteria is appropriate for your application.</span></span> <span data-ttu-id="f17f5-435">同样，当文档导航离开通过 Webview.addweballowedobject 为该文档插入的任何对象时，将不会转到下一个文档，如果你希望它们执行，则需要显式调用 Webview.addweballowedobject。</span><span class="sxs-lookup"><span data-stu-id="f17f5-435">Similarly, once a document navigates away any objects injected via addWebAllowedObject for that document will not carry over to the next document and you'll need to explicitly call addWebAllowedObject if you want them to carry over.</span></span>

<span data-ttu-id="f17f5-436">如果你为没有 WinRT 访问的文档调用 Webview.addweballowedobject，或者如果它具有[通过 ApplicationContentUriRules 的 AllowForWebOnly access](/uwp/schemas/appxpackage/uapmanifestschema/element-uap-rule) ，则仅当对象具有元数据属性时才会注入该对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-436">If you call addWebAllowedObject for a document that has no WinRT access otherwise, or if it has [AllowForWebOnly access via ApplicationContentUriRules](/uwp/schemas/appxpackage/uapmanifestschema/element-uap-rule) then the object will only be injected if the object has the Windows.Foundation.Metadata.AllowForWeb metadata attribute.</span></span> <span data-ttu-id="f17f5-437">否则，注入将失败，并且会向 JavaScript 开发人员控制台报告错误。</span><span class="sxs-lookup"><span data-stu-id="f17f5-437">Otherwise injection will fail and an error will be reported to the JavaScript developer console.</span></span> <span data-ttu-id="f17f5-438">如果在具有完全 WinRT 访问权限的文档上调用，则无论 AllowForWeb 属性如何，都将插入该对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-438">If called on a document that has full WinRT access, then the object will be injected regardless of the AllowForWeb attribute.</span></span> 

<span data-ttu-id="f17f5-439">此外，该对象必须实现 IAgileObject 接口。</span><span class="sxs-lookup"><span data-stu-id="f17f5-439">Additionally, the object must implement the IAgileObject interface.</span></span> <span data-ttu-id="f17f5-440">这是因为 XAML 和 HTML web 视图元素在其应用的 ASTA 视图线程上运行，并且 Web 视图的 JavaScript 线程是不同的 ASTA 线程，因此我们希望鼓励应用开发人员确保其对象可以在 JavaScript 线程上运行，而无需阻止应用视图线程。</span><span class="sxs-lookup"><span data-stu-id="f17f5-440">This is because the XAML and HTML webview elements run on their app's ASTA view threads and the WebView's JavaScript thread is a different ASTA thread and we want to encourage app developers to ensure their object can run on the JavaScript thread without blocking the app view thread if possible.</span></span>

<span data-ttu-id="f17f5-441">Name 参数必须是有效的 JavaScript 属性名称，否则该调用将自动失败。</span><span class="sxs-lookup"><span data-stu-id="f17f5-441">The name parameter must be a valid JavaScript property name otherwise the call will fail silently.</span></span> <span data-ttu-id="f17f5-442">如果名称的属性是已存在于全局对象，则该属性将在属性可配置时被覆盖。</span><span class="sxs-lookup"><span data-stu-id="f17f5-442">If the name is of a property that already exists on the global object then that property is overwritten if the property is configurable.</span></span> <span data-ttu-id="f17f5-443">全局对象上的不可配置属性不会被覆盖，并且 Webview.addweballowedobject 调用将无提示地失败。</span><span class="sxs-lookup"><span data-stu-id="f17f5-443">Non-configurable properties on the global object are not overwritten and the addWebAllowedObject call fails silently.</span></span> <span data-ttu-id="f17f5-444">通过 Webview.addweballowedobject 创建的 JavaScript 属性是可写、可配置和可枚举的。</span><span class="sxs-lookup"><span data-stu-id="f17f5-444">JavaScript properties created via addWebAllowedObject are writable, configurable, and enumerable.</span></span>

```js
let name = "exampleProperty";
webview.addWebAllowedObject(name, applicationObject);
webview.navigate("https://example.com/"); // applicationObject will be available as window.exampleProperty on https://example.com
```

#### <span data-ttu-id="f17f5-445">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-445">Parameters</span></span>
*<span data-ttu-id="f17f5-446">name</span><span class="sxs-lookup"><span data-stu-id="f17f5-446">name</span></span>*
* <span data-ttu-id="f17f5-447">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-447">Type: **String**</span></span>
* <span data-ttu-id="f17f5-448">要向**web 视图**中的文档公开的对象的名称。</span><span class="sxs-lookup"><span data-stu-id="f17f5-448">The name of the object to expose to the document in the **webview**.</span></span>

*<span data-ttu-id="f17f5-449">applicationObject</span><span class="sxs-lookup"><span data-stu-id="f17f5-449">applicationObject</span></span>*
* <span data-ttu-id="f17f5-450">类型：**对象**</span><span class="sxs-lookup"><span data-stu-id="f17f5-450">Type: **Object**</span></span>
* <span data-ttu-id="f17f5-451">要向**web 视图**中的文档公开的对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-451">The object to expose to the document in the **webview**.</span></span>

#### <span data-ttu-id="f17f5-452">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-452">Return value</span></span>
<span data-ttu-id="f17f5-453">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-453">This method does not return a value.</span></span>

#### <span data-ttu-id="f17f5-454">其他功能和要求</span><span class="sxs-lookup"><span data-stu-id="f17f5-454">Additional features and requirements</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-455">最低受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="f17f5-455">Minimum supported client</span></span>** |<span data-ttu-id="f17f5-456">Windows10 [仅限 Windows 应用商店应用]</span><span class="sxs-lookup"><span data-stu-id="f17f5-456">Windows10 [Windows Store apps only]</span></span> |    
|**<span data-ttu-id="f17f5-457">最低受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="f17f5-457">Minimum supported server</span></span>** |<span data-ttu-id="f17f5-458">无受支持的版本</span><span class="sxs-lookup"><span data-stu-id="f17f5-458">None supported</span></span> |   
|**<span data-ttu-id="f17f5-459">最低受支持的电话</span><span class="sxs-lookup"><span data-stu-id="f17f5-459">Minimum supported phone</span></span>**  |<span data-ttu-id="f17f5-460">无受支持的版本</span><span class="sxs-lookup"><span data-stu-id="f17f5-460">None supported</span></span> |  

### <span data-ttu-id="f17f5-461">buildLocalStreamUri</span><span class="sxs-lookup"><span data-stu-id="f17f5-461">buildLocalStreamUri</span></span>

<span data-ttu-id="f17f5-462">创建可传递给[navigateToLocalStreamUri](#methods)的 URI。</span><span class="sxs-lookup"><span data-stu-id="f17f5-462">Creates a URI that you can pass to [navigateToLocalStreamUri](#methods).</span></span>

```js
var string = webview.buildLocalStreamUri(contentIdentifier, relativePath);
```

#### <span data-ttu-id="f17f5-463">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-463">Parameters</span></span>
*<span data-ttu-id="f17f5-464">contentIdentifier</span><span class="sxs-lookup"><span data-stu-id="f17f5-464">contentIdentifier</span></span>*
* <span data-ttu-id="f17f5-465">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-465">Type: **String**</span></span>
* <span data-ttu-id="f17f5-466">URI 引用的内容的唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="f17f5-466">A unique identifier for the content the URI is referencing.</span></span> <span data-ttu-id="f17f5-467">这将定义 URI 的根。</span><span class="sxs-lookup"><span data-stu-id="f17f5-467">This defines the root of the URI.</span></span>

*<span data-ttu-id="f17f5-468">relativePath</span><span class="sxs-lookup"><span data-stu-id="f17f5-468">relativePath</span></span>*
* <span data-ttu-id="f17f5-469">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-469">Type: **String**</span></span>
* <span data-ttu-id="f17f5-470">相对于根的资源的路径。</span><span class="sxs-lookup"><span data-stu-id="f17f5-470">The path to the resource, relative to the root.</span></span>

#### <span data-ttu-id="f17f5-471">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-471">Return value</span></span>
<span data-ttu-id="f17f5-472">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-472">Type: **String**</span></span>

<span data-ttu-id="f17f5-473">通过组合和规范化*contentIdentifier*和*RELATIVEPATH*创建的 URI。</span><span class="sxs-lookup"><span data-stu-id="f17f5-473">The URI created by combining and normalizing the *contentIdentifier* and *relativePath*.</span></span>

#### <span data-ttu-id="f17f5-474">示例</span><span class="sxs-lookup"><span data-stu-id="f17f5-474">Example</span></span>

<span data-ttu-id="f17f5-475">以下示例阐释了一个典型的用例。</span><span class="sxs-lookup"><span data-stu-id="f17f5-475">The following example illustrates a typical use case.</span></span> 

```js
var webview = document.createElement("x-ms-webview"); //Instantiate the webview element
var localStreamUri = webview.buildLocalStreamUri(contentIdentifier, relativePath); //Create URI to pass to navigateToLocalStreamUri method
webview.navigateToLocalStreamUri(localStreamUri, streamResolver); //Load the local web content 
```  

### <span data-ttu-id="f17f5-476">capturePreviewToBlobAsync</span><span class="sxs-lookup"><span data-stu-id="f17f5-476">capturePreviewToBlobAsync</span></span>

<span data-ttu-id="f17f5-477">创建当前[web 视图元素](./webview.md)的图像，并将其写入指定的 image 元素。</span><span class="sxs-lookup"><span data-stu-id="f17f5-477">Creates an image of the current [webview element](./webview.md) and write it to the specified image element.</span></span>

```js
var capturePreviewToBlobAsync = webview.capturePreviewToBlobAsync();
```

#### <span data-ttu-id="f17f5-478">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-478">Parameters</span></span>
<span data-ttu-id="f17f5-479">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-479">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-480">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-480">Return value</span></span>
<span data-ttu-id="f17f5-481">类型： **MSWebViewAsyncOperation**</span><span class="sxs-lookup"><span data-stu-id="f17f5-481">Type: **MSWebViewAsyncOperation**</span></span>

<span data-ttu-id="f17f5-482">一个**MSWebViewAsyncOperation**对象，该对象在完成时提供包含图像的**Blob**对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-482">An **MSWebViewAsyncOperation** object that, when it completes, provides a **Blob** object that contains the image.</span></span> <span data-ttu-id="f17f5-483">使用**capturePreviewToBlobAsync**时，你需要在定义操作后定义成功和错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="f17f5-483">When using **capturePreviewToBlobAsync**, you need to define success and error handlers after defining the operation.</span></span> <span data-ttu-id="f17f5-484">应用事件处理程序后，调用[MSWebViewAsyncOperation](./webview/MSWebViewAsyncOperation.md)对象上的 start 方法以执行该操作。</span><span class="sxs-lookup"><span data-stu-id="f17f5-484">After applying the event handlers, call the start method on the [MSWebViewAsyncOperation](./webview/MSWebViewAsyncOperation.md) object to execute the operation.</span></span>

### <span data-ttu-id="f17f5-485">captureSelectedContentToDataPackageAsync</span><span class="sxs-lookup"><span data-stu-id="f17f5-485">captureSelectedContentToDataPackageAsync</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="f17f5-486">此方法已弃用，并且存在已知问题。</span><span class="sxs-lookup"><span data-stu-id="f17f5-486">This method has been deprecated and has a known issue.</span></span> <span data-ttu-id="f17f5-487">避免在成品代码中使用此方法。</span><span class="sxs-lookup"><span data-stu-id="f17f5-487">Avoid using this method in your production code.</span></span> 

<span data-ttu-id="f17f5-488">异步获取包含**web 视图**中所选内容的[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage) 。</span><span class="sxs-lookup"><span data-stu-id="f17f5-488">Asynchronously gets a [DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage) that contains the selected content within the **webview**.</span></span>

```js
var msWebViewAsyncOperation = webview.captureSelectedContentToDataPackageAsync();
```

#### <span data-ttu-id="f17f5-489">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-489">Parameters</span></span>
<span data-ttu-id="f17f5-490">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-490">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-491">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-491">Return value</span></span>
<span data-ttu-id="f17f5-492">类型： **MSWebViewAsyncOperation**</span><span class="sxs-lookup"><span data-stu-id="f17f5-492">Type: **MSWebViewAsyncOperation**</span></span>

<span data-ttu-id="f17f5-493">一个**MSWebViewAsyncOperation**对象，该对象在完成时提供包含图像的[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage)对象。</span><span class="sxs-lookup"><span data-stu-id="f17f5-493">An **MSWebViewAsyncOperation** object that, when it completes, provides a [DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage) object that contains the image.</span></span> <span data-ttu-id="f17f5-494">使用**captureSelectedContentToDataPackageAsync**时，你需要在定义操作后定义成功和错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="f17f5-494">When using **captureSelectedContentToDataPackageAsync**, you need to define success and error handlers after defining the operation.</span></span> <span data-ttu-id="f17f5-495">应用事件处理程序后，调用 MSWebViewAsyncOperation 对象上的 start 方法以执行该操作。</span><span class="sxs-lookup"><span data-stu-id="f17f5-495">After applying the event handlers, call the start method on the MSWebViewAsyncOperation object to execute the operation.</span></span>

```js
 var operation = webview.captureSelectedContentToDataPackageAsync();
    operation.oncomplete = function () {
        // operation.result is a package object that contains the selected data.
        var url = URL.createObjectURL(operation.result, { oneTimeOnly: true });
        // After converting the package to a URI, put it in an image element.
        document.getElementById('webviewPreview').src = url;
    };
    operation.start();  

```

### <span data-ttu-id="f17f5-496">invokeScriptAsync</span><span class="sxs-lookup"><span data-stu-id="f17f5-496">invokeScriptAsync</span></span>

<span data-ttu-id="f17f5-497">作为异步操作，使用特定参数从当前加载的 HTML 执行指定的脚本函数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-497">As an asynchronous action, executes the specified script function from the currently loaded HTML, with specific arguments.</span></span>

```js
webview.invokeScriptAsync(functionName, ...args)
```

#### <span data-ttu-id="f17f5-498">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-498">Parameters</span></span>

**<span data-ttu-id="f17f5-499">functionName</span><span class="sxs-lookup"><span data-stu-id="f17f5-499">functionName</span></span>**
* <span data-ttu-id="f17f5-500">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-500">Type: **String**</span></span>
* <span data-ttu-id="f17f5-501">要调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="f17f5-501">The name of the function to invoke.</span></span> <span data-ttu-id="f17f5-502">这是 Web 视图顶级文档的全局窗口对象上的属性名称。</span><span class="sxs-lookup"><span data-stu-id="f17f5-502">This is a property name on the global window object of the WebView's top level document.</span></span> <span data-ttu-id="f17f5-503">这可以是一个内置的全局函数（如 eval 或 open），也可以是全局窗口对象上的脚本定义函数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-503">This can be a built-in global function like eval or open, or it can be a script defined function on the global window object.</span></span> <span data-ttu-id="f17f5-504">仅可调用 Web 视图顶层文档中的函数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-504">Only functions in the top level document of the WebView may be invoked.</span></span>

**<span data-ttu-id="f17f5-505">args</span><span class="sxs-lookup"><span data-stu-id="f17f5-505">args</span></span>**
* <span data-ttu-id="f17f5-506">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-506">Type: **String**</span></span>
* <span data-ttu-id="f17f5-507">要传递到已调用函数的可选字符串参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-507">Optional string parameters to pass to the invoked function.</span></span> <span data-ttu-id="f17f5-508">在 functionName 之后，invokeScriptAsync 的任何其他参数都将传递到已调用函数的字符串。</span><span class="sxs-lookup"><span data-stu-id="f17f5-508">After functionName, any additional parameters to invokeScriptAsync are strings passed to the invoked function.</span></span>

#### <span data-ttu-id="f17f5-509">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-509">Return value</span></span>
<span data-ttu-id="f17f5-510">类型： **MSWebViewAsyncOperation**</span><span class="sxs-lookup"><span data-stu-id="f17f5-510">Type: **MSWebViewAsyncOperation**</span></span>

<span data-ttu-id="f17f5-511">使用**invokeScriptAsync**时，你需要在定义操作后定义成功和错误处理程序。</span><span class="sxs-lookup"><span data-stu-id="f17f5-511">When using **invokeScriptAsync**, you need to define success and error handlers after defining the operation.</span></span> <span data-ttu-id="f17f5-512">应用事件处理程序后，调用**MSWebViewAsyncOperation**以执行该操作。</span><span class="sxs-lookup"><span data-stu-id="f17f5-512">After applying the event handlers, call **MSWebViewAsyncOperation.start** to execute the operation.</span></span> <span data-ttu-id="f17f5-513">如果 MSWebViewAsyncOperation 的 complete 事件引发，则 MSWebViewAsyncOperation 的 result 属性是调用该函数的字符串返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-513">If the MSWebViewAsyncOperation's complete event fires then the MSWebViewAsyncOperation's result property is the string return value from invoking the function.</span></span> <span data-ttu-id="f17f5-514">使用被调用函数的返回值可使 Web 视图内容同步回 Web 视图主机。</span><span class="sxs-lookup"><span data-stu-id="f17f5-514">Using the invoked function's return value allows for the WebView content to communication synchronously back to the WebView host.</span></span> <span data-ttu-id="f17f5-515">若要改为将 Web 视图内容异步通信回 Web 视图主机，请参阅 MSWebViewScriptNotify 事件。</span><span class="sxs-lookup"><span data-stu-id="f17f5-515">To instead have the WebView content communicate asynchronously back to the WebView host see the MSWebViewScriptNotify event.</span></span> <span data-ttu-id="f17f5-516">如果调用的函数引发了一个未处理的异常，则将引发 MSWebViewAsyncOperation 的错误事件。</span><span class="sxs-lookup"><span data-stu-id="f17f5-516">If the function invoked throws an unhandled exception then the MSWebViewAsyncOperation's error event will fire.</span></span> 

```js
const functionName = "eval";
const args = ["'Current URL: ' + document.location.href"];

const asyncOp = webview.invokeScriptAsync(functionName, ...args);

asyncOp.onerror = () => console.error("Error: " + asyncOp.error);
asyncOp.oncomplete = () => console.log("Result: " + asyncOp.result); // Logs 'Current URL: about:blank'
asyncOp.start();
```

### <span data-ttu-id="f17f5-517">getDeferredPermissionRequests</span><span class="sxs-lookup"><span data-stu-id="f17f5-517">getDeferredPermissionRequests</span></span>

<span data-ttu-id="f17f5-518">返回由**web 视图**控件中的内容颁发的延迟权限请求的列表。</span><span class="sxs-lookup"><span data-stu-id="f17f5-518">Returns a list of deferred permission requests issued by content in the **webview** control.</span></span>

```js
var sequence<PermissionRequest> = x-ms-webview.getDeferredPermissionRequests();
```

#### <span data-ttu-id="f17f5-519">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-519">Parameters</span></span>
<span data-ttu-id="f17f5-520">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-520">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-521">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-521">Return value</span></span>
<span data-ttu-id="f17f5-522">类型： [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span><span class="sxs-lookup"><span data-stu-id="f17f5-522">Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span></span>

<span data-ttu-id="f17f5-523">指定的延迟权限请求。</span><span class="sxs-lookup"><span data-stu-id="f17f5-523">The specified deferred permission request.</span></span>

#### <span data-ttu-id="f17f5-524">其他功能和要求</span><span class="sxs-lookup"><span data-stu-id="f17f5-524">Additional features and requirements</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-525">最低受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="f17f5-525">Minimum supported client</span></span>** |<span data-ttu-id="f17f5-526">Windows10 [仅限 Windows 应用商店应用]</span><span class="sxs-lookup"><span data-stu-id="f17f5-526">Windows10 [Windows Store apps only]</span></span> |    
|**<span data-ttu-id="f17f5-527">最低受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="f17f5-527">Minimum supported server</span></span>** |<span data-ttu-id="f17f5-528">无受支持的版本</span><span class="sxs-lookup"><span data-stu-id="f17f5-528">None supported</span></span>|   
|**<span data-ttu-id="f17f5-529">最低受支持的电话</span><span class="sxs-lookup"><span data-stu-id="f17f5-529">Minimum supported phone</span></span>**  |<span data-ttu-id="f17f5-530">无受支持的版本</span><span class="sxs-lookup"><span data-stu-id="f17f5-530">None supported</span></span> |    


### <span data-ttu-id="f17f5-531">getDeferredPermissionRequestById</span><span class="sxs-lookup"><span data-stu-id="f17f5-531">getDeferredPermissionRequestById</span></span>

<span data-ttu-id="f17f5-532">返回指定的延迟权限请求。</span><span class="sxs-lookup"><span data-stu-id="f17f5-532">Returns the specified deferred permission request.</span></span> 

```js
var deferredPermissionRequest = x-ms-webview.getDeferredPermissionRequestById(id);
```

#### <span data-ttu-id="f17f5-533">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-533">Parameters</span></span>
*<span data-ttu-id="f17f5-534">id</span><span class="sxs-lookup"><span data-stu-id="f17f5-534">id</span></span>*
* <span data-ttu-id="f17f5-535">类型：**无符号长**</span><span class="sxs-lookup"><span data-stu-id="f17f5-535">Type: **unsigned long**</span></span>
* <span data-ttu-id="f17f5-536">希望获取的延迟权限请求的 ID。</span><span class="sxs-lookup"><span data-stu-id="f17f5-536">The ID of the deferred permission request you wish to get.</span></span>

#### <span data-ttu-id="f17f5-537">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-537">Return value</span></span>
<span data-ttu-id="f17f5-538">类型： [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span><span class="sxs-lookup"><span data-stu-id="f17f5-538">Type: [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)</span></span>

<span data-ttu-id="f17f5-539">指定的延迟权限请求。</span><span class="sxs-lookup"><span data-stu-id="f17f5-539">The specified deferred permission request.</span></span>

#### <span data-ttu-id="f17f5-540">其他功能和要求</span><span class="sxs-lookup"><span data-stu-id="f17f5-540">Additional features and requirements</span></span>

|            |      |
|------------|------|
|**<span data-ttu-id="f17f5-541">最低受支持的客户端</span><span class="sxs-lookup"><span data-stu-id="f17f5-541">Minimum supported client</span></span>** |<span data-ttu-id="f17f5-542">Windows10 [仅限 Windows 应用商店应用]</span><span class="sxs-lookup"><span data-stu-id="f17f5-542">Windows10 [Windows Store apps only]</span></span> |    
|**<span data-ttu-id="f17f5-543">最低受支持的服务器</span><span class="sxs-lookup"><span data-stu-id="f17f5-543">Minimum supported server</span></span>** |<span data-ttu-id="f17f5-544">无受支持的版本</span><span class="sxs-lookup"><span data-stu-id="f17f5-544">None supported</span></span>|   
|**<span data-ttu-id="f17f5-545">最低受支持的电话</span><span class="sxs-lookup"><span data-stu-id="f17f5-545">Minimum supported phone</span></span>**  |<span data-ttu-id="f17f5-546">无受支持的版本</span><span class="sxs-lookup"><span data-stu-id="f17f5-546">None supported</span></span> | 

### <span data-ttu-id="f17f5-547">goBack</span><span class="sxs-lookup"><span data-stu-id="f17f5-547">goBack</span></span>

<span data-ttu-id="f17f5-548">将**web 视图**导航到导航历史记录中的上一页。</span><span class="sxs-lookup"><span data-stu-id="f17f5-548">Navigates the **webview** to the previous page in the navigation history.</span></span> 

```js
webview.goBack();
```

#### <span data-ttu-id="f17f5-549">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-549">Parameters</span></span>
<span data-ttu-id="f17f5-550">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-550">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-551">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-551">Return value</span></span>
<span data-ttu-id="f17f5-552">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-552">This method does not return a value.</span></span>

### <span data-ttu-id="f17f5-553">goForward</span><span class="sxs-lookup"><span data-stu-id="f17f5-553">goForward</span></span>

<span data-ttu-id="f17f5-554">将**web 视图**导航到导航历史记录中的下一页。</span><span class="sxs-lookup"><span data-stu-id="f17f5-554">Navigates the **webview** to the next page in the navigation history.</span></span> 

```js
webview.goForward();
```

#### <span data-ttu-id="f17f5-555">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-555">Parameters</span></span>
<span data-ttu-id="f17f5-556">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-556">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-557">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-557">Return value</span></span>
<span data-ttu-id="f17f5-558">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-558">This method does not return a value.</span></span>

### <span data-ttu-id="f17f5-559">导航</span><span class="sxs-lookup"><span data-stu-id="f17f5-559">navigate</span></span>

<span data-ttu-id="f17f5-560">在指定的统一资源标识符（URI）处加载 HTML 内容。</span><span class="sxs-lookup"><span data-stu-id="f17f5-560">Loads the HTML content at the specified Uniform Resource Identifier (URI).</span></span> 

```js
webview.navigate(uri);
```

#### <span data-ttu-id="f17f5-561">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-561">Parameters</span></span>

**<span data-ttu-id="f17f5-562">uri</span><span class="sxs-lookup"><span data-stu-id="f17f5-562">uri</span></span>**
* <span data-ttu-id="f17f5-563">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-563">Type: **String**</span></span>
* <span data-ttu-id="f17f5-564">要加载的 URI。</span><span class="sxs-lookup"><span data-stu-id="f17f5-564">The URI to load.</span></span>

#### <span data-ttu-id="f17f5-565">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-565">Return value</span></span>
<span data-ttu-id="f17f5-566">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-566">This  method does not return a value.</span></span>

### <span data-ttu-id="f17f5-567">navigateFocus</span><span class="sxs-lookup"><span data-stu-id="f17f5-567">navigateFocus</span></span>

<span data-ttu-id="f17f5-568">将焦点导航到**web 视图**。</span><span class="sxs-lookup"><span data-stu-id="f17f5-568">Navigates focus onto the **webview**.</span></span> <span data-ttu-id="f17f5-569">激发 web 视图的顶级文档的 window's navigatingfocus 事件。</span><span class="sxs-lookup"><span data-stu-id="f17f5-569">Fires the webview's top level document's window's navigatingfocus event.</span></span> <span data-ttu-id="f17f5-570">Navigatingfocus 事件中使用的 FocusNavigationEvent 参数与提供给 navigateFocus 的参数相匹配，但原始参数从宿主文档的坐标空间转换为 web 视图的顶级文档的坐标空间。</span><span class="sxs-lookup"><span data-stu-id="f17f5-570">The FocusNavigationEvent args used in the navigatingfocus event match the parameters provided to navigateFocus except the origin parameters are translated from the host document's coordinate space to the coordinate space of the webview's top level document.</span></span> <span data-ttu-id="f17f5-571">请参阅 web 视图 departingFocus 事件和相应的窗口。 departFocus 方法，用于将焦点从 web 视图转移到主机。</span><span class="sxs-lookup"><span data-stu-id="f17f5-571">See the webview departingFocus event and corresponding window.departFocus method for transferring focus from the webview to the host.</span></span> <span data-ttu-id="f17f5-572">有关通过使用此方法的键盘或游戏板实现焦点导航的示例，请参阅[TVJS 的方向导航库](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)。</span><span class="sxs-lookup"><span data-stu-id="f17f5-572">See the [TVJS's Direction Navigation library](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation) for an example of an implementation of focus navigation via keyboard or gamepad that uses this method.</span></span>

```js
const activeElementBounds = document.activeElement.getBoundingClientRect();
const origin = { 
    originLeft: activeElementBounds.left,
    originTop: activeElementBounds.top,
    originWidth: activeElementBounds.width,
    originHeight: activeElementBounds.height
};
webview.navigateFocus(navigationReason, origin);
```

#### <span data-ttu-id="f17f5-573">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-573">Parameters</span></span>
*<span data-ttu-id="f17f5-574">navigationReason</span><span class="sxs-lookup"><span data-stu-id="f17f5-574">navigationReason</span></span>*
* <span data-ttu-id="f17f5-575">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-575">Type: **String**</span></span>
* <span data-ttu-id="f17f5-576">导航的原因。</span><span class="sxs-lookup"><span data-stu-id="f17f5-576">The reason for the navigation.</span></span> <span data-ttu-id="f17f5-577">此值应为 "左"、"上"、"右" 或 "下"。</span><span class="sxs-lookup"><span data-stu-id="f17f5-577">The value should be either "left", "up", "right", or "down".</span></span> <span data-ttu-id="f17f5-578">焦点从当前焦点的元素移开的方向。</span><span class="sxs-lookup"><span data-stu-id="f17f5-578">It is the direction in which focus is moving away from the currently focused element.</span></span>

*<span data-ttu-id="f17f5-579">原</span><span class="sxs-lookup"><span data-stu-id="f17f5-579">origin</span></span>*
* <span data-ttu-id="f17f5-580">类型：**对象**</span><span class="sxs-lookup"><span data-stu-id="f17f5-580">Type: **Object**</span></span>
* <span data-ttu-id="f17f5-581">导航的来源。</span><span class="sxs-lookup"><span data-stu-id="f17f5-581">The origin of the navigation.</span></span> <span data-ttu-id="f17f5-582">这是一个 JavaScript 对象，其属性为 "originLeft"、"originTop"、"originWidth" 和 "originHeight"。</span><span class="sxs-lookup"><span data-stu-id="f17f5-582">This is a JavaScript object with properties "originLeft", "originTop", "originWidth", and "originHeight".</span></span> <span data-ttu-id="f17f5-583">这些值应描述当前焦点元素远离焦点移动的位置和大小。</span><span class="sxs-lookup"><span data-stu-id="f17f5-583">These values should describe the position and size of the currently focused element away from which focus is moving.</span></span>

#### <span data-ttu-id="f17f5-584">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-584">Return value</span></span>
<span data-ttu-id="f17f5-585">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-585">This method does not return a value.</span></span>

### <span data-ttu-id="f17f5-586">navigateToLocalStreamUri</span><span class="sxs-lookup"><span data-stu-id="f17f5-586">navigateToLocalStreamUri</span></span>

<span data-ttu-id="f17f5-587">使用[**UriToStreamResolver**](/uwp/api/windows.web.iuritostreamresolver.uritostreamasync)在指定 URI 处加载本地 web 内容。</span><span class="sxs-lookup"><span data-stu-id="f17f5-587">Loads local web content at the specified URI using a [**UriToStreamResolver**](/uwp/api/windows.web.iuritostreamresolver.uritostreamasync).</span></span>

```js
webview.navigateToLocalStreamUri(source, streamResolver); 
```

#### <span data-ttu-id="f17f5-588">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-588">Parameters</span></span>

*<span data-ttu-id="f17f5-589">从源</span><span class="sxs-lookup"><span data-stu-id="f17f5-589">source</span></span>*
* <span data-ttu-id="f17f5-590">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-590">Type: **String**</span></span>
* <span data-ttu-id="f17f5-591">标识要加载的本地 HTML 内容的 ms 本地流 URI。</span><span class="sxs-lookup"><span data-stu-id="f17f5-591">An ms-local-stream URI identifying the local HTML content to load.</span></span> <span data-ttu-id="f17f5-592">使用[**buildLocalStreamUri**](/uwp/api/windows.web.ui.iwebviewcontrol.buildlocalstreamuri)创建此字符串。</span><span class="sxs-lookup"><span data-stu-id="f17f5-592">Create this string using [**buildLocalStreamUri**](/uwp/api/windows.web.ui.iwebviewcontrol.buildlocalstreamuri).</span></span>

*<span data-ttu-id="f17f5-593">streamResolver</span><span class="sxs-lookup"><span data-stu-id="f17f5-593">streamResolver</span></span>*
* <span data-ttu-id="f17f5-594">类型：任何</span><span class="sxs-lookup"><span data-stu-id="f17f5-594">Type: any</span></span>
* <span data-ttu-id="f17f5-595">将 URI 转换为流以加载的冲突解决程序。</span><span class="sxs-lookup"><span data-stu-id="f17f5-595">A resolver that converts the URI into a stream to load.</span></span>

#### <span data-ttu-id="f17f5-596">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-596">Return value</span></span>
<span data-ttu-id="f17f5-597">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-597">This method does not return a value.</span></span>

### <span data-ttu-id="f17f5-598">navigateToString</span><span class="sxs-lookup"><span data-stu-id="f17f5-598">navigateToString</span></span>

<span data-ttu-id="f17f5-599">将指定的 HTML 内容加载为新文档。</span><span class="sxs-lookup"><span data-stu-id="f17f5-599">Loads the specified HTML content as a new document.</span></span> 

```js
webview.navigateToString(contents);
```

#### <span data-ttu-id="f17f5-600">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-600">Parameters</span></span>

*<span data-ttu-id="f17f5-601">内容</span><span class="sxs-lookup"><span data-stu-id="f17f5-601">contents</span></span>*
* <span data-ttu-id="f17f5-602">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-602">Type: **String**</span></span>
* <span data-ttu-id="f17f5-603">要显示的 HTML 内容。</span><span class="sxs-lookup"><span data-stu-id="f17f5-603">The HTML content to display.</span></span>

#### <span data-ttu-id="f17f5-604">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-604">Return value</span></span>
<span data-ttu-id="f17f5-605">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-605">This method does not return a value.</span></span>

### <span data-ttu-id="f17f5-606">navigateWithHttpRequestMessage</span><span class="sxs-lookup"><span data-stu-id="f17f5-606">navigateWithHttpRequestMessage</span></span>

<span data-ttu-id="f17f5-607">使用 POST 请求和 HTTP 标头将 web 视图导航到统一资源标识符（URI）。</span><span class="sxs-lookup"><span data-stu-id="f17f5-607">Navigates the webview to a Uniform Resource Identifier (URI) with a POST request and HTTP headers.</span></span> 

```js
webview.navigateWithHttpRequestMessage(requestMessage);
```

#### <span data-ttu-id="f17f5-608">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-608">Parameters</span></span>

*<span data-ttu-id="f17f5-609">requestMessage</span><span class="sxs-lookup"><span data-stu-id="f17f5-609">requestMessage</span></span>*
* <span data-ttu-id="f17f5-610">类型： **HttpRequestMessage**</span><span class="sxs-lookup"><span data-stu-id="f17f5-610">Type: **HttpRequestMessage**</span></span>
* <span data-ttu-id="f17f5-611">HTTP 请求的详细信息。</span><span class="sxs-lookup"><span data-stu-id="f17f5-611">The details of the HTTP request.</span></span> 

#### <span data-ttu-id="f17f5-612">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-612">Return value</span></span>
<span data-ttu-id="f17f5-613">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-613">This method does not return a value.</span></span>

#### <span data-ttu-id="f17f5-614">备注</span><span class="sxs-lookup"><span data-stu-id="f17f5-614">Remarks</span></span>

> [!WARNING]
> <span data-ttu-id="f17f5-615">如果为此请求添加其他标头（如身份验证凭据），请记住这些标题也将包含在任何后续子请求中。</span><span class="sxs-lookup"><span data-stu-id="f17f5-615">If you add additional headers to this request, such as authentication credentials, remember that those headers will also be included with any subsequent child requests.</span></span> <span data-ttu-id="f17f5-616">请注意防止意外泄漏机密或个人信息。</span><span class="sxs-lookup"><span data-stu-id="f17f5-616">Use caution to prevent accidental disclosure of confidential or personal information.</span></span> 


### <span data-ttu-id="f17f5-617">恢复</span><span class="sxs-lookup"><span data-stu-id="f17f5-617">refresh</span></span> 

<span data-ttu-id="f17f5-618">重新加载**web 视图**中的当前内容。</span><span class="sxs-lookup"><span data-stu-id="f17f5-618">Reloads the current content in the **webview**.</span></span> 

```js
webview.refresh();
```

#### <span data-ttu-id="f17f5-619">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-619">Parameters</span></span>
<span data-ttu-id="f17f5-620">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-620">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-621">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-621">Return value</span></span>
<span data-ttu-id="f17f5-622">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-622">This method does not return a value.</span></span>


### <span data-ttu-id="f17f5-623">stop</span><span class="sxs-lookup"><span data-stu-id="f17f5-623">stop</span></span>

<span data-ttu-id="f17f5-624">暂停当前**web 视图**导航或下载。</span><span class="sxs-lookup"><span data-stu-id="f17f5-624">Halts the current **webview** navigation or download.</span></span> 

```js
webview.stop();
```

#### <span data-ttu-id="f17f5-625">参数</span><span class="sxs-lookup"><span data-stu-id="f17f5-625">Parameters</span></span>
<span data-ttu-id="f17f5-626">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="f17f5-626">This method has no parameters.</span></span>

#### <span data-ttu-id="f17f5-627">返回值</span><span class="sxs-lookup"><span data-stu-id="f17f5-627">Return value</span></span>
<span data-ttu-id="f17f5-628">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="f17f5-628">This method does not return a value.</span></span>


## <span data-ttu-id="f17f5-629">属性</span><span class="sxs-lookup"><span data-stu-id="f17f5-629">Properties</span></span>

### <span data-ttu-id="f17f5-630">canGoBack</span><span class="sxs-lookup"><span data-stu-id="f17f5-630">canGoBack</span></span>

<span data-ttu-id="f17f5-631">获取一个值，该值指示**web 视图**是否可以向后导航。</span><span class="sxs-lookup"><span data-stu-id="f17f5-631">Gets a value that indicates whether the **webview** can navigate backward.</span></span>

<span data-ttu-id="f17f5-632">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f17f5-632">This property is read-only.</span></span>

```js
var canGoBack = webview.canGoBack;
```

#### <span data-ttu-id="f17f5-633">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-633">Property value</span></span>
<span data-ttu-id="f17f5-634">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="f17f5-634">Type: **Boolean**</span></span>

<span data-ttu-id="f17f5-635">如果**web 视图**可以向后导航，**则为 True** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="f17f5-635">**True** if the **webview** can navigate backward; otherwise, **false**.</span></span>

### <span data-ttu-id="f17f5-636">canGoForward</span><span class="sxs-lookup"><span data-stu-id="f17f5-636">canGoForward</span></span>

<span data-ttu-id="f17f5-637">获取一个值，该值指示**web 视图**是否可以向前导航。</span><span class="sxs-lookup"><span data-stu-id="f17f5-637">Gets a value that indicates whether the **webview** can navigate forward.</span></span>

<span data-ttu-id="f17f5-638">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f17f5-638">This property is read-only.</span></span>

```js
var canGoForward = webview.canGoForward;
```

#### <span data-ttu-id="f17f5-639">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-639">Property value</span></span>
<span data-ttu-id="f17f5-640">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="f17f5-640">Type: **Boolean**</span></span>

<span data-ttu-id="f17f5-641">如果**web 视图**可以向前导航，**则为 True** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="f17f5-641">**True** if the **webview** can navigate forward; otherwise, **false**.</span></span>

### <span data-ttu-id="f17f5-642">containsFullScreenElement</span><span class="sxs-lookup"><span data-stu-id="f17f5-642">containsFullScreenElement</span></span>

<span data-ttu-id="f17f5-643">获取一个值，该值指示**web 视图**是否包含支持全屏幕的元素。</span><span class="sxs-lookup"><span data-stu-id="f17f5-643">Gets a value that indicates whether the **webview** contains an element that supports full screen.</span></span> <span data-ttu-id="f17f5-644">有关详细信息，请参阅 MSWebViewContainsFullScreenElementChanged 事件。</span><span class="sxs-lookup"><span data-stu-id="f17f5-644">See the MSWebViewContainsFullScreenElementChanged event for more info.</span></span>

<span data-ttu-id="f17f5-645">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f17f5-645">This property is read-only.</span></span>

```js
var containsFullScreenElement = webview.containsFullScreenElement;
```

#### <span data-ttu-id="f17f5-646">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-646">Property value</span></span>
<span data-ttu-id="f17f5-647">类型： **Boolean**</span><span class="sxs-lookup"><span data-stu-id="f17f5-647">Type: **Boolean**</span></span>

<span data-ttu-id="f17f5-648">如果**web 视图**包含支持全屏的元素，**则为 True** ;否则**为 false**。</span><span class="sxs-lookup"><span data-stu-id="f17f5-648">**True** if the **webview** contains an element that supports full screen; otherwise, **false**.</span></span>


### <span data-ttu-id="f17f5-649">documentTitle</span><span class="sxs-lookup"><span data-stu-id="f17f5-649">documentTitle</span></span>

<span data-ttu-id="f17f5-650">获取**web 视图**中当前显示的页面的标题。</span><span class="sxs-lookup"><span data-stu-id="f17f5-650">Gets the title of the page currently displayed in the **webview**.</span></span> 

<span data-ttu-id="f17f5-651">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f17f5-651">This property is read-only.</span></span>

```js
var documentTitle = webview.documentTitle;
```

#### <span data-ttu-id="f17f5-652">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-652">Property value</span></span>
<span data-ttu-id="f17f5-653">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-653">Type: **String**</span></span>

<span data-ttu-id="f17f5-654">页面标题。</span><span class="sxs-lookup"><span data-stu-id="f17f5-654">The page title.</span></span>

### <span data-ttu-id="f17f5-655">height</span><span class="sxs-lookup"><span data-stu-id="f17f5-655">height</span></span>

<span data-ttu-id="f17f5-656">获取或设置**web 视图**的高度。</span><span class="sxs-lookup"><span data-stu-id="f17f5-656">Gets or sets the height of the **webview**.</span></span> 

```js
var height = webview.height;
webview.height = height;

```

#### <span data-ttu-id="f17f5-657">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-657">Property value</span></span>
<span data-ttu-id="f17f5-658">类型：**数字**</span><span class="sxs-lookup"><span data-stu-id="f17f5-658">Type: **Number**</span></span>

<span data-ttu-id="f17f5-659">**Web 视图**的高度。</span><span class="sxs-lookup"><span data-stu-id="f17f5-659">The height of the **webview**.</span></span> 


### <span data-ttu-id="f17f5-660">进程</span><span class="sxs-lookup"><span data-stu-id="f17f5-660">process</span></span>

<span data-ttu-id="f17f5-661">获取**web 视图**进程。</span><span class="sxs-lookup"><span data-stu-id="f17f5-661">Gets the **webview** process.</span></span>

<span data-ttu-id="f17f5-662">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f17f5-662">This property is read-only.</span></span>

```js
var process = webview.process;
webview.process = process;
```

#### <span data-ttu-id="f17f5-663">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-663">Property value</span></span>
<span data-ttu-id="f17f5-664">类型： [MSWebViewProcess](./webview/MSWebViewProcess.md)</span><span class="sxs-lookup"><span data-stu-id="f17f5-664">Type: [MSWebViewProcess](./webview/MSWebViewProcess.md)</span></span>


### <span data-ttu-id="f17f5-665">settings</span><span class="sxs-lookup"><span data-stu-id="f17f5-665">settings</span></span>

<span data-ttu-id="f17f5-666">获取一个[MSWebViewSettings](./webview/MSWebViewSettings.md)对象，该对象包含用于启用或禁用**web 视图**功能的属性。</span><span class="sxs-lookup"><span data-stu-id="f17f5-666">Gets a [MSWebViewSettings](./webview/MSWebViewSettings.md) object that contains properties to enable or disable **webview** features.</span></span>

<span data-ttu-id="f17f5-667">此属性为只读。</span><span class="sxs-lookup"><span data-stu-id="f17f5-667">This property is read-only.</span></span>

```js
var settings = webview.settings;
webview.settings = settings;
```

#### <span data-ttu-id="f17f5-668">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-668">Property value</span></span>
<span data-ttu-id="f17f5-669">类型： [MSWebViewSettings](./webview/MSWebViewSettings.md)</span><span class="sxs-lookup"><span data-stu-id="f17f5-669">Type: [MSWebViewSettings](./webview/MSWebViewSettings.md)</span></span>

<span data-ttu-id="f17f5-670">一个[MSWebViewSettings](./webview/MSWebViewSettings.md)对象，其中包含用于启用或禁用**web 视图**功能的属性。</span><span class="sxs-lookup"><span data-stu-id="f17f5-670">A [MSWebViewSettings](./webview/MSWebViewSettings.md) object that contains properties to enable or disable **webview** features.</span></span>

### <span data-ttu-id="f17f5-671">src</span><span class="sxs-lookup"><span data-stu-id="f17f5-671">src</span></span>

<span data-ttu-id="f17f5-672">获取或设置要在**web 视图**控件中显示的 HTML 内容的统一资源标识符（URI）源。</span><span class="sxs-lookup"><span data-stu-id="f17f5-672">Gets or sets the Uniform Resource Identifier (URI) source of the HTML content to display in the **webview** control.</span></span> 

```js
var src = webview.src;
webview.src = src;
```

#### <span data-ttu-id="f17f5-673">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-673">Property value</span></span>
<span data-ttu-id="f17f5-674">类型： **String**</span><span class="sxs-lookup"><span data-stu-id="f17f5-674">Type: **String**</span></span>

<span data-ttu-id="f17f5-675">要在**web 视图**控件中显示的 HTML 内容的 URI 源。</span><span class="sxs-lookup"><span data-stu-id="f17f5-675">The URI source of the HTML content to display in the **webview** control.</span></span> 


### <span data-ttu-id="f17f5-676">width</span><span class="sxs-lookup"><span data-stu-id="f17f5-676">width</span></span>

<span data-ttu-id="f17f5-677">获取或设置**web 视图**的宽度。</span><span class="sxs-lookup"><span data-stu-id="f17f5-677">Gets or sets the width of the **webview**.</span></span>

```js
var width = webview.width;
webview.width = width;
```

#### <span data-ttu-id="f17f5-678">属性值</span><span class="sxs-lookup"><span data-stu-id="f17f5-678">Property value</span></span>
<span data-ttu-id="f17f5-679">类型：**数字**</span><span class="sxs-lookup"><span data-stu-id="f17f5-679">Type: **Number**</span></span>

<span data-ttu-id="f17f5-680">**Web 视图**的宽度。</span><span class="sxs-lookup"><span data-stu-id="f17f5-680">The width of the **webview**.</span></span>
