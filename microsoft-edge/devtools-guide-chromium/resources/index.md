---
description: Organize resources by frame, domain, type, or other criteria.
title: View Page Resources With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 4f90927cc4044c722d9a62ab4b0427aa2753e4c5
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993588"
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





# <span data-ttu-id="8a3ae-104">View page resources with Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="8a3ae-104">View page resources with Microsoft Edge DevTools</span></span>   

  

<span data-ttu-id="8a3ae-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-105">This guide teaches you how to use Microsoft Edge DevTools to view the resources of a web page.</span></span>  <span data-ttu-id="8a3ae-106">Resources are the files that a page needs in order to display correctly.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-106">Resources are the files that a page needs in order to display correctly.</span></span>  <span data-ttu-id="8a3ae-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-107">Examples of resources include CSS, JavaScript, and HTML files, as well as images.</span></span>  

<span data-ttu-id="8a3ae-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span><span class="sxs-lookup"><span data-stu-id="8a3ae-108">This guide assumes that you are familiar with the basics of [web development][MDNLearnWebDevelopment] and [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="8a3ae-109">Open resources</span><span class="sxs-lookup"><span data-stu-id="8a3ae-109">Open resources</span></span>   

<span data-ttu-id="8a3ae-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-110">When you know the name of the resource that you want to inspect, the **Command Menu** provides a fast way of opening the resource.</span></span>  

1.  <span data-ttu-id="8a3ae-111">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="8a3ae-111">Press `Control`+`P` \(Windows\) or `Command`+`P` \(macOS\).</span></span>  <span data-ttu-id="8a3ae-112">The **Open File** dialog opens.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-112">The **Open File** dialog opens.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-empty.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-command-menu-empty.msft.png":::
       <span data-ttu-id="8a3ae-114">The **Open File** dialog</span><span class="sxs-lookup"><span data-stu-id="8a3ae-114">The **Open File** dialog</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a3ae-115">Select the file from the dropdown, or start typing the filename and press `Enter` once the correct file is highlighted in the autocomplete box.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-115">Select the file from the dropdown, or start typing the filename and press `Enter` once the correct file is highlighted in the autocomplete box.</span></span>  
    
    :::image type="complex" source="../media/resources-command-menu-file-search.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-command-menu-file-search.msft.png":::
       <span data-ttu-id="8a3ae-117">Type a filename in the **Open File** dialog</span><span class="sxs-lookup"><span data-stu-id="8a3ae-117">Type a filename in the **Open File** dialog</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a3ae-118">Open resources in the Network panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-118">Open resources in the Network panel</span></span>   

