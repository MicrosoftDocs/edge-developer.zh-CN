---
description: 检索 `double` 数字值的值。
title: JsNumberToDouble 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsNumberToDouble
helpviewer_keywords:
- JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e4ae744f091045116a639aff619c475c7c7025f3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232541"
---
# JsNumberToDouble 函数

检索 `double` 数字值的值。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToDouble(  
   _In_ JsValueRef value,  
   _Out_ double *doubleValue  
);  
```  
  
#### 参数  
 `value`  
 要转换为值的数量 `double` 值。  
  
 `doubleValue`  
 `double`值。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 此函数检索数字值的值。 如果值的类型 `JsErrorInvalidArgument` 不是数字，则失败。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
