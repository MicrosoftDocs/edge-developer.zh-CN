---
description: 对运行时域的引用。 运行时域通过远程计算和镜像对象公开 JavaScript 运行时。 计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。 原始对象将保留在内存中，除非它们被显式释放。
title: 运行时域-DevTools 协议版本0。2
author: pelavall
ms.author: pelavall
ms.date: 8/17/2018
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: 504f944f7a8389450685b40cdd010b54c3a7ba4e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563395"
---
# <span data-ttu-id="513b3-106">运行时</span><span class="sxs-lookup"><span data-stu-id="513b3-106">Runtime</span></span>
<span data-ttu-id="513b3-107">运行时域通过远程计算和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="513b3-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="513b3-108">计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="513b3-109">原始对象将保留在内存中，除非它们被显式释放。</span><span class="sxs-lookup"><span data-stu-id="513b3-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="513b3-110">方法</span><span class="sxs-lookup"><span data-stu-id="513b3-110">Methods</span></span>**](#methods) | <span data-ttu-id="513b3-111">[enable](#enable)、 [disable](#disable)、[求值](#evaluate)、 [callFunctionOn](#callfunctionon)、 [awaitPromise](#awaitpromise)、 [getProperties](#getproperties)、 [globalLexicalScopeNames](#globallexicalscopenames)、 [releaseObject](#releaseobject)、 [releaseObjectGroup](#releaseobjectgroup)、 [discardConsoleEntries](#discardconsoleentries)</span><span class="sxs-lookup"><span data-stu-id="513b3-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [awaitPromise](#awaitpromise), [getProperties](#getproperties), [globalLexicalScopeNames](#globallexicalscopenames), [releaseObject](#releaseobject), [releaseObjectGroup](#releaseobjectgroup), [discardConsoleEntries](#discardconsoleentries)</span></span> |
| [**<span data-ttu-id="513b3-112">事件</span><span class="sxs-lookup"><span data-stu-id="513b3-112">Events</span></span>**](#events) | <span data-ttu-id="513b3-113">[executionContextCreated](#executioncontextcreated)、 [executionContextDestroyed](#executioncontextdestroyed)、 [executionContextsCleared](#executioncontextscleared)、 [exceptionThrown](#exceptionthrown)、 [consoleAPICalled](#consoleapicalled)</span><span class="sxs-lookup"><span data-stu-id="513b3-113">[executionContextCreated](#executioncontextcreated), [executionContextDestroyed](#executioncontextdestroyed), [executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown), [consoleAPICalled](#consoleapicalled)</span></span> |
| [**<span data-ttu-id="513b3-114">类型</span><span class="sxs-lookup"><span data-stu-id="513b3-114">Types</span></span>**](#types) | <span data-ttu-id="513b3-115">[ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExecutionContextDescription](#executioncontextdescription)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="513b3-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExecutionContextDescription](#executioncontextdescription), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="513b3-116">方法</span><span class="sxs-lookup"><span data-stu-id="513b3-116">Methods</span></span>

### <span data-ttu-id="513b3-117">“启用”</span><span class="sxs-lookup"><span data-stu-id="513b3-117">enable</span></span>
<span data-ttu-id="513b3-118">启用 <code>executionContextCreated</code> 和事件的报告 <code>executionContextDestroyed</code> <code>executionContextsCleared</code> 。</span><span class="sxs-lookup"><span data-stu-id="513b3-118">Enables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span> <span data-ttu-id="513b3-119">启用报告后， <code>executionContextCreated</code> 将为每个现有执行上下文立即发送该事件。</span><span class="sxs-lookup"><span data-stu-id="513b3-119">When the reporting gets enabled the <code>executionContextCreated</code> event will be sent immediately for each existing execution context.</span></span>

</p>

---

### <span data-ttu-id="513b3-120">“禁用”</span><span class="sxs-lookup"><span data-stu-id="513b3-120">disable</span></span>
<span data-ttu-id="513b3-121">禁用 <code>executionContextCreated</code> 和事件的报告 <code>executionContextDestroyed</code> <code>executionContextsCleared</code> 。</span><span class="sxs-lookup"><span data-stu-id="513b3-121">Disables reporting of the <code>executionContextCreated</code>, <code>executionContextDestroyed</code> and <code>executionContextsCleared</code> events.</span></span>

</p>

---

### <span data-ttu-id="513b3-122">评判</span><span class="sxs-lookup"><span data-stu-id="513b3-122">evaluate</span></span>
<span data-ttu-id="513b3-123">计算全局对象上的表达式。</span><span class="sxs-lookup"><span data-stu-id="513b3-123">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-124">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-124">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-125">表达</span><span class="sxs-lookup"><span data-stu-id="513b3-125">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-126">要计算的表达式。</span><span class="sxs-lookup"><span data-stu-id="513b3-126">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-127">includeCommandLineAPI</span><span class="sxs-lookup"><span data-stu-id="513b3-127">includeCommandLineAPI</span></span> <br/> <i><span data-ttu-id="513b3-128">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-128">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-129">确定在评估期间命令行 API 是否应可用。</span><span class="sxs-lookup"><span data-stu-id="513b3-129">Determines whether Command Line API should be available during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-130">objectGroup</span><span class="sxs-lookup"><span data-stu-id="513b3-130">objectGroup</span></span> <br/> <i><span data-ttu-id="513b3-131">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-131">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-132">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-132">Symbolic group name that can be used to release multiple objects.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-133">silent</span><span class="sxs-lookup"><span data-stu-id="513b3-133">silent</span></span> <br/> <i><span data-ttu-id="513b3-134">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-134">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-135">在计算期间引发的静默模式异常不会报告，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="513b3-135">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="513b3-136">重写 <code>setPauseOnException</code> 状态。</span><span class="sxs-lookup"><span data-stu-id="513b3-136">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-137">contextId</span><span class="sxs-lookup"><span data-stu-id="513b3-137">contextId</span></span> <br/> <i><span data-ttu-id="513b3-138">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-138">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="513b3-139">指定要在其中执行计算的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="513b3-139">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="513b3-140">如果省略该参数，将在已检查页面的上下文中执行计算。</span><span class="sxs-lookup"><span data-stu-id="513b3-140">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-141">returnByValue</span><span class="sxs-lookup"><span data-stu-id="513b3-141">returnByValue</span></span> <br/> <i><span data-ttu-id="513b3-142">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-142">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-143">结果是否应为应由 value 发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-143">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-144">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="513b3-144">awaitPromise</span></span> <br/> <i><span data-ttu-id="513b3-145">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-145">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-146"><code>await</code>在解决已完成的承诺后，是否应执行结果值和返回。</span><span class="sxs-lookup"><span data-stu-id="513b3-146">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-147">返回</span><span class="sxs-lookup"><span data-stu-id="513b3-147">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-148">结果</span><span class="sxs-lookup"><span data-stu-id="513b3-148">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-149">评估结果。</span><span class="sxs-lookup"><span data-stu-id="513b3-149">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-150">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="513b3-150">callFunctionOn</span></span>
<span data-ttu-id="513b3-151">调用具有给定对象的给定声明的函数。</span><span class="sxs-lookup"><span data-stu-id="513b3-151">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="513b3-152">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-152">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-153">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-153">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-154">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="513b3-154">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-155">要调用的函数的声明。</span><span class="sxs-lookup"><span data-stu-id="513b3-155">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-156">objectId</span><span class="sxs-lookup"><span data-stu-id="513b3-156">objectId</span></span> <br/> <i><span data-ttu-id="513b3-157">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-157">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="513b3-158">要在其上调用函数的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-158">Identifier of the object to call function on.</span></span> <span data-ttu-id="513b3-159">应指定 "objectId" 或 "executionContextId"。</span><span class="sxs-lookup"><span data-stu-id="513b3-159">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="513b3-160">objectId 必须来自 Runtime。求值（）函数。</span><span class="sxs-lookup"><span data-stu-id="513b3-160">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-161">arguments</span><span class="sxs-lookup"><span data-stu-id="513b3-161">arguments</span></span> <br/> <i><span data-ttu-id="513b3-162">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-162">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="513b3-163">调用参数。</span><span class="sxs-lookup"><span data-stu-id="513b3-163">Call arguments.</span></span> <span data-ttu-id="513b3-164">所有调用参数都必须属于与目标对象相同的 JavaScript world。</span><span class="sxs-lookup"><span data-stu-id="513b3-164">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-165">silent</span><span class="sxs-lookup"><span data-stu-id="513b3-165">silent</span></span> <br/> <i><span data-ttu-id="513b3-166">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-167">在计算期间引发的静默模式异常不会报告，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="513b3-167">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="513b3-168">重写 <code>setPauseOnException</code> 状态。</span><span class="sxs-lookup"><span data-stu-id="513b3-168">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-169">returnByValue</span><span class="sxs-lookup"><span data-stu-id="513b3-169">returnByValue</span></span> <br/> <i><span data-ttu-id="513b3-170">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-170">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-171">结果是否应为应由 value 发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-171">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-172">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="513b3-172">awaitPromise</span></span> <br/> <i><span data-ttu-id="513b3-173">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-173">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-174"><code>await</code>在解决已完成的承诺后，是否应执行结果值和返回。</span><span class="sxs-lookup"><span data-stu-id="513b3-174">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-175">executionContextId</span><span class="sxs-lookup"><span data-stu-id="513b3-175">executionContextId</span></span> <br/> <i><span data-ttu-id="513b3-176">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-176">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="513b3-177">指定将用于调用函数的全局对象的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="513b3-177">Specifies execution context which global object will be used to call function on.</span></span> <span data-ttu-id="513b3-178">应指定 executionContextId 或 objectId。</span><span class="sxs-lookup"><span data-stu-id="513b3-178">Either executionContextId or objectId should be specified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-179">objectGroup</span><span class="sxs-lookup"><span data-stu-id="513b3-179">objectGroup</span></span> <br/> <i><span data-ttu-id="513b3-180">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-180">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-181">可用于释放多个对象的符号组名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-181">Symbolic group name that can be used to release multiple objects.</span></span> <span data-ttu-id="513b3-182">如果未指定 objectGroup，并且 objectId 为，则 objectGroup 将继承自对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-182">If objectGroup is not specified and objectId is, objectGroup will be inherited from object.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-183">返回</span><span class="sxs-lookup"><span data-stu-id="513b3-183">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-184">结果</span><span class="sxs-lookup"><span data-stu-id="513b3-184">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-185">呼叫结果。</span><span class="sxs-lookup"><span data-stu-id="513b3-185">Call result.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-186">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="513b3-186">awaitPromise</span></span>
<span data-ttu-id="513b3-187">将处理程序添加到具有给定承诺对象 id 的承诺。</span><span class="sxs-lookup"><span data-stu-id="513b3-187">Add handler to promise with given promise object id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-188">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-188">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-189">promiseObjectId</span><span class="sxs-lookup"><span data-stu-id="513b3-189">promiseObjectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="513b3-190">承诺的标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-190">Identifier of the promise.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-191">returnByValue</span><span class="sxs-lookup"><span data-stu-id="513b3-191">returnByValue</span></span> <br/> <i><span data-ttu-id="513b3-192">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-192">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-193">结果是否应为应由 value 发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-193">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-194">返回</span><span class="sxs-lookup"><span data-stu-id="513b3-194">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-195">结果</span><span class="sxs-lookup"><span data-stu-id="513b3-195">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-196">承诺结果。</span><span class="sxs-lookup"><span data-stu-id="513b3-196">Promise result.</span></span>  <span data-ttu-id="513b3-197">如果承诺被拒绝，将包含 "拒绝" 值。</span><span class="sxs-lookup"><span data-stu-id="513b3-197">Will contain rejected value if promise was rejected.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-198">getProperties</span><span class="sxs-lookup"><span data-stu-id="513b3-198">getProperties</span></span>
<span data-ttu-id="513b3-199">返回给定对象的属性。</span><span class="sxs-lookup"><span data-stu-id="513b3-199">Returns properties of a given object.</span></span> <span data-ttu-id="513b3-200">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-200">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-201">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-201">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-202">objectId</span><span class="sxs-lookup"><span data-stu-id="513b3-202">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="513b3-203">要为其返回属性的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-203">Identifier of the object to return properties for.</span></span> <span data-ttu-id="513b3-204">objectId 必须来自 evaluateOnCallFrame （）函数。</span><span class="sxs-lookup"><span data-stu-id="513b3-204">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-205">ownProperties</span><span class="sxs-lookup"><span data-stu-id="513b3-205">ownProperties</span></span> <br/> <i><span data-ttu-id="513b3-206">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-206">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-207">如果为 true，则返回仅属于元素本身的属性，而不是其原型链。</span><span class="sxs-lookup"><span data-stu-id="513b3-207">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-208">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="513b3-208">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="513b3-209">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-209">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="513b3-210">实验.</span><span class="sxs-lookup"><span data-stu-id="513b3-210">Experimental.</span></span> </b></span><span data-ttu-id="513b3-211">如果为 true，则仅返回访问器属性（具有 getter/setter）;内部属性也不会返回。</span><span class="sxs-lookup"><span data-stu-id="513b3-211">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-212">返回</span><span class="sxs-lookup"><span data-stu-id="513b3-212">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-213">结果</span><span class="sxs-lookup"><span data-stu-id="513b3-213">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="513b3-214">对象属性。</span><span class="sxs-lookup"><span data-stu-id="513b3-214">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-215">globalLexicalScopeNames</span><span class="sxs-lookup"><span data-stu-id="513b3-215">globalLexicalScopeNames</span></span>
<span data-ttu-id="513b3-216">从控制台全局范围内返回所有 let、常量和类变量。</span><span class="sxs-lookup"><span data-stu-id="513b3-216">Returns all let, const, and class variables from the console global scope.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-217">返回</span><span class="sxs-lookup"><span data-stu-id="513b3-217">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-218">别名</span><span class="sxs-lookup"><span data-stu-id="513b3-218">names</span></span></td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-219">releaseObject</span><span class="sxs-lookup"><span data-stu-id="513b3-219">releaseObject</span></span>
<span data-ttu-id="513b3-220">释放具有给定 id 的远程对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-220">Releases remote object with given id.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-221">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-221">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-222">objectId</span><span class="sxs-lookup"><span data-stu-id="513b3-222">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="513b3-223">要释放的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-223">Identifier of the object to release.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-224">releaseObjectGroup</span><span class="sxs-lookup"><span data-stu-id="513b3-224">releaseObjectGroup</span></span>
<span data-ttu-id="513b3-225">释放属于给定组的所有远程对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-225">Releases all remote objects that belong to a given group.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-226">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-226">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-227">objectGroup</span><span class="sxs-lookup"><span data-stu-id="513b3-227">objectGroup</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-228">符号对象组名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-228">Symbolic object group name.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-229">discardConsoleEntries</span><span class="sxs-lookup"><span data-stu-id="513b3-229">discardConsoleEntries</span></span>
<span data-ttu-id="513b3-230">放弃所收集的异常和控制台 API 调用。</span><span class="sxs-lookup"><span data-stu-id="513b3-230">Discards collected exceptions and console API calls.</span></span>

</p>

---

## <span data-ttu-id="513b3-231">事件</span><span class="sxs-lookup"><span data-stu-id="513b3-231">Events</span></span>

### <span data-ttu-id="513b3-232">executionContextCreated</span><span class="sxs-lookup"><span data-stu-id="513b3-232">executionContextCreated</span></span>
<span data-ttu-id="513b3-233">在创建新的执行上下文时发出。</span><span class="sxs-lookup"><span data-stu-id="513b3-233">Issued when new execution context is created.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-234">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-234">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-235">上下文</span><span class="sxs-lookup"><span data-stu-id="513b3-235">context</span></span></td>
            <td><a href="#executioncontextdescription"><code class="flyout">ExecutionContextDescription</code></a></td>
            <td><span data-ttu-id="513b3-236">新创建的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="513b3-236">A newly created execution context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-237">executionContextDestroyed</span><span class="sxs-lookup"><span data-stu-id="513b3-237">executionContextDestroyed</span></span>
<span data-ttu-id="513b3-238">在销毁执行上下文时发出。</span><span class="sxs-lookup"><span data-stu-id="513b3-238">Issued when execution context is destroyed.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-239">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-239">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-240">executionContextId</span><span class="sxs-lookup"><span data-stu-id="513b3-240">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="513b3-241">被破坏的上下文的 Id</span><span class="sxs-lookup"><span data-stu-id="513b3-241">Id of the destroyed context</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-242">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="513b3-242">executionContextsCleared</span></span>
<span data-ttu-id="513b3-243">在浏览器中清除所有 executionContexts 时发出</span><span class="sxs-lookup"><span data-stu-id="513b3-243">Issued when all executionContexts were cleared in browser</span></span>

</p>

---

### <span data-ttu-id="513b3-244">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="513b3-244">exceptionThrown</span></span>
<span data-ttu-id="513b3-245">当异常引发且未经处理时发出。</span><span class="sxs-lookup"><span data-stu-id="513b3-245">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-246">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-246">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-247">icmp</span><span class="sxs-lookup"><span data-stu-id="513b3-247">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="513b3-248">异常的时间戳。</span><span class="sxs-lookup"><span data-stu-id="513b3-248">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-249">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="513b3-249">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### <span data-ttu-id="513b3-250">consoleAPICalled</span><span class="sxs-lookup"><span data-stu-id="513b3-250">consoleAPICalled</span></span>


<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-251">参数</span><span class="sxs-lookup"><span data-stu-id="513b3-251">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-252">类型</span><span class="sxs-lookup"><span data-stu-id="513b3-252">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="513b3-253">允许的值：日志、信息、警告、错误、调试、断言、表、跟踪、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、startGroupCollapsed、endGroup</span><span class="sxs-lookup"><span data-stu-id="513b3-253">Allowed values: log, info, warning, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, timeStamp, startGroup, startGroupCollapsed, endGroup</span></span></i></td>
            <td><span data-ttu-id="513b3-254">通话的类型。</span><span class="sxs-lookup"><span data-stu-id="513b3-254">Type of the call.</span></span> <span data-ttu-id="513b3-255">这包括日志、信息、警告、错误、调试、断言、表、跟踪、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、groupEnd。</span><span class="sxs-lookup"><span data-stu-id="513b3-255">This includes log, info, warn, error, debug, assert, table, trace, dir, dirxml, clear, select, count, countReset, timeEnd, exception, timeStamp, group, groupCollapsed, groupEnd.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-256">args</span><span class="sxs-lookup"><span data-stu-id="513b3-256">args</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject[]</code></a></td>
            <td><span data-ttu-id="513b3-257">调用参数。</span><span class="sxs-lookup"><span data-stu-id="513b3-257">Call arguments.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-258">executionContextId</span><span class="sxs-lookup"><span data-stu-id="513b3-258">executionContextId</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="513b3-259">进行控制台调用的上下文的标识符</span><span class="sxs-lookup"><span data-stu-id="513b3-259">Identifier of the context where console call was made</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-260">icmp</span><span class="sxs-lookup"><span data-stu-id="513b3-260">timestamp</span></span> <br/> <i><span data-ttu-id="513b3-261">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-261">optional</span></span></i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="513b3-262">通话时间戳。</span><span class="sxs-lookup"><span data-stu-id="513b3-262">Call timestamp.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-263">stackTrace</span><span class="sxs-lookup"><span data-stu-id="513b3-263">stackTrace</span></span> <br/> <i><span data-ttu-id="513b3-264">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-264">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="513b3-265">捕获的堆栈跟踪（如果可用）</span><span class="sxs-lookup"><span data-stu-id="513b3-265">Stack trace captured if available</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

## <span data-ttu-id="513b3-266">类型</span><span class="sxs-lookup"><span data-stu-id="513b3-266">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="513b3-267">ScriptId</span><span class="sxs-lookup"><span data-stu-id="513b3-267">ScriptId</span></span> `string`

<span data-ttu-id="513b3-268">唯一的脚本标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-268">Unique script identifier.</span></span>

</p>

---

### <a name="remoteobjectid"></a> <span data-ttu-id="513b3-269">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="513b3-269">RemoteObjectId</span></span> `string`

<span data-ttu-id="513b3-270">唯一的对象标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-270">Unique object identifier.</span></span>

</p>

---

### <a name="unserializablevalue"></a> <span data-ttu-id="513b3-271">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="513b3-271">UnserializableValue</span></span> `string`

<span data-ttu-id="513b3-272">基元值，不能是 JSON-stringified。</span><span class="sxs-lookup"><span data-stu-id="513b3-272">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="513b3-273">允许值</span><span class="sxs-lookup"><span data-stu-id="513b3-273">Allowed Values</span></span>
<span data-ttu-id="513b3-274">无穷大、NaN、-无穷大、-0</span><span class="sxs-lookup"><span data-stu-id="513b3-274">Infinity, NaN, -Infinity, -0</span></span>
</p>

---

### <a name="remoteobject"></a> <span data-ttu-id="513b3-275">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="513b3-275">RemoteObject</span></span> `object`

<span data-ttu-id="513b3-276">镜像对象引用原始 JavaScript 对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-276">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-277">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-277">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-278">类型</span><span class="sxs-lookup"><span data-stu-id="513b3-278">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="513b3-279">允许的值： object、函数、undefined、string、number、boolean、符号</span><span class="sxs-lookup"><span data-stu-id="513b3-279">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="513b3-280">对象类型。</span><span class="sxs-lookup"><span data-stu-id="513b3-280">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-281">子类型</span><span class="sxs-lookup"><span data-stu-id="513b3-281">subtype</span></span> <br/> <i><span data-ttu-id="513b3-282">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-282">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="513b3-283">允许的值： null、错误、承诺、节点</span><span class="sxs-lookup"><span data-stu-id="513b3-283">Allowed values: null, error, promise, node</span></span></i></td>
            <td><span data-ttu-id="513b3-284">Object 子类型提示。</span><span class="sxs-lookup"><span data-stu-id="513b3-284">Object subtype hint.</span></span> <span data-ttu-id="513b3-285">仅为 <code>object</code> 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="513b3-285">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-286">缺少</span><span class="sxs-lookup"><span data-stu-id="513b3-286">className</span></span> <br/> <i><span data-ttu-id="513b3-287">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-287">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-288">对象类（构造函数）名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-288">Object class (constructor) name.</span></span> <span data-ttu-id="513b3-289">仅为 <code>object</code> 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="513b3-289">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-290">值</span><span class="sxs-lookup"><span data-stu-id="513b3-290">value</span></span> <br/> <i><span data-ttu-id="513b3-291">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-291">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="513b3-292">在基元值或 JSON 值（如果已请求）的情况下的远程对象值。</span><span class="sxs-lookup"><span data-stu-id="513b3-292">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-293">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="513b3-293">unserializableValue</span></span> <br/> <i><span data-ttu-id="513b3-294">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-294">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="513b3-295">不能为 JSON 的基元值-stringified 没有</span><span class="sxs-lookup"><span data-stu-id="513b3-295">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="513b3-296">，但获取此属性。</span><span class="sxs-lookup"><span data-stu-id="513b3-296">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-297">description</span><span class="sxs-lookup"><span data-stu-id="513b3-297">description</span></span> <br/> <i><span data-ttu-id="513b3-298">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-298">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-299">对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="513b3-299">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-300">objectId</span><span class="sxs-lookup"><span data-stu-id="513b3-300">objectId</span></span> <br/> <i><span data-ttu-id="513b3-301">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-301">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="513b3-302">唯一对象标识符（对于非基元值）。</span><span class="sxs-lookup"><span data-stu-id="513b3-302">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-303">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="513b3-303">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="513b3-304">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-304">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="513b3-305">实验.</span><span class="sxs-lookup"><span data-stu-id="513b3-305">Experimental.</span></span> </b></span><span data-ttu-id="513b3-306">Microsoft：此对象的关联调试器属性 id。</span><span class="sxs-lookup"><span data-stu-id="513b3-306">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="513b3-307">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="513b3-307">PropertyDescriptor</span></span> `object`

<span data-ttu-id="513b3-308">对象属性描述符。</span><span class="sxs-lookup"><span data-stu-id="513b3-308">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-309">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-309">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-310">name</span><span class="sxs-lookup"><span data-stu-id="513b3-310">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-311">属性名称或符号描述。</span><span class="sxs-lookup"><span data-stu-id="513b3-311">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-312">值</span><span class="sxs-lookup"><span data-stu-id="513b3-312">value</span></span> <br/> <i><span data-ttu-id="513b3-313">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-313">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-314">与属性关联的值。</span><span class="sxs-lookup"><span data-stu-id="513b3-314">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-315">全</span><span class="sxs-lookup"><span data-stu-id="513b3-315">writable</span></span> <br/> <i><span data-ttu-id="513b3-316">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-316">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-317">如果与属性关联的值可能更改（仅限数据描述符），则为 True。</span><span class="sxs-lookup"><span data-stu-id="513b3-317">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-318">获取</span><span class="sxs-lookup"><span data-stu-id="513b3-318">get</span></span> <br/> <i><span data-ttu-id="513b3-319">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-319">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-320">充当属性的 getter 或没有 <code>undefined</code> getter （仅限访问器描述符）的函数。</span><span class="sxs-lookup"><span data-stu-id="513b3-320">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-321">set</span><span class="sxs-lookup"><span data-stu-id="513b3-321">set</span></span> <br/> <i><span data-ttu-id="513b3-322">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-322">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-323">充当属性的 setter 的函数，或者没有 <code>undefined</code> setter （仅限访问器描述符）的函数。</span><span class="sxs-lookup"><span data-stu-id="513b3-323">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-324">旋钮</span><span class="sxs-lookup"><span data-stu-id="513b3-324">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-325">如果此属性描述符的类型可能已更改，并且该属性可能已从相应对象中删除，则为 True。</span><span class="sxs-lookup"><span data-stu-id="513b3-325">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-326">枚举</span><span class="sxs-lookup"><span data-stu-id="513b3-326">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-327">如果在对相应对象的属性进行枚举时显示此属性，则为 True。</span><span class="sxs-lookup"><span data-stu-id="513b3-327">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-328">wasThrown</span><span class="sxs-lookup"><span data-stu-id="513b3-328">wasThrown</span></span> <br/> <i><span data-ttu-id="513b3-329">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-329">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-330">如果计算期间引发了结果，则为 True。</span><span class="sxs-lookup"><span data-stu-id="513b3-330">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-331">isOwn</span><span class="sxs-lookup"><span data-stu-id="513b3-331">isOwn</span></span> <br/> <i><span data-ttu-id="513b3-332">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-332">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="513b3-333">如果属性为对象所拥有，则为 True。</span><span class="sxs-lookup"><span data-stu-id="513b3-333">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-334">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="513b3-334">msReturnValue</span></span> <br/> <i><span data-ttu-id="513b3-335">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-335">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="513b3-336">实验.</span><span class="sxs-lookup"><span data-stu-id="513b3-336">Experimental.</span></span> </b></span><span data-ttu-id="513b3-337">Microsoft：如果属性为返回值，则为 True。</span><span class="sxs-lookup"><span data-stu-id="513b3-337">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-338">符号</span><span class="sxs-lookup"><span data-stu-id="513b3-338">symbol</span></span> <br/> <i><span data-ttu-id="513b3-339">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-339">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-340">属性符号对象（如果属性属于 `symbol` 类型）。</span><span class="sxs-lookup"><span data-stu-id="513b3-340">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callargument"></a> <span data-ttu-id="513b3-341">CallArgument</span><span class="sxs-lookup"><span data-stu-id="513b3-341">CallArgument</span></span> `object`

<span data-ttu-id="513b3-342">表示函数调用参数。</span><span class="sxs-lookup"><span data-stu-id="513b3-342">Represents function call argument.</span></span> <span data-ttu-id="513b3-343">远程对象 id <code>objectId</code> 、基元 <code>value</code> 、unserializable 基元值或两者均不是（对于未定义的）都应指定它们。</span><span class="sxs-lookup"><span data-stu-id="513b3-343">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-344">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-344">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-345">值</span><span class="sxs-lookup"><span data-stu-id="513b3-345">value</span></span> <br/> <i><span data-ttu-id="513b3-346">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-346">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="513b3-347">基元值或可串行 javascript 对象。</span><span class="sxs-lookup"><span data-stu-id="513b3-347">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-348">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="513b3-348">unserializableValue</span></span> <br/> <i><span data-ttu-id="513b3-349">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-349">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="513b3-350">不能为 JSON 的 stringified 的基元值。</span><span class="sxs-lookup"><span data-stu-id="513b3-350">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-351">objectId</span><span class="sxs-lookup"><span data-stu-id="513b3-351">objectId</span></span> <br/> <i><span data-ttu-id="513b3-352">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-352">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="513b3-353">远程对象句柄。</span><span class="sxs-lookup"><span data-stu-id="513b3-353">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="executioncontextid"></a> <span data-ttu-id="513b3-354">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="513b3-354">ExecutionContextId</span></span> `integer`

<span data-ttu-id="513b3-355">执行上下文的 Id。</span><span class="sxs-lookup"><span data-stu-id="513b3-355">Id of an execution context.</span></span>

</p>

---

### <a name="executioncontextdescription"></a> <span data-ttu-id="513b3-356">ExecutionContextDescription</span><span class="sxs-lookup"><span data-stu-id="513b3-356">ExecutionContextDescription</span></span> `object`

<span data-ttu-id="513b3-357">已隔离世界的描述。</span><span class="sxs-lookup"><span data-stu-id="513b3-357">Description of an isolated world.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-358">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-358">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-359">id</span><span class="sxs-lookup"><span data-stu-id="513b3-359">id</span></span></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="513b3-360">执行上下文的唯一 id。</span><span class="sxs-lookup"><span data-stu-id="513b3-360">Unique id of the execution context.</span></span> <span data-ttu-id="513b3-361">它可用于指定应在哪个执行上下文脚本计算中执行。</span><span class="sxs-lookup"><span data-stu-id="513b3-361">It can be used to specify in which execution context script evaluation should be performed.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-362">原</span><span class="sxs-lookup"><span data-stu-id="513b3-362">origin</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-363">执行上下文原点。</span><span class="sxs-lookup"><span data-stu-id="513b3-363">Execution context origin.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-364">name</span><span class="sxs-lookup"><span data-stu-id="513b3-364">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-365">描述给定上下文的人类可读名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-365">Human readable name describing given context.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="exceptiondetails"></a> <span data-ttu-id="513b3-366">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="513b3-366">ExceptionDetails</span></span> `object`

<span data-ttu-id="513b3-367">有关在脚本编译或执行期间引发的异常（或错误）的详细信息。</span><span class="sxs-lookup"><span data-stu-id="513b3-367">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-368">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-368">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-369">exceptionId</span><span class="sxs-lookup"><span data-stu-id="513b3-369">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="513b3-370">异常 id。</span><span class="sxs-lookup"><span data-stu-id="513b3-370">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-371">文本</span><span class="sxs-lookup"><span data-stu-id="513b3-371">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-372">异常文本，应与异常对象一起使用（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="513b3-372">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-373">lineNumber</span><span class="sxs-lookup"><span data-stu-id="513b3-373">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="513b3-374">异常位置（从0开始）的行号。</span><span class="sxs-lookup"><span data-stu-id="513b3-374">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-375">columnNumber</span><span class="sxs-lookup"><span data-stu-id="513b3-375">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="513b3-376">异常位置（从0开始）的列号。</span><span class="sxs-lookup"><span data-stu-id="513b3-376">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-377">scriptId</span><span class="sxs-lookup"><span data-stu-id="513b3-377">scriptId</span></span> <br/> <i><span data-ttu-id="513b3-378">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-378">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="513b3-379">异常位置的脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="513b3-379">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-380">url</span><span class="sxs-lookup"><span data-stu-id="513b3-380">url</span></span> <br/> <i><span data-ttu-id="513b3-381">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-381">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-382">要在未报告脚本时使用的异常位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="513b3-382">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-383">stackTrace</span><span class="sxs-lookup"><span data-stu-id="513b3-383">stackTrace</span></span> <br/> <i><span data-ttu-id="513b3-384">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-384">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="513b3-385">JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="513b3-385">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-386">除了</span><span class="sxs-lookup"><span data-stu-id="513b3-386">exception</span></span> <br/> <i><span data-ttu-id="513b3-387">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-387">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="513b3-388">异常对象（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="513b3-388">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-389">executionContextId</span><span class="sxs-lookup"><span data-stu-id="513b3-389">executionContextId</span></span> <br/> <i><span data-ttu-id="513b3-390">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-390">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="513b3-391">发生异常的上下文的标识符。</span><span class="sxs-lookup"><span data-stu-id="513b3-391">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="timestamp"></a> <span data-ttu-id="513b3-392">时间戳</span><span class="sxs-lookup"><span data-stu-id="513b3-392">Timestamp</span></span> `integer`

<span data-ttu-id="513b3-393">自 epoch 以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="513b3-393">Number of milliseconds since epoch.</span></span>

</p>

---

### <a name="callframe"></a> <span data-ttu-id="513b3-394">CallFrame</span><span class="sxs-lookup"><span data-stu-id="513b3-394">CallFrame</span></span> `object`

<span data-ttu-id="513b3-395">运行时错误和断言的堆栈条目。</span><span class="sxs-lookup"><span data-stu-id="513b3-395">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-396">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-396">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-397">functionName</span><span class="sxs-lookup"><span data-stu-id="513b3-397">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-398">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-398">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-399">scriptId</span><span class="sxs-lookup"><span data-stu-id="513b3-399">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="513b3-400">JavaScript 脚本 id。如果未启用调试器，ScriptId 将为空。</span><span class="sxs-lookup"><span data-stu-id="513b3-400">JavaScript script id. ScriptId will be empty if debugger is not enabled.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-401">url</span><span class="sxs-lookup"><span data-stu-id="513b3-401">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-402">JavaScript 脚本名称或 url。</span><span class="sxs-lookup"><span data-stu-id="513b3-402">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-403">lineNumber</span><span class="sxs-lookup"><span data-stu-id="513b3-403">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="513b3-404">JavaScript 脚本行数（基于0）。</span><span class="sxs-lookup"><span data-stu-id="513b3-404">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-405">columnNumber</span><span class="sxs-lookup"><span data-stu-id="513b3-405">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="513b3-406">JavaScript 脚本列数（从0开始）。</span><span class="sxs-lookup"><span data-stu-id="513b3-406">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="stacktrace"></a> <span data-ttu-id="513b3-407">StackTrace</span><span class="sxs-lookup"><span data-stu-id="513b3-407">StackTrace</span></span> `object`

<span data-ttu-id="513b3-408">调用断言或错误消息的帧。</span><span class="sxs-lookup"><span data-stu-id="513b3-408">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="513b3-409">属性</span><span class="sxs-lookup"><span data-stu-id="513b3-409">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="513b3-410">description</span><span class="sxs-lookup"><span data-stu-id="513b3-410">description</span></span> <br/> <i><span data-ttu-id="513b3-411">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-411">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="513b3-412">此堆栈跟踪的字符串标签。</span><span class="sxs-lookup"><span data-stu-id="513b3-412">String label of this stack trace.</span></span> <span data-ttu-id="513b3-413">对于异步跟踪，这可能是启动异步调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-413">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-414">callFrames</span><span class="sxs-lookup"><span data-stu-id="513b3-414">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="513b3-415">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="513b3-415">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="513b3-416">代</span><span class="sxs-lookup"><span data-stu-id="513b3-416">parent</span></span> <br/> <i><span data-ttu-id="513b3-417">可选</span><span class="sxs-lookup"><span data-stu-id="513b3-417">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="513b3-418">在此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="513b3-418">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>
</p>

---
