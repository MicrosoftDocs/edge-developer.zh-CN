---
description: 用户为内存分配事件实现了回调例程。
title: JsMemoryAllocationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 511babc7-3caa-4ee5-82a2-943bbd34db8d
caps.latest.revision: 7
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 22b5cc0fe5a2c8b49f71c91d28f95ba29af37849
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232198"
---
# JsMemoryAllocationCallback Typedef

用户为内存分配事件实现了回调例程。  
  
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
 对于 JsMemoryAllocate 事件，返回 true 允许运行时继续分配。 返回 false 表示分配请求被拒绝。 对于其他分配事件，将忽略返回值。  
  
## 备注  
 使用 JsSetRuntimeMemoryAllocationCallback 注册此回调。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
