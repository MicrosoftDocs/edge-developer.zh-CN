---
description: DevTools 协议版本 0.1 (运行时) EdgeHTML 协议参考。 运行时域通过远程评估和镜像对象公开 JavaScript 运行时。 评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。 原始对象将保留于内存中，除非显式释放它们。
title: '运行时域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 942a105199c8740fb7f7496b2a68e3eb0cc46fb4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232098"
---
# <span data-ttu-id="e72cf-106">运行时域 - DevTools 协议版本 0.1 (EdgeHTML) </span><span class="sxs-lookup"><span data-stu-id="e72cf-106">Runtime Domain - DevTools Protocol Version 0.1 (EdgeHTML)</span></span>  

<span data-ttu-id="e72cf-107">运行时域通过远程评估和镜像对象公开 JavaScript 运行时。</span><span class="sxs-lookup"><span data-stu-id="e72cf-107">Runtime domain exposes JavaScript runtime by means of remote evaluation and mirror objects.</span></span> <span data-ttu-id="e72cf-108">评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。</span><span class="sxs-lookup"><span data-stu-id="e72cf-108">Evaluation results are returned as mirror object that expose object type, string representation and unique identifier that can be used for further object reference.</span></span> <span data-ttu-id="e72cf-109">原始对象将保留于内存中，除非显式释放它们。</span><span class="sxs-lookup"><span data-stu-id="e72cf-109">Original objects are maintained in memory unless they are either explicitly released.</span></span>

