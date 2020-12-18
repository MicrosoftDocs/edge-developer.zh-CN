---
description: 执行完整的垃圾回收。
title: JsCollectGarbage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCollectGarbage
helpviewer_keywords:
- JsCollectGarbage function
ms.assetid: 995c79a5-6e18-45be-81ff-2a5d3348edb8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: c551ddf119ec0aa349fcd756f6001d92dbbb0faa
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232216"
---
# JsCollectGarbage 函数

执行完整的垃圾回收。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCollectGarbage(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### 参数  
 `runtime`  
 将在其中执行垃圾回收的运行时。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
