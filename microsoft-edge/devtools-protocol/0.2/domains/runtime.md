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
# 运行时
运行时域通过远程计算和镜像对象公开 JavaScript 运行时。 计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。 原始对象将保留在内存中，除非它们被显式释放。

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)、 [disable](#disable)、[求值](#evaluate)、 [callFunctionOn](#callfunctionon)、 [awaitPromise](#awaitpromise)、 [getProperties](#getproperties)、 [globalLexicalScopeNames](#globallexicalscopenames)、 [releaseObject](#releaseobject)、 [releaseObjectGroup](#releaseobjectgroup)、 [discardConsoleEntries](#discardconsoleentries) |
| [**事件**](#events) | [executionContextCreated](#executioncontextcreated)、 [executionContextDestroyed](#executioncontextdestroyed)、 [executionContextsCleared](#executioncontextscleared)、 [exceptionThrown](#exceptionthrown)、 [consoleAPICalled](#consoleapicalled) |
| [**类型**](#types) | [ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExecutionContextDescription](#executioncontextdescription)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace) |
## 方法

### “启用”
启用 <code>executionContextCreated</code> 和事件的报告 <code>executionContextDestroyed</code> <code>executionContextsCleared</code> 。 启用报告后， <code>executionContextCreated</code> 将为每个现有执行上下文立即发送该事件。

</p>

---

### “禁用”
禁用 <code>executionContextCreated</code> 和事件的报告 <code>executionContextDestroyed</code> <code>executionContextsCleared</code> 。

</p>

---

### 评判
计算全局对象上的表达式。

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
            <td>表达</td>
            <td><code class="flyout">string</code></td>
            <td>要计算的表达式。</td>
        </tr>
        <tr>
            <td>includeCommandLineAPI <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>确定在评估期间命令行 API 是否应可用。</td>
        </tr>
        <tr>
            <td>objectGroup <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>可用于释放多个对象的符号组名称。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>在计算期间引发的静默模式异常不会报告，并且不会暂停执行。 重写 <code>setPauseOnException</code> 状态。</td>
        </tr>
        <tr>
            <td>contextId <br/> <i>可选</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>指定要在其中执行计算的执行上下文。 如果省略该参数，将在已检查页面的上下文中执行计算。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>结果是否应为应由 value 发送的 JSON 对象。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><code>await</code>在解决已完成的承诺后，是否应执行结果值和返回。</td>
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
            <td>结果</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>评估结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### callFunctionOn
调用具有给定对象的给定声明的函数。 结果的对象组继承自目标对象。

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
            <td>要在其上调用函数的对象的标识符。 应指定 "objectId" 或 "executionContextId"。  objectId 必须来自 Runtime。求值（）函数。</td>
        </tr>
        <tr>
            <td>arguments <br/> <i>可选</i></td>
            <td><a href="#callargument"><code class="flyout">CallArgument[]</code></a></td>
            <td>调用参数。 所有调用参数都必须属于与目标对象相同的 JavaScript world。</td>
        </tr>
        <tr>
            <td>silent <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>在计算期间引发的静默模式异常不会报告，并且不会暂停执行。 重写 <code>setPauseOnException</code> 状态。</td>
        </tr>
        <tr>
            <td>returnByValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>结果是否应为应由 value 发送的 JSON 对象。</td>
        </tr>
        <tr>
            <td>awaitPromise <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><code>await</code>在解决已完成的承诺后，是否应执行结果值和返回。</td>
        </tr>
        <tr>
            <td>executionContextId <br/> <i>可选</i></td>
            <td><a href="#executioncontextid"><code class="flyout">ExecutionContextId</code></a></td>
            <td>指定将用于调用函数的全局对象的执行上下文。 应指定 executionContextId 或 objectId。</td>
        </tr>
        <tr>
            <td>objectGroup <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>可用于释放多个对象的符号组名称。 如果未指定 objectGroup，并且 objectId 为，则 objectGroup 将继承自对象。</td>
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
            <td>结果</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>呼叫结果。</td>
        </tr>
    </tbody>
</table>
</p>

---

### awaitPromise
将处理程序添加到具有给定承诺对象 id 的承诺。

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
            <td>结果是否应为应由 value 发送的 JSON 对象。</td>
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
            <td>结果</td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>承诺结果。  如果承诺被拒绝，将包含 "拒绝" 值。</td>
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
            <td>要为其返回属性的对象的标识符。 objectId 必须来自 evaluateOnCallFrame （）函数。</td>
        </tr>
        <tr>
            <td>ownProperties <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果为 true，则返回仅属于元素本身的属性，而不是其原型链。</td>
        </tr>
        <tr>
            <td>accessorPropertiesOnly <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>实验. </b></span>如果为 true，则仅返回访问器属性（具有 getter/setter）;内部属性也不会返回。</td>
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
            <td>结果</td>
            <td><a href="#propertydescriptor"><code class="flyout">PropertyDescriptor[]</code></a></td>
            <td>对象属性。</td>
        </tr>
    </tbody>
</table>
</p>

---

### globalLexicalScopeNames
从控制台全局范围内返回所有 let、常量和类变量。

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
            <td>别名</td>
            <td><code class="flyout">string[]</code></td>
            <td></td>
        </tr>
    </tbody>
</table>
</p>

---

### releaseObject
释放具有给定 id 的远程对象。

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
放弃所收集的异常和控制台 API 调用。

</p>

---

## 事件

### executionContextCreated
在创建新的执行上下文时发出。

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
            <td>被破坏的上下文的 Id</td>
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
当异常引发且未经处理时发出。

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
            <td>icmp</td>
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
            <td><code class="flyout">string</code> <br/> <i>允许的值：日志、信息、警告、错误、调试、断言、表、跟踪、dir、dirxml、clear、select、count、countReset、timeEnd、timeStamp、startGroup、startGroupCollapsed、endGroup</i></td>
            <td>通话的类型。 这包括日志、信息、警告、错误、调试、断言、表、跟踪、dir、dirxml、clear、select、count、countReset、timeEnd、exception、timeStamp、group、groupCollapsed、groupEnd。</td>
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
            <td>icmp <br/> <i>可选</i></td>
            <td><a href="#timestamp"><code class="flyout">Timestamp</code></a></td>
            <td>通话时间戳。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>可选</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>捕获的堆栈跟踪（如果可用）</td>
        </tr>
    </tbody>
</table>
</p>

---

## 类型

### <a name="scriptid"></a> ScriptId `string`

唯一的脚本标识符。

</p>

---

### <a name="remoteobjectid"></a> RemoteObjectId `string`

唯一的对象标识符。

</p>

---

### <a name="unserializablevalue"></a> UnserializableValue `string`

基元值，不能是 JSON-stringified。

##### 允许值
无穷大、NaN、-无穷大、-0
</p>

---

### <a name="remoteobject"></a> RemoteObject `object`

镜像对象引用原始 JavaScript 对象。

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
            <td><code class="flyout">string</code> <br/> <i>允许的值： object、函数、undefined、string、number、boolean、符号</i></td>
            <td>对象类型。</td>
        </tr>
        <tr>
            <td>子类型 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code> <br/> <i>允许的值： null、错误、承诺、节点</i></td>
            <td>Object 子类型提示。 仅为 <code>object</code> 类型值指定。</td>
        </tr>
        <tr>
            <td>缺少 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>对象类（构造函数）名称。 仅为 <code>object</code> 类型值指定。</td>
        </tr>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><code class="flyout">any</code></td>
            <td>在基元值或 JSON 值（如果已请求）的情况下的远程对象值。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>可选</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>不能为 JSON 的基元值-stringified 没有 <code>value</code>，但获取此属性。</td>
        </tr>
        <tr>
            <td>description <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>对象的字符串表示形式。</td>
        </tr>
        <tr>
            <td>objectId <br/> <i>可选</i></td>
            <td><a href="#remoteobjectid"><code class="flyout">RemoteObjectId</code></a></td>
            <td>唯一对象标识符（对于非基元值）。</td>
        </tr>
        <tr>
            <td>msDebuggerPropertyId <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>实验. </b></span>Microsoft：此对象的关联调试器属性 id。</td>
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
            <td>属性名称或符号描述。</td>
        </tr>
        <tr>
            <td>值 <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>与属性关联的值。</td>
        </tr>
        <tr>
            <td>全 <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果与属性关联的值可能更改（仅限数据描述符），则为 True。</td>
        </tr>
        <tr>
            <td>获取 <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>充当属性的 getter 或没有 <code>undefined</code> getter （仅限访问器描述符）的函数。</td>
        </tr>
        <tr>
            <td>set <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>充当属性的 setter 的函数，或者没有 <code>undefined</code> setter （仅限访问器描述符）的函数。</td>
        </tr>
        <tr>
            <td>旋钮</td>
            <td><code class="flyout">boolean</code></td>
            <td>如果此属性描述符的类型可能已更改，并且该属性可能已从相应对象中删除，则为 True。</td>
        </tr>
        <tr>
            <td>枚举</td>
            <td><code class="flyout">boolean</code></td>
            <td>如果在对相应对象的属性进行枚举时显示此属性，则为 True。</td>
        </tr>
        <tr>
            <td>wasThrown <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果计算期间引发了结果，则为 True。</td>
        </tr>
        <tr>
            <td>isOwn <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td>如果属性为对象所拥有，则为 True。</td>
        </tr>
        <tr>
            <td>msReturnValue <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>实验. </b></span>Microsoft：如果属性为返回值，则为 True。</td>
        </tr>
        <tr>
            <td>符号 <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>属性符号对象（如果属性属于 `symbol` 类型）。 </td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="callargument"></a> CallArgument `object`

表示函数调用参数。 远程对象 id <code>objectId</code> 、基元 <code>value</code> 、unserializable 基元值或两者均不是（对于未定义的）都应指定它们。

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
            <td>基元值或可串行 javascript 对象。</td>
        </tr>
        <tr>
            <td>unserializableValue <br/> <i>可选</i></td>
            <td><a href="#unserializablevalue"><code class="flyout">UnserializableValue</code></a></td>
            <td>不能为 JSON 的 stringified 的基元值。</td>
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

执行上下文的 Id。

</p>

---

### <a name="executioncontextdescription"></a> ExecutionContextDescription `object`

已隔离世界的描述。

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
            <td>执行上下文的唯一 id。 它可用于指定应在哪个执行上下文脚本计算中执行。</td>
        </tr>
        <tr>
            <td>原</td>
            <td><code class="flyout">string</code></td>
            <td>执行上下文原点。</td>
        </tr>
        <tr>
            <td>name</td>
            <td><code class="flyout">string</code></td>
            <td>描述给定上下文的人类可读名称。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="exceptiondetails"></a> ExceptionDetails `object`

有关在脚本编译或执行期间引发的异常（或错误）的详细信息。

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
            <td>异常 id。</td>
        </tr>
        <tr>
            <td>文本</td>
            <td><code class="flyout">string</code></td>
            <td>异常文本，应与异常对象一起使用（如果可用）。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>异常位置（从0开始）的行号。</td>
        </tr>
        <tr>
            <td>columnNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>异常位置（从0开始）的列号。</td>
        </tr>
        <tr>
            <td>scriptId <br/> <i>可选</i></td>
            <td><a href="#scriptid"><code class="flyout">ScriptId</code></a></td>
            <td>异常位置的脚本 ID。</td>
        </tr>
        <tr>
            <td>url <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>要在未报告脚本时使用的异常位置的 URL。</td>
        </tr>
        <tr>
            <td>stackTrace <br/> <i>可选</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>JavaScript 堆栈跟踪（如果可用）。</td>
        </tr>
        <tr>
            <td>除了 <br/> <i>可选</i></td>
            <td><a href="#remoteobject"><code class="flyout">RemoteObject</code></a></td>
            <td>异常对象（如果可用）。</td>
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

自 epoch 以来的毫秒数。

</p>

---

### <a name="callframe"></a> CallFrame `object`

运行时错误和断言的堆栈条目。

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
            <td>JavaScript 脚本 id。如果未启用调试器，ScriptId 将为空。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript 脚本名称或 url。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript 脚本行数（基于0）。</td>
        </tr>
        <tr>
            <td>columnNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>JavaScript 脚本列数（从0开始）。</td>
        </tr>
    </tbody>
</table>
</p>

---

### <a name="stacktrace"></a> StackTrace `object`

调用断言或错误消息的帧。

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
            <td>代 <br/> <i>可选</i></td>
            <td><a href="#stacktrace"><code class="flyout">StackTrace</code></a></td>
            <td>在此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。</td>
        </tr>
    </tbody>
</table>
</p>

---
