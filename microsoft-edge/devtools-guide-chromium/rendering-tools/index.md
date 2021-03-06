---
description: 用户期望交互式和流畅的页面。  像素管道中的每个阶段都表示引入 jank 的机会。  了解用于识别和修复减慢运行时性能的常见问题的工具和策略。
title: 分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 646db5b2e88e33b109e5eb3ae01a296bf3a4fb46
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397998"
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

# <a name="analyze-runtime-performance"></a><span data-ttu-id="85d68-106">分析运行时性能</span><span class="sxs-lookup"><span data-stu-id="85d68-106">Analyze runtime performance</span></span>  

<span data-ttu-id="85d68-107">用户期望交互式和流畅的页面。</span><span class="sxs-lookup"><span data-stu-id="85d68-107">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="85d68-108">像素管道中的每个阶段都表示引入 jank 的机会。</span><span class="sxs-lookup"><span data-stu-id="85d68-108">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="85d68-109">了解用于识别和修复减慢运行时性能的常见问题的工具和策略。</span><span class="sxs-lookup"><span data-stu-id="85d68-109">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <a name="summary"></a><span data-ttu-id="85d68-110">摘要</span><span class="sxs-lookup"><span data-stu-id="85d68-110">Summary</span></span>  

*   <span data-ttu-id="85d68-111">不要编写强制浏览器重新计算布局的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="85d68-111">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="85d68-112">分离读取和写入函数，并首先执行读取。</span><span class="sxs-lookup"><span data-stu-id="85d68-112">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="85d68-113">请勿使 CSS 过于复杂。</span><span class="sxs-lookup"><span data-stu-id="85d68-113">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="85d68-114">使用更少的 CSS 并保持 CSS 选择器简单。</span><span class="sxs-lookup"><span data-stu-id="85d68-114">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="85d68-115">尽可能避免布局。</span><span class="sxs-lookup"><span data-stu-id="85d68-115">Avoid layout as much as possible.</span></span>  <span data-ttu-id="85d68-116">选择完全不触发布局的 CSS。</span><span class="sxs-lookup"><span data-stu-id="85d68-116">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="85d68-117">绘制所花的时间可能多于任何其他呈现活动。</span><span class="sxs-lookup"><span data-stu-id="85d68-117">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="85d68-118">注意绘制瓶颈。</span><span class="sxs-lookup"><span data-stu-id="85d68-118">Watch out for paint bottlenecks.</span></span>  
    
## <a name="javascript"></a><span data-ttu-id="85d68-119">JavaScript</span><span class="sxs-lookup"><span data-stu-id="85d68-119">JavaScript</span></span>  

<span data-ttu-id="85d68-120">JavaScript 计算（尤其是触发大量视觉更改的计算）可能会降低应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="85d68-120">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="85d68-121">不要让时间不佳或长时间运行的 JavaScript 干扰用户交互。</span><span class="sxs-lookup"><span data-stu-id="85d68-121">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <a name="javascript-tools"></a><span data-ttu-id="85d68-122">JavaScript：工具</span><span class="sxs-lookup"><span data-stu-id="85d68-122">JavaScript: Tools</span></span>  

<span data-ttu-id="85d68-123">在性能工具 **中** 录制并查找可疑的 `Evaluate Script` 长事件。</span><span class="sxs-lookup"><span data-stu-id="85d68-123">Take a recording in the **Performance** tool and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="85d68-124">如果你在 JavaScript 中非常明显，你可能需要将你的分析介绍到下一个级别并收集 JavaScript CPU 配置文件。</span><span class="sxs-lookup"><span data-stu-id="85d68-124">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="85d68-125">CPU 配置文件显示运行时在页面功能中的使用位置。</span><span class="sxs-lookup"><span data-stu-id="85d68-125">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="85d68-126">了解如何在 Speed Up [JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime]中创建 CPU 配置文件。</span><span class="sxs-lookup"><span data-stu-id="85d68-126">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <a name="javascript-problems"></a><span data-ttu-id="85d68-127">JavaScript：问题</span><span class="sxs-lookup"><span data-stu-id="85d68-127">JavaScript: Problems</span></span>  

