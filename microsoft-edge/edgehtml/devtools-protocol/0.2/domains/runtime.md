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
# 运行时域 - DevTools 协议版本 0.2 (EdgeHTML)   

运行时域通过远程评估和镜像对象公开 JavaScript 运行时。 评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。 原始对象将保留于内存中，除非显式释放它们。

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)， [disable](#disable)， [evaluate](#evaluate)， [callFunctionOn](#callfunctionon)， [awaitPromise](#awaitpromise)， [getProperties](#getproperties)， [globalLexicalScopeNames，](#globallexicalscopenames) [releaseObject](#releaseobject)， [releaseObjectGroup](#releaseobjectgroup)， [discardConsoleEntries](#discardconsoleentries) |
| [**事件**](#events) | [executionContextCreated](#executioncontextcreated)， [executionContextDestroyed](#executioncontextdestroyed)， [executionContextsCleared，](#executioncontextscleared) [exceptionThrown](#exceptionthrown)， [consoleAPICalled](#consoleapicalled) |
| [**类型**](#types) | [ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExecutionContextDescription](#executioncontextdescription)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace) |
## 方法

### “启用”
启用对 <code>executionContextCreated</code> 和 <code>executionContextDestroyed</code> 事件 <code>executionContextsCleared</code> 的报告。 启用报告后，将立即针对每个现有执行上下文 <code>executionContextCreated</code> 发送事件。

</p>

---

### “禁用”
禁用对 <code>executionContextCreated</code> 和 <code>executionContextDestroyed</code> 事件 <code>executionContextsCleared</code> 的报告。

</p>

---

### evaluate
计算全局对象的表达式。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>表达式</td>
            <td><code class="flyout">string</code></td>
            <td>要计算表达式。</td>
        </tr>
        <tr>
            <td>includeCommandLineAPI <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>确定在评估期间命令行 API 是否可用。</td>
        </tr>
        <tr>
            <td>objectGroup <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>可用于释放多个对象的符号组名称。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>在静默模式下，不会报告评估期间引发的异常，并且不会暂停执行。 覆盖 <code>setPauseOnException</code> 状态。</td>
        </tr>
        <tr>
            <td>contextId <br/> <i>可选</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>指定要执行评估的执行上下文。 如果省略该参数，将在已检查页面的上下文中执行计算。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>结果是否应为按值发送的 JSON 对象。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>在解析等待 <code>await</code> 的承诺后，是否应该对结果值执行和返回。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>result</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>评估结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### callFunctionOn
调用给定对象上具有给定声明的函数。 结果的对象组继承自目标对象。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>functionDeclaration</td>
            <td><code class="flyout">string</code></td>
            <td>要调用的函数的声明。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>可选</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>要调用函数的对象的标识符。 应指定 objectId 或 executionContextId。  objectId 必须来自 Runtime.evaluate () 函数。</td>
        </tr>
        <tr>
            <td>arguments <br/> <i>可选</i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td>调用参数。 所有调用参数都必须属于与目标对象相同的 JavaScript 世界。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>在静默模式下，不会报告评估期间引发的异常，并且不会暂停执行。 覆盖 <code>setPauseOnException</code> 状态。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>结果是否应为应按值发送的 JSON 对象。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>在解析等待 <code>await</code> 的承诺后，是否应该对结果值执行和返回。</td>
        </tr>
        <tr>
            <td>executionContextId <br/> <i>可选</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>指定将用来调用函数的全局对象的执行上下文。 应指定 executionContextId 或 objectId。</td>
        </tr>
        <tr>
            <td>objectGroup <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>可用于释放多个对象的符号组名称。 如果未指定 objectGroup 且 objectId 为 objectId，则 objectGroup 将继承自对象。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>result</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>呼叫结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### awaitPromise
添加具有给定承诺对象 ID 的 promise 处理程序。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>promiseObjectId</td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>承诺的标识符。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>结果是否应为按值发送的 JSON 对象。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>result</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>承诺结果。  如果承诺被拒绝，将包含拒绝的值。</td>
        </tr>
    </tbody>
</table>
</p>

---

### getProperties
返回给定对象的属性。 结果的对象组继承自目标对象。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>objectId</td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>要返回其属性的对象的标识符。 objectId 必须来自 Debugger.evaluateOnCallFrame () 函数。</td>
        </tr>
        <tr>
            <td>ownProperties <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果为 true，则返回仅属于元素本身的属性，而不是其原型链的属性。</td>
        </tr>
        <tr>
            <td>accessorPropertiesOnly <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>实验。 </b></span>如果为 true，则返回仅 (getter/setter 属性) 访问器属性;内部属性也不返回。</td>
        </tr>
    </tbody>
</table>
<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>result</td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td>对象属性。</td>
        </tr>
    </tbody>
</table>
</p>

---

### globalLexicalScopeNames
从控制台全局范围返回所有 let、const 和类变量。

<table>
    <thead>
        <tr>
            <th>返回</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>names</td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### releaseObject
使用给定 ID 释放远程对象。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>objectId</td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>要释放的对象的标识符。 </td>
        </tr>
    </tbody>
</table>
</p>

---

### releaseObjectGroup
释放属于给定组的所有远程对象。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>objectGroup</td>
            <td><code class="flyout">string</code></td>
            <td>符号对象组名称。 </td>
        </tr>
    </tbody>
</table>
</p>

---

### discardConsoleEntries
放弃收集的异常和控制台 API 调用。

</p>

---

## 事件

### executionContextCreated
在新建执行上下文时发出。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>上下文</td>
            <td><a href="#executioncontextdescription"><code class="flyout">ExecutionContextDescription</code></a></td>
            <td>新创建的执行上下文。</td>
        </tr>
    </tbody>
</table>
</p>

---

### executionContextDestroyed
在销毁执行上下文时发出。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>executionContextId</td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>已销毁上下文的 ID</td>
        </tr>
    </tbody>
</table>
</p>

---

### executionContextsCleared
在浏览器中清除所有 executionContexts 时发出

</p>

---

### exceptionThrown
引发和未处理异常时发出。

<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>timestamp</td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td>异常的时间戳。</td>
        </tr>
        <tr>
            <td>exceptionDetails</td>
            <td><a href="#exceptiondetails"><code class="flyout">ExceptionDetails</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### consoleAPICalled


<table>
    <thead>
        <tr>
            <th>参数</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>类型</td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：log、info、warning、error、debug、assert、table、trace、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、startGroupCollapsed、endGroup</i></td>
            <td>呼叫的类型。 这包括日志、信息、警告、错误、调试、断言、表、跟踪、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、groupEnd。</td>
        </tr>
        <tr>
            <td>args</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject[]</code></a></td>
            <td>调用参数。</td>
        </tr>
        <tr>
            <td>executionContextId</td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>进行控制台调用的上下文的标识符</td>
        </tr>
        <tr>
            <td>timestamp <br/> <i>可选</i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td>调用时间戳。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>可选</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>堆栈跟踪捕获（如果可用）</td>
        </tr>
    </tbody>
</table>
</p>

---

## 类型

### <a name="scriptid"></a> ScriptId `string`

唯一脚本标识符。

</p>

---

### <a name="remoteobjectid"></a> RemoteObjectId `string`

唯一对象标识符。

</p>

---

### <a name="unserializablevalue"></a> UnserializableValue `string`

不能为 JSON 字符串化的基元值。

##### 允许的值
Infinity、NaN、-Infinity、-0
</p>

---

### <a name="remoteobject"></a> RemoteObject `object`

引用原始 JavaScript 对象的镜像对象。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>类型</td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：object、function、undefined、string、number、boolean、symbol</i></td>
            <td>对象类型。</td>
        </tr>
        <tr>
            <td>subtype <br/> <i>可选</i></td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：null、error、promise、node</i></td>
            <td>对象子类型提示。 仅为 <code>object</code> 类型值指定。</td>
        </tr>
        <tr>
            <td>className <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>对象类 (构造函数) 名称。 仅为 <code>object</code> 类型值指定。</td>
        </tr>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><code class="flyout">any</code></td>
            <td>如果请求远程对象值，则返回基元值 (JSON 值) 。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>可选</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>不能为 JSON 字符串化的基元值没有 <code>value</code>，但获取此属性。</td>
        </tr>
        <tr>
            <td>description <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>对象的字符串表示形式。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>可选</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>非基 (值的唯一对象标识符) 。</td>
        </tr>
        <tr>
            <td>msDebuggerPropertyId <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>实验。 </b></span>Microsoft：此对象的关联调试器属性 ID。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="propertydescriptor"></a> PropertyDescriptor `object`

对象属性描述符。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>属性名称或符号说明。</td>
        </tr>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>与属性关联的值。</td>
        </tr>
        <tr>
            <td>writable <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如此 如果与该属性关联的值可能更改 (描述符仅) 。</td>
        </tr>
        <tr>
            <td>获取 <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>充当属性 getter 的函数，或者如果没有 <code>undefined</code> getter，则 (访问器描述符) 。</td>
        </tr>
        <tr>
            <td>set <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>充当属性设置器的函数，或者如果没有设置器，则 (<code>undefined</code> 访问器描述符) 。</td>
        </tr>
        <tr>
            <td>可配置</td>
            <td><code class="flyout">boolean</code></td>
            <td>如此 如果此属性描述符的类型可能会更改，如果此属性可能从相应的对象中删除。</td>
        </tr>
        <tr>
            <td>enumerable</td>
            <td><code class="flyout">boolean</code></td>
            <td>如果在枚举相应对象的属性期间显示此属性，则其属性值为 True。</td>
        </tr>
        <tr>
            <td>wasThrown <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果在计算过程中引发结果，则其为 True。</td>
        </tr>
        <tr>
            <td>isOwn <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果属性归对象所有，则其属性值为 True。</td>
        </tr>
        <tr>
            <td>msReturnValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>实验。 </b></span>Microsoft：如果该属性是返回值，则其值为 True。</td>
        </tr>
        <tr>
            <td>symbol <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>属性符号对象，如果属性的类型 `symbol` 。 </td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callargument"></a> CallArgument `object`

代表函数调用参数。 应指定远程对象 <code>objectId</code> ID、基元、不可序列化基元值 (未定义) <code>value</code> 值。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><code class="flyout">any</code></td>
            <td>基元值或可序列化的 javascript 对象。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>可选</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>不能为 JSON 字符串化的基元值。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>可选</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>远程对象句柄。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="executioncontextid"></a> ExecutionContextId `integer`

执行上下文的 ID。

</p>

---

### <a name="executioncontextdescription"></a> ExecutionContextDescription `object`

独立世界的说明。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>id</td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>执行上下文的唯一 ID。 它可用于指定应在哪个执行上下文脚本评估中执行。</td>
        </tr>
        <tr>
            <td>origin</td>
            <td><code class="flyout">string</code></td>
            <td>执行上下文源。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>描述给定上下文的可读名称。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="exceptiondetails"></a> ExceptionDetails `object`

有关脚本编译 (过程中) 异常或错误的详细信息。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>exceptionId</td>
            <td><code class="flyout">integer</code></td>
            <td>异常 ID。</td>
        </tr>
        <tr>
            <td>文本</td>
            <td><code class="flyout">string</code></td>
            <td>例外文本，应在可用时与异常对象一同使用。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>异常位置的行号 (从 0) 。</td>
        </tr>
        <tr>
            <td>columnNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>异常位置的列号 (从 0) 。</td>
        </tr>
        <tr>
            <td>scriptId <br/> <i>可选</i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td>异常位置的脚本 ID。</td>
        </tr>
        <tr>
            <td>url <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>未报告脚本时使用的异常位置的 URL。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>可选</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>JavaScript 堆栈跟踪（如果可用）。</td>
        </tr>
        <tr>
            <td>exception <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>Exception 对象（如果可用）。</td>
        </tr>
        <tr>
            <td>executionContextId <br/> <i>可选</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>发生异常的上下文的标识符。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="timestamp"></a> 时间戳 `integer`

自纪元以来的毫秒数。

</p>

---

### <a name="callframe"></a> CallFrame `object`

运行时错误和断言的堆栈项。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>functionName</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript 函数名称。</td>
        </tr>
        <tr>
            <td>scriptId</td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td>JavaScript 脚本 ID。如果未启用调试器，ScriptId 将为空。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript 脚本名称或 URL。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript 脚本行号 (从 0 开始) 。</td>
        </tr>
        <tr>
            <td>columnNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript 脚本列号 (从 0 开始) 。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="stacktrace"></a> StackTrace `object`

断言或错误消息的呼叫帧。

<table>
    <thead>
        <tr>
            <th>属性</th>
            <th></th>
            <th></th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>description <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>此堆栈跟踪的字符串标签。 对于异步跟踪，这可能是启动异步调用的函数的名称。</td>
        </tr>
        <tr>
            <td>callFrames</td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td>JavaScript 函数名称。</td>
        </tr>
        <tr>
            <td>parent <br/> <i>可选</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</td>
        </tr>
    </tbody>
</table>
</p>

---
