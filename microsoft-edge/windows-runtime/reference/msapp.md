---
title: MSApp API 参考
description: 提供帮助程序函数，使你能够创建 Blob 和 MSStream 对象。 使用 JavaScript 的 Windows 应用支持 MSApp 对象和成员。
author: mattwojo
ms.author: mattwoj
ms.date: 03/05/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp、PWA、文件上传、博客、MSStream、windows 10 应用、uwp、edge
ms.openlocfilehash: 0ed8cefa918bd44f3b2c4e8312d2c1d3b4ace8fc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564586"
---
# MSApp

只有使用 JavaScript 的 Windows 应用（包括 PWAs 访问 Windows API 功能）才支持 MSApp 对象及其成员。 MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中的 HTML 文档的本地上下文中;否则，该对象不存在（因此它的任何方法和属性均不可用）。

它提供帮助程序函数，使你能够创建[Blob](https://developer.mozilla.org/docs/Web/API/Blob)和[MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)对象。

```javascript
var result = MSApp.method;
```

| | |
| :--- | :--- |
| [**方法**](#msapp-methods) | [clearTemporaryWebDataAsync](#cleartemporarywebdataasync)、 [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)、 [createDataPackage](#createdatapackage)、 [createDataPackageFromSelection](#createdatapackagefromselection)、 [createFileFromStorageFile](#createfilefromstoragefile)、 [createStreamFromInputStream](#createstreamfrominputstream)、 [execAsyncAtPriority](#execasyncatpriority)、 [execAtPriority](#execatpriority)、 [getCurrentPriority](#getcurrentpriority)、 [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)、[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)、 [getViewId](#getviewid)、 [isTaskScheduledAtPriorityOrHigher、pageHandlesAllApplicationActivations](#istaskscheduledatpriorityorhigher) [、suppressSubdownloadCredentialPrompts](#pagehandlesallapplicationactivations) [、terminateApp](#suppresssubdownloadcredentialprompts)、、 [、、](#terminateapp)、、。 |

| | |
| :--- | :--- |
| [**常量**](#msapp-constants) | [当前](#current)、[高](#high)、[空闲](#idle)、[正常](#normal)。|

| | |
| :--- | :--- |
| [**MSAppAsyncOperation**接口](#msappasyncoperation) | [start](#start) |

## MSApp 方法

### clearTemporaryWebDataAsync 
为应用或[Web 视图](../../webview.md)清除缓存和 indexedDB 数据。

```javascript
var retval = MSApp.clearTemporaryWebDataAsync(#); 
```

#### 参数
此方法没有任何参数。

#### 返回值
处理器类型[`IAsyncAction`](/uwp/api/windows.foundation.iasyncaction)

表示一个异步操作。

### createBlobFromRandomAccessStream
从对象创建[Blob](https://developer.mozilla.org/docs/Web/API/Blob) [`IRandomAccessStream`](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) 。 在处理应用中的对象时，应使用此方法 `IRandomAccessStream` ，以便从流创建基于 W3C 的对象。 创建 blob 后，可以将其与[FileReader](https://developer.mozilla.org/docs/Web/API/FileReader)、 [URL api](https://developer.mozilla.org/docs/Web/API/URL)和[XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)结合使用。 

```javascript
var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
```

#### 参数

`type` 登录

|类型 | 说明 |
|:---- |:--- |
|字符串 | 数据的内容类型。 此字符串应采用 RFC 2616 的3.7 节中定义的媒体类型令牌中指定的格式。

`stream` 登录

|类型 | 描述 |
|:---- |:--- |
|Any | 要存储在 Blob 中的[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) 。

#### 返回值
|类型 | 描述 |
|:---- |:--- |
|Blob | 包含流的新 blob 对象。

#### 异常
|异常 | 条件 |
|:---- |:--- |
|TypeMismatchError | 节点类型与所需的参数类型不兼容。 对于早于 Internet Explorer 10 的版本，将返回 TYPE_MISMATCH_ERR。

#### 备注
通过 window 对象上的 MSApp 命名空间创建来自 Windows 运行时类型的 Blob。 此方法将创建一个 blob，该 blob 实质上是提供给它的对象的轻包装器 [`RandomAccessStream`](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 。 Blob 拥有此流的生存期，并且在销毁 blob 时将关闭流。 

#### 示例

```javascript
var randomAccessStream = dataPackage.GetData("image/bmp");
var blob = window.MSApp.createBlobFromRandomAccessStream("image/bmp", randomAccessStream);
var url = window.URL.createObjectURL(blob, {oneTimeOnly:true});

document.getElementById("imagetag").src = url; 
```

### createDataPackage
将用户或应用程序的指定范围转换为可共享的 HTML 片段。

```javascript
var retVal = MSApp.createDataPackage(object); 
```

#### 参数
`object` 登录

|类型 | 描述 |
|:---- |:--- |
|Any | 可以从选择对象（例如：或手动）创建此范围 `window.selection.getRangeAt(0)` 。

#### 返回值
|类型 | 描述 |
|:---- |:--- |
|Any | 包含指定范围的 HTML 标记。

#### 备注
此方法仅支持[文档对象模型（DOM）范围](https://developer.mozilla.org/docs/Web/API/Range)，而不支持[TextRange](/uwp/api/windows.ui.xaml.documents.textrange)。 针对指定范围返回的数据包包含剪贴板格式的 HTML 标记。

返回的数据包没有可用的属性。

### createDataPackageFromSelection 
将用户或应用程序的选定内容转换为可共享的 HTML 片段。

```javascript
var retVal = MSApp.createDataPackageFromSelection(); 
```

#### 参数
此方法没有任何参数。

#### 返回值
|类型 | 描述 |
|:---- |:--- |
|Any | 包含指定范围的 HTML 标记。

#### 备注
所选内容的返回数据包包含剪贴板格式的 HTML 标记。 如果在应用程序的 UI 中的任何位置都没有用户选择，则 `createDataPackageFromSelection` 返回 null。

返回的数据包没有可用的属性。
 
### createFileFromStorageFile 
将[WinRT](/uwp/api/)转换 [`StorageFile`](/uwp/api/windows.storage.storagefile) 为标准 W3C [`File`](https://developer.mozilla.org/docs/Web/API/File) 对象。

```javascript
var retVal = MSApp.createFileFromStorageFile(storageFile); 
```

#### 参数
`storageFile` 登录

|类型 | 描述 |
|:---- |:--- |
|Any | 包含存储文件。

#### 异常
|异常 | 条件 |
|:---- |:--- |
|TypeMismatchError | 指定的 W3C 文件引用无效。 对于早于 Internet Explorer 10 的版本，将返回 TYPE_MISMATCH_ERR。

### createStreamFromInputStream  

从创建 [`MSStream`](https://msdn.microsoft.com/library/hh772328) [`InputStream`](https://msdn.microsoft.com/library/hh772327) 。  


```javascript
var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
```

#### 参数
`type` 登录

|类型 | 描述 |
|:---- |:--- |
|DOMString | 数据的内容类型。 此字符串应采用 RFC 2616 的3.7 节中定义的媒体类型令牌中指定的格式。 （[请参阅 MIME 类型，例如](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types)文本/纯文本/html、图像/jpeg、图像/png、音频/mpeg、音频/ogg、音频/*、视频/设备类型等）。 

`inputStream` 登录

|类型 | 描述 |
|:---- |:--- |
|Any | [`IInputStream`](/uwp/api/Windows.Storage.Streams.IInputStream)要存储在中的 "" `MSStream` 。

#### 备注
此方法采用内容类型和 `IInputStream` 引用。 然后，该方法验证传入的流引用是否为类型的实例， `IInputStream` 如果不是，则 `DOMException TYPE_MISMATCH_ERR` 引发。 如果没有出现错误，则 `createStreamFromInputStream` `MSStream` 从其输入创建一个（from）。

#### 示例
`IInputStream`可用于创建 `MSStream` 。 与 `MSStreams` 固有的一次使用的对象一样，由 `URL.createObjectURL` image 元素首次解析创建的所有 url 都会被吊销。 此外，在使用该对象后，对此对象的第二个 URL 的请求将失败。

```javascript
var inputStream = myInputStream; //get InputStream from socket API, etc.
var stream = MSApp.createStreamFromInputStream("image/bmp", inputstream);
document.getElementById("imagetag").src = URL.createObjectURL(stream); 
```

### execAsyncAtPriority 
根据给定优先级调度要在稍后的时间执行的回调。 

```javascript
MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
```

#### 参数
`asynchronousCallback` 登录

|类型 | 描述 |
|:---- |:--- |
|函数 | 要以异步方式运行的回调函数，以给定的优先级优先级调度。

`priority` 登录

|类型 | 描述 |
|:---- |:--- |
|DOMString | AsynchronousCallback 回调运行的上下文优先级值。 请参阅[MSApp 常量](#msapp-constants)。

`args` 登录

|类型 | 描述 |
|:---- |:--- |
|Any | 传递到 synchronousCallback 回调函数（作为参数1和 on）的一系列可选参数。

#### 返回值
此方法不返回值。

#### 备注
提供的 `asynchronousCallback` 回调函数将在稍后异步执行。 `asynchronousCallback` 将根据所提供的优先级进行调度。 普通优先级等效于现有 [`setImmediate`](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。 当回调运行时，当前上下文优先级设置为在回调执行期间提供的优先级参数值。

`asynchronousCallback`回调参数可以是任何函数。 如果在参数后提供参数 `priority` ，则它们将全部传递到回调函数。

与 `execAtPriority` 此不同，回调函数返回的任何对象 `asynchronousCallback` 都会被忽略（且不会通过 `execAsyncAtPriority` ）返回。

### execAtPriority 
按给定的上下文优先级运行指定的回调函数。

```javascript
var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
```

#### 参数
`synchronousCallback` 登录

|类型 | 描述 |
|:---- |:--- |
|函数 | 要以给定优先级的上下文优先级同步运行的回调函数。

`priority` 登录

|类型 | 描述 |
|:---- |:--- |
|DOMString | 指定的优先级值，在运行回调函数时将设置当前上下文优先级值 `synchronousCallback` 。 请参阅[MSApp 常量](#msapp-constants)。

`args` 登录

|类型 | 描述 |
|:---- |:--- |
|Any | 传递给回调函数的一系列可选参数 `synchronousCallback` （如参数1和打开）。

#### 返回值
|类型 | 描述 |
|:---- |:--- |
|Any | 返回回调的返回值 `synchronousCallback` （如果适用）。

#### 备注
提供的 `synchronousCallback` 回调方法将同步执行。 在提供的回调函数的持续时间内，当前上下文优先级更改为所提供的优先级值（由 priority 参数提供）。 回调函数执行完毕后，在调用之前，优先级返回到以前的值 `execAtPriority` 。 中的返回值 `execAtPriority` 是回调方法（如提供）的返回值。
 
`synchronousCallback`回调参数可以是任何函数。 如果在 priority 参数后提供任何参数，则它们将传递给所提供的回调方法。 如果回调参数返回一个值，则此值也会成为返回值 `execAtPriority` 。

#### 示例

```javascript
var user = Windows.System.UserProfile.UserInformation;

MSApp.execAtPriority(function () { // This callback executes synchronously.
  user.getFirstNameAsync().then(function () { // Dispatches at high priority.
    return user.getLastNameAsync();
  }).done(function () { // Dispatches at high priority.
    // USEFUL CODE HERE
  });
}, MSApp.HIGH); // The second argument of the execAtPriority method.
```

### getCurrentPriority 
返回当前的上下文优先级。

```javascript
var retval = MSApp.getCurrentPriority();
```

#### 参数
无。 

#### 返回值
|类型 | 描述 |
|:---- |:--- |
|DOMString | 返回值是字符串、或中的 `MSApp.HIGH` 一个 `MSApp.NORMAL` `MSApp.IDLE` 。

#### 备注
此方法返回当前上下文优先级（请参阅 [`MSApp Constants`](#msapp-constants) ），可以通过 and 进行更改 `execAtPriority` `execAsyncAtPriority` 。

#### 示例

```javascript
if (MSApp.getCurrentPriority() === MSApp.IDLE) { 
  // YOUR CODE HERE
}
```

### getHtmlPrintDocumentSource  

已弃用的同步 API。 对于 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。 对于 Windows 8 和8.1 应用，请参阅[getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。  

### getHtmlPrintDocumentSourceAsync
返回要打印的源内容。

#### 参数
`htmlDoc` 登录

|类型 | 描述 |
|:---- |:--- |
|文档 | 要打印的 HTML 文档。 这可以是根文档、iframe 中的文档、文档片段或 SVG 文档。 请注意，htmlDoc 必须是文档，而不是元素。

#### 示例 1

```javascript
var printTask = event.request.createPrintTask(title, function (args) {
                var deferral = args.getDeferral();
                var getPrintDocumentSourceAsync;
                if (MSApp.getHtmlPrintDocumentSourceAsync) { // Windows 10
                    getPrintDocumentSourceAsync = MSApp.getHtmlPrintDocumentSourceAsync(document);
                } else {
                    getPrintDocumentSourceAsync = WinJS.Promise.as(MSApp.getHtmlPrintDocumentSource(document));
                }
                getPrintDocumentSourceAsync.then(function (source) {
                    args.setSource(source);
                    deferral.complete();
                }, function (error) {
                    console.error(error);
                    deferral.complete();
                });
            });
```

#### 示例 2

```javascript
    function registerForPrintContract() {
            var printManager = Windows.Graphics.Printing.PrintManager.getForCurrentView();
            printManager.onprinttaskrequested = onPrintTaskRequested;
            console.log("Print Contract registered. Use the Print button to print.", "sample", "status");
    }
    
    // Variable to hold the document source to print
    var gHtmlPrintDocumentSource = null;
    
    // Print event handler for printing via the PrintManager API.
    function onPrintTaskRequested(printEvent) {
        var printTask = printEvent.request.createPrintTask("Print Sample", function (args) {
            args.setSource(gHtmlPrintDocumentSource);
    
            // Register the handler for print task completion event
            printTask.oncompleted = onPrintTaskCompleted;
        });
    }
    
    // Print Task event handler is invoked when the print job is completed.
    function onPrintTaskCompleted(printTaskCompletionEvent) {
        // Notify the user about the failure
        if (printTaskCompletionEvent.completion === Windows.Graphics.Printing.PrintTaskCompletion.failed) {
            console.log("Failed to print.", "sample", "error");
        }
    }
    
    // Executed just before printing.
    var beforePrint = function () {
        // Replace with code to be executed just before printing the current document:
    };
    
    // Executed immediately after printing.
    var afterPrint = function () {
        // Replace with code to be executed immediately after printing the current document:
    };
    
    function printButtonHandler() {
        // Optionally, functions to be executed immediately before and after printing can be configured as following:
        window.document.body.onbeforeprint = beforePrint;
        window.document.body.onafterprint = afterPrint;
    
        // Get document source to print
        MSApp.getHtmlPrintDocumentSourceAsync(document).then(function (htmlPrintDocumentSource) {
            gHtmlPrintDocumentSource = htmlPrintDocumentSource;
    
            // If the print contract is registered, the print experience is invoked.
            Windows.Graphics.Printing.PrintManager.showPrintUIAsync();
        });
    }
```

### getViewId 
对多个窗口的支持。 

> [!NOTE] 
> 在 Win 8.1 JavaScript UWP 应用中，使用 MSApp DOM Api （现在已 depricated）支持多个窗口。 对于 Windows 10，请使用 `window.open` 、 `window` 和新建 `MSApp.getViewId` 。

| 描述 |Windows 10 | Windows 8.1 |  
|:---- |:---- |:--- |  
| 新建窗口 | [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) | [`MSApp.createNewView`](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
|新的 window 对象 | [`window`](https://developer.mozilla.org/docs/Web/API/Window) |[`MSAppView`](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  

```javascript
var retval = MSApp.getViewId(window); 
```

#### 参数
`window`

|类型 | 描述 |
|:---- |:--- |
|DOMString | 表示包含 DOM 文档的窗口的对象。 | 

#### 返回值

`viewId`

|类型 | 描述 |
|:---- |:--- |
|数字 | 可与各种 api 一起使用 [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) 。 

#### 备注
使用 [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 和 [`window`](https://developer.mozilla.org/docs/Web/API/Window) 用于创建新窗口，但随后要与 WinRT api 交互，请添加 `MSApp.getViewId` API。 它将 `window` 对象作为参数，并返回 `viewId` 可与各种 api 一起使用的数字 [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) 。 

##### 延迟可见性 
WinRT 中的视图正常开始隐藏，最终开发人员在 `TryShowAsStandaloneAsync` 完全准备好后使用类似于显示视图的内容。 在 web world 中， `window.open` 立即显示一个窗口，最终用户可以在加载和呈现内容时观看。 要让新的 windows act 类似于 WinRT 视图，而不是立即显示，我们添加了一个 `window.open` 选项。 例如：
`let newWindow = window.open("https://example.com", null, "msHideView=yes");`

##### 主窗口差异
操作系统最初打开的主窗口的行为方式与它打开的辅助窗口不同： 

|描述 | 主要 | 辅助边框 |
|:---- |:--- |:--- |
|打开窗口 | 允许 | 不允许 |
|window.close | 关闭应用 | 关闭窗口 |
| 导航限制 | 仅 ACUR | 无限制 |

对不允许辅助窗口打开的限制可能会在将来更改，具体取决于[反馈](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。

##### 相同来源通信限制 
有一种很难的技术问题可防止对同步、相同源、跨窗口、脚本调用提供正确支持。 当您打开一个具有相同原点的窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。 `postMessage` 通话的工作方式很好，如果可能，我们建议采用的方式执行操作。 改进此问题的工作正在进行中。


### isTaskScheduledAtPriorityOrHigher 
返回一个布尔值，指示给定优先级或更高级别是否有挂起的工作。

```javascript
var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
```

#### 参数
`priority` 登录

|类型 | 描述 |
|:---- |:--- |
|DOMString | 一个优先级值（请参阅[MSApp 常量](#msapp-constants)），指定优先级级别和上方以查询任何未完成的排队工作。

#### 返回值
|类型 | 描述 |
|:---- |:--- |
|布尔 | `true`如果在指定的优先级级别或更高级别上有任何排队的工作，则返回， `false` 否则返回。

#### 备注
该 `isTaskScheduledAtPriorityOrHigher` 方法为 JavaScript 代码提供了一种方法，用于确定在不同优先级级别（或更高）处是否存在挂起的工作，以便调用 JavaScript 代码可以决定获得更高优先级的工作。

#### 示例

```javascript
function performIdleWork(array_in) {
  var idx = 0;

  function performIdleWorkHelper() {
    for (; idx < array_in.length; ++idx) {

      // USEFUL CODE HERE 

      if (MSApp.isTaskScheduledAtPriorityOrHigher(MSApp.NORMAL)) {
        MSApp.execAsyncAtPriority(performIdleWorkHelper, msPriority.IDLE);
        break;
      } // if
    } // for
  } // performIdleWorkHelper

  performIdleWorkHelper();
} // performIdleWork
```

### pageHandlesAllApplicationActivations
用于在每次激活事件（即单击通知或固定磁贴）之前避免刷新开始路径（页面重新加载）。 

#### 参数

|类型 | 描述 |
|:---- |:--- |
布尔 | 用于 `MSApp.pageHandlesAllApplicationActivations(true)` 始终跳过刷新开始路径（页面重新加载），而直接跳转到触发 `WebUIApplication` 激活的事件。 要求所有页面单独处理激活事件。 通过将此方法定义为 `true` ，单击激活的事件（如 notificaiton）将不会触发重新加载，即用于避免页面重新加载的单行应用的基本操作。

#### 示例 

```javascript
// Without this, the app will first refresh to the start path before every activate event
window.MSApp.pageHandlesAllApplicationActivations(true); 

// This must not be deffered so that it can receive the initial `activated` event in time
window.Windows.UI.WebUI.WebUIApplication.addEventListener(
    `activated`,
    e =>
        microsoftInterface.handleActivatedEvent(e);
    }),
    false
);
```

### suppressSubdownloadCredentialPrompts 
控制在下载资源的过程中应用是否取消可能的身份验证提示。

```javascript
MSApp.suppressSubdownloadCredentialPrompts(suppress); 
```

#### 参数
`suppress` 登录

|类型 | 描述 |
|:---- |:--- |
|布尔 | True 值将抑制潜在的身份验证提示。 False 值不会禁止用户任何潜在的身份验证提示。

#### Returan 值
无。

#### 备注
该 `suppressSubdownloadCredentialPrompts` 方法控制在下载资源的过程中应用是否抑制潜在的身份验证提示。 默认行为是不取消凭据提示。

`suppressSubdownloadCredentialPrompts` 适用于可能加载大量需要身份验证的资源的应用，例如 "邮件" 应用（其中可能包含包含许多图像的新闻稿，其中每个图像需要身份验证）。

当取消凭据提示时，访问需要身份验证的资源时，将不会显示用于验证服务器身份的对话框，并且不会下载资源。 请注意，不 `suppressSubdownloadCredentialPrompts` 会影响代理身份验证或客户端认证请求对话框等其他可能的提示，也不会影响 XHR。

`suppressSubdownloadCredentialPrompts`请注意影响应用程序中的所有内容，包括在元素中托管的内容 `webview` 。
 
**重要提示：** 已缓存凭据提示决策。 因此，在取消凭据提示将立即生效时，如果禁止凭据提示，则在取消后允许凭据提示可能需要对文档进行重新加载才能生效。

#### 示例

```javascript
/ Set to true to suppress potenial credential prompts:
MSApp.suppressSubdownloadCredentialPrompts(true); 
// Now one can load content or navigate iframe/webview to some other site.
```

### terminateApp
终止当前应用程序并生成失败报告。 

```javascript
MSApp.terminateApp(error); 
```

#### 参数
`error` 登录

类型 | 描述 |
|:---- |:--- |
|错误 | 一个 `Error` 对象，可用于描述触发终止的错误。 该 `Error` 对象必须包含数字、说明和堆栈属性; 如果对象不包含这些属性，则不会生成失败报告。

#### 返回值
无。

#### 备注
如果报告的问题是 `terminateApp` 应用的前5个问题之一，它将显示在应用的 "质量" 页面上。

#### 示例
此示例 `terminateApp` 将在遇到异常时进行调用。 `Error`当你捕获异常时，它使用提供的对象。 

```javascript
try {  
        var obj2 = null;  
        obj2.val = 5;  
    }  
    catch(e) {  
        window.MSApp.terminateApp(e);  
    }  
```

### MSApp 常量
与、、和关联的允许的优先级值 `execAsyncAtPriority` `execAtPriority` `getCurrentPriority` `isTaskScheduldAtPriorityOrHigher` 。

#### Current
`current`

|类型 | 描述 |
|:---- |:--- |
|DOMString | 当 `current` 与相应的方法（另请参阅节）一起使用时，该方法将在执行所请求的操作时使用当前的上下文优先级。

#### 高 
`high`

|类型 | 描述 |
|:---- |:--- |
|DOMString | 当 `high` 与相应的方法（请参阅节）一起使用时，该方法在执行请求的操作时将使用高于正常优先级，并且将在任何现有的正常优先级工作之前调度操作。

#### Idle
`idle`

|类型 | 描述 |
|:---- |:--- |
|DOMString | 当 `ideal` 与相应的方法（请参阅节）一起使用时，该方法在执行请求的操作时将使用低于正常优先级，并且在任何现有的常规优先级工作后将调度该操作。

#### 正常
`normal`

|类型 | 描述 |
|:---- |:--- |
|DOMString | 当 `normal` 与相应的方法（另请参阅节）一起使用时，该方法将在执行请求的操作时使用常规的现有优先级。

#### 示例

```javascript
if (window.MSApp.CURRENT) {
  document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
}
```

#### 要求
|IDL | Mshtml |
|:---- |:--- |

## MSAppAsyncOperation

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```

### start
启动 `MSAppAsyncOperation` 。

```javascript
var retval = MSAppAsyncOperation.start();
```

#### 参数
无。

#### 返回值
无。

#### 属性
`error` 属性

|类型 | 描述 |
|:---- |:--- |
|DOMError | 表示中的错误 `MSAppAsyncOperation` 。

```javascript
p = object.error
```

`oncomplete` 属性

|类型 | 描述 |
|:---- |:--- |
|EventHandler | 用于在完成时设置事件处理程序的属性 `MSAppAsyncOperation` 。

```javascript
p = object.oncomplete
```

`onerror` 属性

|类型 | 描述 |
|:---- |:--- |
|EventHandler | 在期间发生错误时设置事件处理程序的属性 `MSAppAsyncOperation` 。

```javascript
p = object.onerror
```

`readyState` 属性

|类型 | 描述 |
|:---- |:--- |
|数字 | 表示使用 JavaScript 的 Windows 应用中的异步操作的状态。 值包括：已启动 [0]，已完成 [1]，错误 [2]。

```javascript
p = object.readyState
```

`result` 属性

|类型 | 描述 |
|:---- |:--- |
|Any |表示的结果 `MSAppAsyncOperation` 。

```javascript
p = object.result
```
