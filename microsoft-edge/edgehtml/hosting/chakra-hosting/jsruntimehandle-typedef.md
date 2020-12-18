---
description: 一个对 Chakra 运行时的句柄。
title: JsRuntimeHandle Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ab08243505b9699fe07ca2e80f7294adf9eb78ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232183"
---
# JsRuntimeHandle Typedef

一个对 Chakra 运行时的句柄。  
  
## 语法  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## 备注  
 每个 Chakra 运行时都有其自己的独立执行引擎、JIT 编译器和垃圾回收堆。 因此，每个运行时与其他运行时完全隔离。  
  
 运行时可用于任何线程，但每次只能有一个线程调用运行时。  
  
> [!WARNING]
>  JsRuntimeHandle 与 Chakra 托管 API 中的其他对象引用不同，它不包含垃圾回收，因为它包含垃圾回收堆本身。 在调用 JsDisposeRuntime 之前，运行时将继续存在。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
