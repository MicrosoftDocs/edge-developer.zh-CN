---
description: 暂停脚本执行并终止运行时中任何正在运行的脚本。
title: JsDisableRuntimeExecution 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsDisableRuntimeExecution
helpviewer_keywords:
- JsDisableRuntimeExecution function
ms.assetid: 4bd4670a-a9da-4f8c-b3fd-1fd366d915c3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 6a08e6a7f89c724f8cf1a73afd97d2cb23c0334e
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232401"
---
# JsDisableRuntimeExecution 函数

暂停脚本执行并终止运行时中任何正在运行的脚本。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsDisableRuntimeExecution(  
   _In_ JsRuntimeHandle runtime  
);  
```  
  
#### 参数  
 `runtime`  
 要挂起的运行时。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 调用暂停的运行时将失败，直到 `JsEnableRuntimeExecution` 被调用。  
  
 无需在运行时处于活动状态的线程上调用此 API。 尽管运行时将设置为挂起状态，但执行脚本可能不会立即挂起;正在运行的脚本将尽快终止，并出现不可捕获的异常。  
  
 在已暂停的运行时中暂停执行是无操作。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
