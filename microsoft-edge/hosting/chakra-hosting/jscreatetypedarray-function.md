---
description: 创建 JavaScript 类型数组对象。
title: JsCreateTypedArray 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 57c5d15d76bf8b3ff29d10f7500fe41b3e959f68
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563147"
---
# JsCreateTypedArray 函数
创建 JavaScript 类型数组对象。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateTypedArray(  
   _In_ JsTypedArrayType arrayType,  
   _In_ JsValueRef baseArray,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int elementLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `arrayType`  
 要创建的数组的类型。  
  
 `baseArray`  
 新数组的基础数组。 `JS_INVALID_REFERENCE`如果没有基本数组，则使用。  
  
 `byteOffset`  
 从 `baseArray` （）的开头 `ArrayBuffer` 到要引用的结果输入数组的偏移量（以字节为单位）。 仅当是对象时才适用 `baseArray` `ArrayBuffer` 。 否则必须为0。  
  
 `elementLength`  
 数组中的元素数。 仅当创建新的类型化数组而 `baseArray` 不 `baseArray` 使用（is `JS_INVALID_REFERENCE` ）或 `baseArray` 对象时 `ArrayBuffer` 才适用。 否则必须为0。  
  
 `result`  
 新的类型化数组对象。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 `baseArray`可以是 `ArrayBuffer` 、其他类型的数组或 JavaScript `Array` 。 如果返回的类型化数组是，则将使用该数组 `baseArray` `ArrayBuffer` ，或者以其他方式创建并使用基础源数组的副本。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)