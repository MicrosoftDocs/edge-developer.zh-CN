---
description: 当投影 API 在不同于原始线程的线程上完成时由 JsRT 调用的应用程序回调。
title: JsProjectionEnqueueCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 19c1cefb-a7be-4196-b780-9fe6adf35ba5
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 47527d5e32076e40a82ab5452c2e0f624e8a2818
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232762"
---
# JsProjectionEnqueueCallback Typedef

当投影 API 在不同于原始线程的线程上完成时由 JsRT 调用的应用程序回调。  
  
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
 在原始线程上调用的回调。  
  
 `jsContext`  
 应用程序上下文。  
  
 `callbackState`  
 必须传递到的 JsRT 上下文 `jsCallback` 。  
  
## 备注  
 需要调用 JsSetProjectionEnqueueCallback 以接收回调。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
