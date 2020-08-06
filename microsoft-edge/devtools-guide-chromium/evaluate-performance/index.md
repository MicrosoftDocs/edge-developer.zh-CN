---
title: 即可体验分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bff2d2fb0ff8424303289183ca8c5935ef477381
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: HT
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







# <span data-ttu-id="9199f-103">即可体验分析运行时性能</span><span class="sxs-lookup"><span data-stu-id="9199f-103">Get Started With Analyzing Runtime Performance</span></span>   



> [!NOTE]
> <span data-ttu-id="9199f-104">请参阅 [优化网站速度][DevtoolsSpeedGetStarted] 了解如何提高页面的加载速度。</span><span class="sxs-lookup"><span data-stu-id="9199f-104">See [Optimize Website Speed][DevtoolsSpeedGetStarted] to learn how to make your pages load faster.</span></span>  

<span data-ttu-id="9199f-105">运行时性能是页面运行（而不是加载）时的性能。</span><span class="sxs-lookup"><span data-stu-id="9199f-105">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="9199f-106">本教程将指导你如何使用 Microsoft Edge 开发人员工具性能面板来分析运行时性能。</span><span class="sxs-lookup"><span data-stu-id="9199f-106">This tutorial teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="9199f-107">在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。</span><span class="sxs-lookup"><span data-stu-id="9199f-107">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <span data-ttu-id="9199f-108">入门</span><span class="sxs-lookup"><span data-stu-id="9199f-108">Get started</span></span>   

<span data-ttu-id="9199f-109">在本教程中，你将在实时页面上打开 DevTools，并使用 "性能" 面板查找页面上的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="9199f-109">In this tutorial, you open DevTools on a live page and use the Performance panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="9199f-110">在 **InPrivate 模式**中打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="9199f-110">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="9199f-111">InPrivate 模式可确保 Microsoft Edge 以干净的状态运行。</span><span class="sxs-lookup"><span data-stu-id="9199f-111">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="9199f-112">例如，如果安装了大量的扩展，则这些扩展可能会导致性能测量产生噪音。</span><span class="sxs-lookup"><span data-stu-id="9199f-112">For example, if you have a lot of extensions installed, those extensions might create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="9199f-113">在 InPrivate 窗口中加载以下页面。</span><span class="sxs-lookup"><span data-stu-id="9199f-113">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="9199f-114">这是你要分析的演示。</span><span class="sxs-lookup"><span data-stu-id="9199f-114">This is the demo that you're going to profile.</span></span>  <span data-ttu-id="9199f-115">该页面显示了一堆上下移动的小图标。</span><span class="sxs-lookup"><span data-stu-id="9199f-115">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/jank/
    ```  
    
1.  <span data-ttu-id="9199f-116">按 `Control`+`Shift`+`I` \(Windows\) 或 `Command`+`Option`+`I` \(macOS\) 打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="9199f-116">Press `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    > ###### <span data-ttu-id="9199f-117">图 1</span><span class="sxs-lookup"><span data-stu-id="9199f-117">Figure 1</span></span>  
    > <span data-ttu-id="9199f-118">左侧为演示，右侧为 DevTools</span><span class="sxs-lookup"><span data-stu-id="9199f-118">The demo on the left, and DevTools on the right</span></span>  
    > ![左侧为演示，右侧为 DevTools][ImageGetStarted]  
    
    > [!NOTE]
    > <span data-ttu-id="9199f-120">至于屏幕截图的其余部分，DevTools 已[停靠至一个单独的窗口][DevtoolsCustomizePlacement]，以便你可以更好地查看内容。</span><span class="sxs-lookup"><span data-stu-id="9199f-120">For the rest of the screenshots, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] so that you can see the contents better.</span></span>  
    
### <span data-ttu-id="9199f-121">模拟移动 CPU</span><span class="sxs-lookup"><span data-stu-id="9199f-121">Simulate a mobile CPU</span></span>  

