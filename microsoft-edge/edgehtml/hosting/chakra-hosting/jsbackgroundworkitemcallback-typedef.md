---
description: 后台工作项回调。
title: JsBackgroundWorkItemCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: e6db52e1-830c-46a2-b9f9-cc2d450a1da8
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d69306b334c2e0c9b27b96a5a417739ffdcd7dd7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232230"
---
# JsBackgroundWorkItemCallback Typedef

后台工作项回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsBackgroundWorkItemCallback)(  
   _In_opt_ void *callbackData  
);  
```  
  
#### 参数  
 callbackData  
 传递给线程服务的数据参数。  
  
## 备注  
 如果提供此参数，则 (主机的线程服务) 以允许主机在其选择的后台线程上调用工作项回调。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
