---
description: 运行序列化脚本。
title: JsRunSerializedScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsRunSerializedScript
helpviewer_keywords:
- JsRunSerializedScript function
ms.assetid: 3fd3f6f1-eb3e-4751-92a5-c93b1035f3b2
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 46f293d76bf0944c1cdedae917735c505798f4ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232695"
---
# JsRunSerializedScript 函数

运行序列化脚本。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScript(  
   _In_z_ const wchar_t *script,  
   _In_ BYTE *buffer,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `script`  
 序列化脚本的源代码。  
  
 `buffer`  
 序列化脚本。  
  
 `sourceContext`  
 用于标识可调试脚本上下文使用的脚本的 Cookie。  
  
 `sourceUrl`  
 脚本来自的位置。  
  
 `result`  
 运行脚本的结果（如果有）。 此参数可以是 null。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 脚本引擎不会将缓冲区持久化到内存中，因此代码必须保持其活动状态，只要它可用于执行脚本。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
