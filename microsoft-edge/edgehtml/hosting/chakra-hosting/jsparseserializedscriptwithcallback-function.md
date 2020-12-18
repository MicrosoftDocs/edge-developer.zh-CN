---
description: 分析序列化脚本并返回表示该脚本的函数。 仅在需要脚本源时，才提供延迟加载脚本源的能力。
title: JsParseSerializedScriptWithCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0a93ecfb-4b82-4a85-b24c-6816db2332ea
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: b145f01a5c3459100d8402beae63b7cff55db7b8
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232526"
---
# JsParseSerializedScriptWithCallback 函数

分析序列化脚本并返回表示该脚本的函数。 仅在需要脚本源时，才提供延迟加载脚本源的能力。  
  
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
 在需要加载脚本的源代码时调用的回调。  
  
 `scriptUnloadCallback`  
 当不再需要序列化脚本和源代码时调用的回调。  
  
 `buffer`  
 序列化脚本。  
  
 `sourceContext`  
 用于标识可调试脚本上下文使用的脚本的 Cookie。     此上下文将传递到 scriptLoadCallback 和 scriptUnloadCallback。  
  
 `sourceUrl`  
 脚本来自的位置。  
  
 `result`  
 一个代表脚本代码的函数。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
  
> [!NOTE]
>  此 API 尚不可用于应用商店应用。  
  
 需要活动脚本上下文。  
  
 运行时将保持该缓冲区，直到从缓冲区创建的任何函数的所有实例都进行垃圾回收。  然后，它将调用 scriptUnloadCallback 以通知调用方安全释放。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
