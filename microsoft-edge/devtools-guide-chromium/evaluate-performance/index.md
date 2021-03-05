---
description: 了解如何在 Microsoft Edge DevTools 中评估运行时性能。
title: 即可体验分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 7cb1d8f073cdb8a43093514dd7dea86d72102011
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11124983"
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

# <span data-ttu-id="52ae8-104">即可体验分析运行时性能</span><span class="sxs-lookup"><span data-stu-id="52ae8-104">Get started with analyzing Runtime performance</span></span>  

> [!NOTE]
> <span data-ttu-id="52ae8-105">要了解如何使网页加载速度更快，请浏览[优化网站速度][DevtoolsSpeedGetStarted]。</span><span class="sxs-lookup"><span data-stu-id="52ae8-105">To learn how to make your pages load faster, navigate to [Optimize Website Speed][DevtoolsSpeedGetStarted].</span></span>  

<span data-ttu-id="52ae8-106">运行时性能是页面运行（而不是加载）时的性能。</span><span class="sxs-lookup"><span data-stu-id="52ae8-106">Runtime performance is how your page performs when it is running, as opposed to loading.</span></span>  <span data-ttu-id="52ae8-107">下面的教程文章教导如何使用Microsoft Edge DevTools性能面板来分析运行时性能。</span><span class="sxs-lookup"><span data-stu-id="52ae8-107">The following tutorial article teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.</span></span>  <span data-ttu-id="52ae8-108">在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。</span><span class="sxs-lookup"><span data-stu-id="52ae8-108">In terms of the **RAIL** model, the skills you learn in this tutorial are useful for analyzing the Response, Animation, and Idle phases of your page.</span></span>  

<!--todo: add rail link when section is ready -->  

## <span data-ttu-id="52ae8-109">入门</span><span class="sxs-lookup"><span data-stu-id="52ae8-109">Get started</span></span>  

<span data-ttu-id="52ae8-110">在下面的教程中，在一个实时页面上打开DevTools，并使用**性能**面板来查找页面上的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="52ae8-110">In the following tutorial, you open DevTools on a live page and use the **Performance** panel to find a performance bottleneck on the page.</span></span>  

