---
description: 创建具有名称的新 JavaScript 函数。
title: JsCreateNamedFunction 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 72f40d06-ab82-4fed-a632-68af6b4126c2
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b54add359422a9312a0ded641051fd04585f3d7e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232338"
---
# JsCreateNamedFunction 函数

创建具有名称的新 JavaScript 函数。
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateNamedFunction(  
   _In_ JsValueRef name,  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### 参数  
 `name`  
 将用于诊断和字符串化目的的此函数的名称。  
  
 `nativeFunction`  
 调用函数时要调用的方法。  
  
 `callbackState`  
 用户提供的状态将传递回回调。  
  
 `function`  
 新函数对象。  
  
## 返回值  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
