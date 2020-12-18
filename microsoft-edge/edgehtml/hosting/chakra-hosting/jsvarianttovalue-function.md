---
description: 创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。
title: JsVariantToValue 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsVariantToValue
helpviewer_keywords:
- JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 58c928b519b5a9a678b6cd6ad367e1db2332f021
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232347"
---
# JsVariantToValue 函数

创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsVariantToValue(  
   _In_ VARIANT *variant,  
   _Out_ JsValueRef *value  
);  
```  
  
#### 参数  
 `variant`  
 要 `VARIANT` 规划的 A。  
  
 `value`  
 作为投影的 JavaScript 值 `VARIANT` 。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 脚本可以使用预计值从脚本调用 COM 自动化对象。 主机负责强制实施 COM 线程规则。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
