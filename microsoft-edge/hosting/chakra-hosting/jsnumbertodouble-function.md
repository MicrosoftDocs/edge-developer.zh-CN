---
description: 检索 `double` 数字值的值。
title: JsNumberToDouble 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsNumberToDouble
helpviewer_keywords:
- JsNumberToDouble function
ms.assetid: 5f52e8b6-2b70-49a3-879a-bd83ebf2ac33
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: fc99e02aa0376bb100b4e1302c29532a57bd539f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563082"
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
 要转换为值的数字值 `double` 。  
  
 `doubleValue`  
 `double`值。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 此函数检索数字值的值。 `JsErrorInvalidArgument`如果值的类型不是数字，它将失败。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)