<span data-ttu-id="9199f-122">与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。</span><span class="sxs-lookup"><span data-stu-id="9199f-122">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="9199f-123">每当你分析页面时，都可使用 CPU 节流来模拟页面在移动设备上的表现。</span><span class="sxs-lookup"><span data-stu-id="9199f-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="9199f-124">在 DevTools 中，单击 "**性能**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9199f-124">In DevTools, click the **Performance** tab.</span></span>  
1.  <span data-ttu-id="9199f-125">请确保已启用**屏幕截图**复选框。</span><span class="sxs-lookup"><span data-stu-id="9199f-125">Make sure that the **Screenshots** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="9199f-126">单击 "**捕获设置**" !["捕获设置"][ImageCaptureSettingsIcon]。</span><span class="sxs-lookup"><span data-stu-id="9199f-126">Click **Capture Settings** ![Capture Settings][ImageCaptureSettingsIcon].</span></span>  <span data-ttu-id="9199f-127">DevTools 显示了有关如何捕获效果指标的设置。</span><span class="sxs-lookup"><span data-stu-id="9199f-127">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="9199f-128">对于 "**CPU**"，选择 **4x 减速**。</span><span class="sxs-lookup"><span data-stu-id="9199f-128">For **CPU**, select **4x slowdown**.</span></span>  <span data-ttu-id="9199f-129">DevTools 将 CPU 限制为比平时慢 4 倍。</span><span class="sxs-lookup"><span data-stu-id="9199f-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    > ###### <span data-ttu-id="9199f-130">图 2</span><span class="sxs-lookup"><span data-stu-id="9199f-130">Figure 2</span></span>  
    > <span data-ttu-id="9199f-131">CPU 节流</span><span class="sxs-lookup"><span data-stu-id="9199f-131">CPU throttling</span></span>  
    > ![CPU 节流][ImageCPUThrottling]  
    
    > [!NOTE]
    > <span data-ttu-id="9199f-133">测试其他页面时，如果你想要确保它们在低端移动设备上都能正常工作，请将 CPU 节流设置为 **6x 减速**。</span><span class="sxs-lookup"><span data-stu-id="9199f-133">When testing other pages, if you want to ensure that they work well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="9199f-134">此演示不适用于 6x 减速，因此出于教学目的仅使用 4x 减速。</span><span class="sxs-lookup"><span data-stu-id="9199f-134">This demo doesn't work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <span data-ttu-id="9199f-135">设置演示</span><span class="sxs-lookup"><span data-stu-id="9199f-135">Set up the demo</span></span>  

<span data-ttu-id="9199f-136">很难创建适用于该网站所有读者的运行时性能演示。</span><span class="sxs-lookup"><span data-stu-id="9199f-136">It is hard to create a runtime performance demo that works consistently for all readers of this website.</span></span>  <span data-ttu-id="9199f-137">本部分允许你自定义演示，确保不管你的设置如何，你的体验与本教程中看到的屏幕截图和说明都相对一致。</span><span class="sxs-lookup"><span data-stu-id="9199f-137">This section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions you see in this tutorial, regardless of your particular setup.</span></span>

1.  <span data-ttu-id="9199f-138">继续单击 "**添加 10**"，直至蓝色图标移动速度明显比以前慢。</span><span class="sxs-lookup"><span data-stu-id="9199f-138">Keep clicking **Add 10** until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="9199f-139">在高端计算机上，可能需要大约 20 次单击。</span><span class="sxs-lookup"><span data-stu-id="9199f-139">On a high-end machine, it may take about 20 clicks.</span></span>  
1.  <span data-ttu-id="9199f-140">单击 "**优化**"。</span><span class="sxs-lookup"><span data-stu-id="9199f-140">Click **Optimize**.</span></span>  <span data-ttu-id="9199f-141">蓝色图标移动速度更快、更平稳。</span><span class="sxs-lookup"><span data-stu-id="9199f-141">The blue icons should move faster and more smoothly.</span></span>  

    > [!NOTE]
    > <span data-ttu-id="9199f-142">如果你看不到优化版本和未优化版本之间的明显差异，请尝试单击 "**减去 10**" 几次，然后重试。</span><span class="sxs-lookup"><span data-stu-id="9199f-142">If you don't see a noticeable difference between the optimized and un-optimized versions, try clicking **Subtract 10** a few times and trying again.</span></span>  
    > <span data-ttu-id="9199f-143">如果添加过多的蓝色图标，则只会使 CPU 占用最大内存，而不会看到两个版本的结果有重大差异。</span><span class="sxs-lookup"><span data-stu-id="9199f-143">If you add too many blue icons, you're just going to max out the CPU and you're not going to see a major difference in the results for the two versions.</span></span>  

