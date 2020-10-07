---
description: Learn how to use Microsoft Edge DevTools to find ways to make your websites load faster.
title: Optimize Website Speed With Microsoft Edge DevTools
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: dafcb9c4d1194239baed7507e505d74d2b4ce1c8
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993436"
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





# <span data-ttu-id="307d4-104">Optimize website speed with Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="307d4-104">Optimize website speed with Microsoft Edge DevTools</span></span>   



## <span data-ttu-id="307d4-105">Goal of tutorial</span><span class="sxs-lookup"><span data-stu-id="307d4-105">Goal of tutorial</span></span>  

<span data-ttu-id="307d4-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span><span class="sxs-lookup"><span data-stu-id="307d4-106">This tutorial teaches you how to use Microsoft Edge DevTools to find ways to make your websites load faster.</span></span>  

## <span data-ttu-id="307d4-107">Prerequisites</span><span class="sxs-lookup"><span data-stu-id="307d4-107">Prerequisites</span></span>  

*   <span data-ttu-id="307d4-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span><span class="sxs-lookup"><span data-stu-id="307d4-108">You should have basic web development experience, similar to what is taught in this [Introduction to Web Development class][CourseraIntroductionWebDevelopmentClass].</span></span>  
*   <span data-ttu-id="307d4-109">You do not need to know anything about load performance.</span><span class="sxs-lookup"><span data-stu-id="307d4-109">You do not need to know anything about load performance.</span></span>  <span data-ttu-id="307d4-110">You learn about it in this tutorial!</span><span class="sxs-lookup"><span data-stu-id="307d4-110">You learn about it in this tutorial!</span></span>  

## <span data-ttu-id="307d4-111">Introduction</span><span class="sxs-lookup"><span data-stu-id="307d4-111">Introduction</span></span>   

<span data-ttu-id="307d4-112">This is Tony.</span><span class="sxs-lookup"><span data-stu-id="307d4-112">This is Tony.</span></span>  <span data-ttu-id="307d4-113">Tony is very famous in cat society.</span><span class="sxs-lookup"><span data-stu-id="307d4-113">Tony is very famous in cat society.</span></span>  <span data-ttu-id="307d4-114">He has built a website so that his fans are able to learn about his favorite foods.</span><span class="sxs-lookup"><span data-stu-id="307d4-114">He has built a website so that his fans are able to learn about his favorite foods.</span></span>  <span data-ttu-id="307d4-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span><span class="sxs-lookup"><span data-stu-id="307d4-115">His fans love the site, but Tony keeps hearing complaints that the site loads slowly.</span></span>  <span data-ttu-id="307d4-116">Tony has asked you to help him speed the site up.</span><span class="sxs-lookup"><span data-stu-id="307d4-116">Tony has asked you to help him speed the site up.</span></span>  

:::image type="complex" source="../media/speed-tony.msft.png" alt-text="Tony the cat" lightbox="../media/speed-tony.msft.png":::
   <span data-ttu-id="307d4-118">Tony the cat</span><span class="sxs-lookup"><span data-stu-id="307d4-118">Tony the cat</span></span>  
:::image-end:::  

## <span data-ttu-id="307d4-119">Step 1: Audit the site</span><span class="sxs-lookup"><span data-stu-id="307d4-119">Step 1: Audit the site</span></span>   

<span data-ttu-id="307d4-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span><span class="sxs-lookup"><span data-stu-id="307d4-120">Whenever you set out to improve the load performance of a site, **always start with an audit**.</span></span>  
<span data-ttu-id="307d4-121">The audit has 2 important functions:</span><span class="sxs-lookup"><span data-stu-id="307d4-121">The audit has 2 important functions:</span></span>  

*   <span data-ttu-id="307d4-122">It creates a **baseline** for you to measure subsequent changes against.</span><span class="sxs-lookup"><span data-stu-id="307d4-122">It creates a **baseline** for you to measure subsequent changes against.</span></span>  
*   <span data-ttu-id="307d4-123">It gives you **actionable tips** on what changes have the most impact.</span><span class="sxs-lookup"><span data-stu-id="307d4-123">It gives you **actionable tips** on what changes have the most impact.</span></span>  
    
### <span data-ttu-id="307d4-124">Set up</span><span class="sxs-lookup"><span data-stu-id="307d4-124">Set up</span></span>   

<span data-ttu-id="307d4-125">First, you must set up the site so that you are able to make changes to it later.</span><span class="sxs-lookup"><span data-stu-id="307d4-125">First, you must set up the site so that you are able to make changes to it later.</span></span>  

1.  <span data-ttu-id="307d4-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span><span class="sxs-lookup"><span data-stu-id="307d4-126">[Open the source code for the site](https://glitch.com/edit/#!/tony).</span></span>  <span data-ttu-id="307d4-127">This tab is referred to as the **editor tab**.</span><span class="sxs-lookup"><span data-stu-id="307d4-127">This tab is referred to as the **editor tab**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-server-js.msft.png":::
       <span data-ttu-id="307d4-129">The **editor tab**</span><span class="sxs-lookup"><span data-stu-id="307d4-129">The **editor tab**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-130">Select **tony**.</span><span class="sxs-lookup"><span data-stu-id="307d4-130">Select **tony**.</span></span>  <span data-ttu-id="307d4-131">A menu appears.</span><span class="sxs-lookup"><span data-stu-id="307d4-131">A menu appears.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-server-js-remix-project.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-server-js-remix-project.msft.png":::
       <span data-ttu-id="307d4-133">The menu that appears after clicking **tony**</span><span class="sxs-lookup"><span data-stu-id="307d4-133">The menu that appears after clicking **tony**</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-134">Select **Remix Project**.</span><span class="sxs-lookup"><span data-stu-id="307d4-134">Select **Remix Project**.</span></span>  <span data-ttu-id="307d4-135">The name of the project changes from **tony** to some randomly-generated name.</span><span class="sxs-lookup"><span data-stu-id="307d4-135">The name of the project changes from **tony** to some randomly-generated name.</span></span>  <span data-ttu-id="307d4-136">You now have your own editable copy of the code.</span><span class="sxs-lookup"><span data-stu-id="307d4-136">You now have your own editable copy of the code.</span></span>  <span data-ttu-id="307d4-137">Later on, you may make changes to this code.</span><span class="sxs-lookup"><span data-stu-id="307d4-137">Later on, you may make changes to this code.</span></span>  
1.  <span data-ttu-id="307d4-138">Select **Show** and select **In a New Window**.</span><span class="sxs-lookup"><span data-stu-id="307d4-138">Select **Show** and select **In a New Window**.</span></span>  <span data-ttu-id="307d4-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span><span class="sxs-lookup"><span data-stu-id="307d4-139">The demo opens in a new tab.  This tab is be referred to as the **demo tab**.  It may take a while for the site to load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-show-live.msft.png":::
       <span data-ttu-id="307d4-141">The demo tab</span><span class="sxs-lookup"><span data-stu-id="307d4-141">The demo tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-142">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="307d4-142">Press `Control`+`Shift`+`J` \(Windows\) or `Command`+`Option`+`J` \(macOS\).</span></span>  <span data-ttu-id="307d4-143">Microsoft Edge DevTools opens up alongside the demo.</span><span class="sxs-lookup"><span data-stu-id="307d4-143">Microsoft Edge DevTools opens up alongside the demo.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-show-live-console.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-show-live-console.msft.png":::
       <span data-ttu-id="307d4-145">DevTools and the demo</span><span class="sxs-lookup"><span data-stu-id="307d4-145">DevTools and the demo</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span><span class="sxs-lookup"><span data-stu-id="307d4-146">For the rest of the screenshots in this tutorial, DevTools is shown in a separate window.</span></span>  <span data-ttu-id="307d4-147">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span><span class="sxs-lookup"><span data-stu-id="307d4-147">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, typing `Undock`, and then selecting **Undock into separate window**.</span></span>  

:::image type="complex" source="../media/speed-console.msft.png" alt-text="Tony the cat" lightbox="../media/speed-console.msft.png":::
   <span data-ttu-id="307d4-149">Undocked DevTools</span><span class="sxs-lookup"><span data-stu-id="307d4-149">Undocked DevTools</span></span>  
:::image-end:::  

### <span data-ttu-id="307d4-150">Establish a baseline</span><span class="sxs-lookup"><span data-stu-id="307d4-150">Establish a baseline</span></span>   

