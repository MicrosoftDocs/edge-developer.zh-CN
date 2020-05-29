---
description: 检索字符串值的字符串指针。
title: JsStringToPointer 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1f5997894c4ea479378a323b230492dde28ab177
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564070"
---
# JsStringToPointer 函数
检索字符串值的字符串指针。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsStringToPointer(  
   _In_ JsValueRef value,  
   _Outptr_result_buffer_(*stringLength) const wchar_t **stringValue,  
   _Out_ size_t *stringLength  
);  
```  
  
#### 参数  
 `value`  
 要转换为字符串指针的字符串值。  
  
 `stringValue`  
 字符串指针。  
  
 `stringLength`  
 字符串的长度。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 此函数检索字符串值的字符串指针。 `JsErrorInvalidArgument`如果值的类型不是字符串，它将失败。 返回的字符串的生存期将与它所来自的值的生存期相同，但字符串指针不会被视为对值的引用（因此将不会阻止回收它）。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)