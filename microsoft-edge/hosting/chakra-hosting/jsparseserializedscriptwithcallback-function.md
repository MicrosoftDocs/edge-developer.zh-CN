---
description: 分析序列化脚本并返回表示脚本的函数。 仅当需要时，才提供延迟加载脚本源的功能。
title: JsParseSerializedScriptWithCallback 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: ad6d635722f0b3fea8b19f8d16679b402d1fd56e
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564213"
---
# JsParseSerializedScriptWithCallback 函数
分析序列化脚本并返回表示脚本的函数。 仅当需要时，才提供延迟加载脚本源的功能。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsParseSerializedScriptWithCallback(  
  _In_ JsSerializedScriptLoadSourceCallback scriptLoadCallback,  
  _In_ JsSerializedScriptUnloadCallback scriptUnloadCallback,  
  _In_ BYTE *buffer,  
  _In_ JsSourceContext sourceContext,  
  _In_z_ const wchar_t *sourceUrl,  
  _Out_ JsValueRef * result  
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
 表示脚本代码的函数。  
  
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
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)