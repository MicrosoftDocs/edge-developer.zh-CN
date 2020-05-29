---
description: 应通过传递到正确线程上的上下文调用的 JsRT 回调 `JsProjectionEnqueueCallback` 。
title: JsProjectionCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 32f22d37-e57e-4196-b6cd-a3fc75bd0632
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: b30f9a7dc4671896eeacecbf58ef88f0383e9e7e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563077"
---
# JsProjectionCallback Typedef
应通过传递到正确线程上的上下文调用的 JsRT 回调 `JsProjectionEnqueueCallback` 。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsProjectionCallback)(  
  _In_ JsProjectionCallbackContext jsContext  
);  
```  
  
#### 参数  
 `jsContext`  
 需要呼叫 `JsSetProjectionEnqueueCallback` 才能接收回拨。  
  
## 备注  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)