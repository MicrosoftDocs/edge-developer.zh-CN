---
description: JsValueRef 的 JavaScript 类型。
title: JsValueType 枚举 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c42231525b55b49f0931a2ace33b373e0d4ae441
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563060"
---
# JsValueType 枚举
JsValueRef 的 JavaScript 类型。  
  
## 语法  
  
```cpp  
enum JsValueType {  
    JsUndefined      = 0,  
    JsNull           = 1,  
    JsNumber         = 2,  
    JsString         = 3,  
    JsBoolean        = 4,  
    JsObject         = 5,  
    JsFunction       = 6,  
    JsError          = 7,  
    JsArray          = 8,  
    JsSymbol         = 9,  
    JsArrayBuffer    = 10,  
    JsTypedArray     = 11,  
    JsDataView       = 12,  
};  
```  
  
## 成员  
  
### 值  
  
|名称|描述|  
|----------|-----------------|  
|`JsUndefined`|值为 `undefined` 值。|  
|`JsNull`|值为 `null` 值。|  
|`JsNumber`|该值是一个 JavaScript 数字值。|  
|`JsString`|该值是一个 JavaScript 字符串值。|  
|`JsBoolean`|该值是一个 JavaScript 布尔值。|  
|`JsObject`|该值是 JavaScript 对象值。|  
|`JsFunction`|该值是 JavaScript 函数对象值。|  
|`JsError`|该值是 JavaScript 错误对象值。|  
|`JsArray`|该值是一个 JavaScript 数组对象值。|  
|`JsSymbol`|该值是一个 JavaScript 符号值。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsArrayBuffer`|该值是 JavaScript `ArrayBuffer` 对象值。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsTypedArray`|该值是一个 JavaScript 类型的数组对象值。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
|`JsDataView`|该值是 JavaScript `DataView` 对象值。<br /><br /> 仅在 Microsoft Edge 模式下支持此枚举值。|  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)