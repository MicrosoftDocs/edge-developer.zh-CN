---
description: 在集合之前调用的回调。
title: JsBeforeCollectCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 58bece47-4e6d-49e7-a93d-b6a8f9928b41
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 23ed386a6a28d356aa80cf85650a981d4836a6b6
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232221"
---
# JsBeforeCollectCallback Typedef

在集合之前调用的回调。  
  
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
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