<span data-ttu-id="307d4-151">The baseline is a record of how the site performed before you made any performance improvements.</span><span class="sxs-lookup"><span data-stu-id="307d4-151">The baseline is a record of how the site performed before you made any performance improvements.</span></span>  

1.  <span data-ttu-id="307d4-152">Select the **Audits** tab.  It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.</span><span class="sxs-lookup"><span data-stu-id="307d4-152">Select the **Audits** tab.  It may be hidden behind the **More Panels** \(![More Panels][ImageMorePanelsIcon]\) button.</span></span>  <span data-ttu-id="307d4-153">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span><span class="sxs-lookup"><span data-stu-id="307d4-153">There is a Lighthouse on this panel because the project that powers the Audits panel is named **Lighthouse**.</span></span>  
    
    [!INCLUDE [audits-panel-note](../includes/audits-panel-note.md)]  
    
    :::image type="complex" source="../media/speed-audits-performance.msft.png" alt-text="Tony the cat" lightbox="../media/speed-audits-performance.msft.png":::
       <span data-ttu-id="307d4-155">The **Audits** panel</span><span class="sxs-lookup"><span data-stu-id="307d4-155">The **Audits** panel</span></span>  
    :::image-end:::  
    
    <!--todo: add link to Lighthouse when section is available  -->  
    <!-- /web/tools/lighthouse  -->  
    
1.  <span data-ttu-id="307d4-156">Match your audit configuration settings to those in the previous figure.</span><span class="sxs-lookup"><span data-stu-id="307d4-156">Match your audit configuration settings to those in the previous figure.</span></span>  <span data-ttu-id="307d4-157">Here is an explanation of the different options:</span><span class="sxs-lookup"><span data-stu-id="307d4-157">Here is an explanation of the different options:</span></span>  
    
    *   <span data-ttu-id="307d4-158">**Device**.</span><span class="sxs-lookup"><span data-stu-id="307d4-158">**Device**.</span></span>  <span data-ttu-id="307d4-159">Setting to **Mobile** changes the user agent string and simulates a mobile viewport.</span><span class="sxs-lookup"><span data-stu-id="307d4-159">Setting to **Mobile** changes the user agent string and simulates a mobile viewport.</span></span>  <span data-ttu-id="307d4-160">Setting to **Desktop** pretty much just disables the **Mobile** changes.</span><span class="sxs-lookup"><span data-stu-id="307d4-160">Setting to **Desktop** pretty much just disables the **Mobile** changes.</span></span>  
    *   <span data-ttu-id="307d4-161">**Audits**.</span><span class="sxs-lookup"><span data-stu-id="307d4-161">**Audits**.</span></span>  <span data-ttu-id="307d4-162">Disabling a category prevents the Audits panel from running those audits, and excludes those audits from your report.</span><span class="sxs-lookup"><span data-stu-id="307d4-162">Disabling a category prevents the Audits panel from running those audits, and excludes those audits from your report.</span></span>  <span data-ttu-id="307d4-163">Leave the other categories enabled, if you want to see the types of recommendations that are provide.</span><span class="sxs-lookup"><span data-stu-id="307d4-163">Leave the other categories enabled, if you want to see the types of recommendations that are provide.</span></span>  <span data-ttu-id="307d4-164">Disabling categories slightly speeds up the auditing process.</span><span class="sxs-lookup"><span data-stu-id="307d4-164">Disabling categories slightly speeds up the auditing process.</span></span>  
    *   <span data-ttu-id="307d4-165">**Throttling**.</span><span class="sxs-lookup"><span data-stu-id="307d4-165">**Throttling**.</span></span>  <span data-ttu-id="307d4-166">Setting to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span><span class="sxs-lookup"><span data-stu-id="307d4-166">Setting to **Simulated Slow 4G, 4x CPU Slowdown** simulates the typical conditions of browsing on a mobile device.</span></span>  <span data-ttu-id="307d4-167">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span><span class="sxs-lookup"><span data-stu-id="307d4-167">It is named "simulated" because the Audits panel does not actually throttle during the auditing process.</span></span>  <span data-ttu-id="307d4-168">Instead, it just extrapolates how long the page would take to load under mobile conditions.</span><span class="sxs-lookup"><span data-stu-id="307d4-168">Instead, it just extrapolates how long the page would take to load under mobile conditions.</span></span>  <span data-ttu-id="307d4-169">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span><span class="sxs-lookup"><span data-stu-id="307d4-169">The **Applied...** setting, on the other hand, actually throttles your CPU and network, with the tradeoff of a longer auditing process.</span></span>  
    *   <span data-ttu-id="307d4-170">**Clear Storage**.</span><span class="sxs-lookup"><span data-stu-id="307d4-170">**Clear Storage**.</span></span>  <span data-ttu-id="307d4-171">Enabling this checkbox clears all storage associated with the page before every audit.</span><span class="sxs-lookup"><span data-stu-id="307d4-171">Enabling this checkbox clears all storage associated with the page before every audit.</span></span>  <span data-ttu-id="307d4-172">Leave this setting on if you want to audit how first-time visitors experience your site.</span><span class="sxs-lookup"><span data-stu-id="307d4-172">Leave this setting on if you want to audit how first-time visitors experience your site.</span></span>  <span data-ttu-id="307d4-173">Disable this setting when you want the repeat-visit experience.</span><span class="sxs-lookup"><span data-stu-id="307d4-173">Disable this setting when you want the repeat-visit experience.</span></span>  
    
1.  <span data-ttu-id="307d4-174">Select **Run Audits**.</span><span class="sxs-lookup"><span data-stu-id="307d4-174">Select **Run Audits**.</span></span>  <span data-ttu-id="307d4-175">After 10 to 30 seconds, the Audits panel shows you a report of the performance of the site.</span><span class="sxs-lookup"><span data-stu-id="307d4-175">After 10 to 30 seconds, the Audits panel shows you a report of the performance of the site.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed.msft.png":::
       <span data-ttu-id="307d4-177">The report for the Audits panel of the performance of the site</span><span class="sxs-lookup"><span data-stu-id="307d4-177">The report for the Audits panel of the performance of the site</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="307d4-178">Handling report errors</span><span class="sxs-lookup"><span data-stu-id="307d4-178">Handling report errors</span></span>   

<span data-ttu-id="307d4-179">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span><span class="sxs-lookup"><span data-stu-id="307d4-179">If you ever get an error in your Audits panel report, try running the demo tab from an **InPrivate** window with no other tabs open.</span></span>  <span data-ttu-id="307d4-180">This ensures that you are running Microsoft Edge from a clean state.</span><span class="sxs-lookup"><span data-stu-id="307d4-180">This ensures that you are running Microsoft Edge from a clean state.</span></span>  <span data-ttu-id="307d4-181">Microsoft Edge Extensions in particular often interfere with the auditing process.</span><span class="sxs-lookup"><span data-stu-id="307d4-181">Microsoft Edge Extensions in particular often interfere with the auditing process.</span></span>  

<!--todo: add screen capture for error in audit -->  
<!--
:::image type="complex" source="../media/speed-.msft.png" alt-text="Tony the cat" lightbox="../media/speed-.msft.png":::
   A report that errored  
:::image-end:::  
-->  

### <span data-ttu-id="307d4-182">Understand your report</span><span class="sxs-lookup"><span data-stu-id="307d4-182">Understand your report</span></span>   

