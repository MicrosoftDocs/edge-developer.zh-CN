---
description: 检索对象的指定索引处的值。
title: JsGetIndexedProperty 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsGetIndexedProperty
helpviewer_keywords:
- JsGetIndexedProperty function
ms.assetid: f61ea388-0ae6-4a19-b3b5-75ed49a3f32d
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 7bb048b841462e27604ab169c69e4c051209a67d
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564252"
---
# JsGetIndexedProperty 函数
检索对象的指定索引处的值。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedProperty(  
   _In_ JsValueRef object,  
   _In_ JsValueRef index,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `object`  
 要操作的对象。  
  
 `index`  
 要检索的索引。  
  
 `result`  
 检索的值。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)