1.  <span data-ttu-id="9199f-144">单击 "**取消优化**"。</span><span class="sxs-lookup"><span data-stu-id="9199f-144">Click **Un-Optimize**.</span></span>  <span data-ttu-id="9199f-145">蓝色图标的移动速度变慢，并且垃圾再次出现。</span><span class="sxs-lookup"><span data-stu-id="9199f-145">The blue icons move slower and with more jank again.</span></span>  

### <span data-ttu-id="9199f-146">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="9199f-146">Record runtime performance</span></span>   

<span data-ttu-id="9199f-147">运行优化版本的页面时，蓝色图标会移动得更快。</span><span class="sxs-lookup"><span data-stu-id="9199f-147">When you ran the optimized version of the page, the blue icons move faster.</span></span>  
<span data-ttu-id="9199f-148">为什么？</span><span class="sxs-lookup"><span data-stu-id="9199f-148">Why is that?</span></span>  <span data-ttu-id="9199f-149">两种版本都应该在相同的时间内将图标移动相同的空间。</span><span class="sxs-lookup"><span data-stu-id="9199f-149">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="9199f-150">在 "性能" 面板中进行录制，了解如何检测未优化版本中的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="9199f-150">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="9199f-151">在 "DevTools" 中，单击 "**记录**" "![录制][ImageRecordIcon]"。</span><span class="sxs-lookup"><span data-stu-id="9199f-151">In DevTools, click **Record** ![Record][ImageRecordIcon].</span></span>  
    <span data-ttu-id="9199f-152">页面运行时，DevTools 将捕获效果指标。</span><span class="sxs-lookup"><span data-stu-id="9199f-152">DevTools captures performance metrics as the page runs.</span></span>  
    
    > ###### <span data-ttu-id="9199f-153">图 3</span><span class="sxs-lookup"><span data-stu-id="9199f-153">Figure 3</span></span> 
    > <span data-ttu-id="9199f-154">分析页面</span><span class="sxs-lookup"><span data-stu-id="9199f-154">Profiling the page</span></span>  
    > ![分析页面][ImagePageProfiling]  
    
1.  <span data-ttu-id="9199f-156">稍等几秒钟。</span><span class="sxs-lookup"><span data-stu-id="9199f-156">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="9199f-157">单击**停止**。</span><span class="sxs-lookup"><span data-stu-id="9199f-157">Click **Stop**.</span></span>  <span data-ttu-id="9199f-158">DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。</span><span class="sxs-lookup"><span data-stu-id="9199f-158">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    > ###### <span data-ttu-id="9199f-159">图 4</span><span class="sxs-lookup"><span data-stu-id="9199f-159">Figure 4</span></span>  
    > <span data-ttu-id="9199f-160">配置文件的结果</span><span class="sxs-lookup"><span data-stu-id="9199f-160">The results of the profile</span></span>  
    > ![配置文件的结果][ImageProfileResults]  

<span data-ttu-id="9199f-162">哇，那是海量数据。</span><span class="sxs-lookup"><span data-stu-id="9199f-162">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="9199f-163">不用担心，你很快就会明白。</span><span class="sxs-lookup"><span data-stu-id="9199f-163">Don't worry, it'll all make more sense shortly.</span></span>  

## <span data-ttu-id="9199f-164">分析结果</span><span class="sxs-lookup"><span data-stu-id="9199f-164">Analyze the results</span></span>   

<span data-ttu-id="9199f-165">记录页面性能后，你可以衡量页面的性能有多糟糕，并找出原因。</span><span class="sxs-lookup"><span data-stu-id="9199f-165">Once you've got a recording the performance of the page, you can measure how poor the performance of the page is, and find the any causes.</span></span>  

### <span data-ttu-id="9199f-166">分析每秒帧数</span><span class="sxs-lookup"><span data-stu-id="9199f-166">Analyze frames per second</span></span>  

<span data-ttu-id="9199f-167">用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。</span><span class="sxs-lookup"><span data-stu-id="9199f-167">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="9199f-168">当动画以 60 FPS运行时，用户会觉得很享受。</span><span class="sxs-lookup"><span data-stu-id="9199f-168">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="9199f-169">查看 **FPS** 图表。</span><span class="sxs-lookup"><span data-stu-id="9199f-169">Look at the **FPS** chart.</span></span>  <span data-ttu-id="9199f-170">每当你在\*\* FPS \*\*上方看到红色条时，表示帧速率下降得太低，以至于可能损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="9199f-170">Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="9199f-171">通常，绿色条越高，FPS 越高。</span><span class="sxs-lookup"><span data-stu-id="9199f-171">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    > ###### <span data-ttu-id="9199f-172">图 5</span><span class="sxs-lookup"><span data-stu-id="9199f-172">Figure 5</span></span>  
    > <span data-ttu-id="9199f-173">FPS 图表</span><span class="sxs-lookup"><span data-stu-id="9199f-173">The FPS chart</span></span>  
    > ![FPS 图表][ImageFPSChart]  

