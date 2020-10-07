---
title: Find and fix problems with the Microsoft Edge DevTools Issues tool
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: bad9e9d99f0d2f3179784920fc334823289b9f99
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992818"
---
<!-- Copyright Sam Dutton 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->  

# <span data-ttu-id="a8c0b-103">Find and fix problems with the Microsoft Edge DevTools Issues tool</span><span class="sxs-lookup"><span data-stu-id="a8c0b-103">Find and fix problems with the Microsoft Edge DevTools Issues tool</span></span>  

<span data-ttu-id="a8c0b-104">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-104">The **Issues** tool in Microsoft Edge DevTools reduces the notification fatigue and clutter of the **Console**.</span></span>  <span data-ttu-id="a8c0b-105">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-105">Use it to find solutions to problems detected by the browser, such as cookie issues and mixed content.</span></span>  

> [!NOTE]
> <span data-ttu-id="a8c0b-106">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span><span class="sxs-lookup"><span data-stu-id="a8c0b-106">In Microsoft Edge 84, the **Issues** tool supports three types of issue:</span></span>  
> *   [<span data-ttu-id="a8c0b-107">Cookie problems</span><span class="sxs-lookup"><span data-stu-id="a8c0b-107">Cookie problems</span></span>][MDNSameSiteCookies]  
> *   [<span data-ttu-id="a8c0b-108">Mixed content</span><span class="sxs-lookup"><span data-stu-id="a8c0b-108">Mixed content</span></span>][MDNMixedContent]  
> *   [<span data-ttu-id="a8c0b-109">COEP issues</span><span class="sxs-lookup"><span data-stu-id="a8c0b-109">COEP issues</span></span>][W3CCOEPSpec]
> 
> <span data-ttu-id="a8c0b-110">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-110">The Microsoft Edge DevTools team plans to support more issue types in future versions of Microsoft Edge.</span></span>  

## <span data-ttu-id="a8c0b-111">Open the Issues tool in the DevTools drawer</span><span class="sxs-lookup"><span data-stu-id="a8c0b-111">Open the Issues tool in the DevTools drawer</span></span>  

1.  <span data-ttu-id="a8c0b-112">Visit a page, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-112">Visit a page, such as [samesite-sandbox.glitch.me][GlitchSamesiteSandbox], that contains issues to fix.</span></span>  
1.  <span data-ttu-id="a8c0b-113">[Open DevTools][DevtoolsOpen].</span><span class="sxs-lookup"><span data-stu-id="a8c0b-113">[Open DevTools][DevtoolsOpen].</span></span>  
1.  :::row:::
       :::column span="":::
          <span data-ttu-id="a8c0b-114">Select the **Go to Issues** button in the yellow warning bar.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-114">Select the **Go to Issues** button in the yellow warning bar.</span></span>  
          
          :::image type="complex" source="../media/issues-open-issues-tab.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-open-issues-tab.msft.png":::
             <span data-ttu-id="a8c0b-116">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-116">The **Go to Issues** button in the yellow warning bar when Issues are detected.</span></span>  
          :::image-end:::  
       :::column-end:::
       :::column span="":::
          <span data-ttu-id="a8c0b-117">Alternatively, select **Issues** from the **More tools** menu.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-117">Alternatively, select **Issues** from the **More tools** menu.</span></span>  
          
          :::image type="complex" source="../media//issues-more-tools-menu.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media//issues-more-tools-menu.msft.png":::
             <span data-ttu-id="a8c0b-119">**Issues** tool in **More tools** menu</span><span class="sxs-lookup"><span data-stu-id="a8c0b-119">**Issues** tool in **More tools** menu</span></span>  
          :::image-end:::  
       :::column-end:::
    :::row-end:::
    
1.  <span data-ttu-id="a8c0b-120">Select the **Reload page** button, if necessary.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-120">Select the **Reload page** button, if necessary.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-before-refresh.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-tab-before-refresh.msft.png":::
       <span data-ttu-id="a8c0b-122">**Issues** tool in the DevTools Drawer with **Reload page** button</span><span class="sxs-lookup"><span data-stu-id="a8c0b-122">**Issues** tool in the DevTools Drawer with **Reload page** button</span></span>  
    :::image-end:::  

    <span data-ttu-id="a8c0b-123">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-123">The issues reported in the **Console** are quite hard to understand, such as the cookie warnings in the following image.</span></span>  <span data-ttu-id="a8c0b-124">Based upon the reported issues, it may not be clear what you must do.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-124">Based upon the reported issues, it may not be clear what you must do.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-after-refresh.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-tab-after-refresh.msft.png":::
       <span data-ttu-id="a8c0b-126">**Issues** tool in the DevTools Drawer with three cookie issues</span><span class="sxs-lookup"><span data-stu-id="a8c0b-126">**Issues** tool in the DevTools Drawer with three cookie issues</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a8c0b-127">View items in the Issues tool</span><span class="sxs-lookup"><span data-stu-id="a8c0b-127">View items in the Issues tool</span></span>  

