---
title: 异步 Windows 运行时方法的特殊错误属性
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: a1fccf1cec811501b94e7da4aa20b69d93754f62
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942069"
---
# 异步 Windows 运行时方法的特殊错误属性  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

在 JavaScript 中调试异步 Windows 运行时方法可能很难，因为在调用堆叠中的某个位置可能会引发该错误。  仅当应用在调试模式下运行时从异步 Windows 运行时方法引发错误时，JavaScript 对象的额外属性才能 `Error` 显示。  
  
## 特殊错误属性  

在调试模式下，由于失败的 Windows 运行时异步操作引发的错误对象具有以下特殊属性：  

*   `asyncOpSource` \ (Object\) 获取有关在引发错误的调用的原始位置的信息。  属性 `asyncOpSource.originatingCall` \ (String\) 显示用户代码中的位置，该位置引起异步操作。  
*   asyncOpType \ (String\) 获取引发错误的异步操作类型的名称。  
    
有关异步操作错误的详细信息，请参阅：  
  
*   [如何处理有关承诺的错误][PreviousVersionsWindowsAppsHh700337]  
*   [解决 Windows 运行时错误][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "如何使用有关 HTML 事件 () 的错误Microsoft 文档"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "解决 HTML 数据文件 (java) |Microsoft 文档"  
