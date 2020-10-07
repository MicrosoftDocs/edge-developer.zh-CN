---
description: JavaScript Runtime (JsRT) APIs enable you to add scripting capabilities to desktop and server-side applications running on Windows.
title: Reference (JavaScript Runtime)
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
# Reference (JavaScript runtime)  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

JavaScript Runtime (JsRT) APIs enable you to add scripting capabilities to desktop and server-side applications running on Windows.  

If you intend to embed [ChakraCore](https://github.com/Microsoft/ChakraCore) in your application, please refer to [ChakraCore Wiki](https://aka.ms/corejsrtref) for JSRT references instead.  

## In this section  

Typedefs, constants, and enumerations that support JsRT hosting are described here:  
  
*   [JavaScript Runtime Typedefs, Constants, and Enumerations](./javascript-runtime-typedefs-constants-and-enumerations.md)  

The following functions enable JsRT hosting:  

*   [JsAddRef Function](./jsaddref-function.md)  
*   [JsBooleanToBool 函数](./jsbooleantobool-function.md)  
*   [JsBoolToBoolean 函数](./jsbooltoboolean-function.md)  
*   [JsCallFunction 函数](./jscallfunction-function.md)  
*   [JsCollectGarbage 函数](./jscollectgarbage-function.md)  
*   [JsConstructObject 函数](./jsconstructobject-function.md)  
*   [JsConvertValueToBoolean 函数](./jsconvertvaluetoboolean-function.md)  
*   [JsConvertValueToNumber 函数](./jsconvertvaluetonumber-function.md)  
*   [JsConvertValueToObject 函数](./jsconvertvaluetoobject-function.md)  
*   [JsConvertValueToString 函数](./jsconvertvaluetostring-function.md)  
*   [JsCreateArray 函数](./jscreatearray-function.md)  
*   [JsCreateArrayBuffer 函数](./jscreatearraybuffer-function.md)  
*   [JsCreateContext 函数](./jscreatecontext-function.md)  
*   [JsCreateDataView Function](./jscreatedataview-function.md)  
*   [JsCreateError 函数](./jscreateerror-function.md)  
*   [JsCreateExternalArrayBuffer 函数](./jscreateexternalarraybuffer-function.md)  
*   [JsCreateExternalObject 函数](./jscreateexternalobject-function.md)  
*   [JsCreateFunction 函数](./jscreatefunction-function.md)  
*   [JsCreateNamedFunction 函数](./jscreatenamedfunction-function.md)  
*   [JsCreateObject 函数](./jscreateobject-function.md)  
*   [JsCreateRangeError 函数](./jscreaterangeerror-function.md)  
*   [JsCreateReferenceError 函数](./jscreatereferenceerror-function.md)  
*   [JsCreateRuntime 函数](./jscreateruntime-function.md)  
*   [JsCreateSymbol 函数](./jscreatesymbol-function.md)  
*   [JsCreateSyntaxError 函数](./jscreatesyntaxerror-function.md)  
*   [JsCreateTypeError 函数](./jscreatetypeerror-function.md)  
*   [JsCreateTypedArray 函数](./jscreatetypedarray-function.md)  
*   [JsCreateURIError 函数](./jscreateurierror-function.md)  
*   [JsDefineProperty 函数](./jsdefineproperty-function.md)  
*   [JsDeleteIndexedProperty 函数](./jsdeleteindexedproperty-function.md)  
*   [JsDeleteProperty 函数](./jsdeleteproperty-function.md)  
*   [JsDisableRuntimeExecution 函数](./jsdisableruntimeexecution-function.md)  
*   [JsDisposeRuntime 函数](./jsdisposeruntime-function.md)  
*   [JsDoubleToNumber 函数](./jsdoubletonumber-function.md)  
*   [JsEnableRuntimeExecution 函数](./jsenableruntimeexecution-function.md)  
*   [JsEnumerateHeap 函数](./jsenumerateheap-function.md)  
*   [JsEquals 函数](./jsequals-function.md)  
*   [JsGetAndClearException 函数](./jsgetandclearexception-function.md)  
*   [JsGetArrayBufferStorage 函数](./jsgetarraybufferstorage-function.md)  
*   [JsGetContextData 函数](./jsgetcontextdata-function.md)  
*   [JsGetContextOfObject 函数](./jsgetcontextofobject-function.md)  
*   [JsGetCurrentContext 函数](./jsgetcurrentcontext-function.md)  
*   [JsGetDataViewStorage 函数](./jsgetdataviewstorage-function.md)  
*   [JsGetExtensionAllowed 函数](./jsgetextensionallowed-function.md)  
*   [JsGetExternalData 函数](./jsgetexternaldata-function.md)  
*   [JsGetFalseValue 函数](./jsgetfalsevalue-function.md)  
*   [JsGetGlobalObject 函数](./jsgetglobalobject-function.md)  
*   [JsGetIndexedPropertiesExternalData 函数](./jsgetindexedpropertiesexternaldata-function.md)  
*   [JsGetIndexedProperty 函数](./jsgetindexedproperty-function.md)  
*   [JsGetNullValue 函数](./jsgetnullvalue-function.md)  
*   [JsGetOwnPropertyDescriptor 函数](./jsgetownpropertydescriptor-function.md)  
*   [JsGetOwnPropertyNames 函数](./jsgetownpropertynames-function.md)  
*   [JsGetOwnPropertySymbols 函数](./jsgetownpropertysymbols-function.md)  
*   [JsGetProperty 函数](./jsgetproperty-function.md)  
*   [JsGetPropertyIdFromName 函数](./jsgetpropertyidfromname-function.md)  
*   [JsGetPropertyIdFromSymbol 函数](./jsgetpropertyidfromsymbol-function.md)  
*   [JsGetPropertyIdType 函数](./jsgetpropertyidtype-function.md)  
*   [JsGetPropertyNameFromId 函数](./jsgetpropertynamefromid-function.md)  
*   [JsGetPrototype 函数](./jsgetprototype-function.md)  
*   [JsGetRuntime 函数](./jsgetruntime-function.md)  
*   [JsGetRuntimeMemoryLimit 函数](./jsgetruntimememorylimit-function.md)  
*   [JsGetRuntimeMemoryUsage 函数](./jsgetruntimememoryusage-function.md)  
*   [JsGetStringLength 函数](./jsgetstringlength-function.md)  
*   [JsGetSymbolFromPropertyId 函数](./jsgetsymbolfrompropertyid-function.md)  
*   [JsGetTrueValue 函数](./jsgettruevalue-function.md)  
*   [JsGetTypedArrayInfo 函数](./jsgettypedarrayinfo-function.md)  
*   [JsGetTypedArrayStorage 函数](./jsgettypedarraystorage-function.md)  
*   [JsGetUndefinedValue 函数](./jsgetundefinedvalue-function.md)  
*   [JsGetValueType 函数](./jsgetvaluetype-function.md)  
*   [JsHasException 函数](./jshasexception-function.md)  
*   [JsHasExternalData 函数](./jshasexternaldata-function.md)  
*   [JsHasIndexedPropertiesExternalData 函数](./jshasindexedpropertiesexternaldata-function.md)  
*   [JsHasIndexedProperty 函数](./jshasindexedproperty-function.md)  
*   [JsHasProperty 函数](./jshasproperty-function.md)  
*   [JsIdle 函数](./jsidle-function.md)  
*   [JsInspectableToObject 函数](./jsinspectabletoobject-function.md)  
*   [JsInstanceOf 函数](./jsinstanceof-function.md)  
*   [JsIntToNumber 函数](./jsinttonumber-function.md)  
*   [JsIsEnumeratingHeap 函数](./jsisenumeratingheap-function.md)  
*   [JsIsRuntimeExecutionDisabled 函数](./jsisruntimeexecutiondisabled-function.md)  
*   [JsNumberToDouble 函数](./jsnumbertodouble-function.md)  
*   [JsNumberToInt 函数](./jsnumbertoint-function.md)  
*   [JsObjectToInspectable 函数](./jsobjecttoinspectable-function.md)  
*   [JsParseScript 函数](./jsparsescript-function.md)  
*   [JsParseSerializedScript 函数](./jsparseserializedscript-function.md)  
*   [JsParseSerializedScriptWithCallback 函数](./jsparseserializedscriptwithcallback-function.md)  
*   [JsPointerToString 函数](./jspointertostring-function.md)  
*   [JsPreventExtension 函数](./jspreventextension-function.md)  
*   [JsProjectWinRTNamespace 函数](./jsprojectwinrtnamespace-function.md)  
*   [JsRelease 函数](./jsrelease-function.md)  
*   [JsRunScript 函数](./jsrunscript-function.md)  
*   [JsRunSerializedScript 函数](./jsrunserializedscript-function.md)  
*   [JsRunSerializedScriptWithCallback 函数](./jsrunserializedscriptwithcallback-function.md)  
*   [JsSerializeScript 函数](./jsserializescript-function.md)  
*   [JsSetContextData 函数](./jssetcontextdata-function.md)  
*   [JsSetCurrentContext 函数](./jssetcurrentcontext-function.md)  
*   [JsSetException 函数](./jssetexception-function.md)  
*   [JsSetExternalData 函数](./jssetexternaldata-function.md)  
*   [JsSetIndexedPropertiesToExternalData 函数](./jssetindexedpropertiestoexternaldata-function.md)  
*   [JsSetIndexedProperty 函数](./jssetindexedproperty-function.md)  
*   [JsSetObjectBeforeCollectCallback 函数](./jssetobjectbeforecollectcallback-function.md)  
*   [JsSetProjectionEnqueueCallback 函数](./jssetprojectionenqueuecallback-function.md)  
*   [JsSetPromiseContinuationCallback 函数](./jssetpromisecontinuationcallback-function.md)  
*   [JsSetProperty 函数](./jssetproperty-function.md)  
*   [JsSetPrototype 函数](./jssetprototype-function.md)  
*   [JsSetRuntimeBeforeCollectCallback 函数](./jssetruntimebeforecollectcallback-function.md)  
*   [JsSetRuntimeMemoryAllocationCallback 函数](./jssetruntimememoryallocationcallback-function.md)  
*   [JsSetRuntimeMemoryLimit 函数](./jssetruntimememorylimit-function.md)  
*   [JsStartDebugging 函数](./jsstartdebugging-function.md)  
*   [JsStartProfiling 函数](./jsstartprofiling-function.md)  
*   [JsStopProfiling 函数](./jsstopprofiling-function.md)  
*   [JsStrictEquals 函数](./jsstrictequals-function.md)  
*   [JsStringToPointer 函数](./jsstringtopointer-function.md)  
*   [JsValueToVariant 函数](./jsvaluetovariant-function.md)  
*   [JsVariantToValue Function](./jsvarianttovalue-function.md)  

## See also  

*   [Hosting the JavaScript Runtime](./hosting-the-javascript-runtime.md)  
*   [JavaScript Runtime Hosting](../javascript-runtime-hosting.md)  
