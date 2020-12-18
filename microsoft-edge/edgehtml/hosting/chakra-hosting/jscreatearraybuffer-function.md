---
description: 创建 JavaScript `ArrayBuffer` 对象。
title: JsCreateArrayBuffer 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: c9e74184-7dd9-41a7-a1fe-9575e1701392
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3bee44d77f78bd35705211c598db78ab09000c71
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232197"
---
# JsCreateArrayBuffer 函数

创建 JavaScript `ArrayBuffer` 对象。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsCreateArrayBuffer(  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `byteLength`  
 ArrayBuffer 中的字节数。  
  
 `result`  
 新的 ArrayBuffer 对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
