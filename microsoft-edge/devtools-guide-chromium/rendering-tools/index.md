---
description: 用户期望交互式和流畅的页面。  像素管道中的每个阶段都代表引入 jank 的机会。  了解用于识别和修复降低运行时性能的常见问题的工具和策略。
title: 分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: d5c37c188ae9038a7baafc936d2a02299def6366
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564705"
---
<!-- Copyright Kayce Basques and Meggin Kearney

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="analyze-runtime-performance"></a>分析运行时性能  

用户期望交互式和流畅的页面。  像素管道中的每个阶段都代表引入 jank 的机会。  了解用于识别和修复降低运行时性能的常见问题的工具和策略。  

### <a name="summary"></a>摘要  

*   不要编写强制浏览器重新计算布局的 JavaScript。  分离读取和写入函数，并首先执行读取。  
*   请勿使 CSS 过于复杂。  使用更少的 CSS 并保持 CSS 选择器简单。  
*   尽可能避免布局。  选择完全不触发布局的 CSS。  
*   绘制所花的时间可能多于任何其他呈现活动。  注意画图瓶颈。  
    
## <a name="javascript"></a>JavaScript  

JavaScript 计算（尤其是触发大量视觉更改的计算）可能会降低应用程序性能。  不要让时间不当时或长时间运行的 JavaScript 干扰用户交互。  

### <a name="javascript-tools"></a>JavaScript：工具  

在性能工具 **中** 录制并查找可疑的 `Evaluate Script` 长事件。  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

如果你未在 JavaScript 中十分明显，你可能需要将你的分析介绍到下一个级别并收集 JavaScript CPU 配置文件。  CPU 配置文件显示运行时在页面函数中的使用位置。  了解如何在 Speed Up [JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime]中创建 CPU 配置文件。

### <a name="javascript-problems"></a>JavaScript：问题  

