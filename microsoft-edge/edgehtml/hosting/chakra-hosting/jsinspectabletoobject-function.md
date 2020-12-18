---
description: 创建一个 JavaScript 值，该值是传入指针的 `IInspectable` 投影。
title: JsInspectableToObject 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: a5d3d91b38c9db5de2eb8fb02526f6072f0f5147
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232582"
---
# JsInspectableToObject 函数

创建一个 JavaScript 值，该值是传入指针的 `IInspectable` 投影。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### 参数  
 `inspectable`  
 要 `IInspectable` 规划的 A。  
  
 `value`  
 作为投影的 JavaScript 值 `IInspectable` 。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 脚本可以使用预计值调用 WinRT 对象。 主机负责强制实施 COM 线程规则。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
