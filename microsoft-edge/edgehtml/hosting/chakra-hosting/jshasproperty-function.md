---
description: 确定对象是否具有属性。
title: JsHasProperty 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasProperty
helpviewer_keywords:
- JsHasProperty function
ms.assetid: 26c94c3d-aae6-4257-8644-df63c7e714fb
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e45ecfaafb06c49a6a3773eb798ee93a19fd6d6e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232409"
---
# JsHasProperty 函数

确定对象是否具有属性。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsHasProperty(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ bool *hasProperty  
);  
```  
  
#### 参数  
 `object`  
 可能包含该属性的对象。  
  
 `propertyId`  
 属性的 ID。  
  
 `hasProperty`  
 对象是 (还是原型) 属性。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
