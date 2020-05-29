---
description: 设置外部对象上的外部数据。
title: JsSetExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetExternalData
helpviewer_keywords:
- JsSetExternalData function
ms.assetid: 94e0ad34-67d7-4f7f-88a3-3b057ef5e4b9
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: cc638905786a1baa0a3d5f79bfa3792a764f358f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564178"
---
# JsSetExternalData 函数
设置外部对象上的外部数据。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetExternalData(  
   _In_ JsValueRef object,  
   _In_opt_ void *externalData  
);  
```  
  
#### 参数  
 `object`  
 外部对象。  
  
 `externalData`  
 存储在对象中的外部数据。 如果对象中不存储任何外部数据，则可以为 null。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)