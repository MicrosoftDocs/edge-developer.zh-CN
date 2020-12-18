---
description: DevTools 协议版本 0.2 (运行时域的 EdgeHTML) 参考。 运行时域通过远程评估和镜像对象公开 JavaScript 运行时。 评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。 原始对象将保留于内存中，除非显式释放它们。
title: '运行时域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f18cca951b298e8b4d870a7d722f30c9d28ad346
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232461"
---
# <span data-ttu-id="ac2e1-106">运行时域 - DevTools 协议版本 0.2 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="ac2e1-106">Runtime Domain - DevTools Protocol Version 0.2 (EdgeHTML)</span></span>  

<span data-ttu-id="ac2e1-107">运行时域通过远程评估和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="ac2e1-108">评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="ac2e1-109">原始对象将保留于内存中，除非显式释放它们。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="ac2e1-110">方法</span><span class="sxs-lookup"><span data-stu-id="ac2e1-110">Methods</span></span>**](#methods) | <span data-ttu-id="ac2e1-111">[enable](#enable)， [disable](#disable)， [evaluate](#evaluate)， [callFunctionOn](#callfunctionon)， [awaitPromise](#awaitpromise)， [getProperties](#getproperties)， [globalLexicalScopeNames，](#globallexicalscopenames) [releaseObject](#releaseobject)， [releaseObjectGroup](#releaseobjectgroup)， [discardConsoleEntries](#discardconsoleentries)</span><span class="sxs-lookup"><span data-stu-id="ac2e1-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span></span> |
| [**<span data-ttu-id="ac2e1-112">事件</span><span class="sxs-lookup"><span data-stu-id="ac2e1-112">Events</span></span>**](#events) | <span data-ttu-id="ac2e1-113">[executionContextCreated](#executioncontextcreated)， [executionContextDestroyed](#executioncontextdestroyed)， [executionContextsCleared，](#executioncontextscleared) [exceptionThrown](#exceptionthrown)， [consoleAPICalled](#consoleapicalled)</span><span class="sxs-lookup"><span data-stu-id="ac2e1-113">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span></span> |
| [**<span data-ttu-id="ac2e1-114">类型</span><span class="sxs-lookup"><span data-stu-id="ac2e1-114">Types</span></span>**](#types) | <span data-ttu-id="ac2e1-115">[ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExecutionContextDescription](#executioncontextdescription)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="ac2e1-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="ac2e1-116">方法</span><span class="sxs-lookup"><span data-stu-id="ac2e1-116">Methods</span></span>

### <span data-ttu-id="ac2e1-117">“启用”</span><span class="sxs-lookup"><span data-stu-id="ac2e1-117">enable</span></span>
<span data-ttu-id="ac2e1-118">启用对 <code>executionContextCreated</code> 和 <code>executionContextDestroyed</code> 事件 <code>executionContextsCleared</code> 的报告。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-118">Enables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span> <span data-ttu-id="ac2e1-119">启用报告后，将立即针对每个现有执行上下文 <code>executionContextCreated</code> 发送事件。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-119">When the reporting gets enabled the <code>executionContextCreated</code> event will be sent immediately for each existing execution context.</span></span>

</p>

---

### <span data-ttu-id="ac2e1-120">“禁用”</span><span class="sxs-lookup"><span data-stu-id="ac2e1-120">disable</span></span>
<span data-ttu-id="ac2e1-121">禁用对 <code>executionContextCreated</code> 和 <code>executionContextDestroyed</code> 事件 <code>executionContextsCleared</code> 的报告。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-121">Disables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span>

</p>

---

### <span data-ttu-id="ac2e1-122">evaluate</span><span class="sxs-lookup"><span data-stu-id="ac2e1-122">evaluate</span></span>
<span data-ttu-id="ac2e1-123">计算全局对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-123">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-124">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-124">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-125">表达式</span><span class="sxs-lookup"><span data-stu-id="ac2e1-125">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-126">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-126">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-127">includeCommandLineAPI</span><span class="sxs-lookup"><span data-stu-id="ac2e1-127">includeCommandLineAPI</span></span> <br/> <i><span data-ttu-id="ac2e1-128">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-128">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-129">确定在评估期间命令行 API 是否可用。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-129">Determines whether Command Line API should be available during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-130">objectGroup</span><span class="sxs-lookup"><span data-stu-id="ac2e1-130">objectGroup</span></span> <br/> <i><span data-ttu-id="ac2e1-131">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-131">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-132">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-132">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-133">silent</span><span class="sxs-lookup"><span data-stu-id="ac2e1-133">silent</span></span> <br/> <i><span data-ttu-id="ac2e1-134">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-134">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-135">在静默模式下，不会报告评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-135">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="ac2e1-136">覆盖 <code>setPauseOnException</code> 状态。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-136">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-137">contextId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-137">contextId</span></span> <br/> <i><span data-ttu-id="ac2e1-138">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-138">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="ac2e1-139">指定要执行评估的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-139">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="ac2e1-140">如果省略该参数，将在已检查页面的上下文中执行计算。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-140">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-141">returnByValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-141">returnByValue</span></span> <br/> <i><span data-ttu-id="ac2e1-142">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-142">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-143">结果是否应为按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-143">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-144">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="ac2e1-144">awaitPromise</span></span> <br/> <i><span data-ttu-id="ac2e1-145">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-145">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-146">在解析等待 <code>await</code> 的承诺后，是否应该对结果值执行和返回。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-146">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-147">返回</span><span class="sxs-lookup"><span data-stu-id="ac2e1-147">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-148">result</span><span class="sxs-lookup"><span data-stu-id="ac2e1-148">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-149">评估结果。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-149">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-150">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="ac2e1-150">callFunctionOn</span></span>
<span data-ttu-id="ac2e1-151">调用给定对象上具有给定声明的函数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-151">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="ac2e1-152">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-152">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-153">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-153">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-154">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="ac2e1-154">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-155">要调用的函数的声明。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-155">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-156">objectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-156">objectId</span></span> <br/> <i><span data-ttu-id="ac2e1-157">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-157">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="ac2e1-158">要调用函数的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-158">Identifier of the object to call function on.</span></span> <span data-ttu-id="ac2e1-159">应指定 objectId 或 executionContextId。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-159">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="ac2e1-160">objectId 必须来自 Runtime.evaluate () 函数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-160">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-161">arguments</span><span class="sxs-lookup"><span data-stu-id="ac2e1-161">arguments</span></span> <br/> <i><span data-ttu-id="ac2e1-162">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-162">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="ac2e1-163">调用参数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-163">Call arguments.</span></span> <span data-ttu-id="ac2e1-164">所有调用参数都必须属于与目标对象相同的 JavaScript 世界。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-164">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-165">silent</span><span class="sxs-lookup"><span data-stu-id="ac2e1-165">silent</span></span> <br/> <i><span data-ttu-id="ac2e1-166">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-167">在静默模式下，不会报告评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-167">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="ac2e1-168">覆盖 <code>setPauseOnException</code> 状态。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-168">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-169">returnByValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-169">returnByValue</span></span> <br/> <i><span data-ttu-id="ac2e1-170">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-170">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-171">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-171">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-172">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="ac2e1-172">awaitPromise</span></span> <br/> <i><span data-ttu-id="ac2e1-173">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-173">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-174">在解析等待 <code>await</code> 的承诺后，是否应该对结果值执行和返回。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-174">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-175">executionContextId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-175">executionContextId</span></span> <br/> <i><span data-ttu-id="ac2e1-176">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-176">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="ac2e1-177">指定将用来调用函数的全局对象的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-177">Specifies execution context which global object will be used to call function on.</span></span> <span data-ttu-id="ac2e1-178">应指定 executionContextId 或 objectId。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-178">Either executionContextId or objectId should be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-179">objectGroup</span><span class="sxs-lookup"><span data-stu-id="ac2e1-179">objectGroup</span></span> <br/> <i><span data-ttu-id="ac2e1-180">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-180">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-181">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-181">Symbolic group name that can be used to release multiple objects.</span></span> <span data-ttu-id="ac2e1-182">如果未指定 objectGroup 且 objectId 为 objectId，则 objectGroup 将继承自对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-182">If objectGroup is not specified and objectId is, objectGroup will be inherited from object.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-183">返回</span><span class="sxs-lookup"><span data-stu-id="ac2e1-183">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-184">result</span><span class="sxs-lookup"><span data-stu-id="ac2e1-184">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-185">呼叫结果。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-185">Call result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-186">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="ac2e1-186">awaitPromise</span></span>
<span data-ttu-id="ac2e1-187">添加具有给定承诺对象 ID 的 promise 处理程序。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-187">Add handler to promise with given promise object id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-188">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-189">promiseObjectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-189">promiseObjectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="ac2e1-190">承诺的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-190">Identifier of the promise.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-191">returnByValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-191">returnByValue</span></span> <br/> <i><span data-ttu-id="ac2e1-192">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-192">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-193">结果是否应为按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-193">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-194">返回</span><span class="sxs-lookup"><span data-stu-id="ac2e1-194">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-195">result</span><span class="sxs-lookup"><span data-stu-id="ac2e1-195">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-196">承诺结果。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-196">Promise result.</span></span>  <span data-ttu-id="ac2e1-197">如果承诺被拒绝，将包含拒绝的值。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-197">Will contain rejected value if promise was rejected.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-198">getProperties</span><span class="sxs-lookup"><span data-stu-id="ac2e1-198">getProperties</span></span>
<span data-ttu-id="ac2e1-199">返回给定对象的属性。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-199">Returns properties of a given object.</span></span> <span data-ttu-id="ac2e1-200">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-200">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-201">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-201">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-202">objectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-202">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="ac2e1-203">要返回其属性的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-203">Identifier of the object to return properties for.</span></span> <span data-ttu-id="ac2e1-204">objectId 必须来自 Debugger.evaluateOnCallFrame () 函数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-204">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-205">ownProperties</span><span class="sxs-lookup"><span data-stu-id="ac2e1-205">ownProperties</span></span> <br/> <i><span data-ttu-id="ac2e1-206">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-206">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-207">如果为 true，则返回仅属于元素本身的属性，而不是其原型链的属性。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-207">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-208">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="ac2e1-208">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="ac2e1-209">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-209">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="ac2e1-210">实验。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-210">Experimental.</span></span> </b></span><span data-ttu-id="ac2e1-211">如果为 true，则返回仅 (getter/setter 属性) 访问器属性;内部属性也不返回。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-211">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-212">返回</span><span class="sxs-lookup"><span data-stu-id="ac2e1-212">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-213">result</span><span class="sxs-lookup"><span data-stu-id="ac2e1-213">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="ac2e1-214">对象属性。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-214">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-215">globalLexicalScopeNames</span><span class="sxs-lookup"><span data-stu-id="ac2e1-215">globalLexicalScopeNames</span></span>
<span data-ttu-id="ac2e1-216">从控制台全局范围返回所有 let、const 和类变量。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-216">Returns all let, const, and class variables from the console global scope.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-217">返回</span><span class="sxs-lookup"><span data-stu-id="ac2e1-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-218">names</span><span class="sxs-lookup"><span data-stu-id="ac2e1-218">names</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-219">releaseObject</span><span class="sxs-lookup"><span data-stu-id="ac2e1-219">releaseObject</span></span>
<span data-ttu-id="ac2e1-220">使用给定 ID 释放远程对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-220">Releases remote object with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-221">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-221">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-222">objectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-222">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="ac2e1-223">要释放的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-223">Identifier of the object to release.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-224">releaseObjectGroup</span><span class="sxs-lookup"><span data-stu-id="ac2e1-224">releaseObjectGroup</span></span>
<span data-ttu-id="ac2e1-225">释放属于给定组的所有远程对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-225">Releases all remote objects that belong to a given group.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-226">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-226">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-227">objectGroup</span><span class="sxs-lookup"><span data-stu-id="ac2e1-227">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-228">符号对象组名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-228">Symbolic object group name.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-229">discardConsoleEntries</span><span class="sxs-lookup"><span data-stu-id="ac2e1-229">discardConsoleEntries</span></span>
<span data-ttu-id="ac2e1-230">放弃收集的异常和控制台 API 调用。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-230">Discards collected exceptions and console API calls.</span></span>

</p>

---

## <span data-ttu-id="ac2e1-231">事件</span><span class="sxs-lookup"><span data-stu-id="ac2e1-231">Events</span></span>

### <span data-ttu-id="ac2e1-232">executionContextCreated</span><span class="sxs-lookup"><span data-stu-id="ac2e1-232">executionContextCreated</span></span>
<span data-ttu-id="ac2e1-233">在新建执行上下文时发出。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-233">Issued when new execution context is created.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-234">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-234">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-235">上下文</span><span class="sxs-lookup"><span data-stu-id="ac2e1-235">context</span></span></td>
            <td><a href="#executioncontextdescription"><code class="flyout">ExecutionContextDescription</code></a></td>
            <td><span data-ttu-id="ac2e1-236">新创建的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-236">A newly created execution context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-237">executionContextDestroyed</span><span class="sxs-lookup"><span data-stu-id="ac2e1-237">executionContextDestroyed</span></span>
<span data-ttu-id="ac2e1-238">在销毁执行上下文时发出。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-238">Issued when execution context is destroyed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-239">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-240">executionContextId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-240">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="ac2e1-241">已销毁上下文的 ID</span><span class="sxs-lookup"><span data-stu-id="ac2e1-241">Id of the destroyed context</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-242">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="ac2e1-242">executionContextsCleared</span></span>
<span data-ttu-id="ac2e1-243">在浏览器中清除所有 executionContexts 时发出</span><span class="sxs-lookup"><span data-stu-id="ac2e1-243">Issued when all executionContexts were cleared in browser</span></span>

</p>

---

### <span data-ttu-id="ac2e1-244">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="ac2e1-244">exceptionThrown</span></span>
<span data-ttu-id="ac2e1-245">引发和未处理异常时发出。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-245">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-246">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-246">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-247">timestamp</span><span class="sxs-lookup"><span data-stu-id="ac2e1-247">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="ac2e1-248">异常的时间戳。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-248">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-249">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="ac2e1-249">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="ac2e1-250">consoleAPICalled</span><span class="sxs-lookup"><span data-stu-id="ac2e1-250">consoleAPICalled</span></span>


<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-251">参数</span><span class="sxs-lookup"><span data-stu-id="ac2e1-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-252">类型</span><span class="sxs-lookup"><span data-stu-id="ac2e1-252">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="ac2e1-253">允许的值：log、info、warning、error、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、startGroupCollapsed、endGroup</span><span class="sxs-lookup"><span data-stu-id="ac2e1-253">Allowed values: log, info, warning, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, timeStamp, startGroup, startGroupCollapsed, endGroup</span></span></i></td>
            <td><span data-ttu-id="ac2e1-254">呼叫的类型。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-254">Type of the call.</span></span> <span data-ttu-id="ac2e1-255">这包括日志、信息、警告、错误、调试、断言、表、跟踪、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、groupEnd。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-255">This includes log, info, warn, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, exception, timeStamp, group, groupCollapsed, groupEnd.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-256">args</span><span class="sxs-lookup"><span data-stu-id="ac2e1-256">args</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject[]</code></a></td>
            <td><span data-ttu-id="ac2e1-257">调用参数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-257">Call arguments.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-258">executionContextId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-258">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="ac2e1-259">进行控制台调用的上下文的标识符</span><span class="sxs-lookup"><span data-stu-id="ac2e1-259">Identifier of the context where console call was made</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-260">timestamp</span><span class="sxs-lookup"><span data-stu-id="ac2e1-260">timestamp</span></span> <br/> <i><span data-ttu-id="ac2e1-261">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-261">optional</span></span></i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="ac2e1-262">调用时间戳。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-262">Call timestamp.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-263">stackTrace</span><span class="sxs-lookup"><span data-stu-id="ac2e1-263">stackTrace</span></span> <br/> <i><span data-ttu-id="ac2e1-264">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-264">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="ac2e1-265">堆栈跟踪捕获（如果可用）</span><span class="sxs-lookup"><span data-stu-id="ac2e1-265">Stack trace captured if available</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="ac2e1-266">类型</span><span class="sxs-lookup"><span data-stu-id="ac2e1-266">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="ac2e1-267">ScriptId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-267">ScriptId</span></span> `string`

<span data-ttu-id="ac2e1-268">唯一脚本标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-268">Unique script identifier.</span></span>

</p>

---

### <a name="remoteobjectid"></a> <span data-ttu-id="ac2e1-269">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-269">RemoteObjectId</span></span> `string`

<span data-ttu-id="ac2e1-270">唯一对象标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-270">Unique object identifier.</span></span>

</p>

---

### <a name="unserializablevalue"></a> <span data-ttu-id="ac2e1-271">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-271">UnserializableValue</span></span> `string`

<span data-ttu-id="ac2e1-272">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-272">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="ac2e1-273">允许的值</span><span class="sxs-lookup"><span data-stu-id="ac2e1-273">Allowed Values</span></span>
<span data-ttu-id="ac2e1-274">Infinity、NaN、-Infinity、-0</span><span class="sxs-lookup"><span data-stu-id="ac2e1-274">Infinity, NaN, -Infinity, -0</span></span>
</p>

---

### <a name="remoteobject"></a> <span data-ttu-id="ac2e1-275">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="ac2e1-275">RemoteObject</span></span> `object`

<span data-ttu-id="ac2e1-276">引用原始 JavaScript 对象的镜像对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-276">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-277">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-277">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-278">类型</span><span class="sxs-lookup"><span data-stu-id="ac2e1-278">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="ac2e1-279">允许的值：object、function、undefined、string、number、boolean、symbol</span><span class="sxs-lookup"><span data-stu-id="ac2e1-279">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="ac2e1-280">对象类型。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-280">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-281">subtype</span><span class="sxs-lookup"><span data-stu-id="ac2e1-281">subtype</span></span> <br/> <i><span data-ttu-id="ac2e1-282">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-282">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="ac2e1-283">允许的值：null、error、promise、node</span><span class="sxs-lookup"><span data-stu-id="ac2e1-283">Allowed values: null, error, promise, node</span></span></i></td>
            <td><span data-ttu-id="ac2e1-284">对象子类型提示。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-284">Object subtype hint.</span></span> <span data-ttu-id="ac2e1-285">仅为 <code>object</code> 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-285">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-286">className</span><span class="sxs-lookup"><span data-stu-id="ac2e1-286">className</span></span> <br/> <i><span data-ttu-id="ac2e1-287">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-287">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-288">对象类 (构造函数) 名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-288">Object class (constructor) name.</span></span> <span data-ttu-id="ac2e1-289">仅为 <code>object</code> 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-289">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-290">值</span><span class="sxs-lookup"><span data-stu-id="ac2e1-290">value</span></span> <br/> <i><span data-ttu-id="ac2e1-291">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-291">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="ac2e1-292">如果请求远程对象值，则返回基元值 (JSON 值) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-292">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-293">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-293">unserializableValue</span></span> <br/> <i><span data-ttu-id="ac2e1-294">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-294">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="ac2e1-295">不能为 JSON 字符串化的基元值没有</span><span class="sxs-lookup"><span data-stu-id="ac2e1-295">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="ac2e1-296">，但获取此属性。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-296">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-297">description</span><span class="sxs-lookup"><span data-stu-id="ac2e1-297">description</span></span> <br/> <i><span data-ttu-id="ac2e1-298">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-298">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-299">对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-299">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-300">objectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-300">objectId</span></span> <br/> <i><span data-ttu-id="ac2e1-301">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-301">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="ac2e1-302">非基 (值的唯一对象标识符) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-302">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-303">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-303">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="ac2e1-304">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-304">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="ac2e1-305">实验。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-305">Experimental.</span></span> </b></span><span data-ttu-id="ac2e1-306">Microsoft：此对象的关联调试器属性 ID。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-306">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="ac2e1-307">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="ac2e1-307">PropertyDescriptor</span></span> `object`

<span data-ttu-id="ac2e1-308">对象属性描述符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-308">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-309">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-309">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-310">name</span><span class="sxs-lookup"><span data-stu-id="ac2e1-310">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-311">属性名称或符号说明。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-311">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-312">值</span><span class="sxs-lookup"><span data-stu-id="ac2e1-312">value</span></span> <br/> <i><span data-ttu-id="ac2e1-313">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-313">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-314">与属性关联的值。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-314">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-315">writable</span><span class="sxs-lookup"><span data-stu-id="ac2e1-315">writable</span></span> <br/> <i><span data-ttu-id="ac2e1-316">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-316">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-317">如此 如果与该属性关联的值可能更改 (描述符仅) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-317">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-318">获取</span><span class="sxs-lookup"><span data-stu-id="ac2e1-318">get</span></span> <br/> <i><span data-ttu-id="ac2e1-319">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-319">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-320">充当属性 getter 的函数，或者如果没有 <code>undefined</code> getter，则 (访问器描述符) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-320">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-321">set</span><span class="sxs-lookup"><span data-stu-id="ac2e1-321">set</span></span> <br/> <i><span data-ttu-id="ac2e1-322">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-322">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-323">充当属性设置器的函数，或者如果没有设置器，则 (<code>undefined</code> 访问器描述符) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-323">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-324">可配置</span><span class="sxs-lookup"><span data-stu-id="ac2e1-324">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-325">如此 如果此属性描述符的类型可能会更改，如果此属性可能从相应的对象中删除。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-325">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-326">enumerable</span><span class="sxs-lookup"><span data-stu-id="ac2e1-326">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-327">如果在枚举相应对象的属性期间显示此属性，则其属性值为 True。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-327">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-328">wasThrown</span><span class="sxs-lookup"><span data-stu-id="ac2e1-328">wasThrown</span></span> <br/> <i><span data-ttu-id="ac2e1-329">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-329">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-330">如果在计算过程中引发结果，则其为 True。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-330">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-331">isOwn</span><span class="sxs-lookup"><span data-stu-id="ac2e1-331">isOwn</span></span> <br/> <i><span data-ttu-id="ac2e1-332">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-332">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="ac2e1-333">如果属性归对象所有，则其属性值为 True。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-333">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-334">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-334">msReturnValue</span></span> <br/> <i><span data-ttu-id="ac2e1-335">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-335">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="ac2e1-336">实验。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-336">Experimental.</span></span> </b></span><span data-ttu-id="ac2e1-337">Microsoft：如果该属性是返回值，则其值为 True。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-337">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-338">symbol</span><span class="sxs-lookup"><span data-stu-id="ac2e1-338">symbol</span></span> <br/> <i><span data-ttu-id="ac2e1-339">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-339">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-340">属性符号对象，如果属性的类型 `symbol` 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-340">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callargument"></a> <span data-ttu-id="ac2e1-341">CallArgument</span><span class="sxs-lookup"><span data-stu-id="ac2e1-341">CallArgument</span></span> `object`

<span data-ttu-id="ac2e1-342">代表函数调用参数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-342">Represents function call argument.</span></span> <span data-ttu-id="ac2e1-343">应指定远程对象 <code>objectId</code> ID、基元、不可序列化基元值 (未定义) <code>value</code> 值。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-343">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-344">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-344">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-345">值</span><span class="sxs-lookup"><span data-stu-id="ac2e1-345">value</span></span> <br/> <i><span data-ttu-id="ac2e1-346">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-346">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="ac2e1-347">基元值或可序列化的 javascript 对象。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-347">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-348">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="ac2e1-348">unserializableValue</span></span> <br/> <i><span data-ttu-id="ac2e1-349">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-349">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="ac2e1-350">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-350">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-351">objectId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-351">objectId</span></span> <br/> <i><span data-ttu-id="ac2e1-352">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-352">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="ac2e1-353">远程对象句柄。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-353">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="executioncontextid"></a> <span data-ttu-id="ac2e1-354">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-354">ExecutionContextId</span></span> `integer`

<span data-ttu-id="ac2e1-355">执行上下文的 ID。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-355">Id of an execution context.</span></span>

</p>

---

### <a name="executioncontextdescription"></a> <span data-ttu-id="ac2e1-356">ExecutionContextDescription</span><span class="sxs-lookup"><span data-stu-id="ac2e1-356">ExecutionContextDescription</span></span> `object`

<span data-ttu-id="ac2e1-357">独立世界的说明。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-357">Description of an isolated world.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-358">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-358">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-359">id</span><span class="sxs-lookup"><span data-stu-id="ac2e1-359">id</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="ac2e1-360">执行上下文的唯一 ID。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-360">Unique id of the execution context.</span></span> <span data-ttu-id="ac2e1-361">它可用于指定应在哪个执行上下文脚本评估中执行。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-361">It can be used to specify in which execution context script evaluation should be performed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-362">origin</span><span class="sxs-lookup"><span data-stu-id="ac2e1-362">origin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-363">执行上下文源。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-363">Execution context origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-364">name</span><span class="sxs-lookup"><span data-stu-id="ac2e1-364">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-365">描述给定上下文的可读名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-365">Human readable name describing given context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="exceptiondetails"></a> <span data-ttu-id="ac2e1-366">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="ac2e1-366">ExceptionDetails</span></span> `object`

<span data-ttu-id="ac2e1-367">有关脚本编译 (过程中) 异常或错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-367">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-368">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-369">exceptionId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-369">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="ac2e1-370">异常 ID。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-370">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-371">文本</span><span class="sxs-lookup"><span data-stu-id="ac2e1-371">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-372">例外文本，应在可用时与异常对象一同使用。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-372">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-373">lineNumber</span><span class="sxs-lookup"><span data-stu-id="ac2e1-373">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="ac2e1-374">异常位置的行号 (从 0) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-374">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-375">columnNumber</span><span class="sxs-lookup"><span data-stu-id="ac2e1-375">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="ac2e1-376">异常位置的列号 (从 0) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-376">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-377">scriptId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-377">scriptId</span></span> <br/> <i><span data-ttu-id="ac2e1-378">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-378">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="ac2e1-379">异常位置的脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-379">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-380">url</span><span class="sxs-lookup"><span data-stu-id="ac2e1-380">url</span></span> <br/> <i><span data-ttu-id="ac2e1-381">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-381">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-382">未报告脚本时使用的异常位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-382">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-383">stackTrace</span><span class="sxs-lookup"><span data-stu-id="ac2e1-383">stackTrace</span></span> <br/> <i><span data-ttu-id="ac2e1-384">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-384">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="ac2e1-385">JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-385">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-386">exception</span><span class="sxs-lookup"><span data-stu-id="ac2e1-386">exception</span></span> <br/> <i><span data-ttu-id="ac2e1-387">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-387">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="ac2e1-388">Exception 对象（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-388">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-389">executionContextId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-389">executionContextId</span></span> <br/> <i><span data-ttu-id="ac2e1-390">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-390">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="ac2e1-391">发生异常的上下文的标识符。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-391">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="timestamp"></a> <span data-ttu-id="ac2e1-392">时间戳</span><span class="sxs-lookup"><span data-stu-id="ac2e1-392">Timestamp</span></span> `integer`

<span data-ttu-id="ac2e1-393">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-393">Number of milliseconds since epoch.</span></span>

</p>

---

### <a name="callframe"></a> <span data-ttu-id="ac2e1-394">CallFrame</span><span class="sxs-lookup"><span data-stu-id="ac2e1-394">CallFrame</span></span> `object`

<span data-ttu-id="ac2e1-395">运行时错误和断言的堆栈项。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-395">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-396">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-396">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-397">functionName</span><span class="sxs-lookup"><span data-stu-id="ac2e1-397">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-398">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-398">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-399">scriptId</span><span class="sxs-lookup"><span data-stu-id="ac2e1-399">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="ac2e1-400">JavaScript 脚本 ID。如果未启用调试器，ScriptId 将为空。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-400">JavaScript script id. ScriptId will be empty if debugger is not enabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-401">url</span><span class="sxs-lookup"><span data-stu-id="ac2e1-401">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-402">JavaScript 脚本名称或 URL。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-402">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-403">lineNumber</span><span class="sxs-lookup"><span data-stu-id="ac2e1-403">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="ac2e1-404">JavaScript 脚本行号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-404">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-405">columnNumber</span><span class="sxs-lookup"><span data-stu-id="ac2e1-405">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="ac2e1-406">JavaScript 脚本列号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-406">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="stacktrace"></a> <span data-ttu-id="ac2e1-407">StackTrace</span><span class="sxs-lookup"><span data-stu-id="ac2e1-407">StackTrace</span></span> `object`

<span data-ttu-id="ac2e1-408">断言或错误消息的呼叫帧。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-408">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="ac2e1-409">属性</span><span class="sxs-lookup"><span data-stu-id="ac2e1-409">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="ac2e1-410">description</span><span class="sxs-lookup"><span data-stu-id="ac2e1-410">description</span></span> <br/> <i><span data-ttu-id="ac2e1-411">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-411">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="ac2e1-412">此堆栈跟踪的字符串标签。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-412">String label of this stack trace.</span></span> <span data-ttu-id="ac2e1-413">对于异步跟踪，这可能是启动异步调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-413">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-414">callFrames</span><span class="sxs-lookup"><span data-stu-id="ac2e1-414">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="ac2e1-415">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-415">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="ac2e1-416">parent</span><span class="sxs-lookup"><span data-stu-id="ac2e1-416">parent</span></span> <br/> <i><span data-ttu-id="ac2e1-417">可选</span><span class="sxs-lookup"><span data-stu-id="ac2e1-417">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="ac2e1-418">此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="ac2e1-418">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
