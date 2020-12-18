---
description: JsValueRef 的 JavaScript 类型。
title: JsValueType 枚举 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueType
helpviewer_keywords:
- JsValueType enumeration
ms.assetid: 6645e723-e554-41fc-b622-ab54ee044b3d
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 840afcde86d4df80490d463921a74c73e42ddfc2
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232348"
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
|`JsNumber`|值为 JavaScript 数字值。|  
|`JsString`|值为 JavaScript 字符串值。|  
|`JsBoolean`|值为 JavaScript 布尔值。|  
|`JsObject`|值为 JavaScript 对象值。|  
|`JsFunction`|值为 JavaScript 函数对象值。|  
|`JsError`|值为 JavaScript 错误对象值。|  
|`JsArray`|值为 JavaScript 数组对象值。|  
|`JsSymbol`|该值是一个 JavaScript 符号值。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsArrayBuffer`|值为 JavaScript `ArrayBuffer` 对象值。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsTypedArray`|该值为 JavaScript 类型数组对象值。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
|`JsDataView`|值为 JavaScript `DataView` 对象值。<br /><br /> 此枚举值仅在 Microsoft Edge 模式下受支持。|  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
