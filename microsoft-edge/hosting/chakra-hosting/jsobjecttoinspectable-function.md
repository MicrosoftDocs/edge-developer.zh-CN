---
description: 将 JavaScript 对象解包到 `IInspectable` 指针。
title: JsObjectToInspectable 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c7127e1cf1372020e0df00b81ed172739379426f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564221"
---
# JsObjectToInspectable 函数
将 JavaScript 对象解包到 `IInspectable` 指针。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsObjectToInspectable(  
   _In_ JsValueRef value,  
   _Out_ IInspectable  **inspectable  
);  
```  
  
#### 参数  
 `value`  
 应投影到的 JavaScript 值 `IInspectable` 。  
  
 `inspectable`  
 `IInspectable`对象的值。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 主机负责强制执行 COM 线程处理规则。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)