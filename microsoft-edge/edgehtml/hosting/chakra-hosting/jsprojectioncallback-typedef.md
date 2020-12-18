---
description: 应在正确的线程上传递上下文时调用的 JsRT `JsProjectionEnqueueCallback` 回调。
title: JsProjectionCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 211325b536dc84340974b02973f1de9d5749a60a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232527"
---
# JsProjectionCallback Typedef

应在正确的线程上传递上下文时调用的 JsRT `JsProjectionEnqueueCallback` 回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### 参数  
 `jsContext`  
 需要调用 `JsSetProjectionEnqueueCallback` 以接收回调。  
  
## 备注  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
