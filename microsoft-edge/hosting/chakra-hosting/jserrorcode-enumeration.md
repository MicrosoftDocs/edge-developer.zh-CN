---
description: 从 Chakra 托管 API 返回的错误代码。
title: JsErrorCode 枚举 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e3d1a319872ac69b2acaf19997f3c38f9c04597b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564266"
---
# <span data-ttu-id="fb1f2-103">JsErrorCode 枚举</span><span class="sxs-lookup"><span data-stu-id="fb1f2-103">JsErrorCode Enumeration</span></span>
<span data-ttu-id="fb1f2-104">从 Chakra 托管 API 返回的错误代码。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-104">An error code returned from a Chakra hosting API.</span></span>  
  
## <span data-ttu-id="fb1f2-105">语法</span><span class="sxs-lookup"><span data-stu-id="fb1f2-105">Syntax</span></span>  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## <span data-ttu-id="fb1f2-106">成员</span><span class="sxs-lookup"><span data-stu-id="fb1f2-106">Members</span></span>  
  
### <span data-ttu-id="fb1f2-107">值</span><span class="sxs-lookup"><span data-stu-id="fb1f2-107">Values</span></span>  
  
|<span data-ttu-id="fb1f2-108">名称</span><span class="sxs-lookup"><span data-stu-id="fb1f2-108">Name</span></span>|<span data-ttu-id="fb1f2-109">描述</span><span class="sxs-lookup"><span data-stu-id="fb1f2-109">Description</span></span>|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|<span data-ttu-id="fb1f2-110">无法将上下文置于调试状态，因为它已处于调试状态。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-110">The context cannot be put into a debug state because it is already in a debug state.</span></span>|  
|`JsErrorAlreadyProfilingContext`|<span data-ttu-id="fb1f2-111">上下文无法启动分析，因为它已在分析。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-111">The context cannot start profiling because it is already profiling.</span></span>|  
|`JsErrorArgumentNotObject`|<span data-ttu-id="fb1f2-112">使用非对象值调用在对象值上运行的托管 API。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-112">A hosting API that operates on object values was called with a non-object value.</span></span>|  
|`JsErrorBadSerializedScript`|<span data-ttu-id="fb1f2-113">使用了错误的序列化脚本，或序列化脚本由不同版本的 Chakra 引擎序列化。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-113">A bad serialized script was used, or the serialized script was serialized by a different version of the Chakra engine.</span></span>|  
|`JsErrorCannotDisableExecution`|<span data-ttu-id="fb1f2-114">运行时不支持可靠的脚本中断。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-114">Runtime does not support reliable script interruption.</span></span>|  
|`JsErrorCannotSerializeDebugScript`|<span data-ttu-id="fb1f2-115">无法在调试上下文中序列化脚本。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-115">Scripts cannot be serialized in debug contexts.</span></span>|  
|`JsErrorCategoryEngine`|<span data-ttu-id="fb1f2-116">与引擎本身中出现的错误相关的错误的类别。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-116">Category of errors that relates to errors occurring within the engine itself.</span></span>|  
|`JsErrorCategoryFatal`|<span data-ttu-id="fb1f2-117">错误的类别，表示引擎出现故障。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-117">Category of errors that are fatal and signify failure of the engine.</span></span>|  
|`JsErrorCategoryScript`|<span data-ttu-id="fb1f2-118">与脚本中的错误相关的错误的类别。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-118">Category of errors that relates to errors in a script.</span></span>|  
|`JsErrorCategoryUsage`|<span data-ttu-id="fb1f2-119">与 API 本身的错误用法相关的错误的类别。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-119">Category of errors that relates to incorrect usage of the API itself.</span></span>|  
|`JsErrorFatal`|<span data-ttu-id="fb1f2-120">引擎出现致命错误。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-120">A fatal error in the engine has occurred.</span></span>|  
|`JsErrorHeapEnumInProgress`|<span data-ttu-id="fb1f2-121">堆枚举目前正在脚本上下文中进行。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-121">A heap enumeration is currently underway in the script context.</span></span>|  
|`JsErrorIdleNotEnabled`|<span data-ttu-id="fb1f2-122">当主机未启用空闲处理时给出的空闲通知。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-122">Idle notification given when the host did not enable idle processing.</span></span>|  
|`JsErrorInDisabledState`|<span data-ttu-id="fb1f2-123">运行时处于禁用状态。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-123">The runtime is in a disabled state.</span></span>|  
|`JsErrorInExceptionState`|<span data-ttu-id="fb1f2-124">引擎处于异常状态，并且在清除该异常之前不能调用任何 Api。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-124">The engine is in an exception state and no APIs can be called until the exception is cleared.</span></span>|  
|`JsErrorInObjectBeforeCollectCallback`|<span data-ttu-id="fb1f2-125">在收集回调之前对象中不支持该操作。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-125">The operation is not supported in an object before collect callback.</span></span><br /><br /> <span data-ttu-id="fb1f2-126">仅在 Microsoft Edge 模式下支持此枚举值。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-126">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorInProfileCallback`|<span data-ttu-id="fb1f2-127">脚本上下文位于配置文件回调的中间。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-127">A script context is in the middle of a profile callback.</span></span>|  
|`JsErrorInThreadServiceCallback`|<span data-ttu-id="fb1f2-128">当前正在进行线程服务回调。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-128">A thread service callback is currently underway.</span></span>|  
|`JsErrorInvalidArgument`|<span data-ttu-id="fb1f2-129">托管 API 的参数无效。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-129">An argument to a hosting API was invalid.</span></span>|  
|`JsErrorNoCurrentContext`|<span data-ttu-id="fb1f2-130">托管 API 要求上下文是最新的，但没有当前上下文。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-130">The hosting API requires that a context be current, but there is no current context.</span></span>|  
|`JsErrorNotImplemented`|<span data-ttu-id="fb1f2-131">尚未实现托管 API。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-131">A hosting API is not yet implemented.</span></span>|  
|`JsErrorNullArgument`|<span data-ttu-id="fb1f2-132">托管 API 的参数在不允许使用 null 的上下文中为 null。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-132">An argument to a hosting API was null in a context where null is not allowed.</span></span>|  
|`JsErrorObjectNotInspectable`|<span data-ttu-id="fb1f2-133">无法将对象解包到 `IInspectable` 指针。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-133">Object cannot be unwrapped to `IInspectable` pointer.</span></span><br /><br /> <span data-ttu-id="fb1f2-134">仅在 Microsoft Edge 模式下支持此枚举值。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-134">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorOutOfMemory`|<span data-ttu-id="fb1f2-135">Chakra 引擎内存不足。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-135">The Chakra engine has run out of memory.</span></span>|  
|`JsErrorPropertyNotSymbol`|<span data-ttu-id="fb1f2-136">对符号属性 id 进行操作但使用非符号属性 id 调用的托管 API。`JsGetSymbolFromPropertyId`如果使用非符号属性 id 调用该函数，则返回错误代码。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-136">A hosting API that operates on symbol property ids but was called with a non-symbol property id. The error code is returned by `JsGetSymbolFromPropertyId` if the function is called with non-symbol property id.</span></span><br /><br /> <span data-ttu-id="fb1f2-137">仅在 Microsoft Edge 模式下支持此枚举值。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-137">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorPropertyNotString`|<span data-ttu-id="fb1f2-138">对字符串属性 id 进行操作但使用非字符串属性 id 调用的托管 API。`JsGetPropertyNamefromId`如果使用非字符串属性 id 调用函数，则该错误代码由现有函数返回。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-138">A hosting API that operates on string property ids but was called with a non-string property id. The error code is returned by existing `JsGetPropertyNamefromId` if the function is called with non-string property id.</span></span><br /><br /> <span data-ttu-id="fb1f2-139">仅在 Microsoft Edge 模式下支持此枚举值。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-139">This enumeration value is supported only in Microsoft Edge mode.</span></span>|  
|`JsErrorRuntimeInUse`|<span data-ttu-id="fb1f2-140">无法释放仍在使用的运行时。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-140">A runtime that is still in use cannot be disposed.</span></span>|  
|`JsErrorScriptCompile`|<span data-ttu-id="fb1f2-141">JavaScript 无法编译。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-141">JavaScript failed to compile.</span></span>|  
|`JsErrorScriptEvalDisabled`|<span data-ttu-id="fb1f2-142">脚本已终止，因为它尝试使用 `eval` 或 `function` 已禁用 eval。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-142">A script was terminated because it tried to use `eval` or `function` and eval was disabled.</span></span>|  
|`JsErrorScriptException`|<span data-ttu-id="fb1f2-143">运行脚本时发生 JavaScript 异常。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-143">A JavaScript exception occurred while running a script.</span></span>|  
|`JsErrorScriptTerminated`|<span data-ttu-id="fb1f2-144">由于请求暂停运行时，脚本被终止。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-144">A script was terminated due to a request to suspend a runtime.</span></span>|  
|`JsErrorWrongRuntime`|<span data-ttu-id="fb1f2-145">使用在不同 JavaScript 运行时上创建的对象调用了托管 API。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-145">A hosting API was called with object created on different JavaScript runtime.</span></span>|  
|`JsErrorWrongThread`|<span data-ttu-id="fb1f2-146">在错误的线程上调用了托管 API。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-146">A hosting API was called on the wrong thread.</span></span>|  
|`JsNoError`|<span data-ttu-id="fb1f2-147">成功错误代码。</span><span class="sxs-lookup"><span data-stu-id="fb1f2-147">Success error code.</span></span>|  
  
## <span data-ttu-id="fb1f2-148">要求</span><span class="sxs-lookup"><span data-stu-id="fb1f2-148">Requirements</span></span>  
 <span data-ttu-id="fb1f2-149">**页眉：** jsrt</span><span class="sxs-lookup"><span data-stu-id="fb1f2-149">**Header:** jsrt.h</span></span>  
  
## <span data-ttu-id="fb1f2-150">另请参阅</span><span class="sxs-lookup"><span data-stu-id="fb1f2-150">See Also</span></span>  
 [<span data-ttu-id="fb1f2-151">参考（JavaScript 运行时）</span><span class="sxs-lookup"><span data-stu-id="fb1f2-151">Reference (JavaScript Runtime)</span></span>](../chakra-hosting/reference-javascript-runtime.md)