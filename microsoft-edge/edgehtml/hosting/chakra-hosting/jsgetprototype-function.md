---
description: 返回对象的原型。
title: JsGetPrototype 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetPrototype
helpviewer_keywords:
- JsGetPrototype function
ms.assetid: 05d743fc-103e-4a92-86f2-a063f39a2a6f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d64e8b090753e5d0627f0d40ee8745eeadd65227
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232697"
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
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
