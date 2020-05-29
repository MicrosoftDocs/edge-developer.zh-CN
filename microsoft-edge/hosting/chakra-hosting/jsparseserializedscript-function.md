---
description: 分析序列化脚本并返回表示脚本的函数。
title: JsParseSerializedScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsParseSerializedScript
helpviewer_keywords:
- JsParseSerializedScript function
ms.assetid: 40d0c7c4-fd5b-46ed-9e65-38c2db2fc859
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: a778a007e69f15063d23cc55f999144ab55a306c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564216"
---
# JsParseSerializedScript 函数
分析序列化脚本并返回表示脚本的函数。  
  
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
 标识可由可调试脚本上下文使用的脚本的 cookie。  
  
 `sourceUrl`  
 脚本的来源位置。  
  
 `result`  
 表示脚本代码的函数。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 脚本引擎不会将缓冲区保留在内存中，因此你的代码必须保持活动状态，因为它可能会用于执行脚本。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)