<span data-ttu-id="307d4-183">The number at the top of your report is the overall performance score for the site.</span><span class="sxs-lookup"><span data-stu-id="307d4-183">The number at the top of your report is the overall performance score for the site.</span></span>  <span data-ttu-id="307d4-184">Later, as you make changes to the code, you should see this number rise.</span><span class="sxs-lookup"><span data-stu-id="307d4-184">Later, as you make changes to the code, you should see this number rise.</span></span>  <span data-ttu-id="307d4-185">A higher score means better performance.</span><span class="sxs-lookup"><span data-stu-id="307d4-185">A higher score means better performance.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-metrics-highlighted.msft.png":::
   <span data-ttu-id="307d4-187">The overall performance score</span><span class="sxs-lookup"><span data-stu-id="307d4-187">The overall performance score</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-188">The **Metrics** section provides quantitative measurements of the performance of the site.</span><span class="sxs-lookup"><span data-stu-id="307d4-188">The **Metrics** section provides quantitative measurements of the performance of the site.</span></span>  <span data-ttu-id="307d4-189">Each metric provides insight into a different aspect of the performance.</span><span class="sxs-lookup"><span data-stu-id="307d4-189">Each metric provides insight into a different aspect of the performance.</span></span>  <span data-ttu-id="307d4-190">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span><span class="sxs-lookup"><span data-stu-id="307d4-190">For example, **First Contentful Paint** tells you when content is first painted to the screen, which is an important milestone in the user's perception of the page load, whereas **Time To Interactive** marks the point at which the page appears ready enough to handle user interactions.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-collapsed-highlighted.msft.png":::
   <span data-ttu-id="307d4-192">The **Metrics** section</span><span class="sxs-lookup"><span data-stu-id="307d4-192">The **Metrics** section</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-193">Select the highlighted toggle button in the following figure to see a description for each metric, and click **Learn More** to read documentation about it.</span><span class="sxs-lookup"><span data-stu-id="307d4-193">Select the highlighted toggle button in the following figure to see a description for each metric, and click **Learn More** to read documentation about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-metrics-expanded.msft.png":::
   <span data-ttu-id="307d4-195">Select the highlighted toggle button to expand the Metrics items</span><span class="sxs-lookup"><span data-stu-id="307d4-195">Select the highlighted toggle button to expand the Metrics items</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-196">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span><span class="sxs-lookup"><span data-stu-id="307d4-196">Below Metrics is a collection of screenshots that show you how the page looked as it loaded.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="307d4-198">Screenshots of how the page looked while loading</span><span class="sxs-lookup"><span data-stu-id="307d4-198">Screenshots of how the page looked while loading</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-199">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span><span class="sxs-lookup"><span data-stu-id="307d4-199">The **Opportunities** section provides specific tips on how to improve the load performance of this specific page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-view-trace.msft.png":::
   <span data-ttu-id="307d4-201">The **Opportunities** section</span><span class="sxs-lookup"><span data-stu-id="307d4-201">The **Opportunities** section</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-202">Select an opportunity to learn more about it.</span><span class="sxs-lookup"><span data-stu-id="307d4-202">Select an opportunity to learn more about it.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-opportunities-expanded.msft.png":::
   <span data-ttu-id="307d4-204">**Eliminate render-blocking resources** opportunity</span><span class="sxs-lookup"><span data-stu-id="307d4-204">**Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-205">Select **Learn More** to see documentation about why an opportunity is important, and specific recommendations on how to fix it.</span><span class="sxs-lookup"><span data-stu-id="307d4-205">Select **Learn More** to see documentation about why an opportunity is important, and specific recommendations on how to fix it.</span></span>  

:::image type="complex" source="../media/speed-web-dev-performance-audits.msft.png" alt-text="Tony the cat" lightbox="../media/speed-web-dev-performance-audits.msft.png":::
   <span data-ttu-id="307d4-207">Documentation for the **Eliminate render-blocking resources** opportunity</span><span class="sxs-lookup"><span data-stu-id="307d4-207">Documentation for the **Eliminate render-blocking resources** opportunity</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-208">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-208">The **Diagnostics** section provides more information about factors that contribute to the load time of the page.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-diagnostics.msft.png":::
   <span data-ttu-id="307d4-210">The **Diagnostics** section</span><span class="sxs-lookup"><span data-stu-id="307d4-210">The **Diagnostics** section</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-211">The **Passed Audits** section shows you what the site is doing correctly.</span><span class="sxs-lookup"><span data-stu-id="307d4-211">The **Passed Audits** section shows you what the site is doing correctly.</span></span>  <span data-ttu-id="307d4-212">Select to expand the section.</span><span class="sxs-lookup"><span data-stu-id="307d4-212">Select to expand the section.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-audits-performance-passed-audits.msft.png":::
   <span data-ttu-id="307d4-214">The **Passed Audits** section</span><span class="sxs-lookup"><span data-stu-id="307d4-214">The **Passed Audits** section</span></span>  
:::image-end:::  

## <span data-ttu-id="307d4-215">Step 2: Experiment</span><span class="sxs-lookup"><span data-stu-id="307d4-215">Step 2: Experiment</span></span>   

<span data-ttu-id="307d4-216">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-216">The Opportunities section of your audit report gives you tips on how to improve the performance of the page.</span></span>  <span data-ttu-id="307d4-217">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span><span class="sxs-lookup"><span data-stu-id="307d4-217">In this section, you implement the recommended changes to the codebase, auditing the site after each change to measure how it affects site speed.</span></span>  

### <span data-ttu-id="307d4-218">Enable text compression</span><span class="sxs-lookup"><span data-stu-id="307d4-218">Enable text compression</span></span>   

<span data-ttu-id="307d4-219">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-219">Your report says that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="307d4-220">Enabling text compression is an opportunity to improve the performance of the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-220">Enabling text compression is an opportunity to improve the performance of the page.</span></span>  

<span data-ttu-id="307d4-221">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span><span class="sxs-lookup"><span data-stu-id="307d4-221">Text compression is when you reduce, or compress, the size of a text file before sending it over the network.</span></span>  <span data-ttu-id="307d4-222">Kind of like how you might zip a folder before emailing it to reduce the size.</span><span class="sxs-lookup"><span data-stu-id="307d4-222">Kind of like how you might zip a folder before emailing it to reduce the size.</span></span>  

<span data-ttu-id="307d4-223">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span><span class="sxs-lookup"><span data-stu-id="307d4-223">Before you enable compression, here are a couple of ways to manually check whether text resources are compressed.</span></span>  

1.  <span data-ttu-id="307d4-224">Select the **Network** tab.</span><span class="sxs-lookup"><span data-stu-id="307d4-224">Select the **Network** tab.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-network.msft.png":::
       <span data-ttu-id="307d4-226">The **Network** panel</span><span class="sxs-lookup"><span data-stu-id="307d4-226">The **Network** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-227">Select the **Network setting** icon.</span><span class="sxs-lookup"><span data-stu-id="307d4-227">Select the **Network setting** icon.</span></span>  
1.  <span data-ttu-id="307d4-228">Select the **Use Large Request Rows** checkbox.</span><span class="sxs-lookup"><span data-stu-id="307d4-228">Select the **Use Large Request Rows** checkbox.</span></span>  <span data-ttu-id="307d4-229">The height of the rows in the table of network requests increases.</span><span class="sxs-lookup"><span data-stu-id="307d4-229">The height of the rows in the table of network requests increases.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows.msft.png":::
       <span data-ttu-id="307d4-231">Large rows in the network requests table</span><span class="sxs-lookup"><span data-stu-id="307d4-231">Large rows in the network requests table</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-232">If you do not see the **Size** column in the table of network requests, click the table header and then select **Size**.</span><span class="sxs-lookup"><span data-stu-id="307d4-232">If you do not see the **Size** column in the table of network requests, click the table header and then select **Size**.</span></span>  

<span data-ttu-id="307d4-233">Each **Size** cell shows two values.</span><span class="sxs-lookup"><span data-stu-id="307d4-233">Each **Size** cell shows two values.</span></span>  <span data-ttu-id="307d4-234">The top value is the size of the downloaded resource.</span><span class="sxs-lookup"><span data-stu-id="307d4-234">The top value is the size of the downloaded resource.</span></span>  
<span data-ttu-id="307d4-235">The bottom value is the size of the uncompressed resource.</span><span class="sxs-lookup"><span data-stu-id="307d4-235">The bottom value is the size of the uncompressed resource.</span></span>  <span data-ttu-id="307d4-236">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span><span class="sxs-lookup"><span data-stu-id="307d4-236">If the two values are the same, then the resource is not being compressed when it is sent over the network.</span></span>  <span data-ttu-id="307d4-237">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span><span class="sxs-lookup"><span data-stu-id="307d4-237">For example, in the previous figure, the top and bottom values for `bundle.js` are `1.2 MB` and `1.2 MB`.</span></span>  

<span data-ttu-id="307d4-238">Check for compression by inspecting the HTTP headers of a resource:</span><span class="sxs-lookup"><span data-stu-id="307d4-238">Check for compression by inspecting the HTTP headers of a resource:</span></span>  

