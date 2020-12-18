---
title: MSApp API 参考
description: 提供可帮助您创建 Blob 和 MSStream 对象的帮助程序函数。  使用 JavaScript 的 Windows 应用支持 MSApp 对象和成员。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp， PWA， 文件上载， 博客， MSStream， windows 10 应用， uwp， edge
ms.date: 12/02/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9a3ad670f61bfafa4480c538dd8f28c7013b7d7f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232318"
---
# MSApp  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

MSApp 对象及其成员仅支持使用 JavaScript \ (（包括访问 Windows API 功能的 PWA）的 Windows 应用) 。  MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中的 HTML 文档的本地上下文中;否则，该对象不存在 (因此，该对象的方法和属性均) 。  

它提供可帮助您创建 [Blob](https://developer.mozilla.org/docs/Web/API/Blob) 和 [MSStream 对象的帮助程序](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) 函数。  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [方法](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      [clearTemporaryWebDataAsync](#cleartemporarywebdataasync)， [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)， [createDataPackage](#createdatapackage)， [createDataPackageFromSelection，](#createdatapackagefromselection) [createFileFromStorageFile](#createfilefromstoragefile)， [createStreamFromInputStream](#createstreamfrominputstream)， [execAsyncAtPriority](#execasyncatpriority)， [execAtPriority](#execatpriority)， [getCurrentPriority](#getcurrentpriority)， [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)，[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)， [getViewId](#getviewid)， [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher)， [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations)， [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts)， [terminateApp.](#terminateapp)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [常量](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      [当前](#current)、 [高](#high)、 [空闲](#idle)、 [正常](#normal)。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [MSAppAsyncOperation 接口](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [start](#start)  
   :::column-end:::
:::row-end:::  

## MSApp 方法  

### clearTemporaryWebDataAsync  

:::row:::
   :::column span="":::
      清除应用或 [WebView](../../hosting/webview/index.md)的缓存和索引DB 数据。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      此方法没有任何参数。  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      类型 [：IAsyncAction](/uwp/api/windows.foundation.iasyncaction)  
      
      表示异步操作。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### createBlobFromRandomAccessStream  

:::row:::
   :::column span="":::
      从[IRandomAccessStream 对象创建](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)Blob。 [](https://developer.mozilla.org/docs/Web/API/Blob)  在处理应用中的对象时，应使用此方法，以便从流创建基于 `IRandomAccessStream` W3C 的对象。  创建 blob 后，它可以与 [FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API](https://developer.mozilla.org/docs/Web/API/URL)和 [XMLHttpRequest 一起使用](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `type` [in]  
      
      | 类型 | 说明 |  
      |:---- |:--- |  
      | 字符串 | 数据的内容类型。  此字符串的格式应为 RFC 2616 的第 3.7 节中定义的媒体类型令牌中指定的格式。  |  
      
      `stream` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 要存储在 Blob 中的[IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Blob | 包含流的新 blob 对象。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      | 异常 | 条件 |  
      |:---- |:--- |  
      | TypeMismatchError | 节点类型与预期的参数类型不兼容。  对于早于 Internet Explorer 10 的版本，TYPE_MISMATCH_ERR返回。  |  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      通过窗口对象的 MSApp 命名空间从 Windows 运行时类型创建 Blob。  此方法将创建一个 blob，该 blob 实质上是提供给 [它的 RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 对象的光包装。  blob 拥有此流的生存期，该流将在 blob 销毁时关闭。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      var randomAccessStream = dataPackage.GetData("image/bmp");
      var blob = window.MSApp.createBlobFromRandomAccessStream("image/bmp", randomAccessStream);
      var url = window.URL.createObjectURL(blob, {oneTimeOnly:true});
      
      document.getElementById("imagetag").src = url; 
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### createDataPackage  

:::row:::
   :::column span="":::
      将用户或应用程序的指定区域转换为可共享的 HTML 片段。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `object` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 可以从选择对象创建此范围，例如： 或 `window.selection.getRangeAt(0)` 手动创建。  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 包含指定范围的 HTML 标记。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      此方法仅支持[文档对象模型 (DOM) Range，](https://developer.mozilla.org/docs/Web/API/Range)而不是[TextRange。](/uwp/api/windows.ui.xaml.documents.textrange)  指定范围的返回数据包包含剪贴板格式的 HTML 标记。  
      
      返回的数据包没有可用的属性。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      无。  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### createDataPackageFromSelection  

:::row:::
   :::column span="":::
      将用户或应用程序的选择转换为可共享的 HTML 片段。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      此方法没有任何参数。  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 包含指定范围的 HTML 标记。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      所选内容返回的数据包包含剪贴板格式的 HTML 标记。  如果在应用程序的 UI 中没有任何用户选择，则 `createDataPackageFromSelection` 返回 `null` 。  
      
      返回的数据包没有可用的属性。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### createFileFromStorageFile  

:::row:::
   :::column span="":::
      将 [WinRT](/uwp/api/) [StorageFile 转换为](/uwp/api/windows.storage.storagefile) 标准 W3C [文件](https://developer.mozilla.org/docs/Web/API/File) 对象。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `storageFile` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 包含存储文件。  |  
   :::column-end:::
   :::column span="":::
      **返回值**
      
      无    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      | 异常 | 条件 |  
      |:---- |:--- |  
      | TypeMismatchError | 指定的 W3C 文件引用无效。  对于早于 Internet Explorer 10 的版本， `TYPE_MISMATCH_ERR` 将返回。  |  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### createStreamFromInputStream  

:::row:::
   :::column span="":::
      从 InputStream 创建[MSStream。](https://msdn.microsoft.com/library/hh772327) [](https://msdn.microsoft.com/library/hh772328)  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `type` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 数据的内容类型。  此字符串的格式应为 RFC 2616 的第 3.7 节中定义的媒体类型令牌中指定的格式。  \ ([请参阅 MIME 类型，] (如 ， 等 https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) `text/plain` `text/html` `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` \) 。  
      
      `inputStream` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 要[存储在中的 IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`  |  
   :::column-end:::
   :::column span="":::
      **返回值**
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      此方法采用内容类型和 `IInputStream` 引用。  然后，该方法验证传入的流引用是一个类型实例，如果没有， `IInputStream` 则引发 `DOMException TYPE_MISMATCH_ERR` 。  如果未发生错误，则 `createStreamFromInputStream` 从 `MSStream` (\) 创建 \) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      An `IInputStream` can be used to create an `MSStream` .  与本质上一次使用的对象一样，第一次由图像元素解析时将吊销创建的所有 `MSStreams` `URL.createObjectURL` URL。  此外，使用流后，对此对象的第二个 URL 的请求将失败。  
      
      ```javascript
      var inputStream = myInputStream; //get InputStream from socket API, and so on
      var stream = MSApp.createStreamFromInputStream("image/bmp", inputstream);
      document.getElementById("imagetag").src = URL.createObjectURL(stream); 
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### execAsyncAtPriority  

:::row:::
   :::column span="":::
      根据给定的优先级安排稍后执行的回调。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `asynchronousCallback` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 函数 | 异步运行的回调函数，以给定优先级调度。  |  
      
      `priority` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 运行 asynchronousCallback 回调的上下文优先级值。  请参阅 [MSApp 常量](#msapp-constants)。  |  
      
      `args` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |   
      | Any | 作为参数 1 等传递给同步Callback 回调函数 \ (的可选一系列参数\) 。  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      此方法不返回值。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      提供的 `asynchronousCallback` 回调函数稍后异步执行。  `asynchronousCallback` 将按照提供的优先级调度。  普通优先级等效于现有的 [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。  当回调运行时，当前上下文优先级将设置为在执行回调期间提供的优先级参数值。  
      
      回调 `asynchronousCallback` 参数可以是任何函数。  如果参数在参数 `priority` 之后提供，则所有参数都将传递给回调函数。  
      
      与回调函数返回的任何对象不同，将忽略 `execAtPriority` `asynchronousCallback` \ (，并且不会通过 `execAsyncAtPriority` \) 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### execAtPriority  

:::row:::
   :::column span="":::
      以给定的上下文优先级运行指定的回调函数。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `synchronousCallback` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 函数 | 要以给定优先级上下文优先级同步运行的回调函数。  |  
      
      `priority` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 运行回调函数时，当前上下文优先级值将设置为的指定 `synchronousCallback` 优先级值。  请参阅 [MSApp 常量](#msapp-constants)。  |  
      
      `args` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 作为参数 1 等传递给回调函数 \ (的可选系列参数 `synchronousCallback` \) 。  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 返回回调 `synchronousCallback` \ (的返回值（如果适用\) ）。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      提供的 `synchronousCallback` 回调方法将同步执行。  当前上下文优先级更改为在提供的回调 (期间由优先级参数) 给定的优先级值。  一旦回调函数完成执行，优先级将返回到调用之前的 `execAtPriority` 上一个值。  返回值 `execAtPriority` 是回调方法 \ (\) 。  
      
      回调 `synchronousCallback` 参数可以是任何函数。  如果在优先级参数之后提供了任何参数，则这些参数将传递给提供的回调方法。  如果回调参数返回值，则此值也将成为返回 `execAtPriority` 值。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
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
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### getCurrentPriority  

:::row:::
   :::column span="":::
      返回当前上下文优先级。  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 返回值是字符串之一 `MSApp.HIGH` ，或 `MSApp.NORMAL` `MSApp.IDLE` 。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      此方法返回当前的上下文优先级 \ (，请参阅 [MSApp 常量](#msapp-constants)\) ，可通过 `execAtPriority` 和 进行更改 `execAsyncAtPriority` 。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      if (MSApp.getCurrentPriority() === MSApp.IDLE) { 
          // YOUR CODE HERE
      }
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### getHtmlPrintDocumentSource  

已弃用同步 API。  对于 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。  对于 Windows 8 和 8.1 应用，请参阅 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。  

### getHtmlPrintDocumentSourceAsync  

:::row:::
   :::column span="":::
      返回要打印的源内容。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `htmlDoc` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 文档 | 要打印的 HTML 文档。  它可以是根文档、iframe 中的文档、文档片段或 SVG 文档。  请注意，htmlDoc 必须是文档，而不是元素。  |  
   :::column-end:::
   :::column span="":::
      **返回值**
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例 1**  
      
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
   :::column-end:::
   :::column span="":::
      **示例 2**  
      
      ```javascript
      function registerForPrintContract() {
              var printManager = Windows.Graphics.Printing.PrintManager.getForCurrentView();
              printManager.onprinttaskrequested = onPrintTaskRequested;
              console.log("Print Contract registered.  Use the Print button to print.", "sample", "status");
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
   :::column-end:::
:::row-end:::  

### getViewId  

:::row:::
   :::column span="":::
      支持多个窗口。  
      
      > [!NOTE] 
      > 在 Win8.1 中，JavaScript UWP 应用支持使用 MSApp DOM API 的多个窗口，这些 API 现已弃用。  对于 Windows 10，请使用 `window.open` 、 `window` 和新的 `MSApp.getViewId` 。  
      
      | 描述 |Windows 10 | Windows 8.1 |  
      |:---- |:---- |:--- |  
      | 创建新窗口 | [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) | [MSApp.createNewView](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |新窗口对象 | [窗口](https://developer.mozilla.org/docs/Web/API/Window) |[MSAppView](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `window`
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 一个代表包含 DOM 文档的窗口的对象。  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      `viewId`
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 数字 | 可以与各种 [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 一起使用。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      使用 [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) 和 [window](https://developer.mozilla.org/docs/Web/API/Window) 创建新窗口，但随后要与 WinRT API 交互，请添加 `MSApp.getViewId` API。  它将对象 `window` 作为参数，并返回可用于各种 `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 的编号。  
      
      *   延迟可见性  
          
          WinRT 中的视图通常开始隐藏，并且最终开发人员使用类似方法在视图完全准备好 `TryShowAsStandaloneAsync` 后显示视图。  在 Web 中，立即显示一个窗口，最终用户可以 `window.open` 监视内容加载和呈现。  若要让新窗口像 WinRT 中的视图一样运行，并且不会立即显示，我们添加了 `window.open` 一个选项。  例如：  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   主窗口差异  
          
          操作系统最初打开的主窗口的行为不同于它打开的辅助窗口：  
          
          | 描述 | 主要 | 辅助边框 |  
          |:---- |:--- |:--- |  
          | window.open | 允许 | 不允许 |  
          | window.close | 关闭应用 | 关闭窗口 |  
          | 导航限制 | 仅 ACUR | 无限制 |  
          
          不允许打开辅助窗口的限制可能会在将来根据反馈 [而更改](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。  
      
      *   同源通信限制  
          
          存在一个难以解决的技术问题，即无法正确支持同步、同源、跨窗口、脚本调用。  打开同一个源的窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。  `postMessage` 调用可以正常工作，并且建议尽可能执行一些操作。  正在努力改进此问题。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### isTaskScheduledAtPriorityOrHigher  

:::row:::
   :::column span="":::
      返回一个布尔 值，该值指示在给定优先级级别还是更高优先级存在挂起的工作。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `priority` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 优先级值 \ (请参阅 [MSApp 常量](#msapp-constants)\) 指定优先级级别及以上以查询任何未完成的排队工作。  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 布尔 | 返回 `true` 指定优先级或高于指定优先级的任何排队工作， `false` 否则返回。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      此方法为 JavaScript 代码提供了一种方法，用于确定各个优先级 `isTaskScheduledAtPriorityOrHigher` 级别 \ (或更高版本\) 是否有挂起的工作，目的是调用 JavaScript 代码随后可以决定获得更高优先级的工作。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
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
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### pageHandlesAllApplicationActivations  

:::row:::
   :::column span="":::
      用于避免刷新启动路径 (页面重新加载) 每个激活事件 \ (例如单击通知或固定磁贴\) 。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 布尔 | 用于 `MSApp.pageHandlesAllApplicationActivations(true)` 始终跳过刷新页面重新加载 (路径，) 直接跳转到触发 `WebUIApplication` 激活的事件。  要求所有页面单独处理激活事件。  将此方法定义为，单击激活的事件 `true` \ (如 notification\) 不会触发重新加载，这是单页应用避免重新加载页面的必备条件。  |  
   :::column-end:::
   :::column span="":::
      **返回值**
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
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
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### suppressSubdownloadCredentialPrompts  

:::row:::
   :::column span="":::
      控制应用是否在下载资源期间禁止可能的身份验证提示。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
     
      `suppress` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 布尔 | 如果值为 true，则禁止潜在的身份验证提示。  值为 false 不会禁止用户的任何潜在身份验证提示。  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      该方法控制应用程序在下载资源期间是否禁止 `suppressSubdownloadCredentialPrompts` 潜在的身份验证提示。  默认行为是禁止显示凭据提示。  
      
      `suppressSubdownloadCredentialPrompts` 供可能加载大量需要身份验证的资源的应用程序使用，例如邮件应用程序 \ (其中可能包含一个新闻稿，其中包含许多图像，其中每个图像都需要身份验证\) 。  
      
      在禁止显示凭据提示时，在访问需要身份验证的资源时，将不会显示用于向服务器进行身份验证的对话框，并且不会下载资源。  请注意 `suppressSubdownloadCredentialPrompts` ，这不会影响其他可能的提示，如代理身份验证或客户端认证请求对话框，也不会影响 XHR。  
      
      请注意， `suppressSubdownloadCredentialPrompts` 这会影响应用程序内的所有内容，包括元素中托管 `webview` 的内容。  
      
      > [!IMPORTANT]
      > 将缓存凭据提示决策。  因此，在禁止显示凭据提示时将立即生效，在禁止显示凭据提示后允许凭据提示可能需要重新加载文档以生效。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      ```javascript
      // Set to true to suppress potential credential prompts:
      MSApp.suppressSubdownloadCredentialPrompts(true);
      // Now one can load content or navigate iframe/webview to some other site.
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### terminateApp  


:::row:::
   :::column span="":::
      终止当前应用程序并生成故障报告。  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      `error` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 错误 | `Error`可用于描述触发终止的错误的对象。  对象必须包含数字、说明和堆栈属性;如果对象不包含这些属性，则不生成 `Error` 故障报告。  |  
   :::column-end:::
   :::column span="":::
      **返回值**
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      如果报告的问题成为应用的前 5 个问题之一，它将显示在应用的"质量 `terminateApp` "页上。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      此示例在 `terminateApp` 遇到异常时调用。  它使用 `Error` 捕获异常时提供的对象。  
      
      ```javascript
      try {  
          var obj2 = null;  
          obj2.val = 5;  
      }  
      catch(e) {  
          window.MSApp.terminateApp(e);  
      }  
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### MSApp 常量  

:::row:::
   :::column span="":::
      允许的优先级值与 `execAsyncAtPriority` 、 `execAtPriority` 和 `getCurrentPriority` 相关联 `isTaskScheduldAtPriorityOrHigher` 。  
   :::column-end:::
   :::column span="":::
      #### 当前  
      
      `current`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 当 `current` 与适当的方法 \ (See also section\) ， the method will use the current contextual priority when executing the requested operation.  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 高   
      
      `high`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 当与适当的方法 `high` \ (See also section\) 一起使用时，该方法在执行请求的操作时将使用高于正常优先级，并且将在任何现有的普通优先级工作之前调度该操作。  |  
   :::column-end:::
   :::column span="":::
      #### Idle  
      
      `idle`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 当与适当的方法 `ideal` \ (See also section\) 一起使用时，该方法在执行请求的操作时将使用低于正常优先级，并且将在任何现有的普通优先级工作后调度该操作。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 正常  
      
      `normal`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 当与适当的方法一 (另请参阅) ，该方法将在执行请求的操作时使用正常的现有 `normal` 优先级。  |  
   :::column-end:::
   :::column span="":::
      **示例**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **要求**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | IDL | Mshtml.idl |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## MSAppAsyncOperation  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### start  

:::row:::
   :::column span="":::
      启动 `MSAppAsyncOperation` 。  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **参数**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **返回值**
      
      无。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **属性**  
      
      `error` property  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMError | 表示中的错误 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` property  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | EventHandler | 属性，用于设置完成时的事件处理程序 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` property  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | EventHandler | 属性，用于设置错误期间的事件处理程序 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` property  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 数字 | 表示使用 JavaScript 的 Windows 应用中异步操作的状态。  值包括： `Started[0]` ， `Completed[1]` 。 `Error[2]`  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` property  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any |表示 `MSAppAsyncOperation` 的结果。  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
