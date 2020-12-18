---
description: 确定当前上下文的运行时是否位于异常状态。
title: JsHasException 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsHasException
helpviewer_keywords:
- JsHasException function
ms.assetid: ac7da3ce-c746-4154-bbb8-bcb0859a8d5b
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4f4abbd6c69a6b2b6414dae2f1de3a2acf21cc32
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232065"
---
# JsHasException 函数

确定当前上下文的运行时是否位于异常状态。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsHasException(  
   _Out_ bool *hasException  
);  
```  
  
#### 参数  
 `hasException`  
 当前上下文的运行时是否位于异常状态。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 如果对运行时的调用导致异常 (运行脚本或由于转换失败) ，运行时将进入"异常状态"。 对运行时应用程序创建的任何上下文的所有 (异常 API 除外) 异常清除之前，将失败 `JsErrorInExceptionState` 。  
  
 如果回调返回到引擎时，当前上下文的运行时为异常状态，则引擎将自动重新引发异常。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
