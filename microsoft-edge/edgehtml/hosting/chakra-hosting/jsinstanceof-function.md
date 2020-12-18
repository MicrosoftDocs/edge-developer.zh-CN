---
description: 执行 JavaScript `instanceof` 运算符测试。
title: JsInstanceOf 函数 |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: 94399a62-b996-4fd2-82ce-1c26e7a4da08
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d8aec1d4512fe937d1fd48aa6f3e88294bf9850c
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232580"
---
# JsInstanceOf 函数

执行 JavaScript `instanceof` 运算符测试。  
  
## 语法  
  
```cpp  
JsInstanceOf(   
  _In_ JsValueRef object,  
  _In_ JsValueRef constructor,  
  _Out_ bool *result  
);  
  
```  
  
#### 参数  
 `object`  
 要测试的对象。  
  
 `constructor`  
 要测试的构造函数函数。  
  
 `result`  
 "object instanceof 构造函数"是否为 true。  
  
## 返回值  
 如果 `JsNoError` 操作成功，则代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
