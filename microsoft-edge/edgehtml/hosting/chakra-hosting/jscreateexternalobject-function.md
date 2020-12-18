---
description: 创建一个存储一些外部数据的新对象。
title: JsCreateExternalObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateExternalObject
helpviewer_keywords:
- JsCreateExternalObject function
ms.assetid: 6bcef506-93fb-429b-b06a-a971ff0b71f3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4d402c3d379a16186daaba601c7f830c53a9a953
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232712"
---
# JsCreateExternalObject 函数

创建一个存储一些外部数据的新对象。
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalObject(  
   _In_opt_ void *data,  
   _In_opt_ JsFinalizeCallback finalizeCallback,  
   _Out_ JsValueRef *object  
);  
```  
  
#### 参数  
 `data`  
 对象将表示的外部数据。 可能为空。  
  
 `finalizeCallback`  
 对象完成时回调。 可能为空。  
  
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
