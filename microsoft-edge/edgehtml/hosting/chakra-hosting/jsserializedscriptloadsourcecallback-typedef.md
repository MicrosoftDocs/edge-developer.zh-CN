---
description: 由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区有效，直到 `JsSerializedScriptUnloadCallback` .
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 2bb30befc61003d20cdeaa293fd1fdfdc95b36f7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232759"
---
# JsSerializedScriptLoadSourceCallback Typedef

由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区有效，直到 `JsSerializedScriptUnloadCallback` .  
  
## 语法  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### 参数  
 `sourceContext`  
 传递给 或 `JsParseSerializedScriptWithCallback` `JsRunSerializedScriptWithCallback` 的上下文。  
  
 `scriptBuffer`  
 返回的脚本。  
  
## 备注  
  
> [!WARNING]
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