下表介绍了一些常见的 JavaScript 问题和潜在解决方案。  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 影响响应或动画的昂贵输入处理程序。  | 触摸，视差滚动。  | 让浏览器处理触摸和滚动，或尽可能晚地绑定侦听器。  导航到 [Paul 的运行时性能清单中的高成本输入处理程序][WebPerformanceCalendarRuntimeChecklist]。  |  
| 影响响应、动画、加载的时间过长的 JavaScript。  | 用户在页面加载后向右滚动 setTimeout / setInterval。  | 优化 JavaScript 运行时：使用 `requestAnimationFrame` ，在帧上分布 DOM 操作，使用 [Web Workers][MDNUsingWebWorkers]。  |  
| 影响响应的长时间运行的 JavaScript。  | [DOMContentLoaded 事件][MDNUsingWebWorkers]因使用 JS 工作而停止。  | 将纯计算工作移动到 [Web 工作人员][MDNUsingWebWorkers]。  如果需要 DOM 访问权限，请使用 `requestAnimationFrame` 。  <!--Navigate to [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| 影响响应或动画的垃圾脚本。  | 垃圾收集可能在任意位置发生。  | 编写更少的垃圾脚本。  导航到 [Paul Paul 的运行时性能清单中的动画中的垃圾回收][WebPerformanceCalendarRuntimeChecklist]。  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <a name="style"></a>样式  

样式更改会非常昂贵，尤其是在这些更改影响 DOM 中的多个元素时。  每次向元素应用样式时，浏览器都会指出对所有相关元素的影响、重新计算布局和重画。  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <a name="style-tools"></a>样式：工具  

在"性能"工具 **中录制** 。  检查录制大事件 `Recalculate Style` \ (以紫色\) 。  

<!--todo: add Recording section when available  -->  

在 `Recalculate Style` "详细信息"窗格中选择一个事件以查看其 **详细信息** 。  如果样式更改需要很长时间，则性能会下降。  如果样式计算影响大量元素，则这是另一个有改进空间的区域。  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="长重新计算样式" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   长重新计算样式  
:::image-end:::  

若要降低事件 `Recalculate Style` 的影响，请：  

*   使用 [CSS 触发器了解][CssTriggers] 哪些 CSS 属性触发器布局、绘制和复合。  这些属性对呈现性能的影响最大。  
*   切换到影响较少的属性。  <!--For more guidance, navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <a name="style-problems"></a>样式：问题  

下表介绍了一些常见的样式问题和潜在解决方案。  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 影响响应或动画的昂贵样式计算。  | 更改元素几何图形（如宽度、高度或位置）的任何 CSS 属性;浏览器检查所有其他元素并重新计算布局。  | 避免触发布局的 CSS |  
| 影响响应或动画的复杂选择器。  | 嵌套选择器强制浏览器了解所有其他元素（包括父元素和子元素）的所有信息。  | 只需一个类引用 CSS 中的元素。  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <a name="layout"></a>布局  

Firefox (或重排) 是浏览器计算页面上所有元素的位置和大小的过程。  Web 的布局模型意味着一个元素可能会影响其他元素;例如，元素的宽度通常会影响任何子元素的宽度，等等，一直向上和向下 `<body>` 影响树。  浏览器可能涉及此过程。  

作为经验法则，如果你在帧完成之前要求从 DOM 返回几何值，你将发现自己具有"强制同步布局"，如果频繁重复或对大型 DOM 树执行，这可能是一个较大的性能瓶颈。  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <a name="layout-tools"></a>布局：工具  

" **性能** "窗格标识页面何时导致强制同步布局。  `Layout`这些事件用红色条标记。  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="强制同步布局" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   强制同步布局  
:::image-end:::  

"布局分隔"是强制同步布局条件的重复。  当 JavaScript 重复写入和读取 DOM 时，会出现此情况，这会强制浏览器重新计算一次又一次布局。  若要标识布局限制，请查找多个强制同步布局警告的模式。  查看上图。  

### <a name="layout-problems"></a>布局：问题  

下表介绍了一些常见的布局问题和潜在解决方案。  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 影响响应或动画的强制同步布局。  | 强制浏览器在像素管道中更早地执行布局，从而在呈现过程中重复步骤。  | 首先批量读取样式，然后执行任何写入操作。  <!--Navigate to [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| 影响响应或动画的布局长线。  | 使浏览器进入读写循环的循环，强制浏览器一次又一次地重新计算布局。  | 使用 FastDom 库自动批处理 [读写操作][GitHubWilsonpageFastdom]。  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <a name="paint-and-composite"></a>画图和复合  

画图是填充像素的过程。  它通常是呈现过程成本最大的部分。  如果你注意到你的页面未以任何设计方式工作，很可能是有绘制问题。  

合成是页面的绘制部分组合在一起以在屏幕上显示的地方。  大多数情况下，如果你坚持使用仅合成器属性，并且完全避免绘制，你应该注意到性能有显著改进，但需要留意层数过多。  <!--Navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <a name="paint-and-composite-tools"></a>画图和复合：工具  

想知道绘制需要多久或多久发生一次画？  选中" [性能"面板][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] 中的" **启用高级画** 图检测"设置，然后录制。  如果大多数呈现时间都用于绘制，则存在绘制问题。  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <a name="paint-and-composite-problems"></a>画图和复合：问题  

下表介绍了一些常见的绘制和复合问题以及潜在的解决方案。  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 画图响应或动画的风暴。  | 影响响应或动画的大画区或昂贵的画图。  | 避免绘制、升级要移动到其自己的图层的元素、使用转换和不透明度。  <!--Navigate to [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| 影响动画的层爆炸。  | 过多元素的过度提示会 `translateZ(0)` 大大影响动画性能。  | 尽量少地提升至层，并且仅在你知道它提供切实改进时。  <!--Navigate to [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "加快 JavaScript 运行时|Microsoft Docs"  
[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#turn-on-advanced-paint-instrumentation "打开高级画图检测 - 性能分析|Microsoft Docs"

<!--[DevtoolsRenderingToolsForcedSynchronousLayouts]: ./rendering-tools/forced-synchronous-layouts.md "Diagnose Forced Synchronous Layouts | Microsoft Docs"  -->  

<!-- The Timeline Tool page is deprecated  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfileJavascript]: ../evaluate-performance/timeline-tool#profile-javascript "Profile JavaScript - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfilePainting]: ../evaluate-performance/timeline-tool#profile-painting "Profile painting - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRecording]: ../evaluate-performance/timeline-tool#make-a-recording "Make a recording - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRenderingSettings]: ../evaluate-performance/timeline-tool#rendering-settings "Rendering settings - How to Use the Timeline Tool | Microsoft Docs"  -->  

<!--[WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]: /web/fundamentals/performance/rendering/avoid-large-complex-layouts-and-layout-thrashing "Avoid Large, Complex Layouts, and Layout Thrashing"  -->  
<!--[WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime]: /web/fundamentals/performance/rendering/optimize-javascript-execution "Optimize JavaScript Runtime"  -->  
<!--[WebFundamentalsPerformanceRenderingReduceScope]: /web/fundamentals/performance/rendering/reduce-the-scope-and-complexity-of-style-calculations "Reduce the Scope and Complexity of Style Calculations"  -->  
<!--[WebFundamentalsPerformanceRenderingSimplifyPaintComplexity]: /web/fundamentals/performance/rendering/simplify-paint-complexity-and-reduce-paint-areas "Simplify Paint Complexity and Reduce Paint Areas"  -->  
<!--[WebFundamentalsPerformanceRenderingCompositorOnlyProperties]: /web/fundamentals/performance/rendering/stick-to-compositor-only-properties-and-manage-layer-count "Stick to Compositor-Only Properties and Manage Layer Count"  -->  

[CssTriggers]: https://csstriggers.com "CSS 触发器"  

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作|MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "运行时性能清单 - Web 性能日历"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "wilsonpage/fastdom |GitHub"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> [此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)可以找到原始页面，由 [Kayce Basques][KayceBasques] \（技术写作人员，Chrome DevTools \& Lighthouse\）和 [Meggin Kearney][MegginKearney] \（技术写作人员\）编写。  

[![知识共享许可协议][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
