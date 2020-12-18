---
description: 函数回调。
title: JsNativeFunction Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 56ef6cdf-4ca9-4f7c-b953-e661addb1a8e
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 891fe55f776e8519a5d3c187104b2bc326336482
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232021"
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
 被叫方  
 `Function`一个代表要调用的函数的对象。  
  
 isConstructCall  
 指示这是常规呼叫还是"新"呼叫。  
  
 arguments  
 调用的参数。  
  
 argumentCount  
 参数数。  
  
## 属性值/返回值  
 呼叫的结果（如果有）。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
