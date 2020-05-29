---
description: 创建一个 JavaScript 值，该值是传入的投影 `VARIANT` 。
title: JsVariantToValue 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsVariantToValue
helpviewer_keywords:
- JsVariantToValue function
ms.assetid: e8f9eb8b-55b3-4b65-927e-cad5b482edee
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 01796bc38548cf56b500731d899541ef214ec4e3
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563057"
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
 `VARIANT`要投影的。  
  
 `value`  
 作为的投影的 JavaScript 值 `VARIANT` 。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 脚本可以使用投影值从脚本调用 COM 自动化对象。 主机负责强制执行 COM 线程处理规则。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)