---
title: 异步 Windows 运行时方法中的特殊错误属性
ms.custom: ''
ms.date: 04/01/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 5cf2604e26c84e769cf44e0879ee137cbfbe8b90
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564580"
---
# 异步 Windows 运行时方法中的特殊错误属性  

很难调试 JavaScript 中的异步 Windows 运行时方法，因为错误可能会从调用堆栈中的某个位置引发。 JavaScript `Error` 对象具有额外的属性，仅当应用在调试模式下运行时从异步 Windows 运行时方法引发时，才会显示这些属性。  
  
## 特殊错误属性  

在调试模式下出现故障的 Windows 运行时异步操作导致的错误对象具有下列特殊属性：  

*   `asyncOpSource` \ （对象 \）获取有关产生错误的调用的原始位置的信息。 属性 `asyncOpSource.originatingCall` \ （字符串 \）显示用户代码中发起异步操作的位置。  
*   asyncOpType \ （字符串 \）获取引发错误的异步操作类型的名称。  
    
有关异步操作的错误的详细信息，请参阅：  
  
*   [如何处理有关承诺的错误][PreviousVersionsWindowsAppsHh700337]  
*   [解决 Windows 运行时错误][PreviousVersionsWindowsAppsHh974350]  

<!-- image links -->  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "如何处理承诺的错误（HTML）"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows 运行时错误疑难解答（HTML）"  
