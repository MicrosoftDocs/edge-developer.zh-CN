---
description: Project for WinRT 命名空间。
title: JsProjectWinRTNamespace 函数 |Microsoft 文档
ms.custom: ''
ms.date: 01/18/2017
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: reference
ms.assetid: 8a23c154-df4b-4ce3-9fef-f41f90acdb87
caps.latest.revision: 5
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: c4d63727b3d25bbb346fee7179ae0d942ae37008
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563072"
---
# JsProjectWinRTNamespace 函数
Project for WinRT 命名空间。  
  
## 语法  
  
```cpp  
STDAPI_(JsErrorCode)  
   JsProjectWinRTNamespace(  
   _In_z_ const wchar_t *namespaceName  
);  
```  
  
#### 参数  
 `namespaceName`  
 要投影的 WinRT 命名空间。  
  
## 返回值  
 `JsNoError`如果操作成功，则为代码，否则为失败代码。  
  
## 备注  
 需要活动脚本上下文。  
  
 此 API 仅在 EdgeHTML 模式下受支持。  
  
> [!NOTE]
>  WinRT 是通用 Windows 平台（UWP）之前的平台名称。  
  
## 要求  
 **页眉：** jsrt  
  
## 另请参阅  
 [参考（JavaScript 运行时）](../chakra-hosting/reference-javascript-runtime.md)