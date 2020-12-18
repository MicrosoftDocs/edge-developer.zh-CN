---
description: 将对象的属性放在一起。
title: JsSetProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetProperty
helpviewer_keywords:
- JsSetProperty function
ms.assetid: 2c36bebf-ec86-425c-8131-2dd75fd30f40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 29c3e04fc240bd63fc755c6727752d053b94484d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232410"
---
# JsSetProperty 函数

将对象的属性放在一起。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _In_ JsValueRef value,  
   _In_ bool useStrictRules  
);  
```  
  
#### 参数  
 `object`  
 包含该属性的对象。  
  
 `propertyId`  
 属性的 ID。  
  
 `value`  
 属性的新值。  
  
 `useStrictRules`  
 属性集应遵循严格的模式规则。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
