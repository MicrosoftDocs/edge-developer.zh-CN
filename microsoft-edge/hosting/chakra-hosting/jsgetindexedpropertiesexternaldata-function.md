---
description: 检索对象的索引属性外部数据信息。
title: JsGetIndexedPropertiesExternalData 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 2c313163-3462-42fd-8dee-3dfb3ac7f43f
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 96fdcd4b6fe29ffc20a796983cc1de692c80a3f1
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563119"
---
# JsGetIndexedPropertiesExternalData 函数
检索对象的索引属性外部数据信息。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsGetIndexedPropertiesExternalData(  
   _In_ JsValueRef object,  
   _Out_ void** data,  
   _Out_ JsTypedArrayType* arrayType,  
   _Out_ unsigned int* elementLength  
);  
```  
  
#### 参数  
 `object`  
 该对象。  
  
 `data`  
 对象的索引属性的外部数据后置存储。  
  
 `arrayType`  
 外部数据中的数组元素类型。  
  
 `elementLength`  
 外部数据中数组元素的数量。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)