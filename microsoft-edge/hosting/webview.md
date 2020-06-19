---
description: 通过 web 视图（EdgeHTML）控件在 Windows 10 应用中托管 web 内容
title: 适用于 Windows 10 应用的 Microsoft Edge Web 视图
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/08/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.technology: webview
keywords: x-ms-web 视图、MSHTMLWebViewElement、web 视图、windows 10 应用、uwp、edge
ms.openlocfilehash: aa9bef7bf214cf4f4ffdb4d68ad3a1a86ac2977b
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752204"
---
# 适用于 Windows 10 应用的 Web 视图（EdgeHTML）  

[!INCLUDE [deprecation-note](./includes/deprecation-note.md)]  

Web 视图（EdgeHTML）控件使你能够在 Windows 10 应用中托管 web 内容。  

对于基于 JavaScript 的 Windows 10 应用，你可以将其用作 XAML 元素（对于[通用 Windows 平台（UWP）应用](/uwp/api/Windows.UI.Xaml.Controls.WebView)和[Windows 窗体和 WPF 桌面应用程序](/windows/communitytoolkit/controls/wpf-winforms/webview)）或 HTML 元素（x ms-web 视图）/dom 对象（MSHTMLWebViewElement），如下所述。  

|  |  |  
|:--- |:--- |  
| [**事件**](#events) | [departingFocus](#departingfocus)、 [MSWebViewContainsFullScreenElementChanged](#mswebviewcontainsfullscreenelementchanged)、 [MSWebViewContentLoading](#mswebviewcontentloading)、 [MSWebViewDOMContentLoaded](#mswebviewdomcontentloaded)、 [MSWebViewFrameContentLoading](#mswebviewframecontentloading)、 [MSWebViewFrameDOMContentLoaded](#mswebviewframedomcontentloaded)、 [MSWebViewFrameNavigationCompleted、MSWebViewFrameNavigationStarting](#mswebviewframenavigationcompleted) [、MSWebViewLongRunningScriptDetected](#mswebviewframenavigationstarting)、 [MSWebViewNavigationCompleted](#mswebviewnavigationcompleted)、 [MSWebViewNavigationStarting](#mswebviewnavigationstarting)、 [MSWebViewNewWindowRequested](#mswebviewnewwindowrequested)、 [MSWebViewPermissionRequested](#mswebviewpermissionrequested)、 [MSWebViewProcessExited、MSWebViewWebResourceRequested](#mswebviewprocessexited) [、MSWebViewScriptNotify](#mswebviewwebresourcerequested) [、MSWebViewUnsafeContentWarningDisplaying](#mswebviewscriptnotify) [、MSWebViewUnsupportedUriSchemeIdentified](#mswebviewunsafecontentwarningdisplaying) [、MSWebViewUnviewableContentIdentified](#mswebviewunsupportedurischemeidentified)、、、 [、、](#mswebviewunviewablecontentidentified) 、 [MSWebViewLongRunningScriptDetected](#mswebviewlongrunningscriptdetected) |  
| [**方法**](#methods) | [webview.addweballowedobject](#addweballowedobject)、 [buildlocalStreamUri](#buildlocalstreamuri)、 [capturePreviewToBlobAsync](#capturepreviewtoblobasync)、 [captureSelectedContentToDataPackageAsync](#captureselectedcontenttodatapackageasync)、 [invokeScriptAsync](#invokescriptasync)、 [getDeferredPermissionRequests](#getdeferredpermissionrequests)、 [getDeferredPermissionRequestById](#getdeferredpermissionrequestbyid)、 [goBack](#goback)、 [goForward](#goforward)、[导航](#navigate)、 [navigateFocus](#navigatefocus)、 [navigateTolocalStreamUri](#navigatetolocalstreamuri)、 [navigateToString](#navigatetostring)、 [navigateWithHttpRequestMessage](#navigatewithhttprequestmessage)、 [refresh](#refresh)、 [stop](#stop) |  
| [**属性**](#properties) | [canGoBack](#cangoback)、 [canGoForward](#cangoforward)、 [containsFullScreenElement](#containsfullscreenelement)、 [documentTitle](#documenttitle)、 [height](#height)、 [process](#process)、 [settings](#settings)、 [src](#src)、 [width](#width) |  

## 语法  

```javascript
// Feature detect for webview support
if (MSHTMLWebViewElement) {
    let wv = document.createElement('x-ms-webview'); // Use CSS to set width, height and other styles
    wv.navigate("https://www.example.com");
    document.body.appendChild(wv);
}
```  

## 备注  

### Web 视图与 iframe  

与标准 HTML [iframe](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)元素一样，你可以使用 web 视图通过来自你的应用包的 HTTP 和本地页面（*ms-appx-web//*）加载远程页面。  但是，Web 视图还可以：  

*   从你的[ApplicationData](/uwp/api/Windows.Storage.ApplicationData) （本地、漫游、临时）文件夹（*ms-appdata///*）和[内存中流](/microsoft-edge/hosting/webview#buildlocalstreamuri)（*ms-stream*：///）加载页面和资源  
*   提供类似浏览器的控件：用于在导航历史记录中[后退](#goback)和[前进](#goforward)以及[停止](#stop)或[刷新](#refresh)当前页。  
*   [捕获 web 内容的屏幕截图](#capturepreviewtoblobasync)，以便轻松实现 Windows 10 应用[共享](/windows/uwp/app-to-app/share-data)合约。  
*   允许在 web 视图内运行的 JavaScript 代码将自定义事件（[MSWebViewScriptNotify](#mswebviewscriptnotify)）提升到你的应用，并允许你的应用在 web 视图（[invokeScriptAsync](#invokescriptasync)）内运行 JavaScript。  
*   向您提供微调的 web 视图内容事件：  
    
    | Web 视图 DOM 事件 | 描述 |  
    |:--- |:--- |  
    | [MSWebViewNavigationStarting](#mswebviewnavigationstarting) | 指示 Web 视图正在开始导航。  |  
    | [MSWebViewContentLoading](#mswebviewcontentloading) | HTML 内容将下载并加载到控件中。  |  
    | [MSWebViewDOMContentLoaded](#mswebviewdomcontentloaded) | 指示主 DOM 元素已完成加载。  |  
    | [MSWebViewNavigationCompleted](#mswebviewnavigationcompleted) | 指示导航完成，并呈现所有媒体元素。  |  
    | [MSWebViewUnviewableContentIdentified](#mswebviewunviewablecontentidentified) | Web 视图发现内容不是 HTML。  |  
    | [UnsafeContentWarningDisplaying](#mswebviewunsafecontentwarningdisplaying) | Web 视图将显示一个警告页面，显示 Windows *SmartScreen 筛选器*报告为不安全的内容。  |  
    
    ...包括在 Web 视图内加载的 iframe 内容的相应[事件](#events)（如[MSWebView**Frame**NavigationStarting](#mswebviewframenavigationstarting)等）。 

### 打印  

打印使用 JavaScript 的 Windows 应用时，将在 `<x-ms-webview>` 打印之前将标记转换为 `<iframe>` 标记。  除了屏幕上显示屏幕和为打印呈现的一般区别之外，应用于元素的 CSS 样式 `<iframe>` 也适用于 `<iframe>` 转换的 `<x-ms-webview>` 。  

### 服务工作人员  

从[2018 年10月的更新](/windows/uwp/whats-new/windows-10-build-17763)（EdgeHTML 18）开始， [web 视图控件支持服务工作人员](/microsoft-edge/dev-guide#service-workers)（除了 Microsoft Edge 浏览器和带有 JavaScript 的 Windows 10 应用）。  

x64 应用体系结构需要中立（任何 CPU）或 x64 程序包，因为 WoW64 进程不支持服务工作人员。  （为节省磁盘空间，所需 Dll 的 WoW 版本不是本机包含在 Windows 中。）  

### 线程模型和可靠性  

通过标记创建 Web 视图 `document.createElement("x-ms-webview")` 或通过标记创建 web 视图 `<x-ms-webview>` 在应用进程中的新唯一线程上创建 web 视图。  在新的唯一线程上运行意味着来自一个 Web 视图的长时间运行脚本无法挂起应用或其他 WebViews。  通过构造函数创建 Web 视图 `new MSWebView()` 在单独的 Web 视图进程中创建 Web 视图。  在唯一进程中运行意味着除了对长时间运行的脚本进行保护之外，应用还会受到阻止 web 视图进程的 web 内容的保护。  通过该方法创建 Web 视图 [`MSWebViewProcess.createWebViewAsync`](./webview/MSWebViewProcess.md#createwebviewasync) 还会在单独的进程中创建 Web 视图，但允许调用方更好地控制进程设置和在 Web 视图进程中分组 WebViews。  有关详细信息，请参阅 `MSWebViewProcess`。  

### WinRT API 访问  

UWP 应用可能允许 WebViews 中的 HTML 文档具有对 WinRT Api 的访问权限。  这是通过 UWP 应用的 AppxManifest.xml 的 ApplicationContentUriRules 元素的规则子元素的 WindowsRuntimeAccess 属性。  将 WindowsRuntimeAccess 设置为 "all"，允许使用匹配 Uri 的 HTML 文档使用 WinRT。  这与在 JavaScript UWP 应用中为 HTML 内容提供 WinRT 访问的方式相同，因此请参阅[PWA 中的调用 WinRT api](/microsoft-edge/progressive-web-apps-edgehtml/windows-features#call-winrt-apis-from-your-pwa)了解详细信息。  

从运行在其自己的线程上的 Web 视图调用时，与 UI 相关的 WinRT Api 可能不起作用，但在从单独的 Web 源进程中运行的 Web 视图调用时可能会运行。  在其自己的唯一线程上使用 Web 视图时，该线程不是应用的视图线程。  需要从应用的视图线程调用某些与 UI 相关的 WinRT Api。  在单独的 Web 视图进程中创建的 WebViews 在视图线程上运行，因此不应面临与在其自己的唯一线程上运行 Web 视图时相同的限制。  如果在 Web 视图中使用与 UI 相关的 WinRT Api 时遇到问题，请确保你在其自己的 Web 视图进程中使用 Web 视图（如上所述）。  

### AppCache 存储限制  

使用 JavaScript[规范](https://go.microsoft.com/fwlink/p/?LinkId=228542)中定义的应用程序缓存 API （或 AppCache）的 JavaScript 支持应用程序，创建脱机 web 应用程序必须遵守可用的存储限制。  这在内存空间有限的设备中尤其如此。  对 AppCache 大小的实际限制始终是可用磁盘存储空间的功能。  下面显示了一般指南。  

| 卷大小 |每个域的 AppCache | AppCache 每位用户 |  
|:--- |:--- |:--- |  
| 高达4GB | 10MB | 50MB |  
| 4GB 到 4 GB | 50MB | 500MB |  
| 达 32 GB | 50MB | 甚至 |  

所有 Windows10 应用都旨在使用相同的 AppCache 配额模型，因此可用磁盘存储限制适用于桌面和手机应用。  在**Web 视图**内加载的页面已占用 1 GB 的*AppCache*空间后，也会出现硬限制;超过此限额的其他*AppCache*存储的请求将被拒绝。  

有关详细信息，请参阅[HTML Web 视图控件示例](https://go.microsoft.com/fwlink/p/?linkid=309825)和 JSBrowser 的[web 视图控制](https://github.com/MicrosoftEdge/JSBrowser#harnessing-the-webview-control)文档。  

## 事件  

### departingFocus  

指示焦点从**web 视图**转到应用中。  在 web 视图的顶级文档调用 departFocus 时激发。  DepartingFocus 事件中的 FocusNavigationEvent 参数与提供给 departFocus 的参数相匹配，除了来源参数从 web 视图的 document's 坐标空间转换到 web 视图主机文档的坐标空间。  请参阅 navigateFocus 方法和相应的窗口 navigatingFocus 将焦点从主机转移到 web 视图的事件。  请参阅[TVJS 的方向导航库](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)，以获取通过键盘或处理此事件的游戏板实现焦点导航的示例。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("departingFocus", handler);
webview.removeEventListener("departingFocus", handler);
```  

#### 事件信息  

|            |      |  
|:--- |:--- |  
| **接口** | [FocusNavigationEvent](./webview/FocusNavigationEvent.md) |  
| **同步** | 是 |   
| **气泡** | 是 |  
| **可取消** | 否 |  

### MSWebViewContainsFullScreenElementChanged  

当**web 视图**当前是否包含全屏元素时发生的状态更改时发生。  将 containsFullScreenElement 属性用于当前值。  此处的全屏元素指通过 requestFullScreen 和 exitFullScreen DOM 函数的全屏元素的全屏[DOM api](https://developer.mozilla.org/docs/Web/API/Fullscreen_API)概念。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | **事件** |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewContentLoading  

指示 HTML 内容已下载并正在加载到控件中。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewContentLoading", handler);
webview.removeEventListener("MSWebViewContentLoading", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** | 是  |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewDOMContentLoaded  

指示主 DOM 元素已完成加载。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewDOMContentLoaded", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** |是 |  
| **气泡** | 否 |  
| **可取消** | 否 |   

### MSWebViewFrameContentLoading  

指示下载并加载到控件中的 HTML 内容 `<iframe>` 。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameContentLoading", handler);
webview.removeEventListener("MSWebViewFrameContentLoading", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |  
| **可取消** | 否 |   

### MSWebViewFrameDOMContentLoaded  

指示主 DOM 元素已在中完成加载 `<iframe>` 。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameDOMContentLoaded", handler);
webview.removeEventListener("MSWebViewFrameDOMContentLoaded", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewFrameNavigationCompleted  

指示导航已完成，并且所有媒体元素都将呈现在中 `<iframe>` 。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewFrameNavigationCompleted", handler);
webview.removeEventListener("MSWebViewFrameNavigationCompleted", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationCompletedEvent](./webview/NavigationCompletedEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewFrameNavigationStarting  

指示 `<iframe>` **web 视图**内的 a 正在开始导航。  在从网络获取导航的任何资源之前，将引发此情况。  在所有 MSWebViewFrameNavigationStarting 事件处理程序完成之前，导航不会启动。  通过调用 cancellable 此事件 `eventArgs.preventDefault()` 。  如果取消，则 Web 视图将不会执行导航。  

```javascript
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

#### 事件信息  

|  |  |
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** | 是 |  
| **气泡** |否 |   
| **可取消** | 是 |  

### MSWebViewLongRunningScriptDetected  

在**web 视图**中不中断的脚本执行期间定期发生，让你停止脚本。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [LongRunningScriptDetectedEvent](./webview/LongRunningScriptDetectedEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |  
| **可取消** | 否 |  

### MSWebViewNavigationCompleted  

指示导航已完成，将呈现所有媒体元素或出现导航错误。  检查事件参数 isSuccess 属性以判断导航是否成功，并检查 webErrorStatus 属性以获取有关导航错误的详细信息。  在从网络获取任何内容之前，如果 URI 的主机名未解析，在这种情况下将在该情况下引发 MSWebViewNavigationStarted 事件后跟 MSWebViewNavigationCompleted 事件，则会出现导航错误。  导航错误可能还会在从 web 服务器收到错误页面后出现，例如，从 HTTP 服务器收到一个404页面，在这种情况下，所有导航事件都将引发、MSWebViewNavigationStarting、MSWebViewContentLoading、MSWebViewDOMContentLoaded 和 MSWebViewNavigationCompleted。  若要为 web 服务器未提供错误页面的情况提供应用导航错误页面，你需要检查 MSWebViewContentLoading 是否未触发失败的导航，这表示没有服务器提供错误页面。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationCompletedEvent](./webview/NavigationCompletedEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewNavigationStarting  

指示**web 视图**正在开始导航。  在从网络获取导航的任何资源之前，将引发此情况。  在所有 MSWebViewNavigationStarting 事件处理程序完成之前，导航不会启动。  通过调用 cancellable 此事件 `eventArgs.preventDefault()` 。  如果取消，则 Web 视图将不会执行导航。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** | 否 |  
| **气泡** | 是 |   
| **可取消** | 是 |  

### MSWebViewNewWindowRequested  

在**web 视图**中的内容尝试打开新窗口时引发。  如果事件未取消，则 web 视图将在用户的默认浏览器中启动新窗口请求的 URI。  

```javascript
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

#### 事件信息  

|  |  |  
|:---|:--- |  
| **接口** | [NavigationEventWithReferrer](./webview/NavigationEventWithReferrer.md) |  
| **同步** | 是 |  
| **气泡** | 否 |  
| **可取消** | 是 |  

### MSWebViewPermissionRequested  

指示**web 视图**中的内容尝试访问通常需要最终用户权限的功能（如地理位置或指针锁定访问）。  如果未注册任何事件处理程序，或者事件处理程序没有调用 permissionRequest （）、defer （）或 deny （），则权限请求将被拒绝。  如果你需要确定是否为实例异步允许或拒绝权限（如果你需要提示用户），请使用 permissionRequest （）。  将延迟权限请求，直到你使用 getDeferredPermissionRequestById 或 web web getDeferredPermissionRequests，并使用对应的 id 值在 DeferredPermissionRequest 上调用 allow （）或 deny （）。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [PermissionRequestedEvent](./webview/PermissionRequestedEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewProcessExited  

指示**web 视图**组件进程 crashsed。  这仅适用于进程外的 Web 视图。  有关如何创建进程内 web 视图（相对于进程内 Web 视图）的说明，请参阅备注部分。  此事件引发后，相应的 Web 视图将置于崩溃状态。  在崩溃的 Web 视图上调用大多数 Web 视图特定的方法或访问大多数 Web 视图特定的属性将引发异常。  若要从此事件中恢复，请从 DOM 中删除崩溃的 Web 视图并将其替换为新的 Web 视图。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewProcessExited", handler);
webview.removeEventListener("MSWebViewProcessExited", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | **事件** |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

### MSWebViewWebResourceRequested  

在**web 视图**元素内的页面请求资源时引发。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [WebResourceRequestedEvent](./webview/WebResourceRequestedEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  


### MSWebViewScriptNotify  

在**web 视图**内的页面调用**window 外部通知**方法时引发。  只有 Uri 与应用的 manifest's ApplicationContentUriRules 中的规则匹配的文档或通过将 web 视图设置为 true 的文档才可用。 isScriptNotifyAllowed 设置为 true。  此外，"外部" 通知仅适用于 web 视图的顶级文档。  

```javascript
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

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [ScriptNotifyEvent](./webview/ScriptNotifyEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |  
| **可取消** | 否 |  

### MSWebViewUnsafeContentWarningDisplaying  

在**web 视图**显示针对 SmartScreen 筛选器被报告为不安全的内容时出现的警告页面时发生。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
webview.removeEventListener("MSWebViewUnsafeContentWarningDisplaying", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | **事件** |  
| **同步** |是 |  
| **气泡** |否 |   
| **可取消** |否 |  

### MSWebViewUnsupportedUriSchemeIdentified  

当导航到**web 视图**不支持的统一资源标识符（URI）时引发。  

```javascript
function handler(eventInfo) { /* Your code */ }
 
// addEventListener syntax
webview.addEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
webview.removeEventListener("MSWebViewUnsupportedUriSchemeIdentified", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [NavigationEvent](./webview/NavigationEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |  
| **可取消** | 是 |  

### MSWebViewUnviewableContentIdentified  

在**web 视图**尝试导航到具有不受支持的内容类型的 web 内容时引发。  例如，web 视图当前不支持 Pdf，并且 PDF 文档的导航不受支持，而是会引发此事件。  

```javascript
function handler(args) {
    if (args.mediaType === "application/pdf") {
        Windows.System.Launcher.launchUriAsync(new Windows.Foundation.Uri(args.uri));
    }
}

// addEventListener syntax
webview.addEventListener("MSWebViewUnviewableContentIdentified", handler);
webview.removeEventListener("MSWebViewUnviewableContentIdentified", handler);
```  

#### 事件信息  

|  |  |  
|:--- |:--- |  
| **接口** | [UnviewableContentIdentifiedEvent](./webview/UnviewableContentIdentifiedEvent.md) |  
| **同步** | 是 |  
| **气泡** | 否 |   
| **可取消** | 否 |  

## 方法  

### Webview.addweballowedobject  

将本机 Windows 运行时对象作为全局参数添加到**web 视图**内的顶级文档中。  

该对象不会插入到当前文档中，而是指向 web 视图导航到的下一个顶级文档。  在运行 HTML 文档中的任何脚本之前插入对象，以便你可以在文档的全局脚本中依赖该对象。  

在 MSWebViewNavigationStarting 事件期间或显式调用导航方法之前，应使用 Webview.addweballowedobject。  在这些情况下，对象将被插入到相应导航的文档中。  在某些其他上下文中调用它时，你无法确定要插入对象的文档。  

在一行中多次调用 Webview.addweballowedobject 将在文档中插入多个对象。  如果在显式导航调用之前和在相应的 MSWebViewNavigationStarting 事件期间再次调用它，则两个调用都将成功，并且你将插入多个对象。  如果用相同名称参数调用多次，则将忽略最后一个通话的 wins 和以前与该名称的通话。  

如果导航失败或被重定向，则将忽略该导航的 Webview.addweballowedobject 调用。  如果你想要处理重定向，你可以按照适用于你的应用程序的任何条件，为重定向和调用 Webview.addweballowedobject 订阅 MSWebViewNavigationStarting 事件监视。  同样，当文档导航离开通过 Webview.addweballowedobject 为该文档插入的任何对象时，将不会转到下一个文档，如果你希望它们执行，则需要显式调用 Webview.addweballowedobject。  

如果你为没有 WinRT 访问的文档调用 Webview.addweballowedobject，或者如果它具有[通过 ApplicationContentUriRules 的 AllowForWebOnly access](/uwp/schemas/appxpackage/uapmanifestschema/element-uap-rule) ，则仅当对象具有元数据属性时才会注入该对象。  否则，注入将失败，并且会向 JavaScript 开发人员控制台报告错误。  如果在具有完全 WinRT 访问权限的文档上调用，则无论 AllowForWeb 属性如何，都将插入该对象。  

此外，该对象必须实现 IAgileObject 接口。  这是因为 XAML 和 HTML web 视图元素在其应用的 ASTA 视图线程上运行，并且 Web 视图的 JavaScript 线程是不同的 ASTA 线程，因此我们希望鼓励应用开发人员确保其对象可以在 JavaScript 线程上运行，而无需阻止应用视图线程。  

Name 参数必须是有效的 JavaScript 属性名称，否则该调用将自动失败。  如果名称的属性是已存在于全局对象，则该属性将在属性可配置时被覆盖。  全局对象上的不可配置属性不会被覆盖，并且 Webview.addweballowedobject 调用将无提示地失败。  通过 Webview.addweballowedobject 创建的 JavaScript 属性是可写、可配置和可枚举的。  

```javascript
let name = "exampleProperty";
webview.addWebAllowedObject(name, applicationObject);
webview.navigate("https://example.com/"); // applicationObject will be available as window.exampleProperty on https://example.com
```  

#### 参数  

*name*  

*   类型： **String**  
*   要向**web 视图**中的文档公开的对象的名称。  

*applicationObject*  

*   类型：**对象**  
*   要向**web 视图**中的文档公开的对象。  

#### 返回值  

此方法不返回值。  

#### 其他功能和要求  

|  |  |  
|:--- |:--- |  
| **最低受支持的客户端** | Windows10 （仅限 Windows 应用商店应用） |    
| **最低受支持的服务器** | 无受支持的版本 |   
| **最低受支持的电话** | 无受支持的版本 |  

### buildLocalStreamUri  

创建可传递给[navigateToLocalStreamUri](#methods)的 URI。  

```javascript
var string = webview.buildLocalStreamUri(contentIdentifier, relativePath);
```  

#### 参数  

*contentIdentifier*  

*   类型： **String**  
*   URI 引用的内容的唯一标识符。  这将定义 URI 的根。  

*relativePath*  

*  类型： **String**  
*  相对于根的资源的路径。  

#### 返回值  

类型： **String**  

通过组合和规范化*contentIdentifier*和*RELATIVEPATH*创建的 URI。  

#### 示例  

以下示例阐释了一个典型的用例。  

```javascript
var webview = document.createElement("x-ms-webview"); //Instantiate the webview element
var localStreamUri = webview.buildLocalStreamUri(contentIdentifier, relativePath); //Create URI to pass to navigateToLocalStreamUri method
webview.navigateToLocalStreamUri(localStreamUri, streamResolver); //Load the local web content 
```  

### capturePreviewToBlobAsync  

创建当前[web 视图元素](./webview.md)的图像，并将其写入指定的 image 元素。  

```javascript
var capturePreviewToBlobAsync = webview.capturePreviewToBlobAsync();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

类型： **MSWebViewAsyncOperation**  

一个**MSWebViewAsyncOperation**对象，该对象在完成时提供包含图像的**Blob**对象。  使用**capturePreviewToBlobAsync**时，你需要在定义操作后定义成功和错误处理程序。  应用事件处理程序后，调用[MSWebViewAsyncOperation](./webview/MSWebViewAsyncOperation.md)对象上的 start 方法以执行该操作。  

### captureSelectedContentToDataPackageAsync  

> [!IMPORTANT]
> 此方法已弃用，并且存在已知问题。  避免在成品代码中使用此方法。  

异步获取包含**web 视图**中所选内容的[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage) 。  

```javascript
var msWebViewAsyncOperation = webview.captureSelectedContentToDataPackageAsync();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

类型： **MSWebViewAsyncOperation**  

一个**MSWebViewAsyncOperation**对象，该对象在完成时提供包含图像的[DataPackage](https://docs.microsoft.com/uwp/api/Windows.ApplicationModel.DataTransfer.DataPackage)对象。  使用**captureSelectedContentToDataPackageAsync**时，你需要在定义操作后定义成功和错误处理程序。  应用事件处理程序后，调用 MSWebViewAsyncOperation 对象上的 start 方法以执行该操作。  

```javascript
 var operation = webview.captureSelectedContentToDataPackageAsync();
    operation.oncomplete = function () {
        // operation.result is a package object that contains the selected data.
        var url = URL.createObjectURL(operation.result, { oneTimeOnly: true });
        // After converting the package to a URI, put it in an image element.
        document.getElementById('webviewPreview').src = url;
    };
    operation.start();
```  

### invokeScriptAsync  

作为异步操作，使用特定参数从当前加载的 HTML 执行指定的脚本函数。  

```javascript
webview.invokeScriptAsync(functionName, ...args)
```  

#### 参数  

**functionName**  

*   类型： **String**  
*   要调用的函数的名称。  这是 Web 视图顶级文档的全局窗口对象上的属性名称。  这可以是一个内置的全局函数（如 eval 或 open），也可以是全局窗口对象上的脚本定义函数。  仅可调用 Web 视图顶层文档中的函数。  

**args**  

*   类型： **String**  
*   要传递到已调用函数的可选字符串参数。  在 functionName 之后，invokeScriptAsync 的任何其他参数都将传递到已调用函数的字符串。  

#### 返回值  

类型： **MSWebViewAsyncOperation**  

使用**invokeScriptAsync**时，你需要在定义操作后定义成功和错误处理程序。  应用事件处理程序后，调用**MSWebViewAsyncOperation**以执行该操作。  如果 MSWebViewAsyncOperation 的 complete 事件引发，则 MSWebViewAsyncOperation 的 result 属性是调用该函数的字符串返回值。  使用被调用函数的返回值可使 Web 视图内容同步回 Web 视图主机。  若要改为将 Web 视图内容异步通信回 Web 视图主机，请参阅 MSWebViewScriptNotify 事件。  如果调用的函数引发了一个未处理的异常，则将引发 MSWebViewAsyncOperation 的错误事件。  

```javascript
const functionName = "eval";
const args = ["'Current URL: ' + document.location.href"];

const asyncOp = webview.invokeScriptAsync(functionName, ...args);

asyncOp.onerror = () => console.error("Error: " + asyncOp.error);
asyncOp.oncomplete = () => console.log("Result: " + asyncOp.result); // Logs 'Current URL: about:blank'
asyncOp.start();
```  

### getDeferredPermissionRequests  

返回由**web 视图**控件中的内容颁发的延迟权限请求的列表。  

```javascript
var sequence<PermissionRequest> = x-ms-webview.getDeferredPermissionRequests();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

类型： [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)  

指定的延迟权限请求。  

#### 其他功能和要求  

|  | |  
|:--- |:--- |  
| **最低受支持的客户端** | Windows10 （仅限 Windows 应用商店应用） |  
| **最低受支持的服务器** | 无受支持的版本 |  
| **最低受支持的电话** | 无受支持的版本 |  


### getDeferredPermissionRequestById  

返回指定的延迟权限请求。  

```javascript
var deferredPermissionRequest = x-ms-webview.getDeferredPermissionRequestById(id);
```  

#### 参数  

*id*  

*   类型：**无符号长**  
*   希望获取的延迟权限请求的 ID。  

#### 返回值  

类型： [DeferredPermissionRequest](./webview/DeferredPermissionRequest.md)  

指定的延迟权限请求。  

#### 其他功能和要求  

|  |  |  
|:--- |:--- |  
| **最低受支持的客户端** | Windows10 （仅限 Windows 应用商店应用） |  
| **最低受支持的服务器** | 无受支持的版本 |  
| **最低受支持的电话** | 无受支持的版本 |  

### goBack  

将**web 视图**导航到导航历史记录中的上一页。  

```javascript
webview.goBack();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

此方法不返回值。  

### goForward  

将**web 视图**导航到导航历史记录中的下一页。  

```javascript
webview.goForward();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

此方法不返回值。  

### 导航  

在指定的统一资源标识符（URI）处加载 HTML 内容。  

```javascript
webview.navigate(uri);
```  

#### 参数  

**uri**  

*   类型： **String**  
*   要加载的 URI。  

#### 返回值  

此方法不返回值。  

### navigateFocus  

将焦点导航到**web 视图**。  激发 web 视图的顶级文档的 window's navigatingfocus 事件。  Navigatingfocus 事件中使用的 FocusNavigationEvent 参数与提供给 navigateFocus 的参数相匹配，但原始参数从宿主文档的坐标空间转换为 web 视图的顶级文档的坐标空间。  请参阅 web 视图 departingFocus 事件和相应的窗口。 departFocus 方法，用于将焦点从 web 视图转移到主机。  有关通过使用此方法的键盘或游戏板实现焦点导航的示例，请参阅[TVJS 的方向导航库](https://github.com/Microsoft/TVHelpers/wiki/Using-DirectionalNavigation)。  

```javascript
const activeElementBounds = document.activeElement.getBoundingClientRect();
const origin = { 
    originLeft: activeElementBounds.left,
    originTop: activeElementBounds.top,
    originWidth: activeElementBounds.width,
    originHeight: activeElementBounds.height
};
webview.navigateFocus(navigationReason, origin);
```  

#### 参数  

*navigationReason*  

*   类型： **String**  
*   导航的原因。  此值应为 "左"、"上"、"右" 或 "下"。  焦点从当前焦点的元素移开的方向。  

*原*  

*   类型：**对象**  
*   导航的来源。  这是一个 JavaScript 对象，其属性为 "originLeft"、"originTop"、"originWidth" 和 "originHeight"。  这些值应描述当前焦点元素远离焦点移动的位置和大小。  

#### 返回值  

此方法不返回值。  

### navigateToLocalStreamUri  

使用[**UriToStreamResolver**](/uwp/api/windows.web.iuritostreamresolver.uritostreamasync)在指定 URI 处加载本地 web 内容。  

```javascript
webview.navigateToLocalStreamUri(source, streamResolver); 
```  

#### 参数  

*从源*  

*   类型： **String**  
*   标识要加载的本地 HTML 内容的 ms 本地流 URI。  使用[**buildLocalStreamUri**](/uwp/api/windows.web.ui.iwebviewcontrol.buildlocalstreamuri)创建此字符串。  

*streamResolver*  

*   类型：任何  
*   将 URI 转换为流以加载的冲突解决程序。  

#### 返回值  

此方法不返回值。  

### navigateToString  

将指定的 HTML 内容加载为新文档。  

```javascript
webview.navigateToString(contents);
```  

#### 参数  

*内容*  

*   类型： **String**  
*   要显示的 HTML 内容。  

#### 返回值  

此方法不返回值。  

### navigateWithHttpRequestMessage  

使用 POST 请求和 HTTP 标头将 web 视图导航到统一资源标识符（URI）。  

```javascript
webview.navigateWithHttpRequestMessage(requestMessage);
```  

#### 参数  

*requestMessage*  

*   类型： **HttpRequestMessage**  
*   HTTP 请求的详细信息。  

#### 返回值  

此方法不返回值。  

#### 备注  

> [!WARNING]
> 如果为此请求添加其他标头（如身份验证凭据），请记住这些标题也将包含在任何后续子请求中。  请注意防止意外泄漏机密或个人信息。  

### 恢复  

重新加载**web 视图**中的当前内容。  

```javascript
webview.refresh();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

此方法不返回值。  

### stop  

暂停当前**web 视图**导航或下载。  

```javascript
webview.stop();
```  

#### 参数  

此方法没有任何参数。  

#### 返回值  

此方法不返回值。  

## 属性  

### canGoBack  

获取一个值，该值指示**web 视图**是否可以向后导航。  

此属性为只读。  

```javascript
var canGoBack = webview.canGoBack;
```  

#### 属性值  

类型： **Boolean**  

如果**web 视图**可以向后导航，**则为 True** ;否则**为 false**。  

### canGoForward  

获取一个值，该值指示**web 视图**是否可以向前导航。  

此属性为只读。  

```javascript
var canGoForward = webview.canGoForward;
```  

#### 属性值  

类型： **Boolean**  

如果**web 视图**可以向前导航，**则为 True** ;否则**为 false**。  

### containsFullScreenElement  

获取一个值，该值指示**web 视图**是否包含支持全屏幕的元素。  有关详细信息，请参阅 MSWebViewContainsFullScreenElementChanged 事件。  

此属性为只读。  

```javascript
var containsFullScreenElement = webview.containsFullScreenElement;
```  

#### 属性值  

类型： **Boolean**  

如果**web 视图**包含支持全屏的元素，**则为 True** ;否则**为 false**。  

### documentTitle  

获取**web 视图**中当前显示的页面的标题。  

此属性为只读。  

```javascript
var documentTitle = webview.documentTitle;
```  

#### 属性值  

类型： **String**  

页面标题。  

### height  

获取或设置**web 视图**的高度。  

```javascript
var height = webview.height;
webview.height = height;
```  

#### 属性值  

类型：**数字**  

**Web 视图**的高度。  

### 进程  

获取**web 视图**进程。  

此属性为只读。  

```javascript
var process = webview.process;
webview.process = process;
```  

#### 属性值  

类型： [MSWebViewProcess](./webview/MSWebViewProcess.md)  

### settings  

获取一个[MSWebViewSettings](./webview/MSWebViewSettings.md)对象，该对象包含用于启用或禁用**web 视图**功能的属性。  

此属性为只读。  

```javascript
var settings = webview.settings;
webview.settings = settings;
```  

#### 属性值  

类型： [MSWebViewSettings](./webview/MSWebViewSettings.md)  

一个[MSWebViewSettings](./webview/MSWebViewSettings.md)对象，其中包含用于启用或禁用**web 视图**功能的属性。  

### src  

获取或设置要在**web 视图**控件中显示的 HTML 内容的统一资源标识符（URI）源。  

```javascript
var src = webview.src;
webview.src = src;
```  

#### 属性值  

类型： **String**  

要在**web 视图**控件中显示的 HTML 内容的 URI 源。  

### width  

获取或设置**web 视图**的宽度。  

```javascript
var width = webview.width;
webview.width = width;
```  

#### 属性值  

类型：**数字**  

**Web 视图**的宽度。  
