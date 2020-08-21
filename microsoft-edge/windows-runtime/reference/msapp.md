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
# <span data-ttu-id="16acb-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="16acb-105">MSApp</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="16acb-106">仅使用 JavaScript \ (的 Windows 应用支持 MSApp 对象及其成员，其中包括访问 Windows API 功能\) 。</span><span class="sxs-lookup"><span data-stu-id="16acb-106">The MSApp object and its members are supported only for Windows apps using JavaScript \(including PWAs accessing Windows API features\).</span></span>  <span data-ttu-id="16acb-107">MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中 HTML 文档的本地上下文中;否则，该对象不存在 (而且，该对象的方法和属性都不) 。</span><span class="sxs-lookup"><span data-stu-id="16acb-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>  

<span data-ttu-id="16acb-108">它提供帮助程序函数，帮助你创建 [Blob 和](https://developer.mozilla.org/docs/Web/API/Blob) [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) 对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="16acb-109">方法</span><span class="sxs-lookup"><span data-stu-id="16acb-109">Methods</span></span>](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="16acb-110">[clearTemporaryWebDataAsync、](#cleartemporarywebdataasync) [createBlobFromRandomAccessSream、](#createblobfromrandomaccessstream) [createDataPackage，](#createdatapackage) [createDataPackageFromSelection、](#createdatapackagefromselection) [createFileFromStorageFile、](#createfilefromstoragefile)createStreamFromInputStream、execAsyncAtPriorityCurrentPriority， [getCurrentPriority](#getcurrentpriority) [getHtmlPrintDocumentSource，](#gethtmlprintdocumentsource)[getCodePrintDocumentSourceAsynce，](#gethtmlprintdocumentsourceasync) [getViewId，](#getviewid) [isTaskScheduledAtPriorityOrHigher、](#istaskscheduledatpriorityorhigher) [pageHandlesAllApplicationActivations，](#pagehandlesallapplicationactivations) [suppressSubdownloadCredentialPrompts，](#suppresssubdownloadcredentialprompts) [terminateApp.](#terminateapp) [createStreamFromInputStream](#createstreamfrominputstream) [execAsyncAtPriority](#execasyncatpriority) [execAtPriority](#execatpriority)</span><span class="sxs-lookup"><span data-stu-id="16acb-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="16acb-111">常量</span><span class="sxs-lookup"><span data-stu-id="16acb-111">Constants</span></span>](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="16acb-112">[current](#current)"current"、"high"、"idle"、"[正常"。](#normal) [high](#high) [idle](#idle)</span><span class="sxs-lookup"><span data-stu-id="16acb-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="16acb-113">MSAppAsyncOperation 接口</span><span class="sxs-lookup"><span data-stu-id="16acb-113">MSAppAsyncOperation interface</span></span>](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [<span data-ttu-id="16acb-114">start</span><span class="sxs-lookup"><span data-stu-id="16acb-114">start</span></span>](#start)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="16acb-115">MSApp 方法</span><span class="sxs-lookup"><span data-stu-id="16acb-115">MSApp methods</span></span>  

### <span data-ttu-id="16acb-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="16acb-116">clearTemporaryWebDataAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-117">清除应用或 [WebView](../../webview.md)的缓存和索引DB 数据。</span><span class="sxs-lookup"><span data-stu-id="16acb-117">Clears cache and indexedDB data for the app or [WebView](../../webview.md).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-118">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-118">Parameters</span></span>**  
      
      <span data-ttu-id="16acb-119">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="16acb-119">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-120">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-120">Return value</span></span>**  
      
      <span data-ttu-id="16acb-121">类型 [：IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="16acb-121">Type: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span></span>  
      
      <span data-ttu-id="16acb-122">表示异步操作。</span><span class="sxs-lookup"><span data-stu-id="16acb-122">Represents an asynchronous action.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-123">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-123">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-124">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-124">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-125">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-125">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-126">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-126">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-127">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-127">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="16acb-128">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="16acb-128">createBlobFromRandomAccessStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-129">从[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)对象创建[Blob。](https://developer.mozilla.org/docs/Web/API/Blob)</span><span class="sxs-lookup"><span data-stu-id="16acb-129">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span>  <span data-ttu-id="16acb-130">在处理应用中的对象时，你应该使用 `IRandomAccessStream` 此方法，以便从流创建基于 W3C 的对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-130">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span>  <span data-ttu-id="16acb-131">创建该 blob 后，它可与 [FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API 和](https://developer.mozilla.org/docs/Web/API/URL) [XMLHttpRequest 结合使用](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。</span><span class="sxs-lookup"><span data-stu-id="16acb-131">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-132">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-132">Parameters</span></span>**  
      
      `type` <span data-ttu-id="16acb-133">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-133">[in]</span></span>  
      
      | <span data-ttu-id="16acb-134">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-134">Type</span></span> | <span data-ttu-id="16acb-135">说明</span><span class="sxs-lookup"><span data-stu-id="16acb-135">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-136">字符串</span><span class="sxs-lookup"><span data-stu-id="16acb-136">String</span></span> | <span data-ttu-id="16acb-137">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="16acb-137">Content type of the data.</span></span>  <span data-ttu-id="16acb-138">此字符串应为在 RFC 2616 第 3.7 部分中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="16acb-138">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  |  
      
      `stream` <span data-ttu-id="16acb-139">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-139">[in]</span></span>  
      
      | <span data-ttu-id="16acb-140">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-140">Type</span></span> | <span data-ttu-id="16acb-141">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-141">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-142">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-142">Any</span></span> | <span data-ttu-id="16acb-143">要存储在 Blob 中的[IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)</span><span class="sxs-lookup"><span data-stu-id="16acb-143">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-144">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-144">Return value</span></span>**  
      
      | <span data-ttu-id="16acb-145">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-145">Type</span></span> | <span data-ttu-id="16acb-146">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-146">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-147">Blob</span><span class="sxs-lookup"><span data-stu-id="16acb-147">Blob</span></span> | <span data-ttu-id="16acb-148">包含流的新 blob 对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-148">New blob object that contains the stream.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-149">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-149">Exceptions</span></span>**  
      
      | <span data-ttu-id="16acb-150">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-150">Exception</span></span> | <span data-ttu-id="16acb-151">条件</span><span class="sxs-lookup"><span data-stu-id="16acb-151">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-152">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="16acb-152">TypeMismatchError</span></span> | <span data-ttu-id="16acb-153">节点类型与预期的参数类型不兼容。</span><span class="sxs-lookup"><span data-stu-id="16acb-153">The node type is incompatible with the expected parameter type.</span></span>  <span data-ttu-id="16acb-154">对于早于上下文Internet Explorer 10，将TYPE_MISMATCH_ERR版本。</span><span class="sxs-lookup"><span data-stu-id="16acb-154">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-155">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-155">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-156">通过窗口对象上的 MSApp 命名空间从 Windows 运行时类型创建 Blob。</span><span class="sxs-lookup"><span data-stu-id="16acb-156">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span>  <span data-ttu-id="16acb-157">此方法将创建一个 blob，它实其实是一个提供给它的 [RandomAccessStream 对象](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 上的浅色包预防器。</span><span class="sxs-lookup"><span data-stu-id="16acb-157">This method will create a blob that is essentially a light wrapper over the [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span>  <span data-ttu-id="16acb-158">blob 拥有此流的生命周期，并且在 blob 被延迟时关闭流。</span><span class="sxs-lookup"><span data-stu-id="16acb-158">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-159">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-159">Example</span></span>**  
      
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

### <span data-ttu-id="16acb-160">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="16acb-160">createDataPackage</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-161">将用户或应用程序的指定范围转换为可以共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="16acb-161">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-162">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-162">Parameters</span></span>**  
      
      `object` <span data-ttu-id="16acb-163">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-163">[in]</span></span>  
      
      | <span data-ttu-id="16acb-164">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-164">Type</span></span> | <span data-ttu-id="16acb-165">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-165">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-166">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-166">Any</span></span> | <span data-ttu-id="16acb-167">可从所选对象（如：）创建此范围，也可以 `window.selection.getRangeAt(0)` 从选择对象中创建，也可以从手动操作。</span><span class="sxs-lookup"><span data-stu-id="16acb-167">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-168">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-168">Return value</span></span>**  
      
      | <span data-ttu-id="16acb-169">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-169">Type</span></span> | <span data-ttu-id="16acb-170">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-170">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-171">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-171">Any</span></span> | <span data-ttu-id="16acb-172">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="16acb-172">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-173">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-173">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-174">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-174">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-175">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-175">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-176">此方法仅支持文档[对象模型， (DOM) ](https://developer.mozilla.org/docs/Web/API/Range) [TEXTRange。](/uwp/api/windows.ui.xaml.documents.textrange)</span><span class="sxs-lookup"><span data-stu-id="16acb-176">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span>  <span data-ttu-id="16acb-177">指定范围的返回数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="16acb-177">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>  
      
      <span data-ttu-id="16acb-178">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="16acb-178">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-179">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-179">Example</span></span>**  
      
      <span data-ttu-id="16acb-180">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-180">None.</span></span>  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="16acb-181">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="16acb-181">createDataPackageFromSelection</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-182">将用户或应用程序的选择转换为可以共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="16acb-182">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-183">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-183">Parameters</span></span>**  
      
      <span data-ttu-id="16acb-184">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="16acb-184">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-185">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-185">Return value</span></span>**  
      
      | <span data-ttu-id="16acb-186">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-186">Type</span></span> | <span data-ttu-id="16acb-187">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-187">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-188">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-188">Any</span></span> | <span data-ttu-id="16acb-189">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="16acb-189">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-190">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-190">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-191">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-191">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-192">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-192">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-193">所选内容的返回数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="16acb-193">The returned data package for the selection contains HTML markup in clipboard format.</span></span>  <span data-ttu-id="16acb-194">如果应用程序的 UI 内的任何位置未进行用户选择，则返回 `createDataPackageFromSelection` `null` 结果。</span><span class="sxs-lookup"><span data-stu-id="16acb-194">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns `null`.</span></span>  
      
      <span data-ttu-id="16acb-195">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="16acb-195">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-196">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-196">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <span data-ttu-id="16acb-197">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="16acb-197">createFileFromStorageFile</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-198">将 [WinRT](/uwp/api/) [StorageFile 转换](/uwp/api/windows.storage.storagefile) 为标准 W3C [文件](https://developer.mozilla.org/docs/Web/API/File) 对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-198">Converts a [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) to a standard W3C [File](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-199">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-199">Parameters</span></span>**  
      
      `storageFile` <span data-ttu-id="16acb-200">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-200">[in]</span></span>
      
      | <span data-ttu-id="16acb-201">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-201">Type</span></span> | <span data-ttu-id="16acb-202">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-202">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-203">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-203">Any</span></span> | <span data-ttu-id="16acb-204">包含存储文件。</span><span class="sxs-lookup"><span data-stu-id="16acb-204">Contains the storage file.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-205">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-205">Return value</span></span>**
      
      <span data-ttu-id="16acb-206">无</span><span class="sxs-lookup"><span data-stu-id="16acb-206">None</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-207">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-207">Exceptions</span></span>**  
      
      | <span data-ttu-id="16acb-208">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-208">Exception</span></span> | <span data-ttu-id="16acb-209">条件</span><span class="sxs-lookup"><span data-stu-id="16acb-209">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-210">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="16acb-210">TypeMismatchError</span></span> | <span data-ttu-id="16acb-211">指定的 W3C 文件引用无效。</span><span class="sxs-lookup"><span data-stu-id="16acb-211">The specified W3C file reference is invalid.</span></span>  <span data-ttu-id="16acb-212">对于早于上述时间Internet Explorer 10 `TYPE_MISMATCH_ERR` 将返回。</span><span class="sxs-lookup"><span data-stu-id="16acb-212">For versions earlier than Internet Explorer 10, `TYPE_MISMATCH_ERR` is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-213">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-213">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-214">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-214">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-215">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-215">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="16acb-216">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="16acb-216">createStreamFromInputStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-217">从[InputStream](https://msdn.microsoft.com/library/hh772327)[创建 MSStream。](https://msdn.microsoft.com/library/hh772328)</span><span class="sxs-lookup"><span data-stu-id="16acb-217">Creates an [MSStream](https://msdn.microsoft.com/library/hh772328) from an [InputStream](https://msdn.microsoft.com/library/hh772327).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-218">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-218">Parameters</span></span>**  
      
      `type` <span data-ttu-id="16acb-219">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-219">[in]</span></span>
      
      | <span data-ttu-id="16acb-220">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-220">Type</span></span> | <span data-ttu-id="16acb-221">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-221">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-222">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-222">DOMString</span></span> | <span data-ttu-id="16acb-223">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="16acb-223">Content type of the data.</span></span>  <span data-ttu-id="16acb-224">此字符串应为在 RFC 2616 第 3.7 部分中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="16acb-224">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  <span data-ttu-id="16acb-225">\ ([请参阅 MIME 类型] (，如 https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) ， ， ， ， ， ， ， ， ， `text/plain` ， `text/html` ， `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` 等等等.) 。</span><span class="sxs-lookup"><span data-stu-id="16acb-225">\([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) such as `text/plain`, `text/html`, `image/jpeg`, `image/png`, `audio/mpeg`, `audio/ogg`, `audio/*`, `video/mp4`, and so on\).</span></span>  
      
      `inputStream` <span data-ttu-id="16acb-226">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-226">[in]</span></span>
      
      | <span data-ttu-id="16acb-227">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-227">Type</span></span> | <span data-ttu-id="16acb-228">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-228">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-229">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-229">Any</span></span> | <span data-ttu-id="16acb-230">要 [存储在的 IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream` 中。</span><span class="sxs-lookup"><span data-stu-id="16acb-230">The [IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-231">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-231">Return value</span></span>**
      
      <span data-ttu-id="16acb-232">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-232">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-233">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-233">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-234">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-234">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-235">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-235">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-236">此方法采用内容类型和 `IInputStream` 参考。</span><span class="sxs-lookup"><span data-stu-id="16acb-236">This method takes a content-type, and the `IInputStream` reference.</span></span>  <span data-ttu-id="16acb-237">然后，该方法验证传递到的流引用是否是类型的实例 `IInputStream` ，而且是否引发 `DOMException TYPE_MISMATCH_ERR` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-237">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span>  <span data-ttu-id="16acb-238">如果没有错误，请从 `createStreamFromInputStream` 它的 `MSStream` inputs\)  (。</span><span class="sxs-lookup"><span data-stu-id="16acb-238">If no error occurs, `createStreamFromInputStream` creates an `MSStream` \(from its inputs\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-239">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-239">Example</span></span>**  
      
      <span data-ttu-id="16acb-240">应用 `IInputStream` 可以用来创建 `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-240">An `IInputStream` can be used to create an `MSStream`.</span></span>  <span data-ttu-id="16acb-241">在本身上一次性对象一次使用，由创建的所有 URL 在第一次被图像元素解 `MSStreams` `URL.createObjectURL` 析时都会被吊销。</span><span class="sxs-lookup"><span data-stu-id="16acb-241">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span>  <span data-ttu-id="16acb-242">此外，在使用流之后，对此对象的第二个 URL 请求将失败。</span><span class="sxs-lookup"><span data-stu-id="16acb-242">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>  
      
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

### <span data-ttu-id="16acb-243">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="16acb-243">execAsyncAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-244">安排以后执行的回调，并与给定优先级执行。</span><span class="sxs-lookup"><span data-stu-id="16acb-244">Schedules a callback to be executed at a later time according to the given priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-245">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-245">Parameters</span></span>**  
      
      `asynchronousCallback` <span data-ttu-id="16acb-246">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-246">[in]</span></span>
      
      | <span data-ttu-id="16acb-247">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-247">Type</span></span> | <span data-ttu-id="16acb-248">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-248">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-249">函数</span><span class="sxs-lookup"><span data-stu-id="16acb-249">Function</span></span> | <span data-ttu-id="16acb-250">要异步运行的回调函数，在给定优先级上调度。</span><span class="sxs-lookup"><span data-stu-id="16acb-250">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>  |  
      
      `priority` <span data-ttu-id="16acb-251">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-251">[in]</span></span>
      
      | <span data-ttu-id="16acb-252">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-252">Type</span></span> | <span data-ttu-id="16acb-253">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-253">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-254">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-254">DOMString</span></span> | <span data-ttu-id="16acb-255">运行 asynchronousCallback 回调时的上下文优先级值。</span><span class="sxs-lookup"><span data-stu-id="16acb-255">The contextual priority value at which the asynchronousCallback callback is run.</span></span>  <span data-ttu-id="16acb-256">请 [参见 MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="16acb-256">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="16acb-257">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-257">[in]</span></span>
      
      | <span data-ttu-id="16acb-258">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-258">Type</span></span> | <span data-ttu-id="16acb-259">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-259">Description</span></span> |  
      |:---- |:--- |   
      | <span data-ttu-id="16acb-260">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-260">Any</span></span> | <span data-ttu-id="16acb-261">传递到 synchronousCallback 回调函数 \ (的可选参数系列作为参数 1 依此类 ) 推。。</span><span class="sxs-lookup"><span data-stu-id="16acb-261">An optional series of arguments that are passed to the synchronousCallback callback function \(as parameters 1 and so on\).</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-262">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-262">Return value</span></span>**  
      
      <span data-ttu-id="16acb-263">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="16acb-263">This method does not return a value.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-264">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-264">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-265">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-265">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-266">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-266">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-267">稍 `asynchronousCallback` 后异步执行提供的回调函数。</span><span class="sxs-lookup"><span data-stu-id="16acb-267">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span>  `asynchronousCallback` <span data-ttu-id="16acb-268">将按所提供优先级分发。</span><span class="sxs-lookup"><span data-stu-id="16acb-268">will be dispatched according to the provided priority.</span></span>  <span data-ttu-id="16acb-269">正常优先级相当于现有 [集合](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。</span><span class="sxs-lookup"><span data-stu-id="16acb-269">Normal priority is equivalent to the existing [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span>  <span data-ttu-id="16acb-270">运行回调时，在执行期间将当前上下文优先级设置为所提供优先级参数值。</span><span class="sxs-lookup"><span data-stu-id="16acb-270">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>  
      
      <span data-ttu-id="16acb-271">回 `asynchronousCallback` 调参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="16acb-271">The `asynchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="16acb-272">如果参数在参数后提供 `priority` ，则这些参数将全都传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="16acb-272">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>  
      
      <span data-ttu-id="16acb-273">与此 `execAtPriority` 不同，回调函数 `asynchronousCallback` 返回的任何对象都将忽略 \ (且不通过 `execAsyncAtPriority` \) 返回。</span><span class="sxs-lookup"><span data-stu-id="16acb-273">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored \(and not returned via `execAsyncAtPriority`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-274">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-274">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="16acb-275">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="16acb-275">execAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-276">在给定的上下文优先级运行指定的回调函数。</span><span class="sxs-lookup"><span data-stu-id="16acb-276">Runs the specified callback function at the given contextual priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-277">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-277">Parameters</span></span>**  
      
      `synchronousCallback` <span data-ttu-id="16acb-278">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-278">[in]</span></span>  
      
      | <span data-ttu-id="16acb-279">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-279">Type</span></span> | <span data-ttu-id="16acb-280">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-280">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-281">函数</span><span class="sxs-lookup"><span data-stu-id="16acb-281">Function</span></span> | <span data-ttu-id="16acb-282">要在给定优先级优先级上同步运行的回调函数。</span><span class="sxs-lookup"><span data-stu-id="16acb-282">The callback function to run synchronously at the given priority contextual priority.</span></span>  |  
      
      `priority` <span data-ttu-id="16acb-283">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-283">[in]</span></span>  
      
      | <span data-ttu-id="16acb-284">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-284">Type</span></span> | <span data-ttu-id="16acb-285">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-285">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-286">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-286">DOMString</span></span> | <span data-ttu-id="16acb-287">运行回调函数时会设置当前上下文优先级值的指定 `synchronousCallback` 优先级值。</span><span class="sxs-lookup"><span data-stu-id="16acb-287">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span>  <span data-ttu-id="16acb-288">请 [参见 MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="16acb-288">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="16acb-289">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-289">[in]</span></span>  
      
      | <span data-ttu-id="16acb-290">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-290">Type</span></span> | <span data-ttu-id="16acb-291">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-291">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-292">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-292">Any</span></span> | <span data-ttu-id="16acb-293">传递到回调函数 `synchronousCallback` \ (作为参数 1 依此类的可选系列) 。</span><span class="sxs-lookup"><span data-stu-id="16acb-293">An optional series of arguments that are passed to the `synchronousCallback` callback function \(as parameters 1 and so on\).</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-294">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-294">Return value</span></span>**  
      
      | <span data-ttu-id="16acb-295">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-295">Type</span></span> | <span data-ttu-id="16acb-296">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-296">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-297">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-297">Any</span></span> | <span data-ttu-id="16acb-298">返回返回适用 `synchronousCallback` \ (的回调值) 。</span><span class="sxs-lookup"><span data-stu-id="16acb-298">Returns the return value of the `synchronousCallback` callback \(as applicable\).</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-299">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-299">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-300">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-300">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-301">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-301">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-302">提供 `synchronousCallback` 的回调方法是同步执行的。</span><span class="sxs-lookup"><span data-stu-id="16acb-302">The provided `synchronousCallback` callback method is execute synchronously.</span></span>  <span data-ttu-id="16acb-303">当前的上下文优先级在提供的回调 (的优先级参数) 更改为提供的回调函数的优先级参数值。</span><span class="sxs-lookup"><span data-stu-id="16acb-303">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span>  <span data-ttu-id="16acb-304">回调函数执行完成后，优先级将返回到调用前的之前的 `execAtPriority` 值。</span><span class="sxs-lookup"><span data-stu-id="16acb-304">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span>  <span data-ttu-id="16acb-305">返回值是 `execAtPriority` 作为 provided\) 的回调方法 \ (的返回。</span><span class="sxs-lookup"><span data-stu-id="16acb-305">The return value from `execAtPriority` is the return value of the callback method \(as provided\).</span></span>  
      
      <span data-ttu-id="16acb-306">回 `synchronousCallback` 调参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="16acb-306">The `synchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="16acb-307">如果在优先级参数之后提供了任何参数，则这些参数将传递到所提供的回调方法。</span><span class="sxs-lookup"><span data-stu-id="16acb-307">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span>  <span data-ttu-id="16acb-308">如果回调参数返回一个值，则此值也将成为返回 `execAtPriority` 值。</span><span class="sxs-lookup"><span data-stu-id="16acb-308">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-309">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-309">Example</span></span>**  
      
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

### <span data-ttu-id="16acb-310">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="16acb-310">getCurrentPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-311">返回当前上下文优先级。</span><span class="sxs-lookup"><span data-stu-id="16acb-311">Returns the current contextual priority.</span></span>  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-312">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-312">Parameters</span></span>**  
      
      <span data-ttu-id="16acb-313">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-313">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-314">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-314">Return value</span></span>**  
      
      | <span data-ttu-id="16acb-315">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-315">Type</span></span> | <span data-ttu-id="16acb-316">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-316">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-317">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-317">DOMString</span></span> | <span data-ttu-id="16acb-318">返回值是一个字符串， `MSApp.HIGH` 或 `MSApp.NORMAL` `MSApp.IDLE` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-318">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-319">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-319">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-320">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-320">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-321">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-321">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-322">此方法返回当前上下文优先级 \ (请参阅 [MSApp 常](#msapp-constants)量 \) ，可以通过此方法 `execAtPriority` 进行更改 `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-322">This method returns the current contextual priority \(see [MSApp Constants](#msapp-constants)\), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-323">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-323">Example</span></span>**  
      
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

### <span data-ttu-id="16acb-324">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="16acb-324">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="16acb-325">已弃用的同步 API。</span><span class="sxs-lookup"><span data-stu-id="16acb-325">Synchronous API that has been deprecated.</span></span>  <span data-ttu-id="16acb-326">有关 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-326">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span>  <span data-ttu-id="16acb-327">对于 Windows 8 和 8.1 应用，请参阅 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。</span><span class="sxs-lookup"><span data-stu-id="16acb-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <span data-ttu-id="16acb-328">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="16acb-328">getHtmlPrintDocumentSourceAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-329">返回要打印的源内容。</span><span class="sxs-lookup"><span data-stu-id="16acb-329">Returns the source content that is to be printed.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-330">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-330">Parameters</span></span>**  
      
      `htmlDoc` <span data-ttu-id="16acb-331">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-331">[in]</span></span>  
      
      | <span data-ttu-id="16acb-332">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-332">Type</span></span> | <span data-ttu-id="16acb-333">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-333">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-334">文档</span><span class="sxs-lookup"><span data-stu-id="16acb-334">Document</span></span> | <span data-ttu-id="16acb-335">要打印的 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="16acb-335">The HTML document to be printed.</span></span>  <span data-ttu-id="16acb-336">可以是根文档、iframe 中的文档、文档片段或 SVG 文档。</span><span class="sxs-lookup"><span data-stu-id="16acb-336">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span>  <span data-ttu-id="16acb-337">请注意，htmlDoc 必须是文档，而非元素。</span><span class="sxs-lookup"><span data-stu-id="16acb-337">Be aware that htmlDoc must be a document, not an element.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-338">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-338">Return value</span></span>**
      
      <span data-ttu-id="16acb-339">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-339">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-340">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-340">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-341">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-341">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-342">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-342">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-343">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-343">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-344">示例 1</span><span class="sxs-lookup"><span data-stu-id="16acb-344">Example 1</span></span>**  
      
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
      **<span data-ttu-id="16acb-345">示例 2</span><span class="sxs-lookup"><span data-stu-id="16acb-345">Example 2</span></span>**  
      
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

### <span data-ttu-id="16acb-346">getViewId</span><span class="sxs-lookup"><span data-stu-id="16acb-346">getViewId</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-347">支持多个窗口。</span><span class="sxs-lookup"><span data-stu-id="16acb-347">Support for multiple windows.</span></span>  
      
      > [!NOTE] 
      > <span data-ttu-id="16acb-348">在 Win8.1 JavaScript UWP 应用中，使用 MSApp DOM API 支持多个窗口，这些窗口现在已按现适用。</span><span class="sxs-lookup"><span data-stu-id="16acb-348">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span>  <span data-ttu-id="16acb-349">对于 Windows 10、使用 `window.open` 、 `window` 新版 `MSApp.getViewId` 和新应用。</span><span class="sxs-lookup"><span data-stu-id="16acb-349">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>  
      
      | <span data-ttu-id="16acb-350">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-350">Description</span></span> |<span data-ttu-id="16acb-351">Windows 10</span><span class="sxs-lookup"><span data-stu-id="16acb-351">Windows 10</span></span> | <span data-ttu-id="16acb-352">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="16acb-352">Windows 8.1</span></span> |  
      |:---- |:---- |:--- |  
      | <span data-ttu-id="16acb-353">创建新窗口</span><span class="sxs-lookup"><span data-stu-id="16acb-353">Create new window</span></span> | [<span data-ttu-id="16acb-354">window.open</span><span class="sxs-lookup"><span data-stu-id="16acb-354">window.open</span></span>](https://developer.mozilla.org/docs/Web/API/Window/open) | [<span data-ttu-id="16acb-355">MSApp.createNewView</span><span class="sxs-lookup"><span data-stu-id="16acb-355">MSApp.createNewView</span></span>](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |<span data-ttu-id="16acb-356">新窗口对象</span><span class="sxs-lookup"><span data-stu-id="16acb-356">New window object</span></span> | [<span data-ttu-id="16acb-357">窗口</span><span class="sxs-lookup"><span data-stu-id="16acb-357">window</span></span>](https://developer.mozilla.org/docs/Web/API/Window) |[<span data-ttu-id="16acb-358">MSAppView</span><span class="sxs-lookup"><span data-stu-id="16acb-358">MSAppView</span></span>](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-359">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-359">Parameters</span></span>**  
      
      `window`
      
      | <span data-ttu-id="16acb-360">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-360">Type</span></span> | <span data-ttu-id="16acb-361">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-361">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-362">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-362">DOMString</span></span> | <span data-ttu-id="16acb-363">代表包含 DOM 文档窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-363">An object representing a window containing a DOM document.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-364">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-364">Return value</span></span>**  
      
      `viewId`
      
      | <span data-ttu-id="16acb-365">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-365">Type</span></span> | <span data-ttu-id="16acb-366">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-366">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-367">数字</span><span class="sxs-lookup"><span data-stu-id="16acb-367">Number</span></span> | <span data-ttu-id="16acb-368">可以与各种 [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 一起使用。</span><span class="sxs-lookup"><span data-stu-id="16acb-368">Can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-369">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-369">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-370">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-370">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-371">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-371">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-372">使用 [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) [和 window](https://developer.mozilla.org/docs/Web/API/Window) 来创建新窗口，然后若要与 WinRT API 交互，请添加 `MSApp.getViewId` API。</span><span class="sxs-lookup"><span data-stu-id="16acb-372">Use [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) and [window](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span>  <span data-ttu-id="16acb-373">它将对象作为参数返回一个数字，并返回一个数字用于 `window` `viewId` [各种 Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API。</span><span class="sxs-lookup"><span data-stu-id="16acb-373">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  
      
      *   <span data-ttu-id="16acb-374">延迟可见性</span><span class="sxs-lookup"><span data-stu-id="16acb-374">Delaying Visibility</span></span>  
          
          <span data-ttu-id="16acb-375">通常情况下，WinRT 中的视图开始隐藏，而最终开发人员使用一些像来完全准备好视图 `TryShowAsStandaloneAsync` 这样的视图。</span><span class="sxs-lookup"><span data-stu-id="16acb-375">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span>  <span data-ttu-id="16acb-376">在 Web 世界中，立即显示一个窗口，最终用户就可以在加载和呈现内容时 `window.open` 观看。</span><span class="sxs-lookup"><span data-stu-id="16acb-376">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span>  <span data-ttu-id="16acb-377">让新窗口像 WinRT 中的视图一样，而不会立即显示，我们添加了一个 `window.open` 选项。</span><span class="sxs-lookup"><span data-stu-id="16acb-377">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span>  <span data-ttu-id="16acb-378">例如：</span><span class="sxs-lookup"><span data-stu-id="16acb-378">For example:</span></span>  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   <span data-ttu-id="16acb-379">主要窗口差别</span><span class="sxs-lookup"><span data-stu-id="16acb-379">Primary Window Differences</span></span>  
          
          <span data-ttu-id="16acb-380">操作系统最初打开的主要窗口的操作方式与其打开的辅助窗口的行为不同：</span><span class="sxs-lookup"><span data-stu-id="16acb-380">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span>  
          
          | <span data-ttu-id="16acb-381">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-381">Description</span></span> | <span data-ttu-id="16acb-382">主要</span><span class="sxs-lookup"><span data-stu-id="16acb-382">Primary</span></span> | <span data-ttu-id="16acb-383">辅助边框</span><span class="sxs-lookup"><span data-stu-id="16acb-383">Secondary</span></span> |  
          |:---- |:--- |:--- |  
          | <span data-ttu-id="16acb-384">window.open</span><span class="sxs-lookup"><span data-stu-id="16acb-384">window.open</span></span> | <span data-ttu-id="16acb-385">允许</span><span class="sxs-lookup"><span data-stu-id="16acb-385">Allowed</span></span> | <span data-ttu-id="16acb-386">不允许</span><span class="sxs-lookup"><span data-stu-id="16acb-386">Disallowed</span></span> |  
          | <span data-ttu-id="16acb-387">window.close</span><span class="sxs-lookup"><span data-stu-id="16acb-387">window.close</span></span> | <span data-ttu-id="16acb-388">关闭应用</span><span class="sxs-lookup"><span data-stu-id="16acb-388">Close app</span></span> | <span data-ttu-id="16acb-389">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="16acb-389">Close window</span></span> |  
          | <span data-ttu-id="16acb-390">导航限制</span><span class="sxs-lookup"><span data-stu-id="16acb-390">Navigation restrictions</span></span> | <span data-ttu-id="16acb-391">仅 ACUR</span><span class="sxs-lookup"><span data-stu-id="16acb-391">ACUR only</span></span> | <span data-ttu-id="16acb-392">无限制</span><span class="sxs-lookup"><span data-stu-id="16acb-392">No restrictions</span></span> |  
          
          <span data-ttu-id="16acb-393">此项限制不允许打开辅助窗口，这可能会在以后根据反馈而 [更改](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。</span><span class="sxs-lookup"><span data-stu-id="16acb-393">The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).</span></span>  
      
      *   <span data-ttu-id="16acb-394">相同 Origin Communication 限制</span><span class="sxs-lookup"><span data-stu-id="16acb-394">Same Origin Communication Restrictions</span></span>  
          
          <span data-ttu-id="16acb-395">一个很难的技术问题，阻止正确支持同步、同一原点、跨窗口、脚本调用。</span><span class="sxs-lookup"><span data-stu-id="16acb-395">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span>  <span data-ttu-id="16acb-396">当您打开一个相同的原始窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。</span><span class="sxs-lookup"><span data-stu-id="16acb-396">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span>  `postMessage` <span data-ttu-id="16acb-397">调用工作正常工作，是可能实现此操作的推荐方法。</span><span class="sxs-lookup"><span data-stu-id="16acb-397">calls work just fine and is the recommended way to do things if possible.</span></span>  <span data-ttu-id="16acb-398">正在努力改进此问题。</span><span class="sxs-lookup"><span data-stu-id="16acb-398">Work to improve this issue is in progress.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-399">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-399">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <span data-ttu-id="16acb-400">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="16acb-400">isTaskScheduledAtPriorityOrHigher</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-401">返回一个布尔值，指示已给定优先级级别是否有挂起的工作。</span><span class="sxs-lookup"><span data-stu-id="16acb-401">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-402">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-402">Parameters</span></span>**  
      
      `priority` <span data-ttu-id="16acb-403">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-403">[in]</span></span>
      
      | <span data-ttu-id="16acb-404">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-404">Type</span></span> | <span data-ttu-id="16acb-405">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-405">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-406">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-406">DOMString</span></span> | <span data-ttu-id="16acb-407">优先级值 \ ([请参阅"MSApp 常](#msapp-constants)量 /) 从而指定任何未完成的已完成工作的优先级及以上查询。</span><span class="sxs-lookup"><span data-stu-id="16acb-407">A priority value \(see [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-408">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-408">Return value</span></span>**  
      
      | <span data-ttu-id="16acb-409">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-409">Type</span></span> | <span data-ttu-id="16acb-410">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-410">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-411">布尔</span><span class="sxs-lookup"><span data-stu-id="16acb-411">Boolean</span></span> | <span data-ttu-id="16acb-412">如果 `true` 具有以上优先级或以上内容的任何已批量化工作， `false` 则返回。</span><span class="sxs-lookup"><span data-stu-id="16acb-412">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-413">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-413">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-414">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-414">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-415">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-415">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-416">此方法针对 JavaScript 代码提供了一种方式来确定与调用 JavaScript 代码可以在后面的 intent 那些优先级级别 （ (或更高版本\) 上有挂起的工作。然后，调用 JavaScript 代码可决定将优先级工作分配给 `isTaskScheduledAtPriorityOrHigher` 更高的工作。</span><span class="sxs-lookup"><span data-stu-id="16acb-416">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels \(or above\) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-417">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-417">Example</span></span>**  
      
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

### <span data-ttu-id="16acb-418">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="16acb-418">pageHandlesAllApplicationActivations</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-419">在每个激活 (的事件 \ (（例如，单击通知或已固定的磁贴\) ）之前，避免更新开始路径的) 页面重新加载) 。</span><span class="sxs-lookup"><span data-stu-id="16acb-419">Used to avoid a refresh of the start path (page reload) before every activate event \(such as clicking a notification or a pinned tile\).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-420">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-420">Parameters</span></span>**  
      
      | <span data-ttu-id="16acb-421">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-421">Type</span></span> | <span data-ttu-id="16acb-422">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-422">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-423">布尔</span><span class="sxs-lookup"><span data-stu-id="16acb-423">Boolean</span></span> | <span data-ttu-id="16acb-424">用 `MSApp.pageHandlesAllApplicationActivations(true)` 来始终刷新开始路径 (页面重新加载) 而直接跳转触发 `WebUIApplication` 已激活事件。</span><span class="sxs-lookup"><span data-stu-id="16acb-424">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span>  <span data-ttu-id="16acb-425">需要所有页面单独处理激活事件。</span><span class="sxs-lookup"><span data-stu-id="16acb-425">Requires that all pages handle activation events separately.</span></span>  <span data-ttu-id="16acb-426">通过将此方法定义为， `true` 单击已激活的事件 \ (（如 notification\) ）将不会触发重新加载，需要单页面应用需要防止页面重新加载。</span><span class="sxs-lookup"><span data-stu-id="16acb-426">By defining this method as `true`, clicking an activated event \(like a notification\) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-427">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-427">Return value</span></span>**
      
      <span data-ttu-id="16acb-428">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-428">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-429">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-429">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-430">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-430">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-431">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-431">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-432">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-432">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-433">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-433">Example</span></span>**  
      
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

### <span data-ttu-id="16acb-434">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="16acb-434">suppressSubdownloadCredentialPrompts</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-435">控制在下载资源期间应用是否会为其隐藏可能的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="16acb-435">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-436">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-436">Parameters</span></span>**  
     
      `suppress` <span data-ttu-id="16acb-437">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-437">[in]</span></span>
      
      | <span data-ttu-id="16acb-438">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-438">Type</span></span> | <span data-ttu-id="16acb-439">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-439">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-440">布尔</span><span class="sxs-lookup"><span data-stu-id="16acb-440">Boolean</span></span> | <span data-ttu-id="16acb-441">有效的值值不能显示可能的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="16acb-441">A value of true suppresses potential authentication prompts.</span></span>  <span data-ttu-id="16acb-442">假如未阻止用户发出的任何潜在身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="16acb-442">A value of false does not suppress any potential authentication prompts from the user.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-443">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-443">Return value</span></span>**  
      
      <span data-ttu-id="16acb-444">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-444">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-445">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-445">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-446">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-446">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-447">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-447">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-448">`suppressSubdownloadCredentialPrompts`此方法控制应用是否在下载资源期间为应用停用可能的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="16acb-448">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span>  <span data-ttu-id="16acb-449">默认行为是不隐藏凭据提示。</span><span class="sxs-lookup"><span data-stu-id="16acb-449">The default behavior is to not suppress credential prompts.</span></span>  
      
      `suppressSubdownloadCredentialPrompts` <span data-ttu-id="16acb-450">应用适用于应用，它可能会加载需要身份验证的过多资源（如邮件应用 \ (），邮件应用可能包含包含大量图像（每个图像都需要身份验证\) ）的新闻稿。</span><span class="sxs-lookup"><span data-stu-id="16acb-450">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app \(which could contain a newsletter containing a number of images where each image requires authentication\).</span></span>  
      
      <span data-ttu-id="16acb-451">当提供凭据提示时，在访问要求身份验证的资源时，不会显示用于身份验证服务器的对话框，并且不会下载该资源。</span><span class="sxs-lookup"><span data-stu-id="16acb-451">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span>  <span data-ttu-id="16acb-452">请 `suppressSubdownloadCredentialPrompts` 注意，不会影响代理身份验证或客户端认证请求对话框等其他可能提示，也不会影响 XHR。</span><span class="sxs-lookup"><span data-stu-id="16acb-452">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>  
      
      <span data-ttu-id="16acb-453">请注意， `suppressSubdownloadCredentialPrompts` 会影响应用程序中的所有内容，包括在元素中托管 `webview` 的内容。</span><span class="sxs-lookup"><span data-stu-id="16acb-453">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>  
      
      > [!IMPORTANT]
      > <span data-ttu-id="16acb-454">已统一提示决定。</span><span class="sxs-lookup"><span data-stu-id="16acb-454">Credential prompt decisions are cached.</span></span>  <span data-ttu-id="16acb-455">因此，当停用凭据提示时，即时取消凭据提示将立即生效，因此，在隐藏凭据提示后，可能需要重新加载凭据提示，使其生效。</span><span class="sxs-lookup"><span data-stu-id="16acb-455">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-456">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-456">Example</span></span>**  
      
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

### <span data-ttu-id="16acb-457">terminateApp</span><span class="sxs-lookup"><span data-stu-id="16acb-457">terminateApp</span></span>  


:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-458">终止当前应用程序并生成失败报告。</span><span class="sxs-lookup"><span data-stu-id="16acb-458">Terminates the current application and generates a failure report.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-459">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-459">Parameters</span></span>**  
      
      `error` <span data-ttu-id="16acb-460">[in]</span><span class="sxs-lookup"><span data-stu-id="16acb-460">[in]</span></span>
      
      | <span data-ttu-id="16acb-461">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-461">Type</span></span> | <span data-ttu-id="16acb-462">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-462">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-463">错误</span><span class="sxs-lookup"><span data-stu-id="16acb-463">Error</span></span> | <span data-ttu-id="16acb-464">`Error`一个可用于描述触发终止的错误的对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-464">An `Error` object that you can use to describe the error that triggered the termination.</span></span>  <span data-ttu-id="16acb-465">`Error`该对象必须包含数字、描述和堆叠属性;如果对象不包含这些属性，则不会生成失败报告。</span><span class="sxs-lookup"><span data-stu-id="16acb-465">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-466">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-466">Return value</span></span>**
      
      <span data-ttu-id="16acb-467">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-467">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-468">异常</span><span class="sxs-lookup"><span data-stu-id="16acb-468">Exceptions</span></span>**  
      
      <span data-ttu-id="16acb-469">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-469">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-470">备注</span><span class="sxs-lookup"><span data-stu-id="16acb-470">Remarks</span></span>**  
      
      <span data-ttu-id="16acb-471">如果该问题报告的 `terminateApp` 问题成为你的应用的最高 5 个问题之一，它将显示在该应用的"质量"页上。</span><span class="sxs-lookup"><span data-stu-id="16acb-471">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-472">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-472">Example</span></span>**  
      
      <span data-ttu-id="16acb-473">遇到 `terminateApp` 异常时此示例调用。</span><span class="sxs-lookup"><span data-stu-id="16acb-473">This example calls `terminateApp` when an exception is encountered.</span></span>  <span data-ttu-id="16acb-474">它使用 `Error` 你关闭异常时提供的对象。</span><span class="sxs-lookup"><span data-stu-id="16acb-474">It uses the `Error` object provided when you catch an exception.</span></span>  
      
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

### <span data-ttu-id="16acb-475">MSApp 常量</span><span class="sxs-lookup"><span data-stu-id="16acb-475">MSApp Constants</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-476">允许关联、、和 `execAsyncAtPriority` `execAtPriority` `getCurrentPriority` `isTaskScheduldAtPriorityOrHigher`</span><span class="sxs-lookup"><span data-stu-id="16acb-476">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="16acb-477">当前</span><span class="sxs-lookup"><span data-stu-id="16acb-477">Current</span></span>  
      
      `current`  
      
      | <span data-ttu-id="16acb-478">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-478">Type</span></span> | <span data-ttu-id="16acb-479">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-479">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-480">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-480">DOMString</span></span> | <span data-ttu-id="16acb-481">与适当方法 \ (See also section\) 结合使用时，该方法将在执行所请求的操作时使用当前上 `current` 下文优先级。</span><span class="sxs-lookup"><span data-stu-id="16acb-481">When `current` is used with the appropriate method \(See also section\), the method will use the current contextual priority when executing the requested operation.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="16acb-482">高 </span><span class="sxs-lookup"><span data-stu-id="16acb-482">High</span></span>  
      
      `high`  
      
      | <span data-ttu-id="16acb-483">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-483">Type</span></span> | <span data-ttu-id="16acb-484">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-484">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-485">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-485">DOMString</span></span> | <span data-ttu-id="16acb-486">与 `high` 相应方法 \ (请参阅另一节\) 时，执行请求的操作时将使用高于正常优先级，并将在任何现有正常优先级工作之前调度操作。</span><span class="sxs-lookup"><span data-stu-id="16acb-486">When `high` is used with the appropriate method \(See also section\), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="16acb-487">Idle</span><span class="sxs-lookup"><span data-stu-id="16acb-487">Idle</span></span>  
      
      `idle`  
      
      | <span data-ttu-id="16acb-488">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-488">Type</span></span> | <span data-ttu-id="16acb-489">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-489">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-490">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-490">DOMString</span></span> | <span data-ttu-id="16acb-491">与 `ideal` 适当方法 \ (See a- section\See a\ see a\ ) 当执行请求的操作时，该方法将使用低于正常优先级，并将在任何现有正常优先级工作后分发操作。</span><span class="sxs-lookup"><span data-stu-id="16acb-491">When `ideal` is used with the appropriate method \(See also section\), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="16acb-492">正常</span><span class="sxs-lookup"><span data-stu-id="16acb-492">Normal</span></span>  
      
      `normal`  
      
      | <span data-ttu-id="16acb-493">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-493">Type</span></span> | <span data-ttu-id="16acb-494">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-494">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-495">DOMString</span><span class="sxs-lookup"><span data-stu-id="16acb-495">DOMString</span></span> | <span data-ttu-id="16acb-496">与 `normal` 适当的方法一起使用 (请参阅"另请参阅) "时，此方法将在执行请求的操作时使用正常的现有优先级。</span><span class="sxs-lookup"><span data-stu-id="16acb-496">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-497">示例</span><span class="sxs-lookup"><span data-stu-id="16acb-497">Example</span></span>**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-498">要求</span><span class="sxs-lookup"><span data-stu-id="16acb-498">Requirements</span></span>**  
      
      | <span data-ttu-id="16acb-499">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-499">Type</span></span> | <span data-ttu-id="16acb-500">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-500">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-501">IDL</span><span class="sxs-lookup"><span data-stu-id="16acb-501">IDL</span></span> | <span data-ttu-id="16acb-502">Mshtml.idl</span><span class="sxs-lookup"><span data-stu-id="16acb-502">Mshtml.idl</span></span> |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="16acb-503">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="16acb-503">MSAppAsyncOperation</span></span>  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <span data-ttu-id="16acb-504">start</span><span class="sxs-lookup"><span data-stu-id="16acb-504">start</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="16acb-505">开始 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-505">Starts the `MSAppAsyncOperation`.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="16acb-506">参数</span><span class="sxs-lookup"><span data-stu-id="16acb-506">Parameters</span></span>**  
      
      <span data-ttu-id="16acb-507">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-507">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="16acb-508">返回值</span><span class="sxs-lookup"><span data-stu-id="16acb-508">Return value</span></span>**
      
      <span data-ttu-id="16acb-509">无。</span><span class="sxs-lookup"><span data-stu-id="16acb-509">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **<span data-ttu-id="16acb-510">属性</span><span class="sxs-lookup"><span data-stu-id="16acb-510">Properties</span></span>**  
      
      `error` <span data-ttu-id="16acb-511">属性</span><span class="sxs-lookup"><span data-stu-id="16acb-511">property</span></span>  
      
      | <span data-ttu-id="16acb-512">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-512">Type</span></span> | <span data-ttu-id="16acb-513">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-513">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-514">DOMError</span><span class="sxs-lookup"><span data-stu-id="16acb-514">DOMError</span></span> | <span data-ttu-id="16acb-515">表示一个错误 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-515">Represents an error in `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` <span data-ttu-id="16acb-516">属性</span><span class="sxs-lookup"><span data-stu-id="16acb-516">property</span></span>  
      
      | <span data-ttu-id="16acb-517">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-517">Type</span></span> | <span data-ttu-id="16acb-518">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-518">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-519">EventHandler</span><span class="sxs-lookup"><span data-stu-id="16acb-519">EventHandler</span></span> | <span data-ttu-id="16acb-520">用于在完成时设置事件处理程序的属性 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-520">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` <span data-ttu-id="16acb-521">属性</span><span class="sxs-lookup"><span data-stu-id="16acb-521">property</span></span>  
      
      | <span data-ttu-id="16acb-522">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-522">Type</span></span> | <span data-ttu-id="16acb-523">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-523">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-524">EventHandler</span><span class="sxs-lookup"><span data-stu-id="16acb-524">EventHandler</span></span> | <span data-ttu-id="16acb-525">用于在错误的过程中设置事件处理程序的属性 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-525">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` <span data-ttu-id="16acb-526">属性</span><span class="sxs-lookup"><span data-stu-id="16acb-526">property</span></span>  
      
      | <span data-ttu-id="16acb-527">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-527">Type</span></span> | <span data-ttu-id="16acb-528">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-528">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-529">数字</span><span class="sxs-lookup"><span data-stu-id="16acb-529">Number</span></span> | <span data-ttu-id="16acb-530">表示使用 JavaScript 的 Windows 应用中异步操作的状态。</span><span class="sxs-lookup"><span data-stu-id="16acb-530">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span>  <span data-ttu-id="16acb-531">值包括 `Started[0]` `Completed[1]` ：、 `Error[2]`</span><span class="sxs-lookup"><span data-stu-id="16acb-531">Values include: `Started[0]`, `Completed[1]`, `Error[2]`.</span></span>  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` <span data-ttu-id="16acb-532">属性</span><span class="sxs-lookup"><span data-stu-id="16acb-532">property</span></span>  
      
      | <span data-ttu-id="16acb-533">类型</span><span class="sxs-lookup"><span data-stu-id="16acb-533">Type</span></span> | <span data-ttu-id="16acb-534">描述</span><span class="sxs-lookup"><span data-stu-id="16acb-534">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="16acb-535">Any</span><span class="sxs-lookup"><span data-stu-id="16acb-535">Any</span></span> |<span data-ttu-id="16acb-536">表示结果 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="16acb-536">Represents the result of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
