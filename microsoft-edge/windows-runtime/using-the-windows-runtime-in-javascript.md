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
# <span data-ttu-id="b31f5-102">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="b31f5-102">Using the Windows Runtime in JavaScript</span></span>  

<span data-ttu-id="b31f5-103">编写通用 Windows 平台 \ （UWP）应用时，可以像使用本机 JavaScript 对象、方法和属性一样使用 Windows 运行时类、方法和属性。</span><span class="sxs-lookup"><span data-stu-id="b31f5-103">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="b31f5-104">本主题提供了介绍信息和指向主题的链接，这些主题解释在 JavaScript 中使用 Windows 运行时 Api 的基本概念，包括有关 Windows 运行时类型的表示方式、如何使用异步 Windows 运行时方法以及如何侦听和处理 Windows 运行时事件的说明。</span><span class="sxs-lookup"><span data-stu-id="b31f5-104">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="b31f5-105">有关常规语言文档，请查看 MDN 的[JavaScript 参考][MDNJavascriptReference]库。</span><span class="sxs-lookup"><span data-stu-id="b31f5-105">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="b31f5-106">对于在 Internet Explorer 中运行的应用，Windows 运行时功能不可用。</span><span class="sxs-lookup"><span data-stu-id="b31f5-106">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="b31f5-107">Windows 运行时参考文档</span><span class="sxs-lookup"><span data-stu-id="b31f5-107">Windows Runtime Reference Documentation</span></span>  

<span data-ttu-id="b31f5-108">有关参考文档，请参阅[Windows 运行时参考][UwpApiIndex]。</span><span class="sxs-lookup"><span data-stu-id="b31f5-108">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="b31f5-109">代码示例在 JavaScript 以及 c + +、c # 和 Visual Basic 中可用。</span><span class="sxs-lookup"><span data-stu-id="b31f5-109">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="b31f5-110">编写 c + +、c # 或 Visual Basic 中的 Windows 运行时组件</span><span class="sxs-lookup"><span data-stu-id="b31f5-110">Writing Windows Runtime Components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="b31f5-111">有关编写可在 JavaScript 中使用的 Windows 运行时组件的说明和指南，请参阅使用[c + + 创建 Windows 运行时组件][WindowsUwpWinrtCpp]和使用[c # 和 Visual Basic 创建 Windows 运行时组件][WindowsUwpWinrtCsharpVb]。</span><span class="sxs-lookup"><span data-stu-id="b31f5-111">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="b31f5-112">带有 Windows 运行时功能的大小写约定</span><span class="sxs-lookup"><span data-stu-id="b31f5-112">Casing Conventions with Windows Runtime Features</span></span>  

<span data-ttu-id="b31f5-113">JavaScript 中的 Windows 运行时功能的大小写约定与其他语言略有不同：</span><span class="sxs-lookup"><span data-stu-id="b31f5-113">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="b31f5-114">命名空间和类采用 Pascal 大小写形式：</span><span class="sxs-lookup"><span data-stu-id="b31f5-114">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="b31f5-115">类的成员（包括方法和属性）和结构和枚举的成员采用 camel 大小写形式：</span><span class="sxs-lookup"><span data-stu-id="b31f5-115">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="b31f5-116">事件名称的小写字母：</span><span class="sxs-lookup"><span data-stu-id="b31f5-116">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="b31f5-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b31f5-117">See Also</span></span>  

[<span data-ttu-id="b31f5-118">使用 Windows 运行时 API 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="b31f5-118">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="b31f5-119">使用 Windows 运行时异步方法</span><span class="sxs-lookup"><span data-stu-id="b31f5-119">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="b31f5-120">处理 JavaScript 中的 Windows 运行时事件</span><span class="sxs-lookup"><span data-stu-id="b31f5-120">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="b31f5-121">Windows 运行时类型的 JavaScript 表示形式</span><span class="sxs-lookup"><span data-stu-id="b31f5-121">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="b31f5-122">Windows 运行时日期时间和时间跨度的 JavaScript 投影</span><span class="sxs-lookup"><span data-stu-id="b31f5-122">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  
 
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
