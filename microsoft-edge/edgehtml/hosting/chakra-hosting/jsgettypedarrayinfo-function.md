---
description: 获取类型数组的常用属性。
title: JsGetTypedArrayInfo 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 992bc4e9-3d06-4ad2-8b6b-88a437360f81
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fdc9a05a2aebdabfd0c8e95c848d3bd5f97e580a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232565"
---
# JsGetTypedArrayInfo 函数

获取类型数组的常用属性。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetTypedArrayInfo(  
  _In_ JsValueRef typedArray,  
  _Out_opt_ JsTypedArrayType *arrayType,  
  _Out_opt_ JsValueRef *arrayBuffer,  
  _Out_opt_ unsigned int *byteOffset,  
  _Out_opt_ unsigned int *byteLength  
);  
  
```  
  
#### 参数  
 `typedArray`  
 键入的数组实例。  
  
 `arrayType`  
 数组的类型。  
  
 `arrayBuffer`  
 `ArrayBuffer`数组的后端存储。  
  
 `byteOffset`  
 从数组引用的 arrayBuffer 开始的偏移量（以字节为单位）。  
  
 `byteLength`  
 数组中的字节数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
