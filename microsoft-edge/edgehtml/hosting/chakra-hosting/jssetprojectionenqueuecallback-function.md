---
description: 设置要用于将投影完成调用回调用方所需线程的回调。
title: JsSetProjectionEnqueueCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7dfedfeb1df5a97159a211795a2dd072d239bb35
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232181"
---
# JsSetProjectionEnqueueCallback 函数

设置要用于将投影完成调用回调用方所需线程的回调。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### 参数  
 `projectionEnqueueContext`  
 每次在后台线程上执行投影完成时将调用的回调。  
  
 `callbackState`  
 提供给的应用程序上下文 `projectionEnqueueContext` 。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 该调用应来自不同的 COM 单元或来自同一 MTA 中的不同线程。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
> [!CAUTION]
>  此 API 当前不支持 PInvoke。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
