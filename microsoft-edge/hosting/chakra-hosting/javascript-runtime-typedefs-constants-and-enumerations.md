---
description: JavaScript 运行时（JsRT） typedef、常量和枚举支持将脚本功能添加到在 Windows 上运行的桌面和服务器端应用程序。
title: JavaScript 运行时 Typedef、常量和枚举
ms.date: 06/08/2020
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 1aa107ed-e144-4947-b5bb-90284a537174
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.openlocfilehash: 20c52c3a958f6ba14fbfbdcdad794747a9c34949
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752260"
---
# <span data-ttu-id="fc7af-103">JavaScript 运行时 Typedef、常量和枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-103">JavaScript Runtime Typedefs, Constants, and Enumerations</span></span>  

[!INCLUDE [deprecation-note](../includes/deprecation-note.md)]  

<span data-ttu-id="fc7af-104">JavaScript 运行时（JsRT） typedef、常量和枚举支持将脚本功能添加到在 Windows 上运行的桌面和服务器端应用程序。</span><span class="sxs-lookup"><span data-stu-id="fc7af-104">JavaScript Runtime (JsRT) typedefs, constants, and enumerations support adding scripting capabilities to desktop and server-side applications running on Windows.</span></span>  

## <span data-ttu-id="fc7af-105">本部分内容</span><span class="sxs-lookup"><span data-stu-id="fc7af-105">In this section</span></span>  

<span data-ttu-id="fc7af-106">以下全局 typedef 支持 JsRT 托管：</span><span class="sxs-lookup"><span data-stu-id="fc7af-106">The following global typedefs support JsRT hosting:</span></span>  

