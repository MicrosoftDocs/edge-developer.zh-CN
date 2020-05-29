---
description: 获取类型化数组使用的基础内存存储。
title: JsGetTypedArrayStorage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 52e4ac5f-cc71-456d-95de-a48f7327503d
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: f03414d64fa819ac464217c8362d02e866d45296
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564243"
---
# JsGetTypedArrayStorage 函数
获取类型化数组使用的基础内存存储。  
  
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
 类型化数组实例。  
  
 `buffer`  
 数组的缓冲区。 返回的缓冲区的生存期与数组的生存期相同。 由于垃圾回收的目的，缓冲区指针不会作为数组的引用计数。  
  
 `bufferLength`  
 缓冲区中的字节数。  
  
 `arrayType`  
 数组的类型。  
  
 `elementSize`  
 数组元素的大小。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)