1.  <span data-ttu-id="307d4-239">Select **bundle.js**.</span><span class="sxs-lookup"><span data-stu-id="307d4-239">Select **bundle.js**.</span></span>  
1.  <span data-ttu-id="307d4-240">Select the **Headers** tab.</span><span class="sxs-lookup"><span data-stu-id="307d4-240">Select the **Headers** tab.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-network-use-large-request-rows-bundle-js.msft.png":::
       <span data-ttu-id="307d4-242">The **Headers** tab</span><span class="sxs-lookup"><span data-stu-id="307d4-242">The **Headers** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-243">Search the **Response Headers** section for a `content-encoding` header.</span><span class="sxs-lookup"><span data-stu-id="307d4-243">Search the **Response Headers** section for a `content-encoding` header.</span></span>  <span data-ttu-id="307d4-244">You should not see one, meaning that `bundle.js` was not compressed.</span><span class="sxs-lookup"><span data-stu-id="307d4-244">You should not see one, meaning that `bundle.js` was not compressed.</span></span>  <span data-ttu-id="307d4-245">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span><span class="sxs-lookup"><span data-stu-id="307d4-245">When a resource is compressed, this header is usually set to `gzip`, `deflate`, or `br`.</span></span>  <span data-ttu-id="307d4-246">See [Directives][MDNContentEncodingDirectives] for an explanation of these values.</span><span class="sxs-lookup"><span data-stu-id="307d4-246">See [Directives][MDNContentEncodingDirectives] for an explanation of these values.</span></span>  

<span data-ttu-id="307d4-247">Enough with the explanations.</span><span class="sxs-lookup"><span data-stu-id="307d4-247">Enough with the explanations.</span></span>  <span data-ttu-id="307d4-248">Time to make some changes!</span><span class="sxs-lookup"><span data-stu-id="307d4-248">Time to make some changes!</span></span>  <span data-ttu-id="307d4-249">Enable text compression by adding a couple of lines of code:</span><span class="sxs-lookup"><span data-stu-id="307d4-249">Enable text compression by adding a couple of lines of code:</span></span>  

1.  <span data-ttu-id="307d4-250">In the editor tab, click **server.js**.</span><span class="sxs-lookup"><span data-stu-id="307d4-250">In the editor tab, click **server.js**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-server-js.msft.png":::
       <span data-ttu-id="307d4-252">Edit</span><span class="sxs-lookup"><span data-stu-id="307d4-252">Edit</span></span> `server.js`  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-253">Add the following code to **server.js**.</span><span class="sxs-lookup"><span data-stu-id="307d4-253">Add the following code to **server.js**.</span></span>  <span data-ttu-id="307d4-254">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span><span class="sxs-lookup"><span data-stu-id="307d4-254">Make sure to put `app.use(compression())` before `app.use(express.static('build'))`.</span></span>  

    ```javascript
    const express = require('express');
    const app = express();
    const fs = require('fs');
    const compression = require('compression');

    app.use(compression());
    app.use(express.static('build'));
    
    const listener = app.listen(process.env.PORT || 1234, function () {
        console.log(`Listening on port ${listener.address().port}`);
    });
    ```  
    
    > [!NOTE]
    > <span data-ttu-id="307d4-255">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span><span class="sxs-lookup"><span data-stu-id="307d4-255">Usually, you have to install the `compression` package via something like `npm i -S compression`, but this has already been done for you.</span></span>  
    
1.  <span data-ttu-id="307d4-256">Wait for Glitch to deploy the new build of the site.</span><span class="sxs-lookup"><span data-stu-id="307d4-256">Wait for Glitch to deploy the new build of the site.</span></span>  <span data-ttu-id="307d4-257">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span><span class="sxs-lookup"><span data-stu-id="307d4-257">The fancy animation next to **Tools** means that the site is getting rebuilt and redeployed.</span></span>  <span data-ttu-id="307d4-258">The change is ready when the animation next to **Tools** goes away.</span><span class="sxs-lookup"><span data-stu-id="307d4-258">The change is ready when the animation next to **Tools** goes away.</span></span>  <span data-ttu-id="307d4-259">Select **Show** and select **In a New Window** again.</span><span class="sxs-lookup"><span data-stu-id="307d4-259">Select **Show** and select **In a New Window** again.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-server-js-edited.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-server-js-edited.msft.png":::
       The animation that indicates that the site is getting built  
    :::image-end:::  
    -->  
    
<span data-ttu-id="307d4-260">Use the workflows that you learned earlier to manually check that the compression is working:</span><span class="sxs-lookup"><span data-stu-id="307d4-260">Use the workflows that you learned earlier to manually check that the compression is working:</span></span>  

1.  <span data-ttu-id="307d4-261">Go back to the demo tab and reload the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-261">Go back to the demo tab and reload the page.</span></span>  <span data-ttu-id="307d4-262">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span><span class="sxs-lookup"><span data-stu-id="307d4-262">The **Size** column should now show 2 different values for text resources like `bundle.js`.</span></span>  <span data-ttu-id="307d4-263">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span><span class="sxs-lookup"><span data-stu-id="307d4-263">In the figure after the following, the top value of `256 KB` for `bundle.js` is the size of the file that was sent over the network, and the bottom value of `1.2 MB` is the uncompressed file size.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-main.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-network-main.msft.png":::
       <span data-ttu-id="307d4-265">The **Size** column now shows 2 different values for text resources</span><span class="sxs-lookup"><span data-stu-id="307d4-265">The **Size** column now shows 2 different values for text resources</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-266">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span><span class="sxs-lookup"><span data-stu-id="307d4-266">The **Response Headers** section for `bundle.js` should now include a `content-encoding: gzip` header.</span></span>
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-network-bundle-js-headers-response.msft.png":::
       <span data-ttu-id="307d4-268">The **Response Headers** section now contains a content-encoding header</span><span class="sxs-lookup"><span data-stu-id="307d4-268">The **Response Headers** section now contains a content-encoding header</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-269">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span><span class="sxs-lookup"><span data-stu-id="307d4-269">Audit the page again to measure what kind of impact text compression has on the load performance of the page:</span></span>  

1.  <span data-ttu-id="307d4-270">Select the **Audits** tab.</span><span class="sxs-lookup"><span data-stu-id="307d4-270">Select the **Audits** tab.</span></span>  
1.  <span data-ttu-id="307d4-271">Select **Perform an audit** \(![Perform an audit][ImagePerformIcon]\).</span><span class="sxs-lookup"><span data-stu-id="307d4-271">Select **Perform an audit** \(![Perform an audit][ImagePerformIcon]\).</span></span>  
1.  <span data-ttu-id="307d4-272">Leave the settings the same as before.</span><span class="sxs-lookup"><span data-stu-id="307d4-272">Leave the settings the same as before.</span></span>  
1.  <span data-ttu-id="307d4-273">Select **Run audit**.</span><span class="sxs-lookup"><span data-stu-id="307d4-273">Select **Run audit**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance.msft.png":::
       <span data-ttu-id="307d4-275">An Audits report after enabling text compression</span><span class="sxs-lookup"><span data-stu-id="307d4-275">An Audits report after enabling text compression</span></span>  
    :::image-end:::  
    
<!--  Woohoo!  That looks like progress.  -->  <span data-ttu-id="307d4-276">Your overall performance score should have increased, meaning that the site is getting faster.</span><span class="sxs-lookup"><span data-stu-id="307d4-276">Your overall performance score should have increased, meaning that the site is getting faster.</span></span>  

#### <span data-ttu-id="307d4-277">Text compression in the real world</span><span class="sxs-lookup"><span data-stu-id="307d4-277">Text compression in the real world</span></span>   

<span data-ttu-id="307d4-278">Most servers really do have simple fixes like this for enabling compression!</span><span class="sxs-lookup"><span data-stu-id="307d4-278">Most servers really do have simple fixes like this for enabling compression!</span></span>  <span data-ttu-id="307d4-279">Just do a search on how to configure whatever server you use to compress text.</span><span class="sxs-lookup"><span data-stu-id="307d4-279">Just do a search on how to configure whatever server you use to compress text.</span></span>  

### <span data-ttu-id="307d4-280">Resize images</span><span class="sxs-lookup"><span data-stu-id="307d4-280">Resize images</span></span>   

<span data-ttu-id="307d4-281">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-281">Your report indicates that avoiding enormous network payloads is one of the top opportunities for improving the performance of the page.</span></span>  <span data-ttu-id="307d4-282">Resizing images helps reduce the size of the network payload.</span><span class="sxs-lookup"><span data-stu-id="307d4-282">Resizing images helps reduce the size of the network payload.</span></span>  <span data-ttu-id="307d4-283">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span><span class="sxs-lookup"><span data-stu-id="307d4-283">If your user is viewing your images on a mobile device screen that is 500-pixels-wide, there is really no point in sending a 1500-pixel-wide image.</span></span>  <span data-ttu-id="307d4-284">Ideally, you send a 500-pixel-wide image, at most.</span><span class="sxs-lookup"><span data-stu-id="307d4-284">Ideally, you send a 500-pixel-wide image, at most.</span></span>  

