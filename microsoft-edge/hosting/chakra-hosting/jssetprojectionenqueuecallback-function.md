---
description: 设置要使用的回调，以便将投影完成调用回调用方所需的线程。
title: JsSetProjectionEnqueueCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: c751ccef-20d2-4d41-9568-1c54adf47cdf
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 02da0238360b0dc6fff9bb86c9f5ab04d1ba7112
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564168"
---
# JsSetProjectionEnqueueCallback 函数
设置要使用的回调，以便将投影完成调用回调用方所需的线程。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetProjectionEnqueueCallback(  
   _In_ JsProjectionEnqueueCallback projectionEnqueueCallback,  
   _In_opt_ void *projectionEnqueueContext);  
  
```  
  
#### 参数  
 `projectionEnqueueContext`  
 任何时候在后台线程上发生投影完成时将调用的回调。  
  
 `callbackState`  
 提供给的应用程序上下文 `projectionEnqueueContext` 。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 该调用应来自不同的 COM 单元或来自同一 MTA 中的不同线程。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
> [!CAUTION]
>  此 API 目前不支持 PInvoke。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)