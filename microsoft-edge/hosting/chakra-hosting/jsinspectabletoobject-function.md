---
description: 创建一个 JavaScript 值，该值是传入的指针的投影 `IInspectable` 。
title: JsInspectableToObject 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: dd0ad567-2ba8-4a63-bee4-2c6ff5ce9fa9
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 26ce17eb3abcefcf9a1f0cc773e9fe4c3aaf05cd
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563099"
---
# JsInspectableToObject 函数
创建一个 JavaScript 值，该值是传入的指针的投影 `IInspectable` 。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsInspectableToObject(  
        _In_ IInspectable  *inspectable,  
        _Out_ JsValueRef *value  
);  
```  
  
#### 参数  
 `inspectable`  
 `IInspectable`要投影的。  
  
 `value`  
 作为的投影的 JavaScript 值 `IInspectable` 。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 所投影值可由脚本用于调用 WinRT 对象。 主机负责强制执行 COM 线程处理规则。  
  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)