1.  <span data-ttu-id="9199f-175">在 **FPS** 图表下方，你将看到 **CPU** 图表。</span><span class="sxs-lookup"><span data-stu-id="9199f-175">Below the **FPS** chart you see the **CPU** chart.</span></span>  <span data-ttu-id="9199f-176">**CPU** 图表中的颜色对应于 "性能" 面板底部 "**摘要**" 选项卡中的 "颜色"。</span><span class="sxs-lookup"><span data-stu-id="9199f-176">The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="9199f-177">**CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。</span><span class="sxs-lookup"><span data-stu-id="9199f-177">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="9199f-178">每当你看到 CPU 长时间处于满负荷状态时，就是提示你应该找到减少工作量的方法。</span><span class="sxs-lookup"><span data-stu-id="9199f-178">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span></span>  
    
    > ###### <span data-ttu-id="9199f-179">图 6</span><span class="sxs-lookup"><span data-stu-id="9199f-179">Figure 6</span></span>  
    > <span data-ttu-id="9199f-180">CPU 图表和摘要选项卡</span><span class="sxs-lookup"><span data-stu-id="9199f-180">The CPU chart and Summary tab</span></span>  
    > ![CPU 图表和摘要选项卡][ImageCPUSummary]  

1.  <span data-ttu-id="9199f-182">将鼠标悬停在 "**FPS**"、"**CPU**" 或 "**NET**" 图表。</span><span class="sxs-lookup"><span data-stu-id="9199f-182">Hover your mouse over the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="9199f-183">DevTools 将显示该时间点处的页面截图。</span><span class="sxs-lookup"><span data-stu-id="9199f-183">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="9199f-184">左右移动鼠标以重播录音。</span><span class="sxs-lookup"><span data-stu-id="9199f-184">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="9199f-185">这称为 "清理"，对于手动分析动画进度非常有用。</span><span class="sxs-lookup"><span data-stu-id="9199f-185">This is called scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    > ###### <span data-ttu-id="9199f-186">图 7</span><span class="sxs-lookup"><span data-stu-id="9199f-186">Figure 7</span></span>  
    > <span data-ttu-id="9199f-187">查看记录的 2500ms 左右页面的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="9199f-187">Viewing a screenshot of the page around the 2500ms mark of the recording</span></span>  
    > ![查看记录的 2500ms 左右页面的屏幕截图][ImageViewingScreenshot]  

1.  <span data-ttu-id="9199f-189">在 "**帧**" 部分中，将鼠标悬停在其中一个绿色正方形上方。</span><span class="sxs-lookup"><span data-stu-id="9199f-189">In the **Frames** section, hover your mouse over one of the green squares.</span></span>  <span data-ttu-id="9199f-190">DevTools 将显示该特定帧的 FPS。</span><span class="sxs-lookup"><span data-stu-id="9199f-190">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="9199f-191">每帧可能远低于 60 FPS的目标。</span><span class="sxs-lookup"><span data-stu-id="9199f-191">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    > ###### <span data-ttu-id="9199f-192">图 8</span><span class="sxs-lookup"><span data-stu-id="9199f-192">Figure 8</span></span>  
    > <span data-ttu-id="9199f-193">将鼠标悬停在帧上方</span><span class="sxs-lookup"><span data-stu-id="9199f-193">Hovering over a frame</span></span>  
    > ![将鼠标悬停在帧上方][ImageFrameHover]  

<span data-ttu-id="9199f-195">当然，通过此演示，很明显页面效果不佳。</span><span class="sxs-lookup"><span data-stu-id="9199f-195">Of course, with this demo, it is pretty obvious that the page is not performing well.</span></span>  <span data-ttu-id="9199f-196">但是在实际情况下，它可能不是非常明显，因此使用所有这些工具可使测量更方便。</span><span class="sxs-lookup"><span data-stu-id="9199f-196">But in real scenarios, it may not be so clear, so having all of these tools to make measurements comes in handy.</span></span>  

