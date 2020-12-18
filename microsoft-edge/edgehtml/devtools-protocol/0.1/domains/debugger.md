---
description: DevTools 协议版本 0.1 (调试) EdgeHTML 协议参考。 调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐步执行、探索堆栈跟踪等。
title: '调试器域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.date: 12/16/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5160e6e69ec76f8c584f1bdb969464d805c7afa7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232474"
---
# 调试器域 - DevTools 协议版本 0.1 (EdgeHTML)   
  
调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐步执行、探索堆栈跟踪等。

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)， [disable](#disable)， [getPossibleBreakpoints，](#getpossiblebreakpoints) [setBreakpointsActive，](#setbreakpointsactive) [setBreakpointByUrl，](#setbreakpointbyurl) [setBreakpoint，](#setbreakpoint) [removeBreakpoint，](#removebreakpoint) [stepOver，](#stepover) [stepInto，](#stepinto) [stepOut，](#stepout) [pause，](#pause) [resume，](#resume) [getScriptSource，](#getscriptsource) [setPauseOnExceptions，](#setpauseonexceptions) [evaluateOnCallFrame，](#evaluateoncallframe) [setVariableValue](#setvariablevalue)， [setBlackboxPatterns，](#setblackboxpatterns) [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue) |
| [**事件**](#events) | [scriptParsed](#scriptparsed)， [breakpointResolved，](#breakpointresolved) [paused，](#paused) [resumed](#resumed) |
| [**类型**](#types) | [BreakpointId](#breakpointid)， [CallFrameId](#callframeid)， [Location](#location)， [BreakLocation](#breaklocation)， [CallFrame](#callframe)， [Scope](#scope) |
| [**依赖关系**](#dependencies) | [运行时](runtime.md) |
## 方法

### “启用”
为给定页面启用调试程序。 在接收到此命令的结果之前，客户端不应假定已启用调试。


---

### “禁用”
禁用给定页面的调试程序。


---

### getPossibleBreakpoints
返回断点可能的位置。 start 和 end range 位置中的 scriptId 应相同。

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
            <td>start</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>要搜索可能的断点位置的范围开始。</td>
        </tr>
        <tr>
            <td>结束</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>要搜索可能断点位置的范围结束， (排除) 。 如果未指定，脚本的末尾将用作范围的末尾。</td>
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
            <td>locations</td>
            <td><a href="#breaklocation"><code class="flyout">BreakLocation</code></a></td>
            <td>可能的断点位置的列表。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpointsActive
激活/停用页面上的所有断点。

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
            <td>active</td>
            <td><code class="flyout">boolean</code></td>
            <td>断点活动状态的新值。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpointByUrl
设置由 URL 或 URL 正则表达式指定的给定位置的 JavaScript 断点。 发出此命令后，所有现有已分析脚本都将解析断点，并返回属性 <code>locations</code> 。 进一步匹配脚本分析将生成 <code>breakpointResolved</code> 后续事件。 此逻辑断点在重新加载页面时将生存下来。

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
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>要设置断点的行号。</td>
        </tr>
        <tr>
            <td>url <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>要设置断点的资源的 URL。</td>
        </tr>
        <tr>
            <td>urlRegex <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>要设置断点的资源 URL 的正则表达式模式。 指定 <code>url</code> 或 <code>urlRegex</code> 必须指定。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>要设置断点的行中的偏移量。</td>
        </tr>
        <tr>
            <td>condition <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>用作断点条件的表达式。 指定此表达式时，如果此表达式计算结果为 true，调试器将仅在断点停止。</td>
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
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>创建的断点的 ID，供进一步参考。</td>
        </tr>
        <tr>
            <td>locations</td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td>添加时此断点解析到的位置列表。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpoint
设置给定位置的 JavaScript 断点。

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
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>要设置断点的位置。</td>
        </tr>
        <tr>
            <td>condition <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>用作断点条件的表达式。 指定此表达式时，如果此表达式计算结果为 true，调试器将仅在断点停止。</td>
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
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>创建的断点的 ID，供进一步参考。</td>
        </tr>
        <tr>
            <td>actualLocation</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>此断点解析到的位置。</td>
        </tr>
    </tbody>
</table>

---

### removeBreakpoint
删除 JavaScript 断点。

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
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

### stepOver
对语句的步骤。


---

### stepInto
进入函数调用。


---

### stepOut
退出函数调用。


---

### pause
停止下一个 JavaScript 语句。


---

### resume
恢复 JavaScript 执行。


---

### getScriptSource
返回具有给定 ID 的脚本的源。

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
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>要获取其源的脚本的 ID。</td>
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
            <td>scriptSource</td>
            <td><code class="flyout">string</code></td>
            <td>脚本源。</td>
        </tr>
    </tbody>
</table>

---

### setPauseOnExceptions
定义异常状态上的暂停。 可以设置为在所有异常、未捕获的异常或无异常上停止。 异常状态的初始暂停为 <code>none</code> 。

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
            <td>state</td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：无、未捕获、全部</i></td>
            <td>暂停异常模式。</td>
        </tr>
    </tbody>
</table>

---

### evaluateOnCallFrame
计算给定呼叫帧上的表达式。

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
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>要评估的呼叫帧标识符。</td>
        </tr>
        <tr>
            <td>表达式</td>
            <td><code class="flyout">string</code></td>
            <td>要计算表达式。</td>
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
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>评估结果的对象包装。</td>
        </tr>
    </tbody>
</table>

---

### setVariableValue
更改调用框中的变量值。 不支持基于对象的作用域，必须手动进行可变。

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
            <td>scopeNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>范围链中列出的基于 0 的范围数。 仅允许使用"local"、"closure"和"catch"范围类型。 可以手动操作其他范围。</td>
        </tr>
        <tr>
            <td>variableName</td>
            <td><code class="flyout">string</code></td>
            <td>变量名称。</td>
        </tr>
        <tr>
            <td>newValue</td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td>新变量值。</td>
        </tr>
        <tr>
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>保留变量的 callframe 的 ID。</td>
        </tr>
    </tbody>
</table>

---

### setBlackboxPatterns
<span><b>实验。 </b></span>将以前的黑盒模式替换为传递的黑色框模式。 使用与其中一种模式匹配的 URL 强制后端跳过脚本中的单步执行/暂停。 调试器将尝试通过多次执行"分步"来退出黑盒脚本，如果失败，最后会采取"退出"措施。

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
            <td>模式</td>
            <td><code class="flyout">string[]</code></td>
            <td>将用于检查脚本 URL 的黑盒状态正则表达式的数组。</td>
        </tr>
    </tbody>
</table>

---

### msSetDebuggerPropertyValue
<span><b>实验。 </b></span>Microsoft：将指定的调试器属性设置为指定值。

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
            <td>debuggerPropertyId</td>
            <td><code class="flyout">string</code></td>
            <td>Microsoft：属性 id (即 msDebuggerPropertyId) 设置。</td>
        </tr>
        <tr>
            <td>newValue</td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
    </tbody>
</table>

---

## 事件

### scriptParsed
分析脚本时触发。 启用调试器时，还会针对所有已知和未添加的脚本触发此事件。

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
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>已分析的脚本的标识符。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>已分析脚本的 URL 或 (（如果有) ）。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">integer</code></td>
            <td>具有给定 URL 的资源中的脚本的行偏移量 (用于脚本标记) 。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>具有给定 URL 的资源中的脚本的列偏移量。</td>
        </tr>
        <tr>
            <td>endLine</td>
            <td><code class="flyout">integer</code></td>
            <td>脚本的最后一行。</td>
        </tr>
        <tr>
            <td>endColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>脚本最后一行的长度。</td>
        </tr>
        <tr>
            <td>executionContextId</td>
            <td><a href="runtime.md#executioncontextid"><code class="flyout">Runtime.ExecutionContextId</code></a></td>
            <td>指定脚本创建上下文。</td>
        </tr>
        <tr>
            <td>sourceMapURL <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>与脚本映射关联的源 (（如果有) ）。</td>
        </tr>
        <tr>
            <td>length <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>实验。 </b></span>此脚本长度。</td>
        </tr>
        <tr>
            <td>msParentId <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>实验。 </b></span>这是父文档 ID。</td>
        </tr>
        <tr>
            <td>msMimeType <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>实验。 </b></span>这是 mime 类型。</td>
        </tr>
        <tr>
            <td>msIsDynamicCode <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>实验。 </b></span>这指示它是否为动态代码。</td>
        </tr>
        <tr>
            <td>msLongDocumentId <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>实验。 </b></span>这是长文档 ID。</td>
        </tr>
    </tbody>
</table>

---

### breakpointResolved
当断点解析为实际脚本和位置时触发。

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
            <td>breakpointId</td>
            <td><a href="#breakpointid"><code class="flyout">BreakpointId</code></a></td>
            <td>断点唯一标识符。</td>
        </tr>
        <tr>
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>实际断点位置。</td>
        </tr>
        <tr>
            <td>msLength <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>实验。 </b></span>Microsoft：代码长度 (即断点) 的字符数。</td>
        </tr>
    </tbody>
</table>

---

### 已暂停
当调试器中断断点或异常时触发。

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
            <td>callFrames</td>
            <td><a href="#callframe"><code class="flyout">CallFrame[]</code></a></td>
            <td>调用调试器停止的堆栈。</td>
        </tr>
        <tr>
            <td>reason</td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：断点、步骤、异常、其他</i></td>
            <td>暂停原因。</td>
        </tr>
        <tr>
            <td>数据 <br/> <i>可选</i></td>
            <td><code class="flyout">object</code></td>
            <td>包含特定于中断的辅助属性的对象。</td>
        </tr>
        <tr>
            <td>hitBreakpoints <br/> <i>可选</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>命中断点 ID</td>
        </tr>
    </tbody>
</table>

---

### 恢复
在调试程序恢复执行时触发。


---

## 类型

### <a name="breakpointid"></a> BreakpointId `string`

断点标识符。


---

### <a name="callframeid"></a> CallFrameId `string`

呼叫帧标识符。


---

### <a name="location"></a> 位置 `object`

源代码中的位置。

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
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>报告在中的脚本标识符 <code>Debugger.scriptParsed</code> 。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的行号 (从 0 开始) 。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的列号 (从 0 开始) 。</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft：代码长度 (即此调用) 的字符数。</td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> BreakLocation `object`

中断源代码中的位置。

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
            <td>scriptId</td>
            <td><a href="runtime.md#scriptid"><code class="flyout">Runtime.ScriptId</code></a></td>
            <td>报告在中的脚本标识符 <code>Debugger.scriptParsed</code> 。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的行号 (从 0 开始) 。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的列号 (从 0 开始) 。</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft：代码长度 (即此调用) 的字符数。</td>
        </tr>
        <tr>
            <td>类型 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>允许的值：debuggerStatement、call、return。</td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> CallFrame `object`

JavaScript 调用框架。 调用堆栈中的呼叫帧数组。

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
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>呼叫帧标识符。 此标识符仅在调试器暂停时有效。</td>
        </tr>
        <tr>
            <td>functionName</td>
            <td><code class="flyout">string</code></td>
            <td>在此调用帧上调用的 JavaScript 函数的名称。</td>
        </tr>
        <tr>
            <td>functionLocation <br/> <i>可选</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b>实验。 </b></span>源代码中的位置。</td>
        </tr>
        <tr>
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>源代码中的位置。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript 脚本名称或 URL。</td>
        </tr>
        <tr>
            <td>scopeChain</td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td>此呼叫帧的范围链。</td>
        </tr>
        <tr>
            <td>this</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> 对象。</td>
        </tr>
        <tr>
            <td>returnValue <br/> <i>可选</i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>如果函数在返回点，则返回的值。</td>
        </tr>
    </tbody>
</table>

---

### <a name="scope"></a> 范围 `object`

范围说明。

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
            <td><code class="flyout">string</code> <br/> <i>允许的值：global、local、with、closure、catch、block、script、eval、module</i></td>
            <td>范围类型。</td>
        </tr>
        <tr>
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>表示范围的对象。 对于和范围，它表示实际对象;对于其余范围，它是人工瞬态对象，用于枚举范围变量 <code>global</code> <code>with</code> 作为其属性。</td>
        </tr>
        <tr>
            <td>name <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td>startLocation <br/> <i>可选</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>范围开始的源代码中的位置</td>
        </tr>
        <tr>
            <td>endLocation <br/> <i>可选</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>范围结束的源代码中的位置</td>
        </tr>
    </tbody>
</table>

---

## 依赖关系

[运行时](runtime.md)
