---
description: 运行序列化脚本。 仅在需要脚本源时，才提供延迟加载脚本源的能力。
title: JsRunSerializedScriptWithCallback 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 0608d778-f65b-4dc5-a745-364aac57ef59
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: ac9ac08357cd479f78e3500bc5eef151fb8e4e6c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232694"
---
# JsRunSerializedScriptWithCallback 函数

运行序列化脚本。 仅在需要脚本源时，才提供延迟加载脚本源的能力。  
  
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
 运行脚本的结果（如果有）。 此参数可以是 null。  
  
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
