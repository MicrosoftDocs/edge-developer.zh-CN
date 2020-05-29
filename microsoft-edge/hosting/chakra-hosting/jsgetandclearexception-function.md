---
description: 返回导致当前上下文的运行时处于异常状态并为该运行时重置异常状态的异常。
title: JsGetAndClearException 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: eb70b4b66b4bb270d9f26487708720efddc2effa
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564264"
---
# JsGetAndClearException 函数
返回导致当前上下文的运行时处于异常状态并为该运行时重置异常状态的异常。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### 参数  
 `exception`  
 当前上下文的运行时的异常。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 如果当前上下文的运行时未处于异常状态，此 API 将返回 `JsErrorInvalidArgument` 。 如果运行时已禁用，这将返回一个异常，指示脚本已终止，但不会清除异常（如果运行时使用重新启用，则会清除异常 `JsEnableRuntimeExecution` ）。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)