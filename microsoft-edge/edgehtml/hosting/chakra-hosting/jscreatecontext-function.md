---
description: 创建用于运行脚本的脚本上下文。
title: JsCreateContext 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsCreateContext
helpviewer_keywords:
- JsCreateContext function
ms.assetid: aceca043-2c73-4029-a06c-8ad6695109cf
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5d6c8149b8a5e5fee7cbc8dac821713b1d9649ee
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232200"
---
# JsCreateContext 函数

创建用于运行脚本的脚本上下文。  
  
## 语法  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _Out_ JsContextRef *newContext);  
  
// Legacy mode signature  
STDAPI_(JsErrorCode) JsCreateContext(  
   _In_ JsRuntimeHandle runtime,  
   _In_ IDebugApplication *debugApplication,  
   _Out_ JsContextRef *newContext  
);  
```  
  
#### 参数  
 `runtime`  
 创建脚本上下文的运行时。  
  
 `debugApplication`  
 用于调试的调试应用程序。 此参数可以是 null，在这种情况下，未为上下文启用调试。  
  
 `newContext`  
 已创建的脚本上下文。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 每个脚本上下文都有自己的全局对象，该对象独立于所有其他脚本上下文。  
  
 Microsoft `debugApplication` Edge 模式不支持此参数。 有关在 Microsoft Edge 模式下使用此 API 有关详细信息，请参阅"面向 Microsoft Edge 与[旧版引擎"。](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
