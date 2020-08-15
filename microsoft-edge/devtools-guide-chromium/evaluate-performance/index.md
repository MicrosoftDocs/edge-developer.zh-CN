---
title: 即可体验分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 94753c7024c2f4f4c96d560c815d310b1f9643a1
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931112"
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
> 若要了解如何使页面更快加载，请参阅 [优化网站速度][DevtoolsSpeedGetStarted]。  

运行时性能是页面运行（而不是加载）时的性能。  以下教程文章介绍了如何使用 Microsoft Edge DevTools 性能面板来分析运行时性能。  在 **RAIL** 模型方面，你在本教程中学习的技能对于分析页面的响应、动画和空闲阶段很有用。  

<!--todo: add rail link when section is ready -->  

## 入门  

在以下教程中，你将在实时页面上打开 DevTools，并使用 " **性能** " 面板查找页面上的性能瓶颈。  

1.  在 **InPrivate 模式**中打开 Microsoft Edge。  InPrivate 模式可确保 Microsoft Edge 以干净的状态运行。  例如，如果安装了大量的扩展，扩展可能会在性能测量中产生噪音。  
    
    <!--TODO: replace section when updated for new Edge  -->
    
1.  在 InPrivate 窗口中加载以下页面。  页面是你要分析的演示。  该页面显示了一堆上下移动的小图标。  
    
    ```https
    https://microsoft-edge-chromium-devtools.glitch.me/sluggish/
    ```  
    
1.  选择 `Control` + `Shift` + `I` \ (Windows \ ) 或 `Command` + `Option` + `I` \ (macOS \ ) 打开 DevTools。  
    
    :::image type="complex" source="../media/evaluate-performance-get-started-side-by-side.msft.png" alt-text="左侧为演示，右侧为 DevTools" lightbox="../media/evaluate-performance-get-started-side-by-side.msft.png":::
       左侧为演示，右侧为 DevTools  
    :::image-end:::  
    
    > [!NOTE]
    > 对于其余的数字，DevTools 将取消 [停靠到一个单独的窗口][DevtoolsCustomizePlacement] ，以便更好地关注内容。  
    
### 模拟移动 CPU  

与台式机和笔记本电脑相比，移动设备的 CPU 功率更小。  每当你分析页面时，都可使用 CPU 节流来模拟页面在移动设备上的表现。  

1.  在 DevTools 中，选择 " **性能** " 选项卡。  
1.  请确保已启用**屏幕截图**复选框。  
1.  选择 " **捕获设置** \ ("！[捕获设置][ImageCaptureSettingsIcon] \ ) 。  DevTools 显示了有关如何捕获效果指标的设置。  
1.  对于 "**CPU**"，选择 **4x 减速**。  DevTools 将 CPU 限制为比平时慢 4 倍。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-settings.msft.png" alt-text="CPU 限制" lightbox="../media/evaluate-performance-performance-capture-settings.msft.png":::
       CPU 限制  
    :::image-end:::  
    
    > [!NOTE]
    > 测试其他页面时;如果你想要确保每个页面在低端移动设备上都可以正常运行，请将 CPU 限制设置为 **6x 减速**。  演示在6x 速度上不能很好地运行，因此它只是为了说明目的而使用4x 减速。  
    
### 设置演示  

很难创建适用于网站所有读者的运行时性能演示。  以下部分允许你自定义演示，以确保你的体验与屏幕截图和说明相对一致，无论你的具体设置如何。

1.  选择 " **添加 10** " 按钮，直到蓝色图标明显比以前慢一些。  在高端计算机上，您可以选择大约20次。  
1.  选择 " **优化**"。  蓝色图标移动速度更快、更平稳。  
    
    > [!NOTE]
    > 若要更好地显示优化版本和未经优化版本之间的差异，请选择几次 " **减 10** " 按钮，然后重试。  
    > 如果添加太多蓝色图标，则可能会导致 CPU 的最大限制，因此你可能无法在两个版本的结果中看到重大差异。  
    
