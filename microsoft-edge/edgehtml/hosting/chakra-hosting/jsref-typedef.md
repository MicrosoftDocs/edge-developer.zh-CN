---
description: 对由 Chakra 垃圾回收器拥有的对象的引用。
title: JsRef Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6aafc39f-6b9c-457f-8bf0-48831bffe9b8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 69d13472b15b5d448908b5dafb2e3d7dc0ace7e4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232024"
---
# JsRef Typedef

对由 Chakra 垃圾回收器拥有的对象的引用。  
  
## 语法  
  
```cpp  
typedef void *JsRef;  
```  
  
## 备注  
 一个 Chakra 运行时将自动跟踪 JsRef 引用，只要它们存储在本地变量或参数中 (即堆栈) 。 将 JsRef 存储在堆栈上外部的某个位置需要调用 JsAddRef 和 JsRelease 来管理对象的生存期，否则垃圾回收器可能会释放仍在使用中的对象。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