<span data-ttu-id="a8c0b-128">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-128">The **Issues** tool in the DevTools Drawer presents warnings in a structured, aggregated, and actionable way.</span></span>  

1.  <span data-ttu-id="a8c0b-129">Select an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-129">Select an item in the **Issues** tool to get guidance on how to fix the issue and find affected resources.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-issue-open.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-tab-issue-open.msft.png":::
       <span data-ttu-id="a8c0b-131">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span><span class="sxs-lookup"><span data-stu-id="a8c0b-131">**Mark cross-site cookies as Secure** issue open in the **Issues** tool</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="a8c0b-132">Each item has four components:</span><span class="sxs-lookup"><span data-stu-id="a8c0b-132">Each item has four components:</span></span>  
    
    *   <span data-ttu-id="a8c0b-133">A headline describing the issue.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-133">A headline describing the issue.</span></span>  
    *   <span data-ttu-id="a8c0b-134">A description providing the context and the solution.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-134">A description providing the context and the solution.</span></span>  
    *   <span data-ttu-id="a8c0b-135">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-135">An **AFFECTED RESOURCES** section that links to resources within the appropriate DevTools context such as the Network panel.</span></span>  
    *   <span data-ttu-id="a8c0b-136">Links to further guidance.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-136">Links to further guidance.</span></span>  
    
1.  <span data-ttu-id="a8c0b-137">Select items in **AFFECTED RESOURCES** to view details.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-137">Select items in **AFFECTED RESOURCES** to view details.</span></span>  <span data-ttu-id="a8c0b-138">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-138">In the following example, the **Mark cross-site cookies as Secure** issue affects one cookie and two requests.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-affected-resources.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-tab-affected-resources.msft.png":::
       <span data-ttu-id="a8c0b-140">Affected resources open in the **Issues** tool in the DevTools Drawer</span><span class="sxs-lookup"><span data-stu-id="a8c0b-140">Affected resources open in the **Issues** tool in the DevTools Drawer</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="a8c0b-141">View issues in context</span><span class="sxs-lookup"><span data-stu-id="a8c0b-141">View issues in context</span></span>  

1.  <span data-ttu-id="a8c0b-142">Select a resource link to view the item in the appropriate context within DevTools.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-142">Select a resource link to view the item in the appropriate context within DevTools.</span></span>  <span data-ttu-id="a8c0b-143">In the following example, select `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-143">In the following example, select `samesite-sandbox.glitch.me` under **Requests** to show the cookies attached to that request.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-request.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-tab-view-request.msft.png":::
       <span data-ttu-id="a8c0b-145">View the affected cookie in the DevTools **Network** panel</span><span class="sxs-lookup"><span data-stu-id="a8c0b-145">View the affected cookie in the DevTools **Network** panel</span></span>  
    :::image-end:::  

1.  <span data-ttu-id="a8c0b-146">Scroll to view the item with a problem: for the following example, the `ck02` cookie.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-146">Scroll to view the item with a problem: for the following example, the `ck02` cookie.</span></span>  <span data-ttu-id="a8c0b-147">Hover over the **SameSite** column to see the `None` value that the issue detected.</span><span class="sxs-lookup"><span data-stu-id="a8c0b-147">Hover over the **SameSite** column to see the `None` value that the issue detected.</span></span>  
    
    :::image type="complex" source="../media/issues-tab-view-issue.msft.png" alt-text="Go to Issues button in yellow warning bar when Issues are detected" lightbox="../media/issues-tab-view-issue.msft.png":::
       `None` <span data-ttu-id="a8c0b-149">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** panel</span><span class="sxs-lookup"><span data-stu-id="a8c0b-149">value in the **SameSite** column for the `ck02` cookie in the DevTools **Network** panel</span></span>  
    :::image-end:::  

## <span data-ttu-id="a8c0b-150">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="a8c0b-150">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsOpen]: ../open.md "Open Microsoft Edge DevTools | Microsoft Docs"  

[GlitchSamesiteSandbox]: https://samesite-sandbox.glitch.me "SameSite cookie tests | Glitch"  

[MDNSameSiteCookies]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Set-Cookie/SameSite "SameSite cookies | MDN"  
[MDNMixedContent]: https://developer.mozilla.org/docs/Web/Security/Mixed_content "Mixed content | MDN"  

[W3CCOEPSpec]: https://wicg.github.io/cross-origin-embedder-policy "Cross-Origin Embedder Policy | Web Incubator Community Group"  

> [!NOTE]
> <span data-ttu-id="a8c0b-156">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="a8c0b-156">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="a8c0b-157">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span><span class="sxs-lookup"><span data-stu-id="a8c0b-157">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/issues/index) and is authored by [Sam Dutton][SamDutton] \(Developer Advocate\).</span></span>  
[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="a8c0b-159">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="a8c0b-159">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[SamDutton]: https://developers.google.com/web/resources/contributors/samdutton  
