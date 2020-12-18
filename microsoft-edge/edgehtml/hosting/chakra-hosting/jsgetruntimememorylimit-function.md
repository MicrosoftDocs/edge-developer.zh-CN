---
description: 获取运行时的当前内存限制。
title: JsGetRuntimeMemoryLimit 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryLimit
helpviewer_keywords:
- JsGetRuntimeMemoryLimit function
ms.assetid: ed81ca60-99fd-46b0-89ae-f6ac07926904
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ed04a0fb921d22eea17eaf86ef7a0152fbf2a1d0
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232710"
---
# JsGetRuntimeMemoryLimit 函数

获取运行时的当前内存限制。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryLimit  
);  
```  
  
#### 参数  
 `runtime`  
 要检索其内存限制的运行时。  
  
 `memoryLimit`  
 运行时的当前内存限制（以字节为单位）或 -1（如果尚未设置限制）。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 运行时的内存限制始终可以检索，而不管该运行时在另一个线程上是否处于活动状态。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
