---
title: Using the Windows Runtime in JavaScript
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
# <span data-ttu-id="5332b-102">Using the Windows Runtime in JavaScript</span><span class="sxs-lookup"><span data-stu-id="5332b-102">Using the Windows Runtime in JavaScript</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="5332b-103">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span><span class="sxs-lookup"><span data-stu-id="5332b-103">When you write a Universal Windows Platform \(UWP\) app, you can use Windows Runtime classes, methods, and properties in much the same way that you would use native JavaScript objects, methods, and properties.</span></span>  <span data-ttu-id="5332b-104">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span><span class="sxs-lookup"><span data-stu-id="5332b-104">This topic provides introductory information and links to topics that explain the basic concepts of using Windows Runtime APIs in JavaScript, including an explanation of how Windows Runtime types are represented, how to use asynchronous Windows Runtime methods, and how to listen to and handle Windows Runtime events.</span></span>  

<span data-ttu-id="5332b-105">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span><span class="sxs-lookup"><span data-stu-id="5332b-105">For general language documentation, check out MDN's [JavaScript reference][MDNJavascriptReference] library.</span></span>  

> [!IMPORTANT]
> <span data-ttu-id="5332b-106">Windows Runtime features are not available for apps that run in Internet Explorer.</span><span class="sxs-lookup"><span data-stu-id="5332b-106">Windows Runtime features are not available for apps that run in Internet Explorer.</span></span>  

## <span data-ttu-id="5332b-107">Windows Runtime reference documentation</span><span class="sxs-lookup"><span data-stu-id="5332b-107">Windows Runtime reference documentation</span></span>  

<span data-ttu-id="5332b-108">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span><span class="sxs-lookup"><span data-stu-id="5332b-108">For reference documentation, see [Windows Runtime Reference][UwpApiIndex].</span></span>  <span data-ttu-id="5332b-109">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span><span class="sxs-lookup"><span data-stu-id="5332b-109">Code examples are available in JavaScript and also in C++, C#, and Visual Basic.</span></span>  

## <span data-ttu-id="5332b-110">Writing Windows Runtime components in C++, C#, or Visual Basic</span><span class="sxs-lookup"><span data-stu-id="5332b-110">Writing Windows Runtime components in C++, C#, or Visual Basic</span></span>  

<span data-ttu-id="5332b-111">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span><span class="sxs-lookup"><span data-stu-id="5332b-111">For instructions and guidelines for writing Windows Runtime components that can be consumed in JavaScript, see [Creating Windows Runtime Components in C++][WindowsUwpWinrtCpp] and [Creating Windows Runtime Components in C# and Visual Basic][WindowsUwpWinrtCsharpVb].</span></span>  

## <span data-ttu-id="5332b-112">Casing conventions with Windows Runtime features</span><span class="sxs-lookup"><span data-stu-id="5332b-112">Casing conventions with Windows Runtime features</span></span>  

<span data-ttu-id="5332b-113">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span><span class="sxs-lookup"><span data-stu-id="5332b-113">Casing conventions for Windows Runtime features in JavaScript differ slightly from those for other languages:</span></span>  

*   <span data-ttu-id="5332b-114">Namespaces and classes are in Pascal case:</span><span class="sxs-lookup"><span data-stu-id="5332b-114">Namespaces and classes are in Pascal case:</span></span>  
    
    ```javascript
    Windows.Deployment.PackageInfo;
    ```  
    
*   <span data-ttu-id="5332b-115">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span><span class="sxs-lookup"><span data-stu-id="5332b-115">Members of classes, including methods and properties, and members of structures and enumerations, are in camel case:</span></span>  
    
    ```javascript
    Deployment.PackageInfo.createPackage();
    ```  
    
*   <span data-ttu-id="5332b-116">Event names are in lower case:</span><span class="sxs-lookup"><span data-stu-id="5332b-116">Event names are in lower case:</span></span>  
    
    ```javascript
    dataTransferManager.ontargetapplicationchosen;
    ```  

## <span data-ttu-id="5332b-117">See also</span><span class="sxs-lookup"><span data-stu-id="5332b-117">See also</span></span>  

[<span data-ttu-id="5332b-118">Considerations when Using the Windows Runtime API</span><span class="sxs-lookup"><span data-stu-id="5332b-118">Considerations when Using the Windows Runtime API</span></span>][WindowsRuntimeConsiderationsApi]  
[<span data-ttu-id="5332b-119">Using Windows Runtime Asynchronous Methods</span><span class="sxs-lookup"><span data-stu-id="5332b-119">Using Windows Runtime Asynchronous Methods</span></span>][WindowsRuntimeAsynchronousMethods]   
[<span data-ttu-id="5332b-120">Handling Windows Runtime Events in JavaScript</span><span class="sxs-lookup"><span data-stu-id="5332b-120">Handling Windows Runtime Events in JavaScript</span></span>][WindowsRuntimeEventsJavascript]   
[<span data-ttu-id="5332b-121">JavaScript Representation of Windows Runtime Types</span><span class="sxs-lookup"><span data-stu-id="5332b-121">JavaScript Representation of Windows Runtime Types</span></span>][WindowsRuntimeJavascriptTypes]   
[<span data-ttu-id="5332b-122">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span><span class="sxs-lookup"><span data-stu-id="5332b-122">JavaScript Projection of Windows Runtime DateTime and TimeSpan</span></span>][WindowsRuntimeDatetimeTimespan]  

<!-- links  -->  

[WindowsRuntimeConsiderationsApi]: ./considerations-when-using-the-windows-runtime-api.md "Considerations when Using the Windows Runtime API | Microsoft Docs"  
[WindowsRuntimeEventsJavascript]: ./handling-windows-runtime-events-in-javascript.md "Handling Windows Runtime Events in JavaScript | Microsoft Docs"  
[WindowsRuntimeJavascriptTypes]: ./javascript-representation-of-windows-runtime-types.md "JavaScript Representation of Windows Runtime Types | Microsoft Docs"  
[WindowsRuntimeAsynchronousMethods]: ./using-windows-runtime-asynchronous-methods.md "Using Windows Runtime Asynchronous Methods | Microsoft Docs"  
[WindowsRuntimeDatetimeTimespan]: ./windows-runtime-datetime-and-timespan-representations.md "Windows Runtime DateTime and TimeSpan Representations | Microsoft Docs"  

[UwpApiIndex]: /uwp/api/index "Windows UWP Namespaces | Microsoft Docs"  
[WindowsUwpWinrtCpp]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-cpp "Windows Runtime components with C++/CX | Microsoft Docs"  
[WindowsUwpWinrtCsharpVb]: /windows/uwp/winrt-components/creating-windows-runtime-components-in-csharp-and-visual-basic "Windows Runtime components with C# and Visual Basic | Microsoft Docs"  

[MDNJavascriptReference]: https://developer.mozilla.org/docs/Web/JavaScript/Reference "JavaScript reference | MDN"  
