---
description: 创建新的 JavaScript ReferenceError error 对象。
title: JsCreateReferenceError 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsCreateReferenceError
helpviewer_keywords:
- JsCreateReferenceError function
ms.assetid: 1d0b2339-4bea-4dd0-a46a-4dcbf0be3bd8
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 958af7111a233077aa7a2c2391b26666f55c634b
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563157"
---
# JsCreateReferenceError 函数
创建新的 JavaScript ReferenceError error 对象。
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateReferenceError(  
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
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)