1.  <span data-ttu-id="307d4-285">In your report, click **Avoid enormous network payloads** to see which images should be resized.</span><span class="sxs-lookup"><span data-stu-id="307d4-285">In your report, click **Avoid enormous network payloads** to see which images should be resized.</span></span>  <span data-ttu-id="307d4-286">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span><span class="sxs-lookup"><span data-stu-id="307d4-286">It looks like 2 of the jpg files are over 2000 KB, which is bigger than necessary.</span></span>  
    
    <!--
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-opportunities-expanded.msft.png":::
       Details about the properly size images opportunity  
    :::image-end:::  
    -->
    
1.  <span data-ttu-id="307d4-287">Back in the editor tab, open `src/model.js`.</span><span class="sxs-lookup"><span data-stu-id="307d4-287">Back in the editor tab, open `src/model.js`.</span></span>  
1.  <span data-ttu-id="307d4-288">Replace `const dir = 'big'` with `const dir = 'small'`.</span><span class="sxs-lookup"><span data-stu-id="307d4-288">Replace `const dir = 'big'` with `const dir = 'small'`.</span></span>  <span data-ttu-id="307d4-289">This directory contains copies of the same images which have been resized.</span><span class="sxs-lookup"><span data-stu-id="307d4-289">This directory contains copies of the same images which have been resized.</span></span>  
1.  <span data-ttu-id="307d4-290">Audit the page again to see how this change affects load performance.</span><span class="sxs-lookup"><span data-stu-id="307d4-290">Audit the page again to see how this change affects load performance.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-compression-small-images-audits-performance.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-compression-small-images-audits-performance.msft.png":::
       <span data-ttu-id="307d4-292">An Audits report after resizing images</span><span class="sxs-lookup"><span data-stu-id="307d4-292">An Audits report after resizing images</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-293">Looks like the change only has a minor affect on the overall performance score.</span><span class="sxs-lookup"><span data-stu-id="307d4-293">Looks like the change only has a minor affect on the overall performance score.</span></span>  <span data-ttu-id="307d4-294">However, one thing that the score does not show clearly is how much network data you are saving your users.</span><span class="sxs-lookup"><span data-stu-id="307d4-294">However, one thing that the score does not show clearly is how much network data you are saving your users.</span></span>  <span data-ttu-id="307d4-295">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span><span class="sxs-lookup"><span data-stu-id="307d4-295">The total size of the old photos was around 5.3 megabytes, whereas now it is only about 0.18 megabytes.</span></span>  

#### <span data-ttu-id="307d4-296">Resizing images in the real world</span><span class="sxs-lookup"><span data-stu-id="307d4-296">Resizing images in the real world</span></span>   

<span data-ttu-id="307d4-297">For a small app, doing a one-off resize like this may be good enough.</span><span class="sxs-lookup"><span data-stu-id="307d4-297">For a small app, doing a one-off resize like this may be good enough.</span></span>  <span data-ttu-id="307d4-298">But for a large app, this obviously is not scalable.</span><span class="sxs-lookup"><span data-stu-id="307d4-298">But for a large app, this obviously is not scalable.</span></span>  <span data-ttu-id="307d4-299">Here are some strategies for managing images in large apps:</span><span class="sxs-lookup"><span data-stu-id="307d4-299">Here are some strategies for managing images in large apps:</span></span>  

*   <span data-ttu-id="307d4-300">Resize images during your build process.</span><span class="sxs-lookup"><span data-stu-id="307d4-300">Resize images during your build process.</span></span>  
*   <span data-ttu-id="307d4-301">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span><span class="sxs-lookup"><span data-stu-id="307d4-301">Create multiple sizes of each image during the build process and then use `srcset` in your code.</span></span>  <span data-ttu-id="307d4-302">At runtime, the browser takes care of choosing which size is best for the device.</span><span class="sxs-lookup"><span data-stu-id="307d4-302">At runtime, the browser takes care of choosing which size is best for the device.</span></span>  
    <!--See [Relative-sized images][relative].  -->
    
<!--[relative]: /web/fundamentals/design-and-ux/responsive/images#relative_sized_images  -->  

*   <span data-ttu-id="307d4-303">Use an image CDN that lets you dynamically resize an image when you request it.</span><span class="sxs-lookup"><span data-stu-id="307d4-303">Use an image CDN that lets you dynamically resize an image when you request it.</span></span>  
*   <span data-ttu-id="307d4-304">At the very least, optimize each image.</span><span class="sxs-lookup"><span data-stu-id="307d4-304">At the very least, optimize each image.</span></span>  <span data-ttu-id="307d4-305">This may create huge savings.</span><span class="sxs-lookup"><span data-stu-id="307d4-305">This may create huge savings.</span></span>  
  <span data-ttu-id="307d4-306">Optimization is when you run an image through a special program that reduces the size of the image file.</span><span class="sxs-lookup"><span data-stu-id="307d4-306">Optimization is when you run an image through a special program that reduces the size of the image file.</span></span>  <span data-ttu-id="307d4-307">See [Essential Image Optimization][EssentialImageOptimization] for more tips.</span><span class="sxs-lookup"><span data-stu-id="307d4-307">See [Essential Image Optimization][EssentialImageOptimization] for more tips.</span></span>  
    
### <span data-ttu-id="307d4-308">Eliminate render-blocking resources</span><span class="sxs-lookup"><span data-stu-id="307d4-308">Eliminate render-blocking resources</span></span>   

<span data-ttu-id="307d4-309">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span><span class="sxs-lookup"><span data-stu-id="307d4-309">Your latest report says that eliminating render-blocking resources is now the biggest opportunity.</span></span>  

<span data-ttu-id="307d4-310">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-310">A render-blocking resource is an external JavaScript or CSS file that the browser must download, parse, and run before it displays the page.</span></span>  <span data-ttu-id="307d4-311">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span><span class="sxs-lookup"><span data-stu-id="307d4-311">The goal is to only run the core CSS and JavaScript code that is required to display the page properly.</span></span>  

<span data-ttu-id="307d4-312">The first task, then, is to find code that you do not need to run on page load.</span><span class="sxs-lookup"><span data-stu-id="307d4-312">The first task, then, is to find code that you do not need to run on page load.</span></span>  

1.  <span data-ttu-id="307d4-313">Select **Eliminate render-blocking resources** to see the resources that are blocking:</span><span class="sxs-lookup"><span data-stu-id="307d4-313">Select **Eliminate render-blocking resources** to see the resources that are blocking:</span></span>  
    `lodash.js` <span data-ttu-id="307d4-314">and `jquery.js`.</span><span class="sxs-lookup"><span data-stu-id="307d4-314">and `jquery.js`.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded.msft.png":::
       <span data-ttu-id="307d4-316">More information about the **Eliminate render-blocking resources** opportunity</span><span class="sxs-lookup"><span data-stu-id="307d4-316">More information about the **Eliminate render-blocking resources** opportunity</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-317">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then select **Show Coverage**.</span><span class="sxs-lookup"><span data-stu-id="307d4-317">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu, start typing `Coverage`, and then select **Show Coverage**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-command-coverage.msft.png":::
       <span data-ttu-id="307d4-319">Open the Command Menu from the **Audits** panel</span><span class="sxs-lookup"><span data-stu-id="307d4-319">Open the Command Menu from the **Audits** panel</span></span>  
    :::image-end:::  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage.msft.png":::
       <span data-ttu-id="307d4-321">The **Coverage** tab</span><span class="sxs-lookup"><span data-stu-id="307d4-321">The **Coverage** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-322">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span><span class="sxs-lookup"><span data-stu-id="307d4-322">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="307d4-323">The **Coverage** tab provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span><span class="sxs-lookup"><span data-stu-id="307d4-323">The **Coverage** tab provides an overview of how much of the code in `bundle.js`, `jquery.js`, and `lodash.js` runs while the page loads.</span></span>  <span data-ttu-id="307d4-324">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span><span class="sxs-lookup"><span data-stu-id="307d4-324">In the figure after the following, about 76% and 30% of the jQuery and Lodash files are not used, respectively.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-audits-performance-oppportunities-expanded-drawer-coverage-reloaded.msft.png":::
       <span data-ttu-id="307d4-326">The Coverage report</span><span class="sxs-lookup"><span data-stu-id="307d4-326">The Coverage report</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-327">Select the **jquery.js** row.</span><span class="sxs-lookup"><span data-stu-id="307d4-327">Select the **jquery.js** row.</span></span>  <span data-ttu-id="307d4-328">DevTools opens the file in the Sources panel.</span><span class="sxs-lookup"><span data-stu-id="307d4-328">DevTools opens the file in the Sources panel.</span></span>  <span data-ttu-id="307d4-329">A line of code ran if it has a blue bar next to it.</span><span class="sxs-lookup"><span data-stu-id="307d4-329">A line of code ran if it has a blue bar next to it.</span></span>  <span data-ttu-id="307d4-330">A red bar means it was not run, and is definitely not needed on page load.</span><span class="sxs-lookup"><span data-stu-id="307d4-330">A red bar means it was not run, and is definitely not needed on page load.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-sources-drawer-coverage-reloaded-jquery-js.msft.png":::
       <span data-ttu-id="307d4-332">Viewing the jQuery file in the **Sources** panel</span><span class="sxs-lookup"><span data-stu-id="307d4-332">Viewing the jQuery file in the **Sources** panel</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-333">Scroll through the jQuery code a bit.</span><span class="sxs-lookup"><span data-stu-id="307d4-333">Scroll through the jQuery code a bit.</span></span>  <span data-ttu-id="307d4-334">Some of the lines that get "run" are actually just comments.</span><span class="sxs-lookup"><span data-stu-id="307d4-334">Some of the lines that get "run" are actually just comments.</span></span>  <span data-ttu-id="307d4-335">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span><span class="sxs-lookup"><span data-stu-id="307d4-335">Running this code through a minifier that strips comments is another way to reduce the size of this file.</span></span>  

