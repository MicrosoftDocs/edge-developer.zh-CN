---
description: 确定当前上下文的运行时是否处于异常状态。
title: JsHasException 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 25ddb8f9cc407dd414a6cd2210c315eb4dd7b141
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564230"
---
# JsHasException 函数
确定当前上下文的运行时是否处于异常状态。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### 参数  
 `hasException`  
 当前上下文的运行时是否处于异常状态。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 如果对运行时的调用导致异常（因为运行脚本或由于类似转换失败），则会将运行时置于 "异常状态"。 对由运行时创建的任何上下文的所有调用（除异常 Api 外）都将失败， `JsErrorInExceptionState` 直到清除该异常。  
  
 如果在回调返回到引擎时当前上下文的运行时处于异常状态，引擎将自动再次引发该异常。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)