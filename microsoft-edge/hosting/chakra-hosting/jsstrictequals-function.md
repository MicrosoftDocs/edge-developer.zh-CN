---
description: 比较两个 JavaScript 值是否严格相等。
title: JsStrictEquals 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStrictEquals
helpviewer_keywords:
- JsStrictEquals function
ms.assetid: b35bc655-7ff8-496a-b678-8950bb976047
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b7f2b7a66c32428100f0c0d0f9db6150559ed7a2
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564166"
---
# JsStrictEquals 函数
比较两个 JavaScript 值是否严格相等。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsStrictEquals(  
   _In_ JsValueRef object1,  
   _In_ JsValueRef object2,  
   _Out_ bool *result  
);  
```  
  
#### 参数  
 `object1`  
 要比较的第一个对象。  
  
 `object2`  
 要比较的第二个对象。  
  
 `result`  
 值是否严格相等。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 此函数等效于 `===` Javascript 中的运算符。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)