---
description: 返回一个值，该值指示是否枚举当前上下文的堆。
title: JsIsEnumeratingHeap 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIsEnumeratingHeap
helpviewer_keywords:
- JsIsEnumeratingHeap function
ms.assetid: 5d14518e-3153-43f2-9a9c-068580cbd54f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5b66fc70ea79d78029f6bc0c900ade1aae38e604
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232573"
---
# JsIsEnumeratingHeap 函数

返回一个值，该值指示是否枚举当前上下文的堆。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsIsEnumeratingHeap(  
   _Out_ bool *isEnumeratingHeap  
);  
```  
  
#### 参数  
 `isEnumeratingHeap`  
 是否枚举堆。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 在桌面应用中受支持，但在应用商店应用中不受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
