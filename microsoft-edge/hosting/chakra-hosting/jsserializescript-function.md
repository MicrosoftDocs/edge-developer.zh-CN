---
description: 将已分析的脚本序列化为可以重复使用的缓冲区。
title: JsSerializeScript 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- jsrt/JsSerializeScript
helpviewer_keywords:
- JsSerializeScript function
ms.assetid: ca42c194-e1c1-407d-b542-b9d494e3ac4e
caps.latest.revision: 12
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 1b45067fddb7ea4dff02e527e460db1270011c61
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564185"
---
# JsSerializeScript 函数
将已分析的脚本序列化为可以重复使用的缓冲区。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode) JsSerializeScript(  
   _In_z_ const wchar_t *script,  
   _Out_writes_to_opt_(*bufferSize,  
   *bufferSize) BYTE *buffer,  
   _Inout_ unsigned long *bufferSize  
);  
```  
  
#### 参数  
 `script`  
 要序列化的脚本。  
  
 `buffer`  
 要将序列化的脚本放入的缓冲区。 可以为 null。  
  
 `bufferSize`  
 输入时，缓冲区的大小（以字节为单位）;退出时，保留序列化脚本所需的缓冲区大小（以字节为单位）。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 `JsSerializeScript` 分析脚本，然后以与运行时无关的格式存储脚本的已分析形式。 然后，可以在任何运行时反序列化脚本，而无需重新分析脚本。  
  
 需要活动脚本上下文。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)