---
description: 创建 Javascript `DataView` 对象。
title: JsCreateDataView 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 1d6d170d53f3bfaf885713b6f3abca0b066f8c1d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232196"
---
# JsCreateDataView Function

创建 Javascript `DataView` 对象。  
  
## 语法  
  
```cpp  
JsErrorCode  JsCreateDataView(  
   _In_ JsValueRef arrayBuffer,  
   _In_ unsigned int byteOffset,  
   _In_ unsigned int byteLength,  
   _Out_ JsValueRef *result  
);  
```  
  
#### 参数  
 `arrayBuffer`  
 要 `ArrayBuffer` 用作结果对象的存储的现有 `DataView` 对象。  
  
 `byteOffset`  
 结果引用起始位置 `arrayBuffer` 的偏移量（以字节 `DataView` 为单位）。  
  
 `byteLength`  
 要引用的结果 DataView 的 ArrayBuffer 中的字节数。  
  
 `result`  
 新的 DataView 对象。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
