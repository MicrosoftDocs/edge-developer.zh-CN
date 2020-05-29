---
description: 线程服务回调。
title: JsThreadServiceCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dbe67be5-418a-4f66-8b68-b38078a6d140
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5eb9f2986c79db024f01f4d22050f79c9689400c
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563068"
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
 要传递到回调的数据参数。  
  
## 备注  
 主机可以在调用 JsCreateRuntime 时指定后台线程服务。 如果已指定，则后台工作项将使用此回调传递到主机。 主机应立即开始执行后台工作项，并返回 true 或返回 false，并且运行时将处理线程中的工作项。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)