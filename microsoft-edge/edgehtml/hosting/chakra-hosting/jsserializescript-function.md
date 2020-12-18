---
description: 将已分析的脚本序列化为缓冲区，而不是重复使用。
title: JsSerializeScript 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 236cf40c91256e999d5390acd395b1e97fe538ad
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232708"
---
# JsSerializeScript 函数

将已分析的脚本序列化为缓冲区，而不是重复使用。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### 参数  
 `script`  
 要序列化的脚本。  
  
 `buffer`  
 要放入序列化脚本的缓冲区。 可以是 null。  
  
 `bufferSize`  
 进入时，缓冲区的大小（以字节为单位）;退出时，保留序列化脚本所需的缓冲区大小（以字节为单位）。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 `JsSerializeScript` 分析脚本，然后以独立于运行时的格式存储脚本的已分析形式。 然后，可以在任何运行时中对序列化脚本进行反序列化，而无需重新分析该脚本。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
