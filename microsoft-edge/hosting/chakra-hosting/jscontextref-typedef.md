---
description: 对脚本上下文的引用。
title: JsContextRef Typedef |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8586bfcc-bb24-430d-a6f2-1a3b3e34ec2e
caps.latest.revision: 6
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 80e4b5034079f4f0d26da070bd209aa41bf3475f
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563189"
---
# JsContextRef Typedef
对脚本上下文的引用。  
  
## 语法  
  
```cpp  
typedef JsRef JsContextRef;  
```  
  
## 备注  
 每个脚本上下文都包含其自己的全局对象，与其他脚本上下文中的全局对象不同。  
  
 许多 Chakra 托管 Api 需要 "活动" 脚本上下文，可使用进行设置 `JsSetCurrentContext` 。 需要设置当前上下文的 Chakra 托管 Api 将在其文档中明确说明。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)