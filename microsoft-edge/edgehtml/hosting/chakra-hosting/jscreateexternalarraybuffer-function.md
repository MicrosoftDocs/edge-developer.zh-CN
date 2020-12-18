---
description: 创建 Javascript `ArrayBuffer` 对象以访问外部内存。
title: JsCreateExternalArrayBuffer 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: article
ms.assetid: 4a02aaec-0f67-4bf9-b37c-71cdb1410ca4
caps.latest.revision: 3
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 78c0d3c8b298876358f247c86a488b6f10e52c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232589"
---
# JsCreateExternalArrayBuffer 函数

创建 Javascript `ArrayBuffer` 对象以访问外部内存。
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateExternalArrayBuffer(  
  _Pre_maybenull_ _Pre_writable_byte_size_(byteLength) void *data,  
  _In_ unsigned int byteLength,  
  _In_opt_ JsFinalizeCallback finalizeCallback,  
  _In_opt_ void *callbackState,  
  _Out_ JsValueRef *result  
);  
  
```  
  
#### 参数  
 `data`  
 指向外部内存的指针。  
  
 `byteLength`  
 外部内存中的字节数。  
  
 `finalizeCallback`  
 对象完成时回调。 可能为空。  
  
 `callbackState`  
 用户提供的状态将传递回 finalizeCallback。  
  
 `result`  
 新 `ArrayBuffer` 对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
