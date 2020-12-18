---
description: 将 JavaScript 对象解包到 `IInspectable` 指针。
title: JsObjectToInspectable 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 1d15b0b8-516f-4fc6-95aa-2ddd65f8ab75
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 0d818f798805e2afad4dc87b308258464d31bf92
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232529"
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
 应预测到的 JavaScript 值 `IInspectable` 。  
  
 `inspectable`  
 `IInspectable`对象的值。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 主机负责强制实施 COM 线程规则。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
