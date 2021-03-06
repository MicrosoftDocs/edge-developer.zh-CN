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
# <a name="special-error-properties-from-asynchronous-windows-runtime-methods"></a><span data-ttu-id="60b64-103">异步 Windows 运行时方法的特殊错误属性</span><span class="sxs-lookup"><span data-stu-id="60b64-103">Special error properties from asynchronous Windows Runtime methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="60b64-104">在 JavaScript 中调试异步 Windows 运行时方法可能比较困难，因为错误可能从调用堆栈中深度的某一位置引发。</span><span class="sxs-lookup"><span data-stu-id="60b64-104">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span>  <span data-ttu-id="60b64-105">JavaScript 对象具有仅在应用在调试模式下运行时从异步 Windows 运行时方法引发错误时 `Error` 显示的额外属性。</span><span class="sxs-lookup"><span data-stu-id="60b64-105">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <a name="special-error-properties"></a><span data-ttu-id="60b64-106">特殊错误属性</span><span class="sxs-lookup"><span data-stu-id="60b64-106">Special error properties</span></span>  

<span data-ttu-id="60b64-107">在调试模式下，由 Windows 运行时异步操作失败导致的错误对象具有以下特殊属性：</span><span class="sxs-lookup"><span data-stu-id="60b64-107">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="60b64-108">\ (Object\) 获取生成错误的调用的原始位置的信息。</span><span class="sxs-lookup"><span data-stu-id="60b64-108">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span>  <span data-ttu-id="60b64-109">属性 \ (String\) 在发起异步操作的用户代码中 `asyncOpSource.originatingCall` 显示位置。</span><span class="sxs-lookup"><span data-stu-id="60b64-109">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="60b64-110">asyncOpType \ (String\) 获取引发错误的异步操作类型的名称。</span><span class="sxs-lookup"><span data-stu-id="60b64-110">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="60b64-111">有关异步操作错误的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="60b64-111">For more information about errors with asynchronous operations, see:</span></span>  

*   [<span data-ttu-id="60b64-112">如何处理有关承诺的错误</span><span class="sxs-lookup"><span data-stu-id="60b64-112">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="60b64-113">解决 Windows 运行时错误</span><span class="sxs-lookup"><span data-stu-id="60b64-113">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  
    
<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "如何处理 HTML 表单中的 (错误) |Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows 运行时错误疑难解答 (HTML) |Microsoft Docs"  
