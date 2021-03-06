---
description: 如果发现自己在控制台中重复键入相同的 JavaScript 表达式，请尝试使用 Live Expressions。
title: 使用 Live Expressions 实时监视 JavaScript 表达式值
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 5bc49b60cc1c1dfb41c793c3fec7681fb6415e4c
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11398796"
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

# <a name="watch-javascript-expression-values-in-real-time-with-live-expressions"></a><span data-ttu-id="c08d5-104">使用 Live Expressions 实时监视 JavaScript 表达式值</span><span class="sxs-lookup"><span data-stu-id="c08d5-104">Watch JavaScript expression values in real-time with Live Expressions</span></span>  

<span data-ttu-id="c08d5-105">如果你发现自己在控制台中重复键入相同的 JavaScript 表达式，你可能会发现创建 Live **Expression**更容易。</span><span class="sxs-lookup"><span data-stu-id="c08d5-105">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="c08d5-106">使用 **Live Expressions，** 键入一次表达式，然后将其固定到控制台的顶部。</span><span class="sxs-lookup"><span data-stu-id="c08d5-106">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="c08d5-107">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="c08d5-107">The value of the expression updates in near real-time.</span></span>  

## <a name="create-a-live-expression"></a><span data-ttu-id="c08d5-108">创建动态表达式</span><span class="sxs-lookup"><span data-stu-id="c08d5-108">Create a Live Expression</span></span>  

1.  <span data-ttu-id="c08d5-109">[打开控制台][DevToolsConsoleReferenceOpenConsole]。</span><span class="sxs-lookup"><span data-stu-id="c08d5-109">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="c08d5-110">Choose **Create Live Expression** \ (Create Live Expression ![ ][ImageCreateLiveExpressionIcon] \) .</span><span class="sxs-lookup"><span data-stu-id="c08d5-110">Choose **Create Live Expression** \(![Create Live Expression][ImageCreateLiveExpressionIcon]\).</span></span>  <span data-ttu-id="c08d5-111">将显示 **"实时表达式** "文本框。</span><span class="sxs-lookup"><span data-stu-id="c08d5-111">The **Live Expression** text box appears.</span></span>  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="在 Live Expression 文本框中键入 document.activeElement" lightbox="../media/console-create-live-expression.msft.png":::
       <span data-ttu-id="c08d5-113">键入 `document.activeElement` Live **Expression** 文本框</span><span class="sxs-lookup"><span data-stu-id="c08d5-113">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="c08d5-114">选择 `Control` + `Enter` \ (Windows、Linux\) 或 `Command` + `Enter` \ (macOS\) \*\*\*\* 保存表达式，或在 Live Expression 文本框外部选择。</span><span class="sxs-lookup"><span data-stu-id="c08d5-114">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save the expression, or choose outside of the **Live Expression** textbox.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="c08d5-115">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="c08d5-115">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateLiveExpressionIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "打开控制台 - 控制台参考|Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="c08d5-117">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c08d5-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c08d5-118">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="c08d5-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="c08d5-120">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c08d5-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