#### <span data-ttu-id="9199f-197">附赠：打开 FPS 计数</span><span class="sxs-lookup"><span data-stu-id="9199f-197">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="9199f-198">另一个非常方便的工具是 FPS 计数，可在页面运行时提供对 FPS 的实时估计。</span><span class="sxs-lookup"><span data-stu-id="9199f-198">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="9199f-199">按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。</span><span class="sxs-lookup"><span data-stu-id="9199f-199">Press `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the Command Menu.</span></span>  
1.  <span data-ttu-id="9199f-200">开始在 "命令" 菜单中键入 `Rendering`，然后选择 "**显示绘制**"。</span><span class="sxs-lookup"><span data-stu-id="9199f-200">Start typing `Rendering` in the Command Menu and select **Show Rendering**.</span></span>  
1.  <span data-ttu-id="9199f-201">在 "**绘制**" 选项卡上，启用 **FPS 计数**。</span><span class="sxs-lookup"><span data-stu-id="9199f-201">In the **Rendering** tab, enable **FPS Meter**.</span></span>  <span data-ttu-id="9199f-202">新的叠加层将显示在视线的右上角。</span><span class="sxs-lookup"><span data-stu-id="9199f-202">A new overlay appears in the top-right of your viewport.</span></span>  
    
    > ###### <span data-ttu-id="9199f-203">图 9</span><span class="sxs-lookup"><span data-stu-id="9199f-203">Figure 9</span></span>  
    > <span data-ttu-id="9199f-204">FPS 计数</span><span class="sxs-lookup"><span data-stu-id="9199f-204">The FPS meter</span></span>  
    > ![FPS 计数][ImageFPSMeter]  

1.  <span data-ttu-id="9199f-206">禁用 **FPS 计数** 然后按 `Escape` 关闭 **绘制** 选项卡。 在本教程中，你不会用到它。</span><span class="sxs-lookup"><span data-stu-id="9199f-206">Disable the **FPS Meter** and press `Escape` to close the **Rendering** tab.  You won't be using it in this tutorial.</span></span>  

### <span data-ttu-id="9199f-207">查找瓶颈</span><span class="sxs-lookup"><span data-stu-id="9199f-207">Find the bottleneck</span></span>  

<span data-ttu-id="9199f-208">现在，您已经测量并验证了动画效果不佳，接下来要回答的问题是：为什么？</span><span class="sxs-lookup"><span data-stu-id="9199f-208">Now that you've measured and verified that the animation is not performing well, the next question to answer is:  why?</span></span>  

1.  <span data-ttu-id="9199f-209">注意 "摘要" 选项卡。 未选中任何事件时，此选项卡显示活动的细目。</span><span class="sxs-lookup"><span data-stu-id="9199f-209">Note the summary tab.  When no events are selected, this tab shows you a breakdown of activity.</span></span>  <span data-ttu-id="9199f-210">该页面花费了大部分时间进行绘制。</span><span class="sxs-lookup"><span data-stu-id="9199f-210">The page spent most of its time rendering.</span></span>  <span data-ttu-id="9199f-211">由于性能是减少工作量的艺术，因此你的目标是减少花费在进行绘制工作上的时间。</span><span class="sxs-lookup"><span data-stu-id="9199f-211">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    > ###### <span data-ttu-id="9199f-212">图 10</span><span class="sxs-lookup"><span data-stu-id="9199f-212">Figure 10</span></span>  
    > <span data-ttu-id="9199f-213">"摘要" 选项卡</span><span class="sxs-lookup"><span data-stu-id="9199f-213">The Summary tab</span></span>  
    > !["摘要" 选项卡][ImageSummaryTab]  

1.  <span data-ttu-id="9199f-215">展开**重点**部分。</span><span class="sxs-lookup"><span data-stu-id="9199f-215">Expand the **Main** section.</span></span>  <span data-ttu-id="9199f-216">DevTools 将显示一段时间内主线程上活动的帧图表。</span><span class="sxs-lookup"><span data-stu-id="9199f-216">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="9199f-217">x 轴表示一段时间内的记录。</span><span class="sxs-lookup"><span data-stu-id="9199f-217">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="9199f-218">每个条形表示一个事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-218">Each bar represents an event.</span></span>  <span data-ttu-id="9199f-219">宽条表示该事件花费了更长的时间。</span><span class="sxs-lookup"><span data-stu-id="9199f-219">A wider bar means that event took longer.</span></span>  <span data-ttu-id="9199f-220">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="9199f-220">The y-axis represents the call stack.</span></span>  <span data-ttu-id="9199f-221">当你看到事件相互叠加时，表示较高的事件导致较低的事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-221">When you see events stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    > ##### <span data-ttu-id="9199f-222">图 11</span><span class="sxs-lookup"><span data-stu-id="9199f-222">Figure 11</span></span>  
    > <span data-ttu-id="9199f-223">主要部分</span><span class="sxs-lookup"><span data-stu-id="9199f-223">The Main section</span></span>  
    > ![主要部分][ImageMainSection]  