1.  <span data-ttu-id="52ae8-111">在 **InPrivate 模式**中打开 Microsoft Edge。</span><span class="sxs-lookup"><span data-stu-id="52ae8-111">Open Microsoft Edge in **InPrivate Mode**.</span></span>  <span data-ttu-id="52ae8-112">InPrivate 模式可确保 Microsoft Edge 以干净的状态运行。</span><span class="sxs-lookup"><span data-stu-id="52ae8-112">InPrivate Mode ensures that Microsoft Edge runs in a clean state.</span></span>  <span data-ttu-id="52ae8-113">例如，如果安装了大量扩展，则扩展可能会在性能测量中产生噪音。</span><span class="sxs-lookup"><span data-stu-id="52ae8-113">For example, if you have a lot of extensions installed, the extensions may create noise in your performance measurements.</span></span>  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  <span data-ttu-id="52ae8-114">在 InPrivate 窗口中加载以下页面。</span><span class="sxs-lookup"><span data-stu-id="52ae8-114">Load the following page in your InPrivate window.</span></span>  <span data-ttu-id="52ae8-115">这个页面就是所要介绍的演示。</span><span class="sxs-lookup"><span data-stu-id="52ae8-115">The page is the demo that you are going to profile.</span></span>  <span data-ttu-id="52ae8-116">该页面显示了一堆上下移动的小图标。</span><span class="sxs-lookup"><span data-stu-id="52ae8-116">The page shows a bunch of little icons moving up and down.</span></span>  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  <span data-ttu-id="52ae8-117">选择`Control`+`Shift`+`I` \（Windows，Linux\）或`Command`+`Option`+`I` \（macOS\）以打开 DevTools。</span><span class="sxs-lookup"><span data-stu-id="52ae8-117">Select `Control`+`Shift`+`I` \(Windows, Linux\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左侧为演示，右侧为 DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       <span data-ttu-id="52ae8-119">左侧为演示，右侧为 DevTools</span><span class="sxs-lookup"><span data-stu-id="52ae8-119">The demo on the left, and DevTools on the right</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-120">对于数据的其余部分，DevTools [解锁到一个单独的窗口][DevtoolsCustomizePlacement]以便更加关注于内容。</span><span class="sxs-lookup"><span data-stu-id="52ae8-120">For the rest of the figures, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] to better focus on the contents.</span></span>  
    
### <span data-ttu-id="52ae8-121">模拟移动 CPU</span><span class="sxs-lookup"><span data-stu-id="52ae8-121">Simulate a mobile CPU</span></span>  

<span data-ttu-id="52ae8-122">与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。</span><span class="sxs-lookup"><span data-stu-id="52ae8-122">Mobile devices have much less CPU power than desktops and laptops.</span></span>  <span data-ttu-id="52ae8-123">每当你分析页面时，都可使用 CPU 节流来模拟页面在移动设备上的表现。</span><span class="sxs-lookup"><span data-stu-id="52ae8-123">Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.</span></span>  

1.  <span data-ttu-id="52ae8-124">在 DevTools 中，选择“**性能**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="52ae8-124">In DevTools, choose the **Performance** tab.</span></span>  
1.  <span data-ttu-id="52ae8-125">请确保已启用**屏幕截图**复选框。</span><span class="sxs-lookup"><span data-stu-id="52ae8-125">Make sure that the **Screenshots** checkbox is enabled.</span></span>  
1.  <span data-ttu-id="52ae8-126">选择**捕获设置**  \(![捕获设置][ImageCaptureSettingsIcon]\)。</span><span class="sxs-lookup"><span data-stu-id="52ae8-126">Choose **Capture Settings** \(![Capture Settings][ImageCaptureSettingsIcon]\).</span></span>  <span data-ttu-id="52ae8-127">DevTools 显示了有关如何捕获效果指标的设置。</span><span class="sxs-lookup"><span data-stu-id="52ae8-127">DevTools reveals settings related to how it captures performance metrics.</span></span>  
1.  <span data-ttu-id="52ae8-128">对于**CPU**，请选择**4倍减速**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-128">For **CPU**, choose **4x slowdown**.</span></span>  <span data-ttu-id="52ae8-129">DevTools 将 CPU 限制为比平时慢 4 倍。</span><span class="sxs-lookup"><span data-stu-id="52ae8-129">DevTools throttles your CPU so that it is 4 times slower than usual.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU 限制" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       <span data-ttu-id="52ae8-131">CPU 限制</span><span class="sxs-lookup"><span data-stu-id="52ae8-131">CPU throttle</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-132">在测试其他页面时；如果想确保每个页面在低端移动设备上都能很好的运行，将CPU限制设置为**6倍减速**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-132">When testing other pages; if you want to ensure that each page works well on low-end mobile devices, set CPU Throttling to **6x slowdown**.</span></span>  <span data-ttu-id="52ae8-133">演示在6倍减速下效果不好，所以只用4倍减速进行教学。</span><span class="sxs-lookup"><span data-stu-id="52ae8-133">The demo does not work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.</span></span>  
    
### <span data-ttu-id="52ae8-134">设置演示</span><span class="sxs-lookup"><span data-stu-id="52ae8-134">Set up the demo</span></span>  

<span data-ttu-id="52ae8-135">很难创建一个对所有网站读者都能稳定运行的性能演示。</span><span class="sxs-lookup"><span data-stu-id="52ae8-135">It is hard to create a runtime performance demo that works consistently for all readers of the website.</span></span>  <span data-ttu-id="52ae8-136">以下部分可以自定义演示，以确保无论特定设置如何，体验与截图和描述都相对一致。</span><span class="sxs-lookup"><span data-stu-id="52ae8-136">The following section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions, regardless of your particular set up.</span></span>

1.  <span data-ttu-id="52ae8-137">选择“**添加 10**”按钮，直到蓝色图标移动速度明显比之前慢。</span><span class="sxs-lookup"><span data-stu-id="52ae8-137">Choose the **Add 10** button until the blue icons move noticeably slower than before.</span></span>  <span data-ttu-id="52ae8-138">在高端计算机上，可能需要选择它大约 20 次。</span><span class="sxs-lookup"><span data-stu-id="52ae8-138">On a high-end machine, you may to choose it about 20 times.</span></span>  
1.  <span data-ttu-id="52ae8-139">选择 **优化**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-139">Choose **Optimize**.</span></span>  <span data-ttu-id="52ae8-140">蓝色图标移动速度更快、更平稳。</span><span class="sxs-lookup"><span data-stu-id="52ae8-140">The blue icons should move faster and more smoothly.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-141">如果要更好地显示优化版本与未优化版本之间的差异，请选择几次**减去 10**按钮，然后重试。</span><span class="sxs-lookup"><span data-stu-id="52ae8-141">To better display a difference between the optimized and un-optimized versions, choose the **Subtract 10** button a few times and try again.</span></span>  
    > <span data-ttu-id="52ae8-142">如果添加太多的蓝色图标，可能会最大限度地使用CPU，然后可能就不会观察到两个版本的结果有很大的差异。</span><span class="sxs-lookup"><span data-stu-id="52ae8-142">If you add too many blue icons, you may max out the CPU and then you may not observe a major difference in the results for the two versions.</span></span>  
    
1.  <span data-ttu-id="52ae8-143">选择 **取消优化**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-143">Choose **Un-Optimize**.</span></span>  <span data-ttu-id="52ae8-144">蓝色图标移动速度变慢，而且又更加迟钝。</span><span class="sxs-lookup"><span data-stu-id="52ae8-144">The blue icons move slower and with more sluggishness again.</span></span>  
    
### <span data-ttu-id="52ae8-145">记录运行时性能</span><span class="sxs-lookup"><span data-stu-id="52ae8-145">Record runtime performance</span></span>  

<span data-ttu-id="52ae8-146">运行优化版本的页面时，蓝色图标会移动得更快。</span><span class="sxs-lookup"><span data-stu-id="52ae8-146">When you ran the optimized version of the page, the blue icons move faster.</span></span>  <span data-ttu-id="52ae8-147">为什么？</span><span class="sxs-lookup"><span data-stu-id="52ae8-147">Why is that?</span></span>  <span data-ttu-id="52ae8-148">两种版本都应该在相同的时间内将图标移动相同的空间。</span><span class="sxs-lookup"><span data-stu-id="52ae8-148">Both versions are supposed to move the icons the same amount of space in the same amount of time.</span></span>  <span data-ttu-id="52ae8-149">在 "性能" 面板中进行录制，了解如何检测未优化版本中的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="52ae8-149">Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.</span></span>  

1.  <span data-ttu-id="52ae8-150">在 DevTools 中， 选择**记录** \(![记录][ImageRecordIcon]\)。</span><span class="sxs-lookup"><span data-stu-id="52ae8-150">In DevTools, choose **Record** \(![Record][ImageRecordIcon]\).</span></span>  <span data-ttu-id="52ae8-151">页面运行时，DevTools 将捕获效果指标。</span><span class="sxs-lookup"><span data-stu-id="52ae8-151">DevTools captures performance metrics as the page runs.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="配置文件页面" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       <span data-ttu-id="52ae8-153">配置文件页面</span><span class="sxs-lookup"><span data-stu-id="52ae8-153">Profile the page</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52ae8-154">稍等几秒钟。</span><span class="sxs-lookup"><span data-stu-id="52ae8-154">Wait a few seconds.</span></span>  
1.  <span data-ttu-id="52ae8-155">选择**停止**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-155">Choose **Stop**.</span></span>  <span data-ttu-id="52ae8-156">DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。</span><span class="sxs-lookup"><span data-stu-id="52ae8-156">DevTools stops recording, processes the data, then displays the results on the Performance panel.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="配置文件的结果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       <span data-ttu-id="52ae8-158">配置文件的结果</span><span class="sxs-lookup"><span data-stu-id="52ae8-158">The results of the profile</span></span>  
    :::image-end:::  
    
<span data-ttu-id="52ae8-159">哇，那是海量数据。</span><span class="sxs-lookup"><span data-stu-id="52ae8-159">Wow, that is an overwhelming amount of data.</span></span>  <span data-ttu-id="52ae8-160">请不要担心，很快此过程就会变得更有意义。</span><span class="sxs-lookup"><span data-stu-id="52ae8-160">do not worry, soon the process makes more sense.</span></span>  

## <span data-ttu-id="52ae8-161">分析结果</span><span class="sxs-lookup"><span data-stu-id="52ae8-161">Analyze the results</span></span>  

<span data-ttu-id="52ae8-162">在记录页面性能后，测量页面的性能质量，并找到任何相关原因。</span><span class="sxs-lookup"><span data-stu-id="52ae8-162">After you record the performance of the page, measure the quality of the performance of the page and find the any causes.</span></span>  

### <span data-ttu-id="52ae8-163">分析每秒帧数</span><span class="sxs-lookup"><span data-stu-id="52ae8-163">Analyze frames per second</span></span>  

<span data-ttu-id="52ae8-164">用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。</span><span class="sxs-lookup"><span data-stu-id="52ae8-164">The main metric for measuring the performance of any animation is frames per second \(FPS\).</span></span>  <span data-ttu-id="52ae8-165">当动画以 60 FPS运行时，用户会觉得很享受。</span><span class="sxs-lookup"><span data-stu-id="52ae8-165">Users are happy when animations run at 60 FPS.</span></span>  

1.  <span data-ttu-id="52ae8-166">查看 **FPS** 图表。</span><span class="sxs-lookup"><span data-stu-id="52ae8-166">Look at the **FPS** chart.</span></span>  <span data-ttu-id="52ae8-167">每当你在\*\* FPS \*\*上方看到红色条时，表示帧速率下降得太低，以至于可能损害用户体验。</span><span class="sxs-lookup"><span data-stu-id="52ae8-167">Whenever you see a red bar above **FPS**, it means that the framerate dropped so low that it is probably harming the user experience.</span></span>  <span data-ttu-id="52ae8-168">通常，绿色条越高，FPS 越高。</span><span class="sxs-lookup"><span data-stu-id="52ae8-168">In general, the higher the green bar, the higher the FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       <span data-ttu-id="52ae8-170">**FPS** 图表</span><span class="sxs-lookup"><span data-stu-id="52ae8-170">The **FPS** chart</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52ae8-171">在 **FPS** 图表下方，你将看到 **CPU** 图表。</span><span class="sxs-lookup"><span data-stu-id="52ae8-171">Below the **FPS** chart you see the **CPU** chart.</span></span>  <span data-ttu-id="52ae8-172">**CPU** 图表中的颜色对应于 "性能" 面板底部 "**摘要**" 选项卡中的 "颜色"。</span><span class="sxs-lookup"><span data-stu-id="52ae8-172">The colors in the **CPU** chart correspond to the colors in the **Summary** tab, at the bottom of the Performance panel.</span></span>  <span data-ttu-id="52ae8-173">**CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。</span><span class="sxs-lookup"><span data-stu-id="52ae8-173">The fact that the **CPU** chart is full of color means that the CPU was maxed out during the recording.</span></span>  <span data-ttu-id="52ae8-174">每当你看到 CPU 长时间处于满负荷状态时，就是提示你应该找到减少工作量的方法。</span><span class="sxs-lookup"><span data-stu-id="52ae8-174">Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="CPU 图表和摘要选项卡" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       <span data-ttu-id="52ae8-176">**CPU**图表和**摘要**选项卡</span><span class="sxs-lookup"><span data-stu-id="52ae8-176">The **CPU** chart and **Summary** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52ae8-177">鼠标悬停在 **FPS**、 **CPU**或**NET** 图表上。</span><span class="sxs-lookup"><span data-stu-id="52ae8-177">Hover on the **FPS**, **CPU**, or **NET** charts.</span></span>  <span data-ttu-id="52ae8-178">DevTools 将显示该时间点处的页面截图。</span><span class="sxs-lookup"><span data-stu-id="52ae8-178">DevTools shows a screenshot of the page at that point in time.</span></span>  <span data-ttu-id="52ae8-179">左右移动鼠标以重播录音。</span><span class="sxs-lookup"><span data-stu-id="52ae8-179">Move your mouse left and right to replay the recording.</span></span>  <span data-ttu-id="52ae8-180">引用该操作为擦除，它对于手动分析动画的进程很有用。</span><span class="sxs-lookup"><span data-stu-id="52ae8-180">The action is referenced as scrubbing, and it is useful for manually analyzing the progression of animations.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="查看2500ms左右的录制页面截图" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       <span data-ttu-id="52ae8-182">查看2500ms左右的录制页面截图</span><span class="sxs-lookup"><span data-stu-id="52ae8-182">View a screenshot of the page around the 2500ms mark of the recording</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52ae8-183">在“**框架**”部分，将鼠标悬停在其中一个绿色方块上。</span><span class="sxs-lookup"><span data-stu-id="52ae8-183">In the **Frames** section, hover on one of the green squares.</span></span>  <span data-ttu-id="52ae8-184">DevTools 将显示该特定帧的 FPS。</span><span class="sxs-lookup"><span data-stu-id="52ae8-184">DevTools shows you the FPS for that particular frame.</span></span>  <span data-ttu-id="52ae8-185">每帧可能远低于 60 FPS的目标。</span><span class="sxs-lookup"><span data-stu-id="52ae8-185">Each frame is probably well below the target of 60 FPS.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       <span data-ttu-id="52ae8-187">鼠标悬停在框架上</span><span class="sxs-lookup"><span data-stu-id="52ae8-187">Hover on a frame</span></span>  
    :::image-end:::  
    
<span data-ttu-id="52ae8-188">当然，应看到页面性能不佳。</span><span class="sxs-lookup"><span data-stu-id="52ae8-188">Of course, you should see that the page is not performing well.</span></span>  <span data-ttu-id="52ae8-189">但是在实际场景中可能就不是那么清楚了，所以掌握所有的工具进行测量就会方便很多。</span><span class="sxs-lookup"><span data-stu-id="52ae8-189">But in real scenarios, it may not be so clear, so having all of the tools to make measurements comes in handy.</span></span>  

#### <span data-ttu-id="52ae8-190">附赠：打开 FPS 计数</span><span class="sxs-lookup"><span data-stu-id="52ae8-190">Bonus: Open the FPS meter</span></span>  

<span data-ttu-id="52ae8-191">另一个非常方便的工具是 FPS 计数，可在页面运行时提供对 FPS 的实时估计。</span><span class="sxs-lookup"><span data-stu-id="52ae8-191">Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.</span></span>  

1.  <span data-ttu-id="52ae8-192">选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-192">Select `Control`+`Shift`+`P` \(Windows, Linux\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.</span></span>  
1.  <span data-ttu-id="52ae8-193">在**命令菜单**中开始键入`Rendering`，然后选择**显示渲染**.</span><span class="sxs-lookup"><span data-stu-id="52ae8-193">Start typing `Rendering` in the **Command Menu** and choose **Show Rendering**.</span></span>  
1.  <span data-ttu-id="52ae8-194">在 "**绘制**" 选项卡上，启用 **FPS 计数**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-194">In the **Rendering** tab, enable **FPS Meter**.</span></span>  <span data-ttu-id="52ae8-195">新的叠加层将显示在视线的右上角。</span><span class="sxs-lookup"><span data-stu-id="52ae8-195">A new overlay appears in the top-right of your viewport.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       <span data-ttu-id="52ae8-197">**FPS 计数**</span><span class="sxs-lookup"><span data-stu-id="52ae8-197">The **FPS meter**</span></span>  
        :::image-end:::  
    
1.  <span data-ttu-id="52ae8-198">禁用 **FPS 计数器**，然后选择 `Escape` 以关闭 “**渲染**”选项卡。本教程中未使用 **FPS计数器**。</span><span class="sxs-lookup"><span data-stu-id="52ae8-198">Disable the **FPS Meter** and select `Escape` to close the **Rendering** tab.  You are not using **FPS Meter** in this tutorial.</span></span>  
    
### <span data-ttu-id="52ae8-199">查找瓶颈</span><span class="sxs-lookup"><span data-stu-id="52ae8-199">Find the bottleneck</span></span>  

<span data-ttu-id="52ae8-200">当测量并验证动画表现不佳之后，下一步就是要回答“为什么？”的问题。</span><span class="sxs-lookup"><span data-stu-id="52ae8-200">After you measured and verified that the animation is not performing well, the next step is to answer the question "why?".</span></span>  

1.  <span data-ttu-id="52ae8-201">当没有选择事件时，“**摘要**”选项卡会显示活动的分类。</span><span class="sxs-lookup"><span data-stu-id="52ae8-201">When no events are selected, the **Summary** tab shows you a breakdown of activity.</span></span>  <span data-ttu-id="52ae8-202">页面大部分时间都在渲染。</span><span class="sxs-lookup"><span data-stu-id="52ae8-202">The page spent most of the time rendering.</span></span>  <span data-ttu-id="52ae8-203">由于性能是减少工作量的艺术，因此你的目标是减少花费在进行绘制工作上的时间。</span><span class="sxs-lookup"><span data-stu-id="52ae8-203">Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="摘要 选项卡" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       <span data-ttu-id="52ae8-205">**摘要** 选项卡</span><span class="sxs-lookup"><span data-stu-id="52ae8-205">The **Summary** tab</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52ae8-206">展开**重点**部分。</span><span class="sxs-lookup"><span data-stu-id="52ae8-206">Expand the **Main** section.</span></span>  <span data-ttu-id="52ae8-207">DevTools 将显示一段时间内主线程上活动的帧图表。</span><span class="sxs-lookup"><span data-stu-id="52ae8-207">DevTools shows you a flame chart of activity on the main thread, over time.</span></span>  <span data-ttu-id="52ae8-208">x 轴表示一段时间内的记录。</span><span class="sxs-lookup"><span data-stu-id="52ae8-208">The x-axis represents the recording, over time.</span></span>  <span data-ttu-id="52ae8-209">每个条形表示一个事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-209">Each bar represents an event.</span></span>  <span data-ttu-id="52ae8-210">宽条表示该事件花费了更长的时间。</span><span class="sxs-lookup"><span data-stu-id="52ae8-210">A wider bar means that event took longer.</span></span>  <span data-ttu-id="52ae8-211">Y 轴表示调用堆叠。</span><span class="sxs-lookup"><span data-stu-id="52ae8-211">The y-axis represents the call stack.</span></span>  <span data-ttu-id="52ae8-212">当你看到事件相互叠加时，表示较高的事件导致较低的事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-212">When you see events stacked on top of each other, it means the upper events caused the lower events.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       <span data-ttu-id="52ae8-214">**主要**部分</span><span class="sxs-lookup"><span data-stu-id="52ae8-214">The **Main** section</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="52ae8-215">记录中有很多数据。</span><span class="sxs-lookup"><span data-stu-id="52ae8-215">There is a lot of data in the recording.</span></span>  <span data-ttu-id="52ae8-216">如果要放大单个事件；请选择、按住并将光标拖动到**Overview**上，即包括**FPS**、**CPU**和**NET**图表的部分。</span><span class="sxs-lookup"><span data-stu-id="52ae8-216">To Zoom into a single event; choose, hold, and dragg your cursor over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.</span></span>  <span data-ttu-id="52ae8-217">"**重点**" 部分和 "**摘要**" 选项卡仅显示录制所选部分的信息。</span><span class="sxs-lookup"><span data-stu-id="52ae8-217">The **Main** section and **Summary** tab only display information for the selected portion of the recording.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="放大事件" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       <span data-ttu-id="52ae8-219">放大事件</span><span class="sxs-lookup"><span data-stu-id="52ae8-219">Zoom into an event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-220">另一种缩放方式，将聚焦在 **主** 部分，选择背景或事件，然后选择 `W`、 `A`、 `S`或 `D`。</span><span class="sxs-lookup"><span data-stu-id="52ae8-220">Another way to zoom, focus the **Main** section, choose the background or an event, and select `W`, `A`, `S`, or `D`.</span></span>  
    
    1.  <span data-ttu-id="52ae8-221">重点关注 **动画帧触发**事件右上角的红色三角形。</span><span class="sxs-lookup"><span data-stu-id="52ae8-221">Focus on the red triangle in the top-right of the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="52ae8-222">每当看到一个红色的三角形，则是一个表示可能有与事件有关问题的警告。</span><span class="sxs-lookup"><span data-stu-id="52ae8-222">Whenever you see a red triangle, it is a warning that there may be an issue related to the event.</span></span>  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-223">每当运行[ `requestAnimationFrame()`回调][MDNWebRequestAnimationFrame]时，就会发生**动画帧触发**事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-223">The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.</span></span>  
    
1.  <span data-ttu-id="52ae8-224">选择 **动画帧触发**事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-224">Choose the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="52ae8-225">"**摘要**" 选项卡现在向你显示有关该事件的信息。</span><span class="sxs-lookup"><span data-stu-id="52ae8-225">The **Summary** tab now shows you information about that event.</span></span>  <span data-ttu-id="52ae8-226">请注意 "**显示**" 链接。</span><span class="sxs-lookup"><span data-stu-id="52ae8-226">Note the **Reveal** link.</span></span>  <span data-ttu-id="52ae8-227">选择后，DevTools 将突出显示启动 **动画帧触发** 事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-227">After you choose it, DevTools to highlights the event that initiated the **Animation Frame Fired** event.</span></span>  <span data-ttu-id="52ae8-228">另外，请关注**app.js:95**链接。</span><span class="sxs-lookup"><span data-stu-id="52ae8-228">Also, focus on the **app.js:95** link.</span></span>  <span data-ttu-id="52ae8-229">选择后，将显示源代码中的相关行。</span><span class="sxs-lookup"><span data-stu-id="52ae8-229">After you choose it, the relevant line in the source code is displayed.</span></span>
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="有关动画帧触发事件的详细信息" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       <span data-ttu-id="52ae8-231">有关**动画帧触发**事件的详细信息</span><span class="sxs-lookup"><span data-stu-id="52ae8-231">More information about the **Animation Frame Fired** event</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-232">选择事件后，使用箭头键选择其旁边的事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-232">After selecting an event, use the arrow keys to select the events next to it.</span></span>  
    
1.  <span data-ttu-id="52ae8-233">在 **app.update** 事件下，有一堆紫色事件。</span><span class="sxs-lookup"><span data-stu-id="52ae8-233">Under the **app.update** event, there is a bunch of purple events.</span></span>  <span data-ttu-id="52ae8-234">如果每个紫色事件都比较宽，看起来每个事件上可能都有个红色三角形。</span><span class="sxs-lookup"><span data-stu-id="52ae8-234">If each purple event was wider, it looks as though each one may have a red triangle on it.</span></span>  
1.  <span data-ttu-id="52ae8-235">选择紫色 **布局**事件之一。</span><span class="sxs-lookup"><span data-stu-id="52ae8-235">Choose one of the purple **Layout** events.</span></span>  <span data-ttu-id="52ae8-236">DevTools 在**摘要**选项卡中提供有关事件的更多信息。确实，有关于强制回流\（换句话说，就是布局\）的警告。</span><span class="sxs-lookup"><span data-stu-id="52ae8-236">DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).</span></span>  
    
