---
description: 添加对垃圾回收对象的引用。
title: JsAddRef 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsAddRef
helpviewer_keywords:
- JsAddRef function
ms.assetid: a7f3ed49-6a86-489a-abdf-c99428e79cae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fd397dbfeacafdf12728ef0ca2a98d97405f6592
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232232"
---
# JsAddRef 函数

添加对垃圾回收对象的引用。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsAddRef(  
   _In_ JsRef ref,  
   _Out_opt_ unsigned int *count  
);  
```  
  
#### 参数  
 `ref`  
 要添加引用的对象。  
  
 `count`  
 对象的新引用计数 (null 值) 。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 只需在不会存储在堆栈上的某一位置的句柄上 `JsRef` 调用它。 调用可确保在调用引用的对象之前 `JsAddRef` `JsRef` 不会 `JsRelease` 释放该对象。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
