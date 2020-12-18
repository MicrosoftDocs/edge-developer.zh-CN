---
description: 检索 `int` 数字值的值。
title: JsNumberToInt 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8b9256d6-76ac-4c74-a97c-fbb16c13f5f5
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 928be9a7cc5cd3e26e8b8df99af1e08a6c50209c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232539"
---
# JsNumberToInt 函数

检索 `int` 数字值的值。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsNumberToInt(  
      _In_ JsValueRef value,  
      _Out_ int *intValue  
);  
```  
  
#### 参数  
 `value`  
 要转换为值的数量 `int` 值。  
  
 `intValue`  
 `int`值。  
  
## 返回值  
  
## 备注  
 此函数检索数字值并转换为 `int` 值。 如果值的类型 `JsErrorInvalidArgument` 不是数字，则失败。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
