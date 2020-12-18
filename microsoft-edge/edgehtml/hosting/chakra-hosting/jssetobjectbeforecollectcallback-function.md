---
description: 设置一个回调函数，该函数在对象垃圾回收之前由运行时调用。
title: JsSetObjectBeforeCollectCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: ea2cbd94-d8b0-4fa9-a4a1-c75a4e338eaf
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 4689184dccaf6bc9f98eeacda5f5a4b91a927d40
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232185"
---
# JsSetObjectBeforeCollectCallback 函数

设置一个回调函数，该函数在对象垃圾回收之前由运行时调用。  
  
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
 要注册回调的对象。  
  
 `callbackState`  
 将传递回回调的用户提供的状态。  
  
 `objectBeforeCollectCallback`  
 正在设置的回调函数。 使用 null 清除以前注册的回调。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 在当前运行时执行线程上调用回调，因此在回调完成之前将阻止执行。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
