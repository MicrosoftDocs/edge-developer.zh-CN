---
description: 设置一个回调函数，该函数由运行时在对象的垃圾回收之前调用。
title: JsSetObjectBeforeCollectCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 77a59c6ace96809c0b232c96aa9639555e7badcd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564172"
---
# JsSetObjectBeforeCollectCallback 函数
设置一个回调函数，该函数由运行时在对象的垃圾回收之前调用。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSetObjectBeforeCollectCallback(  
   _In_ JsRef ref,  
   _In_opt_ void *callbackState,  
   _In_ JsObjectBeforeCollectCallback objectBeforeCollectCallback  
);  
```  
  
#### 参数  
 `ref`  
 要为其注册回调的对象。  
  
 `callbackState`  
 用户提供的状态将传回回调。  
  
 `objectBeforeCollectCallback`  
 正在设置的回调函数。 使用 null 清除以前注册的回调。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 回调将在当前运行时执行线程上调用，因此执行会被阻止，直到回调完成。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)