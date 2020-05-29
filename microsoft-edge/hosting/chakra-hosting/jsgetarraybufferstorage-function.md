---
description: 获取 ArrayBuffer 使用的基础内存存储。
title: JsGetArrayBufferStorage 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 712ae298-36a9-47ef-b089-e51835c056bc
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1e8d265f3e81015ba9f5d0547b6b1c7246c23ce5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564263"
---
# JsGetArrayBufferStorage 函数
获取由使用的基础内存存储 `ArrayBuffer` 。  
  
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
 ArrayBuffer 的缓冲区。 返回的缓冲区的生存期与的生存期相同 `ArrayBuffer` 。 对于垃圾回收用途，缓冲区指针不会作为对的引用进行计数 `ArrayBuffer` 。  
  
 `bufferLength`  
 缓冲区中的字节数。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)