---
description: Identify expensive functions using the Microsoft Edge DevTools Memory panel.
title: Speed Up JavaScript Runtime
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 27afe999083470cde0cc0fabf76d0d1ab54e6562
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993581"
---
<!-- Copyright Kayce Basques and Meggin Kearney

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License. -->

# <span data-ttu-id="e00ff-104">Speed up JavaScript runtime</span><span class="sxs-lookup"><span data-stu-id="e00ff-104">Speed up JavaScript runtime</span></span>  

<span data-ttu-id="e00ff-105">Identify expensive functions using the **Memory** panel.</span><span class="sxs-lookup"><span data-stu-id="e00ff-105">Identify expensive functions using the **Memory** panel.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="e00ff-107">Sample Profiles</span><span class="sxs-lookup"><span data-stu-id="e00ff-107">Sample Profiles</span></span>  
:::image-end:::  

### <span data-ttu-id="e00ff-108">Summary</span><span class="sxs-lookup"><span data-stu-id="e00ff-108">Summary</span></span>  

*   <span data-ttu-id="e00ff-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span><span class="sxs-lookup"><span data-stu-id="e00ff-109">Record exactly which functions were called and how much memory each requires with Allocation Sampling in the **Memory** panel.</span></span>  
*   <span data-ttu-id="e00ff-110">Visualize your profiles as a flame chart.</span><span class="sxs-lookup"><span data-stu-id="e00ff-110">Visualize your profiles as a flame chart.</span></span>  
    
## <span data-ttu-id="e00ff-111">Record a Sampling Profile</span><span class="sxs-lookup"><span data-stu-id="e00ff-111">Record a Sampling Profile</span></span>  

<span data-ttu-id="e00ff-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span><span class="sxs-lookup"><span data-stu-id="e00ff-112">If you notice jank in your JavaScript, collect a Sampling Profile.</span></span>  <span data-ttu-id="e00ff-113">Sampling Profiles show where running time is spent on functions in your page.</span><span class="sxs-lookup"><span data-stu-id="e00ff-113">Sampling Profiles show where running time is spent on functions in your page.</span></span>  

1.  <span data-ttu-id="e00ff-114">Go to the **Memory** panel of DevTools.</span><span class="sxs-lookup"><span data-stu-id="e00ff-114">Go to the **Memory** panel of DevTools.</span></span>  
1.  <span data-ttu-id="e00ff-115">Select the **Allocation sampling** radio button.</span><span class="sxs-lookup"><span data-stu-id="e00ff-115">Select the **Allocation sampling** radio button.</span></span>  
1.  <span data-ttu-id="e00ff-116">Select **Start**.</span><span class="sxs-lookup"><span data-stu-id="e00ff-116">Select **Start**.</span></span>  
1.  <span data-ttu-id="e00ff-117">Depending on what you are trying to analyze, you may either reload the page, interact with the page, or just let the page run.</span><span class="sxs-lookup"><span data-stu-id="e00ff-117">Depending on what you are trying to analyze, you may either reload the page, interact with the page, or just let the page run.</span></span>  
1.  <span data-ttu-id="e00ff-118">Select the **Stop** button when you are finished.</span><span class="sxs-lookup"><span data-stu-id="e00ff-118">Select the **Stop** button when you are finished.</span></span>  
    
> [!NOTE]
> <span data-ttu-id="e00ff-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span><span class="sxs-lookup"><span data-stu-id="e00ff-119">You may also use the [Console Utilities API][DevtoolsConsoleUtilities] to record and group profiles from the command line.</span></span>  

## <span data-ttu-id="e00ff-120">View Sampling Profile</span><span class="sxs-lookup"><span data-stu-id="e00ff-120">View Sampling Profile</span></span>  

<span data-ttu-id="e00ff-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span><span class="sxs-lookup"><span data-stu-id="e00ff-121">When you finish recording, DevTools automatically populates the **Memory** panel under **SAMPLING PROFILES** with the data from your recording.</span></span>  

<span data-ttu-id="e00ff-122">The default view is **Heavy \(Bottom Up\)**.</span><span class="sxs-lookup"><span data-stu-id="e00ff-122">The default view is **Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="e00ff-123">This view enables you to see which functions had the most impact on performance and examine the calling paths to those functions.</span><span class="sxs-lookup"><span data-stu-id="e00ff-123">This view enables you to see which functions had the most impact on performance and examine the calling paths to those functions.</span></span>  

### <span data-ttu-id="e00ff-124">Change sort order</span><span class="sxs-lookup"><span data-stu-id="e00ff-124">Change sort order</span></span>  

