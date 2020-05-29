---
description: 使用标准 JavaScript 语义将值转换为字符串。
title: JsConvertValueToString 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToString
helpviewer_keywords:
- JsConvertValueToString function
ms.assetid: a97aca04-b2ce-446a-acf4-49cd6777a85c
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 21c77ca3050773c07572665c6d58e0ebc05d8ee9
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563180"
---
# JsConvertValueToString 函数
使用标准 JavaScript 语义将值转换为字符串。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToString(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *stringValue  
);  
```  
  
#### 参数  
 `value`  
 要转换的值。  
  
 `stringValue`  
 已转换的值。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)