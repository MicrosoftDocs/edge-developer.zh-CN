---
description: 将当前上下文的运行时设置为异常状态。
title: JsSetException 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetException
helpviewer_keywords:
- JsSetException function
ms.assetid: c528793a-2e1b-4ee1-bd2e-e63fd547dc40
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2c2e3840d2a831db23a525c5d8854b9b2fcfb8c9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232397"
---
# JsSetException 函数

将当前上下文的运行时设置为异常状态。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetException(  
   _In_ JsValueRef exception  
);  
```  
  
#### 参数  
 `exception`  
 为当前上下文的运行时设置的 JavaScript 异常。  
  
## 返回值  
 `JsNoError` 如果引擎已设置为异常状态，则否则为失败代码。  
  
## 备注  
 如果当前上下文的运行时已进入异常状态，则此 API 将返回 `JsErrorInExceptionState` 。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
