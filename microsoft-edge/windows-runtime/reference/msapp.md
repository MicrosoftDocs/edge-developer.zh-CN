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
# <span data-ttu-id="cef79-105">MSApp</span><span class="sxs-lookup"><span data-stu-id="cef79-105">MSApp</span></span>

<span data-ttu-id="cef79-106">只有使用 JavaScript 的 Windows 应用（包括 PWAs 访问 Windows API 功能）才支持 MSApp 对象及其成员。</span><span class="sxs-lookup"><span data-stu-id="cef79-106">The MSApp object and its members are supported only for Windows apps using JavaScript (including PWAs accessing Windows API features).</span></span> <span data-ttu-id="cef79-107">MSApp 对象仅存在于通过 ms-appx URI 方案加载的 Windows 应用中的 HTML 文档的本地上下文中;否则，该对象不存在（因此它的任何方法和属性均不可用）。</span><span class="sxs-lookup"><span data-stu-id="cef79-107">The MSApp object only exists in the local context of an HTML document in a Windows app loaded via the ms-appx URI scheme; otherwise, the object doesn't exist (and consequently, none of its methods and properties are available).</span></span>

<span data-ttu-id="cef79-108">它提供帮助程序函数，使你能够创建[Blob](https://developer.mozilla.org/docs/Web/API/Blob)和[MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx)对象。</span><span class="sxs-lookup"><span data-stu-id="cef79-108">It provides helper functions that enable you to create [Blob](https://developer.mozilla.org/docs/Web/API/Blob) and [MSStream](https://msdn.microsoft.com/library/hh772328(v=vs.85).aspx) objects.</span></span>

```javascript
var result = MSApp.method;
```

| | |
| :--- | :--- |
| [**<span data-ttu-id="cef79-109">方法</span><span class="sxs-lookup"><span data-stu-id="cef79-109">Methods</span></span>**](#msapp-methods) | <span data-ttu-id="cef79-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync)、 [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream)、 [createDataPackage](#createdatapackage)、 [createDataPackageFromSelection](#createdatapackagefromselection)、 [createFileFromStorageFile](#createfilefromstoragefile)、 [createStreamFromInputStream](#createstreamfrominputstream)、 [execAsyncAtPriority](#execasyncatpriority)、 [execAtPriority](#execatpriority)、 [getCurrentPriority](#getcurrentpriority)、 [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource)、[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync)、 [getViewId](#getviewid)、 [isTaskScheduledAtPriorityOrHigher、pageHandlesAllApplicationActivations](#istaskscheduledatpriorityorhigher) [、suppressSubdownloadCredentialPrompts](#pagehandlesallapplicationactivations) [、terminateApp](#suppresssubdownloadcredentialprompts)、、 [、、](#terminateapp)、、。</span><span class="sxs-lookup"><span data-stu-id="cef79-110">[clearTemporaryWebDataAsync](#cleartemporarywebdataasync), [createBlobFromRandomAccessSream](#createblobfromrandomaccessstream), [createDataPackage](#createdatapackage), [createDataPackageFromSelection](#createdatapackagefromselection), [createFileFromStorageFile](#createfilefromstoragefile), [createStreamFromInputStream](#createstreamfrominputstream), [execAsyncAtPriority](#execasyncatpriority), [execAtPriority](#execatpriority), [getCurrentPriority](#getcurrentpriority), [getHtmlPrintDocumentSource](#gethtmlprintdocumentsource),[getHtmlPrintDocumentSourceAsynce](#gethtmlprintdocumentsourceasync), [getViewId](#getviewid), [isTaskScheduledAtPriorityOrHigher](#istaskscheduledatpriorityorhigher), [pageHandlesAllApplicationActivations](#pagehandlesallapplicationactivations), [suppressSubdownloadCredentialPrompts](#suppresssubdownloadcredentialprompts), [terminateApp](#terminateapp).</span></span> |

| | |
| :--- | :--- |
| [**<span data-ttu-id="cef79-111">常量</span><span class="sxs-lookup"><span data-stu-id="cef79-111">Constants</span></span>**](#msapp-constants) | <span data-ttu-id="cef79-112">[当前](#current)、[高](#high)、[空闲](#idle)、[正常](#normal)。</span><span class="sxs-lookup"><span data-stu-id="cef79-112">[current](#current), [high](#high), [idle](#idle), [normal](#normal).</span></span>|

| | |
| :--- | :--- |
| [<span data-ttu-id="cef79-113">**MSAppAsyncOperation**接口</span><span class="sxs-lookup"><span data-stu-id="cef79-113">**MSAppAsyncOperation** interface</span></span>](#msappasyncoperation) | [<span data-ttu-id="cef79-114">start</span><span class="sxs-lookup"><span data-stu-id="cef79-114">start</span></span>](#start) |

## <span data-ttu-id="cef79-115">MSApp 方法</span><span class="sxs-lookup"><span data-stu-id="cef79-115">MSApp Methods</span></span>

### <span data-ttu-id="cef79-116">clearTemporaryWebDataAsync</span><span class="sxs-lookup"><span data-stu-id="cef79-116">clearTemporaryWebDataAsync</span></span> 
<span data-ttu-id="cef79-117">为应用或[Web 视图](../../webview.md)清除缓存和 indexedDB 数据。</span><span class="sxs-lookup"><span data-stu-id="cef79-117">Clears cache and indexedDB data for the app or [WebView](../../webview.md).</span></span>

```javascript
var retval = MSApp.clearTemporaryWebDataAsync(#); 
```

#### <span data-ttu-id="cef79-118">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-118">Parameters</span></span>
<span data-ttu-id="cef79-119">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="cef79-119">This method has no parameters.</span></span>

#### <span data-ttu-id="cef79-120">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-120">Return value</span></span>
<span data-ttu-id="cef79-121">处理器类型[`IAsyncAction`](/uwp/api/windows.foundation.iasyncaction)</span><span class="sxs-lookup"><span data-stu-id="cef79-121">Type: [`IAsyncAction`](/uwp/api/windows.foundation.iasyncaction)</span></span>

<span data-ttu-id="cef79-122">表示一个异步操作。</span><span class="sxs-lookup"><span data-stu-id="cef79-122">Represents an asynchronous action.</span></span>

### <span data-ttu-id="cef79-123">createBlobFromRandomAccessStream</span><span class="sxs-lookup"><span data-stu-id="cef79-123">createBlobFromRandomAccessStream</span></span>
<span data-ttu-id="cef79-124">从对象创建[Blob](https://developer.mozilla.org/docs/Web/API/Blob) [`IRandomAccessStream`](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) 。</span><span class="sxs-lookup"><span data-stu-id="cef79-124">Creates a [Blob](https://developer.mozilla.org/docs/Web/API/Blob) from an [`IRandomAccessStream`](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) object.</span></span> <span data-ttu-id="cef79-125">在处理应用中的对象时，应使用此方法 `IRandomAccessStream` ，以便从流创建基于 W3C 的对象。</span><span class="sxs-lookup"><span data-stu-id="cef79-125">This method should be used when dealing with `IRandomAccessStream` objects in apps in order to create a W3C based object from the stream.</span></span> <span data-ttu-id="cef79-126">创建 blob 后，可以将其与[FileReader](https://developer.mozilla.org/docs/Web/API/FileReader)、 [URL api](https://developer.mozilla.org/docs/Web/API/URL)和[XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest)结合使用。</span><span class="sxs-lookup"><span data-stu-id="cef79-126">Once the blob is created, it can be used with the [FileReader](https://developer.mozilla.org/docs/Web/API/FileReader), [URL APIs](https://developer.mozilla.org/docs/Web/API/URL), and [XMLHttpRequest](https://developer.mozilla.org/docs/Web/API/XMLHttpRequest).</span></span> 

```javascript
var retVal = MSApp.createBlobFromRandomAccessStream(type, stream); 
```

#### <span data-ttu-id="cef79-127">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-127">Parameters</span></span>

`type` <span data-ttu-id="cef79-128">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-128">[in]</span></span>

|<span data-ttu-id="cef79-129">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-129">Type</span></span> | <span data-ttu-id="cef79-130">说明</span><span class="sxs-lookup"><span data-stu-id="cef79-130">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-131">字符串</span><span class="sxs-lookup"><span data-stu-id="cef79-131">String</span></span> | <span data-ttu-id="cef79-132">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="cef79-132">Content type of the data.</span></span> <span data-ttu-id="cef79-133">此字符串应采用 RFC 2616 的3.7 节中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="cef79-133">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span>

`stream` <span data-ttu-id="cef79-134">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-134">[in]</span></span>

|<span data-ttu-id="cef79-135">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-135">Type</span></span> | <span data-ttu-id="cef79-136">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-136">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-137">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-137">Any</span></span> | <span data-ttu-id="cef79-138">要存储在 Blob 中的[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) 。</span><span class="sxs-lookup"><span data-stu-id="cef79-138">[IRandomAccessStream](/uwp/api/Windows.Storage.Streams.IRandomAccessStream) to be stored in the Blob.</span></span>

#### <span data-ttu-id="cef79-139">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-139">Return value</span></span>
|<span data-ttu-id="cef79-140">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-140">Type</span></span> | <span data-ttu-id="cef79-141">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-141">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-142">Blob</span><span class="sxs-lookup"><span data-stu-id="cef79-142">Blob</span></span> | <span data-ttu-id="cef79-143">包含流的新 blob 对象。</span><span class="sxs-lookup"><span data-stu-id="cef79-143">New blob object that contains the stream.</span></span>

#### <span data-ttu-id="cef79-144">异常</span><span class="sxs-lookup"><span data-stu-id="cef79-144">Exceptions</span></span>
|<span data-ttu-id="cef79-145">异常</span><span class="sxs-lookup"><span data-stu-id="cef79-145">Exception</span></span> | <span data-ttu-id="cef79-146">条件</span><span class="sxs-lookup"><span data-stu-id="cef79-146">Condition</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-147">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="cef79-147">TypeMismatchError</span></span> | <span data-ttu-id="cef79-148">节点类型与所需的参数类型不兼容。</span><span class="sxs-lookup"><span data-stu-id="cef79-148">The node type is incompatible with the expected parameter type.</span></span> <span data-ttu-id="cef79-149">对于早于 Internet Explorer 10 的版本，将返回 TYPE_MISMATCH_ERR。</span><span class="sxs-lookup"><span data-stu-id="cef79-149">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>

#### <span data-ttu-id="cef79-150">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-150">Remarks</span></span>
<span data-ttu-id="cef79-151">通过 window 对象上的 MSApp 命名空间创建来自 Windows 运行时类型的 Blob。</span><span class="sxs-lookup"><span data-stu-id="cef79-151">Creates a Blob from Windows Runtime types via the MSApp namespace on the window object.</span></span> <span data-ttu-id="cef79-152">此方法将创建一个 blob，该 blob 实质上是提供给它的对象的轻包装器 [`RandomAccessStream`](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) 。</span><span class="sxs-lookup"><span data-stu-id="cef79-152">This method will create a blob that is essentially a light wrapper over the [`RandomAccessStream`](/uwp/api/Windows.Storage.Streams.RandomAccessStreamReference) object provided to it.</span></span> <span data-ttu-id="cef79-153">Blob 拥有此流的生存期，并且在销毁 blob 时将关闭流。</span><span class="sxs-lookup"><span data-stu-id="cef79-153">The blob owns the lifetime of this stream and the stream will be closed when the blob is destroyed.</span></span> 

#### <span data-ttu-id="cef79-154">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-154">Example</span></span>

```javascript
var randomAccessStream = dataPackage.GetData("image/bmp");
var blob = window.MSApp.createBlobFromRandomAccessStream("image/bmp", randomAccessStream);
var url = window.URL.createObjectURL(blob, {oneTimeOnly:true});

document.getElementById("imagetag").src = url; 
```

### <span data-ttu-id="cef79-155">createDataPackage</span><span class="sxs-lookup"><span data-stu-id="cef79-155">createDataPackage</span></span>
<span data-ttu-id="cef79-156">将用户或应用程序的指定范围转换为可共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="cef79-156">Converts the user's or the application's specified range to an HTML fragment that can be shared.</span></span>

```javascript
var retVal = MSApp.createDataPackage(object); 
```

#### <span data-ttu-id="cef79-157">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-157">Parameters</span></span>
`object` <span data-ttu-id="cef79-158">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-158">[in]</span></span>

|<span data-ttu-id="cef79-159">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-159">Type</span></span> | <span data-ttu-id="cef79-160">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-160">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-161">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-161">Any</span></span> | <span data-ttu-id="cef79-162">可以从选择对象（例如：或手动）创建此范围 `window.selection.getRangeAt(0)` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-162">This range can be created either from a selection object, for example: `window.selection.getRangeAt(0)`, or manually.</span></span>

#### <span data-ttu-id="cef79-163">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-163">Return value</span></span>
|<span data-ttu-id="cef79-164">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-164">Type</span></span> | <span data-ttu-id="cef79-165">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-165">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-166">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-166">Any</span></span> | <span data-ttu-id="cef79-167">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="cef79-167">Contains the HTML markup for the specified range.</span></span>

#### <span data-ttu-id="cef79-168">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-168">Remarks</span></span>
<span data-ttu-id="cef79-169">此方法仅支持[文档对象模型（DOM）范围](https://developer.mozilla.org/docs/Web/API/Range)，而不支持[TextRange](/uwp/api/windows.ui.xaml.documents.textrange)。</span><span class="sxs-lookup"><span data-stu-id="cef79-169">This method supports only [Document Object Model (DOM) Range](https://developer.mozilla.org/docs/Web/API/Range), not [TextRange](/uwp/api/windows.ui.xaml.documents.textrange).</span></span> <span data-ttu-id="cef79-170">针对指定范围返回的数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="cef79-170">The returned data package for the specified range contains HTML markup in clipboard format.</span></span>

<span data-ttu-id="cef79-171">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="cef79-171">There are no available properties for the returned data package.</span></span>

### <span data-ttu-id="cef79-172">createDataPackageFromSelection</span><span class="sxs-lookup"><span data-stu-id="cef79-172">createDataPackageFromSelection</span></span> 
<span data-ttu-id="cef79-173">将用户或应用程序的选定内容转换为可共享的 HTML 片段。</span><span class="sxs-lookup"><span data-stu-id="cef79-173">Converts the user's or the application's selection to an HTML fragment that can be shared.</span></span>

```javascript
var retVal = MSApp.createDataPackageFromSelection(); 
```

#### <span data-ttu-id="cef79-174">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-174">Parameters</span></span>
<span data-ttu-id="cef79-175">此方法没有任何参数。</span><span class="sxs-lookup"><span data-stu-id="cef79-175">This method has no parameters.</span></span>

#### <span data-ttu-id="cef79-176">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-176">Return value</span></span>
|<span data-ttu-id="cef79-177">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-177">Type</span></span> | <span data-ttu-id="cef79-178">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-178">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-179">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-179">Any</span></span> | <span data-ttu-id="cef79-180">包含指定范围的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="cef79-180">Contains the HTML markup for the specified range.</span></span>

#### <span data-ttu-id="cef79-181">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-181">Remarks</span></span>
<span data-ttu-id="cef79-182">所选内容的返回数据包包含剪贴板格式的 HTML 标记。</span><span class="sxs-lookup"><span data-stu-id="cef79-182">The returned data package for the selection contains HTML markup in clipboard format.</span></span> <span data-ttu-id="cef79-183">如果在应用程序的 UI 中的任何位置都没有用户选择，则 `createDataPackageFromSelection` 返回 null。</span><span class="sxs-lookup"><span data-stu-id="cef79-183">If there is no user selection anywhere within the application's UI, the `createDataPackageFromSelection` returns null.</span></span>

<span data-ttu-id="cef79-184">返回的数据包没有可用的属性。</span><span class="sxs-lookup"><span data-stu-id="cef79-184">There are no available properties for the returned data package.</span></span>
 
### <span data-ttu-id="cef79-185">createFileFromStorageFile</span><span class="sxs-lookup"><span data-stu-id="cef79-185">createFileFromStorageFile</span></span> 
<span data-ttu-id="cef79-186">将[WinRT](/uwp/api/)转换 [`StorageFile`](/uwp/api/windows.storage.storagefile) 为标准 W3C [`File`](https://developer.mozilla.org/docs/Web/API/File) 对象。</span><span class="sxs-lookup"><span data-stu-id="cef79-186">Converts a [WinRT](/uwp/api/) [`StorageFile`](/uwp/api/windows.storage.storagefile) to a standard W3C [`File`](https://developer.mozilla.org/docs/Web/API/File) object.</span></span>

```javascript
var retVal = MSApp.createFileFromStorageFile(storageFile); 
```

#### <span data-ttu-id="cef79-187">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-187">Parameters</span></span>
`storageFile` <span data-ttu-id="cef79-188">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-188">[in]</span></span>

|<span data-ttu-id="cef79-189">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-189">Type</span></span> | <span data-ttu-id="cef79-190">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-190">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-191">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-191">Any</span></span> | <span data-ttu-id="cef79-192">包含存储文件。</span><span class="sxs-lookup"><span data-stu-id="cef79-192">Contains the storage file.</span></span>

#### <span data-ttu-id="cef79-193">异常</span><span class="sxs-lookup"><span data-stu-id="cef79-193">Exceptions</span></span>
|<span data-ttu-id="cef79-194">异常</span><span class="sxs-lookup"><span data-stu-id="cef79-194">Exception</span></span> | <span data-ttu-id="cef79-195">条件</span><span class="sxs-lookup"><span data-stu-id="cef79-195">Condition</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-196">TypeMismatchError</span><span class="sxs-lookup"><span data-stu-id="cef79-196">TypeMismatchError</span></span> | <span data-ttu-id="cef79-197">指定的 W3C 文件引用无效。</span><span class="sxs-lookup"><span data-stu-id="cef79-197">The specified W3C file reference is invalid.</span></span> <span data-ttu-id="cef79-198">对于早于 Internet Explorer 10 的版本，将返回 TYPE_MISMATCH_ERR。</span><span class="sxs-lookup"><span data-stu-id="cef79-198">For versions earlier than Internet Explorer 10, TYPE_MISMATCH_ERR is returned.</span></span>

### <span data-ttu-id="cef79-199">createStreamFromInputStream</span><span class="sxs-lookup"><span data-stu-id="cef79-199">createStreamFromInputStream</span></span>  

<span data-ttu-id="cef79-200">从创建 [`MSStream`](https://msdn.microsoft.com/library/hh772328) [`InputStream`](https://msdn.microsoft.com/library/hh772327) 。</span><span class="sxs-lookup"><span data-stu-id="cef79-200">Creates an [`MSStream`](https://msdn.microsoft.com/library/hh772328) from an [`InputStream`](https://msdn.microsoft.com/library/hh772327).</span></span>  


```javascript
var msStream = MSApp.createStreamFromInputStream("image/jpeg", inputStream);
```

#### <span data-ttu-id="cef79-201">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-201">Parameters</span></span>
`type` <span data-ttu-id="cef79-202">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-202">[in]</span></span>

|<span data-ttu-id="cef79-203">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-203">Type</span></span> | <span data-ttu-id="cef79-204">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-204">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-205">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-205">DOMString</span></span> | <span data-ttu-id="cef79-206">数据的内容类型。</span><span class="sxs-lookup"><span data-stu-id="cef79-206">Content type of the data.</span></span> <span data-ttu-id="cef79-207">此字符串应采用 RFC 2616 的3.7 节中定义的媒体类型令牌中指定的格式。</span><span class="sxs-lookup"><span data-stu-id="cef79-207">This string should be in the format specified in the media-type token defined in section 3.7 of RFC 2616.</span></span> <span data-ttu-id="cef79-208">（[请参阅 MIME 类型，例如](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types)文本/纯文本/html、图像/jpeg、图像/png、音频/mpeg、音频/ogg、音频/\*、视频/设备类型等）。</span><span class="sxs-lookup"><span data-stu-id="cef79-208">([See MIME types,](https://developer.mozilla.org/docs/Web/HTTP/Basics_of_HTTP/MIME_types) ie. text/plain, text/html, image/jpeg, image/png, audio/mpeg, audio/ogg, audio/\*, video/mp4, etc.).</span></span> 

`inputStream` <span data-ttu-id="cef79-209">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-209">[in]</span></span>

|<span data-ttu-id="cef79-210">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-210">Type</span></span> | <span data-ttu-id="cef79-211">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-211">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-212">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-212">Any</span></span> | <span data-ttu-id="cef79-213">[`IInputStream`](/uwp/api/Windows.Storage.Streams.IInputStream)要存储在中的 "" `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-213">The [`IInputStream`](/uwp/api/Windows.Storage.Streams.IInputStream) to be stored in the `MSStream`.</span></span>

#### <span data-ttu-id="cef79-214">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-214">Remarks</span></span>
<span data-ttu-id="cef79-215">此方法采用内容类型和 `IInputStream` 引用。</span><span class="sxs-lookup"><span data-stu-id="cef79-215">This method takes a content-type, and the `IInputStream` reference.</span></span> <span data-ttu-id="cef79-216">然后，该方法验证传入的流引用是否为类型的实例， `IInputStream` 如果不是，则 `DOMException TYPE_MISMATCH_ERR` 引发。</span><span class="sxs-lookup"><span data-stu-id="cef79-216">The method then verifies that the stream reference passed in is an instance of type `IInputStream` and if not, throws `DOMException TYPE_MISMATCH_ERR`.</span></span> <span data-ttu-id="cef79-217">如果没有出现错误，则 `createStreamFromInputStream` `MSStream` 从其输入创建一个（from）。</span><span class="sxs-lookup"><span data-stu-id="cef79-217">If no error occurs, `createStreamFromInputStream` creates an `MSStream` (from its inputs).</span></span>

#### <span data-ttu-id="cef79-218">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-218">Example</span></span>
<span data-ttu-id="cef79-219">`IInputStream`可用于创建 `MSStream` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-219">An `IInputStream` can be used to create an `MSStream`.</span></span> <span data-ttu-id="cef79-220">与 `MSStreams` 固有的一次使用的对象一样，由 `URL.createObjectURL` image 元素首次解析创建的所有 url 都会被吊销。</span><span class="sxs-lookup"><span data-stu-id="cef79-220">As `MSStreams` are inherently one-time-use objects, all URLs created by `URL.createObjectURL` are revoked the first time it's resolved by the image element.</span></span> <span data-ttu-id="cef79-221">此外，在使用该对象后，对此对象的第二个 URL 的请求将失败。</span><span class="sxs-lookup"><span data-stu-id="cef79-221">Additionally, requests for a second URL on this object after the stream has been used will fail.</span></span>

```javascript
var inputStream = myInputStream; //get InputStream from socket API, etc.
var stream = MSApp.createStreamFromInputStream("image/bmp", inputstream);
document.getElementById("imagetag").src = URL.createObjectURL(stream); 
```

### <span data-ttu-id="cef79-222">execAsyncAtPriority</span><span class="sxs-lookup"><span data-stu-id="cef79-222">execAsyncAtPriority</span></span> 
<span data-ttu-id="cef79-223">根据给定优先级调度要在稍后的时间执行的回调。</span><span class="sxs-lookup"><span data-stu-id="cef79-223">Schedules a callback to be executed at a later time according to the given priority.</span></span> 

```javascript
MSApp.execAsyncAtPriority(asynchronousCallback, priority, args); 
```

#### <span data-ttu-id="cef79-224">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-224">Parameters</span></span>
`asynchronousCallback` <span data-ttu-id="cef79-225">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-225">[in]</span></span>

|<span data-ttu-id="cef79-226">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-226">Type</span></span> | <span data-ttu-id="cef79-227">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-227">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-228">函数</span><span class="sxs-lookup"><span data-stu-id="cef79-228">Function</span></span> | <span data-ttu-id="cef79-229">要以异步方式运行的回调函数，以给定的优先级优先级调度。</span><span class="sxs-lookup"><span data-stu-id="cef79-229">The callback function to run asynchronously, dispatched at the given priority priority.</span></span>

`priority` <span data-ttu-id="cef79-230">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-230">[in]</span></span>

|<span data-ttu-id="cef79-231">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-231">Type</span></span> | <span data-ttu-id="cef79-232">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-232">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-233">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-233">DOMString</span></span> | <span data-ttu-id="cef79-234">AsynchronousCallback 回调运行的上下文优先级值。</span><span class="sxs-lookup"><span data-stu-id="cef79-234">The contextual priority value at which the asynchronousCallback callback is run.</span></span> <span data-ttu-id="cef79-235">请参阅[MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="cef79-235">See [MSApp Constants](#msapp-constants).</span></span>

`args` <span data-ttu-id="cef79-236">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-236">[in]</span></span>

|<span data-ttu-id="cef79-237">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-237">Type</span></span> | <span data-ttu-id="cef79-238">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-238">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-239">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-239">Any</span></span> | <span data-ttu-id="cef79-240">传递到 synchronousCallback 回调函数（作为参数1和 on）的一系列可选参数。</span><span class="sxs-lookup"><span data-stu-id="cef79-240">An optional series of arguments that are passed to the synchronousCallback callback function (as parameters 1 and on).</span></span>

#### <span data-ttu-id="cef79-241">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-241">Return value</span></span>
<span data-ttu-id="cef79-242">此方法不返回值。</span><span class="sxs-lookup"><span data-stu-id="cef79-242">This method does not return a value.</span></span>

#### <span data-ttu-id="cef79-243">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-243">Remarks</span></span>
<span data-ttu-id="cef79-244">提供的 `asynchronousCallback` 回调函数将在稍后异步执行。</span><span class="sxs-lookup"><span data-stu-id="cef79-244">The provided `asynchronousCallback` callback function is executed asynchronously later.</span></span> `asynchronousCallback` <span data-ttu-id="cef79-245">将根据所提供的优先级进行调度。</span><span class="sxs-lookup"><span data-stu-id="cef79-245">will be dispatched according to the provided priority.</span></span> <span data-ttu-id="cef79-246">普通优先级等效于现有 [`setImmediate`](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) 方法。</span><span class="sxs-lookup"><span data-stu-id="cef79-246">Normal priority is equivalent to the existing [`setImmediate`](https://developer.mozilla.org/docs/Web/API/Window/setImmediate) method.</span></span> <span data-ttu-id="cef79-247">当回调运行时，当前上下文优先级设置为在回调执行期间提供的优先级参数值。</span><span class="sxs-lookup"><span data-stu-id="cef79-247">When the callback is run, the current contextual priority is set to the provided priority parameter value for the duration of the callback's execution.</span></span>

<span data-ttu-id="cef79-248">`asynchronousCallback`回调参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="cef79-248">The `asynchronousCallback` callback parameter can be any function.</span></span> <span data-ttu-id="cef79-249">如果在参数后提供参数 `priority` ，则它们将全部传递到回调函数。</span><span class="sxs-lookup"><span data-stu-id="cef79-249">If arguments are provided after the `priority` parameter, they will all be passed to the callback function.</span></span>

<span data-ttu-id="cef79-250">与 `execAtPriority` 此不同，回调函数返回的任何对象 `asynchronousCallback` 都会被忽略（且不会通过 `execAsyncAtPriority` ）返回。</span><span class="sxs-lookup"><span data-stu-id="cef79-250">Unlike `execAtPriority`, any object returned by the `asynchronousCallback` callback function is ignored (and not returned via `execAsyncAtPriority`).</span></span>

### <span data-ttu-id="cef79-251">execAtPriority</span><span class="sxs-lookup"><span data-stu-id="cef79-251">execAtPriority</span></span> 
<span data-ttu-id="cef79-252">按给定的上下文优先级运行指定的回调函数。</span><span class="sxs-lookup"><span data-stu-id="cef79-252">Runs the specified callback function at the given contextual priority.</span></span>

```javascript
var retval = MSApp.execAtPriority(synchronousCallback, priority, args);
```

#### <span data-ttu-id="cef79-253">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-253">Parameters</span></span>
`synchronousCallback` <span data-ttu-id="cef79-254">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-254">[in]</span></span>

|<span data-ttu-id="cef79-255">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-255">Type</span></span> | <span data-ttu-id="cef79-256">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-256">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-257">函数</span><span class="sxs-lookup"><span data-stu-id="cef79-257">Function</span></span> | <span data-ttu-id="cef79-258">要以给定优先级的上下文优先级同步运行的回调函数。</span><span class="sxs-lookup"><span data-stu-id="cef79-258">The callback function to run synchronously at the given priority contextual priority.</span></span>

`priority` <span data-ttu-id="cef79-259">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-259">[in]</span></span>

|<span data-ttu-id="cef79-260">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-260">Type</span></span> | <span data-ttu-id="cef79-261">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-261">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-262">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-262">DOMString</span></span> | <span data-ttu-id="cef79-263">指定的优先级值，在运行回调函数时将设置当前上下文优先级值 `synchronousCallback` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-263">The specified priority value to which the current contextual priority value will be set when running the `synchronousCallback` callback function.</span></span> <span data-ttu-id="cef79-264">请参阅[MSApp 常量](#msapp-constants)。</span><span class="sxs-lookup"><span data-stu-id="cef79-264">See [MSApp Constants](#msapp-constants).</span></span>

`args` <span data-ttu-id="cef79-265">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-265">[in]</span></span>

|<span data-ttu-id="cef79-266">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-266">Type</span></span> | <span data-ttu-id="cef79-267">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-267">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-268">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-268">Any</span></span> | <span data-ttu-id="cef79-269">传递给回调函数的一系列可选参数 `synchronousCallback` （如参数1和打开）。</span><span class="sxs-lookup"><span data-stu-id="cef79-269">An optional series of arguments that are passed to the `synchronousCallback` callback function (as parameters 1 and on).</span></span>

#### <span data-ttu-id="cef79-270">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-270">Return value</span></span>
|<span data-ttu-id="cef79-271">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-271">Type</span></span> | <span data-ttu-id="cef79-272">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-272">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-273">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-273">Any</span></span> | <span data-ttu-id="cef79-274">返回回调的返回值 `synchronousCallback` （如果适用）。</span><span class="sxs-lookup"><span data-stu-id="cef79-274">Returns the return value of the `synchronousCallback` callback (as applicable).</span></span>

#### <span data-ttu-id="cef79-275">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-275">Remarks</span></span>
<span data-ttu-id="cef79-276">提供的 `synchronousCallback` 回调方法将同步执行。</span><span class="sxs-lookup"><span data-stu-id="cef79-276">The provided `synchronousCallback` callback method is execute synchronously.</span></span> <span data-ttu-id="cef79-277">在提供的回调函数的持续时间内，当前上下文优先级更改为所提供的优先级值（由 priority 参数提供）。</span><span class="sxs-lookup"><span data-stu-id="cef79-277">The current contextual priority is changed to the provided priority value (given by the priority argument) for the duration of the provided callback function.</span></span> <span data-ttu-id="cef79-278">回调函数执行完毕后，在调用之前，优先级返回到以前的值 `execAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-278">Once the callback function finishes executing, priority is returned to the previous value prior to the `execAtPriority` call.</span></span> <span data-ttu-id="cef79-279">中的返回值 `execAtPriority` 是回调方法（如提供）的返回值。</span><span class="sxs-lookup"><span data-stu-id="cef79-279">The return value from `execAtPriority` is the return value of the callback method (as provided).</span></span>
 
<span data-ttu-id="cef79-280">`synchronousCallback`回调参数可以是任何函数。</span><span class="sxs-lookup"><span data-stu-id="cef79-280">The `synchronousCallback` callback parameter can be any function.</span></span> <span data-ttu-id="cef79-281">如果在 priority 参数后提供任何参数，则它们将传递给所提供的回调方法。</span><span class="sxs-lookup"><span data-stu-id="cef79-281">If any arguments are provided after the priority parameter, they will be passed to the provided callback method.</span></span> <span data-ttu-id="cef79-282">如果回调参数返回一个值，则此值也会成为返回值 `execAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-282">If the callback parameter returns a value, this value becomes the return value for `execAtPriority` as well.</span></span>

#### <span data-ttu-id="cef79-283">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-283">Example</span></span>

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

### <span data-ttu-id="cef79-284">getCurrentPriority</span><span class="sxs-lookup"><span data-stu-id="cef79-284">getCurrentPriority</span></span> 
<span data-ttu-id="cef79-285">返回当前的上下文优先级。</span><span class="sxs-lookup"><span data-stu-id="cef79-285">Returns the current contextual priority.</span></span>

```javascript
var retval = MSApp.getCurrentPriority();
```

#### <span data-ttu-id="cef79-286">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-286">Parameters</span></span>
<span data-ttu-id="cef79-287">无。</span><span class="sxs-lookup"><span data-stu-id="cef79-287">None.</span></span> 

#### <span data-ttu-id="cef79-288">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-288">Return value</span></span>
|<span data-ttu-id="cef79-289">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-289">Type</span></span> | <span data-ttu-id="cef79-290">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-290">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-291">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-291">DOMString</span></span> | <span data-ttu-id="cef79-292">返回值是字符串、或中的 `MSApp.HIGH` 一个 `MSApp.NORMAL` `MSApp.IDLE` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-292">The return value is one of the strings `MSApp.HIGH`, `MSApp.NORMAL`, or `MSApp.IDLE`.</span></span>

#### <span data-ttu-id="cef79-293">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-293">Remarks</span></span>
<span data-ttu-id="cef79-294">此方法返回当前上下文优先级（请参阅 [`MSApp Constants`](#msapp-constants) ），可以通过 and 进行更改 `execAtPriority` `execAsyncAtPriority` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-294">This method returns the current contextual priority (see [`MSApp Constants`](#msapp-constants)), which can be changed via `execAtPriority` and `execAsyncAtPriority`.</span></span>

#### <span data-ttu-id="cef79-295">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-295">Example</span></span>

```javascript
if (MSApp.getCurrentPriority() === MSApp.IDLE) { 
  // YOUR CODE HERE
}
```

### <span data-ttu-id="cef79-296">getHtmlPrintDocumentSource</span><span class="sxs-lookup"><span data-stu-id="cef79-296">getHtmlPrintDocumentSource</span></span>  

<span data-ttu-id="cef79-297">已弃用的同步 API。</span><span class="sxs-lookup"><span data-stu-id="cef79-297">Synchronous API that has been deprecated.</span></span> <span data-ttu-id="cef79-298">对于 Windows 10，请参阅 `getHtmlPrintDocumentSourceAsync` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-298">For Windows 10, see `getHtmlPrintDocumentSourceAsync`.</span></span> <span data-ttu-id="cef79-299">对于 Windows 8 和8.1 应用，请参阅[getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325)的 MSDN 条目。</span><span class="sxs-lookup"><span data-stu-id="cef79-299">For Windows 8 and 8.1 apps, see the MSDN entry for [getHtmlPrintDocumentSource](https://msdn.microsoft.com/library/hh772325).</span></span>  

### <span data-ttu-id="cef79-300">getHtmlPrintDocumentSourceAsync</span><span class="sxs-lookup"><span data-stu-id="cef79-300">getHtmlPrintDocumentSourceAsync</span></span>
<span data-ttu-id="cef79-301">返回要打印的源内容。</span><span class="sxs-lookup"><span data-stu-id="cef79-301">Returns the source content that is to be printed.</span></span>

#### <span data-ttu-id="cef79-302">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-302">Parameters</span></span>
`htmlDoc` <span data-ttu-id="cef79-303">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-303">[in]</span></span>

|<span data-ttu-id="cef79-304">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-304">Type</span></span> | <span data-ttu-id="cef79-305">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-305">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-306">文档</span><span class="sxs-lookup"><span data-stu-id="cef79-306">Document</span></span> | <span data-ttu-id="cef79-307">要打印的 HTML 文档。</span><span class="sxs-lookup"><span data-stu-id="cef79-307">The HTML document to be printed.</span></span> <span data-ttu-id="cef79-308">这可以是根文档、iframe 中的文档、文档片段或 SVG 文档。</span><span class="sxs-lookup"><span data-stu-id="cef79-308">This can be the root document, the document in an iframe, a document fragment, or a SVG document.</span></span> <span data-ttu-id="cef79-309">请注意，htmlDoc 必须是文档，而不是元素。</span><span class="sxs-lookup"><span data-stu-id="cef79-309">Be aware that htmlDoc must be a document, not an element.</span></span>

#### <span data-ttu-id="cef79-310">示例 1</span><span class="sxs-lookup"><span data-stu-id="cef79-310">Example 1</span></span>

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

#### <span data-ttu-id="cef79-311">示例 2</span><span class="sxs-lookup"><span data-stu-id="cef79-311">Example 2</span></span>

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

### <span data-ttu-id="cef79-312">getViewId</span><span class="sxs-lookup"><span data-stu-id="cef79-312">getViewId</span></span> 
<span data-ttu-id="cef79-313">对多个窗口的支持。</span><span class="sxs-lookup"><span data-stu-id="cef79-313">Support for multiple windows.</span></span> 

> [!NOTE] 
> <span data-ttu-id="cef79-314">在 Win 8.1 JavaScript UWP 应用中，使用 MSApp DOM Api （现在已 depricated）支持多个窗口。</span><span class="sxs-lookup"><span data-stu-id="cef79-314">In Win8.1 JavaScript UWP apps supported multiple windows using MSApp DOM APIs which are now depricated.</span></span> <span data-ttu-id="cef79-315">对于 Windows 10，请使用 `window.open` 、 `window` 和新建 `MSApp.getViewId` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-315">For Windows 10, use `window.open`, `window`, and the new `MSApp.getViewId`.</span></span>

| <span data-ttu-id="cef79-316">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-316">Description</span></span> |<span data-ttu-id="cef79-317">Windows 10</span><span class="sxs-lookup"><span data-stu-id="cef79-317">Windows 10</span></span> | <span data-ttu-id="cef79-318">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="cef79-318">Windows 8.1</span></span> |  
|:---- |:---- |:--- |  
| <span data-ttu-id="cef79-319">新建窗口</span><span class="sxs-lookup"><span data-stu-id="cef79-319">Create new window</span></span> | [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) | [`MSApp.createNewView`](https://msdn.microsoft.com/library/dn254975(v=vs.85).aspx) |  
|<span data-ttu-id="cef79-320">新的 window 对象</span><span class="sxs-lookup"><span data-stu-id="cef79-320">New window object</span></span> | [`window`](https://developer.mozilla.org/docs/Web/API/Window) |[`MSAppView`](https://msdn.microsoft.com/library/dn268315(v=vs.85).aspx) |  

```javascript
var retval = MSApp.getViewId(window); 
```

#### <span data-ttu-id="cef79-321">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-321">Parameters</span></span>
`window`

|<span data-ttu-id="cef79-322">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-322">Type</span></span> | <span data-ttu-id="cef79-323">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-323">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-324">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-324">DOMString</span></span> | <span data-ttu-id="cef79-325">表示包含 DOM 文档的窗口的对象。</span><span class="sxs-lookup"><span data-stu-id="cef79-325">An object representing a window containing a DOM document.</span></span> | 

#### <span data-ttu-id="cef79-326">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-326">Return value</span></span>

`viewId`

|<span data-ttu-id="cef79-327">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-327">Type</span></span> | <span data-ttu-id="cef79-328">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-328">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-329">数字</span><span class="sxs-lookup"><span data-stu-id="cef79-329">Number</span></span> | <span data-ttu-id="cef79-330">可与各种 api 一起使用 [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) 。</span><span class="sxs-lookup"><span data-stu-id="cef79-330">Can be used with the various [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span> 

#### <span data-ttu-id="cef79-331">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-331">Remarks</span></span>
<span data-ttu-id="cef79-332">使用 [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) 和 [`window`](https://developer.mozilla.org/docs/Web/API/Window) 用于创建新窗口，但随后要与 WinRT api 交互，请添加 `MSApp.getViewId` API。</span><span class="sxs-lookup"><span data-stu-id="cef79-332">Use [`window.open`](https://developer.mozilla.org/docs/Web/API/Window/open) and [`window`](https://developer.mozilla.org/docs/Web/API/Window) for creating new windows, but then to interact with WinRT APIs, add the `MSApp.getViewId` API.</span></span> <span data-ttu-id="cef79-333">它将 `window` 对象作为参数，并返回 `viewId` 可与各种 api 一起使用的数字 [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) 。</span><span class="sxs-lookup"><span data-stu-id="cef79-333">It takes a `window` object as a parameter and returns a `viewId` number that can be used with the various [`Windows.UI.ViewManagement.ApplicationViewSwitcher`](/uwp/api/windows.ui.viewmanagement.applicationviewswitcher) APIs.</span></span> 

##### <span data-ttu-id="cef79-334">延迟可见性</span><span class="sxs-lookup"><span data-stu-id="cef79-334">Delaying Visibility</span></span> 
<span data-ttu-id="cef79-335">WinRT 中的视图正常开始隐藏，最终开发人员在 `TryShowAsStandaloneAsync` 完全准备好后使用类似于显示视图的内容。</span><span class="sxs-lookup"><span data-stu-id="cef79-335">Views in WinRT normally start hidden and the end developer uses something like `TryShowAsStandaloneAsync` to display the view once it is fully prepared.</span></span> <span data-ttu-id="cef79-336">在 web world 中， `window.open` 立即显示一个窗口，最终用户可以在加载和呈现内容时观看。</span><span class="sxs-lookup"><span data-stu-id="cef79-336">In the web world, `window.open` shows a window immediately and the end user can watch as content is loaded and rendered.</span></span> <span data-ttu-id="cef79-337">要让新的 windows act 类似于 WinRT 视图，而不是立即显示，我们添加了一个 `window.open` 选项。</span><span class="sxs-lookup"><span data-stu-id="cef79-337">To have your new windows act like views in WinRT and not display immediately we have added a `window.open` option.</span></span> <span data-ttu-id="cef79-338">例如：</span><span class="sxs-lookup"><span data-stu-id="cef79-338">For example:</span></span>
`let newWindow = window.open("https://example.com", null, "msHideView=yes");`

##### <span data-ttu-id="cef79-339">主窗口差异</span><span class="sxs-lookup"><span data-stu-id="cef79-339">Primary Window Differences</span></span>
<span data-ttu-id="cef79-340">操作系统最初打开的主窗口的行为方式与它打开的辅助窗口不同：</span><span class="sxs-lookup"><span data-stu-id="cef79-340">The primary window that is initially opened by the OS acts differently than the secondary windows that it opens:</span></span> 

|<span data-ttu-id="cef79-341">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-341">Description</span></span> | <span data-ttu-id="cef79-342">主要</span><span class="sxs-lookup"><span data-stu-id="cef79-342">Primary</span></span> | <span data-ttu-id="cef79-343">辅助边框</span><span class="sxs-lookup"><span data-stu-id="cef79-343">Secondary</span></span> |
|:---- |:--- |:--- |
|<span data-ttu-id="cef79-344">打开窗口</span><span class="sxs-lookup"><span data-stu-id="cef79-344">window.open</span></span> | <span data-ttu-id="cef79-345">允许</span><span class="sxs-lookup"><span data-stu-id="cef79-345">Allowed</span></span> | <span data-ttu-id="cef79-346">不允许</span><span class="sxs-lookup"><span data-stu-id="cef79-346">Disallowed</span></span> |
|<span data-ttu-id="cef79-347">window.close</span><span class="sxs-lookup"><span data-stu-id="cef79-347">window.close</span></span> | <span data-ttu-id="cef79-348">关闭应用</span><span class="sxs-lookup"><span data-stu-id="cef79-348">Close app</span></span> | <span data-ttu-id="cef79-349">关闭窗口</span><span class="sxs-lookup"><span data-stu-id="cef79-349">Close window</span></span> |
| <span data-ttu-id="cef79-350">导航限制</span><span class="sxs-lookup"><span data-stu-id="cef79-350">Navigation restrictions</span></span> | <span data-ttu-id="cef79-351">仅 ACUR</span><span class="sxs-lookup"><span data-stu-id="cef79-351">ACUR only</span></span> | <span data-ttu-id="cef79-352">无限制</span><span class="sxs-lookup"><span data-stu-id="cef79-352">No restrictions</span></span> |

<span data-ttu-id="cef79-353">对不允许辅助窗口打开的限制可能会在将来更改，具体取决于[反馈](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer)。</span><span class="sxs-lookup"><span data-stu-id="cef79-353">The restriction to not allow secondary windows to open could change in the future depending on [feedback](https://wpdev.uservoice.com/forums/257854-microsoft-edge-developer).</span></span>

##### <span data-ttu-id="cef79-354">相同来源通信限制</span><span class="sxs-lookup"><span data-stu-id="cef79-354">Same Origin Communication Restrictions</span></span> 
<span data-ttu-id="cef79-355">有一种很难的技术问题可防止对同步、相同源、跨窗口、脚本调用提供正确支持。</span><span class="sxs-lookup"><span data-stu-id="cef79-355">There is a difficult technical issue preventing proper support for synchronous, same-origin, cross-window, script calls.</span></span> <span data-ttu-id="cef79-356">当您打开一个具有相同原点的窗口时，允许一个窗口中的脚本直接调用另一个窗口中的函数，其中一些调用将失败。</span><span class="sxs-lookup"><span data-stu-id="cef79-356">When you open a window that is same origin, script in one window is allowed to directly call functions in the other window, and some of these calls will fail.</span></span> `postMessage` <span data-ttu-id="cef79-357">通话的工作方式很好，如果可能，我们建议采用的方式执行操作。</span><span class="sxs-lookup"><span data-stu-id="cef79-357">calls work just fine and is the recommended way to do things if possible.</span></span> <span data-ttu-id="cef79-358">改进此问题的工作正在进行中。</span><span class="sxs-lookup"><span data-stu-id="cef79-358">Work to improve this issue is in progress.</span></span>


### <span data-ttu-id="cef79-359">isTaskScheduledAtPriorityOrHigher</span><span class="sxs-lookup"><span data-stu-id="cef79-359">isTaskScheduledAtPriorityOrHigher</span></span> 
<span data-ttu-id="cef79-360">返回一个布尔值，指示给定优先级或更高级别是否有挂起的工作。</span><span class="sxs-lookup"><span data-stu-id="cef79-360">Returns a Boolean value indicating whether there is pending work at the given priority level or higher.</span></span>

```javascript
var retval = MSApp.isTaskScheduledAtPriorityOrHigher(priority); 
```

#### <span data-ttu-id="cef79-361">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-361">Parameters</span></span>
`priority` <span data-ttu-id="cef79-362">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-362">[in]</span></span>

|<span data-ttu-id="cef79-363">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-363">Type</span></span> | <span data-ttu-id="cef79-364">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-364">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-365">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-365">DOMString</span></span> | <span data-ttu-id="cef79-366">一个优先级值（请参阅[MSApp 常量](#msapp-constants)），指定优先级级别和上方以查询任何未完成的排队工作。</span><span class="sxs-lookup"><span data-stu-id="cef79-366">A priority value (see [MSApp Constants](#msapp-constants)) specifying the priority level and above to query for any outstanding queued work.</span></span>

#### <span data-ttu-id="cef79-367">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-367">Return value</span></span>
|<span data-ttu-id="cef79-368">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-368">Type</span></span> | <span data-ttu-id="cef79-369">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-369">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-370">布尔</span><span class="sxs-lookup"><span data-stu-id="cef79-370">Boolean</span></span> | <span data-ttu-id="cef79-371">`true`如果在指定的优先级级别或更高级别上有任何排队的工作，则返回， `false` 否则返回。</span><span class="sxs-lookup"><span data-stu-id="cef79-371">Returns `true` if there is any queued work at the specified priority level or above, `false` otherwise.</span></span>

#### <span data-ttu-id="cef79-372">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-372">Remarks</span></span>
<span data-ttu-id="cef79-373">该 `isTaskScheduledAtPriorityOrHigher` 方法为 JavaScript 代码提供了一种方法，用于确定在不同优先级级别（或更高）处是否存在挂起的工作，以便调用 JavaScript 代码可以决定获得更高优先级的工作。</span><span class="sxs-lookup"><span data-stu-id="cef79-373">The `isTaskScheduledAtPriorityOrHigher` method provides a means for JavaScript code to determine if there is pending work at the various priority levels (or above) with the intent that the calling JavaScript code can then decide to yield to higher priority work.</span></span>

#### <span data-ttu-id="cef79-374">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-374">Example</span></span>

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

### <span data-ttu-id="cef79-375">pageHandlesAllApplicationActivations</span><span class="sxs-lookup"><span data-stu-id="cef79-375">pageHandlesAllApplicationActivations</span></span>
<span data-ttu-id="cef79-376">用于在每次激活事件（即单击通知或固定磁贴）之前避免刷新开始路径（页面重新加载）。</span><span class="sxs-lookup"><span data-stu-id="cef79-376">Used to avoid a refresh of the start path (page reload) before every activate event (ie. clicking a notification or a pinned tile).</span></span> 

#### <span data-ttu-id="cef79-377">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-377">Parameters</span></span>

|<span data-ttu-id="cef79-378">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-378">Type</span></span> | <span data-ttu-id="cef79-379">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-379">Description</span></span> |
|:---- |:--- |
<span data-ttu-id="cef79-380">布尔</span><span class="sxs-lookup"><span data-stu-id="cef79-380">Boolean</span></span> | <span data-ttu-id="cef79-381">用于 `MSApp.pageHandlesAllApplicationActivations(true)` 始终跳过刷新开始路径（页面重新加载），而直接跳转到触发 `WebUIApplication` 激活的事件。</span><span class="sxs-lookup"><span data-stu-id="cef79-381">Use `MSApp.pageHandlesAllApplicationActivations(true)` to always skip refreshing the start path (page reload) and instead jump straight to firing the `WebUIApplication` activated event.</span></span> <span data-ttu-id="cef79-382">要求所有页面单独处理激活事件。</span><span class="sxs-lookup"><span data-stu-id="cef79-382">Requires that all pages handle activation events separately.</span></span> <span data-ttu-id="cef79-383">通过将此方法定义为 `true` ，单击激活的事件（如 notificaiton）将不会触发重新加载，即用于避免页面重新加载的单行应用的基本操作。</span><span class="sxs-lookup"><span data-stu-id="cef79-383">By defining this method as `true`, clicking an activated event (like a notificaiton) will not trigger the reload, an essential for single-page apps wishing to avoid page reloads.</span></span>

#### <span data-ttu-id="cef79-384">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-384">Example</span></span> 

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

### <span data-ttu-id="cef79-385">suppressSubdownloadCredentialPrompts</span><span class="sxs-lookup"><span data-stu-id="cef79-385">suppressSubdownloadCredentialPrompts</span></span> 
<span data-ttu-id="cef79-386">控制在下载资源的过程中应用是否取消可能的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="cef79-386">Controls whether an app suppresses possible authentication prompts during the download of resources.</span></span>

```javascript
MSApp.suppressSubdownloadCredentialPrompts(suppress); 
```

#### <span data-ttu-id="cef79-387">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-387">Parameters</span></span>
`suppress` <span data-ttu-id="cef79-388">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-388">[in]</span></span>

|<span data-ttu-id="cef79-389">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-389">Type</span></span> | <span data-ttu-id="cef79-390">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-390">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-391">布尔</span><span class="sxs-lookup"><span data-stu-id="cef79-391">Boolean</span></span> | <span data-ttu-id="cef79-392">True 值将抑制潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="cef79-392">A value of true suppresses potential authentication prompts.</span></span> <span data-ttu-id="cef79-393">False 值不会禁止用户任何潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="cef79-393">A value of false does not suppress any potential authentication prompts from the user.</span></span>

#### <span data-ttu-id="cef79-394">Returan 值</span><span class="sxs-lookup"><span data-stu-id="cef79-394">Returan value</span></span>
<span data-ttu-id="cef79-395">无。</span><span class="sxs-lookup"><span data-stu-id="cef79-395">None.</span></span>

#### <span data-ttu-id="cef79-396">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-396">Remarks</span></span>
<span data-ttu-id="cef79-397">该 `suppressSubdownloadCredentialPrompts` 方法控制在下载资源的过程中应用是否抑制潜在的身份验证提示。</span><span class="sxs-lookup"><span data-stu-id="cef79-397">The `suppressSubdownloadCredentialPrompts` method controls whether an app suppresses potential authentication prompts during the download of resources.</span></span> <span data-ttu-id="cef79-398">默认行为是不取消凭据提示。</span><span class="sxs-lookup"><span data-stu-id="cef79-398">The default behavior is to not suppress credential prompts.</span></span>

`suppressSubdownloadCredentialPrompts` <span data-ttu-id="cef79-399">适用于可能加载大量需要身份验证的资源的应用，例如 "邮件" 应用（其中可能包含包含许多图像的新闻稿，其中每个图像需要身份验证）。</span><span class="sxs-lookup"><span data-stu-id="cef79-399">is intended for use by apps which may load an excessive number of resources that require authentication, such as a mail app (which could contain a newsletter containing a number of images where each image requires authentication).</span></span>

<span data-ttu-id="cef79-400">当取消凭据提示时，访问需要身份验证的资源时，将不会显示用于验证服务器身份的对话框，并且不会下载资源。</span><span class="sxs-lookup"><span data-stu-id="cef79-400">When suppressing credential prompts, dialogs for authenticating to servers will not be shown when accessing resources that require authentication, and the resource will not be downloaded.</span></span> <span data-ttu-id="cef79-401">请注意，不 `suppressSubdownloadCredentialPrompts` 会影响代理身份验证或客户端认证请求对话框等其他可能的提示，也不会影响 XHR。</span><span class="sxs-lookup"><span data-stu-id="cef79-401">Note that `suppressSubdownloadCredentialPrompts` does not impact other possible prompts such as proxy authentication or client certification request dialogs, nor does it impact XHR.</span></span>

<span data-ttu-id="cef79-402">`suppressSubdownloadCredentialPrompts`请注意影响应用程序中的所有内容，包括在元素中托管的内容 `webview` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-402">Be aware that `suppressSubdownloadCredentialPrompts` impacts all content in the application, including content hosted in the `webview` element.</span></span>
 
<span data-ttu-id="cef79-403">**重要提示：** 已缓存凭据提示决策。</span><span class="sxs-lookup"><span data-stu-id="cef79-403">**Important:**  Credential prompt decisions are cached.</span></span> <span data-ttu-id="cef79-404">因此，在取消凭据提示将立即生效时，如果禁止凭据提示，则在取消后允许凭据提示可能需要对文档进行重新加载才能生效。</span><span class="sxs-lookup"><span data-stu-id="cef79-404">Therefore, while suppressing credential prompts will take effect immediately, allowing credential prompts after suppressing them may need a reload of the document to take effect.</span></span>

#### <span data-ttu-id="cef79-405">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-405">Example</span></span>

```javascript
/ Set to true to suppress potenial credential prompts:
MSApp.suppressSubdownloadCredentialPrompts(true); 
// Now one can load content or navigate iframe/webview to some other site.
```

### <span data-ttu-id="cef79-406">terminateApp</span><span class="sxs-lookup"><span data-stu-id="cef79-406">terminateApp</span></span>
<span data-ttu-id="cef79-407">终止当前应用程序并生成失败报告。</span><span class="sxs-lookup"><span data-stu-id="cef79-407">Terminates the current application and generates a failure report.</span></span> 

```javascript
MSApp.terminateApp(error); 
```

#### <span data-ttu-id="cef79-408">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-408">Parameters</span></span>
`error` <span data-ttu-id="cef79-409">登录</span><span class="sxs-lookup"><span data-stu-id="cef79-409">[in]</span></span>

<span data-ttu-id="cef79-410">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-410">Type</span></span> | <span data-ttu-id="cef79-411">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-411">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-412">错误</span><span class="sxs-lookup"><span data-stu-id="cef79-412">Error</span></span> | <span data-ttu-id="cef79-413">一个 `Error` 对象，可用于描述触发终止的错误。</span><span class="sxs-lookup"><span data-stu-id="cef79-413">An `Error` object that you can use to describe the error that triggered the termination.</span></span> <span data-ttu-id="cef79-414">该 `Error` 对象必须包含数字、说明和堆栈属性; 如果对象不包含这些属性，则不会生成失败报告。</span><span class="sxs-lookup"><span data-stu-id="cef79-414">The `Error` object must contain the number, description, and stack properties; a failure report won't be generated if the object doesn't contain these properties.</span></span>

#### <span data-ttu-id="cef79-415">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-415">Return value</span></span>
<span data-ttu-id="cef79-416">无。</span><span class="sxs-lookup"><span data-stu-id="cef79-416">None.</span></span>

#### <span data-ttu-id="cef79-417">备注</span><span class="sxs-lookup"><span data-stu-id="cef79-417">Remarks</span></span>
<span data-ttu-id="cef79-418">如果报告的问题是 `terminateApp` 应用的前5个问题之一，它将显示在应用的 "质量" 页面上。</span><span class="sxs-lookup"><span data-stu-id="cef79-418">If the issue reported by `terminateApp` becomes one of your app's top 5 issues, it will show up on the app's Quality page.</span></span>

#### <span data-ttu-id="cef79-419">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-419">Example</span></span>
<span data-ttu-id="cef79-420">此示例 `terminateApp` 将在遇到异常时进行调用。</span><span class="sxs-lookup"><span data-stu-id="cef79-420">This example calls `terminateApp` when an exception is encountered.</span></span> <span data-ttu-id="cef79-421">`Error`当你捕获异常时，它使用提供的对象。</span><span class="sxs-lookup"><span data-stu-id="cef79-421">It uses the `Error` object provided when you catch an exception.</span></span> 

```javascript
try {  
        var obj2 = null;  
        obj2.val = 5;  
    }  
    catch(e) {  
        window.MSApp.terminateApp(e);  
    }  
```

### <span data-ttu-id="cef79-422">MSApp 常量</span><span class="sxs-lookup"><span data-stu-id="cef79-422">MSApp Constants</span></span>
<span data-ttu-id="cef79-423">与、、和关联的允许的优先级值 `execAsyncAtPriority` `execAtPriority` `getCurrentPriority` `isTaskScheduldAtPriorityOrHigher` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-423">Allowed priority values associated with `execAsyncAtPriority`, `execAtPriority`, `getCurrentPriority`, and `isTaskScheduldAtPriorityOrHigher`.</span></span>

#### <span data-ttu-id="cef79-424">Current</span><span class="sxs-lookup"><span data-stu-id="cef79-424">Current</span></span>
`current`

|<span data-ttu-id="cef79-425">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-425">Type</span></span> | <span data-ttu-id="cef79-426">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-426">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-427">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-427">DOMString</span></span> | <span data-ttu-id="cef79-428">当 `current` 与相应的方法（另请参阅节）一起使用时，该方法将在执行所请求的操作时使用当前的上下文优先级。</span><span class="sxs-lookup"><span data-stu-id="cef79-428">When `current` is used with the appropriate method (See also section), the method will use the current contextual priority when executing the requested operation.</span></span>

#### <span data-ttu-id="cef79-429">高 </span><span class="sxs-lookup"><span data-stu-id="cef79-429">High</span></span>
`high`

|<span data-ttu-id="cef79-430">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-430">Type</span></span> | <span data-ttu-id="cef79-431">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-431">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-432">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-432">DOMString</span></span> | <span data-ttu-id="cef79-433">当 `high` 与相应的方法（请参阅节）一起使用时，该方法在执行请求的操作时将使用高于正常优先级，并且将在任何现有的正常优先级工作之前调度操作。</span><span class="sxs-lookup"><span data-stu-id="cef79-433">When `high` is used with the appropriate method (See also section), the method will use higher than normal priority when executing the requested operation and will be dispatch the operation before any existing normal priority work.</span></span>

#### <span data-ttu-id="cef79-434">Idle</span><span class="sxs-lookup"><span data-stu-id="cef79-434">Idle</span></span>
`idle`

|<span data-ttu-id="cef79-435">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-435">Type</span></span> | <span data-ttu-id="cef79-436">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-436">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-437">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-437">DOMString</span></span> | <span data-ttu-id="cef79-438">当 `ideal` 与相应的方法（请参阅节）一起使用时，该方法在执行请求的操作时将使用低于正常优先级，并且在任何现有的常规优先级工作后将调度该操作。</span><span class="sxs-lookup"><span data-stu-id="cef79-438">When `ideal` is used with the appropriate method (See also section), the method will use lower than normal priority when executing the requested operation and will be dispatch the operation after any existing normal priority work.</span></span>

#### <span data-ttu-id="cef79-439">正常</span><span class="sxs-lookup"><span data-stu-id="cef79-439">Normal</span></span>
`normal`

|<span data-ttu-id="cef79-440">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-440">Type</span></span> | <span data-ttu-id="cef79-441">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-441">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-442">DOMString</span><span class="sxs-lookup"><span data-stu-id="cef79-442">DOMString</span></span> | <span data-ttu-id="cef79-443">当 `normal` 与相应的方法（另请参阅节）一起使用时，该方法将在执行请求的操作时使用常规的现有优先级。</span><span class="sxs-lookup"><span data-stu-id="cef79-443">When `normal` is used with the appropriate method (See also section), the method will use the normal existing priority when executing the requested operation.</span></span>

#### <span data-ttu-id="cef79-444">示例</span><span class="sxs-lookup"><span data-stu-id="cef79-444">Example</span></span>

```javascript
if (window.MSApp.CURRENT) {
  document.getElementById('outputMessageDiv').textContent = 'The value of window.MSApp.CURRENT is "current".';
}
```

#### <span data-ttu-id="cef79-445">要求</span><span class="sxs-lookup"><span data-stu-id="cef79-445">Requirements</span></span>
|<span data-ttu-id="cef79-446">IDL</span><span class="sxs-lookup"><span data-stu-id="cef79-446">IDL</span></span> | <span data-ttu-id="cef79-447">Mshtml</span><span class="sxs-lookup"><span data-stu-id="cef79-447">Mshtml.idl</span></span> |
|:---- |:--- |

## <span data-ttu-id="cef79-448">MSAppAsyncOperation</span><span class="sxs-lookup"><span data-stu-id="cef79-448">MSAppAsyncOperation</span></span>

```javascript
var asyncOperation = MSApp.clearTemporaryWebDataAsync(); 
asyncOperation.oncomplete = function() { console.log("Temporary web data cleared successfully"); }; 
asyncOperation.onerror = function() { console.log("Failed to clear temporary web data"); }; 
asyncOperation.start(); 
```

### <span data-ttu-id="cef79-449">start</span><span class="sxs-lookup"><span data-stu-id="cef79-449">start</span></span>
<span data-ttu-id="cef79-450">启动 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-450">Starts the `MSAppAsyncOperation`.</span></span>

```javascript
var retval = MSAppAsyncOperation.start();
```

#### <span data-ttu-id="cef79-451">参数</span><span class="sxs-lookup"><span data-stu-id="cef79-451">Parameters</span></span>
<span data-ttu-id="cef79-452">无。</span><span class="sxs-lookup"><span data-stu-id="cef79-452">None.</span></span>

#### <span data-ttu-id="cef79-453">返回值</span><span class="sxs-lookup"><span data-stu-id="cef79-453">Return value</span></span>
<span data-ttu-id="cef79-454">无。</span><span class="sxs-lookup"><span data-stu-id="cef79-454">None.</span></span>

#### <span data-ttu-id="cef79-455">属性</span><span class="sxs-lookup"><span data-stu-id="cef79-455">Properties</span></span>
`error` <span data-ttu-id="cef79-456">属性</span><span class="sxs-lookup"><span data-stu-id="cef79-456">property</span></span>

|<span data-ttu-id="cef79-457">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-457">Type</span></span> | <span data-ttu-id="cef79-458">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-458">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-459">DOMError</span><span class="sxs-lookup"><span data-stu-id="cef79-459">DOMError</span></span> | <span data-ttu-id="cef79-460">表示中的错误 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-460">Represents an error in `MSAppAsyncOperation`.</span></span>

```javascript
p = object.error
```

`oncomplete` <span data-ttu-id="cef79-461">属性</span><span class="sxs-lookup"><span data-stu-id="cef79-461">property</span></span>

|<span data-ttu-id="cef79-462">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-462">Type</span></span> | <span data-ttu-id="cef79-463">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-463">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-464">EventHandler</span><span class="sxs-lookup"><span data-stu-id="cef79-464">EventHandler</span></span> | <span data-ttu-id="cef79-465">用于在完成时设置事件处理程序的属性 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-465">Property for setting an event handler on completion of `MSAppAsyncOperation`.</span></span>

```javascript
p = object.oncomplete
```

`onerror` <span data-ttu-id="cef79-466">属性</span><span class="sxs-lookup"><span data-stu-id="cef79-466">property</span></span>

|<span data-ttu-id="cef79-467">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-467">Type</span></span> | <span data-ttu-id="cef79-468">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-468">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-469">EventHandler</span><span class="sxs-lookup"><span data-stu-id="cef79-469">EventHandler</span></span> | <span data-ttu-id="cef79-470">在期间发生错误时设置事件处理程序的属性 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-470">Property for setting an event handler upon an error during `MSAppAsyncOperation`.</span></span>

```javascript
p = object.onerror
```

`readyState` <span data-ttu-id="cef79-471">属性</span><span class="sxs-lookup"><span data-stu-id="cef79-471">property</span></span>

|<span data-ttu-id="cef79-472">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-472">Type</span></span> | <span data-ttu-id="cef79-473">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-473">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-474">数字</span><span class="sxs-lookup"><span data-stu-id="cef79-474">Number</span></span> | <span data-ttu-id="cef79-475">表示使用 JavaScript 的 Windows 应用中的异步操作的状态。</span><span class="sxs-lookup"><span data-stu-id="cef79-475">Represents the state of the asynchronous operation within the Windows app using JavaScript.</span></span> <span data-ttu-id="cef79-476">值包括：已启动 [0]，已完成 [1]，错误 [2]。</span><span class="sxs-lookup"><span data-stu-id="cef79-476">Values include: Started[0], Completed[1], Error[2].</span></span>

```javascript
p = object.readyState
```

`result` <span data-ttu-id="cef79-477">属性</span><span class="sxs-lookup"><span data-stu-id="cef79-477">property</span></span>

|<span data-ttu-id="cef79-478">类型</span><span class="sxs-lookup"><span data-stu-id="cef79-478">Type</span></span> | <span data-ttu-id="cef79-479">描述</span><span class="sxs-lookup"><span data-stu-id="cef79-479">Description</span></span> |
|:---- |:--- |
|<span data-ttu-id="cef79-480">Any</span><span class="sxs-lookup"><span data-stu-id="cef79-480">Any</span></span> |<span data-ttu-id="cef79-481">表示的结果 `MSAppAsyncOperation` 。</span><span class="sxs-lookup"><span data-stu-id="cef79-481">Represents the result of `MSAppAsyncOperation`.</span></span>

```javascript
p = object.result
```
