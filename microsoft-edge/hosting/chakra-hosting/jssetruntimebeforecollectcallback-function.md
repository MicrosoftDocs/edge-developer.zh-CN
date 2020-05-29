---
description: '设置在垃圾回收之前由运行时调用的回调函数。 '
title: JsSetRuntimeBeforeCollectCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSetRuntimeBeforeCollectCallback
helpviewer_keywords:
- JsSetRuntimeBeforeCollectCallback function
ms.assetid: 7b2fb911-6007-4ed9-a307-66cefe590ea4
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 31aefd28698c14a6fe17421a990a7c8b120876bf
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564075"
---
# JsSetRuntimeBeforeCollectCallback 函数
设置在垃圾回收之前由运行时调用的回调函数。  
  
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
 要注册分配回调的运行时。  
  
 `callbackState`  
 用户提供的状态将传回回拨。  
  
 `beforeCollectCallback`  
 正在设置的回调函数。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 回调将在当前运行时执行线程上调用，因此执行会被阻止，直到回调完成。  
  
 主机可使用回调准备垃圾回收。 例如，通过释放 Chakra 对象上的不必要的引用。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)