<span data-ttu-id="e00ff-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function][ImageFocusIcon]\) icon and then choose one of the following options.</span><span class="sxs-lookup"><span data-stu-id="e00ff-125">To change the sorting order, select the dropdown menu next to the **focus selected function** \(![focus selected function][ImageFocusIcon]\) icon and then choose one of the following options.</span></span>

<span data-ttu-id="e00ff-126">**Chart**.</span><span class="sxs-lookup"><span data-stu-id="e00ff-126">**Chart**.</span></span>  <span data-ttu-id="e00ff-127">Displays a chronological chart of the recording.</span><span class="sxs-lookup"><span data-stu-id="e00ff-127">Displays a chronological chart of the recording.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="e00ff-129">Flame chart</span><span class="sxs-lookup"><span data-stu-id="e00ff-129">Flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="e00ff-130">**Heavy \(Bottom Up\)**.</span><span class="sxs-lookup"><span data-stu-id="e00ff-130">**Heavy \(Bottom Up\)**.</span></span>  <span data-ttu-id="e00ff-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span><span class="sxs-lookup"><span data-stu-id="e00ff-131">Lists functions by impact on performance and enables you to examine the calling paths to the functions.</span></span>  <span data-ttu-id="e00ff-132">This is the default view.</span><span class="sxs-lookup"><span data-stu-id="e00ff-132">This is the default view.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-heavy-bottom-up.msft.png":::
   <span data-ttu-id="e00ff-134">Heavy chart</span><span class="sxs-lookup"><span data-stu-id="e00ff-134">Heavy chart</span></span>  
:::image-end:::  

<span data-ttu-id="e00ff-135">**Tree \(Top Down\)**.</span><span class="sxs-lookup"><span data-stu-id="e00ff-135">**Tree \(Top Down\)**.</span></span>  <span data-ttu-id="e00ff-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span><span class="sxs-lookup"><span data-stu-id="e00ff-136">Shows an overall picture of the calling structure, starting at the top of the call stack.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-tree-top-down.msft.png":::
   <span data-ttu-id="e00ff-138">Tree chart</span><span class="sxs-lookup"><span data-stu-id="e00ff-138">Tree chart</span></span>  
:::image-end:::  

### <span data-ttu-id="e00ff-139">Exclude functions</span><span class="sxs-lookup"><span data-stu-id="e00ff-139">Exclude functions</span></span>  

<span data-ttu-id="e00ff-140">To exclude a function from your Sampling Profile, select it and then select the **exclude selected function** \(![exclude selected function][ImageExcludeIcon]\) button.</span><span class="sxs-lookup"><span data-stu-id="e00ff-140">To exclude a function from your Sampling Profile, select it and then select the **exclude selected function** \(![exclude selected function][ImageExcludeIcon]\) button.</span></span>  <span data-ttu-id="e00ff-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span><span class="sxs-lookup"><span data-stu-id="e00ff-141">The requesting function \(parent\) of the excluded function \(child\) is charged with the allocated memory assigned to the excluded function \(child\).</span></span>  

<span data-ttu-id="e00ff-142">Select the **restore all functions** \(![restore all functions][ImageRestoreIcon]\) button to restore all excluded functions back into the recording.</span><span class="sxs-lookup"><span data-stu-id="e00ff-142">Select the **restore all functions** \(![restore all functions][ImageRestoreIcon]\) button to restore all excluded functions back into the recording.</span></span>  

## <span data-ttu-id="e00ff-143">View Sampling Profile as Chart</span><span class="sxs-lookup"><span data-stu-id="e00ff-143">View Sampling Profile as Chart</span></span>  

<span data-ttu-id="e00ff-144">The Chart view provides a visual representation of the Sampling Profile over time.</span><span class="sxs-lookup"><span data-stu-id="e00ff-144">The Chart view provides a visual representation of the Sampling Profile over time.</span></span>  

<span data-ttu-id="e00ff-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span><span class="sxs-lookup"><span data-stu-id="e00ff-145">After you [record a Sampling Profile](#record-a-sampling-profile), view the recording as a flame chart by [changing the sort order](#change-sort-order) to **Chart**.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart.msft.png":::
   <span data-ttu-id="e00ff-147">Flame chart view</span><span class="sxs-lookup"><span data-stu-id="e00ff-147">Flame chart view</span></span>  
:::image-end:::  

<span data-ttu-id="e00ff-148">The flame chart is split into two parts.</span><span class="sxs-lookup"><span data-stu-id="e00ff-148">The flame chart is split into two parts.</span></span>  

