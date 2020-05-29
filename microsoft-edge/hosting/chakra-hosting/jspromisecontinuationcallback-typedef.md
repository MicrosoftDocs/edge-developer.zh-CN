---
description: 承诺延续回调。
title: JsPromiseContinuationCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 023d88af5ff82056d8f57453e0a53b91b34565a6
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563070"
---
# JsPromiseContinuationCallback Typedef
承诺延续回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsPromiseContinuationCallback)(  
  _In_ JsValueRef task,  
  _In_opt_ void *callbackState  
);  
```  
  
#### 参数  
 `task`  
  `callbackState`  
  
## 备注  
 主机可以在中指定承诺延续回调 `JsSetPromiseContinuationCallback` 。 如果脚本创建了一个要在以后运行的任务，则将使用该任务调用承诺延续回调，并且应将任务放在一个 FIFO 队列中，以便在当前脚本完成执行时运行。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)