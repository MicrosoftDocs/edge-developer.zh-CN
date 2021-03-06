---
description: 异步 Windows 运行时方法的特殊错误属性
title: 异步 Windows 运行时方法的特殊错误属性
ms.custom: ''
ms.date: 11/03/2020
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
ms.assetid: 45155584-06d8-4e7f-93a6-8564a93f643d
caps.latest.revision: 4
author: MSEdgeTeam
ms.author: msedgedevrel
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: d9f2fdb007f00c2ab1d1a2050378af80f0075db6
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398838"
---
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a>异步 Windows 运行时方法的特殊错误属性  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

在 JavaScript 中调试异步 Windows 运行时方法可能比较困难，因为错误可能从调用堆栈中深度的某一位置引发。  JavaScript 对象具有仅在应用在调试模式下运行时从异步 Windows 运行时方法引发错误时 `Error` 显示的额外属性。  
  
## <a name="special-error-properties"></a>特殊错误属性  

在调试模式下，由 Windows 运行时异步操作失败导致的错误对象具有以下特殊属性：  

*   `asyncOpSource` \ (Object\) 获取生成错误的调用的原始位置的信息。  属性 \ (String\) 在发起异步操作的用户代码中 `asyncOpSource.originatingCall` 显示位置。  
*   asyncOpType \ (String\) 获取引发错误的异步操作类型的名称。  
    
有关异步操作错误的详细信息，请参阅：  

*   [如何处理有关承诺的错误][PreviousVersionsWindowsAppsHh700337]  
*   [解决 Windows 运行时错误][PreviousVersionsWindowsAppsHh974350]  
    
<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "如何处理 HTML 表单中的 (错误) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows 运行时错误疑难解答 (HTML) |Microsoft Docs"  
