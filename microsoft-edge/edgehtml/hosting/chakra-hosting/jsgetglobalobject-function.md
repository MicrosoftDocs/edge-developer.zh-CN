---
description: 获取当前脚本上下文中的全局对象。
title: JsGetGlobalObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetGlobalObject
helpviewer_keywords:
- JsGetGlobalObject function
ms.assetid: d3e91e64-1ca3-4d2b-aada-725ded0fd0b1
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cda960710180c135b99abd359d0cc76776ff0225
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232442"
---
# JsGetGlobalObject 函数

获取当前脚本上下文中的全局对象。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetGlobalObject(  
   _Out_ JsValueRef *globalObject  
);  
```  
  
#### 参数  
 `globalObject`  
 全局对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
