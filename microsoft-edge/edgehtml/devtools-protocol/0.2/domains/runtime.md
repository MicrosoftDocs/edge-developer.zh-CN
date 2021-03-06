---
description: DevTools 协议版本 0.2 (EdgeHTML) 运行时域参考。 运行时域通过远程评估和镜像对象公开 JavaScript 运行时。 评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。 原始对象在内存中进行维护，除非它们已显式释放。
title: '运行时域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: afc79a17c5002f60806872a9add57f518ff6cb45
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398138"
---
# <a name="runtime-domain---devtools-protocol-version-02-edgehtml"></a><span data-ttu-id="7eb20-106">运行时域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="7eb20-106">Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="7eb20-107">运行时域通过远程评估和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="7eb20-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="7eb20-108">评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。</span><span class="sxs-lookup"><span data-stu-id="7eb20-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="7eb20-109">原始对象在内存中进行维护，除非它们已显式释放。</span><span class="sxs-lookup"><span data-stu-id="7eb20-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>  

| <span data-ttu-id="7eb20-110">分类</span><span class="sxs-lookup"><span data-stu-id="7eb20-110">Classification</span></span> | <span data-ttu-id="7eb20-111">成员</span><span class="sxs-lookup"><span data-stu-id="7eb20-111">Members</span></span> |  
|:--- |:--- |  
| [**<span data-ttu-id="7eb20-112">方法</span><span class="sxs-lookup"><span data-stu-id="7eb20-112">Methods</span></span>**](#methods) | <span data-ttu-id="7eb20-113">[enable](#enable)， [disable](#disable)， [evaluate](#evaluate)， [callFunctionOn](#callfunctionon)， [awaitPromise](#awaitpromise)， [getProperties](#getproperties)， [globalLexicalScopeNames，](#globallexicalscopenames) [releaseObject](#releaseobject)， [releaseObjectGroup](#releaseobjectgroup)， [discardConsoleEntries](#discardconsoleentries)</span><span class="sxs-lookup"><span data-stu-id="7eb20-113">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span></span> |  
| [**<span data-ttu-id="7eb20-114">事件</span><span class="sxs-lookup"><span data-stu-id="7eb20-114">Events</span></span>**](#events) | <span data-ttu-id="7eb20-115">[executionContextCreated](#executioncontextcreated)， [executionContextDestroyed](#executioncontextdestroyed)， [executionContextsCleared，](#executioncontextscleared) [exceptionThrown](#exceptionthrown)， [consoleAPICalled](#consoleapicalled)</span><span class="sxs-lookup"><span data-stu-id="7eb20-115">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span></span> |  
| [**<span data-ttu-id="7eb20-116">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-116">Types</span></span>**](#types) | <span data-ttu-id="7eb20-117">[ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExecutionContextDescription](#executioncontextdescription)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="7eb20-117">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |  

## <a name="methods"></a><span data-ttu-id="7eb20-118">方法</span><span class="sxs-lookup"><span data-stu-id="7eb20-118">Methods</span></span>  

### <a name="enable"></a><span data-ttu-id="7eb20-119">“启用”</span><span class="sxs-lookup"><span data-stu-id="7eb20-119">enable</span></span>  

<span data-ttu-id="7eb20-120">启用对 `executionContextCreated` 、 `executionContextDestroyed` 和事件 `executionContextsCleared` 的报告。</span><span class="sxs-lookup"><span data-stu-id="7eb20-120">Enables reporting of the `executionContextCreated`, `executionContextDestroyed`, and `executionContextsCleared` events.</span></span>  <span data-ttu-id="7eb20-121">启用报告后， `executionContextCreated` 将立即针对每个现有执行上下文发送事件。</span><span class="sxs-lookup"><span data-stu-id="7eb20-121">When the reporting gets enabled the `executionContextCreated` event will be sent immediately for each existing execution context.</span></span>  

---  

### <a name="disable"></a><span data-ttu-id="7eb20-122">“禁用”</span><span class="sxs-lookup"><span data-stu-id="7eb20-122">disable</span></span>  

<span data-ttu-id="7eb20-123">禁用报告 、 `executionContextCreated` `executionContextDestroyed` 和 `executionContextsCleared` 事件。</span><span class="sxs-lookup"><span data-stu-id="7eb20-123">Disables reporting of the `executionContextCreated`, `executionContextDestroyed`, and `executionContextsCleared` events.</span></span>  

---  

### <a name="evaluate"></a><span data-ttu-id="7eb20-124">evaluate</span><span class="sxs-lookup"><span data-stu-id="7eb20-124">evaluate</span></span>  

<span data-ttu-id="7eb20-125">计算全局对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="7eb20-125">Evaluates expression on global object.</span></span>  

| <span data-ttu-id="7eb20-126">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-126">Parameters</span></span> | <span data-ttu-id="7eb20-127">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-127">Type</span></span> | <span data-ttu-id="7eb20-128">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-128">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-129">表达式</span><span class="sxs-lookup"><span data-stu-id="7eb20-129">expression</span></span> | `string` | <span data-ttu-id="7eb20-130">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="7eb20-130">Expression to evaluate.</span></span> |  
| <span data-ttu-id="7eb20-131">includeCommandLineAPI \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-131">includeCommandLineAPI \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-132">确定在评估期间命令行 API 是否可用。</span><span class="sxs-lookup"><span data-stu-id="7eb20-132">Determines whether Command Line API should be available during the evaluation.</span></span> |  
| <span data-ttu-id="7eb20-133">objectGroup \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-133">objectGroup \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-134">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-134">Symbolic group name that can be used to release multiple objects.</span></span> |  
| <span data-ttu-id="7eb20-135">无提示 \ (可选\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-135">silent \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-136">在静默模式下，不会报告在评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="7eb20-136">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span>  <span data-ttu-id="7eb20-137">覆盖 `setPauseOnException` 状态。</span><span class="sxs-lookup"><span data-stu-id="7eb20-137">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="7eb20-138">contextId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-138">contextId \(optional\)</span></span> | [<span data-ttu-id="7eb20-139">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-139">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="7eb20-140">指定要执行评估的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="7eb20-140">Specifies in which execution context to perform evaluation.</span></span>  <span data-ttu-id="7eb20-141">如果省略该参数，将在所检查页面的上下文中执行计算。</span><span class="sxs-lookup"><span data-stu-id="7eb20-141">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span> |  
| <span data-ttu-id="7eb20-142">returnByValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-142">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-143">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-143">Whether the result is expected to be a JSON object that should be sent by value.</span></span> |  
| <span data-ttu-id="7eb20-144">awaitPromise \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-144">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-145">是否应为 `await` 生成的值执行，并解决等待的承诺后返回。</span><span class="sxs-lookup"><span data-stu-id="7eb20-145">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  

| <span data-ttu-id="7eb20-146">返回</span><span class="sxs-lookup"><span data-stu-id="7eb20-146">Returns</span></span> | <span data-ttu-id="7eb20-147">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-147">Type</span></span> | <span data-ttu-id="7eb20-148">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-148">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-149">result</span><span class="sxs-lookup"><span data-stu-id="7eb20-149">result</span></span> | [<span data-ttu-id="7eb20-150">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-150">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-151">评估结果。</span><span class="sxs-lookup"><span data-stu-id="7eb20-151">Evaluation result.</span></span> |  

---  

### <a name="callfunctionon"></a><span data-ttu-id="7eb20-152">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="7eb20-152">callFunctionOn</span></span>  

<span data-ttu-id="7eb20-153">调用给定对象上具有给定声明的函数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-153">Calls function with given declaration on the given object.</span></span>  <span data-ttu-id="7eb20-154">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-154">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="7eb20-155">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-155">Parameters</span></span> | <span data-ttu-id="7eb20-156">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-156">Type</span></span> | <span data-ttu-id="7eb20-157">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-157">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-158">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="7eb20-158">functionDeclaration</span></span> | `string` | <span data-ttu-id="7eb20-159">要调用的函数的声明。</span><span class="sxs-lookup"><span data-stu-id="7eb20-159">Declaration of the function to call.</span></span> |  
| <span data-ttu-id="7eb20-160">objectId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-160">objectId \(optional\)</span></span> | [<span data-ttu-id="7eb20-161">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-161">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="7eb20-162">要调用函数的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-162">Identifier of the object to call function on.</span></span>  <span data-ttu-id="7eb20-163">或者 `objectId` `executionContextId` 应指定。</span><span class="sxs-lookup"><span data-stu-id="7eb20-163">Either `objectId` or `executionContextId` should be specified.</span></span>  `objectId` <span data-ttu-id="7eb20-164">必须来自 `Runtime.evaluate()` 函数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-164">must be from the `Runtime.evaluate()` function.</span></span> |  
| <span data-ttu-id="7eb20-165">参数 \ (可选\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-165">arguments \(optional\)</span></span> | [<span data-ttu-id="7eb20-166">CallArgument[]</span><span class="sxs-lookup"><span data-stu-id="7eb20-166">CallArgument[]</span></span>](#callargument) | <span data-ttu-id="7eb20-167">调用参数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-167">Call arguments.</span></span>  <span data-ttu-id="7eb20-168">所有调用参数都必须属于与目标对象相同的 JavaScript 世界。</span><span class="sxs-lookup"><span data-stu-id="7eb20-168">All call arguments must belong to the same JavaScript world as the target object.</span></span> |  
| <span data-ttu-id="7eb20-169">boolean \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-169">boolean \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-170">在静默模式下，不会报告在评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="7eb20-170">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="7eb20-171">覆盖 `setPauseOnException` 状态。</span><span class="sxs-lookup"><span data-stu-id="7eb20-171">Overrides `setPauseOnException` state.</span></span> |  
| <span data-ttu-id="7eb20-172">returnByValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-172">returnByValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-173">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-173">Whether the result is expected to be a JSON object which should be sent by value.</span></span> |  
| <span data-ttu-id="7eb20-174">awaitPromise \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-174">awaitPromise \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-175">是否应为 `await` 生成的值执行，并解决等待的承诺后返回。</span><span class="sxs-lookup"><span data-stu-id="7eb20-175">Whether execution should `await` for resulting value and return once awaited promise is resolved.</span></span> |  
| <span data-ttu-id="7eb20-176">executionContextId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-176">executionContextId \(optional\)</span></span> | [<span data-ttu-id="7eb20-177">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-177">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="7eb20-178">指定将用来调用函数的全局对象的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="7eb20-178">Specifies execution context which global object will be used to call function on.</span></span>  <span data-ttu-id="7eb20-179">任一</span><span class="sxs-lookup"><span data-stu-id="7eb20-179">Either</span></span>
`executionContextId` <span data-ttu-id="7eb20-180">或 `objectId` 应指定</span><span class="sxs-lookup"><span data-stu-id="7eb20-180">or `objectId` should be specified</span></span> |  
| <span data-ttu-id="7eb20-181">objectGroup \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-181">objectGroup \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-182">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-182">Symbolic group name that can be used to release multiple objects.</span></span>  <span data-ttu-id="7eb20-183">如果 `objectGroup` 未指定且 `objectId` 为， `objectGroup` 则继承自对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-183">If `objectGroup` is not specified and `objectId` is, `objectGroup` will be inherited from object.</span></span> |  

| <span data-ttu-id="7eb20-184">返回</span><span class="sxs-lookup"><span data-stu-id="7eb20-184">Returns</span></span> | <span data-ttu-id="7eb20-185">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-185">Type</span></span> | <span data-ttu-id="7eb20-186">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-186">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-187">result</span><span class="sxs-lookup"><span data-stu-id="7eb20-187">result</span></span> | [<span data-ttu-id="7eb20-188">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-188">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-189">呼叫结果。</span><span class="sxs-lookup"><span data-stu-id="7eb20-189">Call result.</span></span> |  

---  

### <a name="awaitpromise"></a><span data-ttu-id="7eb20-190">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="7eb20-190">awaitPromise</span></span>  

<span data-ttu-id="7eb20-191">添加具有给定承诺对象 ID 的 promise 处理程序。</span><span class="sxs-lookup"><span data-stu-id="7eb20-191">Add handler to promise with given promise object id.</span></span>  

| <span data-ttu-id="7eb20-192">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-192">Parameters</span></span> | <span data-ttu-id="7eb20-193">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-193">Type</span></span> | <span data-ttu-id="7eb20-194">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-194">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-195">promiseObjectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-195">promiseObjectId</span></span> | [<span data-ttu-id="7eb20-196">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-196">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="7eb20-197">承诺的标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-197">Identifier of the promise.</span></span> |  
| <span data-ttu-id="7eb20-198">returnByValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-198">returnByValue \(optional\)</span></span> | <span data-ttu-id="7eb20-199">布尔型</span><span class="sxs-lookup"><span data-stu-id="7eb20-199">boolean</span></span> | <span data-ttu-id="7eb20-200">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-200">Whether the result is expected to be a JSON object that should be sent by value.</span></span> |  

| <span data-ttu-id="7eb20-201">返回</span><span class="sxs-lookup"><span data-stu-id="7eb20-201">Returns</span></span> | <span data-ttu-id="7eb20-202">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-202">Type</span></span> | <span data-ttu-id="7eb20-203">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-203">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-204">result</span><span class="sxs-lookup"><span data-stu-id="7eb20-204">result</span></span> | [<span data-ttu-id="7eb20-205">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-205">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-206">承诺结果。</span><span class="sxs-lookup"><span data-stu-id="7eb20-206">Promise result.</span></span>  <span data-ttu-id="7eb20-207">如果承诺被拒绝，将包含拒绝的值。</span><span class="sxs-lookup"><span data-stu-id="7eb20-207">Will contain rejected value if promise was rejected.</span></span> |  

---  

### <a name="getproperties"></a><span data-ttu-id="7eb20-208">getProperties</span><span class="sxs-lookup"><span data-stu-id="7eb20-208">getProperties</span></span>  

<span data-ttu-id="7eb20-209">返回给定对象的属性。</span><span class="sxs-lookup"><span data-stu-id="7eb20-209">Returns properties of a given object.</span></span> <span data-ttu-id="7eb20-210">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-210">Object group of the result is inherited from the target object.</span></span>  

| <span data-ttu-id="7eb20-211">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-211">Parameters</span></span> | <span data-ttu-id="7eb20-212">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-212">Type</span></span> | <span data-ttu-id="7eb20-213">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-213">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-214">objectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-214">objectId</span></span> | [<span data-ttu-id="7eb20-215">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-215">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="7eb20-216">要返回其属性的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-216">Identifier of the object to return properties for.</span></span>  `objectId` <span data-ttu-id="7eb20-217">必须来自 `Debugger.evaluateOnCallFrame()` 函数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-217">must be from the `Debugger.evaluateOnCallFrame()` function.</span></span> |  
| <span data-ttu-id="7eb20-218">ownProperties \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-218">ownProperties \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-219">If `true` ，则返回仅属于元素本身的属性，而不是其原型链的属性。</span><span class="sxs-lookup"><span data-stu-id="7eb20-219">If `true`, returns properties belonging only to the element itself, not to its prototype chain.</span></span> |  
| <span data-ttu-id="7eb20-220">accessorPropertiesOnly \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-220">accessorPropertiesOnly \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-221">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-221">**Experimental**.</span></span>  <span data-ttu-id="7eb20-222">If `true` ， returns accessor properties \ (with getter/setter\) only; internal properties are not returned either.</span><span class="sxs-lookup"><span data-stu-id="7eb20-222">If `true`, returns accessor properties \(with getter/setter\) only; internal properties are not returned either.</span></span> |  

| <span data-ttu-id="7eb20-223">返回</span><span class="sxs-lookup"><span data-stu-id="7eb20-223">Returns</span></span> | <span data-ttu-id="7eb20-224">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-224">Type</span></span> | <span data-ttu-id="7eb20-225">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-225">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-226">result</span><span class="sxs-lookup"><span data-stu-id="7eb20-226">result</span></span> | [<span data-ttu-id="7eb20-227">PropertyDescriptor[]</span><span class="sxs-lookup"><span data-stu-id="7eb20-227">PropertyDescriptor[]</span></span>](#propertydescriptor) | <span data-ttu-id="7eb20-228">对象属性。</span><span class="sxs-lookup"><span data-stu-id="7eb20-228">Object properties.</span></span> |  

---  

### <a name="globallexicalscopenames"></a><span data-ttu-id="7eb20-229">globalLexicalScopeNames</span><span class="sxs-lookup"><span data-stu-id="7eb20-229">globalLexicalScopeNames</span></span>  

<span data-ttu-id="7eb20-230">从控制台全局范围返回所有 let、const 和类变量。</span><span class="sxs-lookup"><span data-stu-id="7eb20-230">Returns all let, const, and class variables from the console global scope.</span></span>  

| <span data-ttu-id="7eb20-231">返回</span><span class="sxs-lookup"><span data-stu-id="7eb20-231">Returns</span></span> | <span data-ttu-id="7eb20-232">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-232">Type</span></span> | <span data-ttu-id="7eb20-233">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-233">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-234">names</span><span class="sxs-lookup"><span data-stu-id="7eb20-234">names</span></span> | `string[]` | &nbsp; |  

---  

### <a name="releaseobject"></a><span data-ttu-id="7eb20-235">releaseObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-235">releaseObject</span></span>  

<span data-ttu-id="7eb20-236">释放具有给定 ID 的远程对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-236">Releases remote object with given ID.</span></span>  

| <span data-ttu-id="7eb20-237">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-237">Parameters</span></span> | <span data-ttu-id="7eb20-238">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-238">Type</span></span> | <span data-ttu-id="7eb20-239">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-239">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-240">objectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-240">objectId</span></span> | [<span data-ttu-id="7eb20-241">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-241">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="7eb20-242">要释放的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-242">Identifier of the object to release.</span></span> |  

---  

### <a name="releaseobjectgroup"></a><span data-ttu-id="7eb20-243">releaseObjectGroup</span><span class="sxs-lookup"><span data-stu-id="7eb20-243">releaseObjectGroup</span></span>  

<span data-ttu-id="7eb20-244">释放属于给定组的所有远程对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-244">Releases all remote objects that belong to a given group.</span></span>  

| <span data-ttu-id="7eb20-245">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-245">Parameters</span></span> | <span data-ttu-id="7eb20-246">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-246">Type</span></span> | <span data-ttu-id="7eb20-247">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-247">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-248">objectGroup</span><span class="sxs-lookup"><span data-stu-id="7eb20-248">objectGroup</span></span> | `string` | <span data-ttu-id="7eb20-249">符号对象组名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-249">Symbolic object group name.</span></span> |  

---  

### <a name="discardconsoleentries"></a><span data-ttu-id="7eb20-250">discardConsoleEntries</span><span class="sxs-lookup"><span data-stu-id="7eb20-250">discardConsoleEntries</span></span>  

<span data-ttu-id="7eb20-251">放弃收集的异常和控制台 API 调用。</span><span class="sxs-lookup"><span data-stu-id="7eb20-251">Discards collected exceptions and console API calls.</span></span>  

---  

## <a name="events"></a><span data-ttu-id="7eb20-252">事件</span><span class="sxs-lookup"><span data-stu-id="7eb20-252">Events</span></span>  

### <a name="executioncontextcreated"></a><span data-ttu-id="7eb20-253">executionContextCreated</span><span class="sxs-lookup"><span data-stu-id="7eb20-253">executionContextCreated</span></span>  

<span data-ttu-id="7eb20-254">在新建执行上下文时发出。</span><span class="sxs-lookup"><span data-stu-id="7eb20-254">Issued when new execution context is created.</span></span>  

| <span data-ttu-id="7eb20-255">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-255">Parameters</span></span> | <span data-ttu-id="7eb20-256">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-256">Type</span></span> | <span data-ttu-id="7eb20-257">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-257">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-258">上下文</span><span class="sxs-lookup"><span data-stu-id="7eb20-258">context</span></span> | [<span data-ttu-id="7eb20-259">ExecutionContextDescription</span><span class="sxs-lookup"><span data-stu-id="7eb20-259">ExecutionContextDescription</span></span>](#executioncontextdescription) | <span data-ttu-id="7eb20-260">新建的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="7eb20-260">A newly created execution context.</span></span> |  

---  

### <a name="executioncontextdestroyed"></a><span data-ttu-id="7eb20-261">executionContextDestroyed</span><span class="sxs-lookup"><span data-stu-id="7eb20-261">executionContextDestroyed</span></span>  

<span data-ttu-id="7eb20-262">当执行上下文被销毁时发出。</span><span class="sxs-lookup"><span data-stu-id="7eb20-262">Issued when execution context is destroyed.</span></span>  

| <span data-ttu-id="7eb20-263">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-263">Parameters</span></span> | <span data-ttu-id="7eb20-264">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-264">Type</span></span> | <span data-ttu-id="7eb20-265">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-265">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-266">executionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-266">executionContextId</span></span> | [<span data-ttu-id="7eb20-267">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-267">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="7eb20-268">已销毁上下文的 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb20-268">ID of the destroyed context.</span></span> |  

---  

### <a name="executioncontextscleared"></a><span data-ttu-id="7eb20-269">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="7eb20-269">executionContextsCleared</span></span>  

<span data-ttu-id="7eb20-270">在浏览器中清除所有 executionContexts 时发出。</span><span class="sxs-lookup"><span data-stu-id="7eb20-270">Issued when all executionContexts were cleared in browser.</span></span>  

&nbsp;  

---  

### <a name="exceptionthrown"></a><span data-ttu-id="7eb20-271">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="7eb20-271">exceptionThrown</span></span>  

<span data-ttu-id="7eb20-272">引发和未处理异常时发出。</span><span class="sxs-lookup"><span data-stu-id="7eb20-272">Issued when exception was thrown and unhandled.</span></span>  

| <span data-ttu-id="7eb20-273">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-273">Parameters</span></span> | <span data-ttu-id="7eb20-274">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-274">Type</span></span> | <span data-ttu-id="7eb20-275">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-275">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-276">timestamp</span><span class="sxs-lookup"><span data-stu-id="7eb20-276">timestamp</span></span> | [<span data-ttu-id="7eb20-277">时间戳</span><span class="sxs-lookup"><span data-stu-id="7eb20-277">Timestamp</span></span>](#timestamp) | <span data-ttu-id="7eb20-278">异常的时间戳。</span><span class="sxs-lookup"><span data-stu-id="7eb20-278">Timestamp of the exception.</span></span> |  
| <span data-ttu-id="7eb20-279">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="7eb20-279">exceptionDetails</span></span> | [<span data-ttu-id="7eb20-280">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="7eb20-280">ExceptionDetails</span></span>](#exceptiondetails) | &nbsp; |  

---  

### <a name="consoleapicalled"></a><span data-ttu-id="7eb20-281">consoleAPICalled</span><span class="sxs-lookup"><span data-stu-id="7eb20-281">consoleAPICalled</span></span>  

| <span data-ttu-id="7eb20-282">参数</span><span class="sxs-lookup"><span data-stu-id="7eb20-282">Parameters</span></span> | <span data-ttu-id="7eb20-283">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-283">Type</span></span> | <span data-ttu-id="7eb20-284">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-284">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-285">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-285">type</span></span> | `string` | <span data-ttu-id="7eb20-286">呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="7eb20-286">Type of the call.</span></span>  <span data-ttu-id="7eb20-287">允许的值 `log` `info` `warning` ：、、、、、、、、、 `error` `debug` `assert` `table` `trace` `dir` `dirxml` `clear` `select` `count` `countReset` `timeEnd` `timeStamp` `startGroup` `startGroupCollapsed`</span><span class="sxs-lookup"><span data-stu-id="7eb20-287">Allowed values:  `log`, `info`, `warning`, `error`, `debug`, `assert`, `table`, `trace`, `dir`, `dirxml`, `clear`, `select`, `count`, `countReset`, `timeEnd`, `timeStamp`, `startGroup`, `startGroupCollapsed`, and</span></span> `endGroup` |  
| <span data-ttu-id="7eb20-288">args</span><span class="sxs-lookup"><span data-stu-id="7eb20-288">args</span></span> | <span data-ttu-id="7eb20-289">[RemoteObject[]] (#remoteobject</span><span class="sxs-lookup"><span data-stu-id="7eb20-289">[RemoteObject[]](#remoteobject</span></span> | <span data-ttu-id="7eb20-290">调用参数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-290">Call arguments.</span></span> |  
| <span data-ttu-id="7eb20-291">executionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-291">executionContextId</span></span> | [<span data-ttu-id="7eb20-292">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-292">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="7eb20-293">进行控制台调用的上下文的标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-293">Identifier of the context where console call was made.</span></span> |  
| <span data-ttu-id="7eb20-294">timestamp \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-294">timestamp \(optional\)</span></span> | [<span data-ttu-id="7eb20-295">时间戳</span><span class="sxs-lookup"><span data-stu-id="7eb20-295">Timestamp</span></span>](#timestamp) | <span data-ttu-id="7eb20-296">调用时间戳。</span><span class="sxs-lookup"><span data-stu-id="7eb20-296">Call timestamp.</span></span> |  
| <span data-ttu-id="7eb20-297">stackTrace \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-297">stackTrace \(optional\)</span></span> | [<span data-ttu-id="7eb20-298">StackTrace</span><span class="sxs-lookup"><span data-stu-id="7eb20-298">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="7eb20-299">堆栈跟踪捕获（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="7eb20-299">Stack trace captured if available.</span></span> |  

---  

## <a name="types"></a><span data-ttu-id="7eb20-300">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-300">Types</span></span>  

### <a name="scriptid-string"></a><span data-ttu-id="7eb20-301">ScriptId 字符串</span><span class="sxs-lookup"><span data-stu-id="7eb20-301">ScriptId string</span></span>  

<a name="scriptid"></a>

<span data-ttu-id="7eb20-302">唯一脚本标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-302">Unique script identifier.</span></span>  

&nbsp;  

---  

### <a name="remoteobjectid-string"></a><span data-ttu-id="7eb20-303">RemoteObjectId 字符串</span><span class="sxs-lookup"><span data-stu-id="7eb20-303">RemoteObjectId string</span></span>  

<a name="remoteobjectid"></a>

<span data-ttu-id="7eb20-304">唯一对象标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-304">Unique object identifier.</span></span>  

&nbsp;  

---  

### <a name="unserializablevalue-string"></a><span data-ttu-id="7eb20-305">UnserializableValue 字符串</span><span class="sxs-lookup"><span data-stu-id="7eb20-305">UnserializableValue string</span></span>  

<a name="unserializablevalue"></a>  

<span data-ttu-id="7eb20-306">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="7eb20-306">Primitive value which cannot be JSON-stringified.</span></span>  

##### <a name="allowed-values"></a><span data-ttu-id="7eb20-307">允许的值</span><span class="sxs-lookup"><span data-stu-id="7eb20-307">Allowed Values</span></span>  

`Infinity`<span data-ttu-id="7eb20-308">, `NaN`, `-Infinity`,</span><span class="sxs-lookup"><span data-stu-id="7eb20-308">, `NaN`, `-Infinity`,</span></span> `-0`  

---  

### <a name="remoteobject-object"></a><span data-ttu-id="7eb20-309">RemoteObject 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-309">RemoteObject object</span></span>  

<a name="remoteobject"></a>  

<span data-ttu-id="7eb20-310">引用原始 JavaScript 对象的镜像对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-310">Mirror object referencing original JavaScript object.</span></span>  

| <span data-ttu-id="7eb20-311">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-311">Properties</span></span> | <span data-ttu-id="7eb20-312">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-312">Type</span></span> | <span data-ttu-id="7eb20-313">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-313">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-314">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-314">type</span></span> | `string` | <span data-ttu-id="7eb20-315">对象类型。</span><span class="sxs-lookup"><span data-stu-id="7eb20-315">Object type.</span></span>  <span data-ttu-id="7eb20-316">允许的值  `object` `function` `undefined` ：、、、、、 `string` `number` `boolean` 和</span><span class="sxs-lookup"><span data-stu-id="7eb20-316">Allowed values:  `object`, `function`, `undefined`, `string`, `number`, `boolean`, and</span></span> `symbol` |  
| <span data-ttu-id="7eb20-317">subtype \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-317">subtype \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-318">对象子类型提示。</span><span class="sxs-lookup"><span data-stu-id="7eb20-318">Object subtype hint.</span></span>  <span data-ttu-id="7eb20-319">仅为 `object` 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="7eb20-319">Specified for `object` type values only.</span></span>  <span data-ttu-id="7eb20-320">允许的值  `null` `error` `promise` ：、、和</span><span class="sxs-lookup"><span data-stu-id="7eb20-320">Allowed values:  `null`, `error`, `promise`, and</span></span> `node` |  
| <span data-ttu-id="7eb20-321">className \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-321">className \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-322">对象类 \ (构造函数\) 名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-322">Object class \(constructor\) name.</span></span>  <span data-ttu-id="7eb20-323">仅为 `object` 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="7eb20-323">Specified for `object` type values only.</span></span> |  
| <span data-ttu-id="7eb20-324">value \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-324">value \(optional\)</span></span> | `any` | <span data-ttu-id="7eb20-325">基元值或 JSON 值 \ (请求的远程对象值\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-325">Remote object value in case of primitive values or JSON values \(if it was requested\).</span></span> |  
| <span data-ttu-id="7eb20-326">unserializableValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-326">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="7eb20-327">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="7eb20-327">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="7eb20-328">不能为 JSON 字符串化的基元值没有， `value` 但获取此属性。</span><span class="sxs-lookup"><span data-stu-id="7eb20-328">Primitive value which can not be JSON-stringified does not have `value`, but gets this property.</span></span> |  
| <span data-ttu-id="7eb20-329">description \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-329">description \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-330">对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="7eb20-330">String representation of the object.</span></span> |  
| <span data-ttu-id="7eb20-331">objectId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-331">objectId \(optional\)</span></span> | [<span data-ttu-id="7eb20-332">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="7eb20-332">RemoteObjectId</span></span>](#remoteobjectid) | <span data-ttu-id="7eb20-333">非基元值的唯一对象标识符 \ (\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-333">Unique object identifier \(for non-primitive values\).</span></span> |  
| <span data-ttu-id="7eb20-334">msDebuggerPropertyId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-334">msDebuggerPropertyId \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-335">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-335">**Experimental**.</span></span>  <span data-ttu-id="7eb20-336">Microsoft：此对象的关联调试器属性 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb20-336">Microsoft:  The associated debugger property ID for this object.</span></span> |  

---  

### <a name="propertydescriptor-object"></a><span data-ttu-id="7eb20-337">PropertyDescriptor 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-337">PropertyDescriptor object</span></span>  

<a name="propertydescriptor"></a>  

<span data-ttu-id="7eb20-338">对象属性描述符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-338">Object property descriptor.</span></span>  

| <span data-ttu-id="7eb20-339">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-339">Properties</span></span> | <span data-ttu-id="7eb20-340">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-340">Type</span></span> | <span data-ttu-id="7eb20-341">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-341">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-342">name</span><span class="sxs-lookup"><span data-stu-id="7eb20-342">name</span></span> | `string` | <span data-ttu-id="7eb20-343">属性名称或符号说明。</span><span class="sxs-lookup"><span data-stu-id="7eb20-343">Property name or symbol description.</span></span> |  
| <span data-ttu-id="7eb20-344">value \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-344">value \(optional\)</span></span> | [<span data-ttu-id="7eb20-345">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-345">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-346">与属性关联的值。</span><span class="sxs-lookup"><span data-stu-id="7eb20-346">The value associated with the property.</span></span> |  
| <span data-ttu-id="7eb20-347">可写 \ (可选\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-347">writable \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="7eb20-348">如果与该属性关联的值可能已更改 \ (数据描述符\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-348">if the value associated with the property may be changed \(data descriptors only\).</span></span> |  
| <span data-ttu-id="7eb20-349">获取 \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-349">get \(optional\)</span></span> | [<span data-ttu-id="7eb20-350">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-350">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-351">充当属性 getter 的函数，或者如果没有 `undefined` getter \ (访问器描述符\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-351">A function which serves as a getter for the property, or `undefined` if there is no getter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="7eb20-352">set \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-352">set \(optional\)</span></span> | [<span data-ttu-id="7eb20-353">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-353">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-354">充当属性的设置器的函数，或者如果没有设置器 `undefined` \ (访问器描述符\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-354">A function which serves as a setter for the property, or `undefined` if there is no setter \(accessor descriptors only\).</span></span> |  
| <span data-ttu-id="7eb20-355">可配置</span><span class="sxs-lookup"><span data-stu-id="7eb20-355">configurable</span></span> | `boolean` | `True` <span data-ttu-id="7eb20-356">如果此属性描述符的类型可能更改，并且该属性可能从相应的对象中删除。</span><span class="sxs-lookup"><span data-stu-id="7eb20-356">if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span> |  
| <span data-ttu-id="7eb20-357">enumerable</span><span class="sxs-lookup"><span data-stu-id="7eb20-357">enumerable</span></span> | `boolean` | `True` <span data-ttu-id="7eb20-358">如果此属性在枚举相应对象的属性期间显示。</span><span class="sxs-lookup"><span data-stu-id="7eb20-358">if this property shows up during enumeration of the properties on the corresponding object.</span></span> |  
| <span data-ttu-id="7eb20-359">wasThrown \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-359">wasThrown \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="7eb20-360">如果在评估期间引发结果。</span><span class="sxs-lookup"><span data-stu-id="7eb20-360">if the result was thrown during the evaluation.</span></span> |  
| <span data-ttu-id="7eb20-361">isOwn \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-361">isOwn \(optional\)</span></span> | `boolean` | `True` <span data-ttu-id="7eb20-362">属性是否归对象所有。</span><span class="sxs-lookup"><span data-stu-id="7eb20-362">if the property is owned for the object.</span></span> |  
| <span data-ttu-id="7eb20-363">msReturnValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-363">msReturnValue \(optional\)</span></span> | `boolean` | <span data-ttu-id="7eb20-364">**实验**性 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-364">**Experimental**.</span></span>  <span data-ttu-id="7eb20-365">Microsoft：  `True` 如果该属性是返回值。</span><span class="sxs-lookup"><span data-stu-id="7eb20-365">Microsoft:  `True` if the property is a return value.</span></span> |  
| <span data-ttu-id="7eb20-366">symbol \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-366">symbol \(optional\)</span></span> | [<span data-ttu-id="7eb20-367">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-367">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-368">属性符号对象，如果属性的类型 `symbol` 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-368">Property symbol object, if the property is of the `symbol` type.</span></span> |  

---  

### <a name="callargument-object"></a><span data-ttu-id="7eb20-369">CallArgument 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-369">CallArgument object</span></span>  

<a name="callargument"></a>  

<span data-ttu-id="7eb20-370">代表函数调用参数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-370">Represents function call argument.</span></span>  <span data-ttu-id="7eb20-371">应指定远程对象 ID、基元、不可erializable 基元值 (`objectId` `value` \) 的 \) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-371">Either remote object ID `objectId`, primitive `value`, unserializable primitive value, or neither of \(for undefined\) them should be specified.</span></span>  

| <span data-ttu-id="7eb20-372">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-372">Properties</span></span> | <span data-ttu-id="7eb20-373">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-373">Type</span></span> | <span data-ttu-id="7eb20-374">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-374">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-375">value \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-375">value \(optional\)</span></span> | `any` | <span data-ttu-id="7eb20-376">基元值或可序列化的 javascript 对象。</span><span class="sxs-lookup"><span data-stu-id="7eb20-376">Primitive value or serializable javascript object.</span></span> |  
| <span data-ttu-id="7eb20-377">unserializableValue \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-377">unserializableValue \(optional\)</span></span> | [<span data-ttu-id="7eb20-378">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="7eb20-378">UnserializableValue</span></span>](#unserializablevalue) | <span data-ttu-id="7eb20-379">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="7eb20-379">Primitive value which can not be JSON-stringified.</span></span> |  
| <span data-ttu-id="7eb20-380">objectId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-380">objectId \(optional\)</span></span> | <span data-ttu-id="7eb20-381">[RemoteObjectId](#remoteobjectid)]</span><span class="sxs-lookup"><span data-stu-id="7eb20-381">[RemoteObjectId](#remoteobjectid)]</span></span> | <span data-ttu-id="7eb20-382">远程对象句柄。</span><span class="sxs-lookup"><span data-stu-id="7eb20-382">Remote object handle.</span></span> |  

---  

### <a name="executioncontextid-integer"></a><span data-ttu-id="7eb20-383">ExecutionContextId 整数</span><span class="sxs-lookup"><span data-stu-id="7eb20-383">ExecutionContextId integer</span></span>  

<a name="executioncontextid"></a>  

<span data-ttu-id="7eb20-384">执行上下文的 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb20-384">ID of an execution context.</span></span>  

&nbsp;  

---  

### <a name="executioncontextdescription-object"></a><span data-ttu-id="7eb20-385">ExecutionContextDescription 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-385">ExecutionContextDescription object</span></span>  

<a name="executioncontextdescription"></a>  

<span data-ttu-id="7eb20-386">独立世界的说明。</span><span class="sxs-lookup"><span data-stu-id="7eb20-386">Description of an isolated world.</span></span>  

| <span data-ttu-id="7eb20-387">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-387">Properties</span></span> | <span data-ttu-id="7eb20-388">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-388">Type</span></span> | <span data-ttu-id="7eb20-389">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-389">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-390">id</span><span class="sxs-lookup"><span data-stu-id="7eb20-390">id</span></span> | [<span data-ttu-id="7eb20-391">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-391">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="7eb20-392">执行上下文的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb20-392">Unique ID of the execution context.</span></span>  <span data-ttu-id="7eb20-393">它可用于指定执行上下文</span><span class="sxs-lookup"><span data-stu-id="7eb20-393">It can be used to specify in which execution context</span></span>
<span data-ttu-id="7eb20-394">应执行脚本评估。</span><span class="sxs-lookup"><span data-stu-id="7eb20-394">script evaluation should be performed.</span></span> |  
| <span data-ttu-id="7eb20-395">origin</span><span class="sxs-lookup"><span data-stu-id="7eb20-395">origin</span></span> | `string` | <span data-ttu-id="7eb20-396">执行上下文源。</span><span class="sxs-lookup"><span data-stu-id="7eb20-396">Execution context origin.</span></span> |  
| <span data-ttu-id="7eb20-397">name</span><span class="sxs-lookup"><span data-stu-id="7eb20-397">name</span></span> | `string` | <span data-ttu-id="7eb20-398">描述给定上下文的可读名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-398">Human readable name describing given context.</span></span> |  

---  

### <a name="exceptiondetails-object"></a><span data-ttu-id="7eb20-399">ExceptionDetails 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-399">ExceptionDetails object</span></span>  

<a name="exceptiondetails"></a>  

<span data-ttu-id="7eb20-400">有关脚本编译 (过程中) 异常或错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="7eb20-400">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>  

| <span data-ttu-id="7eb20-401">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-401">Properties</span></span> | <span data-ttu-id="7eb20-402">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-402">Type</span></span> | <span data-ttu-id="7eb20-403">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-403">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-404">exceptionId</span><span class="sxs-lookup"><span data-stu-id="7eb20-404">exceptionId</span></span> | `integer` | <span data-ttu-id="7eb20-405">异常 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb20-405">Exception ID.</span></span> |  
| <span data-ttu-id="7eb20-406">文本</span><span class="sxs-lookup"><span data-stu-id="7eb20-406">text</span></span> | `string` | <span data-ttu-id="7eb20-407">异常文本，应在可用时与异常对象一同使用。</span><span class="sxs-lookup"><span data-stu-id="7eb20-407">Exception text, which should be used together with exception object when available.</span></span> |  
| <span data-ttu-id="7eb20-408">lineNumber</span><span class="sxs-lookup"><span data-stu-id="7eb20-408">lineNumber</span></span> | `integer` | <span data-ttu-id="7eb20-409">例外位置 \ (0\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-409">Line number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="7eb20-410">columnNumber</span><span class="sxs-lookup"><span data-stu-id="7eb20-410">columnNumber</span></span> | `integer` | <span data-ttu-id="7eb20-411">例外位置 \ (0\) 的列号。</span><span class="sxs-lookup"><span data-stu-id="7eb20-411">Column number of the exception location \(0-based\).</span></span> |  
| <span data-ttu-id="7eb20-412">scriptId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-412">scriptId \(optional\)</span></span> | [<span data-ttu-id="7eb20-413">ScriptId</span><span class="sxs-lookup"><span data-stu-id="7eb20-413">ScriptId</span></span>](#scriptid) | <span data-ttu-id="7eb20-414">异常位置的脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="7eb20-414">Script ID of the exception location.</span></span> |  
| <span data-ttu-id="7eb20-415">url \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-415">url \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-416">未报告脚本时使用的异常位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="7eb20-416">URL of the exception location, to be used when the script was not reported.</span></span> |  
| <span data-ttu-id="7eb20-417">stackTrace \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-417">stackTrace \(optional\)</span></span> | [<span data-ttu-id="7eb20-418">StackTrace</span><span class="sxs-lookup"><span data-stu-id="7eb20-418">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="7eb20-419">JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="7eb20-419">JavaScript stack trace if available.</span></span> |  
| <span data-ttu-id="7eb20-420">exception \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-420">exception \(optional\)</span></span> | [<span data-ttu-id="7eb20-421">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="7eb20-421">RemoteObject</span></span>](#remoteobject) | <span data-ttu-id="7eb20-422">Exception 对象（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="7eb20-422">Exception object if available.</span></span> |  
| <span data-ttu-id="7eb20-423">executionContextId \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-423">executionContextId \(optional\)</span></span> | [<span data-ttu-id="7eb20-424">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="7eb20-424">ExecutionContextId</span></span>](#executioncontextid) | <span data-ttu-id="7eb20-425">发生异常的上下文的标识符。</span><span class="sxs-lookup"><span data-stu-id="7eb20-425">Identifier of the context where exception happened.</span></span> |  

---  

### <a name="timestamp-integer"></a><span data-ttu-id="7eb20-426">时间戳整数</span><span class="sxs-lookup"><span data-stu-id="7eb20-426">Timestamp integer</span></span>  

<a name="timestamp"></a>  

<span data-ttu-id="7eb20-427">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="7eb20-427">Number of milliseconds since epoch.</span></span>  

&nbsp;  

---  

### <a name="callframe-object"></a><span data-ttu-id="7eb20-428">CallFrame 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-428">CallFrame object</span></span>  

<a name="callframe"></a>  

<span data-ttu-id="7eb20-429">运行时错误和断言的堆栈项。</span><span class="sxs-lookup"><span data-stu-id="7eb20-429">Stack entry for runtime errors and assertions.</span></span>  

| <span data-ttu-id="7eb20-430">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-430">Properties</span></span> | <span data-ttu-id="7eb20-431">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-431">Type</span></span> | <span data-ttu-id="7eb20-432">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-432">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-433">functionName</span><span class="sxs-lookup"><span data-stu-id="7eb20-433">functionName</span></span> | `string` | <span data-ttu-id="7eb20-434">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-434">JavaScript function name.</span></span> |  
| <span data-ttu-id="7eb20-435">scriptId</span><span class="sxs-lookup"><span data-stu-id="7eb20-435">scriptId</span></span> | [<span data-ttu-id="7eb20-436">ScriptId</span><span class="sxs-lookup"><span data-stu-id="7eb20-436">ScriptId</span></span>](#scriptid) | <span data-ttu-id="7eb20-437">JavaScript 脚本 ID。如果未启用调试器，ScriptId 将为空。</span><span class="sxs-lookup"><span data-stu-id="7eb20-437">JavaScript script id. ScriptId will be empty if debugger is not enabled.</span></span> |  
| <span data-ttu-id="7eb20-438">url</span><span class="sxs-lookup"><span data-stu-id="7eb20-438">url</span></span> | `string` | <span data-ttu-id="7eb20-439">JavaScript 脚本名称或 url。</span><span class="sxs-lookup"><span data-stu-id="7eb20-439">JavaScript script name or url.</span></span> |  
| <span data-ttu-id="7eb20-440">lineNumber</span><span class="sxs-lookup"><span data-stu-id="7eb20-440">lineNumber</span></span> | `integer` | <span data-ttu-id="7eb20-441">JavaScript 脚本行号 \ (0-based\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-441">JavaScript script line number \(0-based\).</span></span> |  
| <span data-ttu-id="7eb20-442">columnNumber</span><span class="sxs-lookup"><span data-stu-id="7eb20-442">columnNumber</span></span> | <span data-ttu-id="7eb20-443">整数</span><span class="sxs-lookup"><span data-stu-id="7eb20-443">integer</span></span> | <span data-ttu-id="7eb20-444">JavaScript 脚本列号 \ (0-based\) 。</span><span class="sxs-lookup"><span data-stu-id="7eb20-444">JavaScript script column number \(0-based\).</span></span> |  

---  

### <a name="stacktrace-object"></a><span data-ttu-id="7eb20-445">StackTrace 对象</span><span class="sxs-lookup"><span data-stu-id="7eb20-445">StackTrace object</span></span>  

<a name="stacktrace"></a>  

<span data-ttu-id="7eb20-446">断言或错误消息的呼叫帧。</span><span class="sxs-lookup"><span data-stu-id="7eb20-446">Call frames for assertions or error messages.</span></span>  

| <span data-ttu-id="7eb20-447">属性</span><span class="sxs-lookup"><span data-stu-id="7eb20-447">Properties</span></span> | <span data-ttu-id="7eb20-448">类型</span><span class="sxs-lookup"><span data-stu-id="7eb20-448">Type</span></span> | <span data-ttu-id="7eb20-449">详细信息</span><span class="sxs-lookup"><span data-stu-id="7eb20-449">Details</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="7eb20-450">description \ (optional\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-450">description \(optional\)</span></span> | `string` | <span data-ttu-id="7eb20-451">此堆栈跟踪的字符串标签。</span><span class="sxs-lookup"><span data-stu-id="7eb20-451">String label of this stack trace.</span></span>  <span data-ttu-id="7eb20-452">对于异步跟踪，这可能是启动异步调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-452">For async traces this may be a name of the function that initiated the async call.</span></span> |  
| <span data-ttu-id="7eb20-453">callFrames</span><span class="sxs-lookup"><span data-stu-id="7eb20-453">callFrames</span></span> | [<span data-ttu-id="7eb20-454">CallFrame[]</span><span class="sxs-lookup"><span data-stu-id="7eb20-454">CallFrame[]</span></span>](#callframe) | <span data-ttu-id="7eb20-455">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="7eb20-455">JavaScript function name.</span></span> |  
| <span data-ttu-id="7eb20-456">父 \ (可选\) </span><span class="sxs-lookup"><span data-stu-id="7eb20-456">parent \(optional\)</span></span> | [<span data-ttu-id="7eb20-457">StackTrace</span><span class="sxs-lookup"><span data-stu-id="7eb20-457">StackTrace</span></span>](#stacktrace) | <span data-ttu-id="7eb20-458">此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="7eb20-458">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span> |  

---  
