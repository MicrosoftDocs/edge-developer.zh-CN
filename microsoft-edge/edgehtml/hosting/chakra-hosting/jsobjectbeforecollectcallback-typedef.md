---
description: 在收集对象之前调用的回调。
title: JsObjectBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4c24385ec5e15919719ffb0ae71c8adf39c1724c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232537"
---
# JsObjectBeforeCollectCallback Typedef

在收集对象之前调用的回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### 参数  
 `ref`  
 要收集的对象。  
  
 `callbackState`  
 传递给 `JsSetObjectBeforeCollectCallback` 的状态。  
  
## 备注  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
