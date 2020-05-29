---
description: 在运行时使用与脚本执行相关的所有资源完成时调用。 此时，调用方应释放源（如果已加载）、字节代码和上下文。
title: JsSerializedScriptUnloadCallback typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 9555b3fd8c14c9629d17c13592e3c78a78be150e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564187"
---
# JsSerializedScriptUnloadCallback typedef
在运行时使用与脚本执行相关的所有资源完成时调用。 此时，调用方应释放源（如果已加载）、字节代码和上下文。  
  
## 语法  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### 参数  
 `sourceContext`  
 传递给或的 `JsParseSerializedScriptWithCallback` 上下文 `JsRunSerializedScriptWithCallback` 。  
  
## 备注  
  
> [!WARNING]
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)