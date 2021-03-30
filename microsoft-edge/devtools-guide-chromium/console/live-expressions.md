---
description: 如果发现自己在控制台中重复键入相同的JavaScript表达式，请尝试使用动态表达式。
title: 使用动态表达式实时监视 JavaScript 表达式值
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge,web 开发,f12 工具,开发工具
ms.openlocfilehash: af920de1c395489dc09b83f3cc0f24814c4f5cbe
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439224"
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

# <a name="watch-javascript-expression-values-in-real-time-with-live-expressions"></a><span data-ttu-id="10177-104">使用动态表达式实时监视 JavaScript 表达式值</span><span class="sxs-lookup"><span data-stu-id="10177-104">Watch JavaScript expression values in real-time with Live Expressions</span></span>  

<span data-ttu-id="10177-105">如果发现自己在控制台中重复键入相同的JavaScript表达式，则可能会发现创建**实时表达式**更容易。</span><span class="sxs-lookup"><span data-stu-id="10177-105">If you find yourself typing the same JavaScript expression in the Console repeatedly, you may find it easier to create a **Live Expression**.</span></span>  <span data-ttu-id="10177-106">使用**实时表达式**键入表达式一次，然后将其固定到控制台顶部。</span><span class="sxs-lookup"><span data-stu-id="10177-106">With **Live Expressions** you type an expression once and then pin it to the top of your Console.</span></span>  <span data-ttu-id="10177-107">表达式的值几乎实时更新。</span><span class="sxs-lookup"><span data-stu-id="10177-107">The value of the expression updates in near real-time.</span></span>  

## <a name="create-a-live-expression"></a><span data-ttu-id="10177-108">创建动态表达式</span><span class="sxs-lookup"><span data-stu-id="10177-108">Create a Live Expression</span></span>  

1.  <span data-ttu-id="10177-109">[打开控制台][DevToolsConsoleReferenceOpenConsole]。</span><span class="sxs-lookup"><span data-stu-id="10177-109">[Open the Console][DevToolsConsoleReferenceOpenConsole].</span></span>  
1.  <span data-ttu-id="10177-110">选择“**创建动态表达式**” \(![创建动态表达式](../media/create-live-expression-icon.msft.png)\)。</span><span class="sxs-lookup"><span data-stu-id="10177-110">Choose **Create Live Expression** \(![Create Live Expression](../media/create-live-expression-icon.msft.png)\).</span></span>  <span data-ttu-id="10177-111">“**创建动态表达式**”文本框出现。</span><span class="sxs-lookup"><span data-stu-id="10177-111">The **Live Expression** text box appears.</span></span>  
    
    :::image type="complex" source="../media/console-create-live-expression.msft.png" alt-text="在动态表达式文本框中键入 document.activeElement" lightbox="../media/console-create-live-expression.msft.png":::
       <span data-ttu-id="10177-113">将 `document.activeElement` 键入**动态表达式**文本框</span><span class="sxs-lookup"><span data-stu-id="10177-113">Typing `document.activeElement` into the **Live Expression** text box</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="10177-114">选择`Control`+`Enter` \(Windows、Linux\) 或 `Command`+`Enter` \(macOS\) 以保存表达式，或选择“ 动态表达式”文本框之外的内容。</span><span class="sxs-lookup"><span data-stu-id="10177-114">Select `Control`+`Enter` \(Windows, Linux\) or `Command`+`Enter` \(macOS\) to save the expression, or choose outside of the **Live Expression** textbox.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="10177-115">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="10177-115">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsConsoleReferenceOpenConsole]: ./reference.md#open-the-console "打开控制台 - 控制台参考 | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="10177-117">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="10177-117">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="10177-118">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="10177-118">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/console/live-expressions) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="10177-120">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="10177-120">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
