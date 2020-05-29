---
description: 返回一个值，该值指示是否在运行时中禁用脚本执行。
title: JsIsRuntimeExecutionDisabled 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIsRuntimeExecutionDisabled
helpviewer_keywords:
- JsIsRuntimeExecutionDisabled function
ms.assetid: 77490280-fb84-4614-a1f0-6ac31e3bd607
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 6968a31c9acab70589fe58c86cc566e631778c3c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563089"
---
# JsIsRuntimeExecutionDisabled 函数
返回一个值，该值指示是否在运行时中禁用脚本执行。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsIsRuntimeExecutionDisabled(    _In_ JsRuntimeHandle runtime,    _Out_ bool *isDisabled);  
```  
  
#### 参数  
 `runtime`  
 指定运行时检查是否已禁用执行。  
  
 `isDisabled`  
 `true` 如果执行被禁用，则 `false` 为。  
  
## 返回值  
 `JsNoError` 如果操作成功，则为失败代码。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)