---
description: 获取运行时的当前内存使用情况。
title: JsGetRuntimeMemoryUsage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntimeMemoryUsage
helpviewer_keywords:
- JsGetRuntimeMemoryUsage function
ms.assetid: b9bd4146-bfbc-4cb1-a0e9-a0ded7fb09bd
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9ec8472132b4c50b279ee95f36995bf46c0e29e5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563105"
---
# JsGetRuntimeMemoryUsage 函数
获取运行时的当前内存使用情况。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntimeMemoryUsage(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ size_t *memoryUsage  
);  
```  
  
#### 参数  
 `runtime`  
 要检索其内存使用情况的运行时。  
  
 `memoryUsage`  
 运行时的当前内存使用（以字节为单位）。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 无论运行时是否在另一个线程上处于活动状态，都可以始终检索内存使用情况。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)