| | |
|-|-|
| [**<span data-ttu-id="e72cf-110">方法</span><span class="sxs-lookup"><span data-stu-id="e72cf-110">Methods</span></span>**](#methods) | <span data-ttu-id="e72cf-111">[enable](#enable)， [disable](#disable)， [evaluate](#evaluate)， [callFunctionOn](#callfunctionon)， [getProperties](#getproperties)</span><span class="sxs-lookup"><span data-stu-id="e72cf-111">[enable](#enable), [disable](#disable), [evaluate](#evaluate), [callFunctionOn](#callfunctionon), [getProperties](#getproperties)</span></span> |
| [**<span data-ttu-id="e72cf-112">事件</span><span class="sxs-lookup"><span data-stu-id="e72cf-112">Events</span></span>**](#events) | <span data-ttu-id="e72cf-113">[executionContextsCleared](#executioncontextscleared)， [exceptionThrown](#exceptionthrown)</span><span class="sxs-lookup"><span data-stu-id="e72cf-113">[executionContextsCleared](#executioncontextscleared), [exceptionThrown](#exceptionthrown)</span></span> |
| [**<span data-ttu-id="e72cf-114">类型</span><span class="sxs-lookup"><span data-stu-id="e72cf-114">Types</span></span>**](#types) | <span data-ttu-id="e72cf-115">[ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace)</span><span class="sxs-lookup"><span data-stu-id="e72cf-115">[ScriptId](#scriptid), [RemoteObjectId](#remoteobjectid), [UnserializableValue](#unserializablevalue), [RemoteObject](#remoteobject), [PropertyDescriptor](#propertydescriptor), [CallArgument](#callargument), [ExecutionContextId](#executioncontextid), [ExceptionDetails](#exceptiondetails), [Timestamp](#timestamp), [CallFrame](#callframe), [StackTrace](#stacktrace)</span></span> |
## <span data-ttu-id="e72cf-116">方法</span><span class="sxs-lookup"><span data-stu-id="e72cf-116">Methods</span></span>

### <span data-ttu-id="e72cf-117">“启用”</span><span class="sxs-lookup"><span data-stu-id="e72cf-117">enable</span></span>
<span data-ttu-id="e72cf-118">启用事件 <code>executionContextsCleared</code> 报告。</span><span class="sxs-lookup"><span data-stu-id="e72cf-118">Enables reporting of the <code>executionContextsCleared</code> event.</span></span>


---

### <span data-ttu-id="e72cf-119">“禁用”</span><span class="sxs-lookup"><span data-stu-id="e72cf-119">disable</span></span>
<span data-ttu-id="e72cf-120">禁用事件 <code>executionContextsCleared</code> 报告。</span><span class="sxs-lookup"><span data-stu-id="e72cf-120">Disables reporting of the <code>executionContextsCleared</code> event.</span></span>


---

### <span data-ttu-id="e72cf-121">evaluate</span><span class="sxs-lookup"><span data-stu-id="e72cf-121">evaluate</span></span>
<span data-ttu-id="e72cf-122">计算全局对象的表达式。</span><span class="sxs-lookup"><span data-stu-id="e72cf-122">Evaluates expression on global object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-123">参数</span><span class="sxs-lookup"><span data-stu-id="e72cf-123">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-124">表达式</span><span class="sxs-lookup"><span data-stu-id="e72cf-124">expression</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-125">要计算表达式。</span><span class="sxs-lookup"><span data-stu-id="e72cf-125">Expression to evaluate.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-126">silent</span><span class="sxs-lookup"><span data-stu-id="e72cf-126">silent</span></span> <br/> <i><span data-ttu-id="e72cf-127">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-127">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-128">在静默模式下，不会报告评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="e72cf-128">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="e72cf-129">覆盖 <code>setPauseOnException</code> 状态。</span><span class="sxs-lookup"><span data-stu-id="e72cf-129">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-130">contextId</span><span class="sxs-lookup"><span data-stu-id="e72cf-130">contextId</span></span> <br/> <i><span data-ttu-id="e72cf-131">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-131">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="e72cf-132">指定要执行评估的执行上下文。</span><span class="sxs-lookup"><span data-stu-id="e72cf-132">Specifies in which execution context to perform evaluation.</span></span> <span data-ttu-id="e72cf-133">如果省略该参数，将在已检查页面的上下文中执行计算。</span><span class="sxs-lookup"><span data-stu-id="e72cf-133">If the parameter is omitted the evaluation will be performed in the context of the inspected page.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-134">returnByValue</span><span class="sxs-lookup"><span data-stu-id="e72cf-134">returnByValue</span></span> <br/> <i><span data-ttu-id="e72cf-135">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-135">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-136">结果是否应为按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="e72cf-136">Whether the result is expected to be a JSON object that should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-137">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="e72cf-137">awaitPromise</span></span> <br/> <i><span data-ttu-id="e72cf-138">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-138">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-139">在解析等待 <code>await</code> 的承诺后，是否应该对结果值执行和返回。</span><span class="sxs-lookup"><span data-stu-id="e72cf-139">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-140">返回</span><span class="sxs-lookup"><span data-stu-id="e72cf-140">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-141">result</span><span class="sxs-lookup"><span data-stu-id="e72cf-141">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-142">评估结果。</span><span class="sxs-lookup"><span data-stu-id="e72cf-142">Evaluation result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e72cf-143">callFunctionOn</span><span class="sxs-lookup"><span data-stu-id="e72cf-143">callFunctionOn</span></span>
<span data-ttu-id="e72cf-144">调用给定对象上具有给定声明的函数。</span><span class="sxs-lookup"><span data-stu-id="e72cf-144">Calls function with given declaration on the given object.</span></span> <span data-ttu-id="e72cf-145">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="e72cf-145">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-146">参数</span><span class="sxs-lookup"><span data-stu-id="e72cf-146">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-147">functionDeclaration</span><span class="sxs-lookup"><span data-stu-id="e72cf-147">functionDeclaration</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-148">要调用的函数的声明。</span><span class="sxs-lookup"><span data-stu-id="e72cf-148">Declaration of the function to call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-149">objectId</span><span class="sxs-lookup"><span data-stu-id="e72cf-149">objectId</span></span> <br/> <i><span data-ttu-id="e72cf-150">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-150">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="e72cf-151">要调用函数的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="e72cf-151">Identifier of the object to call function on.</span></span> <span data-ttu-id="e72cf-152">应指定 objectId 或 executionContextId。</span><span class="sxs-lookup"><span data-stu-id="e72cf-152">Either objectId or executionContextId should be specified.</span></span>  <span data-ttu-id="e72cf-153">objectId 必须来自 Runtime.evaluate () 函数。</span><span class="sxs-lookup"><span data-stu-id="e72cf-153">objectId must be from the Runtime.evaluate() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-154">arguments</span><span class="sxs-lookup"><span data-stu-id="e72cf-154">arguments</span></span> <br/> <i><span data-ttu-id="e72cf-155">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-155">optional</span></span></i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td><span data-ttu-id="e72cf-156">调用参数。</span><span class="sxs-lookup"><span data-stu-id="e72cf-156">Call arguments.</span></span> <span data-ttu-id="e72cf-157">所有调用参数都必须属于与目标对象相同的 JavaScript 世界。</span><span class="sxs-lookup"><span data-stu-id="e72cf-157">All call arguments must belong to the same JavaScript world as the target object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-158">silent</span><span class="sxs-lookup"><span data-stu-id="e72cf-158">silent</span></span> <br/> <i><span data-ttu-id="e72cf-159">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-159">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-160">在静默模式下，不会报告评估期间引发的异常，并且不会暂停执行。</span><span class="sxs-lookup"><span data-stu-id="e72cf-160">In silent mode exceptions thrown during evaluation are not reported and do not pause execution.</span></span> <span data-ttu-id="e72cf-161">覆盖 <code>setPauseOnException</code> 状态。</span><span class="sxs-lookup"><span data-stu-id="e72cf-161">Overrides <code>setPauseOnException</code> state.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-162">returnByValue</span><span class="sxs-lookup"><span data-stu-id="e72cf-162">returnByValue</span></span> <br/> <i><span data-ttu-id="e72cf-163">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-163">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-164">结果是否应为应按值发送的 JSON 对象。</span><span class="sxs-lookup"><span data-stu-id="e72cf-164">Whether the result is expected to be a JSON object which should be sent by value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-165">awaitPromise</span><span class="sxs-lookup"><span data-stu-id="e72cf-165">awaitPromise</span></span> <br/> <i><span data-ttu-id="e72cf-166">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-166">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-167">在解析等待 <code>await</code> 的承诺后，是否应该对结果值执行和返回。</span><span class="sxs-lookup"><span data-stu-id="e72cf-167">Whether execution should <code>await</code> for resulting value and return once awaited promise is resolved.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-168">返回</span><span class="sxs-lookup"><span data-stu-id="e72cf-168">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-169">result</span><span class="sxs-lookup"><span data-stu-id="e72cf-169">result</span></span></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-170">呼叫结果。</span><span class="sxs-lookup"><span data-stu-id="e72cf-170">Call result.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <span data-ttu-id="e72cf-171">getProperties</span><span class="sxs-lookup"><span data-stu-id="e72cf-171">getProperties</span></span>
<span data-ttu-id="e72cf-172">返回给定对象的属性。</span><span class="sxs-lookup"><span data-stu-id="e72cf-172">Returns properties of a given object.</span></span> <span data-ttu-id="e72cf-173">结果的对象组继承自目标对象。</span><span class="sxs-lookup"><span data-stu-id="e72cf-173">Object group of the result is inherited from the target object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-174">参数</span><span class="sxs-lookup"><span data-stu-id="e72cf-174">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-175">objectId</span><span class="sxs-lookup"><span data-stu-id="e72cf-175">objectId</span></span></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="e72cf-176">要返回其属性的对象的标识符。</span><span class="sxs-lookup"><span data-stu-id="e72cf-176">Identifier of the object to return properties for.</span></span>  <span data-ttu-id="e72cf-177">objectId 必须来自 Debugger.evaluateOnCallFrame () 函数。</span><span class="sxs-lookup"><span data-stu-id="e72cf-177">objectId must be from the Debugger.evaluateOnCallFrame() function.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-178">ownProperties</span><span class="sxs-lookup"><span data-stu-id="e72cf-178">ownProperties</span></span> <br/> <i><span data-ttu-id="e72cf-179">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-179">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-180">如果为 true，则返回仅属于元素本身的属性，而不是其原型链的属性。</span><span class="sxs-lookup"><span data-stu-id="e72cf-180">If true, returns properties belonging only to the element itself, not to its prototype chain.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-181">accessorPropertiesOnly</span><span class="sxs-lookup"><span data-stu-id="e72cf-181">accessorPropertiesOnly</span></span> <br/> <i><span data-ttu-id="e72cf-182">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-182">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="e72cf-183">实验。</span><span class="sxs-lookup"><span data-stu-id="e72cf-183">Experimental.</span></span> </b></span><span data-ttu-id="e72cf-184">如果为 true，则返回仅 (getter/setter 属性) 访问器属性;内部属性也不返回。</span><span class="sxs-lookup"><span data-stu-id="e72cf-184">If true, returns accessor properties (with getter/setter) only; internal properties are not returned either.</span></span></td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-185">返回</span><span class="sxs-lookup"><span data-stu-id="e72cf-185">Returns</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-186">result</span><span class="sxs-lookup"><span data-stu-id="e72cf-186">result</span></span></td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td><span data-ttu-id="e72cf-187">对象属性。</span><span class="sxs-lookup"><span data-stu-id="e72cf-187">Object properties.</span></span></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="e72cf-188">事件</span><span class="sxs-lookup"><span data-stu-id="e72cf-188">Events</span></span>

### <span data-ttu-id="e72cf-189">executionContextsCleared</span><span class="sxs-lookup"><span data-stu-id="e72cf-189">executionContextsCleared</span></span>
<span data-ttu-id="e72cf-190">在浏览器中清除所有 executionContexts 时发出</span><span class="sxs-lookup"><span data-stu-id="e72cf-190">Issued when all executionContexts were cleared in browser</span></span>


---

### <span data-ttu-id="e72cf-191">exceptionThrown</span><span class="sxs-lookup"><span data-stu-id="e72cf-191">exceptionThrown</span></span>
<span data-ttu-id="e72cf-192">引发和未处理异常时发出。</span><span class="sxs-lookup"><span data-stu-id="e72cf-192">Issued when exception was thrown and unhandled.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-193">参数</span><span class="sxs-lookup"><span data-stu-id="e72cf-193">Parameters</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-194">timestamp</span><span class="sxs-lookup"><span data-stu-id="e72cf-194">timestamp</span></span></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td><span data-ttu-id="e72cf-195">异常的时间戳。</span><span class="sxs-lookup"><span data-stu-id="e72cf-195">Timestamp of the exception.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-196">exceptionDetails</span><span class="sxs-lookup"><span data-stu-id="e72cf-196">exceptionDetails</span></span></td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## <span data-ttu-id="e72cf-197">类型</span><span class="sxs-lookup"><span data-stu-id="e72cf-197">Types</span></span>

### <a name="scriptid"></a> <span data-ttu-id="e72cf-198">ScriptId</span><span class="sxs-lookup"><span data-stu-id="e72cf-198">ScriptId</span></span> `string`

<span data-ttu-id="e72cf-199">唯一脚本标识符。</span><span class="sxs-lookup"><span data-stu-id="e72cf-199">Unique script identifier.</span></span>


---

### <a name="remoteobjectid"></a> <span data-ttu-id="e72cf-200">RemoteObjectId</span><span class="sxs-lookup"><span data-stu-id="e72cf-200">RemoteObjectId</span></span> `string`

<span data-ttu-id="e72cf-201">唯一对象标识符。</span><span class="sxs-lookup"><span data-stu-id="e72cf-201">Unique object identifier.</span></span>


---

### <a name="unserializablevalue"></a> <span data-ttu-id="e72cf-202">UnserializableValue</span><span class="sxs-lookup"><span data-stu-id="e72cf-202">UnserializableValue</span></span> `string`

<span data-ttu-id="e72cf-203">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="e72cf-203">Primitive value which cannot be JSON-stringified.</span></span>

##### <span data-ttu-id="e72cf-204">允许的值</span><span class="sxs-lookup"><span data-stu-id="e72cf-204">Allowed Values</span></span>
<span data-ttu-id="e72cf-205">Infinity、NaN、-Infinity、-0</span><span class="sxs-lookup"><span data-stu-id="e72cf-205">Infinity, NaN, -Infinity, -0</span></span>

---

### <a name="remoteobject"></a> <span data-ttu-id="e72cf-206">RemoteObject</span><span class="sxs-lookup"><span data-stu-id="e72cf-206">RemoteObject</span></span> `object`

<span data-ttu-id="e72cf-207">引用原始 JavaScript 对象的镜像对象。</span><span class="sxs-lookup"><span data-stu-id="e72cf-207">Mirror object referencing original JavaScript object.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-208">属性</span><span class="sxs-lookup"><span data-stu-id="e72cf-208">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-209">类型</span><span class="sxs-lookup"><span data-stu-id="e72cf-209">type</span></span></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="e72cf-210">允许的值：object、function、undefined、string、number、boolean、symbol</span><span class="sxs-lookup"><span data-stu-id="e72cf-210">Allowed values: object, function, undefined, string, number, boolean, symbol</span></span></i></td>
            <td><span data-ttu-id="e72cf-211">对象类型。</span><span class="sxs-lookup"><span data-stu-id="e72cf-211">Object type.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-212">subtype</span><span class="sxs-lookup"><span data-stu-id="e72cf-212">subtype</span></span> <br/> <i><span data-ttu-id="e72cf-213">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-213">optional</span></span></i></td>
            <td><code class="flyout">string</code> <br/> <i><span data-ttu-id="e72cf-214">允许的值：null、error、promise</span><span class="sxs-lookup"><span data-stu-id="e72cf-214">Allowed values: null, error, promise</span></span></i></td>
            <td><span data-ttu-id="e72cf-215">对象子类型提示。</span><span class="sxs-lookup"><span data-stu-id="e72cf-215">Object subtype hint.</span></span> <span data-ttu-id="e72cf-216">仅为 <code>object</code> 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="e72cf-216">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-217">className</span><span class="sxs-lookup"><span data-stu-id="e72cf-217">className</span></span> <br/> <i><span data-ttu-id="e72cf-218">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-218">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-219">对象类 (构造函数) 名称。</span><span class="sxs-lookup"><span data-stu-id="e72cf-219">Object class (constructor) name.</span></span> <span data-ttu-id="e72cf-220">仅为 <code>object</code> 类型值指定。</span><span class="sxs-lookup"><span data-stu-id="e72cf-220">Specified for <code>object</code> type values only.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-221">值</span><span class="sxs-lookup"><span data-stu-id="e72cf-221">value</span></span> <br/> <i><span data-ttu-id="e72cf-222">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-222">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="e72cf-223">如果请求远程对象值，则返回基元值 (JSON 值) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-223">Remote object value in case of primitive values or JSON values (if it was requested).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-224">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="e72cf-224">unserializableValue</span></span> <br/> <i><span data-ttu-id="e72cf-225">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-225">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="e72cf-226">不能为 JSON 字符串化的基元值没有</span><span class="sxs-lookup"><span data-stu-id="e72cf-226">Primitive value which can not be JSON-stringified does not have</span></span> <code>value</code><span data-ttu-id="e72cf-227">，但获取此属性。</span><span class="sxs-lookup"><span data-stu-id="e72cf-227">, but gets this property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-228">description</span><span class="sxs-lookup"><span data-stu-id="e72cf-228">description</span></span> <br/> <i><span data-ttu-id="e72cf-229">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-229">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-230">对象的字符串表示形式。</span><span class="sxs-lookup"><span data-stu-id="e72cf-230">String representation of the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-231">objectId</span><span class="sxs-lookup"><span data-stu-id="e72cf-231">objectId</span></span> <br/> <i><span data-ttu-id="e72cf-232">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-232">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="e72cf-233">非基 (值的唯一对象标识符) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-233">Unique object identifier (for non-primitive values).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-234">msDebuggerPropertyId</span><span class="sxs-lookup"><span data-stu-id="e72cf-234">msDebuggerPropertyId</span></span> <br/> <i><span data-ttu-id="e72cf-235">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-235">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b><span data-ttu-id="e72cf-236">实验。</span><span class="sxs-lookup"><span data-stu-id="e72cf-236">Experimental.</span></span> </b></span><span data-ttu-id="e72cf-237">Microsoft：此对象的关联调试器属性 ID。</span><span class="sxs-lookup"><span data-stu-id="e72cf-237">Microsoft: The associated debugger property id for this object.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="propertydescriptor"></a> <span data-ttu-id="e72cf-238">PropertyDescriptor</span><span class="sxs-lookup"><span data-stu-id="e72cf-238">PropertyDescriptor</span></span> `object`

<span data-ttu-id="e72cf-239">对象属性描述符。</span><span class="sxs-lookup"><span data-stu-id="e72cf-239">Object property descriptor.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-240">属性</span><span class="sxs-lookup"><span data-stu-id="e72cf-240">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-241">name</span><span class="sxs-lookup"><span data-stu-id="e72cf-241">name</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-242">属性名称或符号说明。</span><span class="sxs-lookup"><span data-stu-id="e72cf-242">Property name or symbol description.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-243">值</span><span class="sxs-lookup"><span data-stu-id="e72cf-243">value</span></span> <br/> <i><span data-ttu-id="e72cf-244">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-244">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-245">与属性关联的值。</span><span class="sxs-lookup"><span data-stu-id="e72cf-245">The value associated with the property.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-246">writable</span><span class="sxs-lookup"><span data-stu-id="e72cf-246">writable</span></span> <br/> <i><span data-ttu-id="e72cf-247">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-247">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-248">如此 如果与该属性关联的值可能更改 (描述符仅) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-248">True if the value associated with the property may be changed (data descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-249">获取</span><span class="sxs-lookup"><span data-stu-id="e72cf-249">get</span></span> <br/> <i><span data-ttu-id="e72cf-250">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-250">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-251">充当属性 getter 的函数，或者如果没有 <code>undefined</code> getter，则 (访问器描述符) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-251">A function which serves as a getter for the property, or <code>undefined</code> if there is no getter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-252">set</span><span class="sxs-lookup"><span data-stu-id="e72cf-252">set</span></span> <br/> <i><span data-ttu-id="e72cf-253">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-253">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-254">充当属性设置器的函数，或者如果没有设置器，则 (<code>undefined</code> 访问器描述符) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-254">A function which serves as a setter for the property, or <code>undefined</code> if there is no setter (accessor descriptors only).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-255">可配置</span><span class="sxs-lookup"><span data-stu-id="e72cf-255">configurable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-256">如此 如果此属性描述符的类型可能会更改，如果此属性可能从相应的对象中删除。</span><span class="sxs-lookup"><span data-stu-id="e72cf-256">True if the type of this property descriptor may be changed and if the property may be deleted from the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-257">enumerable</span><span class="sxs-lookup"><span data-stu-id="e72cf-257">enumerable</span></span></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-258">如果在枚举相应对象的属性期间显示此属性，则其属性值为 True。</span><span class="sxs-lookup"><span data-stu-id="e72cf-258">True if this property shows up during enumeration of the properties on the corresponding object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-259">wasThrown</span><span class="sxs-lookup"><span data-stu-id="e72cf-259">wasThrown</span></span> <br/> <i><span data-ttu-id="e72cf-260">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-260">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-261">如果在计算过程中引发结果，则其值为 True。</span><span class="sxs-lookup"><span data-stu-id="e72cf-261">True if the result was thrown during the evaluation.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-262">isOwn</span><span class="sxs-lookup"><span data-stu-id="e72cf-262">isOwn</span></span> <br/> <i><span data-ttu-id="e72cf-263">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-263">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span data-ttu-id="e72cf-264">如果属性归对象所有，则其属性值为 True。</span><span class="sxs-lookup"><span data-stu-id="e72cf-264">True if the property is owned for the object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-265">msReturnValue</span><span class="sxs-lookup"><span data-stu-id="e72cf-265">msReturnValue</span></span> <br/> <i><span data-ttu-id="e72cf-266">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-266">optional</span></span></i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b><span data-ttu-id="e72cf-267">实验。</span><span class="sxs-lookup"><span data-stu-id="e72cf-267">Experimental.</span></span> </b></span><span data-ttu-id="e72cf-268">Microsoft：如果该属性是返回值，则其值为 True。</span><span class="sxs-lookup"><span data-stu-id="e72cf-268">Microsoft: True if the property is a return value.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-269">symbol</span><span class="sxs-lookup"><span data-stu-id="e72cf-269">symbol</span></span> <br/> <i><span data-ttu-id="e72cf-270">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-270">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-271">属性符号对象，如果属性的类型 `symbol` 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-271">Property symbol object, if the property is of the `symbol` type.</span></span> </td>
        </tr>
    </tbody>
</table>

---

### <a name="callargument"></a> <span data-ttu-id="e72cf-272">CallArgument</span><span class="sxs-lookup"><span data-stu-id="e72cf-272">CallArgument</span></span> `object`

<span data-ttu-id="e72cf-273">代表函数调用参数。</span><span class="sxs-lookup"><span data-stu-id="e72cf-273">Represents function call argument.</span></span> <span data-ttu-id="e72cf-274">应指定远程对象 ID、基元、不可序列化基元 (或两者均) 未定义 <code>objectId</code> <code>value</code> 值。</span><span class="sxs-lookup"><span data-stu-id="e72cf-274">Either remote object id <code>objectId</code>, primitive <code>value</code>, unserializable primitive value or neither of (for undefined) them should be specified.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-275">属性</span><span class="sxs-lookup"><span data-stu-id="e72cf-275">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-276">值</span><span class="sxs-lookup"><span data-stu-id="e72cf-276">value</span></span> <br/> <i><span data-ttu-id="e72cf-277">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-277">optional</span></span></i></td>
            <td><code class="flyout">any</code></td>
            <td><span data-ttu-id="e72cf-278">基元值或可序列化的 javascript 对象。</span><span class="sxs-lookup"><span data-stu-id="e72cf-278">Primitive value or serializable javascript object.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-279">unserializableValue</span><span class="sxs-lookup"><span data-stu-id="e72cf-279">unserializableValue</span></span> <br/> <i><span data-ttu-id="e72cf-280">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-280">optional</span></span></i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td><span data-ttu-id="e72cf-281">不能为 JSON 字符串化的基元值。</span><span class="sxs-lookup"><span data-stu-id="e72cf-281">Primitive value which can not be JSON-stringified.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-282">objectId</span><span class="sxs-lookup"><span data-stu-id="e72cf-282">objectId</span></span> <br/> <i><span data-ttu-id="e72cf-283">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-283">optional</span></span></i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td><span data-ttu-id="e72cf-284">远程对象句柄。</span><span class="sxs-lookup"><span data-stu-id="e72cf-284">Remote object handle.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="executioncontextid"></a> <span data-ttu-id="e72cf-285">ExecutionContextId</span><span class="sxs-lookup"><span data-stu-id="e72cf-285">ExecutionContextId</span></span> `integer`

<span data-ttu-id="e72cf-286">执行上下文的 ID。</span><span class="sxs-lookup"><span data-stu-id="e72cf-286">Id of an execution context.</span></span>


---

### <a name="exceptiondetails"></a> <span data-ttu-id="e72cf-287">ExceptionDetails</span><span class="sxs-lookup"><span data-stu-id="e72cf-287">ExceptionDetails</span></span> `object`

<span data-ttu-id="e72cf-288">有关脚本编译 (过程中) 异常或错误的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e72cf-288">Detailed information about exception (or error) that was thrown during script compilation or execution.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-289">属性</span><span class="sxs-lookup"><span data-stu-id="e72cf-289">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-290">exceptionId</span><span class="sxs-lookup"><span data-stu-id="e72cf-290">exceptionId</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e72cf-291">异常 ID。</span><span class="sxs-lookup"><span data-stu-id="e72cf-291">Exception id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-292">文本</span><span class="sxs-lookup"><span data-stu-id="e72cf-292">text</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-293">例外文本，应在可用时与异常对象一同使用。</span><span class="sxs-lookup"><span data-stu-id="e72cf-293">Exception text, which should be used together with exception object when available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-294">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e72cf-294">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e72cf-295">例外位置的行号 (从 0) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-295">Line number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-296">columnNumber</span><span class="sxs-lookup"><span data-stu-id="e72cf-296">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e72cf-297">异常位置的列号 (从 0) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-297">Column number of the exception location (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-298">scriptId</span><span class="sxs-lookup"><span data-stu-id="e72cf-298">scriptId</span></span> <br/> <i><span data-ttu-id="e72cf-299">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-299">optional</span></span></i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="e72cf-300">异常位置的脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="e72cf-300">Script ID of the exception location.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-301">url</span><span class="sxs-lookup"><span data-stu-id="e72cf-301">url</span></span> <br/> <i><span data-ttu-id="e72cf-302">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-302">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-303">未报告脚本时使用的异常位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="e72cf-303">URL of the exception location, to be used when the script was not reported.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-304">stackTrace</span><span class="sxs-lookup"><span data-stu-id="e72cf-304">stackTrace</span></span> <br/> <i><span data-ttu-id="e72cf-305">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-305">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="e72cf-306">JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="e72cf-306">JavaScript stack trace if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-307">exception</span><span class="sxs-lookup"><span data-stu-id="e72cf-307">exception</span></span> <br/> <i><span data-ttu-id="e72cf-308">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-308">optional</span></span></i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td><span data-ttu-id="e72cf-309">Exception 对象（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="e72cf-309">Exception object if available.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-310">executionContextId</span><span class="sxs-lookup"><span data-stu-id="e72cf-310">executionContextId</span></span> <br/> <i><span data-ttu-id="e72cf-311">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-311">optional</span></span></i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td><span data-ttu-id="e72cf-312">发生异常的上下文的标识符。</span><span class="sxs-lookup"><span data-stu-id="e72cf-312">Identifier of the context where exception happened.</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="timestamp"></a> <span data-ttu-id="e72cf-313">时间戳</span><span class="sxs-lookup"><span data-stu-id="e72cf-313">Timestamp</span></span> `integer`

<span data-ttu-id="e72cf-314">自纪元以来的毫秒数。</span><span class="sxs-lookup"><span data-stu-id="e72cf-314">Number of milliseconds since epoch.</span></span>


---

### <a name="callframe"></a> <span data-ttu-id="e72cf-315">CallFrame</span><span class="sxs-lookup"><span data-stu-id="e72cf-315">CallFrame</span></span> `object`

<span data-ttu-id="e72cf-316">运行时错误和断言的堆栈项。</span><span class="sxs-lookup"><span data-stu-id="e72cf-316">Stack entry for runtime errors and assertions.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-317">属性</span><span class="sxs-lookup"><span data-stu-id="e72cf-317">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-318">functionName</span><span class="sxs-lookup"><span data-stu-id="e72cf-318">functionName</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-319">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="e72cf-319">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-320">scriptId</span><span class="sxs-lookup"><span data-stu-id="e72cf-320">scriptId</span></span></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td><span data-ttu-id="e72cf-321">JavaScript 脚本 ID。</span><span class="sxs-lookup"><span data-stu-id="e72cf-321">JavaScript script id.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-322">url</span><span class="sxs-lookup"><span data-stu-id="e72cf-322">url</span></span></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-323">JavaScript 脚本名称或 URL。</span><span class="sxs-lookup"><span data-stu-id="e72cf-323">JavaScript script name or url.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-324">lineNumber</span><span class="sxs-lookup"><span data-stu-id="e72cf-324">lineNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e72cf-325">JavaScript 脚本行号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-325">JavaScript script line number (0-based).</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-326">columnNumber</span><span class="sxs-lookup"><span data-stu-id="e72cf-326">columnNumber</span></span></td>
            <td><code class="flyout">integer</code></td>
            <td><span data-ttu-id="e72cf-327">JavaScript 脚本列号 (从 0 开始) 。</span><span class="sxs-lookup"><span data-stu-id="e72cf-327">JavaScript script column number (0-based).</span></span></td>
        </tr>
    </tbody>
</table>

---

### <a name="stacktrace"></a> <span data-ttu-id="e72cf-328">StackTrace</span><span class="sxs-lookup"><span data-stu-id="e72cf-328">StackTrace</span></span> `object`

<span data-ttu-id="e72cf-329">断言或错误消息的呼叫帧。</span><span class="sxs-lookup"><span data-stu-id="e72cf-329">Call frames for assertions or error messages.</span></span>

<table>
    <thead>
        <tr>
            <th><span data-ttu-id="e72cf-330">属性</span><span class="sxs-lookup"><span data-stu-id="e72cf-330">Properties</span></span></th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td><span data-ttu-id="e72cf-331">description</span><span class="sxs-lookup"><span data-stu-id="e72cf-331">description</span></span> <br/> <i><span data-ttu-id="e72cf-332">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-332">optional</span></span></i></td>
            <td><code class="flyout">string</code></td>
            <td><span data-ttu-id="e72cf-333">此堆栈跟踪的字符串标签。</span><span class="sxs-lookup"><span data-stu-id="e72cf-333">String label of this stack trace.</span></span> <span data-ttu-id="e72cf-334">对于异步跟踪，这可能是启动异步调用的函数的名称。</span><span class="sxs-lookup"><span data-stu-id="e72cf-334">For async traces this may be a name of the function that initiated the async call.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-335">callFrames</span><span class="sxs-lookup"><span data-stu-id="e72cf-335">callFrames</span></span></td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td><span data-ttu-id="e72cf-336">JavaScript 函数名称。</span><span class="sxs-lookup"><span data-stu-id="e72cf-336">JavaScript function name.</span></span></td>
        </tr>
        <tr>
            <td><span data-ttu-id="e72cf-337">parent</span><span class="sxs-lookup"><span data-stu-id="e72cf-337">parent</span></span> <br/> <i><span data-ttu-id="e72cf-338">可选</span><span class="sxs-lookup"><span data-stu-id="e72cf-338">optional</span></span></i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td><span data-ttu-id="e72cf-339">此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</span><span class="sxs-lookup"><span data-stu-id="e72cf-339">Asynchronous JavaScript stack trace that preceded this stack, if available.</span></span></td>
        </tr>
    </tbody>
</table>

---
