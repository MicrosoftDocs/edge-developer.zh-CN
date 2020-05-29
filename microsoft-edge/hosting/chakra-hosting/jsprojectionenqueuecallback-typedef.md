---
description: 当投影 API 在与原始线程不同的线程上完成时，由 JsRT 调用的应用程序回调。
title: JsProjectionEnqueueCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 064a7d1077ae5222e44ab08ebe0592bb97b1f2af
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563076"
---
# JsProjectionEnqueueCallback Typedef
当投影 API 在与原始线程不同的线程上完成时，由 JsRT 调用的应用程序回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsProjectionEnqueueCallback)(  
  _In_ JsProjectionCallback jsCallback,  
  _In_ JsProjectionCallbackContext jsContext,  
  _In_opt_ void *callbackState  
);  
```  
  
#### 参数  
 `jsCallback`  
 要在原始线程上调用的回调。  
  
 `jsContext`  
 应用程序上下文。  
  
 `callbackState`  
 必须传递到的 JsRT 上下文 `jsCallback` 。  
  
## 备注  
 需要调用 JsSetProjectionEnqueueCallback 才能接收回调。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)