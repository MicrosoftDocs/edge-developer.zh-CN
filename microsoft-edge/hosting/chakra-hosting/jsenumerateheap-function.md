---
description: 枚举当前上下文的堆。
title: JsEnumerateHeap 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsEnumerateHeap
helpviewer_keywords:
- JsEnumerateHeap function
ms.assetid: 3e518e0b-b959-4686-899c-83e6b1946c9d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f1c2590388fcc09b641e3908d45eef7271bcb1ad
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564272"
---
# JsEnumerateHeap 函数
枚举当前上下文的堆。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsEnumerateHeap(  
   _Out_ IActiveScriptProfilerHeapEnum **enumerator  
);  
```  
  
#### 参数  
 `enumerator`  
 堆枚举器。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 枚举堆时，无法删除当前上下文，并且在释放堆枚举器之前，所有对上下文状态进行修改的调用都将失败。  
  
 需要活动脚本上下文。  
  
 此 API 在桌面应用中受支持，但在应用商店应用中不受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)