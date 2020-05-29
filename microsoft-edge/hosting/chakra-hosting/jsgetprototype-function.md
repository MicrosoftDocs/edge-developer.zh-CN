---
description: 返回对象的原型。
title: JsGetPrototype 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetPrototype
helpviewer_keywords:
- JsGetPrototype function
ms.assetid: 05d743fc-103e-4a92-86f2-a063f39a2a6f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 12708634fea9e8f9fd1205514845b1cb9760ee9e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563115"
---
# JsGetPrototype 函数
返回对象的原型。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPrototype(  
   _In_ JsValueRef object,  
   _Out_ JsValueRef *prototypeObject  
);  
```  
  
#### 参数  
 `object`  
 要返回其原型的对象。  
  
 `prototypeObject`  
 对象的原型。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)