---
description: 分配回调事件类型。
title: JsMemoryEventType 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsMemoryEventType
helpviewer_keywords:
- JsMemoryEventType enumeration
ms.assetid: b4b176b6-b536-472e-8999-95b681a1df55
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a28010f908285098cf652b497b6d6c272bc763fc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232007"
---
# JsMemoryEventType 枚举

分配回调事件类型。  
  
## 语法  
  
```cpp  
enum JsMemoryEventType;  
```  
  
## 成员  
  
### 值  
  
|名称|描述|  
|----------|-----------------|  
|`JsMemoryAllocate`|指示内存分配请求。|  
|`JsMemoryFailure`|指示分配事件失败。|  
|`JsMemoryFree`|指示释放内存事件。|  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
