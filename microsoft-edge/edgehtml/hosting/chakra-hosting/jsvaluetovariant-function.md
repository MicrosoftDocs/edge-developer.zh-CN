---
description: 初始化作为 `VARIANT` JavaScript 值的投影传入。
title: JsValueToVariant 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsValueToVariant
helpviewer_keywords:
- JsValueToVariant function
ms.assetid: 070244be-a69d-4b78-971b-69c0579c03cf
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: f383f2d8bc3aab70b4a361b370698cd71cb714d3
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232350"
---
# JsValueToVariant 函数

初始化作为 `VARIANT` JavaScript 值的投影传入。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsValueToVariant(  
   _In_ JsValueRef object,  
   _Out_ VARIANT *variant  
);  
```  
  
#### 参数  
 `object`  
 要作为项目表示的 JavaScript 值 `VARIANT` 。  
  
 `variant`  
 指向将初始化为投影的结构 `VARIANT` 指针。  
  
## 返回值  
  
## 备注  
 COM `VARIANT` 自动化客户端可以使用投影来调用投影的 JavaScript 对象。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
