---
description: 如果您发现自己重复在控制台中键入相同的 JavaScript 表达式，请尝试改用实时表达式。
title: 实时监视 JavaScript 表达式值和实时表达式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 6b66c44b77cd50bc0c1575e5eceb7c8d1a01b709
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993112"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# <span data-ttu-id="7ef94-104">实时监视 JavaScript 表达式值和实时表达式</span><span class="sxs-lookup"><span data-stu-id="7ef94-104">Watch JavaScript Expression Values In Real-Time With Live Expressions</span></span>   

  

<span data-ttu-id="7ef94-105">如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建 **实时表达式**变得更容易。</span><span class="sxs-lookup"><span data-stu-id="7ef94-105">If you find yourself typing the same JavaScript expression in the Console repeatedly, you might find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="7ef94-106">使用 **实时表达式** ，您只需要键入一个表达式，然后将其固定到您的控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="7ef94-106">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="7ef94-107">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="7ef94-107">The value of the expression updates in near real-time.</span></span>  

## <span data-ttu-id="7ef94-108">创建实时表达式</span><span class="sxs-lookup"><span data-stu-id="7ef94-108">Create a Live Expression</span></span>   

1.  <span data-ttu-id="7ef94-109">[打开控制台][DevToolsConsoleReferenceOpenConsole]。</span><span class="sxs-lookup"><span data-stu-id="7ef94-109">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="7ef94-110">单击 " **创建实时表达式** \ (![ 创建实时表达式 ][ImageCreateLiveExpressionIcon] \ ) "。</span><span class="sxs-lookup"><span data-stu-id="7ef94-110">Click **Create Live Expression** \(![Create Live Expression][ImageCreateLiveExpressionIcon]\).</span></span>  <span data-ttu-id="7ef94-111">将显示 " **活动表达式** " 文本框。</span><span class="sxs-lookup"><span data-stu-id="7ef94-111">The **Live Expression** text box appears.</span></span>  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="在 "活动表达式" 文本框中键入 activeElement" lightbox="../media/console-create-live-expression.msft.png":::
       <span data-ttu-id="7ef94-113">`document.activeElement`在 "**活动表达式**" 文本框中键入</span><span class="sxs-lookup"><span data-stu-id="7ef94-113">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="7ef94-114">键入 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 保存表达式，或在 "**实时表达式**" 文本框外单击。</span><span class="sxs-lookup"><span data-stu-id="7ef94-114">Type `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save the expression, or click outside of the **Live Expression** text box.</span></span>  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "打开控制台-控制台参考 |Microsoft 文档"  

> [!NOTE]
> <span data-ttu-id="7ef94-116">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="7ef94-116">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="7ef94-117">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="7ef94-117">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="7ef94-119">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="7ef94-119">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
