---
description: 指示运行时执行所需的任何空闲处理。
title: JsIdle 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ecba0aafb6b4dcccb4485c2956cae5ce4045355f
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232711"
---
# JsIdle 函数

指示运行时执行所需的任何空闲处理。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### 参数  
 `nextIdleTick`  
 下一个系统在将有更多的空闲工作时进行计时。 可以是 null。 如果没有即将进行的空闲工作，则返回最大刻度数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 如果当前运行时已启用空闲处理，调用将通知当前运行时主机处于空闲状态，并且该运行时 `JsIdle` 可以执行内存清理任务。  
  
 `JsIdle` 还可以返回系统刻度数，直到运行时有更多的空闲工作需要执行。 在 `JsIdle` 经过此数量的刻度之前调用将不起作用。  
  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
