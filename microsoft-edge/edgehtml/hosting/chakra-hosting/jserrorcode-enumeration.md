---
description: 从 Chakra 托管 API 返回的错误代码。
title: JsErrorCode 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b0a4aa7b47070bd5c8c7fe48cdbecf0dbefa9aa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232336"
---
# <span data-ttu-id="e704e-103">JsErrorCode 枚举</span><span class="sxs-lookup"><span data-stu-id="e704e-103">JsErrorCode Enumeration</span></span>

<span data-ttu-id="e704e-104">从 Chakra 托管 API 返回的错误代码。</span><span class="sxs-lookup"><span data-stu-id="e704e-104">An error code returned from a Chakra hosting API.</span></span>  
  
## <span data-ttu-id="e704e-105">语法</span><span class="sxs-lookup"><span data-stu-id="e704e-105">Syntax</span></span>  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## <span data-ttu-id="e704e-106">成员</span><span class="sxs-lookup"><span data-stu-id="e704e-106">Members</span></span>  
  
### <span data-ttu-id="e704e-107">值</span><span class="sxs-lookup"><span data-stu-id="e704e-107">Values</span></span>  
  
|<span data-ttu-id="e704e-108">名称</span><span class="sxs-lookup"><span data-stu-id="e704e-108">Name</span></span>|<span data-ttu-id="e704e-109">描述</span><span class="sxs-lookup"><span data-stu-id="e704e-109">Description</span></span>|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|<span data-ttu-id="e704e-110">无法将上下文置于调试状态，因为它已进入调试状态。</span><span class="sxs-lookup"><span data-stu-id="e704e-110">The context cannot be put into a debug state because it is already in a debug state.</span></span>|  
|`JsErrorAlreadyProfilingContext`|<span data-ttu-id="e704e-111">上下文无法启动分析，因为它已经在分析。</span><span class="sxs-lookup"><span data-stu-id="e704e-111">The context cannot start profiling because it is already profiling.</span></span>|  
|`JsErrorArgumentNotObject`|<span data-ttu-id="e704e-112">使用非对象值调用了对对象值进行操作的宿主 API。</span><span class="sxs-lookup"><span data-stu-id="e704e-112">A hosting API that operates on object values was called with a non-object value.</span></span>|  
|`JsErrorBadSerializedScript`|<span data-ttu-id="e704e-113">使用了错误的序列化脚本，或者序列化脚本被不同版本的 Chakra 引擎序列化。</span><span class="sxs-lookup"><span data-stu-id="e704e-113">A bad serialized script was used, or the serialized script was serialized by a different version of the Chakra engine.</span></span>|  
|`JsErrorCannotDisableExecution`|<span data-ttu-id="e704e-114">运行时不支持可靠的脚本中断。</span><span class="sxs-lookup"><span data-stu-id="e704e-114">Runtime does not support reliable script interruption.</span></span>|  
|`JsErrorCannotSerializeDebugScript`|<span data-ttu-id="e704e-115">脚本无法在调试上下文中进行序列化。</span><span class="sxs-lookup"><span data-stu-id="e704e-115">Scripts cannot be serialized in debug contexts.</span></span>|  
|`JsErrorCategoryEngine`|<span data-ttu-id="e704e-116">与引擎本身发生的错误相关的错误类别。</span><span class="sxs-lookup"><span data-stu-id="e704e-116">Category of errors that relates to errors occurring within the engine itself.</span></span>|  
|`JsErrorCategoryFatal`|<span data-ttu-id="e704e-117">表示引擎故障的致命错误类别。</span><span class="sxs-lookup"><span data-stu-id="e704e-117">Category of errors that are fatal and signify failure of the engine.</span></span>|  
|`JsErrorCategoryScript`|<span data-ttu-id="e704e-118">与脚本中的错误相关的错误类别。</span><span class="sxs-lookup"><span data-stu-id="e704e-118">Category of errors that relates to errors in a script.</span></span>|  
|`JsErrorCategoryUsage`|<span data-ttu-id="e704e-119">与 API 本身的错误使用相关的错误类别。</span><span class="sxs-lookup"><span data-stu-id="e704e-119">Category of errors that relates to incorrect usage of the API itself.</span></span>|  
|`JsErrorFatal`|<span data-ttu-id="e704e-120">引擎中发生了致命错误。</span><span class="sxs-lookup"><span data-stu-id="e704e-120">A fatal error in the engine has occurred.</span></span>|  
|`JsErrorHeapEnumInProgress`|<span data-ttu-id="e704e-121">堆枚举当前正在脚本上下文中进行。</span><span class="sxs-lookup"><span data-stu-id="e704e-121">A heap enumeration is currently underway in the script context.</span></span>|  
|`JsErrorIdleNotEnabled`|<span data-ttu-id="e704e-122">主机未启用空闲处理时给定的空闲通知。</span><span class="sxs-lookup"><span data-stu-id="e704e-122">Idle notification given when the host did not enable idle processing.</span></span>|  
|`JsErrorInDisabledState`|<span data-ttu-id="e704e-123">运行时处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="e704e-123">The runtime is in a disabled state.</span></span>|  
|`JsErrorInExceptionState`|<span data-ttu-id="e704e-124">引擎在异常状态中，在清除异常之前无法调用任何 API。</span><span class="sxs-lookup"><span data-stu-id="e704e-124">The engine is in an exception state and no APIs can be called until the exception is cleared.</span></span>|  
|`JsErrorInObjectBeforeCollectCallback`|<span data-ttu-id="e704e-125">在收集回调之前，对象不支持该操作。</span><span class="sxs-lookup"><span data-stu-id="e704e-125">The operation is not supported in an object before collect callback.</span></span><br /><br /> <span data-ttu-id="e704e-126">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e704e-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorInProfileCallback`|<span data-ttu-id="e704e-127">脚本上下文位于配置文件回调的中间。</span><span class="sxs-lookup"><span data-stu-id="e704e-127">A script context is in the middle of a profile callback.</span></span>|  
|`JsErrorInThreadServiceCallback`|<span data-ttu-id="e704e-128">线程服务回调当前正在进行中。</span><span class="sxs-lookup"><span data-stu-id="e704e-128">A thread service callback is currently underway.</span></span>|  
|`JsErrorInvalidArgument`|<span data-ttu-id="e704e-129">宿主 API 的参数无效。</span><span class="sxs-lookup"><span data-stu-id="e704e-129">An argument to a hosting API was invalid.</span></span>|  
|`JsErrorNoCurrentContext`|<span data-ttu-id="e704e-130">托管 API 要求上下文是最新的，但没有当前上下文。</span><span class="sxs-lookup"><span data-stu-id="e704e-130">The hosting API requires that a context be current, but there is no current context.</span></span>|  
|`JsErrorNotImplemented`|<span data-ttu-id="e704e-131">托管 API 尚未实现。</span><span class="sxs-lookup"><span data-stu-id="e704e-131">A hosting API is not yet implemented.</span></span>|  
|`JsErrorNullArgument`|<span data-ttu-id="e704e-132">在不允许 null 的上下文中，宿主 API 的参数为 null。</span><span class="sxs-lookup"><span data-stu-id="e704e-132">An argument to a hosting API was null in a context where null is not allowed.</span></span>|  
|`JsErrorObjectNotInspectable`|<span data-ttu-id="e704e-133">对象不能解包到 `IInspectable` 指针。</span><span class="sxs-lookup"><span data-stu-id="e704e-133">Object cannot be unwrapped to `IInspectable` pointer.</span></span><br /><br /> <span data-ttu-id="e704e-134">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e704e-134">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorOutOfMemory`|<span data-ttu-id="e704e-135">The Chakra engine has run out of memory.</span><span class="sxs-lookup"><span data-stu-id="e704e-135">The Chakra engine has run out of memory.</span></span>|  
|`JsErrorPropertyNotSymbol`|<span data-ttu-id="e704e-136">对符号属性 ID 进行操作但使用非符号属性 ID 调用的托管 API。如果使用非符号属性 ID 调用函数，则返回 `JsGetSymbolFromPropertyId` 错误代码。</span><span class="sxs-lookup"><span data-stu-id="e704e-136">A hosting API that operates on symbol property ids but was called with a non-symbol property id. The error code is returned by `JsGetSymbolFromPropertyId` if the function is called with non-symbol property id.</span></span><br /><br /> <span data-ttu-id="e704e-137">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e704e-137">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorPropertyNotString`|<span data-ttu-id="e704e-138">对字符串属性 ID 进行操作但使用非字符串属性 ID 调用的托管 API。如果用非字符串属性 ID 调用函数，则现有函数将返回 `JsGetPropertyNamefromId` 错误代码。</span><span class="sxs-lookup"><span data-stu-id="e704e-138">A hosting API that operates on string property ids but was called with a non-string property id. The error code is returned by existing `JsGetPropertyNamefromId` if the function is called with non-string property id.</span></span><br /><br /> <span data-ttu-id="e704e-139">此枚举值仅在 Microsoft Edge 模式下受支持。</span><span class="sxs-lookup"><span data-stu-id="e704e-139">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorRuntimeInUse`|<span data-ttu-id="e704e-140">无法释放仍在使用的运行时。</span><span class="sxs-lookup"><span data-stu-id="e704e-140">A runtime that is still in use cannot be disposed.</span></span>|  
|`JsErrorScriptCompile`|<span data-ttu-id="e704e-141">JavaScript 无法编译。</span><span class="sxs-lookup"><span data-stu-id="e704e-141">JavaScript failed to compile.</span></span>|  
|`JsErrorScriptEvalDisabled`|<span data-ttu-id="e704e-142">脚本因尝试使用或 eval 被禁用 `eval` `function` 而终止。</span><span class="sxs-lookup"><span data-stu-id="e704e-142">A script was terminated because it tried to use `eval` or `function` and eval was disabled.</span></span>|  
|`JsErrorScriptException`|<span data-ttu-id="e704e-143">运行脚本时发生 JavaScript 异常。</span><span class="sxs-lookup"><span data-stu-id="e704e-143">A JavaScript exception occurred while running a script.</span></span>|  
|`JsErrorScriptTerminated`|<span data-ttu-id="e704e-144">由于请求暂停运行时，脚本已终止。</span><span class="sxs-lookup"><span data-stu-id="e704e-144">A script was terminated due to a request to suspend a runtime.</span></span>|  
|`JsErrorWrongRuntime`|<span data-ttu-id="e704e-145">使用在不同的 JavaScript 运行时上创建的对象调用了托管 API。</span><span class="sxs-lookup"><span data-stu-id="e704e-145">A hosting API was called with object created on different JavaScript runtime.</span></span>|  
|`JsErrorWrongThread`|<span data-ttu-id="e704e-146">在错误的线程上调用了宿主 API。</span><span class="sxs-lookup"><span data-stu-id="e704e-146">A hosting API was called on the wrong thread.</span></span>|  
|`JsNoError`|<span data-ttu-id="e704e-147">成功错误代码。</span><span class="sxs-lookup"><span data-stu-id="e704e-147">Success error code.</span></span>|  
  
## <span data-ttu-id="e704e-148">要求</span><span class="sxs-lookup"><span data-stu-id="e704e-148">Requirements</span></span>  
 <span data-ttu-id="e704e-149">**标头** ：jsrt.h</span><span class="sxs-lookup"><span data-stu-id="e704e-149">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="e704e-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e704e-150">See Also</span></span>  
 [<span data-ttu-id="e704e-151">应用 (JavaScript Runtime)</span><span class="sxs-lookup"><span data-stu-id="e704e-151">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)
