---
description: A reference on all the ways to record and analyze performance in Microsoft Edge DevTools.
title: Performance Analysis Reference
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 0e81cb89f0e690533bdd9c8fdbfce272610be783
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992902"
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







# <span data-ttu-id="f2a9f-104">Performance analysis reference</span><span class="sxs-lookup"><span data-stu-id="f2a9f-104">Performance analysis reference</span></span>   



<span data-ttu-id="f2a9f-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-105">This page is a comprehensive reference of Microsoft Edge DevTools features related to analyzing performance.</span></span>  

<span data-ttu-id="f2a9f-106">See [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span><span class="sxs-lookup"><span data-stu-id="f2a9f-106">See [Get Started With Analyzing Runtime Performance][DevtoolsEvaluatePerformanceGettingStarted] for a guided tutorial on how to analyze the performance of a page using [Microsoft Edge DevTools][MicrosoftEdgeDevTools].</span></span>  

## <span data-ttu-id="f2a9f-107">Record performance</span><span class="sxs-lookup"><span data-stu-id="f2a9f-107">Record performance</span></span>   

### <span data-ttu-id="f2a9f-108">Record runtime performance</span><span class="sxs-lookup"><span data-stu-id="f2a9f-108">Record runtime performance</span></span>   

<span data-ttu-id="f2a9f-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-109">Record runtime performance when you want to analyze the performance of a page as it is running, as opposed to loading.</span></span>  

1.  <span data-ttu-id="f2a9f-110">Go to the page that you want to analyze.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-110">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="f2a9f-111">Click the **Performance** tab in DevTools.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-111">Click the **Performance** tab in DevTools.</span></span>  
1.  <span data-ttu-id="f2a9f-112">Click **Record** \(![Record][ImageRecordIcon]\).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-112">Click **Record** \(![Record][ImageRecordIcon]\).</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-record-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-record-highlight.msft.png":::
       **<span data-ttu-id="f2a9f-114">Record</span><span class="sxs-lookup"><span data-stu-id="f2a9f-114">Record</span></span>**  
    :::image-end:::  
    
1.  <span data-ttu-id="f2a9f-115">Interact with the page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-115">Interact with the page.</span></span>  <span data-ttu-id="f2a9f-116">DevTools records all page activity that occurs as a result of your interactions.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-116">DevTools records all page activity that occurs as a result of your interactions.</span></span>  
1.  <span data-ttu-id="f2a9f-117">Click **Record** again or click **Stop** to stop recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-117">Click **Record** again or click **Stop** to stop recording.</span></span>  
    
### <span data-ttu-id="f2a9f-118">Record load performance</span><span class="sxs-lookup"><span data-stu-id="f2a9f-118">Record load performance</span></span>   

<span data-ttu-id="f2a9f-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-119">Record load performance when you want to analyze the performance of a page as it is loading, as opposed to running.</span></span>  

1.  <span data-ttu-id="f2a9f-120">Go to the page that you want to analyze.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-120">Go to the page that you want to analyze.</span></span>  
1.  <span data-ttu-id="f2a9f-121">Open the **Performance** panel of DevTools.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-121">Open the **Performance** panel of DevTools.</span></span>  
1.  <span data-ttu-id="f2a9f-122">Click **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-122">Click **Refresh page** \(![Refresh Page][ImageRefreshPageIcon]\).</span></span>  <span data-ttu-id="f2a9f-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-123">DevTools records performance metrics while the page refreshes and then automatically stops the recording a couple seconds after the load finishes.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-refresh-button.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refresh-button.msft.png":::
       **<span data-ttu-id="f2a9f-125">Refresh page</span><span class="sxs-lookup"><span data-stu-id="f2a9f-125">Refresh page</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="f2a9f-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-126">DevTools automatically zooms in on the portion of the recording where most of the activity occurred.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed.msft.png":::
   <span data-ttu-id="f2a9f-128">A page-load recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-128">A page-load recording</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-129">Capture screenshots while recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-129">Capture screenshots while recording</span></span>   

<span data-ttu-id="f2a9f-130">Enable the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-130">Enable the **Screenshots** checkbox to capture a screenshot of every frame while recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-capture-screenshots-checkbox.msft.png":::
   <span data-ttu-id="f2a9f-132">The **Screenshots** checkbox</span><span class="sxs-lookup"><span data-stu-id="f2a9f-132">The **Screenshots** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-133">See [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-133">See [View a screenshot](#view-a-screenshot) to learn how to interact with screenshots.</span></span>  

### <span data-ttu-id="f2a9f-134">Force garbage collection while recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-134">Force garbage collection while recording</span></span>   

<span data-ttu-id="f2a9f-135">While you are recording a page, click **Collect garbage** \(![Collect garbage][ImageCollectGarbageIcon]\) to force garbage collection.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-135">While you are recording a page, click **Collect garbage** \(![Collect garbage][ImageCollectGarbageIcon]\) to force garbage collection.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-collect-garbage-button.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-collect-garbage-button.msft.png":::
   <span data-ttu-id="f2a9f-137">Collect garbage</span><span class="sxs-lookup"><span data-stu-id="f2a9f-137">Collect garbage</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-138">Show recording settings</span><span class="sxs-lookup"><span data-stu-id="f2a9f-138">Show recording settings</span></span>   

<span data-ttu-id="f2a9f-139">Click **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-139">Click **Capture settings** \(![Capture settings][ImageCaptureSettingsIcon]\) to expose more settings related to how DevTools captures performance recordings.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-capture-settings-button-open-drawer.msft.png":::
   <span data-ttu-id="f2a9f-141">The **Capture Settings** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-141">The **Capture Settings** section</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-142">Disable JavaScript samples</span><span class="sxs-lookup"><span data-stu-id="f2a9f-142">Disable JavaScript samples</span></span>   

<span data-ttu-id="f2a9f-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-143">By default, the **Main** section of a recording displays detailed call stacks of JavaScript functions that were called during the recording.</span></span>  <span data-ttu-id="f2a9f-144">To disable these call stacks:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-144">To disable these call stacks:</span></span>  

1.  <span data-ttu-id="f2a9f-145">Open the **Capture settings** menu.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-145">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="f2a9f-146">See [Show recording settings](#show-recording-settings).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-146">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="f2a9f-147">Enable the **Disable JavaScript Samples** checkbox.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-147">Enable the **Disable JavaScript Samples** checkbox.</span></span>  
1.  <span data-ttu-id="f2a9f-148">Take a recording of the page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-148">Take a recording of the page.</span></span>  
    
<span data-ttu-id="f2a9f-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-149">The following 2 figures display the difference between disabling and enabling JavaScript samples.</span></span>  <span data-ttu-id="f2a9f-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-150">The **Main** section of the recording is much shorter when sampling is disabled, because it omits all of the JavaScript call stacks.</span></span>  

:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-on.msft.png":::
         <span data-ttu-id="f2a9f-152">An example of a recording when JS samples are disabled</span><span class="sxs-lookup"><span data-stu-id="f2a9f-152">An example of a recording when JS samples are disabled</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off.msft.png":::
         <span data-ttu-id="f2a9f-154">An example of a recording when JS samples are enabled</span><span class="sxs-lookup"><span data-stu-id="f2a9f-154">An example of a recording when JS samples are enabled</span></span>  
      :::image-end:::  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="f2a9f-155">Throttle the network while recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-155">Throttle the network while recording</span></span>   

<span data-ttu-id="f2a9f-156">To throttle the network while recording:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-156">To throttle the network while recording:</span></span>  

1.  <span data-ttu-id="f2a9f-157">Open the **Capture settings** menu.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-157">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="f2a9f-158">See [Show recording settings](#show-recording-settings).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-158">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="f2a9f-159">Set **Network** to the desired level of throttling.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-159">Set **Network** to the desired level of throttling.</span></span>  
    
### <span data-ttu-id="f2a9f-160">Throttle the CPU while recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-160">Throttle the CPU while recording</span></span>   

<span data-ttu-id="f2a9f-161">To throttle the CPU while recording:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-161">To throttle the CPU while recording:</span></span>  

1.  <span data-ttu-id="f2a9f-162">Open the **Capture settings** menu.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-162">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="f2a9f-163">See [Show recording settings](#show-recording-settings).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-163">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="f2a9f-164">Set **CPU** to the desired level of throttling.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-164">Set **CPU** to the desired level of throttling.</span></span>  
    
<span data-ttu-id="f2a9f-165">Throttling is relative to the capabilities of your computer.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-165">Throttling is relative to the capabilities of your computer.</span></span>  <span data-ttu-id="f2a9f-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-166">For example, the **2x slowdown** option makes your CPU operate 2 times slower than normal.</span></span>  <span data-ttu-id="f2a9f-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-167">DevTools do not truly simulate the CPUs of mobile devices, because the architecture of mobile devices is very different from that of desktops and laptops.</span></span>  

### <span data-ttu-id="f2a9f-168">Enable advanced paint instrumentation</span><span class="sxs-lookup"><span data-stu-id="f2a9f-168">Enable advanced paint instrumentation</span></span>   

<span data-ttu-id="f2a9f-169">To view detailed paint instrumentation:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-169">To view detailed paint instrumentation:</span></span>  

1.  <span data-ttu-id="f2a9f-170">Open the **Capture settings** menu.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-170">Open the **Capture settings** menu.</span></span>  <span data-ttu-id="f2a9f-171">See [Show recording settings](#show-recording-settings).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-171">See [Show recording settings](#show-recording-settings).</span></span>  
1.  <span data-ttu-id="f2a9f-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-172">Check the **Enable advanced paint instrumentation (slow)** checkbox.</span></span>  

<span data-ttu-id="f2a9f-173">To learn how to interact with the paint information, see [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-173">To learn how to interact with the paint information, see [View layers](#view-layers-information) and [View paint profiler](#view-paint-profiler).</span></span>  

## <span data-ttu-id="f2a9f-174">Save a recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-174">Save a recording</span></span>   

<span data-ttu-id="f2a9f-175">To save a recording, right-click and select **Save Profile**.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-175">To save a recording, right-click and select **Save Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-save-profile.msft.png":::
   **<span data-ttu-id="f2a9f-177">Save Profile</span><span class="sxs-lookup"><span data-stu-id="f2a9f-177">Save Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="f2a9f-178">Load a recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-178">Load a recording</span></span>   

<span data-ttu-id="f2a9f-179">To load a recording, right-click and select **Load Profile**.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-179">To load a recording, right-click and select **Load Profile**.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-load-profile.msft.png":::
   **<span data-ttu-id="f2a9f-181">Load Profile</span><span class="sxs-lookup"><span data-stu-id="f2a9f-181">Load Profile</span></span>**  
:::image-end:::  

## <span data-ttu-id="f2a9f-182">Clear the previous recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-182">Clear the previous recording</span></span>   

<span data-ttu-id="f2a9f-183">After making a recording, press **Clear recording** \(![Clear recording][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-183">After making a recording, press **Clear recording** \(![Clear recording][ImageClearRecordingIcon]\) to clear that recording from the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-refreshed-disable-javascript-samples-checkbox-off-clear-button.msft.png":::
   **<span data-ttu-id="f2a9f-185">Clear recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-185">Clear recording</span></span>**  
:::image-end:::  

## <span data-ttu-id="f2a9f-186">Analyze a performance recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-186">Analyze a performance recording</span></span>   

<span data-ttu-id="f2a9f-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-187">After you [record runtime performance](#record-runtime-performance) or [record load performance](#record-load-performance), the **Performance** panel provides a lot of data for analyzing the performance of what just happened.</span></span>  

### <span data-ttu-id="f2a9f-188">Select a portion of a recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-188">Select a portion of a recording</span></span>   

<span data-ttu-id="f2a9f-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-189">Drag your mouse left or right across the **Overview** to select a portion of a recording.</span></span>  <span data-ttu-id="f2a9f-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-190">The **Overview** is the section that contains the **FPS**, **CPU**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-zoom-highlighted.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-zoom-highlighted.msft.png":::
   <span data-ttu-id="f2a9f-192">Drag the mouse across the **Overview** to zoom</span><span class="sxs-lookup"><span data-stu-id="f2a9f-192">Drag the mouse across the **Overview** to zoom</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-193">To select a portion using the keyboard:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-193">To select a portion using the keyboard:</span></span>  

1.  <span data-ttu-id="f2a9f-194">Click on the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-194">Click on the background of the **Main** section, or any of the sections next to it, such as **Interactions**, **Network**, or **GPU**.</span></span>  <span data-ttu-id="f2a9f-195">This keyboard workflow only works when one of these sections is in focus.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-195">This keyboard workflow only works when one of these sections is in focus.</span></span>  
1.  <span data-ttu-id="f2a9f-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-196">Use the `W`, `A`, `S`, `D` keys to zoom in, move left, zoom out, and move right, respectively.</span></span>  

<span data-ttu-id="f2a9f-197">To select a portion using a trackpad:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-197">To select a portion using a trackpad:</span></span>  

1.  <span data-ttu-id="f2a9f-198">Hover your mouse over the **Overview** section or the **Details** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-198">Hover your mouse over the **Overview** section or the **Details** section.</span></span>  <span data-ttu-id="f2a9f-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-199">The **Overview** section is the area containing the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="f2a9f-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-200">The **Details** section is the area containing the **Main** section, the **Interactions** section, and so on.</span></span>  
1.  <span data-ttu-id="f2a9f-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-201">Using two fingers, swipe up to zoom out, swipe left to move left, swipe down to zoom in, and swipe right to move right.</span></span>  

<span data-ttu-id="f2a9f-202">To scroll a long flame chart in the **Main** section or any of the neighbors, click and hold while dragging up and down.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-202">To scroll a long flame chart in the **Main** section or any of the neighbors, click and hold while dragging up and down.</span></span>  <span data-ttu-id="f2a9f-203">Drag left and right to move what portion of the recording is selected.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-203">Drag left and right to move what portion of the recording is selected.</span></span>  

### <span data-ttu-id="f2a9f-204">Search activities</span><span class="sxs-lookup"><span data-stu-id="f2a9f-204">Search activities</span></span>   

<span data-ttu-id="f2a9f-205">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-205">Press `Control`+`F` \(Windows\) or `Command`+`F` \(macOS\) to open the search box at the bottom of the **Performance** panel.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-search-regex.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-search-regex.msft.png":::
   <span data-ttu-id="f2a9f-207">The search box</span><span class="sxs-lookup"><span data-stu-id="f2a9f-207">The search box</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-208">To navigate activities that match your query:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-208">To navigate activities that match your query:</span></span>  

*   <span data-ttu-id="f2a9f-209">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-209">Use the **Previous** \(![Previous][ImagePreviousIcon]\) and **Next** \(![Next][ImageNextIcon]\) buttons.</span></span>  
*   <span data-ttu-id="f2a9f-210">Press `Shift`+`Enter` to select the previous or `Enter` to select the next.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-210">Press `Shift`+`Enter` to select the previous or `Enter` to select the next.</span></span>  

<span data-ttu-id="f2a9f-211">To modify query settings:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-211">To modify query settings:</span></span>  

*   <span data-ttu-id="f2a9f-212">Press **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-212">Press **Case sensitive** \(![Case sensitive][ImageSearchCaseIcon]\) to make the query case sensitive.</span></span>  
*   <span data-ttu-id="f2a9f-213">Press **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-213">Press **Regex** \(![Regex][ImageSearchRegexIcon]\) to use a regular expression in your query.</span></span>  

<span data-ttu-id="f2a9f-214">To hide the search box, press **Cancel**.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-214">To hide the search box, press **Cancel**.</span></span>  

### <span data-ttu-id="f2a9f-215">View main thread activity</span><span class="sxs-lookup"><span data-stu-id="f2a9f-215">View main thread activity</span></span>   

<span data-ttu-id="f2a9f-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-216">Use the **Main** section to view activity that occurred on the main thread of the page.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
   <span data-ttu-id="f2a9f-218">The **Main** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-218">The **Main** section</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-219">Click on an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-219">Click on an event to view more information about it in the **Summary** tab.  DevTools outlines the selected event.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-me.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-summary-me.msft.png":::
   <span data-ttu-id="f2a9f-221">More information about the `anonymous` function in the **Summary** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-221">More information about the `anonymous` function in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-222">DevTools represents main thread activity with a flame chart.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-222">DevTools represents main thread activity with a flame chart.</span></span>  <span data-ttu-id="f2a9f-223">The x-axis represents the recording over time.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-223">The x-axis represents the recording over time.</span></span>  <span data-ttu-id="f2a9f-224">The y-axis represents the call stack.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-224">The y-axis represents the call stack.</span></span>  <span data-ttu-id="f2a9f-225">The events on top cause the events below it.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-225">The events on top cause the events below it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-flame-chart.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-main-flame-chart.msft.png":::
   <span data-ttu-id="f2a9f-227">A flame chart</span><span class="sxs-lookup"><span data-stu-id="f2a9f-227">A flame chart</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-228">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-228">In the previous figure, a `click` event caused a `Function Call` in `activitytabs.js` on line 53.</span></span>  <span data-ttu-id="f2a9f-229">Below `Function Call` you see that an anonymous function was called.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-229">Below `Function Call` you see that an anonymous function was called.</span></span>  <span data-ttu-id="f2a9f-230">The anonymous function called `a`, which called `wait`, which called `Minor GC`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-230">The anonymous function called `a`, which called `wait`, which called `Minor GC`.</span></span>  

<span data-ttu-id="f2a9f-231">DevTools assigns scripts random colors.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-231">DevTools assigns scripts random colors.</span></span>  <span data-ttu-id="f2a9f-232">In the previous figure, function calls from one script are colored light green.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-232">In the previous figure, function calls from one script are colored light green.</span></span>  <span data-ttu-id="f2a9f-233">Calls from another script are colored beige.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-233">Calls from another script are colored beige.</span></span>  <span data-ttu-id="f2a9f-234">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-234">The darker yellow represents scripting activity, and the purple event represents rendering activity.</span></span>  <span data-ttu-id="f2a9f-235">These darker yellow and purple events are consistent across all recordings.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-235">These darker yellow and purple events are consistent across all recordings.</span></span>  

<span data-ttu-id="f2a9f-236">See [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript calls.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-236">See [Disable JavaScript samples](#disable-javascript-samples) if you want to hide the detailed flame chart of JavaScript calls.</span></span>  <span data-ttu-id="f2a9f-237">When JS samples are disabled, you only see high-level events such as `Event: click` and `Function Call` from the previous figure.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-237">When JS samples are disabled, you only see high-level events such as `Event: click` and `Function Call` from the previous figure.</span></span>  

### <span data-ttu-id="f2a9f-238">View activities in a table</span><span class="sxs-lookup"><span data-stu-id="f2a9f-238">View activities in a table</span></span>   

<span data-ttu-id="f2a9f-239">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-239">After recording a page, you do not need to rely solely on the **Main** section to analyze activities.</span></span>  <span data-ttu-id="f2a9f-240">DevTools also provides three tabular views for analyzing activities.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-240">DevTools also provides three tabular views for analyzing activities.</span></span>  <span data-ttu-id="f2a9f-241">Each view gives you a different perspective on the activities:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-241">Each view gives you a different perspective on the activities:</span></span>  

*   <span data-ttu-id="f2a9f-242">When you want to view the root activities that cause the most work, use [the Call Tree tab](#the-call-tree-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-242">When you want to view the root activities that cause the most work, use [the Call Tree tab](#the-call-tree-tab).</span></span>  
*   <span data-ttu-id="f2a9f-243">When you want to view the activities where the most time was directly spent, use [the Bottom-Up tab](#the-bottom-up-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-243">When you want to view the activities where the most time was directly spent, use [the Bottom-Up tab](#the-bottom-up-tab).</span></span>  
*   <span data-ttu-id="f2a9f-244">When you want to view the activities in the order in which they occurred during the recording, use [the Event Log tab](#the-event-log-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-244">When you want to view the activities in the order in which they occurred during the recording, use [the Event Log tab](#the-event-log-tab).</span></span>  
    
> [!NOTE]
> <span data-ttu-id="f2a9f-245">The next three sections all refer to the same demo.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-245">The next three sections all refer to the same demo.</span></span>  <span data-ttu-id="f2a9f-246">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span><span class="sxs-lookup"><span data-stu-id="f2a9f-246">Run the demo yourself at [Activity Tabs Demo][ActivityTabsDemo].</span></span>  

#### <span data-ttu-id="f2a9f-247">Root activities</span><span class="sxs-lookup"><span data-stu-id="f2a9f-247">Root activities</span></span>   

<span data-ttu-id="f2a9f-248">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-248">Here is an explanation of the **root activities** concept that is mentioned in the **Call Tree** tab, **Bottom-Up** tab, and **Event Log** sections.</span></span>  

<span data-ttu-id="f2a9f-249">Root activities are those which cause the browser to do some work.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-249">Root activities are those which cause the browser to do some work.</span></span>  <span data-ttu-id="f2a9f-250">For example, when you click a page, the browser fires an `Event` activity as the root activity.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-250">For example, when you click a page, the browser fires an `Event` activity as the root activity.</span></span>  <span data-ttu-id="f2a9f-251">That `Event` might cause a handler to run, and so on.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-251">That `Event` might cause a handler to run, and so on.</span></span>  

<span data-ttu-id="f2a9f-252">In the flame chart of the **Main** section, root activities are at the top of the chart.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-252">In the flame chart of the **Main** section, root activities are at the top of the chart.</span></span>  <span data-ttu-id="f2a9f-253">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-253">In the **Call Tree** and **Event Log** tabs, root activities are the top-level items.</span></span>  

<span data-ttu-id="f2a9f-254">See [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-254">See [The Call Tree tab](#the-call-tree-tab) for an example of root activities.</span></span>  

#### <span data-ttu-id="f2a9f-255">The Call Tree tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-255">The Call Tree tab</span></span>   

<span data-ttu-id="f2a9f-256">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-256">Use the **Call Tree** tab to view which [root activities](#root-activities) cause the most work.</span></span>  

<span data-ttu-id="f2a9f-257">The **Call Tree** tab only displays activities during the selected portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-257">The **Call Tree** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="f2a9f-258">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-258">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-call-tree.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-call-tree.msft.png":::
   <span data-ttu-id="f2a9f-260">The **Call Tree** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-260">The **Call Tree** tab</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-261">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-261">In the previous figure, the top-level of items in the **Activity** column, such as `Evaluate Script` and `Parse HTML` are root activities.</span></span>  <span data-ttu-id="f2a9f-262">The nesting represents the call stack.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-262">The nesting represents the call stack.</span></span>  <span data-ttu-id="f2a9f-263">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-263">For example, in the previous figure, `Parse HTML` which caused `Evaluate Script` which caused `Compile Script` and `(anonymous)`.</span></span>  

<span data-ttu-id="f2a9f-264">**Self Time** represents the time directly spent in that activity.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-264">**Self Time** represents the time directly spent in that activity.</span></span>  <span data-ttu-id="f2a9f-265">**Total Time** represents the time spent in that activity or any of the children.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-265">**Total Time** represents the time spent in that activity or any of the children.</span></span>  

<span data-ttu-id="f2a9f-266">Click **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-266">Click **Self Time**, **Total Time**, or **Activity** to sort the table by that column.</span></span>  

<span data-ttu-id="f2a9f-267">Use the **Filter** text box to filter events by activity name.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-267">Use the **Filter** text box to filter events by activity name.</span></span>  

<span data-ttu-id="f2a9f-268">By default the **Grouping** menu is set to **No Grouping**.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-268">By default the **Grouping** menu is set to **No Grouping**.</span></span>  <span data-ttu-id="f2a9f-269">Use the **Grouping** menu to sort the activity table based on various criteria.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-269">Use the **Grouping** menu to sort the activity table based on various criteria.</span></span>  

<span data-ttu-id="f2a9f-270">Click **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-270">Click **Show Heaviest Stack** \(![Show Heaviest Stack][ImageShowHeaviestStackIcon]\) to reveal another table to the right of the **Activity** table.</span></span>  <span data-ttu-id="f2a9f-271">Click on an activity to populate the **Heaviest Stack** table.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-271">Click on an activity to populate the **Heaviest Stack** table.</span></span>  <span data-ttu-id="f2a9f-272">The **Heaviest Stack** table shows you which children of the selected activity took the longest time to run.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-272">The **Heaviest Stack** table shows you which children of the selected activity took the longest time to run.</span></span>  

#### <span data-ttu-id="f2a9f-273">The Bottom-Up tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-273">The Bottom-Up tab</span></span>   

<span data-ttu-id="f2a9f-274">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-274">Use the **Bottom-Up** tab to view which activities directly took up the most time in aggregate.</span></span>  

<span data-ttu-id="f2a9f-275">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-275">The **Bottom-Up** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="f2a9f-276">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-276">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-bottoms-up.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-bottoms-up.msft.png":::
   <span data-ttu-id="f2a9f-278">The **Bottom-Up** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-278">The **Bottom-Up** tab</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-279">In the **Main** section flame chart of the previous figure, see that almost practically all of the time was spent running `Parse HTML`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-279">In the **Main** section flame chart of the previous figure, see that almost practically all of the time was spent running `Parse HTML`.</span></span>  <span data-ttu-id="f2a9f-280">The top activity in the **Bottom-Up** tab of the previous figure is `Parse HTML`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-280">The top activity in the **Bottom-Up** tab of the previous figure is `Parse HTML`.</span></span>  <!--In the flame chart of the previous figure, the yellow below the calls to `wait` are actually thousands of `Minor GC` calls.  -->  <span data-ttu-id="f2a9f-281">See in the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-281">See in the **Bottom-Up** tab, the next most expensive activity is `Layout`.</span></span>  

<span data-ttu-id="f2a9f-282">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-282">The **Self Time** column represents the aggregated time spent directly in that activity, across all of the occurrences.</span></span>  

<span data-ttu-id="f2a9f-283">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-283">The **Total Time** column represents aggregated time spent in that activity or any of the children.</span></span>  

#### <span data-ttu-id="f2a9f-284">The Event Log tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-284">The Event Log tab</span></span>   

<span data-ttu-id="f2a9f-285">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-285">Use the **Event Log** tab to view activities in the order in which they occurred during the recording.</span></span>  

<span data-ttu-id="f2a9f-286">The **Event Log** tab only displays activities during the selected portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-286">The **Event Log** tab only displays activities during the selected portion of the recording.</span></span>  <span data-ttu-id="f2a9f-287">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-287">See [Select a portion of a recording](#select-a-portion-of-a-recording) to learn how to select portions.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-event-log.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-event-log.msft.png":::
   <span data-ttu-id="f2a9f-289">The **Event Log** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-289">The **Event Log** tab</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-290">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-290">The **Start Time** column represents the point at which that activity started, relative to the start of the recording.</span></span>  <span data-ttu-id="f2a9f-291">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-291">For example, the start time of `175.7 ms` for the selected item in the previous figure means that activity started 175.7 ms after the recording started.</span></span>  

<span data-ttu-id="f2a9f-292">The **Self Time** column represents the time spent directly in that activity.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-292">The **Self Time** column represents the time spent directly in that activity.</span></span>  

<span data-ttu-id="f2a9f-293">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-293">The **Total Time** columns represents time spent directly in that activity or in any of the children.</span></span>  

<span data-ttu-id="f2a9f-294">Click **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-294">Click **Start Time**, **Self Time**, or **Total Time** to sort the table by that column.</span></span>

<span data-ttu-id="f2a9f-295">Use the **Filter** text box to filter activities by name.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-295">Use the **Filter** text box to filter activities by name.</span></span>  

<span data-ttu-id="f2a9f-296">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-296">Use the **Duration** menu to filter out any activities that took less than 1 ms or 15 ms.</span></span>  <span data-ttu-id="f2a9f-297">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-297">By default the **Duration** menu is set to **All**, meaning all activities are shown.</span></span>  

<span data-ttu-id="f2a9f-298">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-298">Disable the **Loading**, **Scripting**, **Rendering**, or **Painting** checkboxes to filter out all activities from those categories.</span></span>  

### <span data-ttu-id="f2a9f-299">View GPU activity</span><span class="sxs-lookup"><span data-stu-id="f2a9f-299">View GPU activity</span></span>   

<span data-ttu-id="f2a9f-300">View GPU activity in the **GPU** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-300">View GPU activity in the **GPU** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-gpu-zoomed.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-gpu-zoomed.msft.png":::
   <span data-ttu-id="f2a9f-302">The **GPU** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-302">The **GPU** section</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-303">View raster activity</span><span class="sxs-lookup"><span data-stu-id="f2a9f-303">View raster activity</span></span>   

<span data-ttu-id="f2a9f-304">View raster activity in the **Raster** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-304">View raster activity in the **Raster** section.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-raster.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-raster.msft.png":::
   <span data-ttu-id="f2a9f-306">The **Raster** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-306">The **Raster** section</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-307">View interactions</span><span class="sxs-lookup"><span data-stu-id="f2a9f-307">View interactions</span></span>   

<span data-ttu-id="f2a9f-308">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-308">Use the **Interactions** section to find and analyze user interactions that happened during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-interactions-animation.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-interactions-animation.msft.png":::
   <span data-ttu-id="f2a9f-310">The **Interactions** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-310">The **Interactions** section</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-311">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-311">A red line at the bottom of an interaction represents time spent waiting for the main thread.</span></span>  

<span data-ttu-id="f2a9f-312">Click an interaction to view more information about it in the **Summary** tab.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-312">Click an interaction to view more information about it in the **Summary** tab.</span></span>  

### <span data-ttu-id="f2a9f-313">Analyze frames per second (FPS)</span><span class="sxs-lookup"><span data-stu-id="f2a9f-313">Analyze frames per second (FPS)</span></span>   

<span data-ttu-id="f2a9f-314">DevTools provides numerous ways to analyze frames per second:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-314">DevTools provides numerous ways to analyze frames per second:</span></span>  

*   <span data-ttu-id="f2a9f-315">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-315">Use [the FPS chart](#the-fps-chart) to get an overview of FPS over the duration of the recording.</span></span>  
*   <span data-ttu-id="f2a9f-316">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-316">Use [the Frames section](#the-frames-section) to view how long a particular frame took.</span></span>  
*   <span data-ttu-id="f2a9f-317">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-317">Use the **FPS meter** for a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="f2a9f-318">See [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-318">See [View frames per second in realtime with the FPS meter](#view-frames-per-second-in-realtime-with-the-fps-meter).</span></span>  
    
#### <span data-ttu-id="f2a9f-319">The FPS chart</span><span class="sxs-lookup"><span data-stu-id="f2a9f-319">The FPS chart</span></span>   

<span data-ttu-id="f2a9f-320">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-320">The **FPS** chart provides an overview of the frame rate across the duration of a recording.</span></span>  <span data-ttu-id="f2a9f-321">In general, the higher the green bar, the better the frame rate.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-321">In general, the higher the green bar, the better the frame rate.</span></span>  

<span data-ttu-id="f2a9f-322">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-322">A red bar above the **FPS** chart is a warning that the frame rate dropped so low that it probably harmed the user's experience.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-fps-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-fps-highlight.msft.png":::
   <span data-ttu-id="f2a9f-324">The **FPS** chart</span><span class="sxs-lookup"><span data-stu-id="f2a9f-324">The **FPS** chart</span></span>  
:::image-end:::  

#### <span data-ttu-id="f2a9f-325">The Frames section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-325">The Frames section</span></span>   

<span data-ttu-id="f2a9f-326">The **Frames** section tells you exactly how long a particular frame took.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-326">The **Frames** section tells you exactly how long a particular frame took.</span></span>  

<span data-ttu-id="f2a9f-327">Hover over a frame to view a tooltip with more information about it.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-327">Hover over a frame to view a tooltip with more information about it.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-hover.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-frames-hover.msft.png":::
   <span data-ttu-id="f2a9f-329">Hover over a frame</span><span class="sxs-lookup"><span data-stu-id="f2a9f-329">Hover over a frame</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-330">Click on a frame to view even more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-330">Click on a frame to view even more information about the frame in the **Summary** tab.  DevTools outlines the selected frame in blue.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-summary.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-frames-summary.msft.png":::
   <span data-ttu-id="f2a9f-332">View a frame in the **Summary** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-332">View a frame in the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-333">View network requests</span><span class="sxs-lookup"><span data-stu-id="f2a9f-333">View network requests</span></span>   

<span data-ttu-id="f2a9f-334">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-334">Expand the **Network** section to view a waterfall of network requests that occurred during the recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-network.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-network.msft.png":::
   <span data-ttu-id="f2a9f-336">The **Network** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-336">The **Network** section</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-337">Requests are color-coded as follows:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-337">Requests are color-coded as follows:</span></span>  

*   <span data-ttu-id="f2a9f-338">HTML: Blue</span><span class="sxs-lookup"><span data-stu-id="f2a9f-338">HTML: Blue</span></span>  
*   <span data-ttu-id="f2a9f-339">CSS: Purple</span><span class="sxs-lookup"><span data-stu-id="f2a9f-339">CSS: Purple</span></span>  
*   <span data-ttu-id="f2a9f-340">JS: Yellow</span><span class="sxs-lookup"><span data-stu-id="f2a9f-340">JS: Yellow</span></span>  
*   <span data-ttu-id="f2a9f-341">Images: Green</span><span class="sxs-lookup"><span data-stu-id="f2a9f-341">Images: Green</span></span>  
    
<span data-ttu-id="f2a9f-342">Click on a request to view more information about it in the **Summary** tab.  For example, in the previous figure, the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-342">Click on a request to view more information about it in the **Summary** tab.  For example, in the previous figure, the **Summary** tab is displaying more information about the blue request that is selected in the **Network** section.</span></span>  

<span data-ttu-id="f2a9f-343">A darker-blue square in the top-left of a request means it is a higher-priority request.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-343">A darker-blue square in the top-left of a request means it is a higher-priority request.</span></span>  <span data-ttu-id="f2a9f-344">A lighter-blue square means lower-priority.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-344">A lighter-blue square means lower-priority.</span></span>  <span data-ttu-id="f2a9f-345">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-345">For example, in the previous figure, the blue, selected request is higher-priority, and the green one below it is lower-priority.</span></span>  

<span data-ttu-id="f2a9f-346">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-346">In the 1st of the following figures, the request for `www.bing.com` is represented by a line on the left, a bar in the middle with a dark portion and a light portion, and a line on the right.</span></span>  <span data-ttu-id="f2a9f-347">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-347">In the 2nd of the following figures shows the corresponding representation of the same request in the **Timing** tab of the **Network** panel.</span></span>  <span data-ttu-id="f2a9f-348">Here is how these two representations map to each other:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-348">Here is how these two representations map to each other:</span></span>

*   <span data-ttu-id="f2a9f-349">The left line is everything up to the `Connection Start` group of events, inclusive.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-349">The left line is everything up to the `Connection Start` group of events, inclusive.</span></span>  <span data-ttu-id="f2a9f-350">In other words, it is everything before `Request Sent`, exclusive.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-350">In other words, it is everything before `Request Sent`, exclusive.</span></span>  
*   <span data-ttu-id="f2a9f-351">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-351">The light portion of the bar is `Request Sent` and `Waiting (TTFB)`.</span></span>  
*   <span data-ttu-id="f2a9f-352">The dark portion of the bar is `Content Download`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-352">The dark portion of the bar is `Content Download`.</span></span>  
*   <span data-ttu-id="f2a9f-353">The right line is essentially time spent waiting for the main thread.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-353">The right line is essentially time spent waiting for the main thread.</span></span>  <span data-ttu-id="f2a9f-354">This is not represented in the **Timing** tab.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-354">This is not represented in the **Timing** tab.</span></span>  
    
:::row:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-performance-network.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-bing-performance-network.msft.png":::
         <span data-ttu-id="f2a9f-356">The line-bar representation of the `www.bing.com` request</span><span class="sxs-lookup"><span data-stu-id="f2a9f-356">The line-bar representation of the `www.bing.com` request</span></span>  
      :::image-end:::  
   :::column-end:::
   :::column span="":::
      :::image type="complex" source="../media/evaluate-performance-bing-network-timing.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-bing-network-timing.msft.png":::
         <span data-ttu-id="f2a9f-358">The **Network** section</span><span class="sxs-lookup"><span data-stu-id="f2a9f-358">The **Network** section</span></span>  
<span data-ttu-id="f2a9f-359">:      ::image-end:::</span><span class="sxs-lookup"><span data-stu-id="f2a9f-359">:      ::image-end:::</span></span>  
   :::column-end:::
:::row-end:::

### <span data-ttu-id="f2a9f-360">View memory metrics</span><span class="sxs-lookup"><span data-stu-id="f2a9f-360">View memory metrics</span></span>   

<span data-ttu-id="f2a9f-361">Enable the **Memory** checkbox to view memory metrics from the last recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-361">Enable the **Memory** checkbox to view memory metrics from the last recording.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-highlight.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-memory-highlight.msft.png":::
   <span data-ttu-id="f2a9f-363">The **Memory** checkbox</span><span class="sxs-lookup"><span data-stu-id="f2a9f-363">The **Memory** checkbox</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-364">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-364">DevTools displays a new **Memory** chart, above the **Summary** tab.  There is also a new chart below the **NET** chart, called **HEAP**.</span></span>  <span data-ttu-id="f2a9f-365">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-365">The **HEAP** chart provides the same information as the **JS Heap** line in the **Memory** chart.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-memory-chart.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-memory-chart.msft.png":::
   <span data-ttu-id="f2a9f-367">Memory metrics</span><span class="sxs-lookup"><span data-stu-id="f2a9f-367">Memory metrics</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-368">The colored lines on the chart map to the colored checkboxes above the chart.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-368">The colored lines on the chart map to the colored checkboxes above the chart.</span></span>  
<span data-ttu-id="f2a9f-369">Disable a checkbox to hide that category from the chart.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-369">Disable a checkbox to hide that category from the chart.</span></span>  

<span data-ttu-id="f2a9f-370">The chart only displays the region of the recording that is currently selected.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-370">The chart only displays the region of the recording that is currently selected.</span></span>  <span data-ttu-id="f2a9f-371">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-371">For example, in the previous figure, the **Memory** chart is only showing memory usage from around the 400 ms mark to the 1750 ms mark.</span></span>  

### <span data-ttu-id="f2a9f-372">View the duration of a portion of a recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-372">View the duration of a portion of a recording</span></span>   

<span data-ttu-id="f2a9f-373">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-373">When analyzing a section like **Network** or **Main**, sometimes you need a more precise estimate of how long certain events took.</span></span>  <span data-ttu-id="f2a9f-374">Hold `Shift`, click and hold, and drag left or right to select a portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-374">Hold `Shift`, click and hold, and drag left or right to select a portion of the recording.</span></span>  <span data-ttu-id="f2a9f-375">At the bottom of your selection, DevTools shows how long that portion took.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-375">At the bottom of your selection, DevTools shows how long that portion took.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-main-duration.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-main-duration.msft.png":::
   <span data-ttu-id="f2a9f-377">View the duration of a portion of a recording</span><span class="sxs-lookup"><span data-stu-id="f2a9f-377">View the duration of a portion of a recording</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-378">View a screenshot</span><span class="sxs-lookup"><span data-stu-id="f2a9f-378">View a screenshot</span></span>   

<span data-ttu-id="f2a9f-379">See [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to enable screenshots.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-379">See [Capture screenshots while recording](#capture-screenshots-while-recording) to learn how to enable screenshots.</span></span>  

<span data-ttu-id="f2a9f-380">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-380">Hover over the **Overview** to view a screenshot of how the page looked during that moment of the recording.</span></span>  <span data-ttu-id="f2a9f-381">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-381">The **Overview** is the section that contains the **CPU**, **FPS**, and **NET** charts.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-screenshots-hover.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-screenshots-hover.msft.png":::
   <span data-ttu-id="f2a9f-383">View a screenshot</span><span class="sxs-lookup"><span data-stu-id="f2a9f-383">View a screenshot</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-384">You may also view screenshots by clicking a frame in the **Frames** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-384">You may also view screenshots by clicking a frame in the **Frames** section.</span></span>  <span data-ttu-id="f2a9f-385">DevTools displays a small version of the screenshot in the **Summary** tab.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-385">DevTools displays a small version of the screenshot in the **Summary** tab.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-summary-preview.msft.png":::
   <span data-ttu-id="f2a9f-387">View a screenshot in the **Summary** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-387">View a screenshot in the **Summary** tab</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-388">Click the thumbnail in the **Summary** tab to zoom in on the screenshot.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-388">Click the thumbnail in the **Summary** tab to zoom in on the screenshot.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-summary-preview-select.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-summary-preview-select.msft.png":::
   <span data-ttu-id="f2a9f-390">Zoom into a screenshot from the **Summary** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-390">Zoom into a screenshot from the **Summary** tab</span></span>  
:::image-end:::  

### <span data-ttu-id="f2a9f-391">View layers information</span><span class="sxs-lookup"><span data-stu-id="f2a9f-391">View layers information</span></span>   

<span data-ttu-id="f2a9f-392">To view advanced layers information about a frame:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-392">To view advanced layers information about a frame:</span></span>  

1.  <span data-ttu-id="f2a9f-393">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-393">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="f2a9f-394">Select a frame in the **Frames** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-394">Select a frame in the **Frames** section.</span></span>  <span data-ttu-id="f2a9f-395">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-395">DevTools displays information about the layers in the new **Layers** tab, next to the **Event Log** tab.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-layers-all.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-layers-all.msft.png":::
       <span data-ttu-id="f2a9f-397">The **Layers** pane</span><span class="sxs-lookup"><span data-stu-id="f2a9f-397">The **Layers** pane</span></span>  
    :::image-end:::  
    
<span data-ttu-id="f2a9f-398">Hover over a layer to highlight it in the diagram.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-398">Hover over a layer to highlight it in the diagram.</span></span>  

:::image type="complex" source="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-performance-frames-document-nav-bar-highlighted.msft.png":::
   <span data-ttu-id="f2a9f-400">Highlight a layer</span><span class="sxs-lookup"><span data-stu-id="f2a9f-400">Highlight a layer</span></span>  
:::image-end:::  

<span data-ttu-id="f2a9f-401">To move the diagram:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-401">To move the diagram:</span></span>  

*   <span data-ttu-id="f2a9f-402">Click **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-402">Click **Pan Mode** \(![Pan Mode][ImagePanModeIcon]\) to move along the X and Y axes.</span></span>  
*   <span data-ttu-id="f2a9f-403">Click **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-403">Click **Rotate Mode** \(![Rotate Mode][ImageRotateModeIcon]\) to rotate along the Z axis.</span></span>  
*   <span data-ttu-id="f2a9f-404">Click **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-404">Click **Reset Transform** \(![Reset Transform][ImageResetTransformIcon]\) to reset the diagram to the original position.</span></span>  
    
### <span data-ttu-id="f2a9f-405">View paint profiler</span><span class="sxs-lookup"><span data-stu-id="f2a9f-405">View paint profiler</span></span>   

<span data-ttu-id="f2a9f-406">To view advanced information about a paint event:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-406">To view advanced information about a paint event:</span></span>  

1.  <span data-ttu-id="f2a9f-407">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-407">[Enable advanced paint instrumentation](#enable-advanced-paint-instrumentation).</span></span>  
1.  <span data-ttu-id="f2a9f-408">Select a **Paint** event in the **Main** section.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-408">Select a **Paint** event in the **Main** section.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-paint-profiler.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-paint-profiler.msft.png":::
       <span data-ttu-id="f2a9f-410">The **Paint Profiler** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-410">The **Paint Profiler** tab</span></span>  
    :::image-end:::  
    
## <span data-ttu-id="f2a9f-411">Analyze rendering performance with the Rendering tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-411">Analyze rendering performance with the Rendering tab</span></span>   

<span data-ttu-id="f2a9f-412">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-412">Use the features of the **Rendering** tab to help visualize the rendering performance of your page.</span></span>  

<span data-ttu-id="f2a9f-413">To open the **Rendering** tab:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-413">To open the **Rendering** tab:</span></span>  

1.  <span data-ttu-id="f2a9f-414">[Open the Command Menu][DevToolsCommandMenu].</span><span class="sxs-lookup"><span data-stu-id="f2a9f-414">[Open the Command Menu][DevToolsCommandMenu].</span></span>  
1.  <span data-ttu-id="f2a9f-415">Start typing `Rendering` and select `Show Rendering`.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-415">Start typing `Rendering` and select `Show Rendering`.</span></span>  <span data-ttu-id="f2a9f-416">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-416">DevTools displays the **Rendering** tab at the bottom of your DevTools window.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-console-drawer-rendering.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-console-drawer-rendering.msft.png":::
       <span data-ttu-id="f2a9f-418">The **Rendering** tab</span><span class="sxs-lookup"><span data-stu-id="f2a9f-418">The **Rendering** tab</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f2a9f-419">View frames per second in realtime with the FPS meter</span><span class="sxs-lookup"><span data-stu-id="f2a9f-419">View frames per second in realtime with the FPS meter</span></span>   

<span data-ttu-id="f2a9f-420">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-420">The **FPS meter** is an overlay that appears in the top-right corner of your viewport.</span></span>  <span data-ttu-id="f2a9f-421">It provides a realtime estimate of FPS as the page runs.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-421">It provides a realtime estimate of FPS as the page runs.</span></span>  <span data-ttu-id="f2a9f-422">To open the **FPS meter**:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-422">To open the **FPS meter**:</span></span>  

1.  <span data-ttu-id="f2a9f-423">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-423">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="f2a9f-424">Enable the **FPS Meter** checkbox.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-424">Enable the **FPS Meter** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-jank-console-rendering-frame-rate.msft.png":::
       <span data-ttu-id="f2a9f-426">The **FPS meter**</span><span class="sxs-lookup"><span data-stu-id="f2a9f-426">The **FPS meter**</span></span>  
    :::image-end:::  
    
### <span data-ttu-id="f2a9f-427">View painting events in realtime with Paint Flashing</span><span class="sxs-lookup"><span data-stu-id="f2a9f-427">View painting events in realtime with Paint Flashing</span></span>   

<span data-ttu-id="f2a9f-428">Use Paint Flashing to get a realtime view of all paint events on the page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-428">Use Paint Flashing to get a realtime view of all paint events on the page.</span></span>  <span data-ttu-id="f2a9f-429">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-429">Whenever a part of the page gets re-painted, DevTools outlines that section in green.</span></span>  

<span data-ttu-id="f2a9f-430">To enable Paint Flashing:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-430">To enable Paint Flashing:</span></span>  

1.  <span data-ttu-id="f2a9f-431">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-431">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="f2a9f-432">Enable the **Paint Flashing** checkbox.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-432">Enable the **Paint Flashing** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-jank-console-rendering-paint-flashing.msft.png":::
       **<span data-ttu-id="f2a9f-434">Paint Flashing</span><span class="sxs-lookup"><span data-stu-id="f2a9f-434">Paint Flashing</span></span>**  
    :::image-end:::  
    
### <span data-ttu-id="f2a9f-435">View an overlay of layers with Layer Borders</span><span class="sxs-lookup"><span data-stu-id="f2a9f-435">View an overlay of layers with Layer Borders</span></span>   

<span data-ttu-id="f2a9f-436">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-436">Use **Layer Borders** to view an overlay of layer borders and tiles on top of the page.</span></span>  

<span data-ttu-id="f2a9f-437">To enable Layer Borders:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-437">To enable Layer Borders:</span></span>  

1.  <span data-ttu-id="f2a9f-438">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-438">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="f2a9f-439">Enable the **Layer Borders** checkbox.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-439">Enable the **Layer Borders** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-devtools-console-rendering-layer-borders.msft.png":::
       **<span data-ttu-id="f2a9f-441">Layer Borders</span><span class="sxs-lookup"><span data-stu-id="f2a9f-441">Layer Borders</span></span>**  
    :::image-end:::  
    
<span data-ttu-id="f2a9f-442">See the comments in [`debug_colors.cc`][ChromiumDebugColors] for an explanation of the color-codings.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-442">See the comments in [`debug_colors.cc`][ChromiumDebugColors] for an explanation of the color-codings.</span></span>  

### <span data-ttu-id="f2a9f-443">Find scroll performance issues in realtime</span><span class="sxs-lookup"><span data-stu-id="f2a9f-443">Find scroll performance issues in realtime</span></span>   

<span data-ttu-id="f2a9f-444">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-444">Use Scrolling Performance Issues to identify elements of the page that have event listeners related to scrolling that may harm the performance of the page.</span></span>  
<span data-ttu-id="f2a9f-445">DevTools outlines the potentially-problematic elements in teal.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-445">DevTools outlines the potentially-problematic elements in teal.</span></span>  

<span data-ttu-id="f2a9f-446">To view scroll performance issues:</span><span class="sxs-lookup"><span data-stu-id="f2a9f-446">To view scroll performance issues:</span></span>  

1.  <span data-ttu-id="f2a9f-447">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span><span class="sxs-lookup"><span data-stu-id="f2a9f-447">Open the **Rendering** tab.  See [Analyze rendering performance with the Rendering tab](#analyze-rendering-performance-with-the-rendering-tab).</span></span>  
1.  <span data-ttu-id="f2a9f-448">Enable the **Scrolling Performance Issues** checkbox.</span><span class="sxs-lookup"><span data-stu-id="f2a9f-448">Enable the **Scrolling Performance Issues** checkbox.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png" alt-text="Record" lightbox="../media/evaluate-performance-bing-console-drawer-rendering-scrolling-performance-issues.msft.png":::
       <span data-ttu-id="f2a9f-450">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span><span class="sxs-lookup"><span data-stu-id="f2a9f-450">**Scrolling Performance Issues** indicates that non-layer viewport-constrained objects may harm scroll performance</span></span>  
    :::image-end:::  
    
<!--  
<!--    


-->  

<!-- image links -->  

[ImageCaptureSettingsIcon]: ../media/capture-settings-icon.msft.png  
[ImageClearRecordingIcon]: ../media/clear-recording-icon.msft.png  
[ImageCollectGarbageIcon]: ../media/collect-garbage-icon.msft.png  
[ImageNextIcon]: ../media/next-icon.msft.png  
[ImagePanModeIcon]: ../media/pan-mode-icon.msft.png  
[ImagePreviousIcon]: ../media/previous-icon.msft.png  
[ImageRecordIcon]: ../media/record-icon.msft.png
[ImageRefreshPageIcon]: ../media/refresh-page-icon.msft.png  
[ImageResetTransformIcon]: ../media/reset-transform-icon.msft.png  
[ImageRotateModeIcon]: ../media/rotate-mode-icon.msft.png  
[ImageSearchCaseIcon]: ../media/search-case-icon.msft.png  
[ImageSearchRegexIcon]: ../media/search-regex-icon.msft.png  
[ImageShowHeaviestStackIcon]: ../media/show-heaviest-stack-icon.msft.png  

<!-- links -->  

[MicrosoftEdgeDevTools]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) Developer tools | Microsoft Docs"  
[DevToolsCommandMenu]: ../command-menu/index.md#open-the-command-menu "Open the Command Menu - Run commands with the Microsoft Edge DevTools Command Menu | Microsoft Docs"  
[DevtoolsEvaluatePerformanceGettingStarted]: ./index.md "Get started with analyzing runtime performance | Microsoft Docs"  

[ActivityTabsDemo]: https://microsoft-edge-chromium-devtools.glitch.me/perf/activitytabs.html "Activity Tabs Demo | glitch"  

[ChromiumDebugColors]: https://cs.chromium.org/chromium/src/cc/debug/debug_colors.cc "debug_colors.cc - Code Search"  

> [!NOTE]
> <span data-ttu-id="f2a9f-456">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f2a9f-456">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f2a9f-457">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="f2a9f-457">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/reference) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f2a9f-459">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f2a9f-459">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
