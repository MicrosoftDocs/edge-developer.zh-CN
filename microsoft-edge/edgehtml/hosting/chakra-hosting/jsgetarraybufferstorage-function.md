---
description: 获取 ArrayBuffer 使用的基础内存存储。
title: JsGetArrayBufferStorage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 64b031a81506e68322759eff49da7467cac6f219
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232325"
---
# JsGetArrayBufferStorage 函数

获取由 . `ArrayBuffer`  
  
## 语法  
  
```cpp  
JsErrorCode STDAPI_ JsGetArrayBufferStorage(  
   _In_ JsValueRef arrayBuffer,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength  
);  
```  
  
#### 参数  
 `arrayBuffer`  
 ArrayBuffer 实例。  
  
 `buffer`  
 ArrayBuffer 的缓冲区。 返回的缓冲区的生存期与 `ArrayBuffer` 出于垃圾回收目的，缓冲区指针 `ArrayBuffer` 不计数为对它的引用。  
  
 `bufferLength`  
 缓冲区中的字节数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
