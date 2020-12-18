---
description: 创建新的 JavaScript 错误对象。
title: JsCreateError 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateError
helpviewer_keywords:
- JsCreateError function
ms.assetid: dadbcac8-c56f-4f30-ba00-2d284daee191
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cd2fd0172902cc6dc8a4dd169eef5947d0b25256
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232199"
---
# JsCreateError 函数

创建新的 JavaScript 错误对象。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateError(  
   _In_ JsValueRef message,  
   _Out_ JsValueRef *error  
);  
```  
  
#### 参数  
 `message`  
 错误对象的消息。  
  
 `error`  
 新的错误对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
