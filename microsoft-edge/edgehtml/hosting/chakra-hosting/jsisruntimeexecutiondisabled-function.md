---
description: 返回一个值，该值指示是否在运行时禁用脚本执行。
title: JsIsRuntimeExecutionDisabled 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0ce59c77525abdb2dd6cac71dde1378264395e79
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232022"
---
# JsIsRuntimeExecutionDisabled 函数

返回一个值，该值指示是否在运行时禁用脚本执行。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### 参数  
 `runtime`  
 指定要检查执行是否禁用的运行时。  
  
 `isDisabled`  
 `true` 如果禁用执行， `false` 否则。  
  
## 返回值  
 `JsNoError` 如果操作成功，则否则失败代码。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
