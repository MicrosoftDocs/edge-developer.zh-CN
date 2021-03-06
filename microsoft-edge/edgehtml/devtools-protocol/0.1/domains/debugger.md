---
description: DevTools 协议版本 0.1 (EdgeHTML) 调试器域参考。  调试器域公开 JavaScript 调试功能。  它允许设置和删除断点、逐步执行、探索堆栈跟踪等。
title: '调试器域 - DevTools 协议版本 0.1 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/03/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.custom: seodec18
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d63408e23fd8912cf617bfefae2b991387b45a38
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397676"
---
# <a name="debugger-domain---devtools-protocol-version-01-edgehtml"></a>调试器域 - DevTools 协议版本 0.1 (EdgeHTML)   
  
调试器域公开 JavaScript 调试功能。  它允许设置和删除断点、逐步执行、探索堆栈跟踪等。

| 分类 | 成员 |  
|:--- |:--- |  
| [方法](#methods) | [enable](#enable)， [disable](#disable)， [getPossibleBreakpoints，](#getpossiblebreakpoints) [setBreakpointsActive，](#setbreakpointsactive) [setBreakpointByUrl，](#setbreakpointbyurl) [setBreakpoint，](#setbreakpoint) [removeBreakpoint，](#removebreakpoint) [stepOver，](#stepover) [stepInto，](#stepinto) [stepOut，](#stepout) [pause，](#pause) [resume，](#resume) [getScriptSource，](#getscriptsource) [setPauseOnExceptions，](#setpauseonexceptions) [evaluateOnCallFrame，](#evaluateoncallframe) [setVariableValue，](#setvariablevalue) [setBlackboxPatterns，](#setblackboxpatterns) [msSetDebuggerPropertyValue](#mssetdebuggerpropertyvalue) |  
| [事件](#events) | [scriptParsed](#scriptparsed)， [breakpointResolved，](#breakpointresolved) [paused，](#paused) [resumed](#resumed) |  
| [类型](#types) | [BreakpointId](#breakpointid)， [CallFrameId](#callframeid)， [Location](#location)， [BreakLocation](#breaklocation)， [CallFrame](#callframe)， [Scope](#scope) |  
| [依赖关系](#dependencies) | [运行时](./runtime.md) |  

## <a name="methods"></a>方法  

### <a name="enable"></a>“启用”  

为给定页面启用调试程序。  在接收此命令的结果之前，客户端不应假定调试已启用。  

&nbsp;  

---  

### <a name="disable"></a>“禁用”  

禁用给定页面的调试程序。  

&nbsp;  

---  

### <a name="getpossiblebreakpoints"></a>getPossibleBreakpoints  

返回断点的可能位置。  start 和 end range 位置中的 scriptId 应相同。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| start | [位置](#location) | 搜索可能断点位置的范围开始。 |  
| 结束 | [位置](#location) | 要搜索 \ (中可能断点位置的范围结束，但不包括\) 。  如果未指定，脚本的末尾将用作范围的末尾。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| locations | [BreakLocation](#breaklocation) | 可能的断点位置的列表。 |  

---  

### <a name="setbreakpointsactive"></a>setBreakpointsActive  

激活/停用页面上的所有断点。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| active | `boolean` | 断点活动状态的新值。 |  

---  

### <a name="setbreakpointbyurl"></a>setBreakpointByUrl  

设置由 URL 或 URL 正则表达式指定的给定位置的 JavaScript 断点。  发出此命令后，所有现有分析脚本都将在属性中解析和返回断 `locations` 点。  进一步匹配脚本分析将导致 `breakpointResolved` 后续事件发布。  此逻辑断点在重新加载页面时将生存下来。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| lineNumber | `integer` | 要设置断点的行号。 |  
| url \ (optional\)  | `string` | 要设置断点的资源的 URL。 |  
| urlRegex \ (optional\)  | `string` | 要设置断点的资源 URL 的正则表达式模式。  或者 `url` `urlRegex` 必须指定。 |  
| columnNumber \ (optional\)  | `integer` | 要设置断点的行中的偏移量。 |  
| condition \ (optional\)  | `string` | 用作断点条件的表达式。  指定此参数时，如果此表达式计算结果为 true，调试器将仅在断点停止。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| breakpointId | [BreakpointId](#breakpointid) | 创建的断点的 ID，供进一步参考。 |  
| locations | [位置[]](#location) | 添加时此断点解析到的位置的列表。 |  

---  

### <a name="setbreakpoint"></a>setBreakpoint  

设置给定位置的 JavaScript 断点。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| location | [位置](#location) | 要设置断点的位置。 |  
| condition \ (optional\)  | `string` | 用作断点条件的表达式。  指定此参数时，如果此表达式计算结果为 true，调试器将仅在断点停止。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| breakpointId | [BreakpointId](#breakpointid) | 创建的断点的 ID，供进一步参考。 |  
| actualLocation | [位置](#location) | 解析到的断点的位置。 |  

---  

### <a name="removebreakpoint"></a>removeBreakpoint  

删除 JavaScript 断点。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| breakpointId | [BreakpointId](#breakpointid) | &nbsp; |  

---  

### <a name="stepover"></a>stepOver  

对语句的步骤。  

&nbsp;  

---  

### <a name="stepinto"></a>stepInto  

进入函数调用。  

&nbsp;  

---  

### <a name="stepout"></a>stepOut  

退出函数调用。  

&nbsp;  

---  

### <a name="pause"></a>pause  

停止下一个 JavaScript 语句。  

&nbsp;  

---  

### <a name="resume"></a>resume  

恢复 JavaScript 执行。  

&nbsp;  

---  

### <a name="getscriptsource"></a>getScriptSource  

返回具有给定 ID 的脚本的源。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | 要获取其源的脚本的 ID。 |  
| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| scriptSource | `string` | 脚本源。 |  

---  

### <a name="setpauseonexceptions"></a>setPauseOnExceptions  

定义异常状态上的暂停。  可以设置为在所有异常、未捕获的异常或无异常上停止。  异常状态的初始暂停为 `none` 。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| state | `string` | 暂停异常模式。  允许的值  `none` ：、 `uncaught` 和 `all` |  

---  

### <a name="evaluateoncallframe"></a>evaluateOnCallFrame  

计算给定呼叫帧上的表达式。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| callFrameId | [CallFrameId](#callframeid) | 要评估的呼叫帧标识符。 |  
| 表达式 | `string` | 要计算表达式。 |  
| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| result | [Runtime.RemoteObject](./runtime.md#remoteobject) | 评估结果的对象包装。 |  

---  

### <a name="setvariablevalue"></a>setVariableValue  

更改调用框内变量的值。  不支持基于对象的作用域，必须手动进行可变。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| scopeNumber | `integer` | 范围链中列出的基于 0 的范围数。  仅 `local` `closure` 允许 ， `catch` 和范围类型。  可以手动操作其他范围。 |  
| variableName | `string` | 变量名称。 |  
| newValue | [Runtime.CallArgument](./runtime.md#callargument) | 新变量值。 |  
| callFrameId | [CallFrameId](#callframeid) | 包含变量的调用框的 ID。 |  

---  

### <a name="setblackboxpatterns"></a>setBlackboxPatterns  

**实验**性 。  将以前的黑箱模式替换为传递的黑色框模式。  强制后端在 URL 与其中一种模式匹配的脚本中跳过单步执行/暂停。  调试程序将尝试通过执行多次来保留黑盒脚本，如果失败 `step in` ，最后 `step out` 将采用此脚本。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| 模式 | `string[]` | 将用于检查脚本 URL 的 blackbox 状态正则表达式的数组。 |  

---  

### <a name="mssetdebuggerpropertyvalue"></a>msSetDebuggerPropertyValue  

**实验**性 。  Microsoft：将指定的调试器属性设置为指定值。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| debuggerPropertyId | `string` | Microsoft：属性 ID \ (即 msDebuggerPropertyId\) 设置。 |  
| newValue | `string` | &nbsp; |  

---  

## <a name="events"></a>事件  

### <a name="scriptparsed"></a>scriptParsed  

分析脚本时触发。  启用调试程序时，还会针对所有已知和未创建脚本触发此事件。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | 分析的脚本的标识符。 |  
| url | `string` | 解析为 \ (\) 的脚本的 URL 或) 。 |  
| startLine | `integer` | 具有给定 URL 的脚本在资源中的行偏移量\ (脚本标记\) 。 |  
| startColumn | `integer` | 具有给定 URL 的资源中的脚本的列偏移量。 |  
| endLine | `integer` | 脚本的最后一行。 |  
| endColumn | `integer` | 脚本最后一行的长度。 |  
| executionContextId | [Runtime.ExecutionContextId](./runtime.md#executioncontextid) | 指定脚本创建上下文。 |  
| sourceMapURL \ (optional\)  | `string` | 与脚本映射关联的源 (（如果有) ）。 |  
| length \ (optional\)  | `integer` | **实验**性 。  此脚本长度。 |  
| msParentId \ (optional\)  | `string` | **实验**性 。  这是父文档 ID。 |  
| msMimeType \ (optional\)  | `string` | **实验**性 。  这是 mime 类型。 |  
| msIsDynamicCode \ (optional\)  | `boolean` | **实验**性 。  这指示它是否为动态代码。 |  
| msLongDocumentId \ (optional\)  | `integer` | **实验**性 。  这是长文档 ID。 |  

---  

### <a name="breakpointresolved"></a>breakpointResolved  

当断点解析为实际脚本和位置时触发。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| breakpointId | [BreakpointId](#breakpointid) | 断点唯一标识符。 |  
| location | [位置](#location) | 实际断点位置。 |  
| msLength \ (optional\)  | `integer` | **实验**性 。  Microsoft：代码 \ (长度，即断点) 字符数\ |  

---  

### <a name="paused"></a>已暂停  

当调试器中断断点或异常时触发。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| callFrames | [CallFrame[]](#callframe) | 调用调试器停止的堆栈。 |  
| reason | `string` | 暂停原因。  允许的值  `breakpoint` `step` `exception` ：、、和 `other` |  
| data \ (optional\)  | `object` | 包含特定于中断的辅助属性的对象。 |  
| hitBreakpoints \ (optional\)  | `string[]` | 命中断点 ID |  

---  

### <a name="resumed"></a>恢复  

在调试程序恢复执行时触发。  

&nbsp;  

---  

## <a name="types"></a>类型  

### <a name="breakpointid-string"></a>BreakpointId 字符串  

<a name="breakpointid"></a>  

断点标识符。  

&nbsp;  

---  

### <a name="callframeid-string"></a>CallFrameId 字符串  

<a name="callframeid"></a>  

呼叫帧标识符。  

&nbsp;  

---  

### <a name="location-object"></a>Location 对象  

<a name="location"></a>  

源代码中的位置。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | 报告在 中的脚本标识符 `Debugger.scriptParsed` 。 |  
| lineNumber | `integer` | 脚本 \ (0\) 中的行) 。 |  
| columnNumber \ (optional\)  | `integer` | 脚本 \ (0\) 中的列号。 |  
| msLength | `integer` | Microsoft：代码 \ (，即在此调用帧) 字符数\字符数。 |  

---  

### <a name="breaklocation-object"></a>BreakLocation 对象  

<a name="breaklocation"></a>  

中断源代码中的位置。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| scriptId | [Runtime.ScriptId](./runtime.md#scriptid) | 中报告的脚本标识符 `Debugger.scriptParsed` 。 |  
| lineNumber | `integer` | 脚本 \ (0\) 中的行) 。 |  
| columnNumber \ (optional\)  | `integer` | 脚本 \ (0\) 中的列号。 |  
| msLength | `integer` | Microsoft：代码 \ (，即在此调用帧) 字符数\字符数。 |  
| type \ (optional\)  | `string` | 允许的值  `debuggerStatement` ：、 `call` 和 `return` |  

---  

### <a name="callframe-object"></a>CallFrame 对象  

<a name="callframe"></a>  

JavaScript 调用帧。  构成调用堆栈的调用帧数组。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| callFrameId | [CallFrameId](#callframeid) | 呼叫帧标识符。  此标识符仅在调试器暂停时有效。 |  
| functionName | `string` | 在此调用帧上调用的 JavaScript 函数的名称。 |  
| functionLocation \ (optional\)  | [位置](#location) | **实验**性 。  源代码中的位置。 |  
| location | [位置](#location) | 源代码中的位置。 |  
| url | `string` | JavaScript 脚本名称或 url。 |  
| scopeChain | [范围[]](#scope) | 此呼叫帧的范围链。 |  
| this | [Runtime.RemoteObject](./runtime.md#remoteobject) | `this` 对象。 |  
| returnValue \ (optional\)  | [Runtime.RemoteObject](./runtime.md#remoteobject) | 如果函数位于返回点，则返回的值。 |  

---  

### <a name="scope-object"></a>Scope 对象  

<a name="scope"></a>  

范围说明。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| 类型 | `string` | 范围类型。  允许的值  `global` `local` `with` ：、、、、、 `closure` `catch` `block` `script` `eval` 和 `module` |  
| object | [Runtime.RemoteObject](./runtime.md#remoteobject) | 表示范围的对象。  对于和范围，它表示实际对象;对于其余范围，它是人工临时对象枚举范围变量 `global` `with` 作为其属性。 |  
| name \ (optional\)  | `string` | &nbsp; |  
| startLocation \ (optional\)  | [位置](#location) | 范围开始的源代码中的位置。 |  
| endLocation \ (optional\)  | [位置](#location) | 范围结束的源代码中的位置。 |  

---  

## <a name="dependencies"></a>依赖关系  

[运行时](./runtime.md)  
