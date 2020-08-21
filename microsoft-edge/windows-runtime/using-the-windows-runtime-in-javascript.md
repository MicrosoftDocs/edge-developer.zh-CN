---
title: 在 JavaScript 中使用 Windows 运行时
ms.custom: ''
ms.date: 07/29/2020
ms.prod: microsoft-edge
ms.reviewer: ''
ms.suite: ''
ms.technology: windows-integration
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
manager: ''
ms.openlocfilehash: 444008598a2f7a2f5257544304bed87fbfaa203a
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942176"
---
# 在 JavaScript 中使用 Windows 运行时  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

在编写通用 Windows 平台 \ (UWP\) 应用时，你可以采用与使用本机 JavaScript 对象、方法和属性相同的方式使用 Windows 运行时类、方法和属性。  本主题提供了一些主题的介绍性信息和链接，这些主题指向介绍使用 JavaScript 中 Windows 运行时 API 的基本概念，包括有关如何表示 Windows 运行时类型的说明、如何使用异步 Windows 运行时方法，以及如何侦听和处理 Windows 运行时事件。  

有关常规语言文档，请查看 MDN 的 [JavaScript 参考][MDNJavascriptReference] 库。  

> [!IMPORTANT]
> Windows 运行时功能不适用于在运行时运行Internet Explorer。  

## Windows 运行时参考文档  

有关参考文档，请参阅 [Windows 运行时参考][UwpApiIndex]。  代码示例可用于 JavaScript 中，而且 C++、C# 和 Visual Basic。  

## 使用 C++、C# 或代码编写 Windows 运行时组Visual Basic  

有关编写可在 JavaScript 中使用的 Windows 运行时组件的说明和指南，请参阅 ["使用 C++][WindowsUwpWinrtCpp] 创建 Windows 运行时组件"以及使用 C# 和 Visual Basic 创建 [Windows 运行时组件][WindowsUwpWinrtCsharpVb]。  

## Windows 运行时功能的级列约定  

JavaScript 中 Windows 运行时功能的级约定与其他语言的约定有所不同：  

*   命名空间和类在 Pascal 案例中：  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   类的成员（包括方法和属性以及结构和枚举的成员）在摄像机情况下如下所示：  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   事件名称为小写：  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## 另请参阅  

[使用 Windows 运行时 API 时的注意事项][WindowsRuntimeConsiderationsApi]  
[使用 Windows 运行时异步方法][WindowsRuntimeAsynchronousMethods]   
[在 JavaScript 中处理 Windows 运行时事件][WindowsRuntimeEventsJavascript]   
[Windows 运行时类型 JavaScript 表示形式][WindowsRuntimeJavascriptTypes]   
[Windows 运行时 DateTime 和 TimeSpan 的 JavaScript 投影][WindowsRuntimeDatetimeTimespan]  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "使用 Windows 运行时 API | 时的注意事项Microsoft 文档"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "使用 JavaScript | 处理 Windows 运行时事件 |Microsoft 文档"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示 |Microsoft 文档"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "使用 Windows 运行时异步方法 |Microsoft 文档"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows 运行时 DateTime 和 TimeSpan Representations |Microsoft 文档"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间 |Microsoft 文档"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "使用 C++/CX | 的 Windows 运行时组件Microsoft 文档"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "使用 C# 和应用 | 的 Windows 运行时组Visual Basic |Microsoft 文档"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript 参考 |MDN"  
