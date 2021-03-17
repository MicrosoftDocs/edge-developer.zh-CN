---
title: MSApp API 参考
description: 提供可帮助您创建 Blob 和 MSStream 对象的帮助程序函数。  MSApp 对象和成员支持使用 JavaScript 的 Windows 应用。
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
keywords: MSapp， PWA， 文件上传， 博客， MSStream， windows 10 应用， uwp， edge
ms.date: 03/16/2021
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0607929971b1dd2956571304230f69f756497e32
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439722"
---
# <a name="msapp"></a><span data-ttu-id="750ec-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="750ec-105">MSApp</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="750ec-106">MSApp 对象及其成员仅支持使用 JavaScript \ (包括访问 Windows API 功能\) 的 Windows 应用。</span><span class="sxs-lookup"><span data-stu-id="750ec-106">The MSApp object and its members are supported only for Windows apps using JavaScript \(including PWAs accessing Windows API features\).</span></span>  <span data-ttu-id="750ec-107">MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中 HTML 文档的本地上下文中;否则，该对象不存在 (因此，该对象的方法和属性均) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>  

<span data-ttu-id="750ec-108">它提供可帮助您创建 [Blob](https://developer.mozilla.org/docs/Web/API/Blob) 和 [MSStream 对象的帮助程序](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) 函数。</span><span class="sxs-lookup"><span data-stu-id="750ec-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="750ec-109">方法</span><span class="sxs-lookup"><span data-stu-id="750ec-109">Methods</span></span>](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="750ec-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync)、 [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)、 [createDataPackage](#createdatapackage)、 [createDataPackageFromSelection](#createdatapackagefromselection)、 [createFileFromStorageFile](#createfilefromstoragefile)、 [createStreamFromInputStream](#createstreamfrominputstream)、 [execAsyncAtPriority](#execasyncatpriority)、 [execAtPriority](#execatpriority)、 [getCurrentPriority](#getcurrentpriority)、 [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)、[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)、 [getViewId](#getviewid)、 [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher)、 [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations)、 [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts)、 [terminateApp](#terminateapp).</span><span class="sxs-lookup"><span data-stu-id="750ec-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="750ec-111">常量</span><span class="sxs-lookup"><span data-stu-id="750ec-111">Constants</span></span>](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="750ec-112">[current](#current)、 [high](#high)、 [idle](#idle)、 [normal](#normal)。</span><span class="sxs-lookup"><span data-stu-id="750ec-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="750ec-113">MSAppAsyncOperation 接口</span><span class="sxs-lookup"><span data-stu-id="750ec-113">MSAppAsyncOperation interface</span></span>](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [<span data-ttu-id="750ec-114">start</span><span class="sxs-lookup"><span data-stu-id="750ec-114">start</span></span>](#start)  
   :::column-end:::
:::row-end:::  

## <a name="msapp-methods"></a><span data-ttu-id="750ec-115">MSApp 方法</span><span class="sxs-lookup"><span data-stu-id="750ec-115">MSApp methods</span></span>  

### <a name="cleartemporarywebdataasync"></a><span data-ttu-id="750ec-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="750ec-116">clearTemporaryWebDataAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-117">清除应用或 [WebView](../../hosting/webview/index.md)的缓存和索引DB 数据。</span><span class="sxs-lookup"><span data-stu-id="750ec-117">Clears cache and indexedDB data for the app or [WebView](../../hosting/webview/index.md).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-118">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-118">Parameters</span></span>**  
      
      <span data-ttu-id="750ec-119">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="750ec-119">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-120">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-120">Return value</span></span>**  
      
      <span data-ttu-id="750ec-121">类型 [：IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="750ec-121">Type: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span></span>  
      
      <span data-ttu-id="750ec-122">表示异步操作。</span><span class="sxs-lookup"><span data-stu-id="750ec-122">Represents an asynchronous action.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-123">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-123">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-124">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-124">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-125">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-125">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-126">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-126">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-127">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-127">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createblobfromrandomaccessstream"></a><span data-ttu-id="750ec-128">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="750ec-128">createBlobFromRandomAccessStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-129">从[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)对象创建 Blob。 [](https://developer.mozilla.org/docs/Web/API/Blob)</span><span class="sxs-lookup"><span data-stu-id="750ec-129">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span>  <span data-ttu-id="750ec-130">在处理应用中的对象时，应使用此方法，以便从流创建基于 `IRandomAccessStream` W3C 的对象。</span><span class="sxs-lookup"><span data-stu-id="750ec-130">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span>  <span data-ttu-id="750ec-131">创建 blob 后，即可与 [FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API](https://developer.mozilla.org/docs/Web/API/URL)和 [XMLHttpRequest 一起使用](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。</span><span class="sxs-lookup"><span data-stu-id="750ec-131">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-132">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-132">Parameters</span></span>**  
      
      `type` <span data-ttu-id="750ec-133">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-133">[in]</span></span>  
      
      | <span data-ttu-id="750ec-134">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-134">Type</span></span> | <span data-ttu-id="750ec-135">说明</span><span class="sxs-lookup"><span data-stu-id="750ec-135">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-136">字符串</span><span class="sxs-lookup"><span data-stu-id="750ec-136">String</span></span> | <span data-ttu-id="750ec-137">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="750ec-137">Content type of the data.</span></span>  <span data-ttu-id="750ec-138">此字符串的格式应为 RFC 2616 的第 3.7 节中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="750ec-138">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  |  
      
      `stream` <span data-ttu-id="750ec-139">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-139">[in]</span></span>  
      
      | <span data-ttu-id="750ec-140">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-140">Type</span></span> | <span data-ttu-id="750ec-141">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-141">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-142">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-142">Any</span></span> | <span data-ttu-id="750ec-143">要存储在 Blob 中的[IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)</span><span class="sxs-lookup"><span data-stu-id="750ec-143">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-144">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-144">Return value</span></span>**  
      
      | <span data-ttu-id="750ec-145">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-145">Type</span></span> | <span data-ttu-id="750ec-146">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-146">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-147">Blob</span><span class="sxs-lookup"><span data-stu-id="750ec-147">Blob</span></span> | <span data-ttu-id="750ec-148">包含流的新 blob 对象。</span><span class="sxs-lookup"><span data-stu-id="750ec-148">New blob object that contains the stream.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-149">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-149">Exceptions</span></span>**  
      
      | <span data-ttu-id="750ec-150">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-150">Exception</span></span> | <span data-ttu-id="750ec-151">条件</span><span class="sxs-lookup"><span data-stu-id="750ec-151">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-152">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="750ec-152">TypeMismatchError</span></span> | <span data-ttu-id="750ec-153">节点类型与预期的参数类型不兼容。</span><span class="sxs-lookup"><span data-stu-id="750ec-153">The node type is incompatible with the expected parameter type.</span></span>  <span data-ttu-id="750ec-154">对于早于 Internet Explorer 10 的版本，TYPE_MISMATCH_ERR返回。</span><span class="sxs-lookup"><span data-stu-id="750ec-154">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-155">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-155">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-156">通过 window 对象的 MSApp 命名空间从 Windows 运行时类型创建 Blob。</span><span class="sxs-lookup"><span data-stu-id="750ec-156">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span>  <span data-ttu-id="750ec-157">此方法将创建一个 blob，该 blob 实质上是提供给 [它的 RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 对象的光包装。</span><span class="sxs-lookup"><span data-stu-id="750ec-157">This method will create a blob that is essentially a light wrapper over the [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span>  <span data-ttu-id="750ec-158">blob 拥有此流的生存期，该流将在 blob 销毁时关闭。</span><span class="sxs-lookup"><span data-stu-id="750ec-158">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-159">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-159">Example</span></span>**  
      
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

### <a name="createdatapackage"></a><span data-ttu-id="750ec-160">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="750ec-160">createDataPackage</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-161">将用户或应用程序的指定范围转换为可共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="750ec-161">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-162">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-162">Parameters</span></span>**  
      
      `object` <span data-ttu-id="750ec-163">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-163">[in]</span></span>  
      
      | <span data-ttu-id="750ec-164">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-164">Type</span></span> | <span data-ttu-id="750ec-165">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-165">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-166">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-166">Any</span></span> | <span data-ttu-id="750ec-167">可以从选择对象创建此范围，例如： `window.selection.getRangeAt(0)` 或手动创建。</span><span class="sxs-lookup"><span data-stu-id="750ec-167">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-168">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-168">Return value</span></span>**  
      
      | <span data-ttu-id="750ec-169">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-169">Type</span></span> | <span data-ttu-id="750ec-170">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-170">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-171">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-171">Any</span></span> | <span data-ttu-id="750ec-172">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="750ec-172">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-173">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-173">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-174">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-174">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-175">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-175">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-176">此方法仅支持文档 [对象模型 (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range)，而不是 [TextRange](/uwp/api/windows.ui.xaml.documents.textrange)。</span><span class="sxs-lookup"><span data-stu-id="750ec-176">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span>  <span data-ttu-id="750ec-177">指定区域返回的数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="750ec-177">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>  
      
      <span data-ttu-id="750ec-178">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="750ec-178">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-179">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-179">Example</span></span>**  
      
      <span data-ttu-id="750ec-180">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-180">None.</span></span>  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createdatapackagefromselection"></a><span data-ttu-id="750ec-181">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="750ec-181">createDataPackageFromSelection</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-182">将用户或应用程序的选择转换为可共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="750ec-182">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-183">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-183">Parameters</span></span>**  
      
      <span data-ttu-id="750ec-184">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="750ec-184">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-185">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-185">Return value</span></span>**  
      
      | <span data-ttu-id="750ec-186">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-186">Type</span></span> | <span data-ttu-id="750ec-187">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-187">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-188">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-188">Any</span></span> | <span data-ttu-id="750ec-189">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="750ec-189">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-190">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-190">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-191">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-191">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-192">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-192">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-193">所选内容返回的数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="750ec-193">The returned data package for the selection contains HTML markup in clipboard format.</span></span>  <span data-ttu-id="750ec-194">如果应用程序 UI 中的任何位置没有用户选择，则 `createDataPackageFromSelection` 返回 `null` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-194">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns `null`.</span></span>  
      
      <span data-ttu-id="750ec-195">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="750ec-195">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-196">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-196">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <a name="createfilefromstoragefile"></a><span data-ttu-id="750ec-197">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="750ec-197">createFileFromStorageFile</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-198">将 [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) 转换为标准 W3C [File](https://developer.mozilla.org/docs/Web/API/File) 对象。</span><span class="sxs-lookup"><span data-stu-id="750ec-198">Converts a [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) to a standard W3C [File](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-199">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-199">Parameters</span></span>**  
      
      `storageFile` <span data-ttu-id="750ec-200">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-200">[in]</span></span>
      
      | <span data-ttu-id="750ec-201">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-201">Type</span></span> | <span data-ttu-id="750ec-202">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-202">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-203">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-203">Any</span></span> | <span data-ttu-id="750ec-204">包含存储文件。</span><span class="sxs-lookup"><span data-stu-id="750ec-204">Contains the storage file.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-205">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-205">Return value</span></span>**
      
      <span data-ttu-id="750ec-206">无</span><span class="sxs-lookup"><span data-stu-id="750ec-206">None</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-207">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-207">Exceptions</span></span>**  
      
      | <span data-ttu-id="750ec-208">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-208">Exception</span></span> | <span data-ttu-id="750ec-209">条件</span><span class="sxs-lookup"><span data-stu-id="750ec-209">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-210">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="750ec-210">TypeMismatchError</span></span> | <span data-ttu-id="750ec-211">指定的 W3C 文件引用无效。</span><span class="sxs-lookup"><span data-stu-id="750ec-211">The specified W3C file reference is invalid.</span></span>  <span data-ttu-id="750ec-212">对于早于 Internet Explorer 10， `TYPE_MISMATCH_ERR` 将返回 。</span><span class="sxs-lookup"><span data-stu-id="750ec-212">For versions earlier than Internet Explorer 10, `TYPE_MISMATCH_ERR` is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-213">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-213">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-214">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-214">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-215">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-215">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="createstreamfrominputstream"></a><span data-ttu-id="750ec-216">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="750ec-216">createStreamFromInputStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-217">从 InputStream 创建[MSStream。](https://msdn.microsoft.com/library/hh772327) [](https://msdn.microsoft.com/library/hh772328)</span><span class="sxs-lookup"><span data-stu-id="750ec-217">Creates an [MSStream](https://msdn.microsoft.com/library/hh772328) from an [InputStream](https://msdn.microsoft.com/library/hh772327).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-218">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-218">Parameters</span></span>**  
      
      `type` <span data-ttu-id="750ec-219">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-219">[in]</span></span>
      
      | <span data-ttu-id="750ec-220">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-220">Type</span></span> | <span data-ttu-id="750ec-221">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-221">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-222">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-222">DOMString</span></span> | <span data-ttu-id="750ec-223">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="750ec-223">Content type of the data.</span></span>  <span data-ttu-id="750ec-224">此字符串的格式应为 RFC 2616 的第 3.7 节中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="750ec-224">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  <span data-ttu-id="750ec-225">\ ([请参阅 MIME 类型，] (https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) 如 `text/plain` `text/html` 、、 、 、 等 `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` \) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-225">\([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) such as `text/plain`, `text/html`, `image/jpeg`, `image/png`, `audio/mpeg`, `audio/ogg`, `audio/*`, `video/mp4`, and so on\).</span></span>  
      
      `inputStream` <span data-ttu-id="750ec-226">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-226">[in]</span></span>
      
      | <span data-ttu-id="750ec-227">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-227">Type</span></span> | <span data-ttu-id="750ec-228">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-228">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-229">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-229">Any</span></span> | <span data-ttu-id="750ec-230">要[存储在 中的 IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`</span><span class="sxs-lookup"><span data-stu-id="750ec-230">The [IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-231">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-231">Return value</span></span>**
      
      <span data-ttu-id="750ec-232">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-232">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-233">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-233">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-234">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-234">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-235">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-235">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-236">此方法采用内容类型和 `IInputStream` 引用。</span><span class="sxs-lookup"><span data-stu-id="750ec-236">This method takes a content-type, and the `IInputStream` reference.</span></span>  <span data-ttu-id="750ec-237">然后，该方法验证传入的流引用是一个类型实例，如果没有， `IInputStream` 则引发 `DOMException TYPE_MISMATCH_ERR` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-237">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span>  <span data-ttu-id="750ec-238">如果未发生错误， `createStreamFromInputStream` 则从它的输入 `MSStream` \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-238">If no error occurs, `createStreamFromInputStream` creates an `MSStream` \(from its inputs\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-239">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-239">Example</span></span>**  
      
      <span data-ttu-id="750ec-240">`IInputStream`可用于创建 `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-240">An `IInputStream` can be used to create an `MSStream`.</span></span>  <span data-ttu-id="750ec-241">与本质上一次使用的对象一样，第一次由 image 元素解析时将吊销创建的所有 `MSStreams` `URL.createObjectURL` URL。</span><span class="sxs-lookup"><span data-stu-id="750ec-241">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span>  <span data-ttu-id="750ec-242">此外，使用流后，对此对象的第二个 URL 的请求将失败。</span><span class="sxs-lookup"><span data-stu-id="750ec-242">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>  
      
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

### <a name="execasyncatpriority"></a><span data-ttu-id="750ec-243">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="750ec-243">execAsyncAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-244">根据给定的优先级安排在以后执行的回调。</span><span class="sxs-lookup"><span data-stu-id="750ec-244">Schedules a callback to be executed at a later time according to the given priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-245">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-245">Parameters</span></span>**  
      
      `asynchronousCallback` <span data-ttu-id="750ec-246">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-246">[in]</span></span>
      
      | <span data-ttu-id="750ec-247">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-247">Type</span></span> | <span data-ttu-id="750ec-248">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-248">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-249">函数</span><span class="sxs-lookup"><span data-stu-id="750ec-249">Function</span></span> | <span data-ttu-id="750ec-250">异步运行的回调函数，以给定优先级调度。</span><span class="sxs-lookup"><span data-stu-id="750ec-250">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>  |  
      
      `priority` <span data-ttu-id="750ec-251">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-251">[in]</span></span>
      
      | <span data-ttu-id="750ec-252">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-252">Type</span></span> | <span data-ttu-id="750ec-253">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-253">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-254">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-254">DOMString</span></span> | <span data-ttu-id="750ec-255">运行 asynchronousCallback 回调的上下文优先级值。</span><span class="sxs-lookup"><span data-stu-id="750ec-255">The contextual priority value at which the asynchronousCallback callback is run.</span></span>  <span data-ttu-id="750ec-256">请参阅 [MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="750ec-256">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="750ec-257">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-257">[in]</span></span>
      
      | <span data-ttu-id="750ec-258">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-258">Type</span></span> | <span data-ttu-id="750ec-259">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-259">Description</span></span> |  
      |:---- |:--- |   
      | <span data-ttu-id="750ec-260">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-260">Any</span></span> | <span data-ttu-id="750ec-261">作为参数 1 等传递给同步Callback 回调函数 \ (的一系列可选参数) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-261">An optional series of arguments that are passed to the synchronousCallback callback function \(as parameters 1 and so on\).</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-262">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-262">Return value</span></span>**  
      
      <span data-ttu-id="750ec-263">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="750ec-263">This method does not return a value.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-264">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-264">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-265">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-265">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-266">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-266">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-267">提供的 `asynchronousCallback` 回调函数稍后异步执行。</span><span class="sxs-lookup"><span data-stu-id="750ec-267">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span>  `asynchronousCallback` <span data-ttu-id="750ec-268">将按照提供的优先级调度。</span><span class="sxs-lookup"><span data-stu-id="750ec-268">will be dispatched according to the provided priority.</span></span>  <span data-ttu-id="750ec-269">普通优先级等同于现有的 [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。</span><span class="sxs-lookup"><span data-stu-id="750ec-269">Normal priority is equivalent to the existing [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span>  <span data-ttu-id="750ec-270">当回调运行时，当前上下文优先级将设置为在执行回调期间提供的 priority 参数值。</span><span class="sxs-lookup"><span data-stu-id="750ec-270">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>  
      
      <span data-ttu-id="750ec-271">`asynchronousCallback`callback 参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="750ec-271">The `asynchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="750ec-272">如果参数在 参数 `priority` 之后提供，则所有参数都将传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="750ec-272">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>  
      
      <span data-ttu-id="750ec-273">与 `execAtPriority` 不同，回调函数返回的任何对象 `asynchronousCallback` 将被忽略 \ (，并且不会通过 `execAsyncAtPriority` \) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-273">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored \(and not returned via `execAsyncAtPriority`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-274">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-274">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <a name="execatpriority"></a><span data-ttu-id="750ec-275">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="750ec-275">execAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-276">以给定的上下文优先级运行指定的回调函数。</span><span class="sxs-lookup"><span data-stu-id="750ec-276">Runs the specified callback function at the given contextual priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-277">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-277">Parameters</span></span>**  
      
      `synchronousCallback` <span data-ttu-id="750ec-278">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-278">[in]</span></span>  
      
      | <span data-ttu-id="750ec-279">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-279">Type</span></span> | <span data-ttu-id="750ec-280">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-280">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-281">函数</span><span class="sxs-lookup"><span data-stu-id="750ec-281">Function</span></span> | <span data-ttu-id="750ec-282">要以给定优先级上下文优先级同步运行的回调函数。</span><span class="sxs-lookup"><span data-stu-id="750ec-282">The callback function to run synchronously at the given priority contextual priority.</span></span>  |  
      
      `priority` <span data-ttu-id="750ec-283">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-283">[in]</span></span>  
      
      | <span data-ttu-id="750ec-284">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-284">Type</span></span> | <span data-ttu-id="750ec-285">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-285">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-286">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-286">DOMString</span></span> | <span data-ttu-id="750ec-287">运行回调函数时，当前上下文优先级值将设置为的指定 `synchronousCallback` 优先级值。</span><span class="sxs-lookup"><span data-stu-id="750ec-287">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span>  <span data-ttu-id="750ec-288">请参阅 [MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="750ec-288">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="750ec-289">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-289">[in]</span></span>  
      
      | <span data-ttu-id="750ec-290">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-290">Type</span></span> | <span data-ttu-id="750ec-291">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-291">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-292">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-292">Any</span></span> | <span data-ttu-id="750ec-293">作为参数 1 等传递给回调函数 `synchronousCallback` \ (一系列可选参数) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-293">An optional series of arguments that are passed to the `synchronousCallback` callback function \(as parameters 1 and so on\).</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-294">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-294">Return value</span></span>**  
      
      | <span data-ttu-id="750ec-295">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-295">Type</span></span> | <span data-ttu-id="750ec-296">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-296">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-297">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-297">Any</span></span> | <span data-ttu-id="750ec-298">返回回调 `synchronousCallback` \ (的返回值（如果适用) ）。</span><span class="sxs-lookup"><span data-stu-id="750ec-298">Returns the return value of the `synchronousCallback` callback \(as applicable\).</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-299">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-299">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-300">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-300">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-301">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-301">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-302">提供的 `synchronousCallback` 回调方法将同步执行。</span><span class="sxs-lookup"><span data-stu-id="750ec-302">The provided `synchronousCallback` callback method is execute synchronously.</span></span>  <span data-ttu-id="750ec-303">当前上下文优先级更改为所提供的优先级值 (在提供的回调函数的持续时间内) priority 参数所给定的优先级值。</span><span class="sxs-lookup"><span data-stu-id="750ec-303">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span>  <span data-ttu-id="750ec-304">执行完回调函数后，优先级将返回到调用之前的 `execAtPriority` 上一个值。</span><span class="sxs-lookup"><span data-stu-id="750ec-304">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span>  <span data-ttu-id="750ec-305">的返回 `execAtPriority` 值是回调方法 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-305">The return value from `execAtPriority` is the return value of the callback method \(as provided\).</span></span>  
      
      <span data-ttu-id="750ec-306">`synchronousCallback`callback 参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="750ec-306">The `synchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="750ec-307">如果在 priority 参数之后提供了任何参数，则这些参数将传递给提供的回调方法。</span><span class="sxs-lookup"><span data-stu-id="750ec-307">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span>  <span data-ttu-id="750ec-308">如果 callback 参数返回值，则此值也将成为 的 `execAtPriority` 返回值。</span><span class="sxs-lookup"><span data-stu-id="750ec-308">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-309">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-309">Example</span></span>**  
      
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

### <a name="getcurrentpriority"></a><span data-ttu-id="750ec-310">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="750ec-310">getCurrentPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-311">返回当前上下文优先级。</span><span class="sxs-lookup"><span data-stu-id="750ec-311">Returns the current contextual priority.</span></span>  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-312">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-312">Parameters</span></span>**  
      
      <span data-ttu-id="750ec-313">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-313">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-314">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-314">Return value</span></span>**  
      
      | <span data-ttu-id="750ec-315">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-315">Type</span></span> | <span data-ttu-id="750ec-316">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-316">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-317">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-317">DOMString</span></span> | <span data-ttu-id="750ec-318">返回值是字符串 、 `MSApp.HIGH` 或 `MSApp.NORMAL` 之一 `MSApp.IDLE` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-318">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-319">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-319">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-320">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-320">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-321">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-321">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-322">此方法返回当前的上下文优先级 \ ([MSApp 常量](#msapp-constants)\) ，可通过 和 `execAtPriority` 进行更改 `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-322">This method returns the current contextual priority \(see [MSApp Constants](#msapp-constants)\), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-323">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-323">Example</span></span>**  
      
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

### <a name="gethtmlprintdocumentsource"></a><span data-ttu-id="750ec-324">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="750ec-324">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="750ec-325">已弃用同步 API。</span><span class="sxs-lookup"><span data-stu-id="750ec-325">Synchronous API that has been deprecated.</span></span>  <span data-ttu-id="750ec-326">对于 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-326">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span>  <span data-ttu-id="750ec-327">对于 Windows 8 和 8.1 应用，请参阅 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。</span><span class="sxs-lookup"><span data-stu-id="750ec-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <a name="gethtmlprintdocumentsourceasync"></a><span data-ttu-id="750ec-328">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="750ec-328">getHtmlPrintDocumentSourceAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-329">返回要打印的源内容。</span><span class="sxs-lookup"><span data-stu-id="750ec-329">Returns the source content that is to be printed.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-330">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-330">Parameters</span></span>**  
      
      `htmlDoc` <span data-ttu-id="750ec-331">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-331">[in]</span></span>  
      
      | <span data-ttu-id="750ec-332">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-332">Type</span></span> | <span data-ttu-id="750ec-333">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-333">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-334">文档</span><span class="sxs-lookup"><span data-stu-id="750ec-334">Document</span></span> | <span data-ttu-id="750ec-335">要打印的 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="750ec-335">The HTML document to be printed.</span></span>  <span data-ttu-id="750ec-336">它可以是根文档、iframe 中的文档、文档片段或 SVG 文档。</span><span class="sxs-lookup"><span data-stu-id="750ec-336">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span>  <span data-ttu-id="750ec-337">请注意，htmlDoc 必须是文档，而不是元素。</span><span class="sxs-lookup"><span data-stu-id="750ec-337">Be aware that htmlDoc must be a document, not an element.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-338">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-338">Return value</span></span>**
      
      <span data-ttu-id="750ec-339">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-339">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-340">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-340">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-341">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-341">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-342">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-342">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-343">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-343">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-344">示例 1</span><span class="sxs-lookup"><span data-stu-id="750ec-344">Example 1</span></span>**  
      
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
      **<span data-ttu-id="750ec-345">示例 2</span><span class="sxs-lookup"><span data-stu-id="750ec-345">Example 2</span></span>**  
      
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

### <a name="getviewid"></a><span data-ttu-id="750ec-346">getViewId</span><span class="sxs-lookup"><span data-stu-id="750ec-346">getViewId</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-347">支持多个窗口。</span><span class="sxs-lookup"><span data-stu-id="750ec-347">Support for multiple windows.</span></span>  
      
      > [!NOTE] 
      > <span data-ttu-id="750ec-348">在 Win8.1 中，JavaScript UWP 应用支持使用 MSApp DOM API 的多个窗口，这些 API 现已弃用。</span><span class="sxs-lookup"><span data-stu-id="750ec-348">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span>  <span data-ttu-id="750ec-349">对于 Windows 10，请使用 `window.open` 、 `window` 和 新的 `MSApp.getViewId` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-349">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>  
      
      | <span data-ttu-id="750ec-350">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-350">Description</span></span> |<span data-ttu-id="750ec-351">Windows10</span><span class="sxs-lookup"><span data-stu-id="750ec-351">Windows 10</span></span> | <span data-ttu-id="750ec-352">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="750ec-352">Windows 8.1</span></span> |  
      |:---- |:---- |:--- |  
      | <span data-ttu-id="750ec-353">创建新窗口</span><span class="sxs-lookup"><span data-stu-id="750ec-353">Create new window</span></span> | [<span data-ttu-id="750ec-354">window.open</span><span class="sxs-lookup"><span data-stu-id="750ec-354">window.open</span></span>](https://developer.mozilla.org/docs/Web/API/Window/open) | [<span data-ttu-id="750ec-355">MSApp.createNewView</span><span class="sxs-lookup"><span data-stu-id="750ec-355">MSApp.createNewView</span></span>](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |<span data-ttu-id="750ec-356">新建窗口对象</span><span class="sxs-lookup"><span data-stu-id="750ec-356">New window object</span></span> | [<span data-ttu-id="750ec-357">窗口</span><span class="sxs-lookup"><span data-stu-id="750ec-357">window</span></span>](https://developer.mozilla.org/docs/Web/API/Window) |[<span data-ttu-id="750ec-358">MSAppView</span><span class="sxs-lookup"><span data-stu-id="750ec-358">MSAppView</span></span>](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-359">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-359">Parameters</span></span>**  
      
      `window`
      
      | <span data-ttu-id="750ec-360">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-360">Type</span></span> | <span data-ttu-id="750ec-361">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-361">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-362">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-362">DOMString</span></span> | <span data-ttu-id="750ec-363">一个代表包含 DOM 文档的窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="750ec-363">An object representing a window containing a DOM document.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-364">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-364">Return value</span></span>**  
      
      `viewId`
      
      | <span data-ttu-id="750ec-365">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-365">Type</span></span> | <span data-ttu-id="750ec-366">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-366">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-367">数字</span><span class="sxs-lookup"><span data-stu-id="750ec-367">Number</span></span> | <span data-ttu-id="750ec-368">可以与各种 [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 一同使用。</span><span class="sxs-lookup"><span data-stu-id="750ec-368">Can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-369">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-369">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-370">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-370">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-371">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-371">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-372">使用 [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) 和 [window](https://developer.mozilla.org/docs/Web/API/Window) 创建新窗口，但随后要与 WinRT API 进行交互，请添加 `MSApp.getViewId` API。</span><span class="sxs-lookup"><span data-stu-id="750ec-372">Use [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) and [window](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span>  <span data-ttu-id="750ec-373">它将对象作为参数，并返回可用于各种 `window` `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 的一个数字。</span><span class="sxs-lookup"><span data-stu-id="750ec-373">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  
      
      *   <span data-ttu-id="750ec-374">延迟可见性</span><span class="sxs-lookup"><span data-stu-id="750ec-374">Delaying Visibility</span></span>  
          
          <span data-ttu-id="750ec-375">WinRT 中的视图通常开始隐藏，并且最终开发人员使用类似方法在视图完全准备好 `TryShowAsStandaloneAsync` 后显示视图。</span><span class="sxs-lookup"><span data-stu-id="750ec-375">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span>  <span data-ttu-id="750ec-376">在 Web 中，立即显示一个窗口，最终用户 `window.open` 可以在加载和呈现内容时进行监视。</span><span class="sxs-lookup"><span data-stu-id="750ec-376">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span>  <span data-ttu-id="750ec-377">若要让新窗口像 WinRT 中的视图一样运行，并且不会立即显示，我们添加了 `window.open` 一个选项。</span><span class="sxs-lookup"><span data-stu-id="750ec-377">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span>  <span data-ttu-id="750ec-378">例如：</span><span class="sxs-lookup"><span data-stu-id="750ec-378">For example:</span></span>  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   <span data-ttu-id="750ec-379">主窗口差异</span><span class="sxs-lookup"><span data-stu-id="750ec-379">Primary Window Differences</span></span>  
          
          <span data-ttu-id="750ec-380">操作系统最初打开的主窗口与它打开的辅助窗口的行为不同：</span><span class="sxs-lookup"><span data-stu-id="750ec-380">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span>  
          
          | <span data-ttu-id="750ec-381">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-381">Description</span></span> | <span data-ttu-id="750ec-382">主要</span><span class="sxs-lookup"><span data-stu-id="750ec-382">Primary</span></span> | <span data-ttu-id="750ec-383">辅助边框</span><span class="sxs-lookup"><span data-stu-id="750ec-383">Secondary</span></span> |  
          |:---- |:--- |:--- |  
          | <span data-ttu-id="750ec-384">window.open</span><span class="sxs-lookup"><span data-stu-id="750ec-384">window.open</span></span> | <span data-ttu-id="750ec-385">允许</span><span class="sxs-lookup"><span data-stu-id="750ec-385">Allowed</span></span> | <span data-ttu-id="750ec-386">不允许</span><span class="sxs-lookup"><span data-stu-id="750ec-386">Disallowed</span></span> |  
          | <span data-ttu-id="750ec-387">window.close</span><span class="sxs-lookup"><span data-stu-id="750ec-387">window.close</span></span> | <span data-ttu-id="750ec-388">关闭应用</span><span class="sxs-lookup"><span data-stu-id="750ec-388">Close app</span></span> | <span data-ttu-id="750ec-389">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="750ec-389">Close window</span></span> |  
          | <span data-ttu-id="750ec-390">导航限制</span><span class="sxs-lookup"><span data-stu-id="750ec-390">Navigation restrictions</span></span> | <span data-ttu-id="750ec-391">仅 ACUR</span><span class="sxs-lookup"><span data-stu-id="750ec-391">ACUR only</span></span> | <span data-ttu-id="750ec-392">无限制</span><span class="sxs-lookup"><span data-stu-id="750ec-392">No restrictions</span></span> |  
          
         <!-- The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).  -->  
      
      *   <span data-ttu-id="750ec-393">同源通信限制</span><span class="sxs-lookup"><span data-stu-id="750ec-393">Same Origin Communication Restrictions</span></span>  
          
          <span data-ttu-id="750ec-394">存在一个难以解决的技术问题，即无法正确支持同步、同源、跨窗口、脚本调用。</span><span class="sxs-lookup"><span data-stu-id="750ec-394">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span>  <span data-ttu-id="750ec-395">打开同一来源的窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。</span><span class="sxs-lookup"><span data-stu-id="750ec-395">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span>  `postMessage` <span data-ttu-id="750ec-396">调用可以正常工作，并且建议尽可能执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="750ec-396">calls work just fine and is the recommended way to do things if possible.</span></span>  <span data-ttu-id="750ec-397">正在改进此问题。</span><span class="sxs-lookup"><span data-stu-id="750ec-397">Work to improve this issue is in progress.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-398">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-398">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <a name="istaskscheduledatpriorityorhigher"></a><span data-ttu-id="750ec-399">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="750ec-399">isTaskScheduledAtPriorityOrHigher</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-400">返回一个 Boolean 值，该值指示在给定优先级级别还是更高优先级存在挂起的工作。</span><span class="sxs-lookup"><span data-stu-id="750ec-400">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-401">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-401">Parameters</span></span>**  
      
      `priority` <span data-ttu-id="750ec-402">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-402">[in]</span></span>
      
      | <span data-ttu-id="750ec-403">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-403">Type</span></span> | <span data-ttu-id="750ec-404">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-404">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-405">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-405">DOMString</span></span> | <span data-ttu-id="750ec-406">优先级值 \ (请参阅 [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work。</span><span class="sxs-lookup"><span data-stu-id="750ec-406">A priority value \(see [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-407">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-407">Return value</span></span>**  
      
      | <span data-ttu-id="750ec-408">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-408">Type</span></span> | <span data-ttu-id="750ec-409">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-409">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-410">布尔</span><span class="sxs-lookup"><span data-stu-id="750ec-410">Boolean</span></span> | <span data-ttu-id="750ec-411">否则 `true` ，返回指定优先级或高于指定优先级的任何排队 `false` 工作。</span><span class="sxs-lookup"><span data-stu-id="750ec-411">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-412">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-412">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-413">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-413">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-414">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-414">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-415">此方法为 JavaScript 代码提供了一种方法，用于确定各个优先级 `isTaskScheduledAtPriorityOrHigher` 级别 \ (或更高版本\) 是否有待处理的工作，目的是调用 JavaScript 代码随后可以决定获得更高优先级的工作。</span><span class="sxs-lookup"><span data-stu-id="750ec-415">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels \(or above\) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-416">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-416">Example</span></span>**  
      
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

### <a name="pagehandlesallapplicationactivations"></a><span data-ttu-id="750ec-417">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="750ec-417">pageHandlesAllApplicationActivations</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-418">用于避免刷新每次激活事件 \ (之前) 页面重新加载的开始路径 (例如单击通知或固定磁贴\) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-418">Used to avoid a refresh of the start path (page reload) before every activate event \(such as clicking a notification or a pinned tile\).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-419">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-419">Parameters</span></span>**  
      
      | <span data-ttu-id="750ec-420">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-420">Type</span></span> | <span data-ttu-id="750ec-421">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-421">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-422">布尔</span><span class="sxs-lookup"><span data-stu-id="750ec-422">Boolean</span></span> | <span data-ttu-id="750ec-423">使用 始终跳过刷新页面重新加载 (路径，) 直接跳转以触发 `MSApp.pageHandlesAllApplicationActivations(true)` `WebUIApplication` 激活的事件。</span><span class="sxs-lookup"><span data-stu-id="750ec-423">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span>  <span data-ttu-id="750ec-424">要求所有页面单独处理激活事件。</span><span class="sxs-lookup"><span data-stu-id="750ec-424">Requires that all pages handle activation events separately.</span></span>  <span data-ttu-id="750ec-425">将此方法定义为 ，单击激活事件 `true` \ (如 notification\) 不会触发重新加载，这是单页应用避免重新加载页面的必备条件。</span><span class="sxs-lookup"><span data-stu-id="750ec-425">By defining this method as `true`, clicking an activated event \(like a notification\) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-426">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-426">Return value</span></span>**
      
      <span data-ttu-id="750ec-427">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-427">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-428">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-428">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-429">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-429">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-430">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-430">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-431">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-431">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-432">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-432">Example</span></span>**  
      
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

### <a name="suppresssubdownloadcredentialprompts"></a><span data-ttu-id="750ec-433">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="750ec-433">suppressSubdownloadCredentialPrompts</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-434">控制应用是否在资源下载过程中禁止可能的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="750ec-434">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-435">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-435">Parameters</span></span>**  
     
      `suppress` <span data-ttu-id="750ec-436">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-436">[in]</span></span>
      
      | <span data-ttu-id="750ec-437">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-437">Type</span></span> | <span data-ttu-id="750ec-438">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-438">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-439">布尔</span><span class="sxs-lookup"><span data-stu-id="750ec-439">Boolean</span></span> | <span data-ttu-id="750ec-440">值为 true 将禁止潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="750ec-440">A value of true suppresses potential authentication prompts.</span></span>  <span data-ttu-id="750ec-441">false 值不会抑制来自用户的任何潜在身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="750ec-441">A value of false does not suppress any potential authentication prompts from the user.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-442">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-442">Return value</span></span>**  
      
      <span data-ttu-id="750ec-443">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-443">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-444">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-444">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-445">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-445">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-446">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-446">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-447">`suppressSubdownloadCredentialPrompts`该方法控制应用在下载资源期间是否禁止潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="750ec-447">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span>  <span data-ttu-id="750ec-448">默认行为是禁止显示凭据提示。</span><span class="sxs-lookup"><span data-stu-id="750ec-448">The default behavior is to not suppress credential prompts.</span></span>  
      
      `suppressSubdownloadCredentialPrompts` <span data-ttu-id="750ec-449">供可能加载大量需要身份验证的资源的应用程序使用，例如邮件应用程序 \ (其中可能包含一个新闻稿，其中包含许多图像，其中每个图像都需要身份验证\) 。</span><span class="sxs-lookup"><span data-stu-id="750ec-449">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app \(which could contain a newsletter containing a number of images where each image requires authentication\).</span></span>  
      
      <span data-ttu-id="750ec-450">禁止显示凭据提示时，在访问需要身份验证的资源时，将不会显示用于向服务器进行身份验证的对话框，并且不会下载该资源。</span><span class="sxs-lookup"><span data-stu-id="750ec-450">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span>  <span data-ttu-id="750ec-451">请注意，不会影响代理身份验证或客户端认证请求对话框等其他可能提示，也不会 `suppressSubdownloadCredentialPrompts` 影响 XHR。</span><span class="sxs-lookup"><span data-stu-id="750ec-451">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>  
      
      <span data-ttu-id="750ec-452">请注意， `suppressSubdownloadCredentialPrompts` 这会影响应用程序内的所有内容，包括元素中托管 `webview` 的内容。</span><span class="sxs-lookup"><span data-stu-id="750ec-452">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>  
      
      > [!IMPORTANT]
      > <span data-ttu-id="750ec-453">将缓存凭据提示决策。</span><span class="sxs-lookup"><span data-stu-id="750ec-453">Credential prompt decisions are cached.</span></span>  <span data-ttu-id="750ec-454">因此，尽管取消显示凭据提示会立即生效，但允许隐藏凭据提示后允许凭据提示可能需要重新加载文档以生效。</span><span class="sxs-lookup"><span data-stu-id="750ec-454">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-455">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-455">Example</span></span>**  
      
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

### <a name="terminateapp"></a><span data-ttu-id="750ec-456">terminateApp</span><span class="sxs-lookup"><span data-stu-id="750ec-456">terminateApp</span></span>  


:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-457">终止当前应用程序并生成故障报告。</span><span class="sxs-lookup"><span data-stu-id="750ec-457">Terminates the current application and generates a failure report.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-458">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-458">Parameters</span></span>**  
      
      `error` <span data-ttu-id="750ec-459">[in]</span><span class="sxs-lookup"><span data-stu-id="750ec-459">[in]</span></span>
      
      | <span data-ttu-id="750ec-460">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-460">Type</span></span> | <span data-ttu-id="750ec-461">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-461">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-462">错误</span><span class="sxs-lookup"><span data-stu-id="750ec-462">Error</span></span> | <span data-ttu-id="750ec-463">`Error`一个可用于描述触发终止的错误的对象。</span><span class="sxs-lookup"><span data-stu-id="750ec-463">An `Error` object that you can use to describe the error that triggered the termination.</span></span>  <span data-ttu-id="750ec-464">对象必须包含数字、说明和堆栈属性;如果对象不包含这些属性，将不会生成 `Error` 故障报告。</span><span class="sxs-lookup"><span data-stu-id="750ec-464">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-465">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-465">Return value</span></span>**
      
      <span data-ttu-id="750ec-466">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-466">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-467">异常</span><span class="sxs-lookup"><span data-stu-id="750ec-467">Exceptions</span></span>**  
      
      <span data-ttu-id="750ec-468">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-468">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-469">备注</span><span class="sxs-lookup"><span data-stu-id="750ec-469">Remarks</span></span>**  
      
      <span data-ttu-id="750ec-470">如果报告的问题成为应用的前 5 个问题之一，它将显示在应用的"质量" `terminateApp` 页面上。</span><span class="sxs-lookup"><span data-stu-id="750ec-470">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-471">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-471">Example</span></span>**  
      
      <span data-ttu-id="750ec-472">此示例在 `terminateApp` 遇到异常时调用 。</span><span class="sxs-lookup"><span data-stu-id="750ec-472">This example calls `terminateApp` when an exception is encountered.</span></span>  <span data-ttu-id="750ec-473">它使用 `Error` 捕获异常时提供的对象。</span><span class="sxs-lookup"><span data-stu-id="750ec-473">It uses the `Error` object provided when you catch an exception.</span></span>  
      
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

### <a name="msapp-constants"></a><span data-ttu-id="750ec-474">MSApp 常量</span><span class="sxs-lookup"><span data-stu-id="750ec-474">MSApp Constants</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-475">与 、 、 和 `execAsyncAtPriority` 关联的允许 `execAtPriority` `getCurrentPriority` 的优先级值 `isTaskScheduldAtPriorityOrHigher` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-475">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>  
   :::column-end:::
   :::column span="":::
      #### <a name="current"></a><span data-ttu-id="750ec-476">Current</span><span class="sxs-lookup"><span data-stu-id="750ec-476">Current</span></span>  
      
      `current`  
      
      | <span data-ttu-id="750ec-477">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-477">Type</span></span> | <span data-ttu-id="750ec-478">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-478">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-479">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-479">DOMString</span></span> | <span data-ttu-id="750ec-480">当 `current` 与适当的方法 \ (See also section\) 一起使用时，该方法将在执行请求的操作时使用当前上下文优先级。</span><span class="sxs-lookup"><span data-stu-id="750ec-480">When `current` is used with the appropriate method \(See also section\), the method will use the current contextual priority when executing the requested operation.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <a name="high"></a><span data-ttu-id="750ec-481">高 </span><span class="sxs-lookup"><span data-stu-id="750ec-481">High</span></span>  
      
      `high`  
      
      | <span data-ttu-id="750ec-482">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-482">Type</span></span> | <span data-ttu-id="750ec-483">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-483">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-484">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-484">DOMString</span></span> | <span data-ttu-id="750ec-485">当与适当的方法 `high` \ (See also section\) 一同使用时，该方法在执行请求的操作时将使用高于正常优先级的优先级，并且将在任何现有的普通优先级工作之前调度该操作。</span><span class="sxs-lookup"><span data-stu-id="750ec-485">When `high` is used with the appropriate method \(See also section\), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      #### <a name="idle"></a><span data-ttu-id="750ec-486">Idle</span><span class="sxs-lookup"><span data-stu-id="750ec-486">Idle</span></span>  
      
      `idle`  
      
      | <span data-ttu-id="750ec-487">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-487">Type</span></span> | <span data-ttu-id="750ec-488">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-488">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-489">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-489">DOMString</span></span> | <span data-ttu-id="750ec-490">当与适当的方法 `ideal` \ (See also section\) 一同使用时，该方法在执行请求的操作时将使用低于正常优先级的优先级，并且将在任何现有的普通优先级工作之后调度该操作。</span><span class="sxs-lookup"><span data-stu-id="750ec-490">When `ideal` is used with the appropriate method \(See also section\), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <a name="normal"></a><span data-ttu-id="750ec-491">正常</span><span class="sxs-lookup"><span data-stu-id="750ec-491">Normal</span></span>  
      
      `normal`  
      
      | <span data-ttu-id="750ec-492">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-492">Type</span></span> | <span data-ttu-id="750ec-493">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-493">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-494">DOMString</span><span class="sxs-lookup"><span data-stu-id="750ec-494">DOMString</span></span> | <span data-ttu-id="750ec-495">当与适当的方法一 (请参阅"另请参阅) "部分时，该方法将在执行请求的操作时使用正常的 `normal` 现有优先级。</span><span class="sxs-lookup"><span data-stu-id="750ec-495">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-496">示例</span><span class="sxs-lookup"><span data-stu-id="750ec-496">Example</span></span>**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-497">要求</span><span class="sxs-lookup"><span data-stu-id="750ec-497">Requirements</span></span>**  
      
      | <span data-ttu-id="750ec-498">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-498">Type</span></span> | <span data-ttu-id="750ec-499">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-499">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-500">IDL</span><span class="sxs-lookup"><span data-stu-id="750ec-500">IDL</span></span> | <span data-ttu-id="750ec-501">Mshtml.idl</span><span class="sxs-lookup"><span data-stu-id="750ec-501">Mshtml.idl</span></span> |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <a name="msappasyncoperation"></a><span data-ttu-id="750ec-502">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="750ec-502">MSAppAsyncOperation</span></span>  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <a name="start"></a><span data-ttu-id="750ec-503">start</span><span class="sxs-lookup"><span data-stu-id="750ec-503">start</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="750ec-504">启动 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-504">Starts the `MSAppAsyncOperation`.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="750ec-505">参数</span><span class="sxs-lookup"><span data-stu-id="750ec-505">Parameters</span></span>**  
      
      <span data-ttu-id="750ec-506">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-506">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="750ec-507">返回值</span><span class="sxs-lookup"><span data-stu-id="750ec-507">Return value</span></span>**
      
      <span data-ttu-id="750ec-508">无。</span><span class="sxs-lookup"><span data-stu-id="750ec-508">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **<span data-ttu-id="750ec-509">属性</span><span class="sxs-lookup"><span data-stu-id="750ec-509">Properties</span></span>**  
      
      `error` <span data-ttu-id="750ec-510">属性</span><span class="sxs-lookup"><span data-stu-id="750ec-510">property</span></span>  
      
      | <span data-ttu-id="750ec-511">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-511">Type</span></span> | <span data-ttu-id="750ec-512">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-512">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-513">DOMError</span><span class="sxs-lookup"><span data-stu-id="750ec-513">DOMError</span></span> | <span data-ttu-id="750ec-514">表示 中的错误 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-514">Represents an error in `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` <span data-ttu-id="750ec-515">属性</span><span class="sxs-lookup"><span data-stu-id="750ec-515">property</span></span>  
      
      | <span data-ttu-id="750ec-516">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-516">Type</span></span> | <span data-ttu-id="750ec-517">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-517">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-518">EventHandler</span><span class="sxs-lookup"><span data-stu-id="750ec-518">EventHandler</span></span> | <span data-ttu-id="750ec-519">属性，用于在完成 时设置事件处理程序 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-519">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` <span data-ttu-id="750ec-520">属性</span><span class="sxs-lookup"><span data-stu-id="750ec-520">property</span></span>  
      
      | <span data-ttu-id="750ec-521">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-521">Type</span></span> | <span data-ttu-id="750ec-522">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-522">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-523">EventHandler</span><span class="sxs-lookup"><span data-stu-id="750ec-523">EventHandler</span></span> | <span data-ttu-id="750ec-524">属性，用于设置错误时的事件处理程序 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-524">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` <span data-ttu-id="750ec-525">属性</span><span class="sxs-lookup"><span data-stu-id="750ec-525">property</span></span>  
      
      | <span data-ttu-id="750ec-526">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-526">Type</span></span> | <span data-ttu-id="750ec-527">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-527">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-528">数字</span><span class="sxs-lookup"><span data-stu-id="750ec-528">Number</span></span> | <span data-ttu-id="750ec-529">表示使用 JavaScript 的 Windows 应用中异步操作的状态。</span><span class="sxs-lookup"><span data-stu-id="750ec-529">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span>  <span data-ttu-id="750ec-530">值包括 `Started[0]` `Completed[1]` `Error[2]` ：、、。</span><span class="sxs-lookup"><span data-stu-id="750ec-530">Values include: `Started[0]`, `Completed[1]`, `Error[2]`.</span></span>  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` <span data-ttu-id="750ec-531">属性</span><span class="sxs-lookup"><span data-stu-id="750ec-531">property</span></span>  
      
      | <span data-ttu-id="750ec-532">类型</span><span class="sxs-lookup"><span data-stu-id="750ec-532">Type</span></span> | <span data-ttu-id="750ec-533">描述</span><span class="sxs-lookup"><span data-stu-id="750ec-533">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="750ec-534">Any</span><span class="sxs-lookup"><span data-stu-id="750ec-534">Any</span></span> |<span data-ttu-id="750ec-535">表示 的结果 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="750ec-535">Represents the result of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
