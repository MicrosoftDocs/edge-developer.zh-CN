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
# <a name="runtime-domain---devtools-protocol-version-01-edgehtml"></a>运行时域 - DevTools 协议版本 0.1 (EdgeHTML)   

运行时域通过远程评估和镜像对象公开 JavaScript 运行时。  评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。  原始对象在内存中进行维护，除非它们已显式释放。  

| 分类 | 成员 |  
|:--- |:--- |  
| [方法](#methods) | [enable](#enable)， [disable](#disable)， [evaluate](#evaluate)， [callFunctionOn](#callfunctionon)， [getProperties](#getproperties) |  
| [事件](#events) | [executionContextsCleared](#executioncontextscleared)， [exceptionThrown](#exceptionthrown) |  
| [类型](#types) | [ScriptId](#scriptid)、 [RemoteObjectId](#remoteobjectid)、 [UnserializableValue](#unserializablevalue)、 [RemoteObject](#remoteobject)、 [PropertyDescriptor](#propertydescriptor)、 [CallArgument](#callargument)、 [ExecutionContextId](#executioncontextid)、 [ExceptionDetails](#exceptiondetails)、 [Timestamp](#timestamp)、 [CallFrame](#callframe)、 [StackTrace](#stacktrace) |  

## <a name="methods"></a>方法  

### <a name="enable"></a>“启用”  

启用事件 `executionContextsCleared` 报告。  

&nbsp;  

---  

### <a name="disable"></a>“禁用”  

禁用事件 `executionContextsCleared` 报告。  

&nbsp;  

---  

### <a name="evaluate"></a>evaluate  

计算全局对象的表达式。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| 表达式 | `string` | 要计算表达式。 |  
| 无提示 \ (可选\)  | `boolean` | 在静默模式下，不会报告在评估期间引发的异常，并且不会暂停执行。  覆盖 `setPauseOnException` 状态。 |  
| contextId \ (optional\)  | [ExecutionContextId](#executioncontextid) | 指定要执行评估的执行上下文。  如果省略该参数，将在所检查页面的上下文中执行计算。 |  
| returnByValue \ (optional\)  | `boolean` | 结果是否应为应按值发送的 JSON 对象。 |  
| awaitPromise \ (optional\)  | `boolean` | 是否应为 `await` 生成的值执行，并解决等待的承诺后返回。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | 评估结果。 |  

---  

### <a name="callfunctionon"></a>callFunctionOn  

调用给定对象上具有给定声明的函数。  结果的对象组继承自目标对象。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| functionDeclaration | `string` | 要调用的函数的声明。 |  
| objectId \ (optional\)  | [RemoteObjectId](#remoteobjectid) | 要调用函数的对象的标识符。  或者 `objectId` `executionContextId` 应指定。  objectId 必须来自 Runtime.evaluate () 函数。 |  
| 参数 \ (可选\)  | [CallArgument[]](#callargument) | 调用参数。  所有调用参数都必须属于与目标对象相同的 JavaScript 世界。 |  
| 无提示 \ (可选\)  | `boolean` | 在静默模式下，不会报告在评估期间引发的异常，并且不会暂停执行。  覆盖 `setPauseOnException` 状态。 |  
| returnByValue \ (optional\)  | `boolean` | 结果是否应为应按值发送的 JSON 对象。 |  
| awaitPromise \ (optional\)  | `boolean` | 是否应为 `await` 生成的值执行，并解决等待的承诺后返回。 |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| result | [RemoteObject](#remoteobject) | 呼叫结果。 |  

---  

### <a name="getproperties"></a>getProperties  

返回给定对象的属性。  结果的对象组继承自目标对象。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| objectId | [RemoteObjectId](#remoteobjectid) | 要返回其属性的对象的标识符。  `objectId` 必须来自 `Debugger.evaluateOnCallFrame()` 函数。 |  
| ownProperties \ (optional\)  | `boolean` | If `true` ，则返回仅属于元素本身的属性，而不是其原型链的属性。 |  
| accessorPropertiesOnly \ (optional\)  | `boolean` | **实验**性 。  If `true` ， returns accessor properties \ (with getter/setter\) only; internal properties are not returned either. |  

| 返回 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| result | [PropertyDescriptor[]](#propertydescriptor) | 对象属性。 |  

---  

## <a name="events"></a>事件  

### <a name="executioncontextscleared"></a>executionContextsCleared  

在浏览器中清除所有 executionContexts 时发出。  

&nbsp;  

---  

### <a name="exceptionthrown"></a>exceptionThrown  

引发和未处理异常时发出。  

| 参数 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| timestamp | [时间戳](#timestamp) | 异常的时间戳。 |  
| exceptionDetails | [ExceptionDetails](#exceptiondetails) | &nbsp; |  

---  

## <a name="types"></a>类型  

### <a name="scriptid-string"></a>ScriptId 字符串  

<a name="scriptid"></a>  

唯一脚本标识符。  

&nbsp;  

---  

### <a name="remoteobjectid-string"></a>RemoteObjectId 字符串  

<a name="remoteobjectid"></a>  

唯一对象标识符。  

&nbsp;  

---  

### <a name="unserializablevalue-string"></a>UnserializableValue 字符串  

<a name="unserializablevalue"></a>  

不能为 JSON 字符串化的基元值。  

##### <a name="allowed-values"></a>允许的值  

`Infinity`, `NaN`, `-Infinity`, `-0`  

---  

### <a name="remoteobject-object"></a>RemoteObject 对象  

<a name="remoteobject"></a>  

引用原始 JavaScript 对象的镜像对象。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| 类型 | `string` | 对象类型。  允许的值  `object` `function` `undefined` ：、、、、、 `string` `number` `boolean` 和 `symbol` |  
| subtype \ (optional\)  | `string` | 对象子类型提示。  仅为 `object` 类型值指定。  允许的值  `null` ：、 `error` 和 `promise` |  
| className \ (optional\)  | `string` | 对象类 \ (构造函数\) 名称。  仅为 `object` 类型值指定。 |  
| value \ (optional\)  | `any` | 基元值或 JSON 值 \ (请求的远程对象值\) 。 |  
| unserializableValue \ (optional\)  | [UnserializableValue](#unserializablevalue) | 不能为 JSON 字符串化的基元值没有， `value` 但获取此属性。 |  
| description \ (optional\)  | `string` | 对象的字符串表示形式。 |  
| objectId \ (optional\)  | [RemoteObjectId](#remoteobjectid) | 非基元值的唯一对象标识符 \ (\) 。 |  
| msDebuggerPropertyId \ (optional\)  | `string` | **实验**性 。  Microsoft：此对象的关联调试器属性 ID。 |  

---  

### <a name="propertydescriptor-object"></a>PropertyDescriptor 对象  

<a name="propertydescriptor"></a>  

对象属性描述符。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| name | `string` | 属性名称或符号说明。 |  
| value \ (optional\)  | [RemoteObject](#remoteobject) | 与属性关联的值。 |  
| 可写 \ (可选\)  | `boolean` | `True` 如果与该属性关联的值可能更改 \ (数据描述符\) 。 |  
| 获取 \ (optional\)  | [RemoteObject](#remoteobject) | 充当属性 getter 的函数，或者如果没有 `undefined` getter \ (访问器描述符\) 。 |  
| set \ (optional\)  | [RemoteObject](#remoteobject) | 用作属性的设置器的函数，或者如果没有设置器 `undefined` \ (访问器描述符\) 。 |  
| 可配置 | `boolean` | `True` 如果此属性描述符的类型可能更改，并且该属性可能从相应的对象中删除。 |  
| enumerable | `boolean` | `True` 如果此属性在枚举相应对象的属性期间显示。 |  
| wasThrown \ (optional\)  | `boolean` | `True` 如果在评估期间引发结果。 |  
| isOwn \ (optional\)  | `boolean` | `True` 属性是否归对象所有。 |  
| msReturnValue \ (optional\)  | `boolean` | **实验**性 。  Microsoft：  `True` 如果该属性是返回值。 |  
| symbol \ (optional\)  | [RemoteObject](#remoteobject) | 属性符号对象，如果属性的类型 `symbol` 。 |  

---  

### <a name="callargument-object"></a>CallArgument 对象  

<a name="callargument"></a>  

代表函数调用参数。  应指定远程对象 ID、不可序列化基元值 (\) \) 。 `value`  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| value \ (optional\)  | `any` | 基元值或可序列化的 javascript 对象。 |  
| unserializableValue \ (optional\)  | [UnserializableValue](#unserializablevalue) | 不能为 JSON 字符串化的基元值。 |  
| objectId \ (optional\)  | [RemoteObjectId](#remoteobjectid) | 远程对象句柄。 |  

---  

### <a name="executioncontextid-integer"></a>ExecutionContextId 整数  

<a name="executioncontextid"></a>  

执行上下文的 ID。  

&nbsp;  

---  

### <a name="exceptiondetails-object"></a>ExceptionDetails 对象  

<a name="exceptiondetails"></a>  

有关在脚本编译或 (过程中) 异常或错误\错误的详细信息。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| exceptionId | `integer` | 异常 ID。 |  
| 文本 | `string` | 异常文本，应在可用时与异常对象一同使用。 |  
| lineNumber | `integer` | 例外位置 \ (0\) 。 |  
| columnNumber | `integer` | 例外位置 \ (0\) 的列号。 |  
| scriptId \ (optional\)  | [ScriptId](#scriptid) | 异常位置的脚本 ID。 |  
| url \ (optional\)  | `string` | 未报告脚本时使用的异常位置的 URL。 |  
| stackTrace \ (optional\)  | [StackTrace](#stacktrace) | JavaScript 堆栈跟踪（如果可用）。 |  
| exception \ (optional\)  | [RemoteObject](#remoteobject) | Exception 对象（如果可用）。 |  
| executionContextId \ (optional\)  | [ExecutionContextId](#executioncontextid) | 发生异常的上下文的标识符。 |  

---  

### <a name="timestamp-integer"></a>时间戳整数  

<a name="timestamp"></a>  

自纪元以来的毫秒数。  

&nbsp;  

---  

### <a name="callframe-object"></a>CallFrame 对象  

<a name="callframe"></a>  

运行时错误和断言的堆栈项。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| functionName | `string` | JavaScript 函数名称。 |  
| scriptId | [ScriptId](#scriptid) | JavaScript 脚本 ID。 |  
| url | `string` | JavaScript 脚本名称或 url。 |  
| lineNumber | `integer` | JavaScript 脚本行号 \ (0-based\) 。 |  
| columnNumber | `integer` | JavaScript 脚本列号 \ (0-based\) 。 |  

---  

### <a name="stacktrace-object"></a>StackTrace 对象  

<a name="stacktrace"></a>  

断言或错误消息的呼叫帧。  

| 属性 | 类型 | 详细信息 |  
|:--- |:--- |:--- |  
| description \ (optional\)  | `string` | 此堆栈跟踪的字符串标签。  对于异步跟踪，这可能是启动异步调用的函数的名称。 |  
| callFrames | [CallFrame[]](#callframe) | JavaScript 函数名称。 |  
| 父 \ (可选\)  | [StackTrace](#stacktrace) | 此堆栈之前的异步 JavaScript 堆栈跟踪（如果可用）。 |  

---  
