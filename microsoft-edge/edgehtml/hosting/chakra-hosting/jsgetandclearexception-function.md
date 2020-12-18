---
description: 返回导致当前上下文的运行时为异常状态并重置该运行时的异常状态异常。
title: JsGetAndClearException 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetAndClearException
helpviewer_keywords:
- JsGetAndClearException function
ms.assetid: 6aec8a88-41ee-47f6-b5f4-32f3cae6bb7b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb296ea351d0466a856d5ac020550ebacc254ac9
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232324"
---
# JsGetAndClearException 函数

返回导致当前上下文的运行时为异常状态并重置该运行时的异常状态异常。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetAndClearException(  
   _Out_ JsValueRef *exception  
);  
```  
  
#### 参数  
 `exception`  
 当前上下文运行时的异常。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 如果当前上下文的运行时未在异常状态中，则此 API 将返回 `JsErrorInvalidArgument` 。 如果禁用运行时，这将返回一个指示脚本已终止的异常，但它不会清除该异常 (如果使用) 重新启用运行时，将 `JsEnableRuntimeExecution` 清除该异常。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