1.  选择 " **取消优化**"。  蓝色图标的移动速度较慢，并且与更多 sluggishness。  
    
### 记录运行时性能  

运行优化版本的页面时，蓝色图标会移动得更快。  为什么？  两种版本都应该在相同的时间内将图标移动相同的空间。  在 "性能" 面板中进行录制，了解如何检测未优化版本中的性能瓶颈。  

1.  在 DevTools 中，选择 " **Record** " (！录制[ImageRecordIcon] \ ) 。  页面运行时，DevTools 将捕获效果指标。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-profiling.msft.png" alt-text="分析页面" lightbox="../media/evaluate-performance-performance-profiling.msft.png":::
       分析页面  
    :::image-end:::  
    
1.  稍等几秒钟。  
1.  选择 " **停止**"。  DevTools 停止录制，处理数据，然后在 "性能" 面板上显示结果。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-capture-results.msft.png" alt-text="配置文件的结果" lightbox="../media/evaluate-performance-performance-capture-results.msft.png":::
       配置文件的结果  
    :::image-end:::  
    
哇，那是海量数据。  不要担心，此过程很快就会更有意义。  

## 分析结果  

记录页面性能后，测量页面性能的质量并找到任何原因。  

### 分析每秒帧数  

用于测量任何动画效果的主要指标是每秒的帧\(FPS\)。  当动画以 60 FPS运行时，用户会觉得很享受。  

1.  查看 **FPS** 图表。  每当你在** FPS **上方看到红色条时，表示帧速率下降得太低，以至于可能损害用户体验。  通常，绿色条越高，FPS 越高。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-fps-chart.msft.png" alt-text="FPS 图表" lightbox="../media/evaluate-performance-performance-fps-chart.msft.png":::
       **FPS**图表  
    :::image-end:::  
    
1.  在 **FPS** 图表下方，你将看到 **CPU** 图表。  **CPU** 图表中的颜色对应于 "性能" 面板底部 "**摘要**" 选项卡中的 "颜色"。  **CPU** 图表充满颜色意味着在录制过程中 CPU 已达到极限。  每当你看到 CPU 长时间处于满负荷状态时，就是提示你应该找到减少工作量的方法。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-cpu-chart.msft.png" alt-text="CPU 图表和摘要选项卡" lightbox="../media/evaluate-performance-performance-cpu-chart.msft.png":::
       **CPU**图表和**摘要**选项卡  
    :::image-end:::  
    
1.  将鼠标悬停在 " **FPS**"、" **CPU**" 或 " **网络** " 图表上。  DevTools 将显示该时间点处的页面截图。  左右移动鼠标以重播录音。  该操作作为 "清理" 引用，并且对于手动分析动画进度非常有用。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-screenshot-hover.msft.png" alt-text="在录制的2500ms 标记周围查看页面的屏幕截图" lightbox="../media/evaluate-performance-performance-screenshot-hover.msft.png":::
       在录制的2500ms 标记周围查看页面的屏幕截图  
    :::image-end:::  
    
1.  在 " **框架** " 部分中，将鼠标悬停在绿色方块之一。  DevTools 将显示该特定帧的 FPS。  每帧可能远低于 60 FPS的目标。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-frame-hover.msft.png" alt-text="将鼠标悬停在框架上" lightbox="../media/evaluate-performance-performance-frame-hover.msft.png":::
       将鼠标悬停在框架上  
    :::image-end:::  
    
当然，您应该会看到页面的性能不佳。  但在实际情况下，它可能不是很清楚，因此，让度量的所有工具都很方便。  

#### 附赠：打开 FPS 计数  

另一个非常方便的工具是 FPS 计数，可在页面运行时提供对 FPS 的实时估计。  

