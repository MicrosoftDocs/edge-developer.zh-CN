---
description: '运行时的属性。 '
title: JsRuntimeAttributes 枚举 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9b8f6788f1de4988e3936701cfc742a564c92cfd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564191"
---
# JsRuntimeAttributes 枚举
运行时的属性。  
  
## 语法  
  
```cpp  
enum JsRuntimeAttributes;  
```  
  
## 成员  
  
### 值  
  
|名称|描述|  
|----------|-----------------|  
|`JsRuntimeAttributeAllowScriptInterrupt`|运行时应支持可靠的脚本中断。 这会增加运行时将以少量运行时性能为代价检查脚本中断请求的位置数。|  
|`JsRuntimeAttributeDisableBackgroundWork`|运行时不会在后台线程上执行任何工作（如垃圾回收）。|  
|`JsRuntimeAttributeDisableEval`|Using `eval` 或 `function` 构造函数将引发异常。|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|运行时不会生成本机代码。|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|运行时将启用所有实验功能。|  
|`JsRuntimeAttributeEnableIdleProcessing`|主机将呼叫 `JsIdle` ，因此启用空闲处理。 否则，运行时将略微严格地管理内存。|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|调用 `JsSetException` 还会将异常调度到脚本调试程序（如果有），让调试程序有机会中断异常。|  
|`JsRuntimeAttributeNone`|无特殊属性。|  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)