---
title: MSApp API 参考
description: 提供帮助程序函数，使你能够创建 Blob 和 MSStream 对象。  使用 JavaScript 的 Windows 应用支持 MSApp 对象和成员。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/29/2020
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp、PWA、文件上传、博客、MSStream、windows 10 应用、uwp、edge
ms.openlocfilehash: 4966f6afbe4e971d6a366de7e9b4f5a6cd2305e0
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942167"
---
# MSApp  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

仅使用 JavaScript \ (的 Windows 应用支持 MSApp 对象及其成员，其中包括访问 Windows API 功能\) 。  MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中 HTML 文档的本地上下文中;否则，该对象不存在 (而且，该对象的方法和属性都不) 。  

它提供帮助程序函数，帮助你创建 [Blob 和](https://developer.mozilla.org/docs/Web/API/Blob) [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) 对象。  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [方法](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      [clearTemporaryWebDataAsync、](#cleartemporarywebdataasync) [createBlobFromRandomAccessSream、](#createblobfromrandomaccessstream) [createDataPackage，](#createdatapackage) [createDataPackageFromSelection、](#createdatapackagefromselection) [createFileFromStorageFile、](#createfilefromstoragefile)createStreamFromInputStream、execAsyncAtPriorityCurrentPriority， [getCurrentPriority](#getcurrentpriority) [getHtmlPrintDocumentSource，](#gethtmlprintdocumentsource)[getCodePrintDocumentSourceAsynce，](#gethtmlprintdocumentsourceasync) [getViewId，](#getviewid) [isTaskScheduledAtPriorityOrHigher、](#istaskscheduledatpriorityorhigher) [pageHandlesAllApplicationActivations，](#pagehandlesallapplicationactivations) [suppressSubdownloadCredentialPrompts，](#suppresssubdownloadcredentialprompts) [terminateApp.](#terminateapp) [createStreamFromInputStream](#createstreamfrominputstream) [execAsyncAtPriority](#execasyncatpriority) [execAtPriority](#execatpriority)  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [常量](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      [current](#current)"current"、"high"、"idle"、"[正常"。](#normal) [high](#high) [idle](#idle)  
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
      清除应用或 [WebView](../../webview.md)的缓存和索引DB 数据。  
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
      从[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)对象创建[Blob。](https://developer.mozilla.org/docs/Web/API/Blob)  在处理应用中的对象时，你应该使用 `IRandomAccessStream` 此方法，以便从流创建基于 W3C 的对象。  创建该 blob 后，它可与 [FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API 和](https://developer.mozilla.org/docs/Web/API/URL) [XMLHttpRequest 结合使用](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。  
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
      | 字符串 | 数据的内容类型。  此字符串应为在 RFC 2616 第 3.7 部分中定义的媒体类型令牌中指定的格式。  |  
      
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
      | TypeMismatchError | 节点类型与预期的参数类型不兼容。  对于早于上下文Internet Explorer 10，将TYPE_MISMATCH_ERR版本。  |  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      通过窗口对象上的 MSApp 命名空间从 Windows 运行时类型创建 Blob。  此方法将创建一个 blob，它实其实是一个提供给它的 [RandomAccessStream 对象](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 上的浅色包预防器。  blob 拥有此流的生命周期，并且在 blob 被延迟时关闭流。  
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
      将用户或应用程序的指定范围转换为可以共享的 HTML 片段。  
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
      | Any | 可从所选对象（如：）创建此范围，也可以 `window.selection.getRangeAt(0)` 从选择对象中创建，也可以从手动操作。  |  
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
      
      此方法仅支持文档[对象模型， (DOM) ](https://developer.mozilla.org/docs/Web/API/Range) [TEXTRange。](/uwp/api/windows.ui.xaml.documents.textrange)  指定范围的返回数据包包含剪贴板格式的 HTML 标记。  
      
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
      将用户或应用程序的选择转换为可以共享的 HTML 片段。  
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
      
      所选内容的返回数据包包含剪贴板格式的 HTML 标记。  如果应用程序的 UI 内的任何位置未进行用户选择，则返回 `createDataPackageFromSelection` `null` 结果。  
      
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
      将 [WinRT](/uwp/api/) [StorageFile 转换](/uwp/api/windows.storage.storagefile) 为标准 W3C [文件](https://developer.mozilla.org/docs/Web/API/File) 对象。  
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
      | TypeMismatchError | 指定的 W3C 文件引用无效。  对于早于上述时间Internet Explorer 10 `TYPE_MISMATCH_ERR` 将返回。  |  
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
      从[InputStream](https://msdn.microsoft.com/library/hh772327)[创建 MSStream。](https://msdn.microsoft.com/library/hh772328)  
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
      | DOMString | 数据的内容类型。  此字符串应为在 RFC 2616 第 3.7 部分中定义的媒体类型令牌中指定的格式。  \ ([请参阅 MIME 类型] (，如 https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) ， ， ， ， ， ， ， ， ， `text/plain` ， `text/html` ， `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` 等等等.) 。  
      
      `inputStream` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 要 [存储在的 IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream` 中。  |  
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
      
      此方法采用内容类型和 `IInputStream` 参考。  然后，该方法验证传递到的流引用是否是类型的实例 `IInputStream` ，而且是否引发 `DOMException TYPE_MISMATCH_ERR` 。  如果没有错误，请从 `createStreamFromInputStream` 它的 `MSStream` inputs\)  (。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      应用 `IInputStream` 可以用来创建 `MSStream` 。  在本身上一次性对象一次使用，由创建的所有 URL 在第一次被图像元素解 `MSStreams` `URL.createObjectURL` 析时都会被吊销。  此外，在使用流之后，对此对象的第二个 URL 请求将失败。  
      
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
      安排以后执行的回调，并与给定优先级执行。  
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
      | 函数 | 要异步运行的回调函数，在给定优先级上调度。  |  
      
      `priority` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 运行 asynchronousCallback 回调时的上下文优先级值。  请 [参见 MSApp 常量](#msapp-constants)。  |  
      
      `args` [in]
      
      | 类型 | 描述 |  
      |:---- |:--- |   
      | Any | 传递到 synchronousCallback 回调函数 \ (的可选参数系列作为参数 1 依此类 ) 推。。  |  
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
      
      稍 `asynchronousCallback` 后异步执行提供的回调函数。  `asynchronousCallback` 将按所提供优先级分发。  正常优先级相当于现有 [集合](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。  运行回调时，在执行期间将当前上下文优先级设置为所提供优先级参数值。  
      
      回 `asynchronousCallback` 调参数可以是任何函数。  如果参数在参数后提供 `priority` ，则这些参数将全都传递给回调函数。  
      
      与此 `execAtPriority` 不同，回调函数 `asynchronousCallback` 返回的任何对象都将忽略 \ (且不通过 `execAsyncAtPriority` \) 返回。  
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
      在给定的上下文优先级运行指定的回调函数。  
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
      | 函数 | 要在给定优先级优先级上同步运行的回调函数。  |  
      
      `priority` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 运行回调函数时会设置当前上下文优先级值的指定 `synchronousCallback` 优先级值。  请 [参见 MSApp 常量](#msapp-constants)。  |  
      
      `args` [in]  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 传递到回调函数 `synchronousCallback` \ (作为参数 1 依此类的可选系列) 。  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any | 返回返回适用 `synchronousCallback` \ (的回调值) 。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      提供 `synchronousCallback` 的回调方法是同步执行的。  当前的上下文优先级在提供的回调 (的优先级参数) 更改为提供的回调函数的优先级参数值。  回调函数执行完成后，优先级将返回到调用前的之前的 `execAtPriority` 值。  返回值是 `execAtPriority` 作为 provided\) 的回调方法 \ (的返回。  
      
      回 `synchronousCallback` 调参数可以是任何函数。  如果在优先级参数之后提供了任何参数，则这些参数将传递到所提供的回调方法。  如果回调参数返回一个值，则此值也将成为返回 `execAtPriority` 值。  
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
      | DOMString | 返回值是一个字符串， `MSApp.HIGH` 或 `MSApp.NORMAL` `MSApp.IDLE` 。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      此方法返回当前上下文优先级 \ (请参阅 [MSApp 常](#msapp-constants)量 \) ，可以通过此方法 `execAtPriority` 进行更改 `execAsyncAtPriority` 。  
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

已弃用的同步 API。  有关 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。  对于 Windows 8 和 8.1 应用，请参阅 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。  

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
      | 文档 | 要打印的 HTML 文档。  可以是根文档、iframe 中的文档、文档片段或 SVG 文档。  请注意，htmlDoc 必须是文档，而非元素。  |  
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
      > 在 Win8.1 JavaScript UWP 应用中，使用 MSApp DOM API 支持多个窗口，这些窗口现在已按现适用。  对于 Windows 10、使用 `window.open` 、 `window` 新版 `MSApp.getViewId` 和新应用。  
      
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
      | DOMString | 代表包含 DOM 文档窗口的对象。  |  
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
      
      使用 [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) [和 window](https://developer.mozilla.org/docs/Web/API/Window) 来创建新窗口，然后若要与 WinRT API 交互，请添加 `MSApp.getViewId` API。  它将对象作为参数返回一个数字，并返回一个数字用于 `window` `viewId` [各种 Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API。  
      
      *   延迟可见性  
          
          通常情况下，WinRT 中的视图开始隐藏，而最终开发人员使用一些像来完全准备好视图 `TryShowAsStandaloneAsync` 这样的视图。  在 Web 世界中，立即显示一个窗口，最终用户就可以在加载和呈现内容时 `window.open` 观看。  让新窗口像 WinRT 中的视图一样，而不会立即显示，我们添加了一个 `window.open` 选项。  例如：  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   主要窗口差别  
          
          操作系统最初打开的主要窗口的操作方式与其打开的辅助窗口的行为不同：  
          
          | 描述 | 主要 | 辅助边框 |  
          |:---- |:--- |:--- |  
          | window.open | 允许 | 不允许 |  
          | window.close | 关闭应用 | 关闭窗口 |  
          | 导航限制 | 仅 ACUR | 无限制 |  
          
          此项限制不允许打开辅助窗口，这可能会在以后根据反馈而 [更改](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。  
      
      *   相同 Origin Communication 限制  
          
          一个很难的技术问题，阻止正确支持同步、同一原点、跨窗口、脚本调用。  当您打开一个相同的原始窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。  `postMessage` 调用工作正常工作，是可能实现此操作的推荐方法。  正在努力改进此问题。  
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
      返回一个布尔值，指示已给定优先级级别是否有挂起的工作。  
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
      | DOMString | 优先级值 \ ([请参阅"MSApp 常](#msapp-constants)量 /) 从而指定任何未完成的已完成工作的优先级及以上查询。  |  
   :::column-end:::
   :::column span="":::
      **返回值**  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 布尔 | 如果 `true` 具有以上优先级或以上内容的任何已批量化工作， `false` 则返回。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **异常**  
      
      无。  
   :::column-end:::
   :::column span="":::
      **备注**  
      
      此方法针对 JavaScript 代码提供了一种方式来确定与调用 JavaScript 代码可以在后面的 intent 那些优先级级别 （ (或更高版本\) 上有挂起的工作。然后，调用 JavaScript 代码可决定将优先级工作分配给 `isTaskScheduledAtPriorityOrHigher` 更高的工作。  
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
      在每个激活 (的事件 \ (（例如，单击通知或已固定的磁贴\) ）之前，避免更新开始路径的) 页面重新加载) 。  
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
      | 布尔 | 用 `MSApp.pageHandlesAllApplicationActivations(true)` 来始终刷新开始路径 (页面重新加载) 而直接跳转触发 `WebUIApplication` 已激活事件。  需要所有页面单独处理激活事件。  通过将此方法定义为， `true` 单击已激活的事件 \ (（如 notification\) ）将不会触发重新加载，需要单页面应用需要防止页面重新加载。  |  
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
      控制在下载资源期间应用是否会为其隐藏可能的身份验证提示。  
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
      | 布尔 | 有效的值值不能显示可能的身份验证提示。  假如未阻止用户发出的任何潜在身份验证提示。  |  
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
      
      `suppressSubdownloadCredentialPrompts`此方法控制应用是否在下载资源期间为应用停用可能的身份验证提示。  默认行为是不隐藏凭据提示。  
      
      `suppressSubdownloadCredentialPrompts` 应用适用于应用，它可能会加载需要身份验证的过多资源（如邮件应用 \ (），邮件应用可能包含包含大量图像（每个图像都需要身份验证\) ）的新闻稿。  
      
      当提供凭据提示时，在访问要求身份验证的资源时，不会显示用于身份验证服务器的对话框，并且不会下载该资源。  请 `suppressSubdownloadCredentialPrompts` 注意，不会影响代理身份验证或客户端认证请求对话框等其他可能提示，也不会影响 XHR。  
      
      请注意， `suppressSubdownloadCredentialPrompts` 会影响应用程序中的所有内容，包括在元素中托管 `webview` 的内容。  
      
      > [!IMPORTANT]
      > 已统一提示决定。  因此，当停用凭据提示时，即时取消凭据提示将立即生效，因此，在隐藏凭据提示后，可能需要重新加载凭据提示，使其生效。  
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
      终止当前应用程序并生成失败报告。  
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
      | 错误 | `Error`一个可用于描述触发终止的错误的对象。  `Error`该对象必须包含数字、描述和堆叠属性;如果对象不包含这些属性，则不会生成失败报告。  |  
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
      
      如果该问题报告的 `terminateApp` 问题成为你的应用的最高 5 个问题之一，它将显示在该应用的"质量"页上。  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **示例**  
      
      遇到 `terminateApp` 异常时此示例调用。  它使用 `Error` 你关闭异常时提供的对象。  
      
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
      允许关联、、和 `execAsyncAtPriority` `execAtPriority` `getCurrentPriority` `isTaskScheduldAtPriorityOrHigher`  
   :::column-end:::
   :::column span="":::
      #### 当前  
      
      `current`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 与适当方法 \ (See also section\) 结合使用时，该方法将在执行所请求的操作时使用当前上 `current` 下文优先级。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 高   
      
      `high`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 与 `high` 相应方法 \ (请参阅另一节\) 时，执行请求的操作时将使用高于正常优先级，并将在任何现有正常优先级工作之前调度操作。  |  
   :::column-end:::
   :::column span="":::
      #### Idle  
      
      `idle`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 与 `ideal` 适当方法 \ (See a- section\See a\ see a\ ) 当执行请求的操作时，该方法将使用低于正常优先级，并将在任何现有正常优先级工作后分发操作。  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### 正常  
      
      `normal`  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMString | 与 `normal` 适当的方法一起使用 (请参阅"另请参阅) "时，此方法将在执行请求的操作时使用正常的现有优先级。  |  
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
      开始 `MSAppAsyncOperation` 。  
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
      
      `error` 属性  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | DOMError | 表示一个错误 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` 属性  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | EventHandler | 用于在完成时设置事件处理程序的属性 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` 属性  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | EventHandler | 用于在错误的过程中设置事件处理程序的属性 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` 属性  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | 数字 | 表示使用 JavaScript 的 Windows 应用中异步操作的状态。  值包括 `Started[0]` `Completed[1]` ：、 `Error[2]`  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` 属性  
      
      | 类型 | 描述 |  
      |:---- |:--- |  
      | Any |表示结果 `MSAppAsyncOperation` 。  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
