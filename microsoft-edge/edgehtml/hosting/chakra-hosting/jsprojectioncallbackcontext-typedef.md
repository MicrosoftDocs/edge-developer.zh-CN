---
description: 从 JsRT 传递到应用程序回调 JsProjectionEnqueueCallback 的上下文，然后由正确线程上的应用程序在提供的回调中传递回 `JsProjectionCallback` JsRT。
title: JsProjectionCallbackContext Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 7742b0186a49e99f2738b81357b9e55cfe00042b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232523"
---
# JsProjectionCallbackContext Typedef

从 JsRT 传递到应用程序回调 JsProjectionEnqueueCallback 的上下文，然后由正确线程上的应用程序在提供的回调中传递回 `JsProjectionCallback` JsRT。  
  
## 语法  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## 备注  
 需要调用 `JsSetProjectionEnqueueCallback` 以接收回调。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
