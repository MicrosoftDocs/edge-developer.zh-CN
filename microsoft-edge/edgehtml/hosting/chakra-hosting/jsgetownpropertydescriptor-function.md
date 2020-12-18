---
description: 获取对象自己的属性的属性描述符。
title: JsGetOwnPropertyDescriptor 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetOwnPropertyDescriptor
helpviewer_keywords:
- JsGetOwnPropertyDescriptor function
ms.assetid: 44c417ce-ab63-44eb-a0ab-19838e3ab34f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 05c7a58fa12d7ca8013c512f40031963ebc8ac18
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232395"
---
# JsGetOwnPropertyDescriptor 函数

获取对象自己的属性的属性描述符。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetOwnPropertyDescriptor(  
   _In_ JsValueRef object,  
   _In_ JsPropertyIdRef propertyId,  
   _Out_ JsValueRef *propertyDescriptor  
);  
```  
  
#### 参数  
 `object`  
 具有该属性的对象。  
  
 `propertyId`  
 属性的 ID。  
  
 `propertyDescriptor`  
 属性描述符。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
