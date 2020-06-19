---
description: 由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区 `JsSerializedScriptUnloadCallback` 有效，直到
title: JsSerializedScriptLoadSourceCallback Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 9406c488-76ac-49e5-b305-39751f3412ea
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 571314145cc19513f04174a9a1c93822a5795b29
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752197"
---
# JsSerializedScriptLoadSourceCallback Typedef
由运行时调用以加载序列化脚本的源代码。 调用方必须保持脚本缓冲区 `JsSerializedScriptUnloadCallback` 有效，直到  
  
## 语法  
  
```cpp  
typedef bool (CALLBACK * JsSerializedScriptLoadSourceCallback)(  
  _In_ JsSourceContextsourceContext,  
  _Outptr_result_z_ const wchar_t** scriptBuffer  
);  
```  
  
#### 参数  
 `sourceContext`  
 传递给或的 `JsParseSerializedScriptWithCallback` 上下文 `JsRunSerializedScriptWithCallback` 。  
  
 `scriptBuffer`  
 脚本返回。  
  
## 备注  
  
> [!WARNING]
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)