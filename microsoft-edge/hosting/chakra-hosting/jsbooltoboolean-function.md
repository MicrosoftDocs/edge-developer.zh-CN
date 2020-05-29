---
description: 从值创建一个布尔值 `bool` 。
title: JsBoolToBoolean 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsBoolToBoolean
helpviewer_keywords:
- JsBoolToBoolean function
ms.assetid: 24322ea3-0638-40a3-9b4c-fc912ebed3ff
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f795bdd02a2a21dc4a0c8948a76ef817d6e0fac6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563198"
---
# JsBoolToBoolean 函数
从值创建一个布尔值 `bool` 。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode JsBoolToBoolean(  
   _In_ bool value,  
   _Out_ JsValueRef *booleanValue  
);  
```  
  
#### 参数  
 `value`  
 要转换的值。  
  
 `booleanValue`  
 已转换的值。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)