1.  选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。  
1.  开始 `Rendering` 在 " **命令" 菜单** 中键入，然后选择 " **显示呈现**"。  
1.  在 "**绘制**" 选项卡上，启用 **FPS 计数**。  新的叠加层将显示在视线的右上角。  
    
    :::image type="complex" source="../media/evaluate-performance-fps-meter-overlay.msft.png" alt-text="FPS 计数" lightbox="../media/evaluate-performance-fps-meter-overlay.msft.png":::
       **FPS 指示器**  
        :::image-end:::  
    
1.  禁用 **FPS 指示器** ，然后选择 `Escape` 以关闭 " **呈现** " 选项卡。 在本教程中，您未使用 **FPS 计量** 器。  
    
### 查找瓶颈  

经过测量并验证动画是否工作不好后，下一步是回答 "为什么？" 的问题。  

1.  未选择任何事件时，" **摘要** " 选项卡将显示活动的细目。  页面大部分时间呈现所花费的时间。  由于性能是减少工作量的艺术，因此你的目标是减少花费在进行绘制工作上的时间。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-summary-tab.msft.png" alt-text=""摘要" 选项卡" lightbox="../media/evaluate-performance-performance-summary-tab.msft.png":::
       " **摘要** " 选项卡  
    :::image-end:::  
    
1.  展开**重点**部分。  DevTools 将显示一段时间内主线程上活动的帧图表。  x 轴表示一段时间内的记录。  每个条形表示一个事件。  宽条表示该事件花费了更长的时间。  Y 轴表示调用堆叠。  当你看到事件相互叠加时，表示较高的事件导致较低的事件。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main.msft.png" alt-text="主要部分" lightbox="../media/evaluate-performance-performance-main.msft.png":::
       **主要**部分  
    :::image-end:::  
    
1.  记录中有很多数据。  放大单个事件;在 **概览**上选择、按住和 dragg 光标，这是包括 **fp**、 **CPU**和 **网络** 图表的部分。  "**重点**" 部分和 "**摘要**" 选项卡仅显示录制所选部分的信息。  
    
    :::image type="complex" source="../media/evaluate-performance-performance-main-zoomed.msft.png" alt-text="放大事件" lightbox="../media/evaluate-performance-performance-main-zoomed.msft.png":::
       放大事件  
    :::image-end:::  
    
    > [!NOTE]
    > 要进行缩放的另一种方法是，重点关注 **主要** 部分，选择背景或事件，然后选择 `W` 、、 `A` `S` 或 `D` 。  
    
    1.  专注于 **动画帧引发** 事件的右上角的红色三角形。  只要看到红色三角形，就会出现一条警告，指出可能存在与事件相关的问题。  
    
    > [!NOTE]
    > 每当运行[ `requestAnimationFrame()`回调][MDNWebRequestAnimationFrame]时，就会发生**动画帧触发**事件。  
    
1.  选择 **动画帧激发** 的事件。  "**摘要**" 选项卡现在向你显示有关该事件的信息。  请注意 "**显示**" 链接。  选择后，DevTools 将突出显示发起 **动画帧触发** 事件的事件。  此外，焦点在 **app.js： 95** 链接上。  选择后，将显示源代码中的相关行。
    
    :::image type="complex" source="../media/evaluate-performance-performance-animation-frame-fired.msft.png" alt-text="有关动画帧触发事件的详细信息" lightbox="../media/evaluate-performance-performance-animation-frame-fired.msft.png":::
       有关 **动画帧激发** 事件的详细信息  
    :::image-end:::  
    
    > [!NOTE]
    > 选择事件后，使用箭头键选择其旁边的事件。  
    
1.  在 **app.update** 事件下，有一堆紫色事件。  如果每个紫色事件的宽度更宽，它看起来好像每个事件都有一个红色三角形。  
1.  选择紫色 **布局** 事件之一。  DevTools 在**摘要**选项卡中提供有关事件的更多信息。确实，有关于强制回流\（换句话说，就是布局\）的警告。  
    
