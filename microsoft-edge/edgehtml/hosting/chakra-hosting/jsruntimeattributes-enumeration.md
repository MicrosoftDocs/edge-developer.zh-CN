---
description: '运行时的属性。 '
title: JsRuntimeAttributes 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRuntimeAttributes
helpviewer_keywords:
- JsRuntimeAttributes enumeration
ms.assetid: f76d82e9-a695-4d6a-96c1-b3a4d27fed68
caps.latest.revision: 14
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: bbc5341c3214d9796278d334507e284989ff45dd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232322"
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
|`JsRuntimeAttributeAllowScriptInterrupt`|运行时应支持可靠的脚本中断。 这将增加运行时将检查脚本中断请求的位置数量，但会花费少量运行时性能。|  
|`JsRuntimeAttributeDisableBackgroundWork`|运行时将不会执行任何工作 (如后台线程上的) 垃圾回收。|  
|`JsRuntimeAttributeDisableEval`|使用 `eval` 或 `function` 构造函数将引发异常。|  
|`JsRuntimeAttributeDisableNativeCodeGeneration`|运行时不会生成本机代码。|  
|`JsRuntimeAttributeEnableExperimentalFeatures`|运行时将启用所有实验功能。|  
|`JsRuntimeAttributeEnableIdleProcessing`|主机将调用 `JsIdle` ，因此启用空闲处理。 否则，运行时将更积极地管理内存。|  
|`JsRuntimeAttributeDispatchSetExceptionsToDebugger`|调用 `JsSetException` 还会将异常调度到脚本调试 (如果) 为调试程序提供中断异常的机会。|  
|`JsRuntimeAttributeNone`|无特殊属性。|  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
