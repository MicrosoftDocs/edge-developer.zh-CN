---
description: 在 JavaScript 中使用 Windows 运行时。
title: 在 JavaScript 中使用 Windows 运行时
ms.prod: microsoft-edge
ms.technology: windows-integration
ms.topic: article
helpviewer_keywords:
- JavaScript, Windows Runtime
ms.assetid: 90658546-f746-4e34-a7d1-71cf9ee322a2
caps.latest.revision: 16
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 10c90a225816cf32e01bc33648571c13a1aae090
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232314"
---
# 在 JavaScript 中使用 Windows 运行时  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

编写通用 Windows 平台 \ (UWP\) 应用时，可以使用与使用本机 JavaScript 对象、方法和属性相同的方式使用 Windows 运行时类、方法和属性。  本主题提供介绍性信息和主题链接，这些主题介绍了在 JavaScript 中使用 Windows 运行时 API 的基本概念，包括如何表示 Windows 运行时类型、如何使用异步 Windows 运行时方法以及如何侦听和处理 Windows 运行时事件的说明。  

有关常规语言文档，请查看 MDN 的 [JavaScript 参考][MDNJavascriptReference] 库。  

> [!IMPORTANT]
> Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。  

## Windows 运行时参考文档  

有关参考文档，请参阅 [Windows 运行时参考][UwpApiIndex]。  JavaScript 以及 C++、C# 和 Visual Basic 中提供了代码示例。  

## 使用 C++、C# 或 Visual Basic  

有关编写可在 JavaScript 中使用的 Windows 运行时组件的说明和指南，请参阅使用 [C++][WindowsUwpWinrtCpp] 创建 Windows 运行时组件以及使用 [C#][WindowsUwpWinrtCsharpVb]和 Visual Basic。  

## Windows 运行时功能的大小写约定  

JavaScript 中 Windows 运行时功能的大小写约定与其他语言的大小写约定略有不同：  

*   命名空间和类在 Pascal 情况下：  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   类的成员（包括方法和属性以及结构和枚举的成员）在 Camel 情况下为：  
    
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

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "使用 Windows 运行时 API 的注意事项 |Microsoft Docs"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "在 JavaScript 中处理 Windows 运行时事件 |Microsoft Docs"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "Windows 运行时类型的 JavaScript 表示形式 |Microsoft Docs"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "使用 Windows 运行时异步方法 |Microsoft Docs"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows 运行时 DateTime 和 TimeSpan 表示形式 |Microsoft Docs"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间 |Microsoft Docs"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "使用 C++/CX 的 Windows 运行时组件 |Microsoft Docs"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "使用 C# 和 Visual Basic 的 Windows 运行时组件 |Microsoft Docs"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript 参考 |MDN"  
