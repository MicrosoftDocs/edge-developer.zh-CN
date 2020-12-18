---
description: 将对象的索引属性设置到外部数据。 外部数据将用作对象的索引属性的后端存储，并像类型数组一样访问。
title: JsSetIndexedPropertiesToExternalData 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: cee2d86d-ed42-4acb-86ef-95a67e63d0d6
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: fa0eba3659c20066913cd42a0a18dd5ffe5f857f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232184"
---
# JsSetIndexedPropertiesToExternalData 函数

将对象的索引属性设置到外部数据。 外部数据将用作对象的索引属性的后端存储，并像类型数组一样访问。  
  
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
 要用作对象索引属性的后端存储的外部数据。  
  
 `arrayType`  
 外部数据中的数组元素类型。  
  
 `elementLength`  
 外部数据中的数组元素数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