*   [<span data-ttu-id="fc7af-107">JsBackgroundWorkItemCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-107">JsBackgroundWorkItemCallback Typedef</span></span>](./jsbackgroundworkitemcallback-typedef.md)  
*   [<span data-ttu-id="fc7af-108">JsBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-108">JsBeforeCollectCallback Typedef</span></span>](./jsbeforecollectcallback-typedef.md)  
*   [<span data-ttu-id="fc7af-109">JsContextRef Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-109">JsContextRef Typedef</span></span>](./jscontextref-typedef.md)  
*   [<span data-ttu-id="fc7af-110">JsFinalizeCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-110">JsFinalizeCallback Typedef</span></span>](./jsfinalizecallback-typedef.md)  
*   [<span data-ttu-id="fc7af-111">JsMemoryAllocationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-111">JsMemoryAllocationCallback Typedef</span></span>](./jsmemoryallocationcallback-typedef.md)  
*   [<span data-ttu-id="fc7af-112">JsNativeFunction Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-112">JsNativeFunction Typedef</span></span>](./jsnativefunction-typedef.md)  
*   [<span data-ttu-id="fc7af-113">JsObjectBeforeCollectCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-113">JsObjectBeforeCollectCallback Typedef</span></span>](./jsobjectbeforecollectcallback-typedef.md)  
*   [<span data-ttu-id="fc7af-114">JsProjectionCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-114">JsProjectionCallback Typedef</span></span>](./jsprojectioncallback-typedef.md)  
*   [<span data-ttu-id="fc7af-115">JsProjectionCallbackContext Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-115">JsProjectionCallbackContext Typedef</span></span>](./jsprojectioncallbackcontext-typedef.md)  
*   [<span data-ttu-id="fc7af-116">JsProjectionEnqueueCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-116">JsProjectionEnqueueCallback Typedef</span></span>](./jsprojectionenqueuecallback-typedef.md)  
*   [<span data-ttu-id="fc7af-117">JsPromiseContinuationCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-117">JsPromiseContinuationCallback Typedef</span></span>](./jspromisecontinuationcallback-typedef.md)  
*   [<span data-ttu-id="fc7af-118">JsPropertyIdRef Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-118">JsPropertyIdRef Typedef</span></span>](./jspropertyidref-typedef.md)  
*   [<span data-ttu-id="fc7af-119">JsRef Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-119">JsRef Typedef</span></span>](./jsref-typedef.md)  
*   [<span data-ttu-id="fc7af-120">JsRuntimeHandle Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-120">JsRuntimeHandle Typedef</span></span>](./jsruntimehandle-typedef.md)  
*   [<span data-ttu-id="fc7af-121">JsSerializedScriptLoadSourceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-121">JsSerializedScriptLoadSourceCallback Typedef</span></span>](./jsserializedscriptloadsourcecallback-typedef.md)  
*   [<span data-ttu-id="fc7af-122">JsSerializedScriptUnloadCallback typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-122">JsSerializedScriptUnloadCallback typedef</span></span>](./jsserializedscriptunloadcallback-typedef.md)  
*   [<span data-ttu-id="fc7af-123">JsSourceContext Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-123">JsSourceContext Typedef</span></span>](./jssourcecontext-typedef.md)  
*   [<span data-ttu-id="fc7af-124">JsThreadServiceCallback Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-124">JsThreadServiceCallback Typedef</span></span>](./jsthreadservicecallback-typedef.md)  
*   [<span data-ttu-id="fc7af-125">JsValueRef Typedef</span><span class="sxs-lookup"><span data-stu-id="fc7af-125">JsValueRef Typedef</span></span>](./jsvalueref-typedef.md)  

<span data-ttu-id="fc7af-126">以下常量支持 JsRT 托管：</span><span class="sxs-lookup"><span data-stu-id="fc7af-126">The following constants support JsRT hosting:</span></span>  

*   [<span data-ttu-id="fc7af-127">JS_INVALID_PROPERTYID 常量</span><span class="sxs-lookup"><span data-stu-id="fc7af-127">JS_INVALID_PROPERTYID Constant</span></span>](./js-invalid-propertyid-constant.md)  
*   [<span data-ttu-id="fc7af-128">JS_INVALID_REFERENCE 常量</span><span class="sxs-lookup"><span data-stu-id="fc7af-128">JS_INVALID_REFERENCE Constant</span></span>](./js-invalid-reference-constant.md)  
*   [<span data-ttu-id="fc7af-129">JS_INVALID_RUNTIME_HANDLE 常量</span><span class="sxs-lookup"><span data-stu-id="fc7af-129">JS_INVALID_RUNTIME_HANDLE Constant</span></span>](./js-invalid-runtime-handle-constant.md)  
*   [<span data-ttu-id="fc7af-130">JS_SOURCE_CONTEXT_NONE 常量</span><span class="sxs-lookup"><span data-stu-id="fc7af-130">JS_SOURCE_CONTEXT_NONE Constant</span></span>](./js-source-context-none-constant.md)  

<span data-ttu-id="fc7af-131">以下枚举支持 JsRT 托管：</span><span class="sxs-lookup"><span data-stu-id="fc7af-131">The following enumerations support JsRT hosting:</span></span>  

*   [<span data-ttu-id="fc7af-132">JsErrorCode 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-132">JsErrorCode Enumeration</span></span>](./jserrorcode-enumeration.md)  
*   [<span data-ttu-id="fc7af-133">JsMemoryEventType 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-133">JsMemoryEventType Enumeration</span></span>](./jsmemoryeventtype-enumeration.md)  
*   [<span data-ttu-id="fc7af-134">JsPropertyIdType 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-134">JsPropertyIdType Enumeration</span></span>](./jspropertyidtype-enumeration.md)  
*   [<span data-ttu-id="fc7af-135">JsRuntimeAttributes 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-135">JsRuntimeAttributes Enumeration</span></span>](./jsruntimeattributes-enumeration.md)  
*   [<span data-ttu-id="fc7af-136">JsRuntimeVersion 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-136">JsRuntimeVersion Enumeration</span></span>](./jsruntimeversion-enumeration.md)  
*   [<span data-ttu-id="fc7af-137">JsTypedArrayType 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-137">JsTypedArrayType Enumeration</span></span>](./jstypedarraytype-enumeration.md)  
*   [<span data-ttu-id="fc7af-138">JsValueType 枚举</span><span class="sxs-lookup"><span data-stu-id="fc7af-138">JsValueType Enumeration</span></span>](./jsvaluetype-enumeration.md)  

## <span data-ttu-id="fc7af-139">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fc7af-139">See also</span></span>  

*   [<span data-ttu-id="fc7af-140">托管 JavaScript 运行时</span><span class="sxs-lookup"><span data-stu-id="fc7af-140">Hosting the JavaScript Runtime</span></span>](./hosting-the-javascript-runtime.md)  
*   [<span data-ttu-id="fc7af-141">JavaScript 运行时托管</span><span class="sxs-lookup"><span data-stu-id="fc7af-141">JavaScript Runtime Hosting</span></span>](../javascript-runtime-hosting.md)  
