---
title: 分析运行时性能入门
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: bff2d2fb0ff8424303289183ca8c5935ef477381
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611739"
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







# <span data-ttu-id="e8886-103">分析运行时性能入门</span><span class="sxs-lookup"><span data-stu-id="e8886-103">Get Started With Analyzing Runtime Performance</span></span>   



> [!NOTE]
> <span data-ttu-id="e8886-104">请参阅[优化网站速度][DevtoolsSpeedGetStarted]，了解如何使页面更快加载。</span><span class="sxs-lookup"><span data-stu-id="e8886-104">See [Optimize Website Speed][DevtoolsSpeedGetStarted] to learn how to make your pages load faster.</span></span>  

<span data-ttu-id="e8886-105">运行时性能是指页面在运行时的执行方式，而不是加载。</span><span class="sxs-lookup"><span data-stu-id="e8886-105">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="e8886-106">本教程指导你如何使用 Microsoft Edge DevTools 性能面板来分析运行时性能。</span><span class="sxs-lookup"><span data-stu-id="e8886-106">This tutorial teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="e8886-107">就**滑轨**模型而言，在本教程中学习的技能对于分析页面的响应、动画和空闲阶段非常有用。</span><span class="sxs-lookup"><span data-stu-id="e8886-107">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <span data-ttu-id="e8886-108">开始行动</span><span class="sxs-lookup"><span data-stu-id="e8886-108">Get started</span></span>   