| <span data-ttu-id="e00ff-149">index</span><span class="sxs-lookup"><span data-stu-id="e00ff-149">index</span></span> | <span data-ttu-id="e00ff-150">Part</span><span class="sxs-lookup"><span data-stu-id="e00ff-150">Part</span></span> | <span data-ttu-id="e00ff-151">Description</span><span class="sxs-lookup"><span data-stu-id="e00ff-151">Description</span></span> |  
| --- |:--- |:--- |  
| <span data-ttu-id="e00ff-152">1</span><span class="sxs-lookup"><span data-stu-id="e00ff-152">1</span></span> | <span data-ttu-id="e00ff-153">Overview</span><span class="sxs-lookup"><span data-stu-id="e00ff-153">Overview</span></span> | <span data-ttu-id="e00ff-154">A birds-eye view of the entire recording.</span><span class="sxs-lookup"><span data-stu-id="e00ff-154">A birds-eye view of the entire recording.</span></span>  <span data-ttu-id="e00ff-155">The height of the bars correspond to the depth of the call stack.</span><span class="sxs-lookup"><span data-stu-id="e00ff-155">The height of the bars correspond to the depth of the call stack.</span></span>  <span data-ttu-id="e00ff-156">So, the higher the bar, the deeper the call stack.</span><span class="sxs-lookup"><span data-stu-id="e00ff-156">So, the higher the bar, the deeper the call stack.</span></span>  |  
| <span data-ttu-id="e00ff-157">2</span><span class="sxs-lookup"><span data-stu-id="e00ff-157">2</span></span> | <span data-ttu-id="e00ff-158">Call Stacks</span><span class="sxs-lookup"><span data-stu-id="e00ff-158">Call Stacks</span></span> | <span data-ttu-id="e00ff-159">This is an in-depth view of the functions that were called during the recording.</span><span class="sxs-lookup"><span data-stu-id="e00ff-159">This is an in-depth view of the functions that were called during the recording.</span></span>  <span data-ttu-id="e00ff-160">The horizontal axis is time and vertical axis is the call stack.</span><span class="sxs-lookup"><span data-stu-id="e00ff-160">The horizontal axis is time and vertical axis is the call stack.</span></span>  <span data-ttu-id="e00ff-161">The stacks are organized top-down.</span><span class="sxs-lookup"><span data-stu-id="e00ff-161">The stacks are organized top-down.</span></span>  <span data-ttu-id="e00ff-162">So, the function on top called the one below it, and so on.</span><span class="sxs-lookup"><span data-stu-id="e00ff-162">So, the function on top called the one below it, and so on.</span></span>  |  

<span data-ttu-id="e00ff-163">Functions are colored randomly.</span><span class="sxs-lookup"><span data-stu-id="e00ff-163">Functions are colored randomly.</span></span>  <span data-ttu-id="e00ff-164">There is no correlation to the colors used in the other panels.</span><span class="sxs-lookup"><span data-stu-id="e00ff-164">There is no correlation to the colors used in the other panels.</span></span>  <span data-ttu-id="e00ff-165">However, functions are always colored the same across invocations so that you are able to see patterns in each runtime.</span><span class="sxs-lookup"><span data-stu-id="e00ff-165">However, functions are always colored the same across invocations so that you are able to see patterns in each runtime.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-highlighted.msft.png":::
   <span data-ttu-id="e00ff-167">Annotated flame chart</span><span class="sxs-lookup"><span data-stu-id="e00ff-167">Annotated flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="e00ff-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span><span class="sxs-lookup"><span data-stu-id="e00ff-168">A tall call stack is not necessarily significant, it just means that a lot of functions were called.</span></span>  <span data-ttu-id="e00ff-169">But a wide bar means that a function took a long time to complete.</span><span class="sxs-lookup"><span data-stu-id="e00ff-169">But a wide bar means that a function took a long time to complete.</span></span>  <span data-ttu-id="e00ff-170">These are candidates for optimization.</span><span class="sxs-lookup"><span data-stu-id="e00ff-170">These are candidates for optimization.</span></span>  

### <span data-ttu-id="e00ff-171">Zoom in on specific parts of recording</span><span class="sxs-lookup"><span data-stu-id="e00ff-171">Zoom in on specific parts of recording</span></span>  

