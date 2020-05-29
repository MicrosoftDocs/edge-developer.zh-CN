---
description: 设置运行时的当前内存限制。
title: JsSetRuntimeMemoryLimit 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryLimit
helpviewer_keywords:
- JsSetRuntimeMemoryLimit function
ms.assetid: 74feb31f-19f6-43e3-b117-0694c59ac593
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ec8d098c528ac813926797280541aa2c9c4fee79
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564073"
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
 新的运行时内存限制（以字节为单位），或者为-1，表示无内存限制。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 内存限制将导致超出限制的任何操作失败，并出现 "内存不足" 错误。 将运行时的内存限制设置为-1 意味着运行时没有内存限制。 新的运行时默认为没有内存限制。 如果新的内存限制超过当前使用，则调用将成功，并且此运行时中的任何未来分配都将失败，直到运行时的内存使用量降到限制以下。  
  
 无论运行时是否在另一个线程上处于活动状态，都可以始终设置运行时的内存限制。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)