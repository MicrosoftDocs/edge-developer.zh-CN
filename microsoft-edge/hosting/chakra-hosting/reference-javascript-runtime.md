---
description: JavaScript 运行时（JsRT） Api 使你能够将脚本功能添加到在 Windows 上运行的桌面和服务器端应用程序。
title: 参考（JavaScript 运行时） |Microsoft 文档
ms.custom: ''
ms.date: 01/15/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0bfe50da-fd79-4e00-9458-bc667769b415
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d1215d84daa31f2338b8c7e237625d0129026bea
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563055"
---
# <span data-ttu-id="a19b6-103">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="a19b6-103">Reference (JavaScript Runtime)</span></span>
<span data-ttu-id="a19b6-104">JavaScript 运行时（JsRT） Api 使你能够将脚本功能添加到在 Windows 上运行的桌面和服务器端应用程序。</span><span class="sxs-lookup"><span data-stu-id="a19b6-104">JavaScript Runtime (JsRT) APIs enable you to add scripting capabilities to desktop and server-side applications running on Windows.</span></span>  
  
 <span data-ttu-id="a19b6-105">如果你打算在你的应用程序中嵌入[ChakraCore](https://github.com/Microsoft/ChakraCore) ，请参阅[CHAKRACORE Wiki](https://aka.ms/corejsrtref) for JSRT 引用。</span><span class="sxs-lookup"><span data-stu-id="a19b6-105">If you intend to embed [ChakraCore](https://github.com/Microsoft/ChakraCore) in your application, please refer to [ChakraCore Wiki](https://aka.ms/corejsrtref) for JSRT references instead.</span></span>  
  
## <span data-ttu-id="a19b6-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="a19b6-106">In This Section</span></span>  
 <span data-ttu-id="a19b6-107">支持 JsRT 托管的 typedef、常量和枚举如下所述：</span><span class="sxs-lookup"><span data-stu-id="a19b6-107">Typedefs, constants, and enumerations that support JsRT hosting are described here:</span></span>  
  
-   [<span data-ttu-id="a19b6-108">JavaScript 运行时的 Typedef、常量和枚举</span><span class="sxs-lookup"><span data-stu-id="a19b6-108">JavaScript Runtime Typedefs, Constants, and Enumerations</span></span>](../chakra-hosting/javascript-runtime-typedefs-constants-and-enumerations.md)  
  
 <span data-ttu-id="a19b6-109">以下函数支持 JsRT 托管：</span><span class="sxs-lookup"><span data-stu-id="a19b6-109">The following functions enable JsRT hosting:</span></span>  
  
-   [<span data-ttu-id="a19b6-110">JsAddRef 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-110">JsAddRef Function</span></span>](../chakra-hosting/jsaddref-function.md)  
  
-   [<span data-ttu-id="a19b6-111">JsBooleanToBool 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-111">JsBooleanToBool Function</span></span>](../chakra-hosting/jsbooleantobool-function.md)  
  
-   [<span data-ttu-id="a19b6-112">JsBoolToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-112">JsBoolToBoolean Function</span></span>](../chakra-hosting/jsbooltoboolean-function.md)  
  
-   [<span data-ttu-id="a19b6-113">JsCallFunction 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-113">JsCallFunction Function</span></span>](../chakra-hosting/jscallfunction-function.md)  
  
-   [<span data-ttu-id="a19b6-114">JsCollectGarbage 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-114">JsCollectGarbage Function</span></span>](../chakra-hosting/jscollectgarbage-function.md)  
  
-   [<span data-ttu-id="a19b6-115">JsConstructObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-115">JsConstructObject Function</span></span>](../chakra-hosting/jsconstructobject-function.md)  
  
-   [<span data-ttu-id="a19b6-116">JsConvertValueToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-116">JsConvertValueToBoolean Function</span></span>](../chakra-hosting/jsconvertvaluetoboolean-function.md)  
  
-   [<span data-ttu-id="a19b6-117">JsConvertValueToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-117">JsConvertValueToNumber Function</span></span>](../chakra-hosting/jsconvertvaluetonumber-function.md)  
  
-   [<span data-ttu-id="a19b6-118">JsConvertValueToObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-118">JsConvertValueToObject Function</span></span>](../chakra-hosting/jsconvertvaluetoobject-function.md)  
  
-   [<span data-ttu-id="a19b6-119">JsConvertValueToString 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-119">JsConvertValueToString Function</span></span>](../chakra-hosting/jsconvertvaluetostring-function.md)  
  
-   [<span data-ttu-id="a19b6-120">JsCreateArray 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-120">JsCreateArray Function</span></span>](../chakra-hosting/jscreatearray-function.md)  
  
-   [<span data-ttu-id="a19b6-121">JsCreateArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-121">JsCreateArrayBuffer Function</span></span>](../chakra-hosting/jscreatearraybuffer-function.md)  
  
-   [<span data-ttu-id="a19b6-122">JsCreateContext 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-122">JsCreateContext Function</span></span>](../chakra-hosting/jscreatecontext-function.md)  
  
-   [<span data-ttu-id="a19b6-123">JsCreateDataView 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-123">JsCreateDataView Function</span></span>](../chakra-hosting/jscreatedataview-function.md)  
  
-   [<span data-ttu-id="a19b6-124">JsCreateError 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-124">JsCreateError Function</span></span>](../chakra-hosting/jscreateerror-function.md)  
  
-   [<span data-ttu-id="a19b6-125">JsCreateExternalArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-125">JsCreateExternalArrayBuffer Function</span></span>](../chakra-hosting/jscreateexternalarraybuffer-function.md)  
  
-   [<span data-ttu-id="a19b6-126">JsCreateExternalObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-126">JsCreateExternalObject Function</span></span>](../chakra-hosting/jscreateexternalobject-function.md)  
  
-   [<span data-ttu-id="a19b6-127">JsCreateFunction 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-127">JsCreateFunction Function</span></span>](../chakra-hosting/jscreatefunction-function.md)  
  
-   [<span data-ttu-id="a19b6-128">JsCreateNamedFunction 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-128">JsCreateNamedFunction Function</span></span>](../chakra-hosting/jscreatenamedfunction-function.md)  
  
-   [<span data-ttu-id="a19b6-129">JsCreateObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-129">JsCreateObject Function</span></span>](../chakra-hosting/jscreateobject-function.md)  
  
-   [<span data-ttu-id="a19b6-130">JsCreateRangeError 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-130">JsCreateRangeError Function</span></span>](../chakra-hosting/jscreaterangeerror-function.md)  
  
-   [<span data-ttu-id="a19b6-131">JsCreateReferenceError 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-131">JsCreateReferenceError Function</span></span>](../chakra-hosting/jscreatereferenceerror-function.md)  
  
-   [<span data-ttu-id="a19b6-132">JsCreateRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-132">JsCreateRuntime Function</span></span>](../chakra-hosting/jscreateruntime-function.md)  
  
-   [<span data-ttu-id="a19b6-133">JsCreateSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-133">JsCreateSymbol Function</span></span>](../chakra-hosting/jscreatesymbol-function.md)  
  
-   [<span data-ttu-id="a19b6-134">JsCreateSyntaxError 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-134">JsCreateSyntaxError Function</span></span>](../chakra-hosting/jscreatesyntaxerror-function.md)  
  
-   [<span data-ttu-id="a19b6-135">JsCreateTypeError 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-135">JsCreateTypeError Function</span></span>](../chakra-hosting/jscreatetypeerror-function.md)  
  
-   [<span data-ttu-id="a19b6-136">JsCreateTypedArray 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-136">JsCreateTypedArray Function</span></span>](../chakra-hosting/jscreatetypedarray-function.md)  
  
-   [<span data-ttu-id="a19b6-137">JsCreateURIError 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-137">JsCreateURIError Function</span></span>](../chakra-hosting/jscreateurierror-function.md)  
  
-   [<span data-ttu-id="a19b6-138">JsDefineProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-138">JsDefineProperty Function</span></span>](../chakra-hosting/jsdefineproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-139">JsDeleteIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-139">JsDeleteIndexedProperty Function</span></span>](../chakra-hosting/jsdeleteindexedproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-140">JsDeleteProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-140">JsDeleteProperty Function</span></span>](../chakra-hosting/jsdeleteproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-141">JsDisableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-141">JsDisableRuntimeExecution Function</span></span>](../chakra-hosting/jsdisableruntimeexecution-function.md)  
  
-   [<span data-ttu-id="a19b6-142">JsDisposeRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-142">JsDisposeRuntime Function</span></span>](../chakra-hosting/jsdisposeruntime-function.md)  
  
-   [<span data-ttu-id="a19b6-143">JsDoubleToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-143">JsDoubleToNumber Function</span></span>](../chakra-hosting/jsdoubletonumber-function.md)  
  
-   [<span data-ttu-id="a19b6-144">JsEnableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-144">JsEnableRuntimeExecution Function</span></span>](../chakra-hosting/jsenableruntimeexecution-function.md)  
  
-   [<span data-ttu-id="a19b6-145">JsEnumerateHeap 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-145">JsEnumerateHeap Function</span></span>](../chakra-hosting/jsenumerateheap-function.md)  
  
-   [<span data-ttu-id="a19b6-146">JsEquals 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-146">JsEquals Function</span></span>](../chakra-hosting/jsequals-function.md)  
  
-   [<span data-ttu-id="a19b6-147">JsGetAndClearException 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-147">JsGetAndClearException Function</span></span>](../chakra-hosting/jsgetandclearexception-function.md)  
  
-   [<span data-ttu-id="a19b6-148">JsGetArrayBufferStorage 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-148">JsGetArrayBufferStorage Function</span></span>](../chakra-hosting/jsgetarraybufferstorage-function.md)  
  
-   [<span data-ttu-id="a19b6-149">JsGetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-149">JsGetContextData Function</span></span>](../chakra-hosting/jsgetcontextdata-function.md)  
  
-   [<span data-ttu-id="a19b6-150">JsGetContextOfObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-150">JsGetContextOfObject Function</span></span>](../chakra-hosting/jsgetcontextofobject-function.md)  
  
-   [<span data-ttu-id="a19b6-151">JsGetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-151">JsGetCurrentContext Function</span></span>](../chakra-hosting/jsgetcurrentcontext-function.md)  
  
-   [<span data-ttu-id="a19b6-152">JsGetDataViewStorage 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-152">JsGetDataViewStorage Function</span></span>](../chakra-hosting/jsgetdataviewstorage-function.md)  
  
-   [<span data-ttu-id="a19b6-153">JsGetExtensionAllowed 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-153">JsGetExtensionAllowed Function</span></span>](../chakra-hosting/jsgetextensionallowed-function.md)  
  
-   [<span data-ttu-id="a19b6-154">JsGetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-154">JsGetExternalData Function</span></span>](../chakra-hosting/jsgetexternaldata-function.md)  
  
-   [<span data-ttu-id="a19b6-155">JsGetFalseValue 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-155">JsGetFalseValue Function</span></span>](../chakra-hosting/jsgetfalsevalue-function.md)  
  
-   [<span data-ttu-id="a19b6-156">JsGetGlobalObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-156">JsGetGlobalObject Function</span></span>](../chakra-hosting/jsgetglobalobject-function.md)  
  
-   [<span data-ttu-id="a19b6-157">JsGetIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-157">JsGetIndexedPropertiesExternalData Function</span></span>](../chakra-hosting/jsgetindexedpropertiesexternaldata-function.md)  
  
-   [<span data-ttu-id="a19b6-158">JsGetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-158">JsGetIndexedProperty Function</span></span>](../chakra-hosting/jsgetindexedproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-159">JsGetNullValue 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-159">JsGetNullValue Function</span></span>](../chakra-hosting/jsgetnullvalue-function.md)  
  
-   [<span data-ttu-id="a19b6-160">JsGetOwnPropertyDescriptor 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-160">JsGetOwnPropertyDescriptor Function</span></span>](../chakra-hosting/jsgetownpropertydescriptor-function.md)  
  
-   [<span data-ttu-id="a19b6-161">JsGetOwnPropertyNames 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-161">JsGetOwnPropertyNames Function</span></span>](../chakra-hosting/jsgetownpropertynames-function.md)  
  
-   [<span data-ttu-id="a19b6-162">JsGetOwnPropertySymbols 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-162">JsGetOwnPropertySymbols Function</span></span>](../chakra-hosting/jsgetownpropertysymbols-function.md)  
  
-   [<span data-ttu-id="a19b6-163">JsGetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-163">JsGetProperty Function</span></span>](../chakra-hosting/jsgetproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-164">JsGetPropertyIdFromName 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-164">JsGetPropertyIdFromName Function</span></span>](../chakra-hosting/jsgetpropertyidfromname-function.md)  
  
-   [<span data-ttu-id="a19b6-165">JsGetPropertyIdFromSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-165">JsGetPropertyIdFromSymbol Function</span></span>](../chakra-hosting/jsgetpropertyidfromsymbol-function.md)  
  
-   [<span data-ttu-id="a19b6-166">JsGetPropertyIdType 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-166">JsGetPropertyIdType Function</span></span>](../chakra-hosting/jsgetpropertyidtype-function.md)  
  
-   [<span data-ttu-id="a19b6-167">JsGetPropertyNameFromId 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-167">JsGetPropertyNameFromId Function</span></span>](../chakra-hosting/jsgetpropertynamefromid-function.md)  
  
-   [<span data-ttu-id="a19b6-168">JsGetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-168">JsGetPrototype Function</span></span>](../chakra-hosting/jsgetprototype-function.md)  
  
-   [<span data-ttu-id="a19b6-169">JsGetRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-169">JsGetRuntime Function</span></span>](../chakra-hosting/jsgetruntime-function.md)  
  
-   [<span data-ttu-id="a19b6-170">JsGetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-170">JsGetRuntimeMemoryLimit Function</span></span>](../chakra-hosting/jsgetruntimememorylimit-function.md)  
  
-   [<span data-ttu-id="a19b6-171">JsGetRuntimeMemoryUsage 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-171">JsGetRuntimeMemoryUsage Function</span></span>](../chakra-hosting/jsgetruntimememoryusage-function.md)  
  
-   [<span data-ttu-id="a19b6-172">JsGetStringLength 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-172">JsGetStringLength Function</span></span>](../chakra-hosting/jsgetstringlength-function.md)  
  
-   [<span data-ttu-id="a19b6-173">JsGetSymbolFromPropertyId 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-173">JsGetSymbolFromPropertyId Function</span></span>](../chakra-hosting/jsgetsymbolfrompropertyid-function.md)  
  
-   [<span data-ttu-id="a19b6-174">JsGetTrueValue 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-174">JsGetTrueValue Function</span></span>](../chakra-hosting/jsgettruevalue-function.md)  
  
-   [<span data-ttu-id="a19b6-175">JsGetTypedArrayInfo 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-175">JsGetTypedArrayInfo Function</span></span>](../chakra-hosting/jsgettypedarrayinfo-function.md)  
  
-   [<span data-ttu-id="a19b6-176">JsGetTypedArrayStorage 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-176">JsGetTypedArrayStorage Function</span></span>](../chakra-hosting/jsgettypedarraystorage-function.md)  
  
-   [<span data-ttu-id="a19b6-177">JsGetUndefinedValue 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-177">JsGetUndefinedValue Function</span></span>](../chakra-hosting/jsgetundefinedvalue-function.md)  
  
-   [<span data-ttu-id="a19b6-178">JsGetValueType 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-178">JsGetValueType Function</span></span>](../chakra-hosting/jsgetvaluetype-function.md)  
  
-   [<span data-ttu-id="a19b6-179">JsHasException 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-179">JsHasException Function</span></span>](../chakra-hosting/jshasexception-function.md)  
  
-   [<span data-ttu-id="a19b6-180">JsHasExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-180">JsHasExternalData Function</span></span>](../chakra-hosting/jshasexternaldata-function.md)  
  
-   [<span data-ttu-id="a19b6-181">JsHasIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-181">JsHasIndexedPropertiesExternalData Function</span></span>](../chakra-hosting/jshasindexedpropertiesexternaldata-function.md)  
  
-   [<span data-ttu-id="a19b6-182">JsHasIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-182">JsHasIndexedProperty Function</span></span>](../chakra-hosting/jshasindexedproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-183">JsHasProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-183">JsHasProperty Function</span></span>](../chakra-hosting/jshasproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-184">JsIdle 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-184">JsIdle Function</span></span>](../chakra-hosting/jsidle-function.md)  
  
-   [<span data-ttu-id="a19b6-185">JsInspectableToObject 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-185">JsInspectableToObject Function</span></span>](../chakra-hosting/jsinspectabletoobject-function.md)  
  
-   [<span data-ttu-id="a19b6-186">JsInstanceOf 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-186">JsInstanceOf Function</span></span>](../chakra-hosting/jsinstanceof-function.md)  
  
-   [<span data-ttu-id="a19b6-187">JsIntToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-187">JsIntToNumber Function</span></span>](../chakra-hosting/jsinttonumber-function.md)  
  
-   [<span data-ttu-id="a19b6-188">JsIsEnumeratingHeap 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-188">JsIsEnumeratingHeap Function</span></span>](../chakra-hosting/jsisenumeratingheap-function.md)  
  
-   [<span data-ttu-id="a19b6-189">JsIsRuntimeExecutionDisabled 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-189">JsIsRuntimeExecutionDisabled Function</span></span>](../chakra-hosting/jsisruntimeexecutiondisabled-function.md)  
  
-   [<span data-ttu-id="a19b6-190">JsNumberToDouble 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-190">JsNumberToDouble Function</span></span>](../chakra-hosting/jsnumbertodouble-function.md)  
  
-   [<span data-ttu-id="a19b6-191">JsNumberToInt 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-191">JsNumberToInt Function</span></span>](../chakra-hosting/jsnumbertoint-function.md)  
  
-   [<span data-ttu-id="a19b6-192">JsObjectToInspectable 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-192">JsObjectToInspectable Function</span></span>](../chakra-hosting/jsobjecttoinspectable-function.md)  
  
-   [<span data-ttu-id="a19b6-193">JsParseScript 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-193">JsParseScript Function</span></span>](../chakra-hosting/jsparsescript-function.md)  
  
-   [<span data-ttu-id="a19b6-194">JsParseSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-194">JsParseSerializedScript Function</span></span>](../chakra-hosting/jsparseserializedscript-function.md)  
  
-   [<span data-ttu-id="a19b6-195">JsParseSerializedScriptWithCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-195">JsParseSerializedScriptWithCallback Function</span></span>](../chakra-hosting/jsparseserializedscriptwithcallback-function.md)  
  
-   [<span data-ttu-id="a19b6-196">JsPointerToString 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-196">JsPointerToString Function</span></span>](../chakra-hosting/jspointertostring-function.md)  
  
-   [<span data-ttu-id="a19b6-197">JsPreventExtension 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-197">JsPreventExtension Function</span></span>](../chakra-hosting/jspreventextension-function.md)  
  
-   [<span data-ttu-id="a19b6-198">JsProjectWinRTNamespace 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-198">JsProjectWinRTNamespace Function</span></span>](../chakra-hosting/jsprojectwinrtnamespace-function.md)  
  
-   [<span data-ttu-id="a19b6-199">JsRelease 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-199">JsRelease Function</span></span>](../chakra-hosting/jsrelease-function.md)  
  
-   [<span data-ttu-id="a19b6-200">JsRunScript 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-200">JsRunScript Function</span></span>](../chakra-hosting/jsrunscript-function.md)  
  
-   [<span data-ttu-id="a19b6-201">JsRunSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-201">JsRunSerializedScript Function</span></span>](../chakra-hosting/jsrunserializedscript-function.md)  
  
-   [<span data-ttu-id="a19b6-202">JsRunSerializedScriptWithCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-202">JsRunSerializedScriptWithCallback Function</span></span>](../chakra-hosting/jsrunserializedscriptwithcallback-function.md)  
  
-   [<span data-ttu-id="a19b6-203">JsSerializeScript 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-203">JsSerializeScript Function</span></span>](../chakra-hosting/jsserializescript-function.md)  
  
-   [<span data-ttu-id="a19b6-204">JsSetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-204">JsSetContextData Function</span></span>](../chakra-hosting/jssetcontextdata-function.md)  
  
-   [<span data-ttu-id="a19b6-205">JsSetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-205">JsSetCurrentContext Function</span></span>](../chakra-hosting/jssetcurrentcontext-function.md)  
  
-   [<span data-ttu-id="a19b6-206">JsSetException 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-206">JsSetException Function</span></span>](../chakra-hosting/jssetexception-function.md)  
  
-   [<span data-ttu-id="a19b6-207">JsSetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-207">JsSetExternalData Function</span></span>](../chakra-hosting/jssetexternaldata-function.md)  
  
-   [<span data-ttu-id="a19b6-208">JsSetIndexedPropertiesToExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-208">JsSetIndexedPropertiesToExternalData Function</span></span>](../chakra-hosting/jssetindexedpropertiestoexternaldata-function.md)  
  
-   [<span data-ttu-id="a19b6-209">JsSetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-209">JsSetIndexedProperty Function</span></span>](../chakra-hosting/jssetindexedproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-210">JsSetObjectBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-210">JsSetObjectBeforeCollectCallback Function</span></span>](../chakra-hosting/jssetobjectbeforecollectcallback-function.md)  
  
-   [<span data-ttu-id="a19b6-211">JsSetProjectionEnqueueCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-211">JsSetProjectionEnqueueCallback Function</span></span>](../chakra-hosting/jssetprojectionenqueuecallback-function.md)  
  
-   [<span data-ttu-id="a19b6-212">JsSetPromiseContinuationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-212">JsSetPromiseContinuationCallback Function</span></span>](../chakra-hosting/jssetpromisecontinuationcallback-function.md)  
  
-   [<span data-ttu-id="a19b6-213">JsSetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-213">JsSetProperty Function</span></span>](../chakra-hosting/jssetproperty-function.md)  
  
-   [<span data-ttu-id="a19b6-214">JsSetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-214">JsSetPrototype Function</span></span>](../chakra-hosting/jssetprototype-function.md)  
  
-   [<span data-ttu-id="a19b6-215">JsSetRuntimeBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-215">JsSetRuntimeBeforeCollectCallback Function</span></span>](../chakra-hosting/jssetruntimebeforecollectcallback-function.md)  
  
-   [<span data-ttu-id="a19b6-216">JsSetRuntimeMemoryAllocationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-216">JsSetRuntimeMemoryAllocationCallback Function</span></span>](../chakra-hosting/jssetruntimememoryallocationcallback-function.md)  
  
-   [<span data-ttu-id="a19b6-217">JsSetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-217">JsSetRuntimeMemoryLimit Function</span></span>](../chakra-hosting/jssetruntimememorylimit-function.md)  
  
-   [<span data-ttu-id="a19b6-218">JsStartDebugging 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-218">JsStartDebugging Function</span></span>](../chakra-hosting/jsstartdebugging-function.md)  
  
-   [<span data-ttu-id="a19b6-219">JsStartProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-219">JsStartProfiling Function</span></span>](../chakra-hosting/jsstartprofiling-function.md)  
  
-   [<span data-ttu-id="a19b6-220">JsStopProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-220">JsStopProfiling Function</span></span>](../chakra-hosting/jsstopprofiling-function.md)  
  
-   [<span data-ttu-id="a19b6-221">JsStrictEquals 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-221">JsStrictEquals Function</span></span>](../chakra-hosting/jsstrictequals-function.md)  
  
-   [<span data-ttu-id="a19b6-222">JsStringToPointer 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-222">JsStringToPointer Function</span></span>](../chakra-hosting/jsstringtopointer-function.md)  
  
-   [<span data-ttu-id="a19b6-223">JsValueToVariant 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-223">JsValueToVariant Function</span></span>](../chakra-hosting/jsvaluetovariant-function.md)  
  
-   [<span data-ttu-id="a19b6-224">JsVariantToValue 函数</span><span class="sxs-lookup"><span data-stu-id="a19b6-224">JsVariantToValue Function</span></span>](../chakra-hosting/jsvarianttovalue-function.md)  
  
## <span data-ttu-id="a19b6-225">另请参阅</span><span class="sxs-lookup"><span data-stu-id="a19b6-225">See Also</span></span>  
 [<span data-ttu-id="a19b6-226">托管 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="a19b6-226">Hosting the JavaScript Runtime</span></span>](../chakra-hosting/hosting-the-javascript-runtime.md)   
 [<span data-ttu-id="a19b6-227">JavaScript 运行时托管</span><span class="sxs-lookup"><span data-stu-id="a19b6-227">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)