<span data-ttu-id="e00ff-172">Select, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span><span class="sxs-lookup"><span data-stu-id="e00ff-172">Select, hold, and drag your mouse left and right across the overview to zoom in on particular parts of the call stack.</span></span>  <span data-ttu-id="e00ff-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span><span class="sxs-lookup"><span data-stu-id="e00ff-173">After you zoom, the call stack automatically displays the portion of the recording that you selected.</span></span>  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-zoomed.msft.png":::
   <span data-ttu-id="e00ff-175">Chart zoomed</span><span class="sxs-lookup"><span data-stu-id="e00ff-175">Chart zoomed</span></span>  
:::image-end:::  

### <span data-ttu-id="e00ff-176">View function details</span><span class="sxs-lookup"><span data-stu-id="e00ff-176">View function details</span></span>  

<span data-ttu-id="e00ff-177">Select on a function to view the definition in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="e00ff-177">Select on a function to view the definition in the **Sources** panel.</span></span>  

<span data-ttu-id="e00ff-178">Hover over a function to display the name and timing data.</span><span class="sxs-lookup"><span data-stu-id="e00ff-178">Hover over a function to display the name and timing data.</span></span>  <span data-ttu-id="e00ff-179">The following information is provided.</span><span class="sxs-lookup"><span data-stu-id="e00ff-179">The following information is provided.</span></span>  

| <span data-ttu-id="e00ff-180">Detail</span><span class="sxs-lookup"><span data-stu-id="e00ff-180">Detail</span></span> | <span data-ttu-id="e00ff-181">Description</span><span class="sxs-lookup"><span data-stu-id="e00ff-181">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="e00ff-182">Name</span><span class="sxs-lookup"><span data-stu-id="e00ff-182">Name</span></span>** | <span data-ttu-id="e00ff-183">The name of the function.</span><span class="sxs-lookup"><span data-stu-id="e00ff-183">The name of the function.</span></span>  |  
| **<span data-ttu-id="e00ff-184">Self size</span><span class="sxs-lookup"><span data-stu-id="e00ff-184">Self size</span></span>** | <span data-ttu-id="e00ff-185">The size of the current invocation of the function, including only the statements in the function.</span><span class="sxs-lookup"><span data-stu-id="e00ff-185">The size of the current invocation of the function, including only the statements in the function.</span></span>  |  
| **<span data-ttu-id="e00ff-186">Total size</span><span class="sxs-lookup"><span data-stu-id="e00ff-186">Total size</span></span>** | <span data-ttu-id="e00ff-187">The size of the current invocation of this function and any functions that it called.</span><span class="sxs-lookup"><span data-stu-id="e00ff-187">The size of the current invocation of this function and any functions that it called.</span></span>  |  
| **<span data-ttu-id="e00ff-188">URL</span><span class="sxs-lookup"><span data-stu-id="e00ff-188">URL</span></span>** | <span data-ttu-id="e00ff-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span><span class="sxs-lookup"><span data-stu-id="e00ff-189">The location of the function definition in the form of `base.js:261` where `base.js` is the name of the file where the function is defined and `261` is the line number of the definition.</span></span>  |  
<!--*   **Aggregated self time**.  Aggregate time for all invocations of the function across the recording, not including functions called by this function.  -->  
<!--*   **Aggregated total time**.  Aggregate total time for all invocations of the function, including functions called by this function.  -->  
<!--*   **Not optimized**.  If the profiler has detected a potential optimization for the function it lists it here.  -->  

:::image type="complex" source="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png" alt-text="Sample Profiles" lightbox="../media/rendering-tools-gh-nodejs-benchmarks-run-memory-sampling-profiles-chart-hover.msft.png":::
   <span data-ttu-id="e00ff-191">View functions details in chart</span><span class="sxs-lookup"><span data-stu-id="e00ff-191">View functions details in chart</span></span>  
:::image-end:::  

## <span data-ttu-id="e00ff-192">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="e00ff-192">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageExcludeIcon]: ../media/exclude-icon.msft.png  
[ImageFocusIcon]: ../media/focus-icon.msft.png  
[ImageRestoreIcon]: ../media/restore-icon.msft.png  

<!-- links -->  

[DevtoolsConsoleUtilities]: ../console/utilities.md "Console utilities API reference | Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfile]: ../console/utilities.md#profile "profile - Console utilities API reference | Microsoft Docs"  
[DevtoolsConsoleUtilitiesProfileEnd]: ../console/utilities.md#profileend "profileEnd - Console utilities API reference | Microsoft Docs"  

> [!NOTE]
> <span data-ttu-id="e00ff-196">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e00ff-196">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e00ff-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span><span class="sxs-lookup"><span data-stu-id="e00ff-197">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/js-execution) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="e00ff-199">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e00ff-199">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