<span data-ttu-id="307d4-336">In short, when you are working with your own code, the Coverage tab helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span><span class="sxs-lookup"><span data-stu-id="307d4-336">In short, when you are working with your own code, the Coverage tab helps you analyze your code, line-by-line, and only ship the code that is needed for page load.</span></span>  

<span data-ttu-id="307d4-337">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span><span class="sxs-lookup"><span data-stu-id="307d4-337">Are the `jquery.js` and `lodash.js` files even needed to load the page?</span></span>  <span data-ttu-id="307d4-338">The Request Blocking tab displays what happens when resources are not available.</span><span class="sxs-lookup"><span data-stu-id="307d4-338">The Request Blocking tab displays what happens when resources are not available.</span></span>  

1.  <span data-ttu-id="307d4-339">Select the **Network** tab.</span><span class="sxs-lookup"><span data-stu-id="307d4-339">Select the **Network** tab.</span></span>  
1.  <span data-ttu-id="307d4-340">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span><span class="sxs-lookup"><span data-stu-id="307d4-340">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu again.</span></span>  
1.  <span data-ttu-id="307d4-341">Start typing `blocking` and then select **Show Request Blocking**.</span><span class="sxs-lookup"><span data-stu-id="307d4-341">Start typing `blocking` and then select **Show Request Blocking**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-empty.msft.png":::
       <span data-ttu-id="307d4-343">The **Request Blocking** tab</span><span class="sxs-lookup"><span data-stu-id="307d4-343">The **Request Blocking** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-344">Select **Add Pattern** \(![Add Pattern][ImageAddPatternIcon]\), type `/libs/*`, and then press `Enter` to confirm.</span><span class="sxs-lookup"><span data-stu-id="307d4-344">Select **Add Pattern** \(![Add Pattern][ImageAddPatternIcon]\), type `/libs/*`, and then press `Enter` to confirm.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-network-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="307d4-346">Add a pattern to block any request to the `libs` directory</span><span class="sxs-lookup"><span data-stu-id="307d4-346">Add a pattern to block any request to the `libs` directory</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-347">Refresh the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-347">Refresh the page.</span></span>  <span data-ttu-id="307d4-348">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span><span class="sxs-lookup"><span data-stu-id="307d4-348">The jQuery and Lodash requests are red, meaning that the requests were blocked.</span></span>   <span data-ttu-id="307d4-349">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span><span class="sxs-lookup"><span data-stu-id="307d4-349">The page still loads and is interactive, so it looks like these resources are not needed whatsoever!</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-network-reloaded-drawer-request-blocking-added.msft.png":::
       <span data-ttu-id="307d4-351">The **Network** panel shows that the requests have been blocked</span><span class="sxs-lookup"><span data-stu-id="307d4-351">The **Network** panel shows that the requests have been blocked</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-352">Select **Remove all patterns** \(![Remove all patterns][ImageRemoveIcon]\) to delete the `/libs/*` blocking pattern.</span><span class="sxs-lookup"><span data-stu-id="307d4-352">Select **Remove all patterns** \(![Remove all patterns][ImageRemoveIcon]\) to delete the `/libs/*` blocking pattern.</span></span>  
    
<span data-ttu-id="307d4-353">In general, the Request Blocking tab is useful for simulating how your page behaves when any given resource is not available.</span><span class="sxs-lookup"><span data-stu-id="307d4-353">In general, the Request Blocking tab is useful for simulating how your page behaves when any given resource is not available.</span></span>  

<span data-ttu-id="307d4-354">Now, remove the references to these files from the code and audit the page again:</span><span class="sxs-lookup"><span data-stu-id="307d4-354">Now, remove the references to these files from the code and audit the page again:</span></span>  

1.  <span data-ttu-id="307d4-355">Back in the editor tab, open `template.html`.</span><span class="sxs-lookup"><span data-stu-id="307d4-355">Back in the editor tab, open `template.html`.</span></span>  
1.  <span data-ttu-id="307d4-356">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span><span class="sxs-lookup"><span data-stu-id="307d4-356">Delete `<script src="/libs/lodash.js">` and `<script src="/libs/jquery.js"></script>`.</span></span>  
1.  <span data-ttu-id="307d4-357">Wait for the site to re-build and re-deploy.</span><span class="sxs-lookup"><span data-stu-id="307d4-357">Wait for the site to re-build and re-deploy.</span></span>  
1.  <span data-ttu-id="307d4-358">Audit the page again from the **Audits** panel.</span><span class="sxs-lookup"><span data-stu-id="307d4-358">Audit the page again from the **Audits** panel.</span></span>  <span data-ttu-id="307d4-359">Your overall score should have improved again.</span><span class="sxs-lookup"><span data-stu-id="307d4-359">Your overall score should have improved again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-2-audits-performance.msft.png":::
       <span data-ttu-id="307d4-361">An **Audits** report after removing the render-blocking resources</span><span class="sxs-lookup"><span data-stu-id="307d4-361">An **Audits** report after removing the render-blocking resources</span></span>  
    :::image-end:::  
    
#### <span data-ttu-id="307d4-362">Optimizing the Critical Rendering Path in the real-world</span><span class="sxs-lookup"><span data-stu-id="307d4-362">Optimizing the Critical Rendering Path in the real-world</span></span>   

<span data-ttu-id="307d4-363">The **Critical Rendering Path** refers to the code that you need to load a page.</span><span class="sxs-lookup"><span data-stu-id="307d4-363">The **Critical Rendering Path** refers to the code that you need to load a page.</span></span>  <span data-ttu-id="307d4-364">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span><span class="sxs-lookup"><span data-stu-id="307d4-364">In general, speed up page load by only shipping critical code during the page load, and then lazy-loading everything else.</span></span>  

<!--[CRP]: /web/fundamentals/performance/critical-rendering-path/  -->  

*   <span data-ttu-id="307d4-365">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span><span class="sxs-lookup"><span data-stu-id="307d4-365">It is unlikely that you are able to find scripts that you are able to remove outright, but you may find many scripts that you do not need to request during the page load, and instead may be requested asynchronously.</span></span>  <!--See [Using async or defer][async].  -->  
*   <span data-ttu-id="307d4-366">If you are using a framework, check if it has a production mode.</span><span class="sxs-lookup"><span data-stu-id="307d4-366">If you are using a framework, check if it has a production mode.</span></span>  <span data-ttu-id="307d4-367">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span><span class="sxs-lookup"><span data-stu-id="307d4-367">This mode may use a feature such as [tree shaking][WebpackTreeShaking] in order to eliminate unnecessary code that is blocking the critical render.</span></span>  
    
<!--[async]: /web/fundamentals/performance/optimizing-content-efficiency/loading-third-party-javascript/#use_async_or_defer  -->  

### <span data-ttu-id="307d4-368">Do less main thread work</span><span class="sxs-lookup"><span data-stu-id="307d4-368">Do less main thread work</span></span>   