1.  <span data-ttu-id="9199f-225">记录中有很多数据。</span><span class="sxs-lookup"><span data-stu-id="9199f-225">There is a lot of data in the recording.</span></span>  <span data-ttu-id="9199f-226">通过单击、按住并在**概览**上拖动鼠标来放大单个事件，该部分包括\*\* FPS **、** CPU **和** NET \*\*图表。</span><span class="sxs-lookup"><span data-stu-id="9199f-226">Zoom in on a single event by clicking, holding, and dragging your mouse over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="9199f-227">"**重点**" 部分和 "**摘要**" 选项卡仅显示录制所选部分的信息。</span><span class="sxs-lookup"><span data-stu-id="9199f-227">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span></span>  
    
    > ###### <span data-ttu-id="9199f-228">图 12</span><span class="sxs-lookup"><span data-stu-id="9199f-228">Figure 12</span></span>  
    > <span data-ttu-id="9199f-229">放大了单个事件</span><span class="sxs-lookup"><span data-stu-id="9199f-229">Zoomed in on a single event</span></span>  
    > ![放大事件][ImageZoomedAnimation]  
    
    > [!NOTE]
    > <span data-ttu-id="9199f-231">缩放的另一种方法是单击**重点**部分的背景或选择一个事件以专注于该部分，然后按`W`、`A`、`S` 和 `D`键。</span><span class="sxs-lookup"><span data-stu-id="9199f-231">Another way to zoom is to focus the **Main** section by clicking its background or selecting an event, and then press the `W`, `A`, `S`, and `D` keys.</span></span>  
    
    1.  <span data-ttu-id="9199f-232">请注意**动画帧触发**事件右上角的红色三角形。</span><span class="sxs-lookup"><span data-stu-id="9199f-232">Note the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="9199f-233">每当你看到红色三角形时，即警告你可能存在与此事件相关的问题。</span><span class="sxs-lookup"><span data-stu-id="9199f-233">Whenever you see a red triangle, it is a warning that there may be an issue related to this event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="9199f-234">每当运行[ `requestAnimationFrame()`回调][MDNWebRequestAnimationFrame]时，就会发生**动画帧触发**事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-234">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="9199f-235">单击**动画帧触发**事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-235">Click the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="9199f-236">"**摘要**" 选项卡现在向你显示有关该事件的信息。</span><span class="sxs-lookup"><span data-stu-id="9199f-236">The **Summary** tab now shows you information about that event.</span></span>  <span data-ttu-id="9199f-237">请注意 "**显示**" 链接。</span><span class="sxs-lookup"><span data-stu-id="9199f-237">Note the **Reveal** link.</span></span>  <span data-ttu-id="9199f-238">单击将使 DevTools 突出显示启动**动画帧触发**事件的事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-238">Clicking that causes DevTools to highlight the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="9199f-239">另请注意 **app.js:95** 链接。</span><span class="sxs-lookup"><span data-stu-id="9199f-239">Also note the **app.js:95** link.</span></span>  <span data-ttu-id="9199f-240">单击可跳至源代码中的相关行。</span><span class="sxs-lookup"><span data-stu-id="9199f-240">Clicking that jumps you to the relevant line in the source code.</span></span>
    
    > ##### <span data-ttu-id="9199f-241">图 13</span><span class="sxs-lookup"><span data-stu-id="9199f-241">Figure 13</span></span>  
    > <span data-ttu-id="9199f-242">有关动画帧触发事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="9199f-242">More information about the Animation Frame Fired event</span></span>  
    > ![有关动画帧触发事件的详细信息][ImageAnimationFrameFired]  
    
    > [!NOTE]
    > <span data-ttu-id="9199f-244">选择事件后，使用箭头键选择其旁边的事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-244">After selecting an event, use the arrow keys to select the events next to it.</span></span>  

