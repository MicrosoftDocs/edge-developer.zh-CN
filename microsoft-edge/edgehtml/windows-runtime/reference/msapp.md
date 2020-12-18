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
# <span data-ttu-id="6ed01-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="6ed01-105">MSApp</span></span>  

[!INCLUDE [deprecation-note](../../includes/legacy-edge-note.md)]  

<span data-ttu-id="6ed01-106">MSApp 对象及其成员仅支持使用 JavaScript \ (（包括访问 Windows API 功能的 PWA）的 Windows 应用) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-106">The MSApp object and its members are supported only for Windows apps using JavaScript \(including PWAs accessing Windows API features\).</span></span>  <span data-ttu-id="6ed01-107">MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中的 HTML 文档的本地上下文中;否则，该对象不存在 (因此，该对象的方法和属性均) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>  

<span data-ttu-id="6ed01-108">它提供可帮助您创建 [Blob](https://developer.mozilla.org/docs/Web/API/Blob) 和 [MSStream 对象的帮助程序](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) 函数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>  

```javascript
var result = MSApp.method;
```  

:::row:::
   :::column span="1":::
      [<span data-ttu-id="6ed01-109">方法</span><span class="sxs-lookup"><span data-stu-id="6ed01-109">Methods</span></span>](#msapp-methods)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6ed01-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync)， [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)， [createDataPackage](#createdatapackage)， [createDataPackageFromSelection，](#createdatapackagefromselection) [createFileFromStorageFile](#createfilefromstoragefile)， [createStreamFromInputStream](#createstreamfrominputstream)， [execAsyncAtPriority](#execasyncatpriority)， [execAtPriority](#execatpriority)， [getCurrentPriority](#getcurrentpriority)， [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)，[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)， [getViewId](#getviewid)， [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher)， [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations)， [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts)， [terminateApp.](#terminateapp)</span><span class="sxs-lookup"><span data-stu-id="6ed01-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6ed01-111">常量</span><span class="sxs-lookup"><span data-stu-id="6ed01-111">Constants</span></span>](#msapp-constants)  
   :::column-end:::
   :::column span="2":::
      <span data-ttu-id="6ed01-112">[当前](#current)、 [高](#high)、 [空闲](#idle)、 [正常](#normal)。</span><span class="sxs-lookup"><span data-stu-id="6ed01-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="1":::
      [<span data-ttu-id="6ed01-113">MSAppAsyncOperation 接口</span><span class="sxs-lookup"><span data-stu-id="6ed01-113">MSAppAsyncOperation interface</span></span>](#msappasyncoperation)  
   :::column-end:::
   :::column span="2":::
      [<span data-ttu-id="6ed01-114">start</span><span class="sxs-lookup"><span data-stu-id="6ed01-114">start</span></span>](#start)  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="6ed01-115">MSApp 方法</span><span class="sxs-lookup"><span data-stu-id="6ed01-115">MSApp methods</span></span>  

### <span data-ttu-id="6ed01-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="6ed01-116">clearTemporaryWebDataAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-117">清除应用或 [WebView](../../hosting/webview/index.md)的缓存和索引DB 数据。</span><span class="sxs-lookup"><span data-stu-id="6ed01-117">Clears cache and indexedDB data for the app or [WebView](../../hosting/webview/index.md).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.clearTemporaryWebDataAsync(#); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-118">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-118">Parameters</span></span>**  
      
      <span data-ttu-id="6ed01-119">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-119">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-120">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-120">Return value</span></span>**  
      
      <span data-ttu-id="6ed01-121">类型 [：IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="6ed01-121">Type: [IAsyncAction](/uwp/api/windows.foundation.iasyncaction)</span></span>  
      
      <span data-ttu-id="6ed01-122">表示异步操作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-122">Represents an asynchronous action.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-123">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-123">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-124">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-124">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-125">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-125">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-126">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-126">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-127">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-127">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="6ed01-128">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="6ed01-128">createBlobFromRandomAccessStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-129">从[IRandomAccessStream 对象创建](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)Blob。 [](https://developer.mozilla.org/docs/Web/API/Blob)</span><span class="sxs-lookup"><span data-stu-id="6ed01-129">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span>  <span data-ttu-id="6ed01-130">在处理应用中的对象时，应使用此方法，以便从流创建基于 `IRandomAccessStream` W3C 的对象。</span><span class="sxs-lookup"><span data-stu-id="6ed01-130">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span>  <span data-ttu-id="6ed01-131">创建 blob 后，它可以与 [FileReader、URL](https://developer.mozilla.org/docs/Web/API/FileReader) [API](https://developer.mozilla.org/docs/Web/API/URL)和 [XMLHttpRequest 一起使用](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)。</span><span class="sxs-lookup"><span data-stu-id="6ed01-131">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-132">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-132">Parameters</span></span>**  
      
      `type` <span data-ttu-id="6ed01-133">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-133">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-134">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-134">Type</span></span> | <span data-ttu-id="6ed01-135">说明</span><span class="sxs-lookup"><span data-stu-id="6ed01-135">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-136">字符串</span><span class="sxs-lookup"><span data-stu-id="6ed01-136">String</span></span> | <span data-ttu-id="6ed01-137">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="6ed01-137">Content type of the data.</span></span>  <span data-ttu-id="6ed01-138">此字符串的格式应为 RFC 2616 的第 3.7 节中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="6ed01-138">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  |  
      
      `stream` <span data-ttu-id="6ed01-139">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-139">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-140">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-140">Type</span></span> | <span data-ttu-id="6ed01-141">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-141">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-142">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-142">Any</span></span> | <span data-ttu-id="6ed01-143">要存储在 Blob 中的[IRandomAccessStream。](/uwp/api/Windows.Storage.Streams.IRandomAccessStream)</span><span class="sxs-lookup"><span data-stu-id="6ed01-143">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-144">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-144">Return value</span></span>**  
      
      | <span data-ttu-id="6ed01-145">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-145">Type</span></span> | <span data-ttu-id="6ed01-146">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-146">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-147">Blob</span><span class="sxs-lookup"><span data-stu-id="6ed01-147">Blob</span></span> | <span data-ttu-id="6ed01-148">包含流的新 blob 对象。</span><span class="sxs-lookup"><span data-stu-id="6ed01-148">New blob object that contains the stream.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-149">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-149">Exceptions</span></span>**  
      
      | <span data-ttu-id="6ed01-150">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-150">Exception</span></span> | <span data-ttu-id="6ed01-151">条件</span><span class="sxs-lookup"><span data-stu-id="6ed01-151">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-152">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="6ed01-152">TypeMismatchError</span></span> | <span data-ttu-id="6ed01-153">节点类型与预期的参数类型不兼容。</span><span class="sxs-lookup"><span data-stu-id="6ed01-153">The node type is incompatible with the expected parameter type.</span></span>  <span data-ttu-id="6ed01-154">对于早于 Internet Explorer 10 的版本，TYPE_MISMATCH_ERR返回。</span><span class="sxs-lookup"><span data-stu-id="6ed01-154">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-155">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-155">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-156">通过窗口对象的 MSApp 命名空间从 Windows 运行时类型创建 Blob。</span><span class="sxs-lookup"><span data-stu-id="6ed01-156">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span>  <span data-ttu-id="6ed01-157">此方法将创建一个 blob，该 blob 实质上是提供给 [它的 RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 对象的光包装。</span><span class="sxs-lookup"><span data-stu-id="6ed01-157">This method will create a blob that is essentially a light wrapper over the [RandomAccessStream](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span>  <span data-ttu-id="6ed01-158">blob 拥有此流的生存期，该流将在 blob 销毁时关闭。</span><span class="sxs-lookup"><span data-stu-id="6ed01-158">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-159">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-159">Example</span></span>**  
      
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

### <span data-ttu-id="6ed01-160">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="6ed01-160">createDataPackage</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-161">将用户或应用程序的指定区域转换为可共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="6ed01-161">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackage(object); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-162">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-162">Parameters</span></span>**  
      
      `object` <span data-ttu-id="6ed01-163">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-163">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-164">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-164">Type</span></span> | <span data-ttu-id="6ed01-165">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-165">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-166">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-166">Any</span></span> | <span data-ttu-id="6ed01-167">可以从选择对象创建此范围，例如： 或 `window.selection.getRangeAt(0)` 手动创建。</span><span class="sxs-lookup"><span data-stu-id="6ed01-167">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-168">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-168">Return value</span></span>**  
      
      | <span data-ttu-id="6ed01-169">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-169">Type</span></span> | <span data-ttu-id="6ed01-170">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-170">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-171">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-171">Any</span></span> | <span data-ttu-id="6ed01-172">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="6ed01-172">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-173">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-173">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-174">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-174">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-175">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-175">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-176">此方法仅支持[文档对象模型 (DOM) Range，](https://developer.mozilla.org/docs/Web/API/Range)而不是[TextRange。](/uwp/api/windows.ui.xaml.documents.textrange)</span><span class="sxs-lookup"><span data-stu-id="6ed01-176">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span>  <span data-ttu-id="6ed01-177">指定范围的返回数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="6ed01-177">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>  
      
      <span data-ttu-id="6ed01-178">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="6ed01-178">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-179">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-179">Example</span></span>**  
      
      <span data-ttu-id="6ed01-180">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-180">None.</span></span>  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="6ed01-181">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="6ed01-181">createDataPackageFromSelection</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-182">将用户或应用程序的选择转换为可共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="6ed01-182">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createDataPackageFromSelection(); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-183">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-183">Parameters</span></span>**  
      
      <span data-ttu-id="6ed01-184">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-184">This method has no parameters.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-185">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-185">Return value</span></span>**  
      
      | <span data-ttu-id="6ed01-186">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-186">Type</span></span> | <span data-ttu-id="6ed01-187">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-187">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-188">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-188">Any</span></span> | <span data-ttu-id="6ed01-189">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="6ed01-189">Contains the HTML markup for the specified range.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-190">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-190">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-191">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-191">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-192">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-192">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-193">所选内容返回的数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="6ed01-193">The returned data package for the selection contains HTML markup in clipboard format.</span></span>  <span data-ttu-id="6ed01-194">如果在应用程序的 UI 中没有任何用户选择，则 `createDataPackageFromSelection` 返回 `null` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-194">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns `null`.</span></span>  
      
      <span data-ttu-id="6ed01-195">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="6ed01-195">There are no available properties for the returned data package.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-196">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-196">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
 
### <span data-ttu-id="6ed01-197">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="6ed01-197">createFileFromStorageFile</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-198">将 [WinRT](/uwp/api/) [StorageFile 转换为](/uwp/api/windows.storage.storagefile) 标准 W3C [文件](https://developer.mozilla.org/docs/Web/API/File) 对象。</span><span class="sxs-lookup"><span data-stu-id="6ed01-198">Converts a [WinRT](/uwp/api/) [StorageFile](/uwp/api/windows.storage.storagefile) to a standard W3C [File](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retVal = MSApp.createFileFromStorageFile(storageFile); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-199">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-199">Parameters</span></span>**  
      
      `storageFile` <span data-ttu-id="6ed01-200">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-200">[in]</span></span>
      
      | <span data-ttu-id="6ed01-201">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-201">Type</span></span> | <span data-ttu-id="6ed01-202">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-202">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-203">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-203">Any</span></span> | <span data-ttu-id="6ed01-204">包含存储文件。</span><span class="sxs-lookup"><span data-stu-id="6ed01-204">Contains the storage file.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-205">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-205">Return value</span></span>**
      
      <span data-ttu-id="6ed01-206">无</span><span class="sxs-lookup"><span data-stu-id="6ed01-206">None</span></span>    
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-207">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-207">Exceptions</span></span>**  
      
      | <span data-ttu-id="6ed01-208">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-208">Exception</span></span> | <span data-ttu-id="6ed01-209">条件</span><span class="sxs-lookup"><span data-stu-id="6ed01-209">Condition</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-210">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="6ed01-210">TypeMismatchError</span></span> | <span data-ttu-id="6ed01-211">指定的 W3C 文件引用无效。</span><span class="sxs-lookup"><span data-stu-id="6ed01-211">The specified W3C file reference is invalid.</span></span>  <span data-ttu-id="6ed01-212">对于早于 Internet Explorer 10 的版本， `TYPE_MISMATCH_ERR` 将返回。</span><span class="sxs-lookup"><span data-stu-id="6ed01-212">For versions earlier than Internet Explorer 10, `TYPE_MISMATCH_ERR` is returned.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-213">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-213">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-214">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-214">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-215">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-215">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="6ed01-216">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="6ed01-216">createStreamFromInputStream</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-217">从 InputStream 创建[MSStream。](https://msdn.microsoft.com/library/hh772327) [](https://msdn.microsoft.com/library/hh772328)</span><span class="sxs-lookup"><span data-stu-id="6ed01-217">Creates an [MSStream](https://msdn.microsoft.com/library/hh772328) from an [InputStream](https://msdn.microsoft.com/library/hh772327).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-218">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-218">Parameters</span></span>**  
      
      `type` <span data-ttu-id="6ed01-219">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-219">[in]</span></span>
      
      | <span data-ttu-id="6ed01-220">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-220">Type</span></span> | <span data-ttu-id="6ed01-221">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-221">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-222">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-222">DOMString</span></span> | <span data-ttu-id="6ed01-223">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="6ed01-223">Content type of the data.</span></span>  <span data-ttu-id="6ed01-224">此字符串的格式应为 RFC 2616 的第 3.7 节中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="6ed01-224">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>  <span data-ttu-id="6ed01-225">\ ([请参阅 MIME 类型，] (如 ， 等 https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) `text/plain` `text/html` `image/jpeg` `image/png` `audio/mpeg` `audio/ogg` `audio/*` `video/mp4` \) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-225">\([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types\) such as `text/plain`, `text/html`, `image/jpeg`, `image/png`, `audio/mpeg`, `audio/ogg`, `audio/*`, `video/mp4`, and so on\).</span></span>  
      
      `inputStream` <span data-ttu-id="6ed01-226">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-226">[in]</span></span>
      
      | <span data-ttu-id="6ed01-227">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-227">Type</span></span> | <span data-ttu-id="6ed01-228">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-228">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-229">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-229">Any</span></span> | <span data-ttu-id="6ed01-230">要[存储在中的 IInputStream。](/uwp/api/Windows.Storage.Streams.IInputStream) `MSStream`</span><span class="sxs-lookup"><span data-stu-id="6ed01-230">The [IInputStream](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-231">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-231">Return value</span></span>**
      
      <span data-ttu-id="6ed01-232">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-232">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-233">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-233">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-234">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-234">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-235">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-235">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-236">此方法采用内容类型和 `IInputStream` 引用。</span><span class="sxs-lookup"><span data-stu-id="6ed01-236">This method takes a content-type, and the `IInputStream` reference.</span></span>  <span data-ttu-id="6ed01-237">然后，该方法验证传入的流引用是一个类型实例，如果没有， `IInputStream` 则引发 `DOMException TYPE_MISMATCH_ERR` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-237">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span>  <span data-ttu-id="6ed01-238">如果未发生错误，则 `createStreamFromInputStream` 从 `MSStream` (\) 创建 \) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-238">If no error occurs, `createStreamFromInputStream` creates an `MSStream` \(from its inputs\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-239">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-239">Example</span></span>**  
      
      <span data-ttu-id="6ed01-240">An `IInputStream` can be used to create an `MSStream` .</span><span class="sxs-lookup"><span data-stu-id="6ed01-240">An `IInputStream` can be used to create an `MSStream`.</span></span>  <span data-ttu-id="6ed01-241">与本质上一次使用的对象一样，第一次由图像元素解析时将吊销创建的所有 `MSStreams` `URL.createObjectURL` URL。</span><span class="sxs-lookup"><span data-stu-id="6ed01-241">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span>  <span data-ttu-id="6ed01-242">此外，使用流后，对此对象的第二个 URL 的请求将失败。</span><span class="sxs-lookup"><span data-stu-id="6ed01-242">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>  
      
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

### <span data-ttu-id="6ed01-243">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="6ed01-243">execAsyncAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-244">根据给定的优先级安排稍后执行的回调。</span><span class="sxs-lookup"><span data-stu-id="6ed01-244">Schedules a callback to be executed at a later time according to the given priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-245">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-245">Parameters</span></span>**  
      
      `asynchronousCallback` <span data-ttu-id="6ed01-246">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-246">[in]</span></span>
      
      | <span data-ttu-id="6ed01-247">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-247">Type</span></span> | <span data-ttu-id="6ed01-248">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-248">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-249">函数</span><span class="sxs-lookup"><span data-stu-id="6ed01-249">Function</span></span> | <span data-ttu-id="6ed01-250">异步运行的回调函数，以给定优先级调度。</span><span class="sxs-lookup"><span data-stu-id="6ed01-250">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>  |  
      
      `priority` <span data-ttu-id="6ed01-251">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-251">[in]</span></span>
      
      | <span data-ttu-id="6ed01-252">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-252">Type</span></span> | <span data-ttu-id="6ed01-253">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-253">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-254">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-254">DOMString</span></span> | <span data-ttu-id="6ed01-255">运行 asynchronousCallback 回调的上下文优先级值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-255">The contextual priority value at which the asynchronousCallback callback is run.</span></span>  <span data-ttu-id="6ed01-256">请参阅 [MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="6ed01-256">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="6ed01-257">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-257">[in]</span></span>
      
      | <span data-ttu-id="6ed01-258">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-258">Type</span></span> | <span data-ttu-id="6ed01-259">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-259">Description</span></span> |  
      |:---- |:--- |   
      | <span data-ttu-id="6ed01-260">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-260">Any</span></span> | <span data-ttu-id="6ed01-261">作为参数 1 等传递给同步Callback 回调函数 \ (的可选一系列参数\) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-261">An optional series of arguments that are passed to the synchronousCallback callback function \(as parameters 1 and so on\).</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-262">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-262">Return value</span></span>**  
      
      <span data-ttu-id="6ed01-263">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-263">This method does not return a value.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-264">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-264">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-265">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-265">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-266">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-266">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-267">提供的 `asynchronousCallback` 回调函数稍后异步执行。</span><span class="sxs-lookup"><span data-stu-id="6ed01-267">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span>  `asynchronousCallback` <span data-ttu-id="6ed01-268">将按照提供的优先级调度。</span><span class="sxs-lookup"><span data-stu-id="6ed01-268">will be dispatched according to the provided priority.</span></span>  <span data-ttu-id="6ed01-269">普通优先级等效于现有的 [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。</span><span class="sxs-lookup"><span data-stu-id="6ed01-269">Normal priority is equivalent to the existing [setImmediate](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span>  <span data-ttu-id="6ed01-270">当回调运行时，当前上下文优先级将设置为在执行回调期间提供的优先级参数值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-270">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>  
      
      <span data-ttu-id="6ed01-271">回调 `asynchronousCallback` 参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-271">The `asynchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="6ed01-272">如果参数在参数 `priority` 之后提供，则所有参数都将传递给回调函数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-272">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>  
      
      <span data-ttu-id="6ed01-273">与回调函数返回的任何对象不同，将忽略 `execAtPriority` `asynchronousCallback` \ (，并且不会通过 `execAsyncAtPriority` \) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-273">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored \(and not returned via `execAsyncAtPriority`\).</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-274">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-274">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

### <span data-ttu-id="6ed01-275">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="6ed01-275">execAtPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-276">以给定的上下文优先级运行指定的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-276">Runs the specified callback function at the given contextual priority.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-277">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-277">Parameters</span></span>**  
      
      `synchronousCallback` <span data-ttu-id="6ed01-278">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-278">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-279">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-279">Type</span></span> | <span data-ttu-id="6ed01-280">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-280">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-281">函数</span><span class="sxs-lookup"><span data-stu-id="6ed01-281">Function</span></span> | <span data-ttu-id="6ed01-282">要以给定优先级上下文优先级同步运行的回调函数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-282">The callback function to run synchronously at the given priority contextual priority.</span></span>  |  
      
      `priority` <span data-ttu-id="6ed01-283">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-283">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-284">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-284">Type</span></span> | <span data-ttu-id="6ed01-285">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-285">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-286">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-286">DOMString</span></span> | <span data-ttu-id="6ed01-287">运行回调函数时，当前上下文优先级值将设置为的指定 `synchronousCallback` 优先级值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-287">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span>  <span data-ttu-id="6ed01-288">请参阅 [MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="6ed01-288">See [MSApp Constants](#msapp-constants).</span></span>  |  
      
      `args` <span data-ttu-id="6ed01-289">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-289">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-290">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-290">Type</span></span> | <span data-ttu-id="6ed01-291">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-291">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-292">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-292">Any</span></span> | <span data-ttu-id="6ed01-293">作为参数 1 等传递给回调函数 \ (的可选系列参数 `synchronousCallback` \) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-293">An optional series of arguments that are passed to the `synchronousCallback` callback function \(as parameters 1 and so on\).</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-294">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-294">Return value</span></span>**  
      
      | <span data-ttu-id="6ed01-295">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-295">Type</span></span> | <span data-ttu-id="6ed01-296">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-296">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-297">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-297">Any</span></span> | <span data-ttu-id="6ed01-298">返回回调 `synchronousCallback` \ (的返回值（如果适用\) ）。</span><span class="sxs-lookup"><span data-stu-id="6ed01-298">Returns the return value of the `synchronousCallback` callback \(as applicable\).</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-299">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-299">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-300">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-300">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-301">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-301">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-302">提供的 `synchronousCallback` 回调方法将同步执行。</span><span class="sxs-lookup"><span data-stu-id="6ed01-302">The provided `synchronousCallback` callback method is execute synchronously.</span></span>  <span data-ttu-id="6ed01-303">当前上下文优先级更改为在提供的回调 (期间由优先级参数) 给定的优先级值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-303">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span>  <span data-ttu-id="6ed01-304">一旦回调函数完成执行，优先级将返回到调用之前的 `execAtPriority` 上一个值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-304">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span>  <span data-ttu-id="6ed01-305">返回值 `execAtPriority` 是回调方法 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-305">The return value from `execAtPriority` is the return value of the callback method \(as provided\).</span></span>  
      
      <span data-ttu-id="6ed01-306">回调 `synchronousCallback` 参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="6ed01-306">The `synchronousCallback` callback parameter can be any function.</span></span>  <span data-ttu-id="6ed01-307">如果在优先级参数之后提供了任何参数，则这些参数将传递给提供的回调方法。</span><span class="sxs-lookup"><span data-stu-id="6ed01-307">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span>  <span data-ttu-id="6ed01-308">如果回调参数返回值，则此值也将成为返回 `execAtPriority` 值。</span><span class="sxs-lookup"><span data-stu-id="6ed01-308">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-309">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-309">Example</span></span>**  
      
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

### <span data-ttu-id="6ed01-310">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="6ed01-310">getCurrentPriority</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-311">返回当前上下文优先级。</span><span class="sxs-lookup"><span data-stu-id="6ed01-311">Returns the current contextual priority.</span></span>  

   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getCurrentPriority();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-312">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-312">Parameters</span></span>**  
      
      <span data-ttu-id="6ed01-313">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-313">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-314">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-314">Return value</span></span>**  
      
      | <span data-ttu-id="6ed01-315">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-315">Type</span></span> | <span data-ttu-id="6ed01-316">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-316">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-317">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-317">DOMString</span></span> | <span data-ttu-id="6ed01-318">返回值是字符串之一 `MSApp.HIGH` ，或 `MSApp.NORMAL` `MSApp.IDLE` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-318">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-319">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-319">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-320">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-320">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-321">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-321">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-322">此方法返回当前的上下文优先级 \ (，请参阅 [MSApp 常量](#msapp-constants)\) ，可通过 `execAtPriority` 和 进行更改 `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-322">This method returns the current contextual priority \(see [MSApp Constants](#msapp-constants)\), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-323">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-323">Example</span></span>**  
      
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

### <span data-ttu-id="6ed01-324">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="6ed01-324">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="6ed01-325">已弃用同步 API。</span><span class="sxs-lookup"><span data-stu-id="6ed01-325">Synchronous API that has been deprecated.</span></span>  <span data-ttu-id="6ed01-326">对于 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-326">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span>  <span data-ttu-id="6ed01-327">对于 Windows 8 和 8.1 应用，请参阅 [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。</span><span class="sxs-lookup"><span data-stu-id="6ed01-327">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <span data-ttu-id="6ed01-328">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="6ed01-328">getHtmlPrintDocumentSourceAsync</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-329">返回要打印的源内容。</span><span class="sxs-lookup"><span data-stu-id="6ed01-329">Returns the source content that is to be printed.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.getHtmlPrintDocumentSourceAsync(document);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-330">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-330">Parameters</span></span>**  
      
      `htmlDoc` <span data-ttu-id="6ed01-331">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-331">[in]</span></span>  
      
      | <span data-ttu-id="6ed01-332">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-332">Type</span></span> | <span data-ttu-id="6ed01-333">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-333">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-334">文档</span><span class="sxs-lookup"><span data-stu-id="6ed01-334">Document</span></span> | <span data-ttu-id="6ed01-335">要打印的 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="6ed01-335">The HTML document to be printed.</span></span>  <span data-ttu-id="6ed01-336">它可以是根文档、iframe 中的文档、文档片段或 SVG 文档。</span><span class="sxs-lookup"><span data-stu-id="6ed01-336">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span>  <span data-ttu-id="6ed01-337">请注意，htmlDoc 必须是文档，而不是元素。</span><span class="sxs-lookup"><span data-stu-id="6ed01-337">Be aware that htmlDoc must be a document, not an element.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-338">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-338">Return value</span></span>**
      
      <span data-ttu-id="6ed01-339">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-339">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-340">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-340">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-341">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-341">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-342">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-342">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-343">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-343">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-344">示例 1</span><span class="sxs-lookup"><span data-stu-id="6ed01-344">Example 1</span></span>**  
      
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
      **<span data-ttu-id="6ed01-345">示例 2</span><span class="sxs-lookup"><span data-stu-id="6ed01-345">Example 2</span></span>**  
      
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

### <span data-ttu-id="6ed01-346">getViewId</span><span class="sxs-lookup"><span data-stu-id="6ed01-346">getViewId</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-347">支持多个窗口。</span><span class="sxs-lookup"><span data-stu-id="6ed01-347">Support for multiple windows.</span></span>  
      
      > [!NOTE] 
      > <span data-ttu-id="6ed01-348">在 Win8.1 中，JavaScript UWP 应用支持使用 MSApp DOM API 的多个窗口，这些 API 现已弃用。</span><span class="sxs-lookup"><span data-stu-id="6ed01-348">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span>  <span data-ttu-id="6ed01-349">对于 Windows 10，请使用 `window.open` 、 `window` 和新的 `MSApp.getViewId` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-349">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>  
      
      | <span data-ttu-id="6ed01-350">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-350">Description</span></span> |<span data-ttu-id="6ed01-351">Windows 10</span><span class="sxs-lookup"><span data-stu-id="6ed01-351">Windows 10</span></span> | <span data-ttu-id="6ed01-352">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="6ed01-352">Windows 8.1</span></span> |  
      |:---- |:---- |:--- |  
      | <span data-ttu-id="6ed01-353">创建新窗口</span><span class="sxs-lookup"><span data-stu-id="6ed01-353">Create new window</span></span> | [<span data-ttu-id="6ed01-354">window.open</span><span class="sxs-lookup"><span data-stu-id="6ed01-354">window.open</span></span>](https://developer.mozilla.org/docs/Web/API/Window/open) | [<span data-ttu-id="6ed01-355">MSApp.createNewView</span><span class="sxs-lookup"><span data-stu-id="6ed01-355">MSApp.createNewView</span></span>](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
      |<span data-ttu-id="6ed01-356">新窗口对象</span><span class="sxs-lookup"><span data-stu-id="6ed01-356">New window object</span></span> | [<span data-ttu-id="6ed01-357">窗口</span><span class="sxs-lookup"><span data-stu-id="6ed01-357">window</span></span>](https://developer.mozilla.org/docs/Web/API/Window) |[<span data-ttu-id="6ed01-358">MSAppView</span><span class="sxs-lookup"><span data-stu-id="6ed01-358">MSAppView</span></span>](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.getViewId(window); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-359">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-359">Parameters</span></span>**  
      
      `window`
      
      | <span data-ttu-id="6ed01-360">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-360">Type</span></span> | <span data-ttu-id="6ed01-361">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-361">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-362">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-362">DOMString</span></span> | <span data-ttu-id="6ed01-363">一个代表包含 DOM 文档的窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="6ed01-363">An object representing a window containing a DOM document.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-364">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-364">Return value</span></span>**  
      
      `viewId`
      
      | <span data-ttu-id="6ed01-365">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-365">Type</span></span> | <span data-ttu-id="6ed01-366">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-366">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-367">数字</span><span class="sxs-lookup"><span data-stu-id="6ed01-367">Number</span></span> | <span data-ttu-id="6ed01-368">可以与各种 [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 一起使用。</span><span class="sxs-lookup"><span data-stu-id="6ed01-368">Can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-369">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-369">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-370">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-370">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-371">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-371">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-372">使用 [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) 和 [window](https://developer.mozilla.org/docs/Web/API/Window) 创建新窗口，但随后要与 WinRT API 交互，请添加 `MSApp.getViewId` API。</span><span class="sxs-lookup"><span data-stu-id="6ed01-372">Use [window.open](https://developer.mozilla.org/docs/Web/API/Window/open) and [window](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span>  <span data-ttu-id="6ed01-373">它将对象 `window` 作为参数，并返回可用于各种 `viewId` [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) API 的编号。</span><span class="sxs-lookup"><span data-stu-id="6ed01-373">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [Windows.UI.ViewManagement.ApplicationViewSwitcher](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span>  
      
      *   <span data-ttu-id="6ed01-374">延迟可见性</span><span class="sxs-lookup"><span data-stu-id="6ed01-374">Delaying Visibility</span></span>  
          
          <span data-ttu-id="6ed01-375">WinRT 中的视图通常开始隐藏，并且最终开发人员使用类似方法在视图完全准备好 `TryShowAsStandaloneAsync` 后显示视图。</span><span class="sxs-lookup"><span data-stu-id="6ed01-375">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span>  <span data-ttu-id="6ed01-376">在 Web 中，立即显示一个窗口，最终用户可以 `window.open` 监视内容加载和呈现。</span><span class="sxs-lookup"><span data-stu-id="6ed01-376">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span>  <span data-ttu-id="6ed01-377">若要让新窗口像 WinRT 中的视图一样运行，并且不会立即显示，我们添加了 `window.open` 一个选项。</span><span class="sxs-lookup"><span data-stu-id="6ed01-377">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span>  <span data-ttu-id="6ed01-378">例如：</span><span class="sxs-lookup"><span data-stu-id="6ed01-378">For example:</span></span>  
          
          ```javascript
          let newWindow = window.open("https://example.com", null, "msHideView=yes");
          ```  
          
      *   <span data-ttu-id="6ed01-379">主窗口差异</span><span class="sxs-lookup"><span data-stu-id="6ed01-379">Primary Window Differences</span></span>  
          
          <span data-ttu-id="6ed01-380">操作系统最初打开的主窗口的行为不同于它打开的辅助窗口：</span><span class="sxs-lookup"><span data-stu-id="6ed01-380">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span>  
          
          | <span data-ttu-id="6ed01-381">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-381">Description</span></span> | <span data-ttu-id="6ed01-382">主要</span><span class="sxs-lookup"><span data-stu-id="6ed01-382">Primary</span></span> | <span data-ttu-id="6ed01-383">辅助边框</span><span class="sxs-lookup"><span data-stu-id="6ed01-383">Secondary</span></span> |  
          |:---- |:--- |:--- |  
          | <span data-ttu-id="6ed01-384">window.open</span><span class="sxs-lookup"><span data-stu-id="6ed01-384">window.open</span></span> | <span data-ttu-id="6ed01-385">允许</span><span class="sxs-lookup"><span data-stu-id="6ed01-385">Allowed</span></span> | <span data-ttu-id="6ed01-386">不允许</span><span class="sxs-lookup"><span data-stu-id="6ed01-386">Disallowed</span></span> |  
          | <span data-ttu-id="6ed01-387">window.close</span><span class="sxs-lookup"><span data-stu-id="6ed01-387">window.close</span></span> | <span data-ttu-id="6ed01-388">关闭应用</span><span class="sxs-lookup"><span data-stu-id="6ed01-388">Close app</span></span> | <span data-ttu-id="6ed01-389">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="6ed01-389">Close window</span></span> |  
          | <span data-ttu-id="6ed01-390">导航限制</span><span class="sxs-lookup"><span data-stu-id="6ed01-390">Navigation restrictions</span></span> | <span data-ttu-id="6ed01-391">仅 ACUR</span><span class="sxs-lookup"><span data-stu-id="6ed01-391">ACUR only</span></span> | <span data-ttu-id="6ed01-392">无限制</span><span class="sxs-lookup"><span data-stu-id="6ed01-392">No restrictions</span></span> |  
          
          <span data-ttu-id="6ed01-393">不允许打开辅助窗口的限制可能会在将来根据反馈 [而更改](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。</span><span class="sxs-lookup"><span data-stu-id="6ed01-393">The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).</span></span>  
      
      *   <span data-ttu-id="6ed01-394">同源通信限制</span><span class="sxs-lookup"><span data-stu-id="6ed01-394">Same Origin Communication Restrictions</span></span>  
          
          <span data-ttu-id="6ed01-395">存在一个难以解决的技术问题，即无法正确支持同步、同源、跨窗口、脚本调用。</span><span class="sxs-lookup"><span data-stu-id="6ed01-395">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span>  <span data-ttu-id="6ed01-396">打开同一个源的窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。</span><span class="sxs-lookup"><span data-stu-id="6ed01-396">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span>  `postMessage` <span data-ttu-id="6ed01-397">调用可以正常工作，并且建议尽可能执行一些操作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-397">calls work just fine and is the recommended way to do things if possible.</span></span>  <span data-ttu-id="6ed01-398">正在努力改进此问题。</span><span class="sxs-lookup"><span data-stu-id="6ed01-398">Work to improve this issue is in progress.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-399">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-399">Example</span></span>**  
      
      ```javascript
      ```   
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
    
### <span data-ttu-id="6ed01-400">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="6ed01-400">isTaskScheduledAtPriorityOrHigher</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-401">返回一个布尔 值，该值指示在给定优先级级别还是更高优先级存在挂起的工作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-401">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-402">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-402">Parameters</span></span>**  
      
      `priority` <span data-ttu-id="6ed01-403">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-403">[in]</span></span>
      
      | <span data-ttu-id="6ed01-404">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-404">Type</span></span> | <span data-ttu-id="6ed01-405">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-405">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-406">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-406">DOMString</span></span> | <span data-ttu-id="6ed01-407">优先级值 \ (请参阅 [MSApp 常量](#msapp-constants)\) 指定优先级级别及以上以查询任何未完成的排队工作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-407">A priority value \(see [MSApp Constants](#msapp-constants)\) specifying the priority level and above to query for any outstanding queued work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-408">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-408">Return value</span></span>**  
      
      | <span data-ttu-id="6ed01-409">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-409">Type</span></span> | <span data-ttu-id="6ed01-410">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-410">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-411">布尔</span><span class="sxs-lookup"><span data-stu-id="6ed01-411">Boolean</span></span> | <span data-ttu-id="6ed01-412">返回 `true` 指定优先级或高于指定优先级的任何排队工作， `false` 否则返回。</span><span class="sxs-lookup"><span data-stu-id="6ed01-412">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-413">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-413">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-414">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-414">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-415">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-415">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-416">此方法为 JavaScript 代码提供了一种方法，用于确定各个优先级 `isTaskScheduledAtPriorityOrHigher` 级别 \ (或更高版本\) 是否有挂起的工作，目的是调用 JavaScript 代码随后可以决定获得更高优先级的工作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-416">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels \(or above\) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-417">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-417">Example</span></span>**  
      
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

### <span data-ttu-id="6ed01-418">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="6ed01-418">pageHandlesAllApplicationActivations</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-419">用于避免刷新启动路径 (页面重新加载) 每个激活事件 \ (例如单击通知或固定磁贴\) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-419">Used to avoid a refresh of the start path (page reload) before every activate event \(such as clicking a notification or a pinned tile\).</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.pageHandlesAllApplicationActivations(boolean);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-420">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-420">Parameters</span></span>**  
      
      | <span data-ttu-id="6ed01-421">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-421">Type</span></span> | <span data-ttu-id="6ed01-422">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-422">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-423">布尔</span><span class="sxs-lookup"><span data-stu-id="6ed01-423">Boolean</span></span> | <span data-ttu-id="6ed01-424">用于 `MSApp.pageHandlesAllApplicationActivations(true)` 始终跳过刷新页面重新加载 (路径，) 直接跳转到触发 `WebUIApplication` 激活的事件。</span><span class="sxs-lookup"><span data-stu-id="6ed01-424">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span>  <span data-ttu-id="6ed01-425">要求所有页面单独处理激活事件。</span><span class="sxs-lookup"><span data-stu-id="6ed01-425">Requires that all pages handle activation events separately.</span></span>  <span data-ttu-id="6ed01-426">将此方法定义为，单击激活的事件 `true` \ (如 notification\) 不会触发重新加载，这是单页应用避免重新加载页面的必备条件。</span><span class="sxs-lookup"><span data-stu-id="6ed01-426">By defining this method as `true`, clicking an activated event \(like a notification\) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-427">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-427">Return value</span></span>**
      
      <span data-ttu-id="6ed01-428">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-428">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-429">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-429">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-430">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-430">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-431">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-431">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-432">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-432">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-433">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-433">Example</span></span>**  
      
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

### <span data-ttu-id="6ed01-434">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="6ed01-434">suppressSubdownloadCredentialPrompts</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-435">控制应用是否在下载资源期间禁止可能的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="6ed01-435">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.suppressSubdownloadCredentialPrompts(suppress);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-436">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-436">Parameters</span></span>**  
     
      `suppress` <span data-ttu-id="6ed01-437">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-437">[in]</span></span>
      
      | <span data-ttu-id="6ed01-438">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-438">Type</span></span> | <span data-ttu-id="6ed01-439">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-439">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-440">布尔</span><span class="sxs-lookup"><span data-stu-id="6ed01-440">Boolean</span></span> | <span data-ttu-id="6ed01-441">如果值为 true，则禁止潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="6ed01-441">A value of true suppresses potential authentication prompts.</span></span>  <span data-ttu-id="6ed01-442">值为 false 不会禁止用户的任何潜在身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="6ed01-442">A value of false does not suppress any potential authentication prompts from the user.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-443">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-443">Return value</span></span>**  
      
      <span data-ttu-id="6ed01-444">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-444">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-445">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-445">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-446">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-446">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-447">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-447">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-448">该方法控制应用程序在下载资源期间是否禁止 `suppressSubdownloadCredentialPrompts` 潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="6ed01-448">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span>  <span data-ttu-id="6ed01-449">默认行为是禁止显示凭据提示。</span><span class="sxs-lookup"><span data-stu-id="6ed01-449">The default behavior is to not suppress credential prompts.</span></span>  
      
      `suppressSubdownloadCredentialPrompts` <span data-ttu-id="6ed01-450">供可能加载大量需要身份验证的资源的应用程序使用，例如邮件应用程序 \ (其中可能包含一个新闻稿，其中包含许多图像，其中每个图像都需要身份验证\) 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-450">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app \(which could contain a newsletter containing a number of images where each image requires authentication\).</span></span>  
      
      <span data-ttu-id="6ed01-451">在禁止显示凭据提示时，在访问需要身份验证的资源时，将不会显示用于向服务器进行身份验证的对话框，并且不会下载资源。</span><span class="sxs-lookup"><span data-stu-id="6ed01-451">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span>  <span data-ttu-id="6ed01-452">请注意 `suppressSubdownloadCredentialPrompts` ，这不会影响其他可能的提示，如代理身份验证或客户端认证请求对话框，也不会影响 XHR。</span><span class="sxs-lookup"><span data-stu-id="6ed01-452">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>  
      
      <span data-ttu-id="6ed01-453">请注意， `suppressSubdownloadCredentialPrompts` 这会影响应用程序内的所有内容，包括元素中托管 `webview` 的内容。</span><span class="sxs-lookup"><span data-stu-id="6ed01-453">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>  
      
      > [!IMPORTANT]
      > <span data-ttu-id="6ed01-454">将缓存凭据提示决策。</span><span class="sxs-lookup"><span data-stu-id="6ed01-454">Credential prompt decisions are cached.</span></span>  <span data-ttu-id="6ed01-455">因此，在禁止显示凭据提示时将立即生效，在禁止显示凭据提示后允许凭据提示可能需要重新加载文档以生效。</span><span class="sxs-lookup"><span data-stu-id="6ed01-455">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-456">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-456">Example</span></span>**  
      
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

### <span data-ttu-id="6ed01-457">terminateApp</span><span class="sxs-lookup"><span data-stu-id="6ed01-457">terminateApp</span></span>  


:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-458">终止当前应用程序并生成故障报告。</span><span class="sxs-lookup"><span data-stu-id="6ed01-458">Terminates the current application and generates a failure report.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      MSApp.terminateApp(error);
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-459">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-459">Parameters</span></span>**  
      
      `error` <span data-ttu-id="6ed01-460">[in]</span><span class="sxs-lookup"><span data-stu-id="6ed01-460">[in]</span></span>
      
      | <span data-ttu-id="6ed01-461">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-461">Type</span></span> | <span data-ttu-id="6ed01-462">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-462">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-463">错误</span><span class="sxs-lookup"><span data-stu-id="6ed01-463">Error</span></span> | <span data-ttu-id="6ed01-464">`Error`可用于描述触发终止的错误的对象。</span><span class="sxs-lookup"><span data-stu-id="6ed01-464">An `Error` object that you can use to describe the error that triggered the termination.</span></span>  <span data-ttu-id="6ed01-465">对象必须包含数字、说明和堆栈属性;如果对象不包含这些属性，则不生成 `Error` 故障报告。</span><span class="sxs-lookup"><span data-stu-id="6ed01-465">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-466">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-466">Return value</span></span>**
      
      <span data-ttu-id="6ed01-467">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-467">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-468">异常</span><span class="sxs-lookup"><span data-stu-id="6ed01-468">Exceptions</span></span>**  
      
      <span data-ttu-id="6ed01-469">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-469">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-470">备注</span><span class="sxs-lookup"><span data-stu-id="6ed01-470">Remarks</span></span>**  
      
      <span data-ttu-id="6ed01-471">如果报告的问题成为应用的前 5 个问题之一，它将显示在应用的"质量 `terminateApp` "页上。</span><span class="sxs-lookup"><span data-stu-id="6ed01-471">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-472">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-472">Example</span></span>**  
      
      <span data-ttu-id="6ed01-473">此示例在 `terminateApp` 遇到异常时调用。</span><span class="sxs-lookup"><span data-stu-id="6ed01-473">This example calls `terminateApp` when an exception is encountered.</span></span>  <span data-ttu-id="6ed01-474">它使用 `Error` 捕获异常时提供的对象。</span><span class="sxs-lookup"><span data-stu-id="6ed01-474">It uses the `Error` object provided when you catch an exception.</span></span>  
      
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

### <span data-ttu-id="6ed01-475">MSApp 常量</span><span class="sxs-lookup"><span data-stu-id="6ed01-475">MSApp Constants</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-476">允许的优先级值与 `execAsyncAtPriority` 、 `execAtPriority` 和 `getCurrentPriority` 相关联 `isTaskScheduldAtPriorityOrHigher` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-476">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="6ed01-477">当前</span><span class="sxs-lookup"><span data-stu-id="6ed01-477">Current</span></span>  
      
      `current`  
      
      | <span data-ttu-id="6ed01-478">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-478">Type</span></span> | <span data-ttu-id="6ed01-479">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-479">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-480">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-480">DOMString</span></span> | <span data-ttu-id="6ed01-481">当 `current` 与适当的方法 \ (See also section\) ， the method will use the current contextual priority when executing the requested operation.</span><span class="sxs-lookup"><span data-stu-id="6ed01-481">When `current` is used with the appropriate method \(See also section\), the method will use the current contextual priority when executing the requested operation.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="6ed01-482">高 </span><span class="sxs-lookup"><span data-stu-id="6ed01-482">High</span></span>  
      
      `high`  
      
      | <span data-ttu-id="6ed01-483">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-483">Type</span></span> | <span data-ttu-id="6ed01-484">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-484">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-485">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-485">DOMString</span></span> | <span data-ttu-id="6ed01-486">当与适当的方法 `high` \ (See also section\) 一起使用时，该方法在执行请求的操作时将使用高于正常优先级，并且将在任何现有的普通优先级工作之前调度该操作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-486">When `high` is used with the appropriate method \(See also section\), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>  |  
   :::column-end:::
   :::column span="":::
      #### <span data-ttu-id="6ed01-487">Idle</span><span class="sxs-lookup"><span data-stu-id="6ed01-487">Idle</span></span>  
      
      `idle`  
      
      | <span data-ttu-id="6ed01-488">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-488">Type</span></span> | <span data-ttu-id="6ed01-489">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-489">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-490">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-490">DOMString</span></span> | <span data-ttu-id="6ed01-491">当与适当的方法 `ideal` \ (See also section\) 一起使用时，该方法在执行请求的操作时将使用低于正常优先级，并且将在任何现有的普通优先级工作后调度该操作。</span><span class="sxs-lookup"><span data-stu-id="6ed01-491">When `ideal` is used with the appropriate method \(See also section\), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>  |  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      #### <span data-ttu-id="6ed01-492">正常</span><span class="sxs-lookup"><span data-stu-id="6ed01-492">Normal</span></span>  
      
      `normal`  
      
      | <span data-ttu-id="6ed01-493">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-493">Type</span></span> | <span data-ttu-id="6ed01-494">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-494">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-495">DOMString</span><span class="sxs-lookup"><span data-stu-id="6ed01-495">DOMString</span></span> | <span data-ttu-id="6ed01-496">当与适当的方法一 (另请参阅) ，该方法将在执行请求的操作时使用正常的现有 `normal` 优先级。</span><span class="sxs-lookup"><span data-stu-id="6ed01-496">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>  |  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-497">示例</span><span class="sxs-lookup"><span data-stu-id="6ed01-497">Example</span></span>**  
      
      ```javascript
      if (window.MSApp.CURRENT) {
          document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
      }
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-498">要求</span><span class="sxs-lookup"><span data-stu-id="6ed01-498">Requirements</span></span>**  
      
      | <span data-ttu-id="6ed01-499">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-499">Type</span></span> | <span data-ttu-id="6ed01-500">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-500">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-501">IDL</span><span class="sxs-lookup"><span data-stu-id="6ed01-501">IDL</span></span> | <span data-ttu-id="6ed01-502">Mshtml.idl</span><span class="sxs-lookup"><span data-stu-id="6ed01-502">Mshtml.idl</span></span> |  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  

## <span data-ttu-id="6ed01-503">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="6ed01-503">MSAppAsyncOperation</span></span>  

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```  

### <span data-ttu-id="6ed01-504">start</span><span class="sxs-lookup"><span data-stu-id="6ed01-504">start</span></span>  

:::row:::
   :::column span="":::
      <span data-ttu-id="6ed01-505">启动 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-505">Starts the `MSAppAsyncOperation`.</span></span>  
   :::column-end:::
   :::column span="":::
      ```javascript
      var retval = MSAppAsyncOperation.start();
      ```  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      **<span data-ttu-id="6ed01-506">参数</span><span class="sxs-lookup"><span data-stu-id="6ed01-506">Parameters</span></span>**  
      
      <span data-ttu-id="6ed01-507">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-507">None.</span></span>  
   :::column-end:::
   :::column span="":::
      **<span data-ttu-id="6ed01-508">返回值</span><span class="sxs-lookup"><span data-stu-id="6ed01-508">Return value</span></span>**
      
      <span data-ttu-id="6ed01-509">无。</span><span class="sxs-lookup"><span data-stu-id="6ed01-509">None.</span></span>  
   :::column-end:::
:::row-end:::  
:::row:::
   :::column span="":::
      
      **<span data-ttu-id="6ed01-510">属性</span><span class="sxs-lookup"><span data-stu-id="6ed01-510">Properties</span></span>**  
      
      `error` <span data-ttu-id="6ed01-511">property</span><span class="sxs-lookup"><span data-stu-id="6ed01-511">property</span></span>  
      
      | <span data-ttu-id="6ed01-512">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-512">Type</span></span> | <span data-ttu-id="6ed01-513">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-513">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-514">DOMError</span><span class="sxs-lookup"><span data-stu-id="6ed01-514">DOMError</span></span> | <span data-ttu-id="6ed01-515">表示中的错误 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-515">Represents an error in `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.error
      ```  
      
      `oncomplete` <span data-ttu-id="6ed01-516">property</span><span class="sxs-lookup"><span data-stu-id="6ed01-516">property</span></span>  
      
      | <span data-ttu-id="6ed01-517">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-517">Type</span></span> | <span data-ttu-id="6ed01-518">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-518">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-519">EventHandler</span><span class="sxs-lookup"><span data-stu-id="6ed01-519">EventHandler</span></span> | <span data-ttu-id="6ed01-520">属性，用于设置完成时的事件处理程序 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-520">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.oncomplete
      ```  
      
      `onerror` <span data-ttu-id="6ed01-521">property</span><span class="sxs-lookup"><span data-stu-id="6ed01-521">property</span></span>  
      
      | <span data-ttu-id="6ed01-522">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-522">Type</span></span> | <span data-ttu-id="6ed01-523">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-523">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-524">EventHandler</span><span class="sxs-lookup"><span data-stu-id="6ed01-524">EventHandler</span></span> | <span data-ttu-id="6ed01-525">属性，用于设置错误期间的事件处理程序 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="6ed01-525">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.onerror
      ```  
      
      `readyState` <span data-ttu-id="6ed01-526">property</span><span class="sxs-lookup"><span data-stu-id="6ed01-526">property</span></span>  
      
      | <span data-ttu-id="6ed01-527">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-527">Type</span></span> | <span data-ttu-id="6ed01-528">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-528">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-529">数字</span><span class="sxs-lookup"><span data-stu-id="6ed01-529">Number</span></span> | <span data-ttu-id="6ed01-530">表示使用 JavaScript 的 Windows 应用中异步操作的状态。</span><span class="sxs-lookup"><span data-stu-id="6ed01-530">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span>  <span data-ttu-id="6ed01-531">值包括： `Started[0]` ， `Completed[1]` 。 `Error[2]`</span><span class="sxs-lookup"><span data-stu-id="6ed01-531">Values include: `Started[0]`, `Completed[1]`, `Error[2]`.</span></span>  |  
      
      ```javascript
      p = object.readyState
      ```  
      
      `result` <span data-ttu-id="6ed01-532">property</span><span class="sxs-lookup"><span data-stu-id="6ed01-532">property</span></span>  
      
      | <span data-ttu-id="6ed01-533">类型</span><span class="sxs-lookup"><span data-stu-id="6ed01-533">Type</span></span> | <span data-ttu-id="6ed01-534">描述</span><span class="sxs-lookup"><span data-stu-id="6ed01-534">Description</span></span> |  
      |:---- |:--- |  
      | <span data-ttu-id="6ed01-535">Any</span><span class="sxs-lookup"><span data-stu-id="6ed01-535">Any</span></span> |<span data-ttu-id="6ed01-536">表示 `MSAppAsyncOperation` 的结果。</span><span class="sxs-lookup"><span data-stu-id="6ed01-536">Represents the result of `MSAppAsyncOperation`.</span></span>  |  
      
      ```javascript
      p = object.result
      ```  
   :::column-end:::
   :::column span="":::
      &nbsp;  
   :::column-end:::
:::row-end:::  
