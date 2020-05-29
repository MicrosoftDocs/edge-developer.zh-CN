---
description: 执行脚本。
title: JsRunScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsRunScript
helpviewer_keywords:
- JsRunScript function
ms.assetid: 8d6b8c9a-af3a-4e21-a330-5a6b535423a3
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 49a06e4e6ad0c04e124b76f31d38b2e362e03f99
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564203"
---
# JsRunScript 函数
执行脚本。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsRunScript(  
   _In_z_ const wchar_t *script,  
   _In_ JsSourceContext sourceContext,  
   _In_z_ const wchar_t *sourceUrl,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `script`  
 要运行的脚本。  
  
 `sourceContext`  
 标识可由可调试脚本上下文使用的脚本的 cookie。  
  
 `sourceUrl`  
 脚本的来源位置。  
  
 `result`  
 脚本的结果（如果有）。 此参数可以为 null。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)