1.  <span data-ttu-id="52ae8-237">在“**摘要**”选项卡中，选择**强制布局**“下的**app.js:71**链接。</span><span class="sxs-lookup"><span data-stu-id="52ae8-237">In the **Summary** tab, choose the **app.js:71** link under **Layout Forced**.</span></span>  <span data-ttu-id="52ae8-238">DevTools 将转到强制布局的代码行。</span><span class="sxs-lookup"><span data-stu-id="52ae8-238">DevTools takes you to the line of code that forced the layout.</span></span>  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="导致强制布局的代码行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       <span data-ttu-id="52ae8-240">导致强制布局的代码行</span><span class="sxs-lookup"><span data-stu-id="52ae8-240">The line of code that caused the forced layout</span></span>  
    :::image-end:::  
    
    > [!NOTE]
    > <span data-ttu-id="52ae8-241">这段代码的问题在于，在每个动画帧中，它都会改变每个图标的样式，然后查询每个图标在页面上的位置。</span><span class="sxs-lookup"><span data-stu-id="52ae8-241">The problem with the code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.</span></span>  <span data-ttu-id="52ae8-242">由于样式发生变化，而浏览器不知道每个图标的位置是否发生变化，所以要重新布局图标，才能计算出新的位置。</span><span class="sxs-lookup"><span data-stu-id="52ae8-242">Because the styles changed, the browser does not know if each icon position changed, so it has to re-layout the icon in order to compute the new position.</span></span>  <!--  > See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->
    