<span data-ttu-id="85d68-128">下表介绍了一些常见的 JavaScript 问题和潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="85d68-128">The following table describes some common JavaScript problems and potential solutions.</span></span>  

| <span data-ttu-id="85d68-129">问题</span><span class="sxs-lookup"><span data-stu-id="85d68-129">Problem</span></span> | <span data-ttu-id="85d68-130">示例</span><span class="sxs-lookup"><span data-stu-id="85d68-130">Example</span></span> | <span data-ttu-id="85d68-131">解决方案</span><span class="sxs-lookup"><span data-stu-id="85d68-131">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="85d68-132">影响响应或动画的昂贵输入处理程序。</span><span class="sxs-lookup"><span data-stu-id="85d68-132">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="85d68-133">触摸、视差滚动。</span><span class="sxs-lookup"><span data-stu-id="85d68-133">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="85d68-134">让浏览器处理触摸和滚动，或尽可能晚地绑定侦听器。</span><span class="sxs-lookup"><span data-stu-id="85d68-134">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="85d68-135">导航到 [Paul Paul 的运行时性能清单中的昂贵输入处理程序][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="85d68-135">Navigate to [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="85d68-136">影响响应、动画、加载的时间过长 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="85d68-136">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="85d68-137">用户滚动页面加载后，setTimeout/setInterval。</span><span class="sxs-lookup"><span data-stu-id="85d68-137">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="85d68-138">优化 JavaScript 运行时：使用 `requestAnimationFrame` ，在帧上分布 DOM 操作，使用 [Web 工作人员][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="85d68-138">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="85d68-139">影响响应的长时间运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="85d68-139">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="85d68-140">[DOMContentLoaded 事件][MDNUsingWebWorkers]因 JS 工作而停止。</span><span class="sxs-lookup"><span data-stu-id="85d68-140">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="85d68-141">将纯计算工作移动到 [Web 工作人员][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="85d68-141">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="85d68-142">如果需要 DOM 访问权限，请使用 `requestAnimationFrame` 。</span><span class="sxs-lookup"><span data-stu-id="85d68-142">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--Navigate to [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="85d68-143">影响响应或动画的垃圾脚本。</span><span class="sxs-lookup"><span data-stu-id="85d68-143">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="85d68-144">垃圾收集可能在任何位置发生。</span><span class="sxs-lookup"><span data-stu-id="85d68-144">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="85d68-145">编写更少的垃圾脚本。</span><span class="sxs-lookup"><span data-stu-id="85d68-145">Write less garbage-y scripts.</span></span>  <span data-ttu-id="85d68-146">导航到 [Paul Paul 运行时性能检查表中动画中的垃圾回收][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="85d68-146">Navigate to [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <a name="style"></a><span data-ttu-id="85d68-147">样式</span><span class="sxs-lookup"><span data-stu-id="85d68-147">Style</span></span>  

<span data-ttu-id="85d68-148">样式更改成本昂贵，尤其是在这些更改影响 DOM 中的多个元素时。</span><span class="sxs-lookup"><span data-stu-id="85d68-148">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="85d68-149">每次向元素应用样式时，浏览器都会指出对所有相关元素的影响、重新计算布局和重画。</span><span class="sxs-lookup"><span data-stu-id="85d68-149">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <a name="style-tools"></a><span data-ttu-id="85d68-150">样式：工具</span><span class="sxs-lookup"><span data-stu-id="85d68-150">Style: Tools</span></span>  

<span data-ttu-id="85d68-151">在"性能"工具 **中录制** 。</span><span class="sxs-lookup"><span data-stu-id="85d68-151">Take a recording in the **Performance** tool.</span></span>  <span data-ttu-id="85d68-152">检查录制大型事件 `Recalculate Style` \ (紫色\) 。</span><span class="sxs-lookup"><span data-stu-id="85d68-152">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="85d68-153">选择 `Recalculate Style` 事件以查看详细信息窗格中有关 **它** 的详细信息。</span><span class="sxs-lookup"><span data-stu-id="85d68-153">Choose a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="85d68-154">如果样式更改需要很长时间，则性能会下降。</span><span class="sxs-lookup"><span data-stu-id="85d68-154">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="85d68-155">如果样式计算影响大量元素，则这是另一个有改进空间的区域。</span><span class="sxs-lookup"><span data-stu-id="85d68-155">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="长重新计算样式" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="85d68-157">长重新计算样式</span><span class="sxs-lookup"><span data-stu-id="85d68-157">Long recalculate style</span></span>  
:::image-end:::  

<span data-ttu-id="85d68-158">若要降低事件 `Recalculate Style` 的影响，请：</span><span class="sxs-lookup"><span data-stu-id="85d68-158">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="85d68-159">使用 [CSS 触发器了解][CssTriggers] 哪些 CSS 属性触发布局、绘制和复合。</span><span class="sxs-lookup"><span data-stu-id="85d68-159">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="85d68-160">这些属性对呈现性能的影响最大。</span><span class="sxs-lookup"><span data-stu-id="85d68-160">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="85d68-161">切换到影响较少的属性。</span><span class="sxs-lookup"><span data-stu-id="85d68-161">Switch to properties that have less impact.</span></span>  <!--For more guidance, navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <a name="style-problems"></a><span data-ttu-id="85d68-162">样式：问题</span><span class="sxs-lookup"><span data-stu-id="85d68-162">Style: Problems</span></span>  

<span data-ttu-id="85d68-163">下表介绍了一些常见的样式问题和潜在的解决方案。</span><span class="sxs-lookup"><span data-stu-id="85d68-163">The following table describes some common style problems and potential solutions.</span></span>  

| <span data-ttu-id="85d68-164">问题</span><span class="sxs-lookup"><span data-stu-id="85d68-164">Problem</span></span> | <span data-ttu-id="85d68-165">示例</span><span class="sxs-lookup"><span data-stu-id="85d68-165">Example</span></span> | <span data-ttu-id="85d68-166">解决方案</span><span class="sxs-lookup"><span data-stu-id="85d68-166">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="85d68-167">影响响应或动画的昂贵样式计算。</span><span class="sxs-lookup"><span data-stu-id="85d68-167">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="85d68-168">更改元素几何图形的任何 CSS 属性，如宽度、高度或位置;浏览器检查所有其他元素并重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="85d68-168">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="85d68-169">避免触发布局的 CSS</span><span class="sxs-lookup"><span data-stu-id="85d68-169">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="85d68-170">影响响应或动画的复杂选择器。</span><span class="sxs-lookup"><span data-stu-id="85d68-170">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="85d68-171">嵌套选择器强制浏览器了解所有其他元素（包括父元素和子元素）的所有内容。</span><span class="sxs-lookup"><span data-stu-id="85d68-171">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="85d68-172">只需一个类引用 CSS 中的元素。</span><span class="sxs-lookup"><span data-stu-id="85d68-172">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <a name="layout"></a><span data-ttu-id="85d68-173">布局</span><span class="sxs-lookup"><span data-stu-id="85d68-173">Layout</span></span>  

<span data-ttu-id="85d68-174">布局 (Firefox) 是浏览器计算页面上所有元素的位置和大小的过程。</span><span class="sxs-lookup"><span data-stu-id="85d68-174">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="85d68-175">Web 的布局模型意味着一个元素可能会影响其他元素;例如，元素的宽度通常会影响任何子元素的宽度，等等，一直向上和向下影响 `<body>` 树。</span><span class="sxs-lookup"><span data-stu-id="85d68-175">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="85d68-176">浏览器可能涉及此过程。</span><span class="sxs-lookup"><span data-stu-id="85d68-176">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="85d68-177">作为经验的一般规则，如果在帧完成之前从 DOM 请求返回几何值，你将发现自己具有"强制同步布局"，如果频繁重复或对大型 DOM 树执行，这可能是一个较大的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="85d68-177">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <a name="layout-tools"></a><span data-ttu-id="85d68-178">布局：工具</span><span class="sxs-lookup"><span data-stu-id="85d68-178">Layout: Tools</span></span>  

<span data-ttu-id="85d68-179">" **性能** "窗格标识页面何时导致强制同步布局。</span><span class="sxs-lookup"><span data-stu-id="85d68-179">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="85d68-180">这些事件 `Layout` 用红色条形标记。</span><span class="sxs-lookup"><span data-stu-id="85d68-180">These `Layout` events are marked with red bars.</span></span>  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="强制同步布局" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="85d68-182">强制同步布局</span><span class="sxs-lookup"><span data-stu-id="85d68-182">Forced synchronous layout</span></span>  
:::image-end:::  

<span data-ttu-id="85d68-183">"布局限制"是强制同步布局条件的重复。</span><span class="sxs-lookup"><span data-stu-id="85d68-183">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="85d68-184">当 JavaScript 反复写入 DOM 和从 DOM 中读取时，将发生这种情况，这会强制浏览器一次又一次地重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="85d68-184">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="85d68-185">若要标识布局限制，请查找多个强制同步布局警告的模式。</span><span class="sxs-lookup"><span data-stu-id="85d68-185">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="85d68-186">查看上图。</span><span class="sxs-lookup"><span data-stu-id="85d68-186">Review the previous figure.</span></span>  

### <a name="layout-problems"></a><span data-ttu-id="85d68-187">布局：问题</span><span class="sxs-lookup"><span data-stu-id="85d68-187">Layout: Problems</span></span>  

<span data-ttu-id="85d68-188">下表介绍了一些常见的布局问题和潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="85d68-188">The following table describes some common layout problems and potential solutions.</span></span>  

| <span data-ttu-id="85d68-189">问题</span><span class="sxs-lookup"><span data-stu-id="85d68-189">Problem</span></span> | <span data-ttu-id="85d68-190">示例</span><span class="sxs-lookup"><span data-stu-id="85d68-190">Example</span></span> | <span data-ttu-id="85d68-191">解决方案</span><span class="sxs-lookup"><span data-stu-id="85d68-191">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="85d68-192">影响响应或动画的强制同步布局。</span><span class="sxs-lookup"><span data-stu-id="85d68-192">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="85d68-193">强制浏览器在像素管道中更早地执行布局，从而在呈现过程中重复步骤。</span><span class="sxs-lookup"><span data-stu-id="85d68-193">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="85d68-194">首先批处理样式读取，然后执行任何写入操作。</span><span class="sxs-lookup"><span data-stu-id="85d68-194">Batch your style reads first, then do any writes.</span></span>  <!--Navigate to [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="85d68-195">影响响应或动画的布局长线。</span><span class="sxs-lookup"><span data-stu-id="85d68-195">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="85d68-196">使浏览器进入读写循环的循环，强制浏览器一次又一次地重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="85d68-196">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="85d68-197">使用 FastDom 库自动批量执行 [读写操作][GitHubWilsonpageFastdom]。</span><span class="sxs-lookup"><span data-stu-id="85d68-197">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <a name="paint-and-composite"></a><span data-ttu-id="85d68-198">绘制和复合</span><span class="sxs-lookup"><span data-stu-id="85d68-198">Paint and composite</span></span>  

<span data-ttu-id="85d68-199">绘制是填充像素的过程。</span><span class="sxs-lookup"><span data-stu-id="85d68-199">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="85d68-200">它通常是呈现过程成本最大的部分。</span><span class="sxs-lookup"><span data-stu-id="85d68-200">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="85d68-201">如果你注意到页面未以任何设计方式工作，很可能是存在绘制问题。</span><span class="sxs-lookup"><span data-stu-id="85d68-201">If you noticed that your page is not working as designed in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="85d68-202">合成是页面的绘制部分放在一起以在屏幕上显示的地方。</span><span class="sxs-lookup"><span data-stu-id="85d68-202">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="85d68-203">大多数情况下，如果你坚持使用仅合成器属性，并完全避免绘制，则应该注意到性能有重大改进，但需要注意层数过多。</span><span class="sxs-lookup"><span data-stu-id="85d68-203">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should notice a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--Navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <a name="paint-and-composite-tools"></a><span data-ttu-id="85d68-204">绘制和复合：工具</span><span class="sxs-lookup"><span data-stu-id="85d68-204">Paint and composite: Tools</span></span>  

<span data-ttu-id="85d68-205">想知道绘制需要多久或多久发生一次画？</span><span class="sxs-lookup"><span data-stu-id="85d68-205">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="85d68-206">检查["性能"面板][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]中的"启用高级\*\*\*\* 绘制检测"设置，然后录制。</span><span class="sxs-lookup"><span data-stu-id="85d68-206">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="85d68-207">如果大部分呈现时间都用于绘制，则存在绘制问题。</span><span class="sxs-lookup"><span data-stu-id="85d68-207">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <a name="paint-and-composite-problems"></a><span data-ttu-id="85d68-208">绘制和复合：问题</span><span class="sxs-lookup"><span data-stu-id="85d68-208">Paint and composite: Problems</span></span>  

<span data-ttu-id="85d68-209">下表介绍了一些常见的绘制和复合问题以及潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="85d68-209">The following table describes some common paint and composite problems and potential solutions.</span></span>  

| <span data-ttu-id="85d68-210">问题</span><span class="sxs-lookup"><span data-stu-id="85d68-210">Problem</span></span> | <span data-ttu-id="85d68-211">示例</span><span class="sxs-lookup"><span data-stu-id="85d68-211">Example</span></span> | <span data-ttu-id="85d68-212">解决方案</span><span class="sxs-lookup"><span data-stu-id="85d68-212">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="85d68-213">影响响应或动画的绘制风暴。</span><span class="sxs-lookup"><span data-stu-id="85d68-213">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="85d68-214">影响响应或动画的较大绘制区域或昂贵的绘制。</span><span class="sxs-lookup"><span data-stu-id="85d68-214">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="85d68-215">避免绘制、升级要移动到其自己的图层的元素、使用转换和不透明度。</span><span class="sxs-lookup"><span data-stu-id="85d68-215">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--Navigate to [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="85d68-216">影响动画的层分解。</span><span class="sxs-lookup"><span data-stu-id="85d68-216">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="85d68-217">过多元素的过度提升会 `translateZ(0)` 大大影响动画性能。</span><span class="sxs-lookup"><span data-stu-id="85d68-217">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="85d68-218">尽量少地提升为层，并且只有在你知道它提供实际改进时才能提升。</span><span class="sxs-lookup"><span data-stu-id="85d68-218">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--Navigate to [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="85d68-219">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="85d68-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "加快 JavaScript 运行时|Microsoft Docs"  
[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#turn-on-advanced-paint-instrumentation "打开高级绘制检测 - 性能分析参考|Microsoft Docs"

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

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "使用 Web 工作人员|MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "运行时性能清单 - Web 性能日历"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "wilsonpage/fastdom |GitHub"  

> [!NOTE]
> <span data-ttu-id="85d68-226">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="85d68-226">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="85d68-227">原始页面位于此处，[](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)由[一位（][KayceBasques]该链接人）\ (Technical Writer、Chrome DevTools \& Lighthouse\) 和[Meggin Kearney][MegginKearney] \ (Tech Writer\) 创作。</span><span class="sxs-lookup"><span data-stu-id="85d68-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="85d68-229">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="85d68-229">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
