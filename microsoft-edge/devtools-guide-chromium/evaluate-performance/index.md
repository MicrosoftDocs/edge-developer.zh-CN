---
description: Learn how to evaluate runtime performance in Microsoft Edge DevTools.
title: Get Started With Analyzing Runtime Performance
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 65351f3846ed76ef8a27dbff2cfb08c497282d15
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992944"
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

# <span data-ttu-id="d3490-104">Get started with analyzing Runtime performance</span><span class="sxs-lookup"><span data-stu-id="d3490-104">Get started with analyzing Runtime performance</span></span>  

> [!NOTE]
> <span data-ttu-id="d3490-105">To learn how to make your pages load faster, see [Optimize Website Speed][DevtoolsSpeedGetStarted].</span><span class="sxs-lookup"><span data-stu-id="d3490-105">To learn how to make your pages load faster, see [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

<span data-ttu-id="d3490-106">Runtime performance is how your page performs when it is running, as opposed to loading.</span><span class="sxs-lookup"><span data-stu-id="d3490-106">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="d3490-107">The following tutorial article teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span><span class="sxs-lookup"><span data-stu-id="d3490-107">The following tutorial article teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="d3490-108">在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。</span><span class="sxs-lookup"><span data-stu-id="d3490-108">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <span data-ttu-id="d3490-109">Get started</span><span class="sxs-lookup"><span data-stu-id="d3490-109">Get started</span></span>  

<span data-ttu-id="d3490-110">In the following tutorial, you open DevTools on a live page and use the **Performance** panel to find a performance bottleneck on the page.</span><span class="sxs-lookup"><span data-stu-id="d3490-110">In the following tutorial, you open DevTools on a live page and use the **Performance** panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="d3490-111">Open Microsoft Edge in **InPrivate Mode**.</span><span class="sxs-lookup"><span data-stu-id="d3490-111">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="d3490-112">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span><span class="sxs-lookup"><span data-stu-id="d3490-112">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="d3490-113">For example, if you have a lot of extensions installed, the extensions may create noise in your performance measurements.</span><span class="sxs-lookup"><span data-stu-id="d3490-113">For example, if you have a lot of extensions installed, the extensions may create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="d3490-114">Load the following page in your InPrivate window.</span><span class="sxs-lookup"><span data-stu-id="d3490-114">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="d3490-115">The page is the demo that you are going to profile.</span><span class="sxs-lookup"><span data-stu-id="d3490-115">The page is the demo that you are going to profile.</span></span>  <span data-ttu-id="d3490-116">The page shows a bunch of little icons moving up and down.</span><span class="sxs-lookup"><span data-stu-id="d3490-116">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  <span data-ttu-id="d3490-117">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span><span class="sxs-lookup"><span data-stu-id="d3490-117">Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       <span data-ttu-id="d3490-119">The demo on the left, and DevTools on the right</span><span class="sxs-lookup"><span data-stu-id="d3490-119">The demo on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-120">For the rest of the figures, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] to better focus on the contents.</span><span class="sxs-lookup"><span data-stu-id="d3490-120">For the rest of the figures, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] to better focus on the contents.</span></span>  
    
### <span data-ttu-id="d3490-121">Simulate a mobile CPU</span><span class="sxs-lookup"><span data-stu-id="d3490-121">Simulate a mobile CPU</span></span>  

<span data-ttu-id="d3490-122">与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。</span><span class="sxs-lookup"><span data-stu-id="d3490-122">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="d3490-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span><span class="sxs-lookup"><span data-stu-id="d3490-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="d3490-124">In DevTools, choose the **Performance** tab.</span><span class="sxs-lookup"><span data-stu-id="d3490-124">In DevTools, choose the **Performance** tab.</span></span>  
1.  <span data-ttu-id="d3490-125">Make sure that the **Screenshots** checkbox is enabled.</span><span class="sxs-lookup"><span data-stu-id="d3490-125">Make sure that the **Screenshots** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="d3490-126">Choose **Capture Settings** \(![Capture Settings][ImageCaptureSettingsIcon]\).</span><span class="sxs-lookup"><span data-stu-id="d3490-126">Choose **Capture Settings** \(![Capture Settings][ImageCaptureSettingsIcon]\).</span></span>  <span data-ttu-id="d3490-127">DevTools reveals settings related to how it captures performance metrics.</span><span class="sxs-lookup"><span data-stu-id="d3490-127">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="d3490-128">对于 "**CPU**"，选择 **4x 减速**。</span><span class="sxs-lookup"><span data-stu-id="d3490-128">For **CPU**, select **4x slowdown**.</span></span>  <span data-ttu-id="d3490-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span><span class="sxs-lookup"><span data-stu-id="d3490-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       <span data-ttu-id="d3490-131">CPU throttle</span><span class="sxs-lookup"><span data-stu-id="d3490-131">CPU throttle</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-132">When testing other pages; if you want to ensure that each page works well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span><span class="sxs-lookup"><span data-stu-id="d3490-132">When testing other pages; if you want to ensure that each page works well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="d3490-133">The demo does not work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span><span class="sxs-lookup"><span data-stu-id="d3490-133">The demo does not work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <span data-ttu-id="d3490-134">Set up the demo</span><span class="sxs-lookup"><span data-stu-id="d3490-134">Set up the demo</span></span>  

<span data-ttu-id="d3490-135">It is hard to create a runtime performance demo that works consistently for all readers of the website.</span><span class="sxs-lookup"><span data-stu-id="d3490-135">It is hard to create a runtime performance demo that works consistently for all readers of the website.</span></span>  <span data-ttu-id="d3490-136">The following section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions, regardless of your particular set up.</span><span class="sxs-lookup"><span data-stu-id="d3490-136">The following section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions, regardless of your particular set up.</span></span>

1.  <span data-ttu-id="d3490-137">Choose the **Add 10** button until the blue icons move noticeably slower than before.</span><span class="sxs-lookup"><span data-stu-id="d3490-137">Choose the **Add 10** button until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="d3490-138">On a high-end machine, you may to choose it about 20 times.</span><span class="sxs-lookup"><span data-stu-id="d3490-138">On a high-end machine, you may to choose it about 20 times.</span></span>  
1.  <span data-ttu-id="d3490-139">Choose **Optimize**.</span><span class="sxs-lookup"><span data-stu-id="d3490-139">Choose **Optimize**.</span></span>  <span data-ttu-id="d3490-140">The blue icons should move faster and more smoothly.</span><span class="sxs-lookup"><span data-stu-id="d3490-140">The blue icons should move faster and more smoothly.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-141">To better display a difference between the optimized and un-optimized versions, choose the **Subtract 10** button a few times and try again.</span><span class="sxs-lookup"><span data-stu-id="d3490-141">To better display a difference between the optimized and un-optimized versions, choose the **Subtract 10** button a few times and try again.</span></span>  
    > <span data-ttu-id="d3490-142">If you add too many blue icons, you may max out the CPU and then you may not observe a major difference in the results for the two versions.</span><span class="sxs-lookup"><span data-stu-id="d3490-142">If you add too many blue icons, you may max out the CPU and then you may not observe a major difference in the results for the two versions.</span></span>  
    
1.  <span data-ttu-id="d3490-143">Choose **Un-Optimize**.</span><span class="sxs-lookup"><span data-stu-id="d3490-143">Choose **Un-Optimize**.</span></span>  <span data-ttu-id="d3490-144">The blue icons move slower and with more sluggishness again.</span><span class="sxs-lookup"><span data-stu-id="d3490-144">The blue icons move slower and with more sluggishness again.</span></span>  
    
### <span data-ttu-id="d3490-145">Record runtime performance</span><span class="sxs-lookup"><span data-stu-id="d3490-145">Record runtime performance</span></span>  

<span data-ttu-id="d3490-146">运行优化版本的页面时，蓝色图标会移动得更快。</span><span class="sxs-lookup"><span data-stu-id="d3490-146">When you ran the optimized version of the page, the blue icons move faster.</span></span>  <span data-ttu-id="d3490-147">为什么？</span><span class="sxs-lookup"><span data-stu-id="d3490-147">Why is that?</span></span>  <span data-ttu-id="d3490-148">两种版本都应该在相同的时间内将图标移动相同的空间。</span><span class="sxs-lookup"><span data-stu-id="d3490-148">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="d3490-149">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span><span class="sxs-lookup"><span data-stu-id="d3490-149">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="d3490-150">In DevTools, choose **Record** \(![Record][ImageRecordIcon]\).</span><span class="sxs-lookup"><span data-stu-id="d3490-150">In DevTools, choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  <span data-ttu-id="d3490-151">DevTools captures performance metrics as the page runs.</span><span class="sxs-lookup"><span data-stu-id="d3490-151">DevTools captures performance metrics as the page runs.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       <span data-ttu-id="d3490-153">Profile the page</span><span class="sxs-lookup"><span data-stu-id="d3490-153">Profile the page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3490-154">Wait a few seconds.</span><span class="sxs-lookup"><span data-stu-id="d3490-154">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="d3490-155">Choose **Stop**.</span><span class="sxs-lookup"><span data-stu-id="d3490-155">Choose **Stop**.</span></span>  <span data-ttu-id="d3490-156">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span><span class="sxs-lookup"><span data-stu-id="d3490-156">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       <span data-ttu-id="d3490-158">配置文件的结果</span><span class="sxs-lookup"><span data-stu-id="d3490-158">The results of the profile</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d3490-159">Wow, that is an overwhelming amount of data.</span><span class="sxs-lookup"><span data-stu-id="d3490-159">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="d3490-160">do not worry, soon the process makes more sense.</span><span class="sxs-lookup"><span data-stu-id="d3490-160">do not worry, soon the process makes more sense.</span></span>  

## <span data-ttu-id="d3490-161">Analyze the results</span><span class="sxs-lookup"><span data-stu-id="d3490-161">Analyze the results</span></span>  

<span data-ttu-id="d3490-162">After you record the performance of the page, measure the quality of the performance of the page and find the any causes.</span><span class="sxs-lookup"><span data-stu-id="d3490-162">After you record the performance of the page, measure the quality of the performance of the page and find the any causes.</span></span>  

### <span data-ttu-id="d3490-163">Analyze frames per second</span><span class="sxs-lookup"><span data-stu-id="d3490-163">Analyze frames per second</span></span>  

<span data-ttu-id="d3490-164">用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。</span><span class="sxs-lookup"><span data-stu-id="d3490-164">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="d3490-165">当动画以 60 FPS运行时，用户会觉得很享受。</span><span class="sxs-lookup"><span data-stu-id="d3490-165">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="d3490-166">查看 **FPS** 图表。</span><span class="sxs-lookup"><span data-stu-id="d3490-166">Look at the **FPS** chart.</span></span>  <span data-ttu-id="d3490-167">每当你在\*\* FPS \*\*上方看到红色条时，表示帧速率下降得太低，以至于可能损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="d3490-167">Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="d3490-168">In general, the higher the green bar, the higher the FPS.</span><span class="sxs-lookup"><span data-stu-id="d3490-168">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       <span data-ttu-id="d3490-170">The **FPS** chart</span><span class="sxs-lookup"><span data-stu-id="d3490-170">The **FPS** chart</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3490-171">Below the **FPS** chart you see the **CPU** chart.</span><span class="sxs-lookup"><span data-stu-id="d3490-171">Below the **FPS** chart you see the **CPU** chart.</span></span>  <span data-ttu-id="d3490-172">**CPU** 图表中的颜色对应于 "性能" 面板底部 "**摘要**" 选项卡中的 "颜色"。</span><span class="sxs-lookup"><span data-stu-id="d3490-172">The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="d3490-173">**CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。</span><span class="sxs-lookup"><span data-stu-id="d3490-173">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="d3490-174">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span><span class="sxs-lookup"><span data-stu-id="d3490-174">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       <span data-ttu-id="d3490-176">The **CPU** chart and **Summary** tab</span><span class="sxs-lookup"><span data-stu-id="d3490-176">The **CPU** chart and **Summary** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3490-177">Hover on the **FPS**, **CPU**, or **NET** charts.</span><span class="sxs-lookup"><span data-stu-id="d3490-177">Hover on the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="d3490-178">DevTools shows a screenshot of the page at that point in time.</span><span class="sxs-lookup"><span data-stu-id="d3490-178">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="d3490-179">Move your mouse left and right to replay the recording.</span><span class="sxs-lookup"><span data-stu-id="d3490-179">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="d3490-180">The action is referenced as scrubbing, and it is useful for manually analyzing the progression of animations.</span><span class="sxs-lookup"><span data-stu-id="d3490-180">The action is referenced as scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       <span data-ttu-id="d3490-182">View a screenshot of the page around the 2500ms mark of the recording</span><span class="sxs-lookup"><span data-stu-id="d3490-182">View a screenshot of the page around the 2500ms mark of the recording</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3490-183">In the **Frames** section, hover on one of the green squares.</span><span class="sxs-lookup"><span data-stu-id="d3490-183">In the **Frames** section, hover on one of the green squares.</span></span>  <span data-ttu-id="d3490-184">DevTools shows you the FPS for that particular frame.</span><span class="sxs-lookup"><span data-stu-id="d3490-184">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="d3490-185">Each frame is probably well below the target of 60 FPS.</span><span class="sxs-lookup"><span data-stu-id="d3490-185">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       <span data-ttu-id="d3490-187">Hover on a frame</span><span class="sxs-lookup"><span data-stu-id="d3490-187">Hover on a frame</span></span>  
    :::image-end:::  
    
<span data-ttu-id="d3490-188">Of course, you should see that the page is not performing well.</span><span class="sxs-lookup"><span data-stu-id="d3490-188">Of course, you should see that the page is not performing well.</span></span>  <span data-ttu-id="d3490-189">But in real scenarios, it may not be so clear, so having all of the tools to make measurements comes in handy.</span><span class="sxs-lookup"><span data-stu-id="d3490-189">But in real scenarios, it may not be so clear, so having all of the tools to make measurements comes in handy.</span></span>  

#### <span data-ttu-id="d3490-190">Bonus: Open the FPS meter</span><span class="sxs-lookup"><span data-stu-id="d3490-190">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="d3490-191">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span><span class="sxs-lookup"><span data-stu-id="d3490-191">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="d3490-192">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span><span class="sxs-lookup"><span data-stu-id="d3490-192">Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="d3490-193">Start typing `Rendering` in the **Command Menu** and select **Show Rendering**.</span><span class="sxs-lookup"><span data-stu-id="d3490-193">Start typing `Rendering` in the **Command Menu** and select **Show Rendering**.</span></span>  
1.  <span data-ttu-id="d3490-194">In the **Rendering** tab, enable **FPS Meter**.</span><span class="sxs-lookup"><span data-stu-id="d3490-194">In the **Rendering** tab, enable **FPS Meter**.</span></span>  <span data-ttu-id="d3490-195">A new overlay appears in the top-right of your viewport.</span><span class="sxs-lookup"><span data-stu-id="d3490-195">A new overlay appears in the top-right of your viewport.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       <span data-ttu-id="d3490-197">The **FPS meter**</span><span class="sxs-lookup"><span data-stu-id="d3490-197">The **FPS meter**</span></span>  
        :::image-end:::  
    
1.  <span data-ttu-id="d3490-198">Disable the **FPS Meter** and select `Escape` to close the **Rendering** tab.  You are not using **FPS Meter** in this tutorial.</span><span class="sxs-lookup"><span data-stu-id="d3490-198">Disable the **FPS Meter** and select `Escape` to close the **Rendering** tab.  You are not using **FPS Meter** in this tutorial.</span></span>  
    
### <span data-ttu-id="d3490-199">Find the bottleneck</span><span class="sxs-lookup"><span data-stu-id="d3490-199">Find the bottleneck</span></span>  

<span data-ttu-id="d3490-200">After you measured and verified that the animation is not performing well, the next step is to answer the question "why?".</span><span class="sxs-lookup"><span data-stu-id="d3490-200">After you measured and verified that the animation is not performing well, the next step is to answer the question "why?".</span></span>  

1.  <span data-ttu-id="d3490-201">When no events are selected, the **Summary** tab shows you a breakdown of activity.</span><span class="sxs-lookup"><span data-stu-id="d3490-201">When no events are selected, the **Summary** tab shows you a breakdown of activity.</span></span>  <span data-ttu-id="d3490-202">The page spent most of the time rendering.</span><span class="sxs-lookup"><span data-stu-id="d3490-202">The page spent most of the time rendering.</span></span>  <span data-ttu-id="d3490-203">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span><span class="sxs-lookup"><span data-stu-id="d3490-203">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       <span data-ttu-id="d3490-205">The **Summary** tab</span><span class="sxs-lookup"><span data-stu-id="d3490-205">The **Summary** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3490-206">Expand the **Main** section.</span><span class="sxs-lookup"><span data-stu-id="d3490-206">Expand the **Main** section.</span></span>  <span data-ttu-id="d3490-207">DevTools 将显示一段时间内主线程上活动的帧图表。</span><span class="sxs-lookup"><span data-stu-id="d3490-207">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="d3490-208">x 轴表示一段时间内的记录。</span><span class="sxs-lookup"><span data-stu-id="d3490-208">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="d3490-209">每个条形表示一个事件。</span><span class="sxs-lookup"><span data-stu-id="d3490-209">Each bar represents an event.</span></span>  <span data-ttu-id="d3490-210">宽条表示该事件花费了更长的时间。</span><span class="sxs-lookup"><span data-stu-id="d3490-210">A wider bar means that event took longer.</span></span>  <span data-ttu-id="d3490-211">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="d3490-211">The y-axis represents the call stack.</span></span>  <span data-ttu-id="d3490-212">When you see events stacked on top of each other, it means the upper events caused the lower events.</span><span class="sxs-lookup"><span data-stu-id="d3490-212">When you see events stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       <span data-ttu-id="d3490-214">The **Main** section</span><span class="sxs-lookup"><span data-stu-id="d3490-214">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="d3490-215">There is a lot of data in the recording.</span><span class="sxs-lookup"><span data-stu-id="d3490-215">There is a lot of data in the recording.</span></span>  <span data-ttu-id="d3490-216">To Zoom into a single event; choose, hold, and dragg your cursor over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span><span class="sxs-lookup"><span data-stu-id="d3490-216">To Zoom into a single event; choose, hold, and dragg your cursor over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="d3490-217">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span><span class="sxs-lookup"><span data-stu-id="d3490-217">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       <span data-ttu-id="d3490-219">Zoom into an event</span><span class="sxs-lookup"><span data-stu-id="d3490-219">Zoom into an event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-220">Another way to zoom, focus the **Main** section, choose the background or an event, and select `W`, `A`, `S`, or `D`.</span><span class="sxs-lookup"><span data-stu-id="d3490-220">Another way to zoom, focus the **Main** section, choose the background or an event, and select `W`, `A`, `S`, or `D`.</span></span>  
    
    1.  <span data-ttu-id="d3490-221">Focus on the red triangle in the top-right of the **Animation Frame Fired** event.</span><span class="sxs-lookup"><span data-stu-id="d3490-221">Focus on the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="d3490-222">Whenever you see a red triangle, it is a warning that there may be an issue related to the event.</span><span class="sxs-lookup"><span data-stu-id="d3490-222">Whenever you see a red triangle, it is a warning that there may be an issue related to the event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-223">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span><span class="sxs-lookup"><span data-stu-id="d3490-223">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="d3490-224">Choose the **Animation Frame Fired** event.</span><span class="sxs-lookup"><span data-stu-id="d3490-224">Choose the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="d3490-225">The **Summary** tab now shows you information about that event.</span><span class="sxs-lookup"><span data-stu-id="d3490-225">The **Summary** tab now shows you information about that event.</span></span>  <span data-ttu-id="d3490-226">Note the **Reveal** link.</span><span class="sxs-lookup"><span data-stu-id="d3490-226">Note the **Reveal** link.</span></span>  <span data-ttu-id="d3490-227">After you choose it, DevTools to highlights the event that initiated the **Animation Frame Fired** event.</span><span class="sxs-lookup"><span data-stu-id="d3490-227">After you choose it, DevTools to highlights the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="d3490-228">Also, focus on the **app.js:95** link.</span><span class="sxs-lookup"><span data-stu-id="d3490-228">Also, focus on the **app.js:95** link.</span></span>  <span data-ttu-id="d3490-229">After you choose it, the relevant line in the source code is displayed.</span><span class="sxs-lookup"><span data-stu-id="d3490-229">After you choose it, the relevant line in the source code is displayed.</span></span>
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       <span data-ttu-id="d3490-231">More information about the **Animation Frame Fired** event</span><span class="sxs-lookup"><span data-stu-id="d3490-231">More information about the **Animation Frame Fired** event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-232">After selecting an event, use the arrow keys to select the events next to it.</span><span class="sxs-lookup"><span data-stu-id="d3490-232">After selecting an event, use the arrow keys to select the events next to it.</span></span>  
    
1.  <span data-ttu-id="d3490-233">Under the **app.update** event, there is a bunch of purple events.</span><span class="sxs-lookup"><span data-stu-id="d3490-233">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="d3490-234">If each purple event was wider, it looks as though each one may have a red triangle on it.</span><span class="sxs-lookup"><span data-stu-id="d3490-234">If each purple event was wider, it looks as though each one may have a red triangle on it.</span></span>  
1.  <span data-ttu-id="d3490-235">Choose one of the purple **Layout** events.</span><span class="sxs-lookup"><span data-stu-id="d3490-235">Choose one of the purple **Layout** events.</span></span>  <span data-ttu-id="d3490-236">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span><span class="sxs-lookup"><span data-stu-id="d3490-236">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  
    
1.  <span data-ttu-id="d3490-237">In the **Summary** tab, choose the **app.js:71** link under **Layout Forced**.</span><span class="sxs-lookup"><span data-stu-id="d3490-237">In the **Summary** tab, choose the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="d3490-238">DevTools takes you to the line of code that forced the layout.</span><span class="sxs-lookup"><span data-stu-id="d3490-238">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       <span data-ttu-id="d3490-240">The line of code that caused the forced layout</span><span class="sxs-lookup"><span data-stu-id="d3490-240">The line of code that caused the forced layout</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="d3490-241">The problem with the code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span><span class="sxs-lookup"><span data-stu-id="d3490-241">The problem with the code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="d3490-242">Because the styles changed, the browser does not know if each icon position changed, so it has to re-layout the icon in order to compute the new position.</span><span class="sxs-lookup"><span data-stu-id="d3490-242">Because the styles changed, the browser does not know if each icon position changed, so it has to re-layout the icon in order to compute the new position.</span></span>  <!--  > See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->
    
<!-- todo: add layouts section when available -->

<span data-ttu-id="d3490-243">That was a lot to learn.</span><span class="sxs-lookup"><span data-stu-id="d3490-243">That was a lot to learn.</span></span>  <span data-ttu-id="d3490-244">You now have a solid foundation in the basic workflow for analyzing runtime performance.</span><span class="sxs-lookup"><span data-stu-id="d3490-244">You now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="d3490-245">Good job.</span><span class="sxs-lookup"><span data-stu-id="d3490-245">Good job.</span></span>  

### <span data-ttu-id="d3490-246">Bonus: Analyze the optimized version</span><span class="sxs-lookup"><span data-stu-id="d3490-246">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="d3490-247">Using the workflows and tools that you just learned, choose **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span><span class="sxs-lookup"><span data-stu-id="d3490-247">Using the workflows and tools that you just learned, choose **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="d3490-248">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you are able to see that the optimized version of the app does much less work, resulting in better performance.</span><span class="sxs-lookup"><span data-stu-id="d3490-248">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you are able to see that the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="d3490-249">Even the optimized version is not great, because it manipulates the `top` property of every icon.</span><span class="sxs-lookup"><span data-stu-id="d3490-249">Even the optimized version is not great, because it manipulates the `top` property of every icon.</span></span>  <span data-ttu-id="d3490-250">A better approach is to stick to properties that only affect compositing.</span><span class="sxs-lookup"><span data-stu-id="d3490-250">A better approach is to stick to properties that only affect compositing.</span></span>  <!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## <span data-ttu-id="d3490-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="d3490-251">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

<span data-ttu-id="d3490-252">To get more comfortable with the Performance panel, practice makes perfect.</span><span class="sxs-lookup"><span data-stu-id="d3490-252">To get more comfortable with the Performance panel, practice makes perfect.</span></span>  <span data-ttu-id="d3490-253">Try profiling your pages and analyzing the results.</span><span class="sxs-lookup"><span data-stu-id="d3490-253">Try profiling your pages and analyzing the results.</span></span>  <span data-ttu-id="d3490-254">If you have any questions about your results, use the **Send Feedback** icon, select `Alt`+`Shift`+`I` \(Windows\), select `Option`+`Shift`+`I` \(macOS\), or [tweet the DevTools team][TwitterEdgeDevtools].</span><span class="sxs-lookup"><span data-stu-id="d3490-254">If you have any questions about your results, use the **Send Feedback** icon, select `Alt`+`Shift`+`I` \(Windows\), select `Option`+`Shift`+`I` \(macOS\), or [tweet the DevTools team][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="d3490-255">Include screenshots or links to reproducible pages, if possible.</span><span class="sxs-lookup"><span data-stu-id="d3490-255">Include screenshots or links to reproducible pages, if possible.</span></span>  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   <span data-ttu-id="d3490-257">The **Send Feedback** icon in the Microsoft Edge DevTools</span><span class="sxs-lookup"><span data-stu-id="d3490-257">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="d3490-258">Last, there are many ways to improve runtime performance.</span><span class="sxs-lookup"><span data-stu-id="d3490-258">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="d3490-259">This article focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span><span class="sxs-lookup"><span data-stu-id="d3490-259">This article focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

<!-- links -->

[DevtoolsCustomizePlacement]: ../customize/placement.md "Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)"  
[DevtoolsSpeedGetStarted]: ../speed/get-started.md "使用 Microsoft Edge 开发人员工具优化网站速度"  

[TwitterEdgeDevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "EdgeDevTools - 发布推文 | Twitter"  

[MDNWebRequestAnimationFrame]: https://developer.mozilla.org/docs/Web/API/window/requestAnimationFrame "Window.requestAnimationFrame\(\) | MDN"  

<!--[InPrivate]: https://support.microsoft.com/help/4026200/microsoft-edge-browse-inprivate "Browse InPrivate in Microsoft Edge"  -->

<!--[FrameAnatomy]: https://aerotwist.com/blog/the-anatomy-of-a-frame  -->  

<!--[RAIL]: /web/fundamentals/performance/rail  -->  
<!--[RenderingAvoidSynchronousLayouts]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing#avoid_forced_synchronous_layouts  -->  
<!--[RenderingAvoidThrashing]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing  -->  
<!--[RenderingCompositor]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count#use_transform_and_opacity_changes_for_animations  -->  
<!--[RenderingDebounceInputs]: /web/fundamentals/performance/rendering/debounce-your-input-handlers  -->
<!--[RenderingManageLayers]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count  -->  
<!--[RenderingOptimizeJS]: /web/fundamentals/performance/rendering/optimize-javascript-execution  -->  
<!--[RenderingPerformance]: /web/fundamentals/performance/rendering  -->  
<!--[RenderingReduceScope]: /web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations  -->  
<!--[RenderingSimplifyPaint]: /web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas  -->  

<!--[StackOverflowAlphabetBrowserDevtools]: https://stackoverflow.com/questions/ask?tags=alphabet-browser-devtools "Alphabet Browser - Stack Overflow"  -->  

> [!NOTE]
> <span data-ttu-id="d3490-264">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="d3490-264">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="d3490-265">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="d3490-265">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="d3490-267">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="d3490-267">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
