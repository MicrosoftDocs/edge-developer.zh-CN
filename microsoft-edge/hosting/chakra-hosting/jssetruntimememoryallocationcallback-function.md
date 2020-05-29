---
description: 为指定的运行时设置内存分配回调。
title: JsSetRuntimeMemoryAllocationCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeMemoryAllocationCallback
helpviewer_keywords:
- JsSetRuntimeMemoryAllocationCallback function
ms.assetid: 6aa7d58d-6456-4df1-815f-1ba36fb4ae14
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5c648761473023f00e894fbf75c794cfcc9422c5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564074"
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
 要注册分配回调的运行时。  
  
 `callbackState`  
 用户提供的状态将传回回拨。  
  
 `allocationCallback`  
 为内存分配事件调用内存分配回调。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 注册内存分配回调将使运行时在从操作系统获取内存或释放内存到操作系统时回调主机。 在运行时内存管理器分配内存块之前调用回调例程。 如果回调返回 false，则分配将被拒绝。 在释放内存块以及分配失败后，运行时内存管理器也将调用回调例程。  
  
 回调将在当前运行时执行线程上调用，因此执行会被阻止，直到回调完成。  
  
 不存储回调的返回值;以前拒绝的分配不会阻止运行时再次调用新内存分配的回调。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)