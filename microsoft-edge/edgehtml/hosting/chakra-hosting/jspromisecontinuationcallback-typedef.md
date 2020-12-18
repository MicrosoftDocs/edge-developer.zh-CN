---
description: 承诺延续回调。
title: JsPromiseContinuationCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 51a3fd02-9668-4cf7-bb0b-e1fd03b2528f
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da121d186cd9d0ab1a9770be08c9a92b52cf3366
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232760"
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
 主机可以在 中指定承诺延续回调 `JsSetPromiseContinuationCallback` 。 如果脚本创建要稍后运行的任务，则承诺延续回调将随任务一起调用，并且该任务应放入 FIFO 队列中，以在当前脚本执行完成时运行。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
