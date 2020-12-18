---
description: 分析脚本并返回表示该脚本的函数。
title: JsParseScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseScript
helpviewer_keywords:
- JsParseScript function
ms.assetid: e9d0e363-7cbe-43eb-9dc0-1f47e586c9ab
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 656d9a992868a3cb892808775f160092b8eaf069
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232533"
---
# JsParseScript 函数

分析脚本并返回表示该脚本的函数。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsParseScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `script`  
 要分析的脚本。  
  
 `sourceContext`  
 用于标识可调试脚本上下文使用的脚本的 Cookie。  
  
 `sourceUrl`  
 脚本来自的位置。  
  
 `result`  
 一个代表脚本代码的函数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
