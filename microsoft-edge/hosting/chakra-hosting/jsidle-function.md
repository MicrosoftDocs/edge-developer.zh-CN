---
description: 通知运行时执行需要执行的任何空闲处理。
title: JsIdle 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsIdle
helpviewer_keywords:
- JsIdle function
ms.assetid: 372d1c62-8e19-4886-aa33-364cabc09bba
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 4da7148bf7daa3db983ab8f5bba622bfe0b19466
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564224"
---
# JsIdle 函数
通知运行时执行需要执行的任何空闲处理。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsIdle(  
   _Out_opt_ unsigned int *nextIdleTick  
);  
```  
  
#### 参数  
 `nextIdleTick`  
 当有更多空闲工作需要执行时，下一个系统将勾选。 可以为 null。 如果没有即将进行的空闲工作要执行，则返回最大刻度数。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 如果当前运行时已启用空闲处理，则调用 `JsIdle` 将通知当前运行时主机处于空闲状态，并且运行时可以执行内存清理任务。  
  
 `JsIdle` 还可以返回系统计时周期数，直到有运行时需要执行的更多空闲工作。 `JsIdle`此滴答数过去的通话将不起作用。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)