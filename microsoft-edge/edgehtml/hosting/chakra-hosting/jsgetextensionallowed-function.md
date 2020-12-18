---
description: 返回一个值，该值指示对象是否可扩展。
title: JsGetExtensionAllowed 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsGetExtensionAllowed
helpviewer_keywords:
- JsGetExtensionAllowed function
ms.assetid: 839054a1-d643-47d9-89db-6a015bba0d91
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7bc9e3265b48a27d0da4bc4646b2b5e3b1765b86
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232445"
---
# JsGetExtensionAllowed 函数

返回一个值，该值指示对象是否可扩展。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetExtensionAllowed(  
   _In_ JsValueRef object,  
   _Out_ bool *value  
);  
```  
  
#### 参数  
 `object`  
 要测试的对象。  
  
 `value`  
 对象是否可扩展。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
