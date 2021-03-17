---
description: 了解如何在 Microsoft Edge DevTools 中评估运行时性能。
title: 即可体验分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/08/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 439d6d4331550b7fc92bfc5fef4c3fc88df38872
ms.sourcegitcommit: 4b9fb5c1176fdaa5e3c60af2b84e38d5bb86cd81
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/16/2021
ms.locfileid: "11439610"
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

# <a name="get-started-with-analyzing-runtime-performance"></a>即可体验分析运行时性能  

> [!NOTE]
> 要了解如何使网页加载速度更快，请浏览[优化网站速度][DevtoolsSpeedGetStarted]。  

运行时性能是页面运行（而不是加载）时的性能。  下面的教程文章教导如何使用Microsoft Edge DevTools性能面板来分析运行时性能。  在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。  

<!--todo: add rail link when section is ready -->  

## <a name="get-started"></a>入门  

在下面的教程中，在一个实时页面上打开DevTools，并使用**性能**面板来查找页面上的性能瓶颈。  

1.  在 **InPrivate 模式**中打开 Microsoft Edge。  InPrivate 模式可确保 Microsoft Edge 以干净的状态运行。  例如，如果安装了大量扩展，则扩展可能会在性能测量中产生噪音。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  在 InPrivate 窗口中加载以下页面。  这个页面就是所要介绍的演示。  该页面显示了一堆上下移动的小图标。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  选择`Control`+`Shift`+`I` \（Windows，Linux\）或`Command`+`Option`+`I` \（macOS\）以打开 DevTools。  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左侧为演示，右侧为 DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       左侧为演示，右侧为 DevTools  
    :::image-end:::  
    
    > [!NOTE]
    > 对于数据的其余部分，DevTools [解锁到一个单独的窗口][DevtoolsCustomizePlacement]以便更加关注于内容。  
    
### <a name="simulate-a-mobile-cpu"></a>模拟移动 CPU  

与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。  每当你分析页面时，都可使用 CPU 节流来模拟页面在移动设备上的表现。  

1.  在 DevTools 中，选择 **"性能"** 工具。  
1.  确保你选择"屏幕截图"旁边的 **复选框**。  
1.  Choose **Capture Settings** \ (Capture Settings ![ ](../media/capture-settings-icon.msft.png) \) .  DevTools 显示了有关如何捕获效果指标的设置。  
1.  对于**CPU**，请选择**4倍减速**。  DevTools 将 CPU 限制为比平时慢 4 倍。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU 限制" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       CPU 限制  
    :::image-end:::  
    
    > [!NOTE]
    > 在测试其他页面时；如果想确保每个页面在低端移动设备上都能很好的运行，将CPU限制设置为**6倍减速**。  演示在6倍减速下效果不好，所以只用4倍减速进行教学。  
    
### <a name="set-up-the-demo"></a>设置演示  

很难创建一个对所有网站读者都能稳定运行的性能演示。  以下部分可以自定义演示，以确保无论特定设置如何，体验与截图和描述都相对一致。

1.  选择“**添加 10**”按钮，直到蓝色图标移动速度明显比之前慢。  在高端计算机上，可能需要选择它大约 20 次。  
1.  选择 **优化**。  蓝色图标移动速度更快、更平稳。  
    
    > [!NOTE]
    > 如果要更好地显示优化版本与未优化版本之间的差异，请选择几次**减去 10**按钮，然后重试。  
    > 如果添加太多的蓝色图标，可能会最大限度地使用CPU，然后可能就不会观察到两个版本的结果有很大的差异。  
    
1.  选择 **取消优化**。  蓝色图标移动速度变慢，而且又更加迟钝。  
    
### <a name="record-runtime-performance"></a>记录运行时性能  

运行优化版本的页面时，蓝色图标会移动得更快。  为什么？  两种版本都应该在相同的时间内将图标移动相同的空间。  在 "性能" 面板中进行录制，了解如何检测未优化版本中的性能瓶颈。  