<!-- todo: add layouts section when available -->

<span data-ttu-id="52ae8-243">这有许多需要学习。</span><span class="sxs-lookup"><span data-stu-id="52ae8-243">That was a lot to learn.</span></span>  <span data-ttu-id="52ae8-244">现在，已经为分析运行时性能的基本工作流程打下了坚实的基础。</span><span class="sxs-lookup"><span data-stu-id="52ae8-244">You now have a solid foundation in the basic workflow for analyzing runtime performance.</span></span>  <span data-ttu-id="52ae8-245">太棒了。</span><span class="sxs-lookup"><span data-stu-id="52ae8-245">Good job.</span></span>  

### <span data-ttu-id="52ae8-246">附赠：分析优化的版本</span><span class="sxs-lookup"><span data-stu-id="52ae8-246">Bonus: Analyze the optimized version</span></span>  

<span data-ttu-id="52ae8-247">利用刚才学习的工作流程和工具，在演示中选择**优化**以启用优化后的代码，再进行一次性能记录，然后分析结果。</span><span class="sxs-lookup"><span data-stu-id="52ae8-247">Using the workflows and tools that you just learned, choose **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.</span></span>  <span data-ttu-id="52ae8-248">从帧率的提升到**主要**部分火焰图表中事件的减少，能够看到优化版的应用所做的工作更少，从而获得更好的性能。</span><span class="sxs-lookup"><span data-stu-id="52ae8-248">From the improved framerate to the reduction in events in the flame chart in the **Main** section, you are able to see that the optimized version of the app does much less work, resulting in better performance.</span></span>  

