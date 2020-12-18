---
description: '启用运行时中的脚本执行。 '
title: JsEnableRuntimeExecution 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsEnableRuntimeExecution
helpviewer_keywords:
- JsEnableRuntimeExecution function
ms.assetid: daa2036b-aef6-497d-a8ce-5a006b6ed13f
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: e87191197f70898b2f69d138026edd4e75cd5114
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232398"
---
# JsEnableRuntimeExecution 函数

启用运行时中的脚本执行。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsEnableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### 参数  
 `runtime`  
 要启用的运行时。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 在已启用脚本执行的运行时中启用脚本执行是无操作。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
