---
description: 设置线程上的当前脚本上下文。
title: JsSetCurrentContext 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetCurrentContext
helpviewer_keywords:
- JsSetCurrentContext function
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57620ad0e986034791ec07765d7cc115b958d661
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564183"
---
# JsSetCurrentContext 函数
设置线程上的当前脚本上下文。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetCurrentContext(  
   _In_ JsContextRef context  
);  
```  
  
#### 参数  
 `context`  
 要成为最新的脚本上下文。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  

## 示例

```cpp
JsRuntimeHandle runtime;
JsContextRef context;

// Create a runtime.
JsCreateRuntime(JsRuntimeAttributeNone, nullptr, &runtime);

// Create an execution context.
JsCreateContext(runtime, &context);

// Now set the current execution context.
JsSetCurrentContext(context);
```

## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)