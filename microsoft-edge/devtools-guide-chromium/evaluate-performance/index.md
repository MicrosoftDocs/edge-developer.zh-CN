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







# 即可体验分析运行时性能   



> [!NOTE]
> 请参阅 [优化网站速度][DevtoolsSpeedGetStarted] 了解如何提高页面的加载速度。  

运行时性能是页面运行（而不是加载）时的性能。  本教程将指导你如何使用 Microsoft Edge 开发人员工具性能面板来分析运行时性能。  在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。  

<!--todo: add rail link when section is ready -->  

## 入门   

在本教程中，你将在实时页面上打开 DevTools，并使用 "性能" 面板查找页面上的性能瓶颈。  

1.  在 **InPrivate 模式**中打开 Microsoft Edge。  InPrivate 模式可确保 Microsoft Edge 以干净的状态运行。  例如，如果安装了大量的扩展，则这些扩展可能会导致性能测量产生噪音。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  在 InPrivate 窗口中加载以下页面。  这是你要分析的演示。  该页面显示了一堆上下移动的小图标。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/jank/
    ```  
    
1.  按 `Control`+`Shift`+`I` \(Windows\) 或 `Command`+`Option`+`I` \(macOS\) 打开 DevTools。  
    
    > ###### 图 1  
    > 左侧为演示，右侧为 DevTools  
    > ![左侧为演示，右侧为 DevTools][ImageGetStarted]  
    
    > [!NOTE]
    > 至于屏幕截图的其余部分，DevTools 已[停靠至一个单独的窗口][DevtoolsCustomizePlacement]，以便你可以更好地查看内容。  
    
### 模拟移动 CPU  

与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。  每当你分析页面时，都可使用 CPU 节流来模拟页面在移动设备上的表现。  

1.  在 DevTools 中，单击 "**性能**" 选项卡。  
1.  请确保已启用**屏幕截图**复选框。  
1.  单击 "**捕获设置**" !["捕获设置"][ImageCaptureSettingsIcon]。  DevTools 显示了有关如何捕获效果指标的设置。  
1.  对于 "**CPU**"，选择 **4x 减速**。  DevTools 将 CPU 限制为比平时慢 4 倍。  
    
    > ###### 图 2  
    > CPU 节流  
    > ![CPU 节流][ImageCPUThrottling]  
    
    > [!NOTE]
    > 测试其他页面时，如果你想要确保它们在低端移动设备上都能正常工作，请将 CPU 节流设置为 **6x 减速**。  此演示不适用于 6x 减速，因此出于教学目的仅使用 4x 减速。  
    
### 设置演示  

很难创建适用于该网站所有读者的运行时性能演示。  本部分允许你自定义演示，确保不管你的设置如何，你的体验与本教程中看到的屏幕截图和说明都相对一致。

1.  继续单击 "**添加 10**"，直至蓝色图标移动速度明显比以前慢。  在高端计算机上，可能需要大约 20 次单击。  
1.  单击 "**优化**"。  蓝色图标移动速度更快、更平稳。  

    > [!NOTE]
    > 如果你看不到优化版本和未优化版本之间的明显差异，请尝试单击 "**减去 10**" 几次，然后重试。  
    > 如果添加过多的蓝色图标，则只会使 CPU 占用最大内存，而不会看到两个版本的结果有重大差异。  

1.  单击 "**取消优化**"。  蓝色图标的移动速度变慢，并且垃圾再次出现。  

### 记录运行时性能   

运行优化版本的页面时，蓝色图标会移动得更快。  
为什么？  两种版本都应该在相同的时间内将图标移动相同的空间。  在 "性能" 面板中进行录制，了解如何检测未优化版本中的性能瓶颈。  

1.  在 "DevTools" 中，单击 "**记录**" "![录制][ImageRecordIcon]"。  
    页面运行时，DevTools 将捕获效果指标。  
    
    > ###### 图 3 
    > 分析页面  
    > ![分析页面][ImagePageProfiling]  
    
1.  稍等几秒钟。  
1.  单击**停止**。  DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。  
    
    > ###### 图 4  
    > 配置文件的结果  
    > ![配置文件的结果][ImageProfileResults]  

哇，那是海量数据。  不用担心，你很快就会明白。  

## 分析结果   

记录页面性能后，你可以衡量页面的性能有多糟糕，并找出原因。  

### 分析每秒帧数  

用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。  当动画以 60 FPS运行时，用户会觉得很享受。  

1.  查看 **FPS** 图表。  每当你在** FPS **上方看到红色条时，表示帧速率下降得太低，以至于可能损害用户体验。  通常，绿色条越高，FPS 越高。  
    
    > ###### 图 5  
    > FPS 图表  
    > ![FPS 图表][ImageFPSChart]  

1.  在 **FPS** 图表下方，你将看到 **CPU** 图表。  **CPU** 图表中的颜色对应于 "性能" 面板底部 "**摘要**" 选项卡中的 "颜色"。  **CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。  每当你看到 CPU 长时间处于满负荷状态时，就是提示你应该找到减少工作量的方法。  
    
    > ###### 图 6  
    > CPU 图表和摘要选项卡  
    > ![CPU 图表和摘要选项卡][ImageCPUSummary]  

1.  将鼠标悬停在 "**FPS**"、"**CPU**" 或 "**NET**" 图表。  DevTools 将显示该时间点处的页面截图。  左右移动鼠标以重播录音。  这称为 "清理"，对于手动分析动画进度非常有用。  
    
    > ###### 图 7  
    > 查看记录的 2500ms 左右页面的屏幕截图  
    > ![查看记录的 2500ms 左右页面的屏幕截图][ImageViewingScreenshot]  

1.  在 "**帧**" 部分中，将鼠标悬停在其中一个绿色正方形上方。  DevTools 将显示该特定帧的 FPS。  每帧可能远低于 60 FPS的目标。  
    
    > ###### 图 8  
    > 将鼠标悬停在帧上方  
    > ![将鼠标悬停在帧上方][ImageFrameHover]  

当然，通过此演示，很明显页面效果不佳。  但是在实际情况下，它可能不是非常明显，因此使用所有这些工具可使测量更方便。  

#### 附赠：打开 FPS 计数  

另一个非常方便的工具是 FPS 计数，可在页面运行时提供对 FPS 的实时估计。  

1.  按 `Control`+`Shift`+`P` \(Windows\) 或 `Command`+`Shift`+`P` \(macOS\) 打开命令菜单。  
1.  开始在 "命令" 菜单中键入 `Rendering`，然后选择 "**显示绘制**"。  
1.  在 "**绘制**" 选项卡上，启用 **FPS 计数**。  新的叠加层将显示在视线的右上角。  
    
    > ###### 图 9  
    > FPS 计数  
    > ![FPS 计数][ImageFPSMeter]  

1.  禁用 **FPS 计数** 然后按 `Escape` 关闭 **绘制** 选项卡。 在本教程中，你不会用到它。  

### 查找瓶颈  

现在，您已经测量并验证了动画效果不佳，接下来要回答的问题是：为什么？  

1.  注意 "摘要" 选项卡。 未选中任何事件时，此选项卡显示活动的细目。  该页面花费了大部分时间进行绘制。  由于性能是减少工作量的艺术，因此你的目标是减少花费在进行绘制工作上的时间。  
    
    > ###### 图 10  
    > "摘要" 选项卡  
    > !["摘要" 选项卡][ImageSummaryTab]  

1.  展开**重点**部分。  DevTools 将显示一段时间内主线程上活动的帧图表。  x 轴表示一段时间内的记录。  每个条形表示一个事件。  宽条表示该事件花费了更长的时间。  Y 轴表示调用堆叠。  当你看到事件相互叠加时，表示较高的事件导致较低的事件。  
    
    > ##### 图 11  
    > 主要部分  
    > ![主要部分][ImageMainSection]  

1.  记录中有很多数据。  通过单击、按住并在**概览**上拖动鼠标来放大单个事件，该部分包括** FPS **、** CPU **和** NET **图表。  "**重点**" 部分和 "**摘要**" 选项卡仅显示录制所选部分的信息。  
    
    > ###### 图 12  
    > 放大了单个事件  
    > ![放大事件][ImageZoomedAnimation]  
    
    > [!NOTE]
    > 缩放的另一种方法是单击**重点**部分的背景或选择一个事件以专注于该部分，然后按`W`、`A`、`S` 和 `D`键。  
    
    1.  请注意**动画帧触发**事件右上角的红色三角形。  每当你看到红色三角形时，即警告你可能存在与此事件相关的问题。  
    
    > [!NOTE]
    > 每当运行[ `requestAnimationFrame()`回调][MDNWebRequestAnimationFrame]时，就会发生**动画帧触发**事件。  
    
1.  单击**动画帧触发**事件。  "**摘要**" 选项卡现在向你显示有关该事件的信息。  请注意 "**显示**" 链接。  单击将使 DevTools 突出显示启动**动画帧触发**事件的事件。  另请注意 **app.js:95** 链接。  单击可跳至源代码中的相关行。
    
    > ##### 图 13  
    > 有关动画帧触发事件的详细信息  
    > ![有关动画帧触发事件的详细信息][ImageAnimationFrameFired]  
    
    > [!NOTE]
    > 选择事件后，使用箭头键选择其旁边的事件。  

1.  在 **app.update** 事件下，有一堆紫色事件。  如果它们更宽，则似乎每个事件上可能都有一个红色三角形。  立即单击紫色"**布局**"事件之一。  DevTools 在**摘要**选项卡中提供有关事件的更多信息。确实，有关于强制回流\（换句话说，就是布局\）的警告。  

1.  在 "**摘要**" 选项卡中，单击 "**强制布局**" 下的 "**app.js:71**" 链接。  DevTools 将转到强制布局的代码行。  
    
    > ##### 图 14  
    > 导致强制布局的代码行  
    > ![导致强制布局的代码行][ImageForcedLayoutSRC]  
    
    > [!NOTE]
    > 此代码的问题是，在每个动画帧中，它将更改每个图标的样式，然后查询页面上每个图标的位置。  因为样式已更改，浏览器不知道每个图标位置是否已更改，因此必须重新布局图标才能计算其位置。  <!--  See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->

<!-- todo: add layouts section when available -->

哎呀！  这项工作非常繁琐，但是现在你已经在基本工作流程中为分析运行时性能奠定了坚实的基础。  太棒了。  

### 附赠：分析优化的版本  

使用刚刚学习的工作流程和工具，单击演示上的**优化**以启用优化的代码，进行另一次性能记录，然后分析结果。  在**重点**部分的帧图表中，从提高的帧速率到事件的减少，你可以看到该应用程序的优化版本所做的工作少得多，从而提高了性能。  

> [!NOTE]
> 即使这个“优化”版本也不是那么好，因为它仍然可以操纵每个图标的`top`属性。  更好的方法是保留仅影响合成的属性。  
<!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## 后续步骤

<!--The foundation for understanding performance is the RAIL model.  This model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

若要更轻松地使用 "性能" 面板，请多多操练，所谓熟能生巧。  尝试分析自己的页面并分析结果。  如果你对结果有任何疑问，请使用**反馈**图标，在 Windows 上按 `Alt` + `Shift` + `I`（macOS 上按 `Option` + `Shift` + `I`），或[向我们发送推文][TwitterEdgeDevtools]。  如果可能，请包括屏幕截图或指向可重现页面的链接。

> ##### 图 15
> Microsoft Edge 开发人员工具中的 **反馈** 图标  
> ![Microsoft Edge 开发人员工具中的**反馈**图标][ImageFeedbackIcon]

<!-- To really master runtime performance, you've got to learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最后，可通过多种方法来改善运行时性能。  本教程重点介绍了一个特定的动画瓶颈，使你重点关注“性能”面板，但这只是你可能遇到的许多瓶颈之一。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

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
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/evaluate-performance/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
