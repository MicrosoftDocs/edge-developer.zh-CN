---
description: 设置运行时的当前内存限制。
title: JsSetRuntimeMemoryLimit 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1c31d8bbbec4be22fc1af09e546ad4c95f8ec2bd
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232008"
---
# JsSetRuntimeMemoryLimit 函数

设置运行时的当前内存限制。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryLimit(  
   _In_ JsRuntimeHandle runtime,  
   _In_ size_t memoryLimit  
);  
```  
  
#### 参数  
 `runtime`  
 要设置其内存限制的运行时。  
  
 `memoryLimit`  
 新的运行时内存限制（以字节为单位）或 -1（无内存限制）。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 内存限制将导致任何超过该限制的操作失败，并出现"内存不足"错误。 将运行时的内存限制设置为 -1 意味着运行时没有内存限制。 新运行时默认为没有内存限制。 如果新内存限制超过当前使用量，调用将成功，并且此运行时中任何未来分配将失败，直到运行时的内存使用率低于该限制。  
  
 运行时的内存限制始终可以设置，而不管该运行时在另一个线程上是否处于活动状态。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
