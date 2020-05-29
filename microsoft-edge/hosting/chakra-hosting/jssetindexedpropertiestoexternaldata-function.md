---
description: 将对象的索引属性设置为外部数据。 外部数据将用作对象的索引属性的 back store，并像类型化数组一样进行访问。
title: JsSetIndexedPropertiesToExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c1aed6e194b1dc1c35f403626a7b6c02a7752ffb
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564175"
---
# JsSetIndexedPropertiesToExternalData 函数
将对象的索引属性设置为外部数据。 外部数据将用作对象的索引属性的 back store，并像类型化数组一样进行访问。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetIndexedPropertiesToExternalData(  
   _In_ JsValueRef object,  
   _In_ void* data,  
   _In_ JsTypedArrayType arrayType,  
   _In_ unsigned int elementLength  
);  
```  
  
#### 参数  
 `object`  
 要操作的对象。  
  
 `data`  
 要用作对象的索引属性的 back store 的外部数据。  
  
 `arrayType`  
 外部数据中的数组元素类型。  
  
 `elementLength`  
 外部数据中数组元素的数量。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)