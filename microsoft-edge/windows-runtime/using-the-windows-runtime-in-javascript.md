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
# <span data-ttu-id="f6851-102">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="f6851-102">Using the Windows Runtime in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="f6851-103">在编写通用 Windows 平台 \ (UWP\) 应用时，你可以采用与使用本机 JavaScript 对象、方法和属性相同的方式使用 Windows 运行时类、方法和属性。</span><span class="sxs-lookup"><span data-stu-id="f6851-103">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="f6851-104">本主题提供了一些主题的介绍性信息和链接，这些主题指向介绍使用 JavaScript 中 Windows 运行时 API 的基本概念，包括有关如何表示 Windows 运行时类型的说明、如何使用异步 Windows 运行时方法，以及如何侦听和处理 Windows 运行时事件。</span><span class="sxs-lookup"><span data-stu-id="f6851-104">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="f6851-105">有关常规语言文档，请查看 MDN 的 [JavaScript 参考][MDNJavascriptReference] 库。</span><span class="sxs-lookup"><span data-stu-id="f6851-105">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="f6851-106">Windows 运行时功能不适用于在运行时运行Internet Explorer。</span><span class="sxs-lookup"><span data-stu-id="f6851-106">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="f6851-107">Windows 运行时参考文档</span><span class="sxs-lookup"><span data-stu-id="f6851-107">Windows Runtime reference documentation</span></span>  

<span data-ttu-id="f6851-108">有关参考文档，请参阅 [Windows 运行时参考][UwpApiIndex]。</span><span class="sxs-lookup"><span data-stu-id="f6851-108">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="f6851-109">代码示例可用于 JavaScript 中，而且 C++、C# 和 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="f6851-109">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="f6851-110">使用 C++、C# 或代码编写 Windows 运行时组Visual Basic</span><span class="sxs-lookup"><span data-stu-id="f6851-110">Writing Windows Runtime components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="f6851-111">有关编写可在 JavaScript 中使用的 Windows 运行时组件的说明和指南，请参阅 ["使用 C++][WindowsUwpWinrtCpp] 创建 Windows 运行时组件"以及使用 C# 和 Visual Basic 创建 [Windows 运行时组件][WindowsUwpWinrtCsharpVb]。</span><span class="sxs-lookup"><span data-stu-id="f6851-111">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="f6851-112">Windows 运行时功能的级列约定</span><span class="sxs-lookup"><span data-stu-id="f6851-112">Casing conventions with Windows Runtime features</span></span>  

<span data-ttu-id="f6851-113">JavaScript 中 Windows 运行时功能的级约定与其他语言的约定有所不同：</span><span class="sxs-lookup"><span data-stu-id="f6851-113">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="f6851-114">命名空间和类在 Pascal 案例中：</span><span class="sxs-lookup"><span data-stu-id="f6851-114">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="f6851-115">类的成员（包括方法和属性以及结构和枚举的成员）在摄像机情况下如下所示：</span><span class="sxs-lookup"><span data-stu-id="f6851-115">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="f6851-116">事件名称为小写：</span><span class="sxs-lookup"><span data-stu-id="f6851-116">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="f6851-117">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f6851-117">See also</span></span>  

[<span data-ttu-id="f6851-118">使用 Windows 运行时 API 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="f6851-118">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="f6851-119">使用 Windows 运行时异步方法</span><span class="sxs-lookup"><span data-stu-id="f6851-119">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="f6851-120">在 JavaScript 中处理 Windows 运行时事件</span><span class="sxs-lookup"><span data-stu-id="f6851-120">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="f6851-121">Windows 运行时类型 JavaScript 表示形式</span><span class="sxs-lookup"><span data-stu-id="f6851-121">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="f6851-122">Windows 运行时 DateTime 和 TimeSpan 的 JavaScript 投影</span><span class="sxs-lookup"><span data-stu-id="f6851-122">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  

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
