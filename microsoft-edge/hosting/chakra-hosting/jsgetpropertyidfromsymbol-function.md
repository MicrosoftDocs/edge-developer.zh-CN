---
description: 获取与该符号关联的属性 ID。
title: JsGetPropertyIdFromSymbol 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 190fe4b9-352e-4b10-9d0e-6c6bbd6363e8
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 0d11dbaf25b85e2bcd85a0cf2bac1b499fd4fa3e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564246"
---
# JsGetPropertyIdFromSymbol 函数
获取与该符号关联的属性 ID。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetPropertyIdFromSymbol(  
   _In_ JsValueRef symbol,  
   _Out_ JsPropertyIdRef *propertyId  
);  
```  
  
#### 参数  
 `symbol`  
 正在检索其属性 ID 的符号。  
  
 `propertyId`  
 给定符号的属性 ID。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 属性 Id 特定于上下文，不能跨上下文使用。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)