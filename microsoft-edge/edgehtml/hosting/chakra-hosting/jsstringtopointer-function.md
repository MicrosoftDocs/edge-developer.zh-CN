---
description: 检索字符串值的字符串指针。
title: JsStringToPointer 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStringToPointer
helpviewer_keywords:
- JsStringToPointer function
ms.assetid: c7aa7a09-489d-4435-8f8a-aeb62f8875ae
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 77b8e16be41d8b5541129b50fa200b947f566342
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232354"
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
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 此函数检索字符串值的字符串指针。 如果值的类型不是字符串，它将 `JsErrorInvalidArgument` 失败。 返回的字符串的生存期与它所返回值的生存期相同，但字符串指针不会被视为对值 (的引用，因此不会阻止从) 。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