<span data-ttu-id="307d4-369">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span><span class="sxs-lookup"><span data-stu-id="307d4-369">Your latest report shows some minor potential savings in the Opportunities section, but if you look down in the Diagnostics section, it looks like the biggest bottleneck is too much main thread activity.</span></span>  

<span data-ttu-id="307d4-370">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span><span class="sxs-lookup"><span data-stu-id="307d4-370">The main thread is where the browser does most of the work needed to display a page, such as parsing and running HTML, CSS, and JavaScript.</span></span>  

<span data-ttu-id="307d4-371">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span><span class="sxs-lookup"><span data-stu-id="307d4-371">The goal is to use the Performance panel to analyze what work the main thread is doing while the page loads, and find ways to defer or remove unnecessary work.</span></span>  

1.  <span data-ttu-id="307d4-372">Select the **Performance** tab.</span><span class="sxs-lookup"><span data-stu-id="307d4-372">Select the **Performance** tab.</span></span>  
1.  <span data-ttu-id="307d4-373">Select **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span><span class="sxs-lookup"><span data-stu-id="307d4-373">Select **Capture Settings** \(![Capture Settings][ImageCaptureIcon]\).</span></span>  
1.  <span data-ttu-id="307d4-374">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span><span class="sxs-lookup"><span data-stu-id="307d4-374">Set **Network** to **Slow 3G** and **CPU** to **6x slowdown**.</span></span>  <span data-ttu-id="307d4-375">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span><span class="sxs-lookup"><span data-stu-id="307d4-375">Mobile devices typically have more hardware constraints than laptops or desktops, so these settings let you experience the page load as if you were using a less powerful device.</span></span>  
1.  <span data-ttu-id="307d4-376">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span><span class="sxs-lookup"><span data-stu-id="307d4-376">Select **Refresh** \(![Refresh][ImageRefreshIcon]\).</span></span>  <span data-ttu-id="307d4-377">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span><span class="sxs-lookup"><span data-stu-id="307d4-377">DevTools refreshes the page and then produces a visualization of all the work performed in order to load the page.</span></span>  <span data-ttu-id="307d4-378">This visualization is referred to as the **trace**.</span><span class="sxs-lookup"><span data-stu-id="307d4-378">This visualization is referred to as the **trace**.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu.msft.png":::
       <span data-ttu-id="307d4-380">The **Performance** panel trace of the page load</span><span class="sxs-lookup"><span data-stu-id="307d4-380">The **Performance** panel trace of the page load</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-381">The trace shows activity chronologically, from left to right.</span><span class="sxs-lookup"><span data-stu-id="307d4-381">The trace shows activity chronologically, from left to right.</span></span>  <span data-ttu-id="307d4-382">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span><span class="sxs-lookup"><span data-stu-id="307d4-382">The FPS, CPU, and NET charts at the top give you an overview of frames per second, CPU activity, and network activity.</span></span>  <span data-ttu-id="307d4-383">The block of yellow selected that you see in the figure after the following, the CPU was completely busy with scripting activity.</span><span class="sxs-lookup"><span data-stu-id="307d4-383">The block of yellow selected that you see in the figure after the following, the CPU was completely busy with scripting activity.</span></span>  <span data-ttu-id="307d4-384">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span><span class="sxs-lookup"><span data-stu-id="307d4-384">This is a clue that you may be able to speed up page load by doing less JavaScript work.</span></span>  

:::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main-highlight.msft.png":::
   <span data-ttu-id="307d4-386">The Overview section of the trace</span><span class="sxs-lookup"><span data-stu-id="307d4-386">The Overview section of the trace</span></span>  
:::image-end:::  

<span data-ttu-id="307d4-387">Investigate the trace to find ways to do less JavaScript work:</span><span class="sxs-lookup"><span data-stu-id="307d4-387">Investigate the trace to find ways to do less JavaScript work:</span></span>  

1.  <span data-ttu-id="307d4-388">Select the **Timings** section to expand it.</span><span class="sxs-lookup"><span data-stu-id="307d4-388">Select the **Timings** section to expand it.</span></span>  <span data-ttu-id="307d4-389">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span><span class="sxs-lookup"><span data-stu-id="307d4-389">Based on the fact that there may be a bunch of [Timings][MDNUserTimingApi] measures from React, it seems like Tony's app is using the development mode of React.</span></span>  <span data-ttu-id="307d4-390">Switching to the production mode of React may yield some easy performance wins.</span><span class="sxs-lookup"><span data-stu-id="307d4-390">Switching to the production mode of React may yield some easy performance wins.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings.msft.png":::
       <span data-ttu-id="307d4-392">The **Timings** section</span><span class="sxs-lookup"><span data-stu-id="307d4-392">The **Timings** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-393">Select **Timings** again to collapse that section.</span><span class="sxs-lookup"><span data-stu-id="307d4-393">Select **Timings** again to collapse that section.</span></span>  
1.  <span data-ttu-id="307d4-394">Browse the **Main** section.</span><span class="sxs-lookup"><span data-stu-id="307d4-394">Browse the **Main** section.</span></span>  <span data-ttu-id="307d4-395">This section shows a chronological log of main thread activity, from left to right.</span><span class="sxs-lookup"><span data-stu-id="307d4-395">This section shows a chronological log of main thread activity, from left to right.</span></span>  <span data-ttu-id="307d4-396">The y-axis (top to bottom) shows why events occurred.</span><span class="sxs-lookup"><span data-stu-id="307d4-396">The y-axis (top to bottom) shows why events occurred.</span></span>  <span data-ttu-id="307d4-397">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span><span class="sxs-lookup"><span data-stu-id="307d4-397">For example, in the figyre after the following, the `Evaluate Script` event caused the `(anonymous)` function to run, which caused `(anonymous)` to run, which caused `__webpack__require__` to run, and so on.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-main.msft.png":::
       <span data-ttu-id="307d4-399">The **Main** section</span><span class="sxs-lookup"><span data-stu-id="307d4-399">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="307d4-400">Scroll down to the bottom of the **Main** section.</span><span class="sxs-lookup"><span data-stu-id="307d4-400">Scroll down to the bottom of the **Main** section.</span></span>  <span data-ttu-id="307d4-401">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span><span class="sxs-lookup"><span data-stu-id="307d4-401">When you use a framework, most of the upper activity is caused by the framework, which is usually out of your control.</span></span>  <span data-ttu-id="307d4-402">The activity caused by your app is usually at the bottom.</span><span class="sxs-lookup"><span data-stu-id="307d4-402">The activity caused by your app is usually at the bottom.</span></span>  <span data-ttu-id="307d4-403">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span><span class="sxs-lookup"><span data-stu-id="307d4-403">In this app, it seems like a function named `App` is causing a lot of requests to a `mineBitcoin` function.</span></span>  <span data-ttu-id="307d4-404">It sounds like Tony might be using the devices of his fans to mine cryptocurrency...</span><span class="sxs-lookup"><span data-stu-id="307d4-404">It sounds like Tony might be using the devices of his fans to mine cryptocurrency...</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-minebitcoin.msft.png":::
       <span data-ttu-id="307d4-406">Hover on the `mineBitcoin` activity</span><span class="sxs-lookup"><span data-stu-id="307d4-406">Hover on the `mineBitcoin` activity</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="307d4-407">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span><span class="sxs-lookup"><span data-stu-id="307d4-407">Although the requests that your framework makes are usually out of your control, sometimes you may structure your app in a way that causes the framework to run inefficiently.</span></span>  <span data-ttu-id="307d4-408">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span><span class="sxs-lookup"><span data-stu-id="307d4-408">Restructuring your app to use the framework efficiently is a way to do less main thread work.</span></span>  <span data-ttu-id="307d4-409">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span><span class="sxs-lookup"><span data-stu-id="307d4-409">However, this requires a deep understanding of how your framework works, and what kind of changes you make in your own code in order to use the framework more efficiently.</span></span>  
    