1.  在 "**摘要**" 选项卡中，选择 "**布局强制**" 下的 " **app.js： 71** " 链接。  DevTools 将转到强制布局的代码行。  
    
    :::image type="complex" source="../media/evaluate-performance-sources-app-update.msft.png" alt-text="导致强制布局的代码行" lightbox="../media/evaluate-performance-sources-app-update.msft.png":::
       导致强制布局的代码行  
    :::image-end:::  
    
    > [!NOTE]
    > 代码问题是，在每个动画帧中，它会更改每个图标的样式，然后查询页面上每个图标的位置。  由于样式已更改，因此浏览器不知道每个图标位置是否已更改，因此它必须重新布局图标才能计算新位置。  <!--  > See [Avoid forced synchronous layouts][RenderingAvoidSynchronousLayouts] to learn more.  -->
    
<!-- todo: add layouts section when available -->

要了解的很多。  现在，你在分析运行时性能的基本工作流中拥有坚实的基础。  太棒了。  

### 附赠：分析优化的版本  

使用您刚刚学习的工作流和工具，选择演示的 **优化** 以启用优化的代码，执行另一条性能记录，然后分析结果。  从改进的帧数到 **主** 部分中的火焰图中的事件减少，你可以看到应用的优化版本的工作量很少，从而提高性能。  

> [!NOTE]
> 即使优化版本也不是很好，因为它会对 `top` 每个图标的属性进行操作。  更好的方法是保留仅影响合成的属性。  <!--  > See [Use transform and opacity changes for animations][RenderingCompositor] for more information.  -->  

<!--todo: add rendering section when available -->

## 后续步骤

<!--The foundation for understanding performance is the RAIL model.  The RAIL model teaches you the performance metrics that are most important to your users.  
See [Measure Performance With The RAIL Model][RAIL] to learn more.  -->  

若要更轻松地使用 "性能" 面板，请多多操练，所谓熟能生巧。  尝试分析你的页面并分析结果。  如果对结果有任何疑问，请使用 "**发送反馈**" 图标，选择 `Alt` + `Shift` + `I` \ (Windows \ ) ，选择 `Option` + `Shift` + `I` \ (macOS \ ) ，或[tweet DevTools 团队][TwitterEdgeDevtools]。  如果可能，请包括屏幕截图或指向可重现页面的链接。  

:::image type="complex" source="../media/evaluate-performance-feedback-icon.msft.png" alt-text="Microsoft Edge 开发人员工具中的**反馈**图标" lightbox="../media/evaluate-performance-feedback-icon.msft.png":::
   Microsoft Edge DevTools 中的 " **发送反馈** " 图标  
:::image-end:::  

<!-- To really become an expert in runtime performance, you must learn how the browser translates HTML, CSS, and JS into pixels on a screen.  The best place to start is the [Rendering Performance Overview][RenderingPerformance].  [The Anatomy Of A Frame][FrameAnatomy] dives into even more detail.  -->  

最后，可通过多种方法来改善运行时性能。  本文重点介绍一个特定的动画瓶颈，让你通过 "性能" 面板集中浏览，但这只是你可能遇到的多个瓶颈之一。  <!--  The rest of the Rendering Performance series has a lot of good tips for improving various aspects of runtime performance, such as:  -->

<!--
*   [Optimizing JS Execution][RenderingOptimizeJS]  
*   [Reduce The Scope And Complexity Of Style Calculations][RenderingReduceScope]  
*   [Avoid Large, Complex Layouts And Layout Thrashing][RenderingAvoidThrashing]  
*   [Simplify Paint Complexity And Reduce Paint Areas][RenderingSimplifyPaint]  
*   [Stick To Compositor-Only Properties And Manage Layer Count][RenderingManageLayers]  
*   [Debounce Your Input Handlers][RenderingDebounceInputs]  
-->

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
