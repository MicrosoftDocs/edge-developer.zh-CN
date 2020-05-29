---
description: Chakra 运行时的句柄。
title: JsRuntimeHandle Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 69e59bfd-9b0e-4710-9aa8-fbd6844171bc
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4ccdcf39ec6062db47e1b9de249d75c8804de405
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564189"
---
# JsRuntimeHandle Typedef
Chakra 运行时的句柄。  
  
## 语法  
  
```cpp  
typedef void *JsRuntimeHandle;  
```  
  
## 备注  
 每个 Chakra 运行时都有其自己的独立执行引擎、JIT 编译器和垃圾回收的堆。 因此，每个运行时都与其他运行时完全隔离。  
  
 运行时可以在任何线程上使用，但每次只能有一个线程可以调用运行时。  
  
> [!WARNING]
>  与 Chakra 托管 API 中的其他对象引用不同，JsRuntimeHandle 不会被垃圾回收，因为它包含垃圾回收的堆本身。 在调用 JsDisposeRuntime 之前，运行时将继续存在。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)