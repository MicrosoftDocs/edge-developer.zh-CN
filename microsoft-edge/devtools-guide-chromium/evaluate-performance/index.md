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

# Get started with analyzing Runtime performance  

> [!NOTE]
> To learn how to make your pages load faster, see [Optimize Website Speed][DevtoolsSpeedGetStarted].  

Runtime performance is how your page performs when it is running, as opposed to loading.  The following tutorial article teaches you how to use the Microsoft Edge DevTools Performance panel to analyze runtime performance.  在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。  

<!--todo: add rail link when section is ready -->  

## Get started  

In the following tutorial, you open DevTools on a live page and use the **Performance** panel to find a performance bottleneck on the page.  

1.  Open Microsoft Edge in **InPrivate Mode**.  InPrivate Mode ensures that Microsoft Edge runs in a clean state.  For example, if you have a lot of extensions installed, the extensions may create noise in your performance measurements.  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  Load the following page in your InPrivate window.  The page is the demo that you are going to profile.  The page shows a bunch of little icons moving up and down.  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  Select `Control`+`Shift`+`I` \(Windows\) or `Command`+`Option`+`I` \(macOS\) to open DevTools.  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       The demo on the left, and DevTools on the right  
    :::image-end:::  
    
    > [!NOTE]
    > For the rest of the figures, DevTools is [undocked to a separate window][DevtoolsCustomizePlacement] to better focus on the contents.  
    
### Simulate a mobile CPU  

与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。  Whenever you profile a page, use CPU Throttling to simulate how your page performs on mobile devices.  

1.  In DevTools, choose the **Performance** tab.  
1.  Make sure that the **Screenshots** checkbox is enabled.  
1.  Choose **Capture Settings** \(![Capture Settings][ImageCaptureSettingsIcon]\).  DevTools reveals settings related to how it captures performance metrics.  
1.  对于 "**CPU**"，选择 **4x 减速**。  DevTools throttles your CPU so that it is 4 times slower than usual.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       CPU throttle  
    :::image-end:::  
    
    > [!NOTE]
    > When testing other pages; if you want to ensure that each page works well on low-end mobile devices, set CPU Throttling to **6x slowdown**.  The demo does not work well with 6x slowdown, so it just uses 4x slowdown for instructional purposes.  
    
### Set up the demo  

It is hard to create a runtime performance demo that works consistently for all readers of the website.  The following section lets you customize the demo to ensure that your experience is relatively consistent with the screenshots and descriptions, regardless of your particular set up.

1.  Choose the **Add 10** button until the blue icons move noticeably slower than before.  On a high-end machine, you may to choose it about 20 times.  
1.  Choose **Optimize**.  The blue icons should move faster and more smoothly.  
    
    > [!NOTE]
    > To better display a difference between the optimized and un-optimized versions, choose the **Subtract 10** button a few times and try again.  
    > If you add too many blue icons, you may max out the CPU and then you may not observe a major difference in the results for the two versions.  
    
1.  Choose **Un-Optimize**.  The blue icons move slower and with more sluggishness again.  
    
### Record runtime performance  

运行优化版本的页面时，蓝色图标会移动得更快。  为什么？  两种版本都应该在相同的时间内将图标移动相同的空间。  Take a recording in the Performance panel to learn how to detect the performance bottleneck in the un-optimized version.  

1.  In DevTools, choose **Record** \(![Record][ImageRecordIcon]\).  DevTools captures performance metrics as the page runs.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       Profile the page  
    :::image-end:::  
    
1.  Wait a few seconds.  
1.  Choose **Stop**.  DevTools stops recording, processes the data, then displays the results on the Performance panel.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       配置文件的结果  
    :::image-end:::  
    
Wow, that is an overwhelming amount of data.  do not worry, soon the process makes more sense.  

## Analyze the results  

After you record the performance of the page, measure the quality of the performance of the page and find the any causes.  

### Analyze frames per second  

用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。  当动画以 60 FPS运行时，用户会觉得很享受。  

1.  查看 **FPS** 图表。  每当你在** FPS **上方看到红色条时，表示帧速率下降得太低，以至于可能损害用户体验。  In general, the higher the green bar, the higher the FPS.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       The **FPS** chart  
    :::image-end:::  
    
1.  Below the **FPS** chart you see the **CPU** chart.  **CPU** 图表中的颜色对应于 "性能" 面板底部 "**摘要**" 选项卡中的 "颜色"。  **CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。  Whenever you see the CPU maxed out for long periods, it is a cue to find ways to do less work.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       The **CPU** chart and **Summary** tab  
    :::image-end:::  
    
1.  Hover on the **FPS**, **CPU**, or **NET** charts.  DevTools shows a screenshot of the page at that point in time.  Move your mouse left and right to replay the recording.  The action is referenced as scrubbing, and it is useful for manually analyzing the progression of animations.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       View a screenshot of the page around the 2500ms mark of the recording  
    :::image-end:::  
    
1.  In the **Frames** section, hover on one of the green squares.  DevTools shows you the FPS for that particular frame.  Each frame is probably well below the target of 60 FPS.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       Hover on a frame  
    :::image-end:::  
    
