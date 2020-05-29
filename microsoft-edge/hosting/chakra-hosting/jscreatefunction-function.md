---
description: 创建新的 JavaScript 函数。
title: JsCreateFunction 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateFunction
helpviewer_keywords:
- JsCreateFunction function
ms.assetid: b298a96a-5ef7-4203-a8c8-55f9bfc6d2bb
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 22585afcb379c281eda621c3b233ccf4bc278ad1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563164"
---
# JsCreateFunction 函数
创建新的 JavaScript 函数。
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateFunction(  
   _In_ JsNativeFunction nativeFunction,  
   _In_opt_ void *callbackState,  
   _Out_ JsValueRef *function  
);  
```  
  
#### 参数  
 `nativeFunction`  
 调用函数时调用的方法。  
  
 `callbackState`  
 用户提供的状态将传回回调。  
  
 `function`  
 新的函数对象。  
  
## 返回值  
 通话的结果（如果有）。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)