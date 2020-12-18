---
description: 线程服务回调。
title: JsThreadServiceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5f1fe416e158e9524bdd1caab847977a5dd21b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232352"
---
# JsThreadServiceCallback Typedef

线程服务回调。  
  
## 语法  
  
```cpp  
typedef bool (CALLBACK *JsThreadServiceCallback)(  
   _In_ JsBackgroundWorkItemCallback callback,  
   _In_opt_ void *callbackData  
);  
```  
  
#### 参数  
 回调  
 后台工作项的回调。  
  
 callbackData  
 要传递给回调的数据参数。  
  
## 备注  
 主机可以在调用 JsCreateRuntime 时指定后台线程服务。 如果指定，则后台工作项将使用此回调传递给主机。 主机应立即开始执行后台工作项并返回 true 或返回 false，运行时将在线程中处理工作项。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
