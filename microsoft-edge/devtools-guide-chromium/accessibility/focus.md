---
description: Open the Console, create a Live Expression, and set the expression to document.activeElement.
title: Track Which Element Has Focus
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 9000b8ca1fa52daf5257f201c65dcabd78298ec7
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993203"
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

# <span data-ttu-id="adaa7-104">Track Which Element Has Focus</span><span class="sxs-lookup"><span data-stu-id="adaa7-104">Track Which Element Has Focus</span></span>  

<span data-ttu-id="adaa7-105">Suppose that you are testing the keyboard navigation accessibility of a page.</span><span class="sxs-lookup"><span data-stu-id="adaa7-105">Suppose that you are testing the keyboard navigation accessibility of a page.</span></span>  <span data-ttu-id="adaa7-106">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span><span class="sxs-lookup"><span data-stu-id="adaa7-106">When navigating the page with the `Tab` key, the focus ring sometimes disappears because the element that has focus is hidden.</span></span>  

<span data-ttu-id="adaa7-107">Complete the following actions to track the focused element in DevTools.</span><span class="sxs-lookup"><span data-stu-id="adaa7-107">Complete the following actions to track the focused element in DevTools.</span></span>  

1.  <span data-ttu-id="adaa7-108">Open the **Console**.</span><span class="sxs-lookup"><span data-stu-id="adaa7-108">Open the **Console**.</span></span>  
1.  <span data-ttu-id="adaa7-109">Click **Create Live Expression** \(![Create Live Expression][ImageCreateIcon]\).</span><span class="sxs-lookup"><span data-stu-id="adaa7-109">Click **Create Live Expression** \(![Create Live Expression][ImageCreateIcon]\).</span></span>  
    
    :::image type="complex" source="../media/accessibility-console-create-live-expression-empty.msft.png" alt-text="Create a Live Expression" lightbox="../media/accessibility-console-create-live-expression-empty.msft.png":::
       <span data-ttu-id="adaa7-111">Create a Live Expression</span><span class="sxs-lookup"><span data-stu-id="adaa7-111">Create a Live Expression</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="adaa7-112">Type `document.activeElement`.</span><span class="sxs-lookup"><span data-stu-id="adaa7-112">Type `document.activeElement`.</span></span>  
1.  <span data-ttu-id="adaa7-113">Click outside of the **Live Expression** UI to save.</span><span class="sxs-lookup"><span data-stu-id="adaa7-113">Click outside of the **Live Expression** UI to save.</span></span>  
    
<span data-ttu-id="adaa7-114">The value that you see below `document.activeElement` is the result of the expression.</span><span class="sxs-lookup"><span data-stu-id="adaa7-114">The value that you see below `document.activeElement` is the result of the expression.</span></span>  

<span data-ttu-id="adaa7-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span><span class="sxs-lookup"><span data-stu-id="adaa7-115">Since that expression always represents the focused element, you now have a way to always keep track of which element has focus.</span></span>  

*   <span data-ttu-id="adaa7-116">Hover over the result to highlight the focused element in the viewport.</span><span class="sxs-lookup"><span data-stu-id="adaa7-116">Hover over the result to highlight the focused element in the viewport.</span></span>  
*   <span data-ttu-id="adaa7-117">Right-click the result and select **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** panel.</span><span class="sxs-lookup"><span data-stu-id="adaa7-117">Right-click the result and select **Reveal in Elements panel** to show the element in the DOM Tree on the **Elements** panel.</span></span>  
*   <span data-ttu-id="adaa7-118">Right-click the result and select **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span><span class="sxs-lookup"><span data-stu-id="adaa7-118">Right-click the result and select **Store as global variable** to create a variable reference to the node that you are able to use in the **Console**.</span></span>  

## <span data-ttu-id="adaa7-119">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="adaa7-119">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageCreateIcon]: ../media/create-live-expression-icon.msft.png  

<!-- links -->  

> [!NOTE]
> <span data-ttu-id="adaa7-120">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="adaa7-120">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="adaa7-121">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="adaa7-121">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/accessibility/focus) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="adaa7-123">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="adaa7-123">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