1.  在 DevTools**** 中，选择"记录 ![ " ("记录 ](../media/record-icon.msft.png) ") "。  页面运行时，DevTools 将捕获效果指标。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="配置文件页面" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       配置文件页面  
    :::image-end:::  
    
1.  稍等几秒钟。  
1.  选择**停止**。  DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="配置文件的结果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       配置文件的结果  
    :::image-end:::  
    
哇，那是海量数据。  请不要担心，很快此过程就会变得更有意义。  

## <a name="analyze-the-results"></a>分析结果  

在记录页面性能后，测量页面的性能质量，并找到任何相关原因。  

### <a name="analyze-frames-per-second"></a>分析每秒帧数  

用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。  当动画以 60 FPS运行时，用户会觉得很享受。  

1.  查看 **FPS** 图表。  每当红色条显示在 **FPS**上方时，这意味着帧速率下降得过低，可能损害用户体验。  通常，绿色条越高，FPS 越高。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       **FPS** 图表  
    :::image-end:::  
    
1.  在 **FPS** 图表下方， **显示 CPU** 图表。  CPU**图表中的颜色对应于**"性能"面板底部的"摘要****"面板中的颜色。  **CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。  每当 CPU 长时间达到最大值时，你应该找到减少工作的方法指示器。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="CPU 图表和摘要面板" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       **CPU**图表和**摘要**面板  
    :::image-end:::  
    
1.  鼠标悬停在 **FPS**、 **CPU**或**NET** 图表上。  DevTools 将显示该时间点处的页面截图。  左右移动鼠标以重播录音。  引用该操作为擦除，它对于手动分析动画的进程很有用。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="查看2500ms左右的录制页面截图" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       查看2500ms左右的录制页面截图  
    :::image-end:::  
    
1.  在“**框架**”部分，将鼠标悬停在其中一个绿色方块上。  DevTools 将显示该特定帧的 FPS。  每帧可能远低于 60 FPS的目标。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       鼠标悬停在框架上  
    :::image-end:::  
    
当然，显示指示网页运行不佳。  但是在实际场景中可能就不是那么清楚了，所以掌握所有的工具进行测量就会方便很多。  

#### <a name="bonus-open-the-fps-meter"></a>附赠：打开 FPS 计数  

另一个非常方便的工具是 FPS 计数，可在页面运行时提供对 FPS 的实时估计。  

