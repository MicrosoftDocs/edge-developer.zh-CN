---
description: 将 `VARIANT` 作为 JavaScript 值的投影初始化传入的。
title: JsValueToVariant 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: d8748fddcc149cf09fbd46ad3ad489cd66200b71
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563061"
---
# JsValueToVariant 函数
将 `VARIANT` 作为 JavaScript 值的投影初始化传入的。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### 参数  
 `object`  
 项目的 JavaScript 值 `VARIANT` 。  
  
 `variant`  
 指向 `VARIANT` 将初始化为投影的结构的指针。  
  
## 返回值  
  
## 备注  
 `VARIANT`COM 自动化客户端可以使用投影来调入计划的 JavaScript 对象。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)