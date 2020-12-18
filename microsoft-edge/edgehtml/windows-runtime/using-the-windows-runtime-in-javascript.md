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
# <span data-ttu-id="00a82-103">在 JavaScript 中使用 Windows 运行时</span><span class="sxs-lookup"><span data-stu-id="00a82-103">Using the Windows Runtime in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="00a82-104">编写通用 Windows 平台 \ (UWP\) 应用时，可以使用与使用本机 JavaScript 对象、方法和属性相同的方式使用 Windows 运行时类、方法和属性。</span><span class="sxs-lookup"><span data-stu-id="00a82-104">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="00a82-105">本主题提供介绍性信息和主题链接，这些主题介绍了在 JavaScript 中使用 Windows 运行时 API 的基本概念，包括如何表示 Windows 运行时类型、如何使用异步 Windows 运行时方法以及如何侦听和处理 Windows 运行时事件的说明。</span><span class="sxs-lookup"><span data-stu-id="00a82-105">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="00a82-106">有关常规语言文档，请查看 MDN 的 [JavaScript 参考][MDNJavascriptReference] 库。</span><span class="sxs-lookup"><span data-stu-id="00a82-106">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="00a82-107">Windows 运行时功能不适用于在 Internet Explorer 中运行的应用。</span><span class="sxs-lookup"><span data-stu-id="00a82-107">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="00a82-108">Windows 运行时参考文档</span><span class="sxs-lookup"><span data-stu-id="00a82-108">Windows Runtime reference documentation</span></span>  

<span data-ttu-id="00a82-109">有关参考文档，请参阅 [Windows 运行时参考][UwpApiIndex]。</span><span class="sxs-lookup"><span data-stu-id="00a82-109">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="00a82-110">JavaScript 以及 C++、C# 和 Visual Basic 中提供了代码示例。</span><span class="sxs-lookup"><span data-stu-id="00a82-110">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="00a82-111">使用 C++、C# 或 Visual Basic</span><span class="sxs-lookup"><span data-stu-id="00a82-111">Writing Windows Runtime components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="00a82-112">有关编写可在 JavaScript 中使用的 Windows 运行时组件的说明和指南，请参阅使用 [C++][WindowsUwpWinrtCpp] 创建 Windows 运行时组件以及使用 [C#][WindowsUwpWinrtCsharpVb]和 Visual Basic。</span><span class="sxs-lookup"><span data-stu-id="00a82-112">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="00a82-113">Windows 运行时功能的大小写约定</span><span class="sxs-lookup"><span data-stu-id="00a82-113">Casing conventions with Windows Runtime features</span></span>  

<span data-ttu-id="00a82-114">JavaScript 中 Windows 运行时功能的大小写约定与其他语言的大小写约定略有不同：</span><span class="sxs-lookup"><span data-stu-id="00a82-114">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="00a82-115">命名空间和类在 Pascal 情况下：</span><span class="sxs-lookup"><span data-stu-id="00a82-115">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="00a82-116">类的成员（包括方法和属性以及结构和枚举的成员）在 Camel 情况下为：</span><span class="sxs-lookup"><span data-stu-id="00a82-116">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="00a82-117">事件名称为小写：</span><span class="sxs-lookup"><span data-stu-id="00a82-117">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="00a82-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00a82-118">See also</span></span>  

[<span data-ttu-id="00a82-119">使用 Windows 运行时 API 时的注意事项</span><span class="sxs-lookup"><span data-stu-id="00a82-119">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="00a82-120">使用 Windows 运行时异步方法</span><span class="sxs-lookup"><span data-stu-id="00a82-120">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="00a82-121">在 JavaScript 中处理 Windows 运行时事件</span><span class="sxs-lookup"><span data-stu-id="00a82-121">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="00a82-122">Windows 运行时类型 JavaScript 表示形式</span><span class="sxs-lookup"><span data-stu-id="00a82-122">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="00a82-123">Windows 运行时 DateTime 和 TimeSpan 的 JavaScript 投影</span><span class="sxs-lookup"><span data-stu-id="00a82-123">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  

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
