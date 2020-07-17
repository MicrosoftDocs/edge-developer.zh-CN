---
description: 对调试器域的引用。 调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。
title: 调试器域-DevTools 协议版本0.1 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ms.openlocfilehash: 1e76d17e5dfbe39ba61c7cb45a4e88b9fd223068
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882952"
---
# 调试器域-DevTools 协议版本0.1 （EdgeHTML）  
  
调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。

| | |
|-|-|
| [**方法**](#methods) | [enable](#enable)、 [disable](#disable)、 [getPossibleBreakpoints](#getpossiblebreakpoints)、 [setBreakpointsActive](#setbreakpointsactive)、 [setBreakpointByUrl](#setbreakpointbyurl)、 [setBreakpoint](#setbreakpoint)、 [removeBreakpoint](#removebreakpoint)、[跨距](#stepover)、 [stepInto](#stepinto)、 [stepOut](#stepout)、[暂停](#pause)、[恢复](#resume)、 [getScriptSource、setPauseOnExceptions](#getscriptsource)、 [evaluateOnCallFrame](#evaluateoncallframe)、 [setVariableValue](#setvariablevalue)、 [setBlackboxPatterns](#setblackboxpatterns)、msSetDebuggerPropertyValue、、、 [、、](#mssetdebuggerpropertyvalue) 、 [setPauseOnExceptions](#setpauseonexceptions) |
| [**事件**](#events) | [scriptParsed](#scriptparsed)、 [breakpointResolved](#breakpointresolved)、已[暂停](#paused)、已[恢复](#resumed) |
| [**类型**](#types) | [BreakpointId](#breakpointid)、 [CallFrameId](#callframeid)、 [Location](#location)、 [BreakLocation](#breaklocation)、 [CallFrame](#callframe)、 [Scope](#scope) |
| [**依赖关系**](#dependencies) | [运行时](runtime.md) |
## 方法

### “启用”
为给定页面启用调试器。 客户端不应假设已启用调试，直到接收到此命令的结果。


---

### “禁用”
为给定页禁用调试器。


---

### getPossibleBreakpoints
返回断点的可能位置。 开始和结束区域位置中的 scriptId 应相同。

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
            <td>在中搜索可能的断点位置的起始范围。</td>
        </tr>
        <tr>
            <td>结束</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>在（不包括）中搜索可能的断点位置的结尾。 当未指定时，脚本的结尾将用作区域的结尾。</td>
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
            <td>各个</td>
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
在通过 URL 或 URL regex 指定的给定位置设置 JavaScript 断点。 发出此命令后，所有现有的已分析脚本都将在属性中解析和返回断点 <code>locations</code> 。 进一步匹配的脚本分析将导致后续 <code>breakpointResolved</code> 事件被发布。 此逻辑断点将在页面重新加载后继续。

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
            <td>用于设置断点的行号。</td>
        </tr>
        <tr>
            <td>url <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>要在其上设置断点的资源的 URL。</td>
        </tr>
        <tr>
            <td>urlRegex <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>要在其上设置断点的资源的 Url 的正则表达式模式。 <code>url</code>或者 <code>urlRegex</code> 必须指定。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>行中的偏移量，用于设置断点。</td>
        </tr>
        <tr>
            <td>符合 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>用作断点条件的表达式。 如果指定，只有当此表达式的计算结果为 true 时，调试器才会在断点处停止。</td>
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
            <td>用于进一步引用的已创建断点的 Id。</td>
        </tr>
        <tr>
            <td>各个</td>
            <td><a href="#location"><code class="flyout">Location[]</code></a></td>
            <td>添加此断点时，此断点的解决位置的列表。</td>
        </tr>
    </tbody>
</table>

---

### setBreakpoint
在给定位置设置 JavaScript 断点。

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
            <td>在其中设置断点的位置。</td>
        </tr>
        <tr>
            <td>符合 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>用作断点条件的表达式。 如果指定，只有当此表达式的计算结果为 true 时，调试器才会在断点处停止。</td>
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
            <td>用于进一步引用的已创建断点的 Id。</td>
        </tr>
        <tr>
            <td>actualLocation</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>解决此断点的位置。</td>
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

### 配合
对语句执行步骤。


---

### stepInto
执行函数调用中的步骤。


---

### stepOut
执行函数调用之外的步骤。


---

### pause
在下一个 JavaScript 语句停止。


---

### resume
继续执行 JavaScript。


---

### getScriptSource
返回具有给定 id 的脚本的源。

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
            <td>要获取其源的脚本的 Id。</td>
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
定义 "在异常状态时暂停" 状态。 可以设置为在所有异常、未捕获的异常或无异常的情况下停止。 异常状态的初始暂停为 <code>none</code> 。

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
            <td>状态</td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：无、未捕获、全部</i></td>
            <td>"在例外模式暂停"。</td>
        </tr>
    </tbody>
</table>

---

### evaluateOnCallFrame
计算给定调用帧上的表达式。

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
            <td>要计算的调用帧标识符。</td>
        </tr>
        <tr>
            <td>表达</td>
            <td><code class="flyout">string</code></td>
            <td>要计算的表达式。</td>
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
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>计算结果的对象包装器。</td>
        </tr>
    </tbody>
</table>

---

### setVariableValue
更改 callframe 中的变量值。 基于对象的作用域不受支持，必须手动进行。

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
            <td>作用域链中列出了从0开始的范围数。 仅允许 "local"、"闭" 和 "catch" 作用域类型。 其他作用域可以手动操作。</td>
        </tr>
        <tr>
            <td>variableName</td>
            <td><code class="flyout">string</code></td>
            <td>变量名称。</td>
        </tr>
        <tr>
            <td>newValue</td>
            <td><a href="runtime.md#callargument"><code class="flyout">Runtime.CallArgument</code></a></td>
            <td>新的变量值。</td>
        </tr>
        <tr>
            <td>callFrameId</td>
            <td><a href="#callframeid"><code class="flyout">CallFrameId</code></a></td>
            <td>保存变量的 callframe 的 Id。</td>
        </tr>
    </tbody>
</table>

---

### setBlackboxPatterns
<span><b>实验. </b></span>将以前的 blackbox 模式替换为已传递的模式。 强制后端通过与其中一个模式匹配的 url 跳过在脚本中的步进/暂停。 调试程序将尝试通过多次执行 "step in" 来退出 blackboxed 脚本，最后，如果不成功，则使用 "跳出"。

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
            <td>将用于检查 blackbox 状态的脚本 url 的 regexps 数组。</td>
        </tr>
    </tbody>
</table>

---

### msSetDebuggerPropertyValue
<span><b>实验. </b></span>Microsoft：将指定的调试器属性设置为指定值。

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
            <td>Microsoft：要设置的属性 id （如 msDebuggerPropertyId）。</td>
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
在分析脚本时激发。 启用调试程序时，还会针对所有已知和 uncollected 脚本触发此事件。

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
            <td>已分析的脚本的 URL 或名称（如果有）。</td>
        </tr>
        <tr>
            <td>startLine</td>
            <td><code class="flyout">integer</code></td>
            <td>具有给定 URL （对于脚本标记）的资源中的脚本的行偏移量。</td>
        </tr>
        <tr>
            <td>startColumn</td>
            <td><code class="flyout">integer</code></td>
            <td>具有给定 URL 的资源内的脚本的列偏移量。</td>
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
            <td>与脚本关联的源映射的 URL （如果有）。</td>
        </tr>
        <tr>
            <td>时长 <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>实验. </b></span>此脚本长度。</td>
        </tr>
        <tr>
            <td>msParentId <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>实验. </b></span>这是父文档 ID。</td>
        </tr>
        <tr>
            <td>msMimeType <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td><span><b>实验. </b></span>这是 mime 类型。</td>
        </tr>
        <tr>
            <td>msIsDynamicCode <br/> <i>可选</i></td>
            <td><code class="flyout">boolean</code></td>
            <td><span><b>实验. </b></span>这指示它是否是动态代码。</td>
        </tr>
        <tr>
            <td>msLongDocumentId <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td><span><b>实验. </b></span>这是长文档 ID。</td>
        </tr>
    </tbody>
</table>

---

### breakpointResolved
将断点解析为实际脚本和位置时激发。

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
            <td><span><b>实验. </b></span>Microsoft：断点位置处的代码长度（即字符数）。</td>
        </tr>
    </tbody>
</table>

---

### 已暂停
当调试程序中断断点或异常时引发。

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
            <td>调试器在其上停止的调用堆栈。</td>
        </tr>
        <tr>
            <td>reason</td>
            <td><code class="flyout">string</code> <br/> <i>允许的值：断点、步骤、异常、其他</i></td>
            <td>暂停原因。</td>
        </tr>
        <tr>
            <td>数据 <br/> <i>可选</i></td>
            <td><code class="flyout">object</code></td>
            <td>包含特定于断点的辅助属性的对象。</td>
        </tr>
        <tr>
            <td>hitBreakpoints <br/> <i>可选</i></td>
            <td><code class="flyout">string[]</code></td>
            <td>命中断点 Id</td>
        </tr>
    </tbody>
</table>

---

### 稍后
调试器恢复执行时激发。


---

## 类型

### <a name="breakpointid"></a> BreakpointId `string`

断点标识符。


---

### <a name="callframeid"></a> CallFrameId `string`

通话帧标识符。


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
            <td>中报告的脚本标识符 <code>Debugger.scriptParsed</code> 。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的行号（从0开始）。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的列号（基于0）。</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft：此调用帧上的代码长度（例如字符数）。</td>
        </tr>
    </tbody>
</table>

---

### <a name="breaklocation"></a> BreakLocation `object`

在源代码中中断位置。

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
            <td>中报告的脚本标识符 <code>Debugger.scriptParsed</code> 。</td>
        </tr>
        <tr>
            <td>lineNumber</td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的行号（从0开始）。</td>
        </tr>
        <tr>
            <td>columnNumber <br/> <i>可选</i></td>
            <td><code class="flyout">integer</code></td>
            <td>脚本中的列号（基于0）。</td>
        </tr>
        <tr>
            <td>msLength</td>
            <td><code class="flyout">integer</code></td>
            <td>Microsoft：此调用帧上的代码长度（例如字符数）。</td>
        </tr>
        <tr>
            <td>类型 <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td>允许的值： debuggerStatement、call、return。</td>
        </tr>
    </tbody>
</table>

---

### <a name="callframe"></a> CallFrame `object`

JavaScript 调用帧。 调用帧的数组构成了调用堆栈。

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
            <td>通话帧标识符。 此标识符仅在调试器暂停时才有效。</td>
        </tr>
        <tr>
            <td>functionName</td>
            <td><code class="flyout">string</code></td>
            <td>在此调用帧上调用的 JavaScript 函数的名称。</td>
        </tr>
        <tr>
            <td>functionLocation <br/> <i>可选</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td><span><b>实验. </b></span>源代码中的位置。</td>
        </tr>
        <tr>
            <td>location</td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>源代码中的位置。</td>
        </tr>
        <tr>
            <td>url</td>
            <td><code class="flyout">string</code></td>
            <td>JavaScript 脚本名称或 url。</td>
        </tr>
        <tr>
            <td>scopeChain</td>
            <td><a href="#scope"><code class="flyout">Scope[]</code></a></td>
            <td>此通话帧的作用域链。</td>
        </tr>
        <tr>
            <td>此</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td><code>this</code> 此调用帧的对象。</td>
        </tr>
        <tr>
            <td>returnValue <br/> <i>可选</i></td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>如果函数位于返回点，则返回值。</td>
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
            <td><code class="flyout">string</code> <br/> <i>允许的值：全局、本地、使用、关闭、捕获、阻止、脚本、评估、模块</i></td>
            <td>范围类型。</td>
        </tr>
        <tr>
            <td>object</td>
            <td><a href="runtime.md#remoteobject"><code class="flyout">Runtime.RemoteObject</code></a></td>
            <td>表示范围的对象。 对于 <code>global</code> 和 <code>with</code> 作用域它表示实际对象; 对于作用域的其余部分，它是将 scope 变量枚举为其属性的人工瞬时对象。</td>
        </tr>
        <tr>
            <td>name <br/> <i>可选</i></td>
            <td><code class="flyout">string</code></td>
            <td></td>
        </tr>
        <tr>
            <td>startLocation <br/> <i>可选</i></td>
            <td><a href="#location"><code class="flyout">Location</code></a></td>
            <td>作用域在源代码中的起始位置</td>
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