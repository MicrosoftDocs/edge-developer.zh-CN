---
description: JavaScript 运行时 (JsRT) Api 使你能够将脚本功能添加到在 Windows 上运行的桌面和服务器端应用程序。
title: 应用 (JavaScript Runtime)
ms.date: 06/08/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 0bfe50da-fd79-4e00-9458-bc667769b415
caps.latest.revision: 9
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 7166e6cd5d64060c2939d8404e1415dc34fce17b
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752211"
---
# <span data-ttu-id="2cf0b-103"> (JavaScript 运行时) 的参考</span><span class="sxs-lookup"><span data-stu-id="2cf0b-103">Reference (JavaScript runtime)</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="2cf0b-104">JavaScript 运行时 (JsRT) Api 使你能够将脚本功能添加到在 Windows 上运行的桌面和服务器端应用程序。</span><span class="sxs-lookup"><span data-stu-id="2cf0b-104">JavaScript Runtime (JsRT) APIs enable you to add scripting capabilities to desktop and server-side applications running on Windows.</span></span>  

<span data-ttu-id="2cf0b-105">如果你打算在你的应用程序中嵌入 [ChakraCore](https://github.com/Microsoft/ChakraCore) ，请参阅 [CHAKRACORE Wiki](https://aka.ms/corejsrtref) for JSRT 引用。</span><span class="sxs-lookup"><span data-stu-id="2cf0b-105">If you intend to embed [ChakraCore](https://github.com/Microsoft/ChakraCore) in your application, please refer to [ChakraCore Wiki](https://aka.ms/corejsrtref) for JSRT references instead.</span></span>  

## <span data-ttu-id="2cf0b-106">本部分内容</span><span class="sxs-lookup"><span data-stu-id="2cf0b-106">In this section</span></span>  

<span data-ttu-id="2cf0b-107">支持 JsRT 托管的 typedef、常量和枚举如下所述：</span><span class="sxs-lookup"><span data-stu-id="2cf0b-107">Typedefs, constants, and enumerations that support JsRT hosting are described here:</span></span>  
  
*   [<span data-ttu-id="2cf0b-108">JavaScript 运行时 Typedef、常量和枚举</span><span class="sxs-lookup"><span data-stu-id="2cf0b-108">JavaScript Runtime Typedefs, Constants, and Enumerations</span></span>](./javascript-runtime-typedefs-constants-and-enumerations.md)  

<span data-ttu-id="2cf0b-109">以下函数支持 JsRT 托管：</span><span class="sxs-lookup"><span data-stu-id="2cf0b-109">The following functions enable JsRT hosting:</span></span>  

*   [<span data-ttu-id="2cf0b-110">JsAddRef 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-110">JsAddRef Function</span></span>](./jsaddref-function.md)  
*   [<span data-ttu-id="2cf0b-111">JsBooleanToBool 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-111">JsBooleanToBool Function</span></span>](./jsbooleantobool-function.md)  
*   [<span data-ttu-id="2cf0b-112">JsBoolToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-112">JsBoolToBoolean Function</span></span>](./jsbooltoboolean-function.md)  
*   [<span data-ttu-id="2cf0b-113">JsCallFunction 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-113">JsCallFunction Function</span></span>](./jscallfunction-function.md)  
*   [<span data-ttu-id="2cf0b-114">JsCollectGarbage 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-114">JsCollectGarbage Function</span></span>](./jscollectgarbage-function.md)  
*   [<span data-ttu-id="2cf0b-115">JsConstructObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-115">JsConstructObject Function</span></span>](./jsconstructobject-function.md)  
*   [<span data-ttu-id="2cf0b-116">JsConvertValueToBoolean 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-116">JsConvertValueToBoolean Function</span></span>](./jsconvertvaluetoboolean-function.md)  
*   [<span data-ttu-id="2cf0b-117">JsConvertValueToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-117">JsConvertValueToNumber Function</span></span>](./jsconvertvaluetonumber-function.md)  
*   [<span data-ttu-id="2cf0b-118">JsConvertValueToObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-118">JsConvertValueToObject Function</span></span>](./jsconvertvaluetoobject-function.md)  
*   [<span data-ttu-id="2cf0b-119">JsConvertValueToString 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-119">JsConvertValueToString Function</span></span>](./jsconvertvaluetostring-function.md)  
*   [<span data-ttu-id="2cf0b-120">JsCreateArray 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-120">JsCreateArray Function</span></span>](./jscreatearray-function.md)  
*   [<span data-ttu-id="2cf0b-121">JsCreateArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-121">JsCreateArrayBuffer Function</span></span>](./jscreatearraybuffer-function.md)  
*   [<span data-ttu-id="2cf0b-122">JsCreateContext 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-122">JsCreateContext Function</span></span>](./jscreatecontext-function.md)  
*   [<span data-ttu-id="2cf0b-123">JsCreateDataView Function</span><span class="sxs-lookup"><span data-stu-id="2cf0b-123">JsCreateDataView Function</span></span>](./jscreatedataview-function.md)  
*   [<span data-ttu-id="2cf0b-124">JsCreateError 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-124">JsCreateError Function</span></span>](./jscreateerror-function.md)  
*   [<span data-ttu-id="2cf0b-125">JsCreateExternalArrayBuffer 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-125">JsCreateExternalArrayBuffer Function</span></span>](./jscreateexternalarraybuffer-function.md)  
*   [<span data-ttu-id="2cf0b-126">JsCreateExternalObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-126">JsCreateExternalObject Function</span></span>](./jscreateexternalobject-function.md)  
*   [<span data-ttu-id="2cf0b-127">JsCreateFunction 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-127">JsCreateFunction Function</span></span>](./jscreatefunction-function.md)  
*   [<span data-ttu-id="2cf0b-128">JsCreateNamedFunction 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-128">JsCreateNamedFunction Function</span></span>](./jscreatenamedfunction-function.md)  
*   [<span data-ttu-id="2cf0b-129">JsCreateObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-129">JsCreateObject Function</span></span>](./jscreateobject-function.md)  
*   [<span data-ttu-id="2cf0b-130">JsCreateRangeError 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-130">JsCreateRangeError Function</span></span>](./jscreaterangeerror-function.md)  
*   [<span data-ttu-id="2cf0b-131">JsCreateReferenceError 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-131">JsCreateReferenceError Function</span></span>](./jscreatereferenceerror-function.md)  
*   [<span data-ttu-id="2cf0b-132">JsCreateRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-132">JsCreateRuntime Function</span></span>](./jscreateruntime-function.md)  
*   [<span data-ttu-id="2cf0b-133">JsCreateSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-133">JsCreateSymbol Function</span></span>](./jscreatesymbol-function.md)  
*   [<span data-ttu-id="2cf0b-134">JsCreateSyntaxError 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-134">JsCreateSyntaxError Function</span></span>](./jscreatesyntaxerror-function.md)  
*   [<span data-ttu-id="2cf0b-135">JsCreateTypeError 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-135">JsCreateTypeError Function</span></span>](./jscreatetypeerror-function.md)  
*   [<span data-ttu-id="2cf0b-136">JsCreateTypedArray 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-136">JsCreateTypedArray Function</span></span>](./jscreatetypedarray-function.md)  
*   [<span data-ttu-id="2cf0b-137">JsCreateURIError 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-137">JsCreateURIError Function</span></span>](./jscreateurierror-function.md)  
*   [<span data-ttu-id="2cf0b-138">JsDefineProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-138">JsDefineProperty Function</span></span>](./jsdefineproperty-function.md)  
*   [<span data-ttu-id="2cf0b-139">JsDeleteIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-139">JsDeleteIndexedProperty Function</span></span>](./jsdeleteindexedproperty-function.md)  
*   [<span data-ttu-id="2cf0b-140">JsDeleteProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-140">JsDeleteProperty Function</span></span>](./jsdeleteproperty-function.md)  
*   [<span data-ttu-id="2cf0b-141">JsDisableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-141">JsDisableRuntimeExecution Function</span></span>](./jsdisableruntimeexecution-function.md)  
*   [<span data-ttu-id="2cf0b-142">JsDisposeRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-142">JsDisposeRuntime Function</span></span>](./jsdisposeruntime-function.md)  
*   [<span data-ttu-id="2cf0b-143">JsDoubleToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-143">JsDoubleToNumber Function</span></span>](./jsdoubletonumber-function.md)  
*   [<span data-ttu-id="2cf0b-144">JsEnableRuntimeExecution 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-144">JsEnableRuntimeExecution Function</span></span>](./jsenableruntimeexecution-function.md)  
*   [<span data-ttu-id="2cf0b-145">JsEnumerateHeap 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-145">JsEnumerateHeap Function</span></span>](./jsenumerateheap-function.md)  
*   [<span data-ttu-id="2cf0b-146">JsEquals 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-146">JsEquals Function</span></span>](./jsequals-function.md)  
*   [<span data-ttu-id="2cf0b-147">JsGetAndClearException 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-147">JsGetAndClearException Function</span></span>](./jsgetandclearexception-function.md)  
*   [<span data-ttu-id="2cf0b-148">JsGetArrayBufferStorage 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-148">JsGetArrayBufferStorage Function</span></span>](./jsgetarraybufferstorage-function.md)  
*   [<span data-ttu-id="2cf0b-149">JsGetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-149">JsGetContextData Function</span></span>](./jsgetcontextdata-function.md)  
*   [<span data-ttu-id="2cf0b-150">JsGetContextOfObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-150">JsGetContextOfObject Function</span></span>](./jsgetcontextofobject-function.md)  
*   [<span data-ttu-id="2cf0b-151">JsGetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-151">JsGetCurrentContext Function</span></span>](./jsgetcurrentcontext-function.md)  
*   [<span data-ttu-id="2cf0b-152">JsGetDataViewStorage 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-152">JsGetDataViewStorage Function</span></span>](./jsgetdataviewstorage-function.md)  
*   [<span data-ttu-id="2cf0b-153">JsGetExtensionAllowed 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-153">JsGetExtensionAllowed Function</span></span>](./jsgetextensionallowed-function.md)  
*   [<span data-ttu-id="2cf0b-154">JsGetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-154">JsGetExternalData Function</span></span>](./jsgetexternaldata-function.md)  
*   [<span data-ttu-id="2cf0b-155">JsGetFalseValue 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-155">JsGetFalseValue Function</span></span>](./jsgetfalsevalue-function.md)  
*   [<span data-ttu-id="2cf0b-156">JsGetGlobalObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-156">JsGetGlobalObject Function</span></span>](./jsgetglobalobject-function.md)  
*   [<span data-ttu-id="2cf0b-157">JsGetIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-157">JsGetIndexedPropertiesExternalData Function</span></span>](./jsgetindexedpropertiesexternaldata-function.md)  
*   [<span data-ttu-id="2cf0b-158">JsGetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-158">JsGetIndexedProperty Function</span></span>](./jsgetindexedproperty-function.md)  
*   [<span data-ttu-id="2cf0b-159">JsGetNullValue 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-159">JsGetNullValue Function</span></span>](./jsgetnullvalue-function.md)  
*   [<span data-ttu-id="2cf0b-160">JsGetOwnPropertyDescriptor 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-160">JsGetOwnPropertyDescriptor Function</span></span>](./jsgetownpropertydescriptor-function.md)  
*   [<span data-ttu-id="2cf0b-161">JsGetOwnPropertyNames 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-161">JsGetOwnPropertyNames Function</span></span>](./jsgetownpropertynames-function.md)  
*   [<span data-ttu-id="2cf0b-162">JsGetOwnPropertySymbols 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-162">JsGetOwnPropertySymbols Function</span></span>](./jsgetownpropertysymbols-function.md)  
*   [<span data-ttu-id="2cf0b-163">JsGetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-163">JsGetProperty Function</span></span>](./jsgetproperty-function.md)  
*   [<span data-ttu-id="2cf0b-164">JsGetPropertyIdFromName 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-164">JsGetPropertyIdFromName Function</span></span>](./jsgetpropertyidfromname-function.md)  
*   [<span data-ttu-id="2cf0b-165">JsGetPropertyIdFromSymbol 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-165">JsGetPropertyIdFromSymbol Function</span></span>](./jsgetpropertyidfromsymbol-function.md)  
*   [<span data-ttu-id="2cf0b-166">JsGetPropertyIdType 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-166">JsGetPropertyIdType Function</span></span>](./jsgetpropertyidtype-function.md)  
*   [<span data-ttu-id="2cf0b-167">JsGetPropertyNameFromId 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-167">JsGetPropertyNameFromId Function</span></span>](./jsgetpropertynamefromid-function.md)  
*   [<span data-ttu-id="2cf0b-168">JsGetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-168">JsGetPrototype Function</span></span>](./jsgetprototype-function.md)  
*   [<span data-ttu-id="2cf0b-169">JsGetRuntime 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-169">JsGetRuntime Function</span></span>](./jsgetruntime-function.md)  
*   [<span data-ttu-id="2cf0b-170">JsGetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-170">JsGetRuntimeMemoryLimit Function</span></span>](./jsgetruntimememorylimit-function.md)  
*   [<span data-ttu-id="2cf0b-171">JsGetRuntimeMemoryUsage 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-171">JsGetRuntimeMemoryUsage Function</span></span>](./jsgetruntimememoryusage-function.md)  
*   [<span data-ttu-id="2cf0b-172">JsGetStringLength 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-172">JsGetStringLength Function</span></span>](./jsgetstringlength-function.md)  
*   [<span data-ttu-id="2cf0b-173">JsGetSymbolFromPropertyId 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-173">JsGetSymbolFromPropertyId Function</span></span>](./jsgetsymbolfrompropertyid-function.md)  
*   [<span data-ttu-id="2cf0b-174">JsGetTrueValue 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-174">JsGetTrueValue Function</span></span>](./jsgettruevalue-function.md)  
*   [<span data-ttu-id="2cf0b-175">JsGetTypedArrayInfo 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-175">JsGetTypedArrayInfo Function</span></span>](./jsgettypedarrayinfo-function.md)  
*   [<span data-ttu-id="2cf0b-176">JsGetTypedArrayStorage 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-176">JsGetTypedArrayStorage Function</span></span>](./jsgettypedarraystorage-function.md)  
*   [<span data-ttu-id="2cf0b-177">JsGetUndefinedValue 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-177">JsGetUndefinedValue Function</span></span>](./jsgetundefinedvalue-function.md)  
*   [<span data-ttu-id="2cf0b-178">JsGetValueType 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-178">JsGetValueType Function</span></span>](./jsgetvaluetype-function.md)  
*   [<span data-ttu-id="2cf0b-179">JsHasException 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-179">JsHasException Function</span></span>](./jshasexception-function.md)  
*   [<span data-ttu-id="2cf0b-180">JsHasExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-180">JsHasExternalData Function</span></span>](./jshasexternaldata-function.md)  
*   [<span data-ttu-id="2cf0b-181">JsHasIndexedPropertiesExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-181">JsHasIndexedPropertiesExternalData Function</span></span>](./jshasindexedpropertiesexternaldata-function.md)  
*   [<span data-ttu-id="2cf0b-182">JsHasIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-182">JsHasIndexedProperty Function</span></span>](./jshasindexedproperty-function.md)  
*   [<span data-ttu-id="2cf0b-183">JsHasProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-183">JsHasProperty Function</span></span>](./jshasproperty-function.md)  
*   [<span data-ttu-id="2cf0b-184">JsIdle 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-184">JsIdle Function</span></span>](./jsidle-function.md)  
*   [<span data-ttu-id="2cf0b-185">JsInspectableToObject 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-185">JsInspectableToObject Function</span></span>](./jsinspectabletoobject-function.md)  
*   [<span data-ttu-id="2cf0b-186">JsInstanceOf 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-186">JsInstanceOf Function</span></span>](./jsinstanceof-function.md)  
*   [<span data-ttu-id="2cf0b-187">JsIntToNumber 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-187">JsIntToNumber Function</span></span>](./jsinttonumber-function.md)  
*   [<span data-ttu-id="2cf0b-188">JsIsEnumeratingHeap 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-188">JsIsEnumeratingHeap Function</span></span>](./jsisenumeratingheap-function.md)  
*   [<span data-ttu-id="2cf0b-189">JsIsRuntimeExecutionDisabled 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-189">JsIsRuntimeExecutionDisabled Function</span></span>](./jsisruntimeexecutiondisabled-function.md)  
*   [<span data-ttu-id="2cf0b-190">JsNumberToDouble 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-190">JsNumberToDouble Function</span></span>](./jsnumbertodouble-function.md)  
*   [<span data-ttu-id="2cf0b-191">JsNumberToInt 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-191">JsNumberToInt Function</span></span>](./jsnumbertoint-function.md)  
*   [<span data-ttu-id="2cf0b-192">JsObjectToInspectable 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-192">JsObjectToInspectable Function</span></span>](./jsobjecttoinspectable-function.md)  
*   [<span data-ttu-id="2cf0b-193">JsParseScript 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-193">JsParseScript Function</span></span>](./jsparsescript-function.md)  
*   [<span data-ttu-id="2cf0b-194">JsParseSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-194">JsParseSerializedScript Function</span></span>](./jsparseserializedscript-function.md)  
*   [<span data-ttu-id="2cf0b-195">JsParseSerializedScriptWithCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-195">JsParseSerializedScriptWithCallback Function</span></span>](./jsparseserializedscriptwithcallback-function.md)  
*   [<span data-ttu-id="2cf0b-196">JsPointerToString 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-196">JsPointerToString Function</span></span>](./jspointertostring-function.md)  
*   [<span data-ttu-id="2cf0b-197">JsPreventExtension 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-197">JsPreventExtension Function</span></span>](./jspreventextension-function.md)  
*   [<span data-ttu-id="2cf0b-198">JsProjectWinRTNamespace 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-198">JsProjectWinRTNamespace Function</span></span>](./jsprojectwinrtnamespace-function.md)  
*   [<span data-ttu-id="2cf0b-199">JsRelease 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-199">JsRelease Function</span></span>](./jsrelease-function.md)  
*   [<span data-ttu-id="2cf0b-200">JsRunScript 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-200">JsRunScript Function</span></span>](./jsrunscript-function.md)  
*   [<span data-ttu-id="2cf0b-201">JsRunSerializedScript 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-201">JsRunSerializedScript Function</span></span>](./jsrunserializedscript-function.md)  
*   [<span data-ttu-id="2cf0b-202">JsRunSerializedScriptWithCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-202">JsRunSerializedScriptWithCallback Function</span></span>](./jsrunserializedscriptwithcallback-function.md)  
*   [<span data-ttu-id="2cf0b-203">JsSerializeScript 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-203">JsSerializeScript Function</span></span>](./jsserializescript-function.md)  
*   [<span data-ttu-id="2cf0b-204">JsSetContextData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-204">JsSetContextData Function</span></span>](./jssetcontextdata-function.md)  
*   [<span data-ttu-id="2cf0b-205">JsSetCurrentContext 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-205">JsSetCurrentContext Function</span></span>](./jssetcurrentcontext-function.md)  
*   [<span data-ttu-id="2cf0b-206">JsSetException 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-206">JsSetException Function</span></span>](./jssetexception-function.md)  
*   [<span data-ttu-id="2cf0b-207">JsSetExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-207">JsSetExternalData Function</span></span>](./jssetexternaldata-function.md)  
*   [<span data-ttu-id="2cf0b-208">JsSetIndexedPropertiesToExternalData 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-208">JsSetIndexedPropertiesToExternalData Function</span></span>](./jssetindexedpropertiestoexternaldata-function.md)  
*   [<span data-ttu-id="2cf0b-209">JsSetIndexedProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-209">JsSetIndexedProperty Function</span></span>](./jssetindexedproperty-function.md)  
*   [<span data-ttu-id="2cf0b-210">JsSetObjectBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-210">JsSetObjectBeforeCollectCallback Function</span></span>](./jssetobjectbeforecollectcallback-function.md)  
*   [<span data-ttu-id="2cf0b-211">JsSetProjectionEnqueueCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-211">JsSetProjectionEnqueueCallback Function</span></span>](./jssetprojectionenqueuecallback-function.md)  
*   [<span data-ttu-id="2cf0b-212">JsSetPromiseContinuationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-212">JsSetPromiseContinuationCallback Function</span></span>](./jssetpromisecontinuationcallback-function.md)  
*   [<span data-ttu-id="2cf0b-213">JsSetProperty 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-213">JsSetProperty Function</span></span>](./jssetproperty-function.md)  
*   [<span data-ttu-id="2cf0b-214">JsSetPrototype 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-214">JsSetPrototype Function</span></span>](./jssetprototype-function.md)  
*   [<span data-ttu-id="2cf0b-215">JsSetRuntimeBeforeCollectCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-215">JsSetRuntimeBeforeCollectCallback Function</span></span>](./jssetruntimebeforecollectcallback-function.md)  
*   [<span data-ttu-id="2cf0b-216">JsSetRuntimeMemoryAllocationCallback 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-216">JsSetRuntimeMemoryAllocationCallback Function</span></span>](./jssetruntimememoryallocationcallback-function.md)  
*   [<span data-ttu-id="2cf0b-217">JsSetRuntimeMemoryLimit 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-217">JsSetRuntimeMemoryLimit Function</span></span>](./jssetruntimememorylimit-function.md)  
*   [<span data-ttu-id="2cf0b-218">JsStartDebugging 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-218">JsStartDebugging Function</span></span>](./jsstartdebugging-function.md)  
*   [<span data-ttu-id="2cf0b-219">JsStartProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-219">JsStartProfiling Function</span></span>](./jsstartprofiling-function.md)  
*   [<span data-ttu-id="2cf0b-220">JsStopProfiling 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-220">JsStopProfiling Function</span></span>](./jsstopprofiling-function.md)  
*   [<span data-ttu-id="2cf0b-221">JsStrictEquals 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-221">JsStrictEquals Function</span></span>](./jsstrictequals-function.md)  
*   [<span data-ttu-id="2cf0b-222">JsStringToPointer 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-222">JsStringToPointer Function</span></span>](./jsstringtopointer-function.md)  
*   [<span data-ttu-id="2cf0b-223">JsValueToVariant 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-223">JsValueToVariant Function</span></span>](./jsvaluetovariant-function.md)  
*   [<span data-ttu-id="2cf0b-224">JsVariantToValue 函数</span><span class="sxs-lookup"><span data-stu-id="2cf0b-224">JsVariantToValue Function</span></span>](./jsvarianttovalue-function.md)  

## <span data-ttu-id="2cf0b-225">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2cf0b-225">See also</span></span>  

*   [<span data-ttu-id="2cf0b-226">托管 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="2cf0b-226">Hosting the JavaScript Runtime</span></span>](./hosting-the-javascript-runtime.md)  
*   [<span data-ttu-id="2cf0b-227">JavaScript 运行时托管</span><span class="sxs-lookup"><span data-stu-id="2cf0b-227">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)  
