---
title: 异步 Windows 运行时方法中的特殊错误属性
ms.custom: ''
ms.date: 04/01/2020
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
ms.openlocfilehash: 5cf2604e26c84e769cf44e0879ee137cbfbe8b90
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564580"
---
# <span data-ttu-id="2c89c-102">异步 Windows 运行时方法中的特殊错误属性</span><span class="sxs-lookup"><span data-stu-id="2c89c-102">Special Error Properties from Asynchronous Windows Runtime Methods</span></span>  

<span data-ttu-id="2c89c-103">很难调试 JavaScript 中的异步 Windows 运行时方法，因为错误可能会从调用堆栈中的某个位置引发。</span><span class="sxs-lookup"><span data-stu-id="2c89c-103">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span> <span data-ttu-id="2c89c-104">JavaScript `Error` 对象具有额外的属性，仅当应用在调试模式下运行时从异步 Windows 运行时方法引发时，才会显示这些属性。</span><span class="sxs-lookup"><span data-stu-id="2c89c-104">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <span data-ttu-id="2c89c-105">特殊错误属性</span><span class="sxs-lookup"><span data-stu-id="2c89c-105">Special Error Properties</span></span>  

<span data-ttu-id="2c89c-106">在调试模式下出现故障的 Windows 运行时异步操作导致的错误对象具有下列特殊属性：</span><span class="sxs-lookup"><span data-stu-id="2c89c-106">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="2c89c-107">\ （对象 \）获取有关产生错误的调用的原始位置的信息。</span><span class="sxs-lookup"><span data-stu-id="2c89c-107">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span> <span data-ttu-id="2c89c-108">属性 `asyncOpSource.originatingCall` \ （字符串 \）显示用户代码中发起异步操作的位置。</span><span class="sxs-lookup"><span data-stu-id="2c89c-108">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="2c89c-109">asyncOpType \ （字符串 \）获取引发错误的异步操作类型的名称。</span><span class="sxs-lookup"><span data-stu-id="2c89c-109">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="2c89c-110">有关异步操作的错误的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="2c89c-110">For more information about errors with asynchronous operations, see:</span></span>  
  
*   [<span data-ttu-id="2c89c-111">如何处理有关承诺的错误</span><span class="sxs-lookup"><span data-stu-id="2c89c-111">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="2c89c-112">解决 Windows 运行时错误</span><span class="sxs-lookup"><span data-stu-id="2c89c-112">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  

<!-- image links -->  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "如何处理承诺的错误（HTML）"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Windows 运行时错误疑难解答（HTML）"  