1.  <span data-ttu-id="9199f-245">在 **app.update** 事件下，有一堆紫色事件。</span><span class="sxs-lookup"><span data-stu-id="9199f-245">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="9199f-246">如果它们更宽，则似乎每个事件上可能都有一个红色三角形。</span><span class="sxs-lookup"><span data-stu-id="9199f-246">If they were wider, it looks as though each one might have a red triangle on it.</span></span>  <span data-ttu-id="9199f-247">立即单击紫色"**布局**"事件之一。</span><span class="sxs-lookup"><span data-stu-id="9199f-247">Click one of the purple **Layout** events now.</span></span>  <span data-ttu-id="9199f-248">DevTools 在**摘要**选项卡中提供有关事件的更多信息。确实，有关于强制回流\（换句话说，就是布局\）的警告。</span><span class="sxs-lookup"><span data-stu-id="9199f-248">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  

1.  <span data-ttu-id="9199f-249">在 "**摘要**" 选项卡中，单击 "**强制布局**" 下的 "**app.js:71**" 链接。</span><span class="sxs-lookup"><span data-stu-id="9199f-249">In the **Summary** tab, click the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="9199f-250">DevTools 将转到强制布局的代码行。</span><span class="sxs-lookup"><span data-stu-id="9199f-250">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    > ##### <span data-ttu-id="9199f-251">图 14</span><span class="sxs-lookup"><span data-stu-id="9199f-251">Figure 14</span></span>  
    > <span data-ttu-id="9199f-252">导致强制布局的代码行</span><span class="sxs-lookup"><span data-stu-id="9199f-252">The line of code that caused the forced layout</span></span>  
    > ![导致强制布局的代码行][ImageForcedLayoutSRC]  
    
    > [!NOTE]
    > <span data-ttu-id="9199f-254">此代码的问题是，在每个动画帧中，它将更改每个图标的样式，然后查询页面上每个图标的位置。</span><span class="sxs-lookup"><span data-stu-id="9199f-254">The problem with this code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="9199f-255">因为样式已更改，浏览器不知道每个图标位置是否已更改，因此必须重新布局图标才能计算其位置。</span><span class="sxs-lookup"><span data-stu-id="9199f-255">Because the styles changed, the browser doesn't know if each icon position changed, so it has to re-layout the icon in order to compute its position.</span></span>  <!--  See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->

<!-- todo: add layouts section when available -->

<span data-ttu-id="9199f-256">哎呀！</span><span class="sxs-lookup"><span data-stu-id="9199f-256">Phew!</span></span>  <span data-ttu-id="9199f-257">这项工作非常繁琐，但是现在你已经在基本工作流程中为分析运行时性能奠定了坚实的基础。</span><span class="sxs-lookup"><span data-stu-id="9199f-257">That was a lot to take in, but you now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="9199f-258">太棒了。</span><span class="sxs-lookup"><span data-stu-id="9199f-258">Good job.</span></span>  

### <span data-ttu-id="9199f-259">附赠：分析优化的版本</span><span class="sxs-lookup"><span data-stu-id="9199f-259">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="9199f-260">使用刚刚学习的工作流程和工具，单击演示上的**优化**以启用优化的代码，进行另一次性能记录，然后分析结果。</span><span class="sxs-lookup"><span data-stu-id="9199f-260">Using the workflows and tools that you just learned, click **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="9199f-261">在**重点**部分的帧图表中，从提高的帧速率到事件的减少，你可以看到该应用程序的优化版本所做的工作少得多，从而提高了性能。</span><span class="sxs-lookup"><span data-stu-id="9199f-261">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you can see that the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="9199f-262">即使这个“优化”版本也不是那么好，因为它仍然可以操纵每个图标的`top`属性。</span><span class="sxs-lookup"><span data-stu-id="9199f-262">Even this "optimized" version isn't that great, because it still manipulates the `top` property of each icon.</span></span>  <span data-ttu-id="9199f-263">更好的方法是保留仅影响合成的属性。</span><span class="sxs-lookup"><span data-stu-id="9199f-263">A better approach is to stick to properties that only affect compositing.</span></span>  
<!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## <span data-ttu-id="9199f-264">后续步骤</span><span class="sxs-lookup"><span data-stu-id="9199f-264">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  This model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

