---
description: 创建 Javascript `DataView` 对象。
title: JsCreateDataView 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 161e59eb-d429-46f7-9a38-bbf2149ccf44
caps.latest.revision: 2
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1bf237458e8561b7070e4f3f0d4a14050f028375
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563172"
---
# JsCreateDataView 函数
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
 将 `ArrayBuffer` 用作结果对象的存储的现有对象 `DataView` 。  
  
 `byteOffset`  
 从结果的起始位置到引用的开始处的偏移量（以字节为单位） `arrayBuffer` `DataView` 。  
  
 `byteLength`  
 结果 DataView 引用的 ArrayBuffer 中的字节数。  
  
 `result`  
 新的 DataView 对象。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 Microsoft Edge 模式下受支持。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)