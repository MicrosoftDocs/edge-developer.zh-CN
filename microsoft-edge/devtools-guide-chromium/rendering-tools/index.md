---
description: 用户需要交互式页面和平滑页面。  像素管道中的每个阶段都表示引入 jank 的商机。  了解用于识别和修复降低运行时性能的常见问题的工具和策略。
title: 分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: f7ca848712268110700fac2c5fb75fe1751812bf
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992701"
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

# 分析运行时性能 

用户需要交互式页面和平滑页面。  像素管道中的每个阶段都表示引入 jank 的商机。  了解用于识别和修复降低运行时性能的常见问题的工具和策略。  

### 摘要  

*   不要编写强制浏览器重新计算布局的 JavaScript。  单独读取和写入函数，并首先执行读取操作。  
*   不要过度复杂地处理您的 CSS。  使用较少的 CSS，让你的 CSS 选择器更简单。  
*   尽可能避免布局。  选择根本不触发布局的 CSS。  
*   绘制可能比任何其他呈现活动占用更多的时间。  注意绘制瓶颈。  
    
## JavaScript  

JavaScript 计算（尤其是触发大量视觉变化的情况）可能会延迟应用程序性能。  不要让错误计时或长时间运行的 JavaScript 干扰用户交互。  

### JavaScript：工具  

在 " **性能** " 面板中记笔记，并查找可疑的长 `Evaluate Script` 事件。  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

f 你注意到你的 JavaScript 中有很多 jank，你可能需要分析到下一级别并收集 JavaScript CPU 配置文件。  CPU 配置文件显示运行时在页面的功能中所用的位置。  了解如何在 [加速 JavaScript 运行时][DevtoolsRenderingToolsJavascriptRuntime]中创建 CPU 配置文件。

### JavaScript：问题  

下表介绍了一些常见的 JavaScript 问题和可能的解决方案：  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 影响响应或动画的昂贵输入处理程序。  | 触摸，视差滚动。  | 让浏览器处理触摸并滚动，或者尽可能晚地绑定侦听器。  查看 [Paul Lewis "运行时性能清单" 中的昂贵输入处理程序][WebPerformanceCalendarRuntimeChecklist]。  |  
| 影响响应、动画和加载的 JavaScript 计时错误。  | 用户在页面加载、setTimeout/setInterval 后立即滚动。  | 优化 JavaScript 运行时：使用 `requestAnimationFrame` ，在整个框架上分配 DOM 操作，使用 [Web 工作人员][MDNUsingWebWorkers]。  |  
| 长时间运行的 JavaScript 会影响响应。  | [DOMContentLoaded 事件][MDNUsingWebWorkers]将在使用 JS 工作塞满时停止。  | 将纯计算工作移动到 [Web 工作人员][MDNUsingWebWorkers]。  如果需要 DOM 访问权限，请使用 `requestAnimationFrame` 。  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| 影响响应或动画的垃圾 y 脚本。  | 垃圾回收可能发生在任何位置。  | 编写较少的垃圾脚本。  请参阅 [Paul Lewis "运行时性能清单"][WebPerformanceCalendarRuntimeChecklist]中的动画中的垃圾回收。  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## 样式  

样式更改成本很高，尤其是当这些更改影响 DOM 中的多个元素时。  无论何时对元素应用样式，浏览器都将计算出对所有相关元素的影响，重新计算布局，然后重新绘制。  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### 样式：工具  

在 " **性能** " 面板中记笔记。  检查录制中是否有较大 `Recalculate Style` 的事件 \ (显示为紫色 \ ) 。  

<!--todo: add Recording section when available  -->  

单击 `Recalculate Style` 事件可在 **详细** 信息窗格中查看有关它的详细信息。  如果样式更改花费很长时间，则会影响性能。  如果样式计算影响大量元素，这是一个具有空间以改进的另一个区域。  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="较长的重新计算样式" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   较长的重新计算样式  
:::image-end:::  

