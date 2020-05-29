---
description: 在回收之前调用的回调。
title: JsBeforeCollectCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 17f279c2d2ffcc8d02819994dddebfc22baa4cab
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563199"
---
# JsBeforeCollectCallback Typedef
在回收之前调用的回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsBeforeCollectCallback)(  
_In_opt_ void *callbackState  
);  
```  
  
#### 参数  
 callbackState  
 传递给 JsSetBeforeCollectCallback 的状态。  
  
## 备注  
 使用 JsSetBeforeCollectCallback 注册此回调。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)