1.  <span data-ttu-id="307d4-410">Expand the **Bottom-Up** section.</span><span class="sxs-lookup"><span data-stu-id="307d4-410">Expand the **Bottom-Up** section.</span></span>  <span data-ttu-id="307d4-411">This tab breaks down what activities took up the most time.</span><span class="sxs-lookup"><span data-stu-id="307d4-411">This tab breaks down what activities took up the most time.</span></span>  <span data-ttu-id="307d4-412">If you do not see anything in the Bottom-Up section, click the label for **Main** section.</span><span class="sxs-lookup"><span data-stu-id="307d4-412">If you do not see anything in the Bottom-Up section, click the label for **Main** section.</span></span>  <span data-ttu-id="307d4-413">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span><span class="sxs-lookup"><span data-stu-id="307d4-413">The **Bottom-Up** section only shows information for whatever activity, or group of activity, you have currently selected.</span></span>  <span data-ttu-id="307d4-414">For example, if you clicked on one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span><span class="sxs-lookup"><span data-stu-id="307d4-414">For example, if you clicked on one of the `mineBitcoin` activities, the **Bottom-Up** section is only going to show information for that one activity.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-performance-slow-network-slow-cpu-timings-summary-minebitcoin.msft.png":::
       <span data-ttu-id="307d4-416">The **Bottom-Up** tab</span><span class="sxs-lookup"><span data-stu-id="307d4-416">The **Bottom-Up** tab</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-417">The **Self Time** column shows you how much time was spent directly in each activity.</span><span class="sxs-lookup"><span data-stu-id="307d4-417">The **Self Time** column shows you how much time was spent directly in each activity.</span></span>  <span data-ttu-id="307d4-418">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span><span class="sxs-lookup"><span data-stu-id="307d4-418">For example, in the following figure, about 63% of main thread time was spent on the `mineBitcoin` function.</span></span>  

<span data-ttu-id="307d4-419">Time to see whether using production mode and reducing JavaScript activity may speed up the page load.</span><span class="sxs-lookup"><span data-stu-id="307d4-419">Time to see whether using production mode and reducing JavaScript activity may speed up the page load.</span></span>  <span data-ttu-id="307d4-420">Start with production mode:</span><span class="sxs-lookup"><span data-stu-id="307d4-420">Start with production mode:</span></span>  

1.  <span data-ttu-id="307d4-421">In the editor tab, open `webpack.config.js`.</span><span class="sxs-lookup"><span data-stu-id="307d4-421">In the editor tab, open `webpack.config.js`.</span></span>  
1.  <span data-ttu-id="307d4-422">Change `"mode":"development"` to `"mode":"production"`.</span><span class="sxs-lookup"><span data-stu-id="307d4-422">Change `"mode":"development"` to `"mode":"production"`.</span></span>  
1.  <span data-ttu-id="307d4-423">Wait for the new build to deploy.</span><span class="sxs-lookup"><span data-stu-id="307d4-423">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="307d4-424">Audit the page again.</span><span class="sxs-lookup"><span data-stu-id="307d4-424">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-3-audits-performance.msft.png":::
       <span data-ttu-id="307d4-426">An Audits report after configuring webpack to use production mode</span><span class="sxs-lookup"><span data-stu-id="307d4-426">An Audits report after configuring webpack to use production mode</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-427">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span><span class="sxs-lookup"><span data-stu-id="307d4-427">Reduce JavaScript activity by removing the request to `mineBitcoin`:</span></span>  

1.  <span data-ttu-id="307d4-428">In the editor tab, open `src/App.jsx`.</span><span class="sxs-lookup"><span data-stu-id="307d4-428">In the editor tab, open `src/App.jsx`.</span></span>  
1.  <span data-ttu-id="307d4-429">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span><span class="sxs-lookup"><span data-stu-id="307d4-429">Comment out the request to `this.mineBitcoin(1500)` in the `constructor`.</span></span>  
1.  <span data-ttu-id="307d4-430">Wait for the new build to deploy.</span><span class="sxs-lookup"><span data-stu-id="307d4-430">Wait for the new build to deploy.</span></span>  
1.  <span data-ttu-id="307d4-431">Audit the page again.</span><span class="sxs-lookup"><span data-stu-id="307d4-431">Audit the page again.</span></span>  
    
    :::image type="complex" source="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png" alt-text="Tony the cat" lightbox="../media/speed-glitch-tony-remix-updated-4-audits-performance.msft.png":::
       <span data-ttu-id="307d4-433">An Audits report after removing unnecessary JavaScript work</span><span class="sxs-lookup"><span data-stu-id="307d4-433">An Audits report after removing unnecessary JavaScript work</span></span>  
    :::image-end:::  
    
<span data-ttu-id="307d4-434">Looks like that last change caused a massive jump in performance!</span><span class="sxs-lookup"><span data-stu-id="307d4-434">Looks like that last change caused a massive jump in performance!</span></span>  

> [!NOTE]
> <span data-ttu-id="307d4-435">This section provided a rather brief introduction to the Performance panel.</span><span class="sxs-lookup"><span data-stu-id="307d4-435">This section provided a rather brief introduction to the Performance panel.</span></span>  <span data-ttu-id="307d4-436">See [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference] to learn more about how to analyze page performance.</span><span class="sxs-lookup"><span data-stu-id="307d4-436">See [Performance Analysis Reference][DevtoolsEvaluatePerformanceReference] to learn more about how to analyze page performance.</span></span>  

<!--todo: add section when available -->  

#### <span data-ttu-id="307d4-437">Doing less main thread work in the real world</span><span class="sxs-lookup"><span data-stu-id="307d4-437">Doing less main thread work in the real world</span></span>   

<span data-ttu-id="307d4-438">In general, the **Performance** panel is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span><span class="sxs-lookup"><span data-stu-id="307d4-438">In general, the **Performance** panel is the most common way to understand what activity your site does as it loads, and find ways to remove unnecessary activity.</span></span>  

<span data-ttu-id="307d4-439">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span><span class="sxs-lookup"><span data-stu-id="307d4-439">If you prefer an approach that feels more like `console.log()`, the [User Timing API][MDNUserTimingApi] enables you to arbitrarily mark up certain phases of your app lifecycle, in order to track how long each of those phases takes.</span></span>  

## <span data-ttu-id="307d4-440">Summary</span><span class="sxs-lookup"><span data-stu-id="307d4-440">Summary</span></span>   

*   <span data-ttu-id="307d4-441">Whenever you set out to optimize the load performance of a site, always start with an audit.</span><span class="sxs-lookup"><span data-stu-id="307d4-441">Whenever you set out to optimize the load performance of a site, always start with an audit.</span></span>  <span data-ttu-id="307d4-442">The audit establishes a baseline, and gives you tips on how to improve.</span><span class="sxs-lookup"><span data-stu-id="307d4-442">The audit establishes a baseline, and gives you tips on how to improve.</span></span>  
*   <span data-ttu-id="307d4-443">Make one change at a time, and audit the page after each change in order to see how that isolated change affects performance.</span><span class="sxs-lookup"><span data-stu-id="307d4-443">Make one change at a time, and audit the page after each change in order to see how that isolated change affects performance.</span></span>  

<!--
## Next steps   

*   Run audits on your own site!  If you need help interpreting your report, or finding ways to improve your load performance, check out [Feedback](#feedback) for ways to get help from the DevTools community.  Stack Overflow, the mailing list, or Twitter are probably best for these types of questions.  
*   Please leave [feedback](#feedback) on this tutorial.  I really do use the data to make better tutorials for you.  
-->  

<!--  
  


-->  

<!-- image links -->  

[ImageAddPatternIcon]: ../media/add-pattern-icon.msft.png  
[ImageCaptureIcon]: ../media/capture-icon.msft.png  
[ImageLargeResourceRowsButtonIcon]: ../media/large-resource-rows-button-icon.msft.png  
[ImageMorePanelsIcon]: ../media/more-panels-icon.msft.png  
[ImagePerformIcon]: ../media/perform-icon.msft.png  
[ImageRefreshIcon]: ../media/reload-icon.msft.png  
[ImageRemoveIcon]: ../media/remove-icon.msft.png  
<!-- links -->  

[DevtoolsEvaluatePerformanceReference]: ../evaluate-performance/reference.md "Performance analysis reference | Microsoft Docs"  

[CourseraIntroductionWebDevelopmentClass]: https://www.coursera.org/learn/web-development#syllabus "Introduction to Web Development class | Coursera"  

[EssentialImageOptimization]: https://images.guide "Essential Image Optimization"  

[MDNContentEncodingDirectives]: https://developer.mozilla.org/docs/Web/HTTP/Headers/Content-Encoding#Directives "Directives - Content-Encoding | MDN"  
[MDNUserTimingApi]: https://developer.mozilla.org/docs/Web/API/User_Timing_API "User Timing API | MDN"  

[WebpackTreeShaking]: https://webpack.js.org/guides/tree-shaking "Tree Shaking | webpack"  

> [!NOTE]
> <span data-ttu-id="307d4-450">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="307d4-450">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="307d4-451">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/speed/get-started)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="307d4-451">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/speed/get-started) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="307d4-453">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="307d4-453">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