Of course, you should see that the page is not performing well.  But in real scenarios, it may not be so clear, so having all of the tools to make measurements comes in handy.  

#### Bonus: Open the FPS meter  

Another handy tool is the FPS meter, which provides real-time estimates for FPS as the page runs.  

1.  Select `Control`+`Shift`+`P` \(Windows\) or `Command`+`Shift`+`P` \(macOS\) to open the **Command Menu**.  
1.  Start typing `Rendering` in the **Command Menu** and select **Show Rendering**.  
1.  In the **Rendering** tab, enable **FPS Meter**.  A new overlay appears in the top-right of your viewport.  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       The **FPS meter**  
        :::image-end:::  
    
1.  Disable the **FPS Meter** and select `Escape` to close the **Rendering** tab.  You are not using **FPS Meter** in this tutorial.  
    
### Find the bottleneck  

After you measured and verified that the animation is not performing well, the next step is to answer the question "why?".  

1.  When no events are selected, the **Summary** tab shows you a breakdown of activity.  The page spent most of the time rendering.  Since performance is the art of doing less work, your goal is to reduce the amount of time spent doing rendering work.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       The **Summary** tab  
    :::image-end:::  
    
1.  Expand the **Main** section.  DevTools 将显示一段时间内主线程上活动的帧图表。  x 轴表示一段时间内的记录。  每个条形表示一个事件。  宽条表示该事件花费了更长的时间。  Y 轴表示调用堆叠。  When you see events stacked on top of each other, it means the upper events caused the lower events.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       The **Main** section  
    :::image-end:::  
    
1.  There is a lot of data in the recording.  To Zoom into a single event; choose, hold, and dragg your cursor over the **Overview**, which is the section that includes the **FPS**, **CPU**, and **NET** charts.  The **Main** section and **Summary** tab only display information for the selected portion of the recording.  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       Zoom into an event  
    :::image-end:::  
    
    > [!NOTE]
    > Another way to zoom, focus the **Main** section, choose the background or an event, and select `W`, `A`, `S`, or `D`.  
    
    1.  Focus on the red triangle in the top-right of the **Animation Frame Fired** event.  Whenever you see a red triangle, it is a warning that there may be an issue related to the event.  
    
    > [!NOTE]
    > The **Animation Frame Fired** event occurs whenever a [`requestAnimationFrame()` callback][MDNWebRequestAnimationFrame] is run.  
    
1.  Choose the **Animation Frame Fired** event.  The **Summary** tab now shows you information about that event.  Note the **Reveal** link.  After you choose it, DevTools to highlights the event that initiated the **Animation Frame Fired** event.  Also, focus on the **app.js:95** link.  After you choose it, the relevant line in the source code is displayed.
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       More information about the **Animation Frame Fired** event  
    :::image-end:::  
    
    > [!NOTE]
    > After selecting an event, use the arrow keys to select the events next to it.  
    
1.  Under the **app.update** event, there is a bunch of purple events.  If each purple event was wider, it looks as though each one may have a red triangle on it.  
1.  Choose one of the purple **Layout** events.  DevTools provides more information about the event in the **Summary** tab.  Indeed, there is a warning about forced reflows \(another word for layout\).  
    
1.  In the **Summary** tab, choose the **app.js:71** link under **Layout Forced**.  DevTools takes you to the line of code that forced the layout.  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       The line of code that caused the forced layout  
    :::image-end:::  
    
    > [!NOTE]
    > The problem with the code is that, in each animation frame, it changes the style for each icon, and then queries the position of each icon on the page.  Because the styles changed, the browser does not know if each icon position changed, so it has to re-layout the icon in order to compute the new position.  <!--  > See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->
    
<!-- todo: add layouts section when available -->

That was a lot to learn.  You now have a solid foundation in the basic workflow for analyzing runtime performance.  Good job.  

### Bonus: Analyze the optimized version  

Using the workflows and tools that you just learned, choose **Optimize** on the demo to enable the optimized code, take another performance recording, and then analyze the results.  From the improved framerate to the reduction in events in the flame chart in the **Main** section, you are able to see that the optimized version of the app does much less work, resulting in better performance.  

> [!NOTE]
> Even the optimized version is not great, because it manipulates the `top` property of every icon.  A better approach is to stick to properties that only affect compositing.  <!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## 后续步骤

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

To get more comfortable with the Performance panel, practice makes perfect.  Try profiling your pages and analyzing the results.  If you have any questions about your results, use the **Send Feedback** icon, select `Alt`+`Shift`+`I` \(Windows\), select `Option`+`Shift`+`I` \(macOS\), or [tweet the DevTools team][TwitterEdgeDevtools].  Include screenshots or links to reproducible pages, if possible.  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="The demo on the left, and DevTools on the right" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   The **Send Feedback** icon in the Microsoft Edge DevTools  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

Last, there are many ways to improve runtime performance.  This article focused on one particular animation bottleneck to give you a focused tour through the Performance panel, but it is only one of many bottlenecks you may encounter.  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
