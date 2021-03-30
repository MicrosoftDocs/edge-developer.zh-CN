---
description: DevTools 协议版本 0.1 (运行时域) EdgeHTML 版本参考。  运行时域通过远程评估和镜像对象公开 JavaScript 运行时。  评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。  原始对象在内存中进行维护，除非它们已显式释放。
title: '运行时域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9aa87c1c289452844ef3442811f84881fc752b4
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397690"
---
# <a name="runtime-domain---devtools-protocol-version-01-edgehtml"></a><span data-ttu-id="af79a-106">运行时域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="af79a-106">Runtime Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="af79a-107">运行时域通过远程评估和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="af79a-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span>  <span data-ttu-id="af79a-108">评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。</span><span class="sxs-lookup"><span data-stu-id="af79a-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span>  <span data-ttu-id="af79a-109">原始对象在内存中进行维护，除非它们已显式释放。</span><span class="sxs-lookup"><span data-stu-id="af79a-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>  

| <span data-ttu-id="af79a-110">分类</span><span class="sxs-lookup"><span data-stu-id="af79a-110">Classification</span></span> | <span data-ttu-id="af79a-111">成员</span><span class="sxs-lookup"><span data-stu-id="af79a-111">Members</span></span> |  
|:--- |:--- |  
| [<span data-ttu-id="af79a-112">方法</span><span class="sxs-lookup"><span data-stu-id="af79a-112">Methods</span></span>](#methods) | <span data-ttu-id="af79a-113">[enable](#enable)， [disable](#disable)， [evaluate](#evaluate)， [callFunctionOn](#callfunctionon)， [getProperties](#getproperties)</span><span class="sxs-lookup"><span data-stu-id="af79a-113">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties)</span></span> |  
| [<span data-ttu-id="af79a-114">事件</span><span class="sxs-lookup"><span data-stu-id="af79a-114">Events</span></span>](#events) | <span data-ttu-id="af79a-115">[executionContextsCleared](#executioncontextscleared)， [exceptionThrown](#exceptionthrown)</span><span class="sxs-lookup"><span data-stu-id="af79a-115">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span></span> |  
| [<span data-ttu-id="af79a-116">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-116">Types</span></span>](#types) | <span data-ttu-id="af79a-117">[ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="af79a-117">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |  

## <a name="methods"></a><span data-ttu-id="af79a-118">方法</span><span class="sxs-lookup"><span data-stu-id="af79a-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="af79a-119">“启用”</span><span class="sxs-lookup"><span data-stu-id="af79a-119">enable</span></span>  

<span data-ttu-id="af79a-120">启用事件 `executionContextsCleared` 报告。</span><span class="sxs-lookup"><span data-stu-id="af79a-120">Enables reporting of the `executionContextsCleared` event.</span></span>  

&nbsp;  

---  

### <a name="disable"></a><span data-ttu-id="af79a-121">“禁用”</span><span class="sxs-lookup"><span data-stu-id="af79a-121">disable</span></span>  

<span data-ttu-id="af79a-122">禁用事件 `executionContextsCleared` 报告。</span><span class="sxs-lookup"><span data-stu-id="af79a-122">Disables reporting of the `executionContextsCleared` event.</span></span>  

&nbsp;  

---  

### <a name="evaluate"></a><span data-ttu-id="af79a-123">evaluate</span><span class="sxs-lookup"><span data-stu-id="af79a-123">evaluate</span></span>  

<span data-ttu-id="af79a-124">计算全局对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="af79a-124">Evaluates expression on global object.</span></span>  

| <span data-ttu-id="af79a-125">参数</span><span class="sxs-lookup"><span data-stu-id="af79a-125">Parameters</span></span> | <span data-ttu-id="af79a-126">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-126">Type</span></span> | <span data-ttu-id="af79a-127">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-127">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-128">表达式</span><span class="sxs-lookup"><span data-stu-id="af79a-128">expression</span></span> | `string` | <span data-ttu-id="af79a-129">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="af79a-129">Expression to evaluate.</span></span> |  
| <span data-ttu-id="af79a-130">无提示 \(可选\) </span><span class="sxs-lookup"><span data-stu-id="af79a-130">silent \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-131">在静默模式下，不会报告在评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="af79a-131">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span>  <span data-ttu-id="af79a-132">覆盖 `setPauseOnException` 状态。</span><span class="sxs-lookup"><span data-stu-id="af79a-132">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="af79a-133">contextId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-133">contextId \(optional\)</span></span> | [<span data-ttu-id="af79a-134">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="af79a-134">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="af79a-135">指定要执行评估的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="af79a-135">Specifies in which execution context to perform evaluation.</span></span>  <span data-ttu-id="af79a-136">如果省略该参数，将在所检查页面的上下文中执行计算。</span><span class="sxs-lookup"><span data-stu-id="af79a-136">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span> |  
| <span data-ttu-id="af79a-137">returnByValue \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-137">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-138">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="af79a-138">Whether the result is expected to be a JSON object that should be sent by value.</span></span> |  
| <span data-ttu-id="af79a-139">awaitPromise \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-139">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-140">是否应为 `await` 生成的值执行，并解决等待的承诺后返回。</span><span class="sxs-lookup"><span data-stu-id="af79a-140">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  

| <span data-ttu-id="af79a-141">返回</span><span class="sxs-lookup"><span data-stu-id="af79a-141">Returns</span></span> | <span data-ttu-id="af79a-142">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-142">Type</span></span> | <span data-ttu-id="af79a-143">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-143">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-144">result</span><span class="sxs-lookup"><span data-stu-id="af79a-144">result</span></span> | [<span data-ttu-id="af79a-145">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-145">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-146">评估结果。</span><span class="sxs-lookup"><span data-stu-id="af79a-146">Evaluation result.</span></span> |  

---  

### <a name="callfunctionon"></a><span data-ttu-id="af79a-147">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="af79a-147">callFunctionOn</span></span>  

<span data-ttu-id="af79a-148">调用给定对象上具有给定声明的函数。</span><span class="sxs-lookup"><span data-stu-id="af79a-148">Calls function with given declaration on the given object.</span></span>  <span data-ttu-id="af79a-149">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="af79a-149">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="af79a-150">参数</span><span class="sxs-lookup"><span data-stu-id="af79a-150">Parameters</span></span> | <span data-ttu-id="af79a-151">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-151">Type</span></span> | <span data-ttu-id="af79a-152">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-152">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-153">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="af79a-153">functionDeclaration</span></span> | `string` | <span data-ttu-id="af79a-154">要调用的函数的声明。</span><span class="sxs-lookup"><span data-stu-id="af79a-154">Declaration of the function to call.</span></span> |  
| <span data-ttu-id="af79a-155">objectId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-155">objectId \(optional\)</span></span> | [<span data-ttu-id="af79a-156">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="af79a-156">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="af79a-157">要调用函数的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="af79a-157">Identifier of the object to call function on.</span></span>  <span data-ttu-id="af79a-158">或者 `objectId` `executionContextId` 应指定。</span><span class="sxs-lookup"><span data-stu-id="af79a-158">Either `objectId` or `executionContextId` should be specified.</span></span>  <span data-ttu-id="af79a-159">objectId 必须来自 Runtime.evaluate () 函数。</span><span class="sxs-lookup"><span data-stu-id="af79a-159">objectId must be from the Runtime.evaluate() function.</span></span> |  
| <span data-ttu-id="af79a-160">参数 \(可选\) </span><span class="sxs-lookup"><span data-stu-id="af79a-160">arguments \(optional\)</span></span> | [<span data-ttu-id="af79a-161">CallArgument[]</span><span class="sxs-lookup"><span data-stu-id="af79a-161">CallArgument[]</span></span>](#callargument) | <span data-ttu-id="af79a-162">调用参数。</span><span class="sxs-lookup"><span data-stu-id="af79a-162">Call arguments.</span></span>  <span data-ttu-id="af79a-163">所有调用参数都必须属于与目标对象相同的 JavaScript 世界。</span><span class="sxs-lookup"><span data-stu-id="af79a-163">All call arguments must belong to the same JavaScript world as the target object.</span></span> |  
| <span data-ttu-id="af79a-164">无提示 \(可选\) </span><span class="sxs-lookup"><span data-stu-id="af79a-164">silent \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-165">在静默模式下，不会报告在评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="af79a-165">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span>  <span data-ttu-id="af79a-166">覆盖 `setPauseOnException` 状态。</span><span class="sxs-lookup"><span data-stu-id="af79a-166">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="af79a-167">returnByValue \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-167">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-168">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="af79a-168">Whether the result is expected to be a JSON object which should be sent by value.</span></span> |  
| <span data-ttu-id="af79a-169">awaitPromise \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-169">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-170">是否应为 `await` 生成的值执行，并解决等待的承诺后返回。</span><span class="sxs-lookup"><span data-stu-id="af79a-170">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  

| <span data-ttu-id="af79a-171">返回</span><span class="sxs-lookup"><span data-stu-id="af79a-171">Returns</span></span> | <span data-ttu-id="af79a-172">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-172">Type</span></span> | <span data-ttu-id="af79a-173">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-173">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-174">result</span><span class="sxs-lookup"><span data-stu-id="af79a-174">result</span></span> | [<span data-ttu-id="af79a-175">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-175">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-176">呼叫结果。</span><span class="sxs-lookup"><span data-stu-id="af79a-176">Call result.</span></span> |  

---  

### <a name="getproperties"></a><span data-ttu-id="af79a-177">getProperties</span><span class="sxs-lookup"><span data-stu-id="af79a-177">getProperties</span></span>  

<span data-ttu-id="af79a-178">返回给定对象的属性。</span><span class="sxs-lookup"><span data-stu-id="af79a-178">Returns properties of a given object.</span></span>  <span data-ttu-id="af79a-179">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="af79a-179">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="af79a-180">参数</span><span class="sxs-lookup"><span data-stu-id="af79a-180">Parameters</span></span> | <span data-ttu-id="af79a-181">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-181">Type</span></span> | <span data-ttu-id="af79a-182">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-182">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-183">objectId</span><span class="sxs-lookup"><span data-stu-id="af79a-183">objectId</span></span> | [<span data-ttu-id="af79a-184">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="af79a-184">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="af79a-185">要返回其属性的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="af79a-185">Identifier of the object to return properties for.</span></span>  `objectId` <span data-ttu-id="af79a-186">必须来自 `Debugger.evaluateOnCallFrame()` 函数。</span><span class="sxs-lookup"><span data-stu-id="af79a-186">must be from the `Debugger.evaluateOnCallFrame()` function.</span></span> |  
| <span data-ttu-id="af79a-187">ownProperties \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-187">ownProperties \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-188">If `true` ，则返回仅属于元素本身的属性，而不是其原型链的属性。</span><span class="sxs-lookup"><span data-stu-id="af79a-188">If `true`, returns properties belonging only to the element itself, not to its prototype chain.</span></span> |  
| <span data-ttu-id="af79a-189">accessorPropertiesOnly \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-189">accessorPropertiesOnly \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-190">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="af79a-190">**Experimental**.</span></span>  <span data-ttu-id="af79a-191">If `true` ， returns accessor properties \(with getter/setter\) only; internal properties are not returned either.</span><span class="sxs-lookup"><span data-stu-id="af79a-191">If `true`, returns accessor properties \(with getter/setter\) only; internal properties are not returned either.</span></span> |  

| <span data-ttu-id="af79a-192">返回</span><span class="sxs-lookup"><span data-stu-id="af79a-192">Returns</span></span> | <span data-ttu-id="af79a-193">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-193">Type</span></span> | <span data-ttu-id="af79a-194">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-194">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-195">result</span><span class="sxs-lookup"><span data-stu-id="af79a-195">result</span></span> | [<span data-ttu-id="af79a-196">PropertyDescriptor[]</span><span class="sxs-lookup"><span data-stu-id="af79a-196">PropertyDescriptor[]</span></span>](#propertydescriptor) | <span data-ttu-id="af79a-197">对象属性。</span><span class="sxs-lookup"><span data-stu-id="af79a-197">Object properties.</span></span> |  

---  

## <a name="events"></a><span data-ttu-id="af79a-198">事件</span><span class="sxs-lookup"><span data-stu-id="af79a-198">Events</span></span>  

### <a name="executioncontextscleared"></a><span data-ttu-id="af79a-199">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="af79a-199">executionContextsCleared</span></span>  

<span data-ttu-id="af79a-200">在浏览器中清除所有 executionContexts 时发出。</span><span class="sxs-lookup"><span data-stu-id="af79a-200">Issued when all executionContexts were cleared in browser.</span></span>  

&nbsp;  

---  

### <a name="exceptionthrown"></a><span data-ttu-id="af79a-201">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="af79a-201">exceptionThrown</span></span>  

<span data-ttu-id="af79a-202">引发和未处理异常时发出。</span><span class="sxs-lookup"><span data-stu-id="af79a-202">Issued when exception was thrown and unhandled.</span></span>  

| <span data-ttu-id="af79a-203">参数</span><span class="sxs-lookup"><span data-stu-id="af79a-203">Parameters</span></span> | <span data-ttu-id="af79a-204">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-204">Type</span></span> | <span data-ttu-id="af79a-205">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-205">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-206">timestamp</span><span class="sxs-lookup"><span data-stu-id="af79a-206">timestamp</span></span> | [<span data-ttu-id="af79a-207">时间戳</span><span class="sxs-lookup"><span data-stu-id="af79a-207">Timestamp</span></span>](#timestamp) | <span data-ttu-id="af79a-208">异常的时间戳。</span><span class="sxs-lookup"><span data-stu-id="af79a-208">Timestamp of the exception.</span></span> |  
| <span data-ttu-id="af79a-209">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="af79a-209">exceptionDetails</span></span> | [<span data-ttu-id="af79a-210">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="af79a-210">ExceptionDetails</span></span>](#exceptiondetails) | &nbsp; |  

---  

## <a name="types"></a><span data-ttu-id="af79a-211">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-211">Types</span></span>  

### <a name="scriptid-string"></a><span data-ttu-id="af79a-212">ScriptId 字符串</span><span class="sxs-lookup"><span data-stu-id="af79a-212">ScriptId string</span></span>  

<a name="scriptid"></a>  

<span data-ttu-id="af79a-213">唯一脚本标识符。</span><span class="sxs-lookup"><span data-stu-id="af79a-213">Unique script identifier.</span></span>  

&nbsp;  

---  

### <a name="remoteobjectid-string"></a><span data-ttu-id="af79a-214">RemoteObjectId 字符串</span><span class="sxs-lookup"><span data-stu-id="af79a-214">RemoteObjectId string</span></span>  

<a name="remoteobjectid"></a>  

<span data-ttu-id="af79a-215">唯一对象标识符。</span><span class="sxs-lookup"><span data-stu-id="af79a-215">Unique object identifier.</span></span>  

&nbsp;  

---  

### <a name="unserializablevalue-string"></a><span data-ttu-id="af79a-216">UnserializableValue 字符串</span><span class="sxs-lookup"><span data-stu-id="af79a-216">UnserializableValue string</span></span>  

<a name="unserializablevalue"></a>  

<span data-ttu-id="af79a-217">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="af79a-217">Primitive value which cannot be JSON-stringified.</span></span>  

##### <a name="allowed-values"></a><span data-ttu-id="af79a-218">允许的值</span><span class="sxs-lookup"><span data-stu-id="af79a-218">Allowed Values</span></span>  

`Infinity`<span data-ttu-id="af79a-219">, `NaN`, `-Infinity`,</span><span class="sxs-lookup"><span data-stu-id="af79a-219">, `NaN`, `-Infinity`,</span></span> `-0`  

---  

### <a name="remoteobject-object"></a><span data-ttu-id="af79a-220">RemoteObject 对象</span><span class="sxs-lookup"><span data-stu-id="af79a-220">RemoteObject object</span></span>  

<a name="remoteobject"></a>  

<span data-ttu-id="af79a-221">引用原始 JavaScript 对象的镜像对象。</span><span class="sxs-lookup"><span data-stu-id="af79a-221">Mirror object referencing original JavaScript object.</span></span>  

| <span data-ttu-id="af79a-222">属性</span><span class="sxs-lookup"><span data-stu-id="af79a-222">Properties</span></span> | <span data-ttu-id="af79a-223">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-223">Type</span></span> | <span data-ttu-id="af79a-224">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-224">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-225">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-225">type</span></span> | `string` | <span data-ttu-id="af79a-226">对象类型。</span><span class="sxs-lookup"><span data-stu-id="af79a-226">Object type.</span></span>  <span data-ttu-id="af79a-227">允许的值  `object` `function` `undefined` ：、、、、、 `string` `number` `boolean` 和</span><span class="sxs-lookup"><span data-stu-id="af79a-227">Allowed values:  `object`, `function`, `undefined`, `string`, `number`, `boolean`, and</span></span> `symbol` |  
| <span data-ttu-id="af79a-228">subtype \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-228">subtype \(optional\)</span></span> | `string` | <span data-ttu-id="af79a-229">对象子类型提示。</span><span class="sxs-lookup"><span data-stu-id="af79a-229">Object subtype hint.</span></span>  <span data-ttu-id="af79a-230">仅为 `object` 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="af79a-230">Specified for `object` type values only.</span></span>  <span data-ttu-id="af79a-231">允许的值  `null` ：、 `error` 和</span><span class="sxs-lookup"><span data-stu-id="af79a-231">Allowed values:  `null`, `error`, and</span></span> `promise` |  
| <span data-ttu-id="af79a-232">className \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-232">className \(optional\)</span></span> | `string` | <span data-ttu-id="af79a-233">对象类 \(构造函数\) 名称。</span><span class="sxs-lookup"><span data-stu-id="af79a-233">Object class \(constructor\) name.</span></span>  <span data-ttu-id="af79a-234">仅为 `object` 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="af79a-234">Specified for `object` type values only.</span></span> |  
| <span data-ttu-id="af79a-235">value \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-235">value \(optional\)</span></span> | `any` | <span data-ttu-id="af79a-236">基元值或 JSON 值 \(请求的远程对象值\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-236">Remote object value in case of primitive values or JSON values \(if it was requested\).</span></span> |  
| <span data-ttu-id="af79a-237">unserializableValue \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-237">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="af79a-238">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="af79a-238">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="af79a-239">不能为 JSON 字符串化的基元值没有， `value` 但获取此属性。</span><span class="sxs-lookup"><span data-stu-id="af79a-239">Primitive value which can not be JSON-stringified does not have `value`, but gets this property.</span></span> |  
| <span data-ttu-id="af79a-240">description \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-240">description \(optional\)</span></span> | `string` | <span data-ttu-id="af79a-241">对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="af79a-241">String representation of the object.</span></span> |  
| <span data-ttu-id="af79a-242">objectId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-242">objectId \(optional\)</span></span> | [<span data-ttu-id="af79a-243">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="af79a-243">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="af79a-244">非基元值的唯一对象标识符 \(\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-244">Unique object identifier \(for non-primitive values\).</span></span> |  
| <span data-ttu-id="af79a-245">msDebuggerPropertyId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-245">msDebuggerPropertyId \(optional\)</span></span> | `string` | <span data-ttu-id="af79a-246">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="af79a-246">**Experimental**.</span></span>  <span data-ttu-id="af79a-247">Microsoft：此对象的关联调试器属性 ID。</span><span class="sxs-lookup"><span data-stu-id="af79a-247">Microsoft:  The associated debugger property ID for this object.</span></span> |  

---  

### <a name="propertydescriptor-object"></a><span data-ttu-id="af79a-248">PropertyDescriptor 对象</span><span class="sxs-lookup"><span data-stu-id="af79a-248">PropertyDescriptor object</span></span>  

<a name="propertydescriptor"></a>  

<span data-ttu-id="af79a-249">对象属性描述符。</span><span class="sxs-lookup"><span data-stu-id="af79a-249">Object property descriptor.</span></span>  

| <span data-ttu-id="af79a-250">属性</span><span class="sxs-lookup"><span data-stu-id="af79a-250">Properties</span></span> | <span data-ttu-id="af79a-251">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-251">Type</span></span> | <span data-ttu-id="af79a-252">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-252">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-253">name</span><span class="sxs-lookup"><span data-stu-id="af79a-253">name</span></span> | `string` | <span data-ttu-id="af79a-254">属性名称或符号说明。</span><span class="sxs-lookup"><span data-stu-id="af79a-254">Property name or symbol description.</span></span> |  
| <span data-ttu-id="af79a-255">value \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-255">value \(optional\)</span></span> | [<span data-ttu-id="af79a-256">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-256">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-257">与属性关联的值。</span><span class="sxs-lookup"><span data-stu-id="af79a-257">The value associated with the property.</span></span> |  
| <span data-ttu-id="af79a-258">可写 \(可选\) </span><span class="sxs-lookup"><span data-stu-id="af79a-258">writable \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="af79a-259">如果与该属性关联的值可能更改 \(数据描述符\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-259">if the value associated with the property may be changed \(data descriptors only\).</span></span> |  
| <span data-ttu-id="af79a-260">获取 \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-260">get \(optional\)</span></span> | [<span data-ttu-id="af79a-261">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-261">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-262">充当属性 getter 的函数，或者如果没有 `undefined` getter \(访问器描述符\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-262">A function which serves as a getter for the property, or `undefined` if there is no getter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="af79a-263">set \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-263">set \(optional\)</span></span> | [<span data-ttu-id="af79a-264">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-264">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-265">用作属性的设置器的函数，或者如果没有设置器 `undefined` \(访问器描述符\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-265">A function which serves as a setter for the property, or `undefined` if there is no setter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="af79a-266">可配置</span><span class="sxs-lookup"><span data-stu-id="af79a-266">configurable</span></span> | `boolean` | `True` <span data-ttu-id="af79a-267">如果此属性描述符的类型可能更改，并且该属性可能从相应的对象中删除。</span><span class="sxs-lookup"><span data-stu-id="af79a-267">if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span> |  
| <span data-ttu-id="af79a-268">enumerable</span><span class="sxs-lookup"><span data-stu-id="af79a-268">enumerable</span></span> | `boolean` | `True` <span data-ttu-id="af79a-269">如果此属性在枚举相应对象的属性期间显示。</span><span class="sxs-lookup"><span data-stu-id="af79a-269">if this property shows up during enumeration of the properties on the corresponding object.</span></span> |  
| <span data-ttu-id="af79a-270">wasThrown \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-270">wasThrown \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="af79a-271">如果在评估期间引发结果。</span><span class="sxs-lookup"><span data-stu-id="af79a-271">if the result was thrown during the evaluation.</span></span> |  
| <span data-ttu-id="af79a-272">isOwn \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-272">isOwn \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="af79a-273">属性是否归对象所有。</span><span class="sxs-lookup"><span data-stu-id="af79a-273">if the property is owned for the object.</span></span> |  
| <span data-ttu-id="af79a-274">msReturnValue \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-274">msReturnValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="af79a-275">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="af79a-275">**Experimental**.</span></span>  <span data-ttu-id="af79a-276">Microsoft：  `True` 如果该属性是返回值。</span><span class="sxs-lookup"><span data-stu-id="af79a-276">Microsoft:  `True` if the property is a return value.</span></span> |  
| <span data-ttu-id="af79a-277">symbol \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-277">symbol \(optional\)</span></span> | [<span data-ttu-id="af79a-278">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-278">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-279">属性符号对象，如果属性的类型 `symbol` 。</span><span class="sxs-lookup"><span data-stu-id="af79a-279">Property symbol object, if the property is of the `symbol` type.</span></span> |  

---  

### <a name="callargument-object"></a><span data-ttu-id="af79a-280">CallArgument 对象</span><span class="sxs-lookup"><span data-stu-id="af79a-280">CallArgument object</span></span>  

<a name="callargument"></a>  

<span data-ttu-id="af79a-281">代表函数调用参数。</span><span class="sxs-lookup"><span data-stu-id="af79a-281">Represents function call argument.</span></span>  <span data-ttu-id="af79a-282">应指定远程对象 ID、不可序列化基元值 (\) \) 。 `value`</span><span class="sxs-lookup"><span data-stu-id="af79a-282">Either remote object ID `value`, unserializable primitive value or neither of \(for undefined\) them should be specified.</span></span>  

| <span data-ttu-id="af79a-283">属性</span><span class="sxs-lookup"><span data-stu-id="af79a-283">Properties</span></span> | <span data-ttu-id="af79a-284">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-284">Type</span></span> | <span data-ttu-id="af79a-285">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-285">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-286">value \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-286">value \(optional\)</span></span> | `any` | <span data-ttu-id="af79a-287">基元值或可序列化的 javascript 对象。</span><span class="sxs-lookup"><span data-stu-id="af79a-287">Primitive value or serializable javascript object.</span></span> |  
| <span data-ttu-id="af79a-288">unserializableValue \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-288">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="af79a-289">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="af79a-289">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="af79a-290">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="af79a-290">Primitive value which can not be JSON-stringified.</span></span> |  
| <span data-ttu-id="af79a-291">objectId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-291">objectId \(optional\)</span></span> | [<span data-ttu-id="af79a-292">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="af79a-292">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="af79a-293">远程对象句柄。</span><span class="sxs-lookup"><span data-stu-id="af79a-293">Remote object handle.</span></span> |  

---  

### <a name="executioncontextid-integer"></a><span data-ttu-id="af79a-294">ExecutionContextId 整数</span><span class="sxs-lookup"><span data-stu-id="af79a-294">ExecutionContextId integer</span></span>  

<a name="executioncontextid"></a>  

<span data-ttu-id="af79a-295">执行上下文的 ID。</span><span class="sxs-lookup"><span data-stu-id="af79a-295">ID of an execution context.</span></span>  

&nbsp;  

---  

### <a name="exceptiondetails-object"></a><span data-ttu-id="af79a-296">ExceptionDetails 对象</span><span class="sxs-lookup"><span data-stu-id="af79a-296">ExceptionDetails object</span></span>  

<a name="exceptiondetails"></a>  

<span data-ttu-id="af79a-297">有关在脚本编译或 (过程中) 异常或错误\错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="af79a-297">Detailed information about exception \(or error\) that was thrown during script compilation or execution.</span></span>  

| <span data-ttu-id="af79a-298">属性</span><span class="sxs-lookup"><span data-stu-id="af79a-298">Properties</span></span> | <span data-ttu-id="af79a-299">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-299">Type</span></span> | <span data-ttu-id="af79a-300">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-300">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-301">exceptionId</span><span class="sxs-lookup"><span data-stu-id="af79a-301">exceptionId</span></span> | `integer` | <span data-ttu-id="af79a-302">异常 ID。</span><span class="sxs-lookup"><span data-stu-id="af79a-302">Exception ID.</span></span> |  
| <span data-ttu-id="af79a-303">文本</span><span class="sxs-lookup"><span data-stu-id="af79a-303">text</span></span> | `string` | <span data-ttu-id="af79a-304">异常文本，应在可用时与异常对象一同使用。</span><span class="sxs-lookup"><span data-stu-id="af79a-304">Exception text, which should be used together with exception object when available.</span></span> |  
| <span data-ttu-id="af79a-305">lineNumber</span><span class="sxs-lookup"><span data-stu-id="af79a-305">lineNumber</span></span> | `integer` | <span data-ttu-id="af79a-306">例外位置 \(0\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-306">Line number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="af79a-307">columnNumber</span><span class="sxs-lookup"><span data-stu-id="af79a-307">columnNumber</span></span> | `integer` | <span data-ttu-id="af79a-308">例外位置 \(0\) 的列号。</span><span class="sxs-lookup"><span data-stu-id="af79a-308">Column number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="af79a-309">scriptId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-309">scriptId \(optional\)</span></span> | [<span data-ttu-id="af79a-310">ScriptId</span><span class="sxs-lookup"><span data-stu-id="af79a-310">ScriptId</span></span>](#scriptid) | <span data-ttu-id="af79a-311">异常位置的脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="af79a-311">Script ID of the exception location.</span></span> |  
| <span data-ttu-id="af79a-312">url \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-312">url \(optional\)</span></span> | `string` | <span data-ttu-id="af79a-313">未报告脚本时使用的异常位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="af79a-313">URL of the exception location, to be used when the script was not reported.</span></span> |  
| <span data-ttu-id="af79a-314">stackTrace \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-314">stackTrace \(optional\)</span></span> | [<span data-ttu-id="af79a-315">StackTrace</span><span class="sxs-lookup"><span data-stu-id="af79a-315">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="af79a-316">JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="af79a-316">JavaScript stack trace if available.</span></span> |  
| <span data-ttu-id="af79a-317">exception \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-317">exception \(optional\)</span></span> | [<span data-ttu-id="af79a-318">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="af79a-318">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="af79a-319">Exception 对象（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="af79a-319">Exception object if available.</span></span> |  
| <span data-ttu-id="af79a-320">executionContextId \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-320">executionContextId \(optional\)</span></span> | [<span data-ttu-id="af79a-321">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="af79a-321">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="af79a-322">发生异常的上下文的标识符。</span><span class="sxs-lookup"><span data-stu-id="af79a-322">Identifier of the context where exception happened.</span></span> |  

---  

### <a name="timestamp-integer"></a><span data-ttu-id="af79a-323">时间戳整数</span><span class="sxs-lookup"><span data-stu-id="af79a-323">Timestamp integer</span></span>  

<a name="timestamp"></a>  

<span data-ttu-id="af79a-324">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="af79a-324">Number of milliseconds since epoch.</span></span>  

&nbsp;  

---  

### <a name="callframe-object"></a><span data-ttu-id="af79a-325">CallFrame 对象</span><span class="sxs-lookup"><span data-stu-id="af79a-325">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="af79a-326">运行时错误和断言的堆栈项。</span><span class="sxs-lookup"><span data-stu-id="af79a-326">Stack entry for runtime errors and assertions.</span></span>  

| <span data-ttu-id="af79a-327">属性</span><span class="sxs-lookup"><span data-stu-id="af79a-327">Properties</span></span> | <span data-ttu-id="af79a-328">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-328">Type</span></span> | <span data-ttu-id="af79a-329">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-329">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-330">functionName</span><span class="sxs-lookup"><span data-stu-id="af79a-330">functionName</span></span> | `string` | <span data-ttu-id="af79a-331">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="af79a-331">JavaScript function name.</span></span> |  
| <span data-ttu-id="af79a-332">scriptId</span><span class="sxs-lookup"><span data-stu-id="af79a-332">scriptId</span></span> | [<span data-ttu-id="af79a-333">ScriptId</span><span class="sxs-lookup"><span data-stu-id="af79a-333">ScriptId</span></span>](#scriptid) | <span data-ttu-id="af79a-334">JavaScript 脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="af79a-334">JavaScript script ID.</span></span> |  
| <span data-ttu-id="af79a-335">url</span><span class="sxs-lookup"><span data-stu-id="af79a-335">url</span></span> | `string` | <span data-ttu-id="af79a-336">JavaScript 脚本名称或 url。</span><span class="sxs-lookup"><span data-stu-id="af79a-336">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="af79a-337">lineNumber</span><span class="sxs-lookup"><span data-stu-id="af79a-337">lineNumber</span></span> | `integer` | <span data-ttu-id="af79a-338">JavaScript 脚本行号 \(0-based\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-338">JavaScript script line number \(0-based\).</span></span> |  
| <span data-ttu-id="af79a-339">columnNumber</span><span class="sxs-lookup"><span data-stu-id="af79a-339">columnNumber</span></span> | `integer` | <span data-ttu-id="af79a-340">JavaScript 脚本列号 \(0-based\) 。</span><span class="sxs-lookup"><span data-stu-id="af79a-340">JavaScript script column number \(0-based\).</span></span> |  

---  

### <a name="stacktrace-object"></a><span data-ttu-id="af79a-341">StackTrace 对象</span><span class="sxs-lookup"><span data-stu-id="af79a-341">StackTrace object</span></span>  

<a name="stacktrace"></a>  

<span data-ttu-id="af79a-342">断言或错误消息的呼叫帧。</span><span class="sxs-lookup"><span data-stu-id="af79a-342">Call frames for assertions or error messages.</span></span>  

| <span data-ttu-id="af79a-343">属性</span><span class="sxs-lookup"><span data-stu-id="af79a-343">Properties</span></span> | <span data-ttu-id="af79a-344">类型</span><span class="sxs-lookup"><span data-stu-id="af79a-344">Type</span></span> | <span data-ttu-id="af79a-345">详细信息</span><span class="sxs-lookup"><span data-stu-id="af79a-345">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="af79a-346">description \(optional\) </span><span class="sxs-lookup"><span data-stu-id="af79a-346">description \(optional\)</span></span> | `string` | <span data-ttu-id="af79a-347">此堆栈跟踪的字符串标签。</span><span class="sxs-lookup"><span data-stu-id="af79a-347">String label of this stack trace.</span></span>  <span data-ttu-id="af79a-348">对于异步跟踪，这可能是启动异步调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="af79a-348">For async traces this may be a name of the function that initiated the async call.</span></span> |  
| <span data-ttu-id="af79a-349">callFrames</span><span class="sxs-lookup"><span data-stu-id="af79a-349">callFrames</span></span> | [<span data-ttu-id="af79a-350">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="af79a-350">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="af79a-351">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="af79a-351">JavaScript function name.</span></span> |  
| <span data-ttu-id="af79a-352">父 \(可选\) </span><span class="sxs-lookup"><span data-stu-id="af79a-352">parent \(optional\)</span></span> | [<span data-ttu-id="af79a-353">StackTrace</span><span class="sxs-lookup"><span data-stu-id="af79a-353">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="af79a-354">此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="af79a-354">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span> |  

---  
