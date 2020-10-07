---
title: Special Error Properties from Asynchronous Windows Runtime Methods
ms.custom: ''
ms.date: 07/29/2020
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
ms.openlocfilehash: a1fccf1cec811501b94e7da4aa20b69d93754f62
ms.sourcegitcommit: 29cbe0f464ba0092e025f502833eb9cc3e02ee89
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "10942069"
---
# <span data-ttu-id="b94f9-102">Special error properties from asynchronous Windows Runtime methods</span><span class="sxs-lookup"><span data-stu-id="b94f9-102">Special error properties from asynchronous Windows Runtime methods</span></span>  

[!INCLUDE [deprecation-note](../includes/legacy-edge-note.md)]  

<span data-ttu-id="b94f9-103">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span><span class="sxs-lookup"><span data-stu-id="b94f9-103">It can be difficult to debug asynchronous Windows Runtime methods in JavaScript, because the error may be thrown from somewhere deep in the call stack.</span></span>  <span data-ttu-id="b94f9-104">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span><span class="sxs-lookup"><span data-stu-id="b94f9-104">The JavaScript `Error` object has extra properties that appear only when the error is thrown from an asynchronous Windows Runtime method when the app is running in debug mode.</span></span>  
  
## <span data-ttu-id="b94f9-105">Special error properties</span><span class="sxs-lookup"><span data-stu-id="b94f9-105">Special error properties</span></span>  

<span data-ttu-id="b94f9-106">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span><span class="sxs-lookup"><span data-stu-id="b94f9-106">An error object that results from a failed Windows Runtime asynchronous operation in debug mode has the following special properties:</span></span>  

*   `asyncOpSource` <span data-ttu-id="b94f9-107">\(Object\) Gets information about the original location where the call that produced an error was made.</span><span class="sxs-lookup"><span data-stu-id="b94f9-107">\(Object\) Gets information about the original location where the call that produced an error was made.</span></span>  <span data-ttu-id="b94f9-108">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span><span class="sxs-lookup"><span data-stu-id="b94f9-108">The property `asyncOpSource.originatingCall` \(String\) displays the location in the user's code that originated the asynchronous operation.</span></span>  
*   <span data-ttu-id="b94f9-109">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span><span class="sxs-lookup"><span data-stu-id="b94f9-109">asyncOpType \(String\) Gets the name of the asynchronous operation type that raised the error.</span></span>  
    
<span data-ttu-id="b94f9-110">For more information about errors with asynchronous operations, see:</span><span class="sxs-lookup"><span data-stu-id="b94f9-110">For more information about errors with asynchronous operations, see:</span></span>  
  
*   [<span data-ttu-id="b94f9-111">How to handle errors with promises</span><span class="sxs-lookup"><span data-stu-id="b94f9-111">How to handle errors with promises</span></span>][PreviousVersionsWindowsAppsHh700337]  
*   [<span data-ttu-id="b94f9-112">Troubleshooting Windows Runtime errors</span><span class="sxs-lookup"><span data-stu-id="b94f9-112">Troubleshooting Windows Runtime errors</span></span>][PreviousVersionsWindowsAppsHh974350]  

<!-- links -->  

[PreviousVersionsWindowsAppsHh700337]: /previous-versions/windows/apps/hh700337(v=win.10) "How to handle errors with promises (HTML) | Microsoft Docs"  
[PreviousVersionsWindowsAppsHh974350]: /previous-versions/windows/apps/hh974350(v=win.10) "Troubleshooting Windows Runtime errors (HTML) | Microsoft Docs"  
