---
description: 获取上下文所属的运行时。
title: JsGetRuntime 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetRuntime
helpviewer_keywords:
- JsGetRuntime function
ms.assetid: 5b62e940-a885-405a-9fdd-0495fb391b95
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6eeb132dd35fcb5104828bef8e8f27334a5f34e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563112"
---
# JsGetRuntime 函数
获取上下文所属的运行时。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetRuntime(  
   _In_ JsContextRef context,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### 参数  
 `context`  
 要从中获取运行时的上下文。  
  
 `runtime`  
 上下文所属的运行时。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)