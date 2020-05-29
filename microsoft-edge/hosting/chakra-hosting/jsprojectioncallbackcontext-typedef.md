---
description: 传递到应用程序回调、JsProjectionEnqueueCallback、JsRT 的上下文，然后 `JsProjectionCallback` 通过应用程序在正确的线程上传回 JsRT。
title: JsProjectionCallbackContext Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 50c705c5-664f-4a1a-92f6-4882fc718ab1
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 58d4c74da13ae0dd269f3c101bbf3d2b95e77732
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563078"
---
# JsProjectionCallbackContext Typedef
传递到应用程序回调、JsProjectionEnqueueCallback、JsRT 的上下文，然后 `JsProjectionCallback` 通过应用程序在正确的线程上传回 JsRT。  
  
## 语法  
  
```cpp  
typedef void *JsProjectionCallbackContext;  
```  
  
## 备注  
 需要呼叫 `JsSetProjectionEnqueueCallback` 才能接收回拨。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)