<span data-ttu-id="9199f-265">若要更轻松地使用 "性能" 面板，请多多操练，所谓熟能生巧。</span><span class="sxs-lookup"><span data-stu-id="9199f-265">To get more comfortable with the Performance panel, practice makes perfect.</span></span>  <span data-ttu-id="9199f-266">尝试分析自己的页面并分析结果。</span><span class="sxs-lookup"><span data-stu-id="9199f-266">Try profiling your own pages and analyzing the results.</span></span>  <span data-ttu-id="9199f-267">如果你对结果有任何疑问，请使用**反馈**图标，在 Windows 上按 `Alt` + `Shift` + `I`（macOS 上按 `Option` + `Shift` + `I`），或[向我们发送推文][TwitterEdgeDevtools]。</span><span class="sxs-lookup"><span data-stu-id="9199f-267">If you have any questions about your results, use the **Feedback** icon, press `Alt` + `Shift` + `I` on Windows (`Option` + `Shift` + `I` on macOS), or [tweet at us][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="9199f-268">如果可能，请包括屏幕截图或指向可重现页面的链接。</span><span class="sxs-lookup"><span data-stu-id="9199f-268">Include screenshots or links to reproducible pages, if possible.</span></span>

> ##### <span data-ttu-id="9199f-269">图 15</span><span class="sxs-lookup"><span data-stu-id="9199f-269">Figure 15</span></span>
> <span data-ttu-id="9199f-270">Microsoft Edge 开发人员工具中的 **反馈** 图标</span><span class="sxs-lookup"><span data-stu-id="9199f-270">The **Feedback** icon in the Microsoft Edge DevTools</span></span>  
> ![Microsoft Edge 开发人员工具中的**反馈**图标][ImageFeedbackIcon]

<!-- To really master runtime performance, you've got to learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="9199f-272">最后，可通过多种方法来改善运行时性能。</span><span class="sxs-lookup"><span data-stu-id="9199f-272">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="9199f-273">本教程重点介绍了一个特定的动画瓶颈，使你重点关注“性能”面板，但这只是你可能遇到的许多瓶颈之一。</span><span class="sxs-lookup"><span data-stu-id="9199f-273">This tutorial focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

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

[ImageGetStarted]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-get-started-side-by-side.msft.png "图 1：左侧为演示，右侧为 DevTools"  
[ImageCPUThrottling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-settings.msft.png "图 2：CPU 节流"  
[ImagePageProfiling]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-profiling.msft.png "图 3：分析页面"  
[ImageProfileResults]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-capture-results.msft.png "图 4：配置文件的结果"  
[ImageFPSChart]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-fps-chart.msft.png "图 5：FPS 图表"  
[ImageCPUSummary]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-cpu-chart.msft.png "图 6：CPU "图表" 和 "摘要" 选项卡，用蓝色勾勒出"  
[ImageViewingScreenshot]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-screenshot-hover.msft.png "图 7：查看记录的 2500ms 左右页面的屏幕截图"  
[ImageFrameHover]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-frame-hover.msft.png "图 8：将鼠标悬停在帧上方"  
[ImageFPSMeter]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-fps-meter-overlay.msft.png "图 9：FPS 计数"  
[ImageSummaryTab]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-summary-tab.msft.png "图 10："摘要" 选项卡"  
[ImageMainSection]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main.msft.png "图 11：“重点”部分"  
[ImageZoomedAnimation]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-main-zoomed.msft.png "图 12：放大单个动画帧触发事件"  
[ImageAnimationFrameFired]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-performance-animation-frame-fired.msft.png "图 13：有关动画帧触发事件的详细信息"  
[ImageForcedLayoutSRC]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-sources-app-update.msft.png "图 14：导致强制布局的代码行"  
[ImageFeedbackIcon]: /microsoft-edge/devtools-guide-chromium/media/evaluate-performance-feedback-icon.msft.png "图 15：Microsoft Edge 开发人员工具中的**反馈**图标"

<!-- links -->

[ DevtoolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）"   
[DevtoolsCustomizePlacement]: /microsoft-edge/devtools-guide-chromium/customize/placement "Change Microsoft Edge DevTools Placement (Undock, Dock To Bottom, Dock To Left)"  
[DevtoolsSpeedGetStarted]: /microsoft-edge/devtools-guide-chromium/speed/get-started "使用 Microsoft Edge 开发人员工具优化网站速度"  

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
> <span data-ttu-id="9199f-293">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9199f-293">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9199f-294">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9199f-294">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9199f-296">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9199f-296">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
