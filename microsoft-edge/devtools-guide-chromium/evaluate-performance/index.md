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







# 分析运行时性能入门   



> [!NOTE]
> 请参阅[优化网站速度][DevtoolsSpeedGetStarted]，了解如何使页面更快加载。  

运行时性能是指页面在运行时的执行方式，而不是加载。  本教程指导你如何使用 Microsoft Edge DevTools 性能面板来分析运行时性能。  就**滑轨**模型而言，在本教程中学习的技能对于分析页面的响应、动画和空闲阶段非常有用。  

<!--todo: add rail link when section is ready -->  

## 开始行动   

在本教程中，你将在实时页面上打开 DevTools，并使用 "性能" 面板查找页面上的性能瓶颈。  

1.  在**InPrivate 模式下**打开 Microsoft Edge。  InPrivate 模式可确保 Microsoft Edge 在干净状态下运行。  例如，如果安装了大量的扩展，这些扩展可能会在性能测量中产生噪音。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  在您的 InPrivate 窗口中加载以下页面。  这是您要分析的演示。  页面将显示一组小图标，上下移动。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/jank/
    ```  
    
1.  按 `Control` + `Shift` + `I` \ （Windows \）或 `Command` + `Option` + `I` \ （macOS \）打开 DevTools。  
    
    > ###### 图 1  
    > 左侧的演示和右侧的 DevTools  
    > ![左侧的演示和右侧的 DevTools][ImageGetStarted]  
    
    > [!NOTE]
    > 对于屏幕截图的其余部分，DevTools 将取消[停靠到一个单独的窗口][DevtoolsCustomizePlacement]，以便你可以更好地查看内容。  
    
### 模拟移动 CPU  

移动设备具有比台式机和笔记本电脑更少的 CPU 功率。  分析页面时，请使用 CPU 限制模拟页面在移动设备上的执行方式。  

1.  在 DevTools 中，单击 "**性能**" 选项卡。  
1.  请确保 "**屏幕截图**" 复选框已启用。  
1.  单击 "**捕获设置** ![ 捕获设置" ][ImageCaptureSettingsIcon] 。  DevTools 显示与如何捕获性能指标相关的设置。  
1.  对于**CPU**，选择**4x 减速**。  DevTools 将 CPU 限制为比平时慢4倍。  
    
    > ###### 图 2  
    > CPU 限制  
    > ![CPU 限制][ImageCPUThrottling]  
    
    > [!NOTE]
    > 测试其他页面时，如果你希望确保它们在低端移动设备上能够正常工作，请将 CPU 限制设置为**6x 减速**。  此演示不太适合6x 速度，因此它只是为了说明目的而使用4x 减速。  
    
### 设置演示  

很难创建适用于本网站的所有读者的运行时性能演示。  本部分允许你自定义演示，以确保你的体验与你在本教程中看到的屏幕截图和说明相对一致，无论你的特定设置如何。

1.  继续单击 "**添加 10** "，直到蓝色图标的移动速度明显比以前慢一些。  在高端计算机上，可能需要大约20次单击。  
1.  单击 "**优化**"。  蓝色图标的移动速度更快、更流畅。  

    > [!NOTE]
    > 如果未看到已优化和未优化版本之间的显著差异，请尝试单击几次**减去 10**次，然后重试。  
    > 如果添加过多的蓝色图标，则只需占用 CPU 的最大值，您就不会看到两个版本的结果中的主要差异。  

1.  单击 "**取消优化**"。  蓝色图标的移动速度较慢，并且与更多 jank。  

### 记录运行时性能   

运行优化版本的页面时，蓝色图标的移动速度更快。  
这是为什么呢？  这两个版本都可以在同一时间内将图标移动相同的空间量。  在 "性能" 面板中记录一个记录，了解如何检测未优化版本中的性能瓶颈。  

1.  在 DevTools 中，单击 "**录制** ![ 记录" ][ImageRecordIcon] 。  
    DevTools 在页面运行时捕获性能指标。  
    
    > ###### 图 3 
    > 分析页面  
    > ![分析页面][ImagePageProfiling]  
    
1.  等待几秒钟。  
1.  单击 "**停止**"。  DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。  
    
    > ###### 图 4  
    > 配置文件的结果  
    > ![配置文件的结果][ImageProfileResults]  

哇，这是大量数据。  别担心，很快就会有更多的意义。  

## 分析结果   

记录了页面性能后，你可以测量页面性能有多差，并找到任何原因。  

### 分析每秒帧数  

测量任何动画性能的主要指标是每秒帧数 \ （FPS \）。  当动画在 60 FPS 运行时，用户将感到满意。  

1.  查看**FPS**图表。  每当你在**FPS**上方看到红色条形图时，这意味着该变得较低的变帧可能会损害用户体验。  通常情况下，绿色条越高，FPS 越高。  
    
    > ###### 图 5  
    > FPS 图表  
    > ![FPS 图表][ImageFPSChart]  

1.  在**FPS**图表下，你可以看到**CPU**图表。  **CPU**图表中的颜色对应于 "性能" 面板底部的 "**摘要**" 选项卡中的颜色。  **Cpu**图表的完全颜色意味着在录制期间 cpu 已 maxed。  只要您看到 CPU maxed 长时间，它就是查找更少工作的方法的提示。  
    
    > ###### 图 6  
    > CPU 图表和摘要选项卡  
    > ![CPU 图表和摘要选项卡][ImageCPUSummary]  

1.  将鼠标悬停在 " **FPS**"、" **CPU**" 或 "**网络**" 图表上。  DevTools 显示该时间点的页面的屏幕截图。  将鼠标向左和向右移动以重播录制。  这称为 "清理"，它对于手动分析动画进度很有用。  
    
    > ###### 图 7  
    > 在录制的2500ms 标记周围查看页面的屏幕截图  
    > ![在录制的2500ms 标记周围查看页面的屏幕截图][ImageViewingScreenshot]  

1.  在 "**框架**" 部分中，将鼠标悬停在其中一个绿色方块上。  DevTools 显示该特定帧的 FPS。  每个帧可能很好地低于 60 FPS 的目标。  
    
    > ###### 图 8  
    > 将鼠标悬停在框架上  
    > ![将鼠标悬停在框架上][ImageFrameHover]  

当然，通过此演示，很明显，页面的性能不佳。  但在实际情况下，它可能不是很清楚，因此，让所有这些工具能够使测量更方便。  

#### 奖金：打开 FPS 指示器  

另一个方便的工具是 FPS 指示器，可在页面运行时提供对 FPS 的实时估计。  

1.  按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "命令" 菜单。  
1.  开始 `Rendering` 在 "命令" 菜单中键入，然后选择 "**显示呈现**"。  
1.  在 "**呈现**" 选项卡上，启用**FPS 指示器**。  新的覆盖区将出现在视区的右上角。  
    
    > ###### 图 9  
    > FPS 指示器  
    > ![FPS 指示器][ImageFPSMeter]  

1.  禁用**FPS 指示器**，然后按 `Escape` 关闭 "**呈现**" 选项卡。 您不会在本教程中使用它。  

### 找出瓶颈  

现在，你已经测量并验证动画是否工作不好，下一个要回答的问题是：为什么？  

1.  注意 "摘要" 选项卡。 如果未选择任何事件，此选项卡将显示活动的细目。  该页的大部分时间都已花费在呈现中。  由于性能是执行较少工作的艺术，因此你的目标是减少执行呈现工作所花费的时间量。  
    
    > ###### 图 10  
    > "摘要" 选项卡  
    > !["摘要" 选项卡][ImageSummaryTab]  

1.  展开 "**主**" 部分。  DevTools 显示了一段时间内主线程上活动的火焰图表。  X 轴代表一段时间内的录音。  每条条表示一个事件。  较大的栏表示事件花费较长时间。  Y 轴表示调用堆栈。  当你看到彼此重叠的事件时，它表示较高事件导致较低的事件。  
    
    > ##### 图 11  
    > 主要部分  
    > ![主要部分][ImageMainSection]  

1.  录制中有大量数据。  通过在**概述**中单击、按住和拖动鼠标来放大单个事件，这是包括**FPS**、 **CPU**和**网络**图表的部分。  "**主要**" 部分和 "**摘要**" 选项卡仅显示录制的选定部分的信息。  
    
    > ###### 图 12  
    > 放大单个事件  
    > ![放大事件][ImageZoomedAnimation]  
    
    > [!NOTE]
    > 缩放的另一种方法是通过单击其背景或选择事件来重点关注**主**节，然后按 `W` 、、 `A` `S` 、和 `D` 键。  
    
    1.  注意**动画帧**的右上角的红色三角形激发了事件。  只要看到红色三角形，就会出现一条警告，指出可能存在与此事件相关的问题。  
    
    > [!NOTE]
    > 只要运行[ `requestAnimationFrame()` 回调][MDNWebRequestAnimationFrame]，就会发生引发事件的**动画帧**。  
    
1.  单击**动画帧激发**的事件。  "**摘要**" 选项卡现显示有关该事件的信息。  注意 "**显示**" 链接。  单击 "导致 DevTools"，以突出显示发起**动画帧触发**事件的事件。  另请注意， **app.config： 95**链接。  单击该方法可跳转到源代码中的相关行。
    
    > ##### 图 13  
    > 有关动画帧激发事件的详细信息  
    > ![有关动画帧激发事件的详细信息][ImageAnimationFrameFired]  
    
    > [!NOTE]
    > 选择事件后，使用箭头键选择它旁边的事件。  

1.  在**应用程序更新**事件下，有一组紫色事件。  如果它们的宽度较宽，则它看起来好像每个文件可能有一个红色三角形。  立即单击其中一个紫色**布局**事件。  DevTools 在 "**摘要**" 选项卡中提供有关事件的详细信息。 事实上，有关于强制重排 \ （另一个 word for layout）的警告。  

1.  在 "**摘要**" 选项卡中，单击 "**布局强制**" 下的 " **.js： 71** " 链接。  DevTools 将转到强制执行布局的代码行。  
    
    > ##### 图 14  
    > 导致强制布局的代码行  
    > ![导致强制布局的代码行][ImageForcedLayoutSRC]  
    
    > [!NOTE]
    > 此代码的问题是，在每个动画帧中，它会更改每个图标的样式，然后查询页面上每个图标的位置。  由于样式已更改，因此浏览器不知道每个图标位置是否已更改，因此它必须重新布局图标才能计算其位置。  <!--  See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->

<!-- todo: add layouts section when available -->

唷！  这是很多事情，但现在在分析运行时性能的基本工作流中有坚实的基础。  干得好。  

### 奖金：分析优化版本  

使用您刚刚学习的工作流和工具，单击演示的 "**优化**" 以启用优化的代码，执行另一条性能记录，然后分析结果。  从改进的帧数到**主**部分中的火焰图中的事件减少，你可以看到应用的优化版本的工作量很少，从而提高性能。  

> [!NOTE]
> 即使此 "优化" 版本也不是很好，因为它仍会操纵 `top` 每个图标的属性。  更好的方法是坚持仅影响合成的属性。  
<!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## 后续步骤

<!--The foundation for understanding performance is the RAIL model.  This model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

为了更舒适地使用 "性能" 面板，最佳做法是实现完美。  尝试分析自己的页面并分析结果。  如果您对结果有任何疑问，请使用 "**反馈**" 图标，按 macOS 上的 " `Alt`  +  `Shift`  +  `I` Windows" `Option`  +  `Shift`  +  `I` 或 " [tweet][TwitterEdgeDevtools]"。  将屏幕截图或链接添加到可重复的页面（如有可能）。

> ##### 图 15
> Microsoft Edge DevTools 中的 "**反馈**" 图标  
> ![Microsoft Edge DevTools 中的 * * 反馈 * * 图标][ImageFeedbackIcon]

<!-- To really master runtime performance, you've got to learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最后，可以通过多种方式来提高运行时性能。  本教程重点介绍一个特定的动画瓶颈，让您能够通过 "性能" 面板集中浏览，但这只是你可能遇到的一个瓶颈。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
