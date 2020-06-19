---
description: 运行序列化脚本。 仅当需要时，才提供延迟加载脚本源的功能。
title: JsRunSerializedScriptWithCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 84a74d3c1aa68469dfe2fe42fdee685faa4c358c
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10752218"
---
# JsRunSerializedScriptWithCallback 函数
运行序列化脚本。 仅当需要时，才提供延迟加载脚本源的功能。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsRunSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_opt_ JsValueRef *result  
);  
  
```  
  
#### 参数  
 `scriptLoadCallback`  
 回调需要加载脚本的源代码时调用。  
  
 `scriptUnloadCallback`  
 当不再需要序列化脚本和源代码时调用回调。  
  
 `buffer`  
 序列化脚本。  
  
 `sourceContext`  
 标识可由可调试脚本上下文使用的脚本的 cookie。     此上下文将传递到 scriptLoadCallback 和 scriptUnloadCallback。  
  
 `sourceUrl`  
 脚本的来源位置。  
  
 `result`  
 运行脚本的结果（如果有）。 此参数可以为 null。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
  
> [!NOTE]
>  此 API 尚不可用于应用商店应用。  
  
 需要活动脚本上下文。  
  
 运行时将一直保留到缓冲区，直到从缓冲区创建的所有函数的所有实例都被垃圾回收。  然后，它将调用 scriptUnloadCallback 以通知呼叫者安全释放。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)