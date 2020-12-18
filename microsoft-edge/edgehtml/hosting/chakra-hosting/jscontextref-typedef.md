---
description: 对脚本上下文的引用。
title: JsContextRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c8a8fcbd67afb150d682cfc19321f0f13acfe3a6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232219"
---
# JsContextRef Typedef

对脚本上下文的引用。  
  
## 语法  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## 备注  
 每个脚本上下文都包含其自己的全局对象，不同于其他脚本上下文中的全局对象。  
  
 许多 Chakra 托管 API 都需要"活动"脚本上下文，可以使用它进行设置 `JsSetCurrentContext` 。 需要设置当前上下文的 Chakra 托管 API 将明确记录在文档中。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
