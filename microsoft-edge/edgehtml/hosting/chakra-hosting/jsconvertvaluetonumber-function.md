---
description: 使用标准 JavaScript 语义将值转换为数字。
title: JsConvertValueToNumber 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsConvertValueToNumber
helpviewer_keywords:
- JsConvertValueToNumber function
ms.assetid: c47b8653-0591-4863-b8b5-33187b315816
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 8d00950ef3835c6d75f8f55ffe5002b32c6ee160
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232220"
---
# JsConvertValueToNumber 函数

使用标准 JavaScript 语义将值转换为数字。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsConvertValueToNumber(  
   _In_ JsValueRef value,  
   _Out_ JsValueRef *numberValue  
);  
```  
  
#### 参数  
 `value`  
 要转换的值。  
  
 `numberValue`  
 转换后的值。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
