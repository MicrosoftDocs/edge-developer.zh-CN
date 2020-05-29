---
description: 在收集对象之前调用的回调。
title: JsObjectBeforeCollectCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: f21a064a-579f-44cb-9d21-76b62e8c18f5
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 27bbd1aed72cc751397ac4e6734f107612653b66
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563080"
---
# JsObjectBeforeCollectCallback Typedef
在收集对象之前调用的回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsObjectBeforeCollectCallback)(  
  _In_ JsRef ref,  
  _In_opt_ void *callbackState  
);  
```  
  
#### 参数  
 `ref`  
 要收集的对象。  
  
 `callbackState`  
 传递到的状态 `JsSetObjectBeforeCollectCallback` 。  
  
## 备注  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)