1.  选择 `Control`+`Shift`+`P` \(Windows、Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 打开**命令菜单**。  
1.  在**命令菜单**中开始键入`Rendering`，然后选择**显示渲染**.  
1.  在呈现 **工具** 中，打开 **FPS 指示器**。  新的叠加层将显示在视线的右上角。  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       **FPS 计数**  
        :::image-end:::  
    
1.  关闭 **FPS 指示器并选择** 关闭 `Escape` **呈现工具** 。  本教程中未 **使用 FPS** 指示器。  
    
### <a name="find-the-bottleneck"></a>查找瓶颈  

当测量并验证动画表现不佳之后，下一步就是要回答“为什么？”的问题。  

1.  未选择任何事件时 **，"摘要"** 面板将显示活动的细目。  页面大部分时间都在渲染。  由于性能是减少工作量的艺术，因此你的目标是减少花费在进行绘制工作上的时间。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text="摘要面板" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       摘要**面板**  
    :::image-end:::  
    
1.  展开**重点**部分。  DevTools 将显示一段时间内主线程上活动的帧图表。  x 轴表示一段时间内的记录。  每个条形表示一个事件。  宽条表示该事件花费了更长的时间。  Y 轴表示调用堆叠。  当事件堆叠在一起时，这意味着上面的事件导致了较低的事件。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       **主要**部分  
    :::image-end:::  
    
1.  记录中有很多数据。  如果要放大单个事件；请选择、按住并将光标拖动到**Overview**上，即包括**FPS**、**CPU**和**NET**图表的部分。  " **主** 节"和" **摘要** "面板仅显示所选部分录制的信息。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="放大事件" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       放大事件  
    :::image-end:::  
    
    > [!NOTE]
    > 另一种缩放方式，将聚焦在 **主** 部分，选择背景或事件，然后选择 `W`、 `A`、 `S`或 `D`。  
    
    1.  重点关注 **动画帧触发**事件右上角的红色三角形。  每当显示红色三角形时，都会显示一条警告，指出可能有与事件相关的问题。  
    
    > [!NOTE]
    > 每当 **运行** [requestAnimationFrame][MDNWebRequestAnimationFrame] 或 () 时，将发生 Animation Frame Fired 事件。  
    
1.  选择 **动画帧触发**事件。  " **摘要** "面板现在将显示有关该事件的信息。  请注意 "**显示**" 链接。  选择后，DevTools 将突出显示启动 **动画帧触发** 事件。  另外，请关注**app.js:95**链接。  选择后，将显示源代码中的相关行。
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="有关动画帧触发事件的详细信息" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       有关**动画帧触发**事件的详细信息  
    :::image-end:::  
    
    > [!NOTE]
    > 选择事件后，使用箭头键选择事件旁边的事件。  
    
1.  在 **app.update** 事件下，有一堆紫色事件。  如果每个紫色事件都比较宽，看起来每个事件上可能都有个红色三角形。  
1.  选择紫色 **布局**事件之一。  DevTools 在摘要面板中提供有关 **事件** 详细信息。  实际上，存在一条有关强制重排 \ (layout\) 的警告。  
    
1.  在摘要 **面板中** ，选择布局强制 ** 下的app.js：71** **链接**。  DevTools 将转到强制布局的代码行。  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="导致强制布局的代码行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       导致强制布局的代码行  
    :::image-end:::  
    
    > [!NOTE]
    > 这段代码的问题在于，在每个动画帧中，它都会改变每个图标的样式，然后查询每个图标在页面上的位置。  由于样式发生变化，而浏览器不知道每个图标的位置是否发生变化，所以要重新布局图标，才能计算出新的位置。  <!--  > To learn more, navigate to [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts].  -->
    
<!-- todo: add layouts section when available -->

这有许多需要学习。  现在，已经为分析运行时性能的基本工作流程打下了坚实的基础。  太棒了。  

### <a name="bonus-analyze-the-optimized-version"></a>附赠：分析优化的版本  

使用刚学到的工作流和工具，在演示中选择"**** 优化"以打开优化的代码，执行另一个性能记录，然后分析结果。  从改进的帧速率到 **主** 部分中绘制图表的事件减少，应用的优化版本执行的工作要少得多，从而产生更好的性能。  

> [!NOTE]
> 即使优化版本也不很好，因为它可以操纵每个图标的`top`属性。  更好的方法是保留仅影响合成的属性。  <!--  > For more information, navigate to [Use transform and opacity changes for animations][RenderingCompositor].  -->  

<!--todo: add rendering section when available -->

## <a name="next-steps"></a>后续步骤

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
To learn more, navigate to [Measure Performance With The RAIL Model][RAIL].  -->  

为了更加熟悉性能 **工具** ，实践非常完美。  试着对页面进行剖析并分析结果。  如果对结果有任何疑问，请使用**发送反馈** 图标，选择 `Alt`+`Shift`+`I`  \(Windows, Linux\)，选择 `Option`+`Shift`+`I`  \(macOS\)， 或[发 tweet 给 DevTools 团队][TwitterEdgeDevtools]。  如果可能，请包括屏幕截图或指向可重现页面的链接。  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge 开发人员工具中的**反馈**图标" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   Microsoft Edge DevTools 中的**发送反馈**图标  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最后，可通过多种方法来改善运行时性能。  本文重点介绍了一个特定的动画瓶颈，有针对性地参观性能面板，但这只是可能遇到的众多瓶颈之一。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->

[ DevtoolsCustomizePlacement]: ../customize/placement.md  "更改 Microsoft Edge 开发人员工具的放置位置（取消停靠、停靠至底部、停靠至左）"   
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
