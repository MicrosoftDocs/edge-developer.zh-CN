---
description: 用户为内存分配事件实现回调例程。
title: JsMemoryAllocationCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b11b3d076c01dbfcae190fd665528323d6f8b987
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563088"
---
# JsMemoryAllocationCallback Typedef
用户为内存分配事件实现回调例程。  
  
## 语法  
  
```cpp  
typedef bool (CALLBACK * JsMemoryAllocationCallback)(  
   _In_opt_ void *callbackState,  
   _In_ JsMemoryEventType allocationEvent,  
   _In_ size_t allocationSize  
);  
```  
  
#### 参数  
 callbackState  
 传递给 JsSetRuntimeMemoryAllocationCallback 的状态。  
  
 allocationEvent  
 类型分配事件的类型。  
  
 allocationSize  
 分配的大小。  
  
## 属性值/返回值  
 对于 JsMemoryAllocate 事件，返回 true 将允许运行时继续分配。 返回 false 表示分配请求被拒绝。 对于其他分配事件，将忽略返回值。  
  
## 备注  
 使用 JsSetRuntimeMemoryAllocationCallback 注册此回调。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)