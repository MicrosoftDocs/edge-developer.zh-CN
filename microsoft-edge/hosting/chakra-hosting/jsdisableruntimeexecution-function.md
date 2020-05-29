---
description: 暂停脚本执行并终止运行时中运行的任何脚本。
title: JsDisableRuntimeExecution 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 575947d3038eaa136e9d6ae62507501bc768eabe
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563138"
---
# JsDisableRuntimeExecution 函数
暂停脚本执行并终止运行时中运行的任何脚本。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### 参数  
 `runtime`  
 要暂停的运行时。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 调用挂起的运行时将失败，直到 `JsEnableRuntimeExecution` 调用。  
  
 不必在运行时处于活动状态的线程上调用此 API。 尽管运行时将设置为挂起状态，但可能无法立即挂起正在执行的脚本;将尽快终止正在运行的脚本，并显示 uncatchable 异常。  
  
 在已暂停的运行时中暂停执行是无中断操作。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)