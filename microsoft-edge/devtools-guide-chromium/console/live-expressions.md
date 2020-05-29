---
title: 实时监视 JavaScript 表达式值和实时表达式
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/24/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: c388e44ca5507dd88ad9ad7b7ee985e658dfc569
ms.sourcegitcommit: 5cdc1626d5581b79c0f2ac4ea62e7f1974ebfa57
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/27/2020
ms.locfileid: "10601738"
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





# <span data-ttu-id="326c5-103">实时监视 JavaScript 表达式值和实时表达式</span><span class="sxs-lookup"><span data-stu-id="326c5-103">Watch JavaScript Expression Values In Real-Time With Live Expressions</span></span>   

  

<span data-ttu-id="326c5-104">如果您发现自己在控制台中重复键入相同的 JavaScript 表达式，您可能会发现创建**实时表达式**变得更容易。</span><span class="sxs-lookup"><span data-stu-id="326c5-104">If you find yourself typing the same JavaScript expression in the Console repeatedly, you might find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="326c5-105">使用**实时表达式**，您只需要键入一个表达式，然后将其固定到您的控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="326c5-105">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="326c5-106">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="326c5-106">The value of the expression updates in near real-time.</span></span>  

## <span data-ttu-id="326c5-107">创建实时表达式</span><span class="sxs-lookup"><span data-stu-id="326c5-107">Create a Live Expression</span></span>   

1.  <span data-ttu-id="326c5-108">[打开控制台][DevToolsConsoleReferenceOpenConsole]。</span><span class="sxs-lookup"><span data-stu-id="326c5-108">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="326c5-109">单击 "**创建实时表达式**" ![ 创建实时表达式 ][ImageCreateLiveExpressionIcon] 。</span><span class="sxs-lookup"><span data-stu-id="326c5-109">Click **Create Live Expression** ![Create Live Expression][ImageCreateLiveExpressionIcon].</span></span>  <span data-ttu-id="326c5-110">将显示 "**活动表达式**" 文本框。</span><span class="sxs-lookup"><span data-stu-id="326c5-110">The **Live Expression** text box appears.</span></span>  
    
    > ##### <span data-ttu-id="326c5-111">图 1</span><span class="sxs-lookup"><span data-stu-id="326c5-111">Figure 1</span></span>  
    > <span data-ttu-id="326c5-112">`document.activeElement`在 "**活动表达式**" 文本框中键入</span><span class="sxs-lookup"><span data-stu-id="326c5-112">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    > ![在 "活动表达式" 文本框中键入 activeElement][ImageLiveExpressionTextbox]  
    
1.  <span data-ttu-id="326c5-114">键入 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）保存表达式，或单击 "**实时表达式**" 文本框外部。</span><span class="sxs-lookup"><span data-stu-id="326c5-114">Type `Control`+`Enter` \(Windows\) or `Command`+`Enter` \(macOS\) to save the expression, or click outside of the **Live Expression** text box.</span></span>  

<!--todo: add reference open console (open the console) section when available  -->  

 



<!-- image links -->  

[ImageCreateLiveExpressionIcon]: /microsoft-edge/devtools-guide-chromium/media/create-live-expression-icon.msft.png  

[ImageLiveExpressionTextbox]: /microsoft-edge/devtools-guide-chromium/media/console-create-live-expression.msft.png "图1：在 "活动表达式" 文本框中键入 activeElement"  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: /microsoft-edge/devtools-guide-chromium/console/reference#open-the-console "打开控制台参考"  

> [!NOTE]
> <span data-ttu-id="326c5-117">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="326c5-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="326c5-118">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="326c5-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="326c5-120">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="326c5-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
