---
description: 完成回调。
title: JsFinalizeCallback Typedef |Microsoft Docs
ms.prod: microsoft-edge
ms.topic: reference
ms.assetid: aa7a0269-b9d4-4717-97ac-8da7eb6ced15
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 794edbb3a61c8c213c0908740ed0a867488a2c6d
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232331"
---
# JsFinalizeCallback Typedef

完成回调。  
  
## 语法  
  
```cpp  
typedef void (CALLBACK *JsFinalizeCallback)(  
   _In_opt_ void *data  
);  
```  
  
#### 参数  
 数据  
 创建要完成的对象时传入的外部数据。  
  
## 要求  
 **标头** ：jsrt.h  
  
## 另请参阅  
 [应用 (JavaScript Runtime)](../chakra-hosting/reference-javascript-runtime.md)
