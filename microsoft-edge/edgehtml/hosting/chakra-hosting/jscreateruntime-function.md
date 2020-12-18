---
description: 创建新的运行时。
title: JsCreateRuntime 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateRuntime
helpviewer_keywords:
- JsCreateRuntime function
ms.assetid: 92d09b89-6593-4d73-a562-88f9fec10228
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3b893bd75725d6d9da56417ba83adfce18d77bac
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232419"
---
# JsCreateRuntime 函数

创建新的运行时。
  
## 语法  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateRuntime(  
   _In_ JsRuntimeAttributes attributes,  
   _In_ JsRuntimeVersion version,  
   _In_opt_ JsThreadServiceCallback threadService,  
   _Out_ JsRuntimeHandle *runtime  
);  
```  
  
#### 参数  
 `attributes`  
 要创建的运行时的属性。  
  
 `version`  
 要创建的运行时的版本。  
  
 `threadService`  
 运行时的线程服务。 可以是 null。  
  
 `runtime`  
 创建的运行时。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 Microsoft `version` Edge 模式不支持此参数。 有关在 Microsoft Edge 模式下使用此 API 有关详细信息，请参阅"面向 Microsoft Edge 与[旧版引擎"。](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