> [!NOTE]
> <span data-ttu-id="52ae8-249">即使优化版本也不很好，因为它可以操纵每个图标的`top`属性。</span><span class="sxs-lookup"><span data-stu-id="52ae8-249">Even the optimized version is not great, because it manipulates the `top` property of every icon.</span></span>  <span data-ttu-id="52ae8-250">更好的方法是保留仅影响合成的属性。</span><span class="sxs-lookup"><span data-stu-id="52ae8-250">A better approach is to stick to properties that only affect compositing.</span></span>  <!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## <span data-ttu-id="52ae8-251">后续步骤</span><span class="sxs-lookup"><span data-stu-id="52ae8-251">Next steps</span></span>

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

<span data-ttu-id="52ae8-252">若要更轻松地使用 "性能" 面板，请多多操练，所谓熟能生巧。</span><span class="sxs-lookup"><span data-stu-id="52ae8-252">To get more comfortable with the Performance panel, practice makes perfect.</span></span>  <span data-ttu-id="52ae8-253">试着对页面进行剖析并分析结果。</span><span class="sxs-lookup"><span data-stu-id="52ae8-253">Try profiling your pages and analyzing the results.</span></span>  <span data-ttu-id="52ae8-254">如果对结果有任何疑问，请使用**发送反馈** 图标，选择 `Alt`+`Shift`+`I`  \(Windows, Linux\)，选择 `Option`+`Shift`+`I`  \(macOS\)， 或[发 tweet 给 DevTools 团队][TwitterEdgeDevtools]。</span><span class="sxs-lookup"><span data-stu-id="52ae8-254">If you have any questions about your results, use the **Send Feedback** icon, select `Alt`+`Shift`+`I` \(Windows, Linux\), select `Option`+`Shift`+`I` \(macOS\), or [tweet the DevTools team][TwitterEdgeDevtools].</span></span>  <span data-ttu-id="52ae8-255">如果可能，请包括屏幕截图或指向可重现页面的链接。</span><span class="sxs-lookup"><span data-stu-id="52ae8-255">Include screenshots or links to reproducible pages, if possible.</span></span>  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge 开发人员工具中的**反馈**图标" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   <span data-ttu-id="52ae8-257">Microsoft Edge DevTools 中的**发送反馈**图标</span><span class="sxs-lookup"><span data-stu-id="52ae8-257">The **Send Feedback** icon in the Microsoft Edge DevTools</span></span>  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

<span data-ttu-id="52ae8-258">最后，可通过多种方法来改善运行时性能。</span><span class="sxs-lookup"><span data-stu-id="52ae8-258">Last, there are many ways to improve runtime performance.</span></span>  <span data-ttu-id="52ae8-259">本文重点介绍了一个特定的动画瓶颈，有针对性地参观性能面板，但这只是可能遇到的众多瓶颈之一。</span><span class="sxs-lookup"><span data-stu-id="52ae8-259">This article focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.</span></span>  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

## <span data-ttu-id="52ae8-260">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="52ae8-260">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ DevtoolsCustomizePlacement]: ../customize/placement.md  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）"   
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
> <span data-ttu-id="52ae8-265">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="52ae8-265">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="52ae8-266">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="52ae8-266">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="52ae8-268">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="52ae8-268">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
