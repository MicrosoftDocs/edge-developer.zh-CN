---
description: 获取类型数组使用的基础内存存储。
title: JsGetTypedArrayStorage 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 442727228433368de14bac528ea416fcc2a95fa8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232062"
---
# JsGetTypedArrayStorage 函数

获取类型数组使用的基础内存存储。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayStorage(  
   _In_ JsValueRef typedArray,  
   _Outptr_result_bytebuffer_(*bufferLength) BYTE **buffer,  
   _Out_ unsigned int *bufferLength,  
   _Out_opt_ JsTypedArrayType *arrayType,  
   _Out_opt_ int *elementSize  
);  
```  
  
#### 参数  
 `typedArray`  
 键入的数组实例。  
  
 `buffer`  
 数组的缓冲区。 返回的缓冲区的生存期与数组的生存期相同。 出于垃圾回收目的，缓冲区指针不计数为对数组的引用。  
  
 `bufferLength`  
 缓冲区中的字节数。  
  
 `arrayType`  
 数组的类型。  
  
 `elementSize`  
 数组元素的大小。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
