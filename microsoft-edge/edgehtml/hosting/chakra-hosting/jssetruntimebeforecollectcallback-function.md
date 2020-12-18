---
description: '设置垃圾回收前运行时调用的回调函数。 '
title: JsSetRuntimeBeforeCollectCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 94ad29fcfb778fc630d70664f917c6b5c2637dde
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232186"
---
# JsSetRuntimeBeforeCollectCallback 函数

设置垃圾回收前运行时调用的回调函数。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetRuntimeBeforeCollectCallback(  
   _In_ JsRuntimeHandle runtime,  
   _In_opt_ void *callbackState,  
   _In_ JsBeforeCollectCallback beforeCollectCallback  
);  
```  
  
#### 参数  
 `runtime`  
 要注册其分配回调的运行时。  
  
 `callbackState`  
 用户提供的状态将传递回回调。  
  
 `beforeCollectCallback`  
 正在设置的回调函数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 在当前运行时执行线程上调用回调，因此在回调完成之前将阻止执行。  
  
 主机可以使用回调来准备垃圾回收。 例如，通过释放对 Chakra 对象不必要的引用。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
