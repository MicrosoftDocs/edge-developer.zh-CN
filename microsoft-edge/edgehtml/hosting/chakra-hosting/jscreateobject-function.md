---
description: 创建新的对象。
title: JsCreateObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateObject
helpviewer_keywords:
- JsCreateObject function
ms.assetid: 6c1d01a4-9254-443e-b974-6f0b0c861ca2
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d5effe7ade1679392fcad7f2bb5cea880712ef7f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232339"
---
# JsCreateObject 函数

创建新的对象。
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateObject(  
   _Out_ JsValueRef *object  
);  
```  
  
#### 参数  
 `object`  
 新对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
