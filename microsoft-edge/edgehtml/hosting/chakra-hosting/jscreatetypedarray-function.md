---
description: 创建 JavaScript 类型数组对象。
title: JsCreateTypedArray 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 937a2a91-6f5f-4aaa-a018-d3089702bf36
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 62f62296d81dafe6515f69a990e33ff5c00730e1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232552"
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
 新数组的基准数组。 如果没有 `JS_INVALID_REFERENCE` 基本数组，请使用。  
  
 `byteOffset`  
 结果类型数组从 () `baseArray` `ArrayBuffer` 的偏移量（以字节为单位）。 仅在对象 `baseArray` 适用 `ArrayBuffer` 时适用。 否则必须为 0。  
  
 `elementLength`  
 数组中的元素数。 仅在创建一个新的类型数组（ () `baseArray` `baseArray` `JS_INVALID_REFERENCE` 或对象 `baseArray` `ArrayBuffer` 时适用。 否则必须为 0。  
  
 `result`  
 新的类型数组对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 可以是 `baseArray` 一个 `ArrayBuffer` 、另一个键入的数组或一个 JavaScript `Array` 。 返回的键入的数组将使用 if 它是一个 ，或以其他方式创建和使用基础源数组 `baseArray` `ArrayBuffer` 的副本。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
