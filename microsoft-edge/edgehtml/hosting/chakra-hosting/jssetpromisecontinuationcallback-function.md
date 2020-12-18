---
description: 设置一个承诺延续回调函数，该函数在任务需要排队等待将来执行时由上下文调用。
title: JsSetPromiseContinuationCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 6ef0faf4-1500-4bd9-aeca-c208492af8ea
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: da928431f05831c95d5bc116dbd129de9cb5f3b4
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232436"
---
# JsSetPromiseContinuationCallback 函数

设置一个承诺延续回调函数，该函数在任务需要排队等待将来执行时由上下文调用。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetPromiseContinuationCallback(  
   _In_ JsPromiseContinuationCallback promiseContinuationCallback,  
   _In_opt_ void *callbackState  
);  
```  
  
#### 参数  
 `promiseContinuationCallback`  
 正在设置的回调函数。  
  
 `callbackState`  
 用户提供的状态将传递回回调。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
