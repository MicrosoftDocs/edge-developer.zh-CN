---
description: 来自异步 Windows 运行时方法的特殊错误属性。
title: 异步 Windows 运行时方法的特殊错误属性
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 3557d0097d632f4058e46acbff748f7177d24ab1
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232317"
---
# 异步 Windows 运行时方法的特殊错误属性  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

在 JavaScript 中调试异步 Windows 运行时方法可能比较困难，因为错误可能从调用堆栈中深度的某一位置引发。  JavaScript 对象具有仅在应用在调试模式下运行时从异步 Windows 运行时方法引发错误时 `Error` 显示的额外属性。  
  
## 特殊错误属性  

调试模式下 Windows 运行时异步操作失败导致的错误对象具有以下特殊属性：  

*   `asyncOpSource` \ (Object\) 获取有关生成错误的调用的原始位置的信息。  属性 \ (String\) 显示发起异步操作的用户 `asyncOpSource.originatingCall` 代码中的位置。  
*   asyncOpType \ (String\) 获取引发错误的异步操作类型的名称。  
    
有关异步操作错误的详细信息，请参阅：  
  
*   [如何处理有关承诺的错误][PreviousVersionsWindowsAppsHh700337]  
*   [解决 Windows 运行时错误][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "如何处理 HTML 表单中 (错误) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows 运行时错误疑难解答 (HTML) |Microsoft Docs"  
