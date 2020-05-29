---
description: 函数回调。
title: JsNativeFunction Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c0b73a11d3a0b2ed0867ef001f3c29c5643132a0
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563086"
---
# JsNativeFunction Typedef
函数回调。  
  
## 语法  
  
```cpp  
typedef _Ret_maybenull_ JsValueRef (CALLBACK * JsNativeFunction)(  
   _In_ JsValueRef callee,  
   _In_ bool isConstructCall,  
   _In_ JsValueRef *arguments,  
   _In_ unsigned short argumentCount  
);  
```  
  
#### 参数  
 方  
 一个 `Function` 表示正在调用的函数的对象。  
  
 isConstructCall  
 指示这是常规呼叫还是 "new" 呼叫。  
  
 arguments  
 调用的参数。  
  
 argumentCount  
 参数的数目。  
  
## 属性值/返回值  
 通话的结果（如果有）。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)