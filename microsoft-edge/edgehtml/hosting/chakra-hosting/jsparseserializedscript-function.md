---
description: 分析序列化脚本并返回表示该脚本的函数。
title: JsParseSerializedScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 66ecabb9d96c3f339625f93858444f55d25fd4d7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232532"
---
# JsParseSerializedScript 函数

分析序列化脚本并返回表示该脚本的函数。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `script`  
 要分析的脚本。  
  
 `buffer`  
 序列化脚本。  
  
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
  
 脚本引擎不会将缓冲区持久化到内存中，因此代码必须保持其活动状态，只要它可用于执行脚本。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
