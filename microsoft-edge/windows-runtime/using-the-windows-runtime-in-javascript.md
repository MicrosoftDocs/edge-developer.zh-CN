---
title: 在 JavaScript 中使用 Windows 运行时
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: bffde93aa973f492189aedcfcaa9c3694d9e61bc
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564578"
---
# 在 JavaScript 中使用 Windows 运行时  

编写通用 Windows 平台 \ （UWP）应用时，可以像使用本机 JavaScript 对象、方法和属性一样使用 Windows 运行时类、方法和属性。  本主题提供了介绍信息和指向主题的链接，这些主题解释在 JavaScript 中使用 Windows 运行时 Api 的基本概念，包括有关 Windows 运行时类型的表示方式、如何使用异步 Windows 运行时方法以及如何侦听和处理 Windows 运行时事件的说明。  

有关常规语言文档，请查看 MDN 的[JavaScript 参考][MDNJavascriptReference]库。  

> [!IMPORTANT]
> 对于在 Internet Explorer 中运行的应用，Windows 运行时功能不可用。  

## Windows 运行时参考文档  

有关参考文档，请参阅[Windows 运行时参考][UwpApiIndex]。  代码示例在 JavaScript 以及 c + +、c # 和 Visual Basic 中可用。  

## 编写 c + +、c # 或 Visual Basic 中的 Windows 运行时组件  

有关编写可在 JavaScript 中使用的 Windows 运行时组件的说明和指南，请参阅使用[c + + 创建 Windows 运行时组件][WindowsUwpWinrtCpp]和使用[c # 和 Visual Basic 创建 Windows 运行时组件][WindowsUwpWinrtCsharpVb]。  

## 带有 Windows 运行时功能的大小写约定  

JavaScript 中的 Windows 运行时功能的大小写约定与其他语言略有不同：  

*   命名空间和类采用 Pascal 大小写形式：  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   类的成员（包括方法和属性）和结构和枚举的成员采用 camel 大小写形式：  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   事件名称的小写字母：  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## 另请参阅  

[使用 Windows 运行时 API 时的注意事项][WindowsRuntimeConsiderationsApi]  
[使用 Windows 运行时异步方法][WindowsRuntimeAsynchronousMethods]   
[处理 JavaScript 中的 Windows 运行时事件][WindowsRuntimeEventsJavascript]   
[Windows 运行时类型的 JavaScript 表示形式][WindowsRuntimeJavascriptTypes]   
[Windows 运行时日期时间和时间跨度的 JavaScript 投影][WindowsRuntimeDatetimeTimespan]  
 
<!-- image links -->  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: /microsoft-edge/windows-runtime/considerations-when-using-the-windows-runtime-api "使用 Windows 运行时 API 时的注意事项"  
[WindowsRuntimeEventsJavascript]: /microsoft-edge/windows-runtime/handling-windows-runtime-events-in-javascript "处理 JavaScript 中的 Windows 运行时事件"  
[WindowsRuntimeJavascriptTypes]: /microsoft-edge/windows-runtime/javascript-representation-of-windows-runtime-types "Windows 运行时类型的 JavaScript 表示形式"  
[WindowsRuntimeAsynchronousMethods]: /microsoft-edge/windows-runtime/using-windows-runtime-asynchronous-methods "使用 Windows 运行时异步方法"  
[WindowsRuntimeDatetimeTimespan]: /microsoft-edge/windows-runtime/windows-runtime-datetime-and-timespan-representations "Windows 运行时日期时间和时间跨度表示形式"  

[UwpApiIndex]: /uwp/api/index "Windows UWP 命名空间"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "带有 c + +/CX 的 Windows 运行时组件"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "带有 c # 和 Visual Basic 的 Windows 运行时组件"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript 参考 |MDN"  
