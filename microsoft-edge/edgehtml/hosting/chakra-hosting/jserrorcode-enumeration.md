---
description: 从 Chakra 托管 API 返回的错误代码。
title: JsErrorCode 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b0a4aa7b47070bd5c8c7fe48cdbecf0dbefa9aa5
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232336"
---
# JsErrorCode 枚举

从 Chakra 托管 API 返回的错误代码。  
  
## 语法  
  
```cpp  
enum JsErrorCode : unsigned int;  
```  
  
## 成员  
  
### 值  
  
|名称|描述|  
|----------|-----------------|  
|`JsErrorAlreadyDebuggingContext`|无法将上下文置于调试状态，因为它已进入调试状态。|  
|`JsErrorAlreadyProfilingContext`|上下文无法启动分析，因为它已经在分析。|  
|`JsErrorArgumentNotObject`|使用非对象值调用了对对象值进行操作的宿主 API。|  
|`JsErrorBadSerializedScript`|使用了错误的序列化脚本，或者序列化脚本被不同版本的 Chakra 引擎序列化。|  
|`JsErrorCannotDisableExecution`|运行时不支持可靠的脚本中断。|  
|`JsErrorCannotSerializeDebugScript`|脚本无法在调试上下文中进行序列化。|  
|`JsErrorCategoryEngine`|与引擎本身发生的错误相关的错误类别。|  
|`JsErrorCategoryFatal`|表示引擎故障的致命错误类别。|  
|`JsErrorCategoryScript`|与脚本中的错误相关的错误类别。|  
|`JsErrorCategoryUsage`|与 API 本身的错误使用相关的错误类别。|  
|`JsErrorFatal`|引擎中发生了致命错误。|  
|`JsErrorHeapEnumInProgress`|堆枚举当前正在脚本上下文中进行。|  
|`JsErrorIdleNotEnabled`|主机未启用空闲处理时给定的空闲通知。|  
|`JsErrorInDisabledState`|运行时处于禁用状态。|  
|`JsErrorInExceptionState`|引擎在异常状态中，在清除异常之前无法调用任何 API。|  
|`JsErrorInObjectBeforeCollectCallback`|在收集回调之前，对象不支持该操作。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsErrorInProfileCallback`|脚本上下文位于配置文件回调的中间。|  
|`JsErrorInThreadServiceCallback`|线程服务回调当前正在进行中。|  
|`JsErrorInvalidArgument`|宿主 API 的参数无效。|  
|`JsErrorNoCurrentContext`|托管 API 要求上下文是最新的，但没有当前上下文。|  
|`JsErrorNotImplemented`|托管 API 尚未实现。|  
|`JsErrorNullArgument`|在不允许 null 的上下文中，宿主 API 的参数为 null。|  
|`JsErrorObjectNotInspectable`|对象不能解包到 `IInspectable` 指针。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsErrorOutOfMemory`|The Chakra engine has run out of memory.|  
|`JsErrorPropertyNotSymbol`|对符号属性 ID 进行操作但使用非符号属性 ID 调用的托管 API。如果使用非符号属性 ID 调用函数，则返回 `JsGetSymbolFromPropertyId` 错误代码。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsErrorPropertyNotString`|对字符串属性 ID 进行操作但使用非字符串属性 ID 调用的托管 API。如果用非字符串属性 ID 调用函数，则现有函数将返回 `JsGetPropertyNamefromId` 错误代码。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsErrorRuntimeInUse`|无法释放仍在使用的运行时。|  
|`JsErrorScriptCompile`|JavaScript 无法编译。|  
|`JsErrorScriptEvalDisabled`|脚本因尝试使用或 eval 被禁用 `eval` `function` 而终止。|  
|`JsErrorScriptException`|运行脚本时发生 JavaScript 异常。|  
|`JsErrorScriptTerminated`|由于请求暂停运行时，脚本已终止。|  
|`JsErrorWrongRuntime`|使用在不同的 JavaScript 运行时上创建的对象调用了托管 API。|  
|`JsErrorWrongThread`|在错误的线程上调用了宿主 API。|  
|`JsNoError`|成功错误代码。|  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