<span data-ttu-id="8a3ae-119">See [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span><span class="sxs-lookup"><span data-stu-id="8a3ae-119">See [Inspect the details of a resource][DevtoolsNetworkInspectDetailsResource].</span></span>  

:::image type="complex" source="../media/resources-network-response.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-network-response.msft.png":::
   <span data-ttu-id="8a3ae-121">Inspect a resource in the **Network** panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-121">Inspect a resource in the **Network** panel</span></span>  
:::image-end:::  

### <span data-ttu-id="8a3ae-122">Reveal resources in the Network panel from other panels</span><span class="sxs-lookup"><span data-stu-id="8a3ae-122">Reveal resources in the Network panel from other panels</span></span>   

<span data-ttu-id="8a3ae-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-123">The [Browse resources](#browse-resources) section below shows you how to view resources from various parts of the DevTools UI.</span></span>  <span data-ttu-id="8a3ae-124">If you ever want to inspect a resource in the **Network** panel, right-click the resource and select **Reveal in Network panel**.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-124">If you ever want to inspect a resource in the **Network** panel, right-click the resource and select **Reveal in Network panel**.</span></span>  

:::image type="complex" source="../media/resources-sources-page-reveal-in-network-panel.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-sources-page-reveal-in-network-panel.msft.png":::
   **<span data-ttu-id="8a3ae-126">Reveal in Network panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-126">Reveal in Network panel</span></span>**  
:::image-end:::  

## <span data-ttu-id="8a3ae-127">Browse resources</span><span class="sxs-lookup"><span data-stu-id="8a3ae-127">Browse resources</span></span>   

### <span data-ttu-id="8a3ae-128">Browse resources in the Network panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-128">Browse resources in the Network panel</span></span>   

<span data-ttu-id="8a3ae-129">See [Log network activity][DevtoolsNetworkLogActivity].</span><span class="sxs-lookup"><span data-stu-id="8a3ae-129">See [Log network activity][DevtoolsNetworkLogActivity].</span></span>  

:::image type="complex" source="../media/resources-network-resources.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-network-resources.msft.png":::
   <span data-ttu-id="8a3ae-131">Page resources in the **Network** Log</span><span class="sxs-lookup"><span data-stu-id="8a3ae-131">Page resources in the **Network** Log</span></span>  
:::image-end:::  

### <span data-ttu-id="8a3ae-132">Browse by directory</span><span class="sxs-lookup"><span data-stu-id="8a3ae-132">Browse by directory</span></span>   

<span data-ttu-id="8a3ae-133">To view the resources of a page organized by directory:</span><span class="sxs-lookup"><span data-stu-id="8a3ae-133">To view the resources of a page organized by directory:</span></span>  

1.  <span data-ttu-id="8a3ae-134">Click the **Sources** tab to open the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-134">Click the **Sources** tab to open the **Sources** panel.</span></span>  
1.  <span data-ttu-id="8a3ae-135">Click the **Page** tab to show the resources of the page.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-135">Click the **Page** tab to show the resources of the page.</span></span>  <span data-ttu-id="8a3ae-136">The **Page** pane opens.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-136">The **Page** pane opens.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-empty.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-sources-page-empty.msft.png":::
       <span data-ttu-id="8a3ae-138">The **Page** pane</span><span class="sxs-lookup"><span data-stu-id="8a3ae-138">The **Page** pane</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8a3ae-139">Here is a breakdown of the non-obvious items in the previous figure.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-139">Here is a breakdown of the non-obvious items in the previous figure.</span></span>  
    
    | <span data-ttu-id="8a3ae-140">Page item</span><span class="sxs-lookup"><span data-stu-id="8a3ae-140">Page item</span></span> | <span data-ttu-id="8a3ae-141">Description</span><span class="sxs-lookup"><span data-stu-id="8a3ae-141">Description</span></span> |  
    |:--- |:--- |  
    | `top` | <span data-ttu-id="8a3ae-142">The main document [browsing context][MDNInlineFrame].</span><span class="sxs-lookup"><span data-stu-id="8a3ae-142">The main document [browsing context][MDNInlineFrame].</span></span> |  
    | `airhorner.com` | <span data-ttu-id="8a3ae-143">The domain.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-143">The domain.</span></span>  <span data-ttu-id="8a3ae-144">All resources nested under it come from that domain.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-144">All resources nested under it come from that domain.</span></span>  <span data-ttu-id="8a3ae-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-145">For example, the full URL of the `comlink.global.j` file is probably `https://airhorner.com/scripts/comlink.global.js`.</span></span> |  
    | `scripts` | <span data-ttu-id="8a3ae-146">A directory.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-146">A directory.</span></span> |  
    | `(index)` | <span data-ttu-id="8a3ae-147">The main HTML document.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-147">The main HTML document.</span></span> |  
    | `sw.js` | <span data-ttu-id="8a3ae-148">A service worker runtime context.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-148">A service worker runtime context.</span></span> |  
    
1.  <span data-ttu-id="8a3ae-149">Click a resource to view it in the **Editor**.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-149">Click a resource to view it in the **Editor**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-sources-page-resource.msft.png":::
       <span data-ttu-id="8a3ae-151">View a file in the **Editor**</span><span class="sxs-lookup"><span data-stu-id="8a3ae-151">View a file in the **Editor**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a3ae-152">Browse by filename</span><span class="sxs-lookup"><span data-stu-id="8a3ae-152">Browse by filename</span></span>   

<span data-ttu-id="8a3ae-153">By default the **Page** pane groups resources by directory.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-153">By default the **Page** pane groups resources by directory.</span></span>  <span data-ttu-id="8a3ae-154">To disable this grouping and view the resources for each domain as a flat list:</span><span class="sxs-lookup"><span data-stu-id="8a3ae-154">To disable this grouping and view the resources for each domain as a flat list:</span></span>  

1.  <span data-ttu-id="8a3ae-155">Open the **Page** pane.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-155">Open the **Page** pane.</span></span>  <span data-ttu-id="8a3ae-156">See [Browse by directory](#browse-by-directory).</span><span class="sxs-lookup"><span data-stu-id="8a3ae-156">See [Browse by directory](#browse-by-directory).</span></span>  
1.  <span data-ttu-id="8a3ae-157">Click **More Options** `...` and disable **Group By Folder**.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-157">Click **More Options** `...` and disable **Group By Folder**.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resource-group-by-folder.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-sources-page-resource-group-by-folder.msft.png":::
       <span data-ttu-id="8a3ae-159">The **Group By Folder** option</span><span class="sxs-lookup"><span data-stu-id="8a3ae-159">The **Group By Folder** option</span></span>  
    :::image-end:::  
    
    <span data-ttu-id="8a3ae-160">Resources are organized by file type.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-160">Resources are organized by file type.</span></span>  <span data-ttu-id="8a3ae-161">Within each file type the resources are organized alphabetically.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-161">Within each file type the resources are organized alphabetically.</span></span>  
    
    :::image type="complex" source="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-sources-page-resources-empty-not-grouped-by-folder.msft.png":::
       <span data-ttu-id="8a3ae-163">The **Page** pane after disabling **Group By Folder**</span><span class="sxs-lookup"><span data-stu-id="8a3ae-163">The **Page** pane after disabling **Group By Folder**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="8a3ae-164">Browse by file type</span><span class="sxs-lookup"><span data-stu-id="8a3ae-164">Browse by file type</span></span>   

<span data-ttu-id="8a3ae-165">To group resources together based on their file type:</span><span class="sxs-lookup"><span data-stu-id="8a3ae-165">To group resources together based on their file type:</span></span>  

1.  <span data-ttu-id="8a3ae-166">Click the **Application** tab.  The **Application** panel opens.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-166">Click the **Application** tab.  The **Application** panel opens.</span></span>  <span data-ttu-id="8a3ae-167">By default the **Manifest** pane usually opens first.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-167">By default the **Manifest** pane usually opens first.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-application-mainfest-airhorner.msft.png":::
       <span data-ttu-id="8a3ae-169">The **Application** panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-169">The **Application** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a3ae-170">Scroll down to the **Frames** pane.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-170">Scroll down to the **Frames** pane.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-application-mainfest-airhorner-frames-expanded.msft.png":::
       <span data-ttu-id="8a3ae-172">The **Frames** pane</span><span class="sxs-lookup"><span data-stu-id="8a3ae-172">The **Frames** pane</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="8a3ae-173">Expand the sections in which you are interested.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-173">Expand the sections in which you are interested.</span></span>  
1.  <span data-ttu-id="8a3ae-174">Click a resource to view it.</span><span class="sxs-lookup"><span data-stu-id="8a3ae-174">Click a resource to view it.</span></span>  
    
    :::image type="complex" source="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-application-mainfest-airhorner-expanded-resources.msft.png":::
       <span data-ttu-id="8a3ae-176">View a resource in the **Application** panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-176">View a resource in the **Application** panel</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="8a3ae-177">Browse files by type in the Network panel</span><span class="sxs-lookup"><span data-stu-id="8a3ae-177">Browse files by type in the Network panel</span></span>   

<span data-ttu-id="8a3ae-178">See [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span><span class="sxs-lookup"><span data-stu-id="8a3ae-178">See [Filter by resource type][DevtoolsNetworkFilterByResourceType].</span></span>  

:::image type="complex" source="../media/resources-network-resources-filter-css.msft.png" alt-text="The Open File dialog" lightbox="../media/resources-network-resources-filter-css.msft.png":::
   <span data-ttu-id="8a3ae-180">Filter for CSS in the **Network** Log</span><span class="sxs-lookup"><span data-stu-id="8a3ae-180">Filter for CSS in the **Network** Log</span></span>  
:::image-end:::  

<!--  
  


-->  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer tools | Microsoft Docs"  
[DevtoolsNetworkFilterByResourceType]: ../network/index.md#filter-by-resource-type "Filter by resource type - Inspect network activity in Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsNetworkInspectDetailsResource]: ../network/index.md#inspect-the-details-of-the-resource "Inspect the details of the resource - Inspect network activity in Microsoft Edge DevTools | Microsoft Docs"  
[DevtoolsNetworkLogActivity]: ../network/index.md#log-network-activity "Log network activity - Inspect network activity in Microsoft Edge DevTools | Microsoft Docs"  

[MDNInlineFrame]: https://developer.mozilla.org/docs/Web/HTML/Element/iframe "<iframe>: The Inline Frame element | MDN"  
[MDNLearnWebDevelopment]: https://developer.mozilla.org/docs/Learn "Learn web development | MDN"  

> [!NOTE]
> <span data-ttu-id="8a3ae-187">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8a3ae-187">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8a3ae-188">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/resources/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="8a3ae-188">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/resources/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8a3ae-190">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8a3ae-190">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
