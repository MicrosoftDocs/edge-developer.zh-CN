---
description: 运行时在使用与脚本执行相关的所有资源完成时调用它。 如果加载，调用方此时应释放源、字节代码和上下文。
title: JsSerializedScriptUnloadCallback typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 8d18c392-cca0-411e-9f2b-0d788b16161a
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5c63f2ff3faf21a19e31f2f6fd1692e21d59fc0b
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232709"
---
# JsSerializedScriptUnloadCallback typedef

运行时在使用与脚本执行相关的所有资源完成时调用它。 如果加载，调用方此时应释放源、字节代码和上下文。  
  
## 语法  
  
```cpp  
 typedef void (CALLBACK * JsSerializedScriptUnloadCallback)(  
  _In_ JsSourceContext sourceContext  
);  
```  
  
#### 参数  
 `sourceContext`  
 传递给 或 `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 的上下文。  
  
## 备注  
  
> [!WARNING]
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
