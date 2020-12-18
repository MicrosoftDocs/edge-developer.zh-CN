---
description: 在当前上下文中停止分析。
title: JsStopProfiling 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStopProfiling
helpviewer_keywords:
- JsStopProfiling function
ms.assetid: 3639c04f-a0f9-418b-be39-92f64b4e7ef8
caps.latest.revision: 13
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 02c42afda7e61d71b90a9a1a71aa71cc53584ff8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232391"
---
# JsStopProfiling 函数

在当前上下文中停止分析。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsStopProfiling(  
   _In_ HRESULT reason  
);  
```  
  
#### 参数  
 `reason`  
 停止分析以传递到探查器回调的原因。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 如果分析尚未启动，将不会返回错误。  
  
 需要活动脚本上下文。  
  
 此 API 在桌面应用中受支持，但在应用商店应用中不受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
