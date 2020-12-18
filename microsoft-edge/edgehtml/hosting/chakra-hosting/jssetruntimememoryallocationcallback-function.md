---
description: 为指定的运行时设置内存分配回调。
title: JsSetRuntimeMemoryAllocationCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ee2abf36e14c26ac58b90d48a6115fd6502307c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232356"
---
# JsSetRuntimeMemoryAllocationCallback 函数

为指定的运行时设置内存分配回调。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeMemoryAllocationCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryAllocationCallback allocationCallback  
);  
```  
  
#### 参数  
 `runtime`  
 要注册其分配回调的运行时。  
  
 `callbackState`  
 用户提供的状态将传递回回调。  
  
 `allocationCallback`  
 为内存分配事件调用的内存分配回调。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 注册内存分配回调将导致运行时在从操作系统获取内存或向操作系统释放内存时回调主机。 在运行时内存管理器分配内存块之前调用回调例程。 如果回调返回 false，则分配将被拒绝。 运行时内存管理器还将在释放内存块后以及分配失败后调用回调例程。  
  
 在当前运行时执行线程上调用回调，因此在回调完成之前将阻止执行。  
  
 不存储回调的返回值;以前拒绝的分配不会阻止运行时稍后再次调用回调以用于新的内存分配。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
