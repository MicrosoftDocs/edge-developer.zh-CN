---
description: 设置线程上的当前脚本上下文。
title: JsSetCurrentContext 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetCurrentContext
helpviewer_keywords:
- JsSetCurrentContext function
ms.assetid: 603cc94c-6585-411b-89f9-c6f144e2aa30
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 60ec1760c582f1f6771a5af64f59c4a77b1a43f8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232358"
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
 要成为当前脚本的脚本上下文。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  

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
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