<span data-ttu-id="e8886-109">在本教程中，你将在实时页面上打开 DevTools，并使用 "性能" 面板查找页面上的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="e8886-109">In this tutorial, you open DevTools on a live page and use the Performance panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="e8886-110">在**InPrivate 模式下**打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="e8886-110">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="e8886-111">InPrivate 模式可确保 Microsoft Edge 在干净状态下运行。</span><span class="sxs-lookup"><span data-stu-id="e8886-111">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="e8886-112">例如，如果安装了大量的扩展，这些扩展可能会在性能测量中产生噪音。</span><span class="sxs-lookup"><span data-stu-id="e8886-112">For example, if you have a lot of extensions installed, those extensions might create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="e8886-113">在您的 InPrivate 窗口中加载以下页面。</span><span class="sxs-lookup"><span data-stu-id="e8886-113">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="e8886-114">这是您要分析的演示。</span><span class="sxs-lookup"><span data-stu-id="e8886-114">This is the demo that you're going to profile.</span></span>  <span data-ttu-id="e8886-115">页面将显示一组小图标，上下移动。</span><span class="sxs-lookup"><span data-stu-id="e8886-115">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/jank/
    ```  
    
1.  <span data-ttu-id="e8886-116">按 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="e8886-116">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    > ###### <span data-ttu-id="e8886-117">图 1</span><span class="sxs-lookup"><span data-stu-id="e8886-117">Figure 1</span></span>  
    > <span data-ttu-id="e8886-118">左侧的演示和右侧的 DevTools</span><span class="sxs-lookup"><span data-stu-id="e8886-118">The demo on the left, and DevTools on the right</span></span>  
    > ![左侧的演示和右侧的 DevTools][ImageGetStarted]  
    
    > [!NOTE]
    > <span data-ttu-id="e8886-120">对于屏幕截图的其余部分，DevTools 将取消[停靠到一个单独的窗口][DevtoolsCustomizePlacement]，以便你可以更好地查看内容。</span><span class="sxs-lookup"><span data-stu-id="e8886-120">For the rest of the screenshots, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] so that you can see the contents better.</span></span>  
    
### <span data-ttu-id="e8886-121">模拟移动 CPU</span><span class="sxs-lookup"><span data-stu-id="e8886-121">Simulate a mobile CPU</span></span>  

<span data-ttu-id="e8886-122">移动设备具有比台式机和笔记本电脑更少的 CPU 功率。</span><span class="sxs-lookup"><span data-stu-id="e8886-122">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="e8886-123">分析页面时，请使用 CPU 限制模拟页面在移动设备上的执行方式。</span><span class="sxs-lookup"><span data-stu-id="e8886-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="e8886-124">在 DevTools 中，单击 "**性能**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e8886-124">In DevTools, click the **Performance** tab.</span></span>  
1.  <span data-ttu-id="e8886-125">请确保 "**屏幕截图**" 复选框已启用。</span><span class="sxs-lookup"><span data-stu-id="e8886-125">Make sure that the **Screenshots** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="e8886-126">单击 "**捕获设置** ![ 捕获设置" ][ImageCaptureSettingsIcon] 。</span><span class="sxs-lookup"><span data-stu-id="e8886-126">Click **Capture Settings** ![Capture Settings][ImageCaptureSettingsIcon].</span></span>  <span data-ttu-id="e8886-127">DevTools 显示与如何捕获性能指标相关的设置。</span><span class="sxs-lookup"><span data-stu-id="e8886-127">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="e8886-128">对于**CPU**，选择**4x 减速**。</span><span class="sxs-lookup"><span data-stu-id="e8886-128">For **CPU**, select **4x slowdown**.</span></span>  <span data-ttu-id="e8886-129">DevTools 将 CPU 限制为比平时慢4倍。</span><span class="sxs-lookup"><span data-stu-id="e8886-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    > ###### <span data-ttu-id="e8886-130">图 2</span><span class="sxs-lookup"><span data-stu-id="e8886-130">Figure 2</span></span>  
    > <span data-ttu-id="e8886-131">CPU 限制</span><span class="sxs-lookup"><span data-stu-id="e8886-131">CPU throttling</span></span>  
    > ![CPU 限制][ImageCPUThrottling]  
    
    > [!NOTE]
    > <span data-ttu-id="e8886-133">测试其他页面时，如果你希望确保它们在低端移动设备上能够正常工作，请将 CPU 限制设置为**6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="e8886-133">When testing other pages, if you want to ensure that they work well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="e8886-134">此演示不太适合6x 速度，因此它只是为了说明目的而使用4x 减速。</span><span class="sxs-lookup"><span data-stu-id="e8886-134">This demo doesn't work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <span data-ttu-id="e8886-135">设置演示</span><span class="sxs-lookup"><span data-stu-id="e8886-135">Set up the demo</span></span>  

<span data-ttu-id="e8886-136">很难创建适用于本网站的所有读者的运行时性能演示。</span><span class="sxs-lookup"><span data-stu-id="e8886-136">It is hard to create a runtime performance demo that works consistently for all readers of this website.</span></span>  <span data-ttu-id="e8886-137">本部分允许你自定义演示，以确保你的体验与你在本教程中看到的屏幕截图和说明相对一致，无论你的特定设置如何。</span><span class="sxs-lookup"><span data-stu-id="e8886-137">This section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions you see in this tutorial, regardless of your particular setup.</span></span>

1.  <span data-ttu-id="e8886-138">继续单击 "**添加 10** "，直到蓝色图标的移动速度明显比以前慢一些。</span><span class="sxs-lookup"><span data-stu-id="e8886-138">Keep clicking **Add 10** until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="e8886-139">在高端计算机上，可能需要大约20次单击。</span><span class="sxs-lookup"><span data-stu-id="e8886-139">On a high-end machine, it may take about 20 clicks.</span></span>  
1.  <span data-ttu-id="e8886-140">单击 "**优化**"。</span><span class="sxs-lookup"><span data-stu-id="e8886-140">Click **Optimize**.</span></span>  <span data-ttu-id="e8886-141">蓝色图标的移动速度更快、更流畅。</span><span class="sxs-lookup"><span data-stu-id="e8886-141">The blue icons should move faster and more smoothly.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="e8886-142">如果未看到已优化和未优化版本之间的显著差异，请尝试单击几次**减去 10**次，然后重试。</span><span class="sxs-lookup"><span data-stu-id="e8886-142">If you don't see a noticeable difference between the optimized and un-optimized versions, try clicking **Subtract 10** a few times and trying again.</span></span>  
    > <span data-ttu-id="e8886-143">如果添加过多的蓝色图标，则只需占用 CPU 的最大值，您就不会看到两个版本的结果中的主要差异。</span><span class="sxs-lookup"><span data-stu-id="e8886-143">If you add too many blue icons, you're just going to max out the CPU and you're not going to see a major difference in the results for the two versions.</span></span>  

1.  <span data-ttu-id="e8886-144">单击 "**取消优化**"。</span><span class="sxs-lookup"><span data-stu-id="e8886-144">Click **Un-Optimize**.</span></span>  <span data-ttu-id="e8886-145">蓝色图标的移动速度较慢，并且与更多 jank。</span><span class="sxs-lookup"><span data-stu-id="e8886-145">The blue icons move slower and with more jank again.</span></span>  

### <span data-ttu-id="e8886-146">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="e8886-146">Record runtime performance</span></span>   

<span data-ttu-id="e8886-147">运行优化版本的页面时，蓝色图标的移动速度更快。</span><span class="sxs-lookup"><span data-stu-id="e8886-147">When you ran the optimized version of the page, the blue icons move faster.</span></span>  
<span data-ttu-id="e8886-148">这是为什么呢？</span><span class="sxs-lookup"><span data-stu-id="e8886-148">Why is that?</span></span>  <span data-ttu-id="e8886-149">这两个版本都可以在同一时间内将图标移动相同的空间量。</span><span class="sxs-lookup"><span data-stu-id="e8886-149">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="e8886-150">在 "性能" 面板中记录一个记录，了解如何检测未优化版本中的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="e8886-150">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="e8886-151">在 DevTools 中，单击 "**录制** ![ 记录" ][ImageRecordIcon] 。</span><span class="sxs-lookup"><span data-stu-id="e8886-151">In DevTools, click **Record** ![Record][ImageRecordIcon].</span></span>  
    <span data-ttu-id="e8886-152">DevTools 在页面运行时捕获性能指标。</span><span class="sxs-lookup"><span data-stu-id="e8886-152">DevTools captures performance metrics as the page runs.</span></span>  
    
    > ###### <span data-ttu-id="e8886-153">图 3</span><span class="sxs-lookup"><span data-stu-id="e8886-153">Figure 3</span></span> 
    > <span data-ttu-id="e8886-154">分析页面</span><span class="sxs-lookup"><span data-stu-id="e8886-154">Profiling the page</span></span>  
    > ![分析页面][ImagePageProfiling]  
    
1.  <span data-ttu-id="e8886-156">等待几秒钟。</span><span class="sxs-lookup"><span data-stu-id="e8886-156">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="e8886-157">单击 "**停止**"。</span><span class="sxs-lookup"><span data-stu-id="e8886-157">Click **Stop**.</span></span>  <span data-ttu-id="e8886-158">DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。</span><span class="sxs-lookup"><span data-stu-id="e8886-158">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    > ###### <span data-ttu-id="e8886-159">图 4</span><span class="sxs-lookup"><span data-stu-id="e8886-159">Figure 4</span></span>  
    > <span data-ttu-id="e8886-160">配置文件的结果</span><span class="sxs-lookup"><span data-stu-id="e8886-160">The results of the profile</span></span>  
    > ![配置文件的结果][ImageProfileResults]  

<span data-ttu-id="e8886-162">哇，这是大量数据。</span><span class="sxs-lookup"><span data-stu-id="e8886-162">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="e8886-163">别担心，很快就会有更多的意义。</span><span class="sxs-lookup"><span data-stu-id="e8886-163">Don't worry, it'll all make more sense shortly.</span></span>  

## <span data-ttu-id="e8886-164">分析结果</span><span class="sxs-lookup"><span data-stu-id="e8886-164">Analyze the results</span></span>   

<span data-ttu-id="e8886-165">记录了页面性能后，你可以测量页面性能有多差，并找到任何原因。</span><span class="sxs-lookup"><span data-stu-id="e8886-165">Once you've got a recording the performance of the page, you can measure how poor the performance of the page is, and find the any causes.</span></span>  

### <span data-ttu-id="e8886-166">分析每秒帧数</span><span class="sxs-lookup"><span data-stu-id="e8886-166">Analyze frames per second</span></span>  

<span data-ttu-id="e8886-167">测量任何动画性能的主要指标是每秒帧数 \ （FPS \）。</span><span class="sxs-lookup"><span data-stu-id="e8886-167">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="e8886-168">当动画在 60 FPS 运行时，用户将感到满意。</span><span class="sxs-lookup"><span data-stu-id="e8886-168">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="e8886-169">查看**FPS**图表。</span><span class="sxs-lookup"><span data-stu-id="e8886-169">Look at the **FPS** chart.</span></span>  <span data-ttu-id="e8886-170">每当你在**FPS**上方看到红色条形图时，这意味着该变得较低的变帧可能会损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="e8886-170">Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="e8886-171">通常情况下，绿色条越高，FPS 越高。</span><span class="sxs-lookup"><span data-stu-id="e8886-171">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    > ###### <span data-ttu-id="e8886-172">图 5</span><span class="sxs-lookup"><span data-stu-id="e8886-172">Figure 5</span></span>  
    > <span data-ttu-id="e8886-173">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="e8886-173">The FPS chart</span></span>  
    > ![FPS 图表][ImageFPSChart]  

1.  <span data-ttu-id="e8886-175">在**FPS**图表下，你可以看到**CPU**图表。</span><span class="sxs-lookup"><span data-stu-id="e8886-175">Below the **FPS** chart you see the **CPU** chart.</span></span>  <span data-ttu-id="e8886-176">**CPU**图表中的颜色对应于 "性能" 面板底部的 "**摘要**" 选项卡中的颜色。</span><span class="sxs-lookup"><span data-stu-id="e8886-176">The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="e8886-177">**Cpu**图表的完全颜色意味着在录制期间 cpu 已 maxed。</span><span class="sxs-lookup"><span data-stu-id="e8886-177">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="e8886-178">只要您看到 CPU maxed 长时间，它就是查找更少工作的方法的提示。</span><span class="sxs-lookup"><span data-stu-id="e8886-178">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span></span>  
    
    > ###### <span data-ttu-id="e8886-179">图 6</span><span class="sxs-lookup"><span data-stu-id="e8886-179">Figure 6</span></span>  
    > <span data-ttu-id="e8886-180">CPU 图表和摘要选项卡</span><span class="sxs-lookup"><span data-stu-id="e8886-180">The CPU chart and Summary tab</span></span>  
    > ![CPU 图表和摘要选项卡][ImageCPUSummary]  

1.  <span data-ttu-id="e8886-182">将鼠标悬停在 " **FPS**"、" **CPU**" 或 "**网络**" 图表上。</span><span class="sxs-lookup"><span data-stu-id="e8886-182">Hover your mouse over the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="e8886-183">DevTools 显示该时间点的页面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="e8886-183">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="e8886-184">将鼠标向左和向右移动以重播录制。</span><span class="sxs-lookup"><span data-stu-id="e8886-184">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="e8886-185">这称为 "清理"，它对于手动分析动画进度很有用。</span><span class="sxs-lookup"><span data-stu-id="e8886-185">This is called scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    > ###### <span data-ttu-id="e8886-186">图 7</span><span class="sxs-lookup"><span data-stu-id="e8886-186">Figure 7</span></span>  
    > <span data-ttu-id="e8886-187">在录制的2500ms 标记周围查看页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="e8886-187">Viewing a screenshot of the page around the 2500ms mark of the recording</span></span>  
    > ![在录制的2500ms 标记周围查看页面的屏幕截图][ImageViewingScreenshot]  

1.  <span data-ttu-id="e8886-189">在 "**框架**" 部分中，将鼠标悬停在其中一个绿色方块上。</span><span class="sxs-lookup"><span data-stu-id="e8886-189">In the **Frames** section, hover your mouse over one of the green squares.</span></span>  <span data-ttu-id="e8886-190">DevTools 显示该特定帧的 FPS。</span><span class="sxs-lookup"><span data-stu-id="e8886-190">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="e8886-191">每个帧可能很好地低于 60 FPS 的目标。</span><span class="sxs-lookup"><span data-stu-id="e8886-191">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    > ###### <span data-ttu-id="e8886-192">图 8</span><span class="sxs-lookup"><span data-stu-id="e8886-192">Figure 8</span></span>  
    > <span data-ttu-id="e8886-193">将鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="e8886-193">Hovering over a frame</span></span>  
    > ![将鼠标悬停在框架上][ImageFrameHover]  

<span data-ttu-id="e8886-195">当然，通过此演示，很明显，页面的性能不佳。</span><span class="sxs-lookup"><span data-stu-id="e8886-195">Of course, with this demo, it is pretty obvious that the page is not performing well.</span></span>  <span data-ttu-id="e8886-196">但在实际情况下，它可能不是很清楚，因此，让所有这些工具能够使测量更方便。</span><span class="sxs-lookup"><span data-stu-id="e8886-196">But in real scenarios, it may not be so clear, so having all of these tools to make measurements comes in handy.</span></span>  

#### <span data-ttu-id="e8886-197">奖金：打开 FPS 指示器</span><span class="sxs-lookup"><span data-stu-id="e8886-197">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="e8886-198">另一个方便的工具是 FPS 指示器，可在页面运行时提供对 FPS 的实时估计。</span><span class="sxs-lookup"><span data-stu-id="e8886-198">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="e8886-199">按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。</span><span class="sxs-lookup"><span data-stu-id="e8886-199">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="e8886-200">开始 `Rendering` 在 "命令" 菜单中键入，然后选择 "**显示呈现**"。</span><span class="sxs-lookup"><span data-stu-id="e8886-200">Start typing `Rendering` in the Command Menu and select **Show Rendering**.</span></span>  
1.  <span data-ttu-id="e8886-201">在 "**呈现**" 选项卡上，启用**FPS 指示器**。</span><span class="sxs-lookup"><span data-stu-id="e8886-201">In the **Rendering** tab, enable **FPS Meter**.</span></span>  <span data-ttu-id="e8886-202">新的覆盖区将出现在视区的右上角。</span><span class="sxs-lookup"><span data-stu-id="e8886-202">A new overlay appears in the top-right of your viewport.</span></span>  
    
    > ###### <span data-ttu-id="e8886-203">图 9</span><span class="sxs-lookup"><span data-stu-id="e8886-203">Figure 9</span></span>  
    > <span data-ttu-id="e8886-204">FPS 指示器</span><span class="sxs-lookup"><span data-stu-id="e8886-204">The FPS meter</span></span>  
    > ![FPS 指示器][ImageFPSMeter]  

1.  <span data-ttu-id="e8886-206">禁用**FPS 指示器**，然后按 `Escape` 关闭 "**呈现**" 选项卡。 您不会在本教程中使用它。</span><span class="sxs-lookup"><span data-stu-id="e8886-206">Disable the **FPS Meter** and press `Escape` to close the **Rendering** tab.  You won't be using it in this tutorial.</span></span>  

### <span data-ttu-id="e8886-207">找出瓶颈</span><span class="sxs-lookup"><span data-stu-id="e8886-207">Find the bottleneck</span></span>  

<span data-ttu-id="e8886-208">现在，你已经测量并验证动画是否工作不好，下一个要回答的问题是：为什么？</span><span class="sxs-lookup"><span data-stu-id="e8886-208">Now that you've measured and verified that the animation is not performing well, the next question to answer is:  why?</span></span>  

1.  <span data-ttu-id="e8886-209">注意 "摘要" 选项卡。 如果未选择任何事件，此选项卡将显示活动的细目。</span><span class="sxs-lookup"><span data-stu-id="e8886-209">Note the summary tab.  When no events are selected, this tab shows you a breakdown of activity.</span></span>  <span data-ttu-id="e8886-210">该页的大部分时间都已花费在呈现中。</span><span class="sxs-lookup"><span data-stu-id="e8886-210">The page spent most of its time rendering.</span></span>  <span data-ttu-id="e8886-211">由于性能是执行较少工作的艺术，因此你的目标是减少执行呈现工作所花费的时间量。</span><span class="sxs-lookup"><span data-stu-id="e8886-211">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    > ###### <span data-ttu-id="e8886-212">图 10</span><span class="sxs-lookup"><span data-stu-id="e8886-212">Figure 10</span></span>  
    > <span data-ttu-id="e8886-213">"摘要" 选项卡</span><span class="sxs-lookup"><span data-stu-id="e8886-213">The Summary tab</span></span>  
    > !["摘要" 选项卡][ImageSummaryTab]  

1.  <span data-ttu-id="e8886-215">展开 "**主**" 部分。</span><span class="sxs-lookup"><span data-stu-id="e8886-215">Expand the **Main** section.</span></span>  <span data-ttu-id="e8886-216">DevTools 显示了一段时间内主线程上活动的火焰图表。</span><span class="sxs-lookup"><span data-stu-id="e8886-216">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="e8886-217">X 轴代表一段时间内的录音。</span><span class="sxs-lookup"><span data-stu-id="e8886-217">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="e8886-218">每条条表示一个事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-218">Each bar represents an event.</span></span>  <span data-ttu-id="e8886-219">较大的栏表示事件花费较长时间。</span><span class="sxs-lookup"><span data-stu-id="e8886-219">A wider bar means that event took longer.</span></span>  <span data-ttu-id="e8886-220">Y 轴表示调用堆栈。</span><span class="sxs-lookup"><span data-stu-id="e8886-220">The y-axis represents the call stack.</span></span>  <span data-ttu-id="e8886-221">当你看到彼此重叠的事件时，它表示较高事件导致较低的事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-221">When you see events stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    > ##### <span data-ttu-id="e8886-222">图 11</span><span class="sxs-lookup"><span data-stu-id="e8886-222">Figure 11</span></span>  
    > <span data-ttu-id="e8886-223">主要部分</span><span class="sxs-lookup"><span data-stu-id="e8886-223">The Main section</span></span>  
    > ![主要部分][ImageMainSection]  

1.  <span data-ttu-id="e8886-225">录制中有大量数据。</span><span class="sxs-lookup"><span data-stu-id="e8886-225">There is a lot of data in the recording.</span></span>  <span data-ttu-id="e8886-226">通过在**概述**中单击、按住和拖动鼠标来放大单个事件，这是包括**FPS**、 **CPU**和**网络**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="e8886-226">Zoom in on a single event by clicking, holding, and dragging your mouse over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="e8886-227">"**主要**" 部分和 "**摘要**" 选项卡仅显示录制的选定部分的信息。</span><span class="sxs-lookup"><span data-stu-id="e8886-227">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span></span>  
    
    > ###### <span data-ttu-id="e8886-228">图 12</span><span class="sxs-lookup"><span data-stu-id="e8886-228">Figure 12</span></span>  
    > <span data-ttu-id="e8886-229">放大单个事件</span><span class="sxs-lookup"><span data-stu-id="e8886-229">Zoomed in on a single event</span></span>  
    > ![放大事件][ImageZoomedAnimation]  
    
    > [!NOTE]
    > <span data-ttu-id="e8886-231">缩放的另一种方法是通过单击其背景或选择事件来重点关注**主**节，然后按 `W` 、、 `A` `S` 、和 `D` 键。</span><span class="sxs-lookup"><span data-stu-id="e8886-231">Another way to zoom is to focus the **Main** section by clicking its background or selecting an event, and then press the `W`, `A`, `S`, and `D` keys.</span></span>  
    
    1.  <span data-ttu-id="e8886-232">注意**动画帧**的右上角的红色三角形激发了事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-232">Note the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="e8886-233">只要看到红色三角形，就会出现一条警告，指出可能存在与此事件相关的问题。</span><span class="sxs-lookup"><span data-stu-id="e8886-233">Whenever you see a red triangle, it is a warning that there may be an issue related to this event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="e8886-234">只要运行[ `requestAnimationFrame()` 回调][MDNWebRequestAnimationFrame]，就会发生引发事件的**动画帧**。</span><span class="sxs-lookup"><span data-stu-id="e8886-234">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="e8886-235">单击**动画帧激发**的事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-235">Click the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="e8886-236">"**摘要**" 选项卡现显示有关该事件的信息。</span><span class="sxs-lookup"><span data-stu-id="e8886-236">The **Summary** tab now shows you information about that event.</span></span>  <span data-ttu-id="e8886-237">注意 "**显示**" 链接。</span><span class="sxs-lookup"><span data-stu-id="e8886-237">Note the **Reveal** link.</span></span>  <span data-ttu-id="e8886-238">单击 "导致 DevTools"，以突出显示发起**动画帧触发**事件的事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-238">Clicking that causes DevTools to highlight the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="e8886-239">另请注意， **app.config： 95**链接。</span><span class="sxs-lookup"><span data-stu-id="e8886-239">Also note the **app.js:95** link.</span></span>  <span data-ttu-id="e8886-240">单击该方法可跳转到源代码中的相关行。</span><span class="sxs-lookup"><span data-stu-id="e8886-240">Clicking that jumps you to the relevant line in the source code.</span></span>
    
    > ##### <span data-ttu-id="e8886-241">图 13</span><span class="sxs-lookup"><span data-stu-id="e8886-241">Figure 13</span></span>  
    > <span data-ttu-id="e8886-242">有关动画帧激发事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="e8886-242">More information about the Animation Frame Fired event</span></span>  
    > ![有关动画帧激发事件的详细信息][ImageAnimationFrameFired]  
    
    > [!NOTE]
    > <span data-ttu-id="e8886-244">选择事件后，使用箭头键选择它旁边的事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-244">After selecting an event, use the arrow keys to select the events next to it.</span></span>  

1.  <span data-ttu-id="e8886-245">在**应用程序更新**事件下，有一组紫色事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-245">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="e8886-246">如果它们的宽度较宽，则它看起来好像每个文件可能有一个红色三角形。</span><span class="sxs-lookup"><span data-stu-id="e8886-246">If they were wider, it looks as though each one might have a red triangle on it.</span></span>  <span data-ttu-id="e8886-247">立即单击其中一个紫色**布局**事件。</span><span class="sxs-lookup"><span data-stu-id="e8886-247">Click one of the purple **Layout** events now.</span></span>  <span data-ttu-id="e8886-248">DevTools 在 "**摘要**" 选项卡中提供有关事件的详细信息。 事实上，有关于强制重排 \ （另一个 word for layout）的警告。</span><span class="sxs-lookup"><span data-stu-id="e8886-248">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  

1.  <span data-ttu-id="e8886-249">在 "**摘要**" 选项卡中，单击 "**布局强制**" 下的 " **.js： 71** " 链接。</span><span class="sxs-lookup"><span data-stu-id="e8886-249">In the **Summary** tab, click the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="e8886-250">DevTools 将转到强制执行布局的代码行。</span><span class="sxs-lookup"><span data-stu-id="e8886-250">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    > ##### <span data-ttu-id="e8886-251">图 14</span><span class="sxs-lookup"><span data-stu-id="e8886-251">Figure 14</span></span>  
    > <span data-ttu-id="e8886-252">导致强制布局的代码行</span><span class="sxs-lookup"><span data-stu-id="e8886-252">The line of code that caused the forced layout</span></span>  
    > ![导致强制布局的代码行][ImageForcedLayoutSRC]  
    
    > [!NOTE]
    > <span data-ttu-id="e8886-254">此代码的问题是，在每个动画帧中，它会更改每个图标的样式，然后查询页面上每个图标的位置。</span><span class="sxs-lookup"><span data-stu-id="e8886-254">The problem with this code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="e8886-255">由于样式已更改，因此浏览器不知道每个图标位置是否已更改，因此它必须重新布局图标才能计算其位置。</span><span class="sxs-lookup"><span data-stu-id="e8886-255">Because the styles changed, the browser doesn't know if each icon position changed, so it has to re-layout the icon in order to compute its position.</span></span>  <!--  See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->

<!-- todo: add layouts section when available -->

<span data-ttu-id="e8886-256">唷！</span><span class="sxs-lookup"><span data-stu-id="e8886-256">Phew!</span></span>  <span data-ttu-id="e8886-257">这是很多事情，但现在在分析运行时性能的基本工作流中有坚实的基础。</span><span class="sxs-lookup"><span data-stu-id="e8886-257">That was a lot to take in, but you now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="e8886-258">干得好。</span><span class="sxs-lookup"><span data-stu-id="e8886-258">Good job.</span></span>  

### <span data-ttu-id="e8886-259">奖金：分析优化版本</span><span class="sxs-lookup"><span data-stu-id="e8886-259">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="e8886-260">使用您刚刚学习的工作流和工具，单击演示的 "**优化**" 以启用优化的代码，执行另一条性能记录，然后分析结果。</span><span class="sxs-lookup"><span data-stu-id="e8886-260">Using the workflows and tools that you just learned, click **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="e8886-261">从改进的帧数到**主**部分中的火焰图中的事件减少，你可以看到应用的优化版本的工作量很少，从而提高性能。</span><span class="sxs-lookup"><span data-stu-id="e8886-261">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you can see that the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="e8886-262">即使此 "优化" 版本也不是很好，因为它仍会操纵 `top` 每个图标的属性。</span><span class="sxs-lookup"><span data-stu-id="e8886-262">Even this "optimized" version isn't that great, because it still manipulates the `top` property of each icon.</span></span>  <span data-ttu-id="e8886-263">更好的方法是坚持仅影响合成的属性。</span><span class="sxs-lookup"><span data-stu-id="e8886-263">A better approach is to stick to properties that only affect compositing.</span></span>  
<!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## <span data-ttu-id="e8886-264">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e8886-264">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  This model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

<span data-ttu-id="e8886-265">为了更舒适地使用 "性能" 面板，最佳做法是实现完美。</span><span class="sxs-lookup"><span data-stu-id="e8886-265">To get more comfortable with the Performance panel, practice makes perfect.</span></span>  <span data-ttu-id="e8886-266">尝试分析自己的页面并分析结果。</span><span class="sxs-lookup"><span data-stu-id="e8886-266">Try profiling your own pages and analyzing the results.</span></span>  <span data-ttu-id="e8886-267">如果您对结果有任何疑问，请使用 "**反馈**" 图标，按 macOS 上的 " `Alt`  +  `Shift`  +  `I` Windows" `Option`  +  `Shift`  +  `I` 或 " [tweet][TwitterEdgeDevtools]"。</span><span class="sxs-lookup"><span data-stu-id="e8886-267">If you have any questions about your results, use the **Feedback** icon, press `Alt` + `Shift` + `I` on Windows (`Option` + `Shift` + `I` on macOS), or [tweet at us][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="e8886-268">将屏幕截图或链接添加到可重复的页面（如有可能）。</span><span class="sxs-lookup"><span data-stu-id="e8886-268">Include screenshots or links to reproducible pages, if possible.</span></span>

> ##### <span data-ttu-id="e8886-269">图 15</span><span class="sxs-lookup"><span data-stu-id="e8886-269">Figure 15</span></span>
> <span data-ttu-id="e8886-270">Microsoft Edge DevTools 中的 "**反馈**" 图标</span><span class="sxs-lookup"><span data-stu-id="e8886-270">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
> ![Microsoft Edge DevTools 中的 \* \* 反馈 \* \* 图标][ImageFeedbackIcon]

<!-- To really master runtime performance, you've got to learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="e8886-272">最后，可以通过多种方式来提高运行时性能。</span><span class="sxs-lookup"><span data-stu-id="e8886-272">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="e8886-273">本教程重点介绍一个特定的动画瓶颈，让您能够通过 "性能" 面板集中浏览，但这只是你可能遇到的一个瓶颈。</span><span class="sxs-lookup"><span data-stu-id="e8886-273">This tutorial focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

<!-- image links -->  

[ImageCaptureSettingsIcon]: /microsoft-edge/devtools-guide-chromium/media/capture-settings-icon.msft.png  
[ImageRecordIcon]: /microsoft-edge/devtools-guide-chromium/media/record-icon.msft.png  

[ImageGetStarted]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-get-started-side-by-side.msft.png "图1：左侧的演示，以及右侧的 DevTools"  
[ImageCPUThrottling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings.msft.png "图2： CPU 限制"  
[ImagePageProfiling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-profiling.msft.png "图3：分析页面"  
[ImageProfileResults]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-results.msft.png "图4：配置文件的结果"  
[ImageFPSChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-chart.msft.png "图5： FPS 图表"  
[ImageCPUSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-cpu-chart.msft.png "图6： "CPU" 图表和 "摘要" 选项卡，以蓝色列出"  
[ImageViewingScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshot-hover.msft.png "图7：在录制的2500ms 标记周围查看页面的屏幕截图"  
[ImageFrameHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frame-hover.msft.png "图8：将鼠标悬停在框架上"  
[ImageFPSMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-fps-meter-overlay.msft.png "图9： FPS 指示器"  
[ImageSummaryTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-tab.msft.png "图10： "摘要" 选项卡"  
[ImageMainSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main.msft.png "图11：主要部分"  
[ImageZoomedAnimation]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "图12：放大单个动画帧激发的事件"  
[ImageAnimationFrameFired]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-animation-frame-fired.msft.png "图13：有关动画帧激发事件的详细信息"  
[ImageForcedLayoutSRC]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-sources-app-update.msft.png "图14：导致强制布局的代码行"  
[ImageFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-feedback-icon.msft.png "图15： Microsoft Edge DevTools 中的 * * 反馈 * * 图标"

<!-- links -->

[DevtoolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "更改 Microsoft Edge DevTools 位置（"取消停靠"、"停靠到底部"、"停靠到左侧"）"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "通过 Microsoft Edge DevTools 优化网站速度"  

[TwitterEdgeDevtools]: https://twitter.com/intent/tweet?text=@EdgeDevTools "EdgeDevTools-发布 Tweet |Twitter"  

[MDNWebRequestAnimationFrame]: https://developer.mozilla.org/docs/Web/API/window/requestAnimationFrame "RequestAnimationFrame \ （\） |MDN"  

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
> <span data-ttu-id="e8886-293">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e8886-293">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e8886-294">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="e8886-294">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="e8886-296">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e8886-296">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
