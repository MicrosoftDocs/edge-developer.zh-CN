---
description: 从 Chakra 托管 API 返回的错误代码。
title: JsErrorCode 枚举 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsErrorCode
helpviewer_keywords:
- JsErrorCode enumeration
ms.assetid: 4902f3f3-47a5-4e74-9c29-f96eeecbcda9
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: e3d1a319872ac69b2acaf19997f3c38f9c04597b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564266"
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
|`JsErrorAlreadyDebuggingContext`|无法将上下文置于调试状态，因为它已处于调试状态。|  
|`JsErrorAlreadyProfilingContext`|上下文无法启动分析，因为它已在分析。|  
|`JsErrorArgumentNotObject`|使用非对象值调用在对象值上运行的托管 API。|  
|`JsErrorBadSerializedScript`|使用了错误的序列化脚本，或序列化脚本由不同版本的 Chakra 引擎序列化。|  
|`JsErrorCannotDisableExecution`|运行时不支持可靠的脚本中断。|  
|`JsErrorCannotSerializeDebugScript`|无法在调试上下文中序列化脚本。|  
|`JsErrorCategoryEngine`|与引擎本身中出现的错误相关的错误的类别。|  
|`JsErrorCategoryFatal`|错误的类别，表示引擎出现故障。|  
|`JsErrorCategoryScript`|与脚本中的错误相关的错误的类别。|  
|`JsErrorCategoryUsage`|与 API 本身的错误用法相关的错误的类别。|  
|`JsErrorFatal`|引擎出现致命错误。|  
|`JsErrorHeapEnumInProgress`|堆枚举目前正在脚本上下文中进行。|  
|`JsErrorIdleNotEnabled`|当主机未启用空闲处理时给出的空闲通知。|  
|`JsErrorInDisabledState`|运行时处于禁用状态。|  
|`JsErrorInExceptionState`|引擎处于异常状态，并且在清除该异常之前不能调用任何 Api。|  
|`JsErrorInObjectBeforeCollectCallback`|在收集回调之前对象中不支持该操作。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsErrorInProfileCallback`|脚本上下文位于配置文件回调的中间。|  
|`JsErrorInThreadServiceCallback`|当前正在进行线程服务回调。|  
|`JsErrorInvalidArgument`|托管 API 的参数无效。|  
|`JsErrorNoCurrentContext`|托管 API 要求上下文是最新的，但没有当前上下文。|  
|`JsErrorNotImplemented`|尚未实现托管 API。|  
|`JsErrorNullArgument`|托管 API 的参数在不允许使用 null 的上下文中为 null。|  
|`JsErrorObjectNotInspectable`|无法将对象解包到 `IInspectable` 指针。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsErrorOutOfMemory`|Chakra 引擎内存不足。|  
|`JsErrorPropertyNotSymbol`|对符号属性 id 进行操作但使用非符号属性 id 调用的托管 API。`JsGetSymbolFromPropertyId`如果使用非符号属性 id 调用该函数，则返回错误代码。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsErrorPropertyNotString`|对字符串属性 id 进行操作但使用非字符串属性 id 调用的托管 API。`JsGetPropertyNamefromId`如果使用非字符串属性 id 调用函数，则该错误代码由现有函数返回。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsErrorRuntimeInUse`|无法释放仍在使用的运行时。|  
|`JsErrorScriptCompile`|JavaScript 无法编译。|  
|`JsErrorScriptEvalDisabled`|脚本已终止，因为它尝试使用 `eval` 或 `function` 已禁用 eval。|  
|`JsErrorScriptException`|运行脚本时发生 JavaScript 异常。|  
|`JsErrorScriptTerminated`|由于请求暂停运行时，脚本被终止。|  
|`JsErrorWrongRuntime`|使用在不同 JavaScript 运行时上创建的对象调用了托管 API。|  
|`JsErrorWrongThread`|在错误的线程上调用了托管 API。|  
|`JsNoError`|成功错误代码。|  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)