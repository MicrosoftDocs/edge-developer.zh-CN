---
description: 获取与名称关联的属性 ID。
title: JsGetPropertyIdFromName 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPropertyIdFromName
helpviewer_keywords:
- JsGetPropertyIdFromName function
ms.assetid: 1674906f-746a-4c62-99cd-023276683a86
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: adc8de4d55fa0c74ad191b4621ceb3a54026d02d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232550"
---
# JsGetPropertyIdFromName 函数

获取与名称关联的属性 ID。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromName(  
   _In_z_ const wchar_t *name,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### 参数  
 `name`  
 要获取或创建的属性 ID 的名称。 该名称可能只包含数字。  
  
 `propertyId`  
 此运行时中给定名称的属性 ID。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 属性 ID 特定于上下文，不能跨上下文使用。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
