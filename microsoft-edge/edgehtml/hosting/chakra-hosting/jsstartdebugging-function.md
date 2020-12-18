---
description: 在当前上下文中开始调试。
title: JsStartDebugging 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
f1_keywords:
- jsrt/JsStartDebugging
helpviewer_keywords:
- JsStartDebugging function
ms.assetid: c48ba02d-6d47-466f-a970-02f087d525f3
caps.latest.revision: 15
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 9685779911db8e3045986682b66d13e38c70fe8d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232693"
---
# JsStartDebugging 函数

在当前上下文中开始调试。  
  
## 语法  
  
```cpp  
// Microsoft Edge mode signature  
STDAPI_(JsErrorCode) JsStartDebugging();  
  
// Legacy mode signature  
STDAPI_(JsErrorCode)  JsStartDebugging(  
   _In_ IDebugApplication *debugApplication  
);  
```  
  
#### 参数  
 `debugApplication`  
 用于调试的调试应用程序。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 在使用此 API 之前，主机应确保使用或 `CoInitializeEx` `COINIT_MULTITHREADED` 至少调用 `COINIT_APARTMENTTHREADED` 一次  
  
 Microsoft `debugApplication` Edge 模式不支持此参数。 有关在 Microsoft Edge 模式下使用此 API 有关详细信息，请参阅"面向 Microsoft Edge 与[旧版引擎"。](../chakra-hosting/targeting-edge-vs-legacy-engines-in-jsrt-apis.md)  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