要减少事件的影响，请 `Recalculate Style` 执行以下操作：  

*   使用 [CSS 触发器][CssTriggers] 了解哪些 CSS 属性会触发布局、画图和复合。  这些属性对呈现性能有最严重的影响。  
*   切换到影响较少的属性。  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### 样式：问题  

下表介绍了一些常见的样式问题和可能的解决方案：  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 影响响应或动画的昂贵的样式计算。  | 更改元素的几何图形（如宽度、高度或位置）的任何 CSS 属性;浏览器检查所有其他元素并重新计算布局。  | 避免触发布局的 CSS |  
| 影响响应或动画的复杂选择器。  | 嵌套的选择器强制浏览器了解所有其他元素（包括父级和子级）的所有内容。  | 仅使用类引用 CSS 中的元素。  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## 布局  

在 Firefox) 中 (或重排布局是浏览器计算页面上所有元素的位置和大小的过程。  Web 布局模型意味着一个元素可能会影响其他元素;例如，元素的宽度 `<body>` 通常影响任何子元素的宽度，依此类推，在树中向上和向下。  该过程可能会非常适用于浏览器。  

作为一般经验法则，如果你在帧完成之前要求从 DOM 返回几何值，你将发现你有 "强制同步布局"，如果频繁地重复或执行大型 DOM 树，则可能会产生大性能瓶颈。  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### 布局：工具  

" **性能** " 窗格标识页面何时导致强制同步布局。  这些 `Layout` 事件标有红条。  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="强制同步布局" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   强制同步布局  
:::image-end:::  

"布局失效" 是强制执行同步布局条件的重复。  这会在 JavaScript 重复写入和读取 DOM 时发生，从而强制浏览器重新计算布局。  若要识别布局失效，请查看多个强制同步布局警告的模式。  请参阅上图。  

### 布局：问题  

下表介绍了一些常见布局问题和可能的解决方案：  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 影响响应或动画的强制同步布局。  | 强制浏览器在像素管道前面执行布局，从而在呈现过程中产生重复步骤。  | 将首先读取样式，然后执行任何写操作。  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| 影响响应或动画的布局失效。  | 将浏览器置于读写读写循环中的循环，强制浏览器重新计算布局。  | 使用 [FastDom 库][GitHubWilsonpageFastdom]自动批处理读写操作。  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## 画图和复合  

"画图" 是填充像素的过程。  它通常是呈现过程中最昂贵的部分。  如果你注意到你的页面是以任何方式 janky 的，则可能是你遇到了画图问题。  

合成是指将页面的绘制部分放置在屏幕上以显示在屏幕上的位置。  在大多数情况下，如果您仅坚持使用组合器的属性并避免画图，您应该可以看到性能的显著改进，但需要注意大量的层计数。  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### 画图和复合：工具  

想要了解绘制所需的时间或绘图的频率是多少？  选中 "**性能**" 面板中的 "[启用高级画图检测][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]" 设置，然后进行录制。  如果大多数渲染时间都花在绘图上，则您遇到了画图问题。  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### 画图和复合：问题  

下表介绍了一些常见的画图和复合问题以及可能的解决方案：  

| 问题 | 示例 | 解决方案 |  
|:--- |:--- |:--- |  
| 绘制影响响应或动画的风暴。  | 大型油漆区域或影响响应或动画的昂贵油漆。  | 避免使用 "画图"，提升移动到自己的图层的元素，使用转换和不透明度。  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| 影响动画的图层爆发。  | Overpromotion `translateZ(0)` 严重影响动画性能的元素太多。  | 谨慎地推广图层，仅当您知道它可以提供有形改进时。  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "加速 JavaScript 运行时 |Microsoft 文档"  
[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#enable-advanced-paint-instrumentation "启用高级画图检测-性能分析参考 |Microsoft 文档"

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

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作人员 |MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "运行时性能清单-Web 性能日历"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "wilsonpage/fastdom |GitHub"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Meggin Kearney][MegginKearney] \ (技术作者 \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
