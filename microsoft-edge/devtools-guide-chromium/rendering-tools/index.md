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
# <a name="analyze-runtime-performance"></a><span data-ttu-id="aa1bd-106">分析运行时性能</span><span class="sxs-lookup"><span data-stu-id="aa1bd-106">Analyze runtime performance</span></span>  

<span data-ttu-id="aa1bd-107">用户期望交互式和流畅的页面。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-107">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="aa1bd-108">像素管道中的每个阶段都代表引入 jank 的机会。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-108">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="aa1bd-109">了解用于识别和修复降低运行时性能的常见问题的工具和策略。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-109">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <a name="summary"></a><span data-ttu-id="aa1bd-110">摘要</span><span class="sxs-lookup"><span data-stu-id="aa1bd-110">Summary</span></span>  

*   <span data-ttu-id="aa1bd-111">不要编写强制浏览器重新计算布局的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-111">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="aa1bd-112">分离读取和写入函数，并首先执行读取。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-112">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="aa1bd-113">请勿使 CSS 过于复杂。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-113">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="aa1bd-114">使用更少的 CSS 并保持 CSS 选择器简单。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-114">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="aa1bd-115">尽可能避免布局。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-115">Avoid layout as much as possible.</span></span>  <span data-ttu-id="aa1bd-116">选择完全不触发布局的 CSS。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-116">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="aa1bd-117">绘制所花的时间可能多于任何其他呈现活动。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-117">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="aa1bd-118">注意画图瓶颈。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-118">Watch out for paint bottlenecks.</span></span>  
    
## <a name="javascript"></a><span data-ttu-id="aa1bd-119">JavaScript</span><span class="sxs-lookup"><span data-stu-id="aa1bd-119">JavaScript</span></span>  

<span data-ttu-id="aa1bd-120">JavaScript 计算（尤其是触发大量视觉更改的计算）可能会降低应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-120">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="aa1bd-121">不要让时间不当时或长时间运行的 JavaScript 干扰用户交互。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-121">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <a name="javascript-tools"></a><span data-ttu-id="aa1bd-122">JavaScript：工具</span><span class="sxs-lookup"><span data-stu-id="aa1bd-122">JavaScript: Tools</span></span>  

<span data-ttu-id="aa1bd-123">在性能工具 **中** 录制并查找可疑的 `Evaluate Script` 长事件。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-123">Take a recording in the **Performance** tool and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="aa1bd-124">如果你未在 JavaScript 中十分明显，你可能需要将你的分析介绍到下一个级别并收集 JavaScript CPU 配置文件。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-124">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="aa1bd-125">CPU 配置文件显示运行时在页面函数中的使用位置。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-125">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="aa1bd-126">了解如何在 Speed Up [JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime]中创建 CPU 配置文件。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-126">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <a name="javascript-problems"></a><span data-ttu-id="aa1bd-127">JavaScript：问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-127">JavaScript: Problems</span></span>  

<span data-ttu-id="aa1bd-128">下表介绍了一些常见的 JavaScript 问题和潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-128">The following table describes some common JavaScript problems and potential solutions.</span></span>  

| <span data-ttu-id="aa1bd-129">问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-129">Problem</span></span> | <span data-ttu-id="aa1bd-130">示例</span><span class="sxs-lookup"><span data-stu-id="aa1bd-130">Example</span></span> | <span data-ttu-id="aa1bd-131">解决方案</span><span class="sxs-lookup"><span data-stu-id="aa1bd-131">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aa1bd-132">影响响应或动画的昂贵输入处理程序。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-132">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-133">触摸，视差滚动。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-133">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="aa1bd-134">让浏览器处理触摸和滚动，或尽可能晚地绑定侦听器。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-134">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="aa1bd-135">导航到 [Paul 的运行时性能清单中的高成本输入处理程序][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-135">Navigate to [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="aa1bd-136">影响响应、动画、加载的时间过长的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-136">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="aa1bd-137">用户在页面加载后向右滚动 setTimeout / setInterval。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-137">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="aa1bd-138">优化 JavaScript 运行时：使用 `requestAnimationFrame` ，在帧上分布 DOM 操作，使用 [Web Workers][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-138">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="aa1bd-139">影响响应的长时间运行的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-139">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="aa1bd-140">[DOMContentLoaded 事件][MDNUsingWebWorkers]因使用 JS 工作而停止。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-140">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="aa1bd-141">将纯计算工作移动到 [Web 工作人员][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-141">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="aa1bd-142">如果需要 DOM 访问权限，请使用 `requestAnimationFrame` 。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-142">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--Navigate to [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="aa1bd-143">影响响应或动画的垃圾脚本。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-143">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-144">垃圾收集可能在任意位置发生。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-144">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="aa1bd-145">编写更少的垃圾脚本。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-145">Write less garbage-y scripts.</span></span>  <span data-ttu-id="aa1bd-146">导航到 [Paul Paul 的运行时性能清单中的动画中的垃圾回收][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-146">Navigate to [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <a name="style"></a><span data-ttu-id="aa1bd-147">样式</span><span class="sxs-lookup"><span data-stu-id="aa1bd-147">Style</span></span>  

<span data-ttu-id="aa1bd-148">样式更改会非常昂贵，尤其是在这些更改影响 DOM 中的多个元素时。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-148">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="aa1bd-149">每次向元素应用样式时，浏览器都会指出对所有相关元素的影响、重新计算布局和重画。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-149">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <a name="style-tools"></a><span data-ttu-id="aa1bd-150">样式：工具</span><span class="sxs-lookup"><span data-stu-id="aa1bd-150">Style: Tools</span></span>  

<span data-ttu-id="aa1bd-151">在"性能"工具 **中录制** 。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-151">Take a recording in the **Performance** tool.</span></span>  <span data-ttu-id="aa1bd-152">检查录制大事件 `Recalculate Style` \ (以紫色\) 。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-152">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="aa1bd-153">在 `Recalculate Style` "详细信息"窗格中选择一个事件以查看其 **详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-153">Choose a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="aa1bd-154">如果样式更改需要很长时间，则性能会下降。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-154">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="aa1bd-155">如果样式计算影响大量元素，则这是另一个有改进空间的区域。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-155">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="长重新计算样式" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="aa1bd-157">长重新计算样式</span><span class="sxs-lookup"><span data-stu-id="aa1bd-157">Long recalculate style</span></span>  
:::image-end:::  

<span data-ttu-id="aa1bd-158">若要降低事件 `Recalculate Style` 的影响，请：</span><span class="sxs-lookup"><span data-stu-id="aa1bd-158">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="aa1bd-159">使用 [CSS 触发器了解][CssTriggers] 哪些 CSS 属性触发器布局、绘制和复合。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-159">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="aa1bd-160">这些属性对呈现性能的影响最大。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-160">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="aa1bd-161">切换到影响较少的属性。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-161">Switch to properties that have less impact.</span></span>  <!--For more guidance, navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <a name="style-problems"></a><span data-ttu-id="aa1bd-162">样式：问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-162">Style: Problems</span></span>  

<span data-ttu-id="aa1bd-163">下表介绍了一些常见的样式问题和潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-163">The following table describes some common style problems and potential solutions.</span></span>  

| <span data-ttu-id="aa1bd-164">问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-164">Problem</span></span> | <span data-ttu-id="aa1bd-165">示例</span><span class="sxs-lookup"><span data-stu-id="aa1bd-165">Example</span></span> | <span data-ttu-id="aa1bd-166">解决方案</span><span class="sxs-lookup"><span data-stu-id="aa1bd-166">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aa1bd-167">影响响应或动画的昂贵样式计算。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-167">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-168">更改元素几何图形（如宽度、高度或位置）的任何 CSS 属性;浏览器检查所有其他元素并重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-168">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="aa1bd-169">避免触发布局的 CSS</span><span class="sxs-lookup"><span data-stu-id="aa1bd-169">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="aa1bd-170">影响响应或动画的复杂选择器。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-170">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-171">嵌套选择器强制浏览器了解所有其他元素（包括父元素和子元素）的所有信息。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-171">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="aa1bd-172">只需一个类引用 CSS 中的元素。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-172">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <a name="layout"></a><span data-ttu-id="aa1bd-173">布局</span><span class="sxs-lookup"><span data-stu-id="aa1bd-173">Layout</span></span>  

<span data-ttu-id="aa1bd-174">Firefox (或重排) 是浏览器计算页面上所有元素的位置和大小的过程。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-174">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="aa1bd-175">Web 的布局模型意味着一个元素可能会影响其他元素;例如，元素的宽度通常会影响任何子元素的宽度，等等，一直向上和向下 `<body>` 影响树。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-175">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="aa1bd-176">浏览器可能涉及此过程。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-176">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="aa1bd-177">作为经验法则，如果你在帧完成之前要求从 DOM 返回几何值，你将发现自己具有"强制同步布局"，如果频繁重复或对大型 DOM 树执行，这可能是一个较大的性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-177">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <a name="layout-tools"></a><span data-ttu-id="aa1bd-178">布局：工具</span><span class="sxs-lookup"><span data-stu-id="aa1bd-178">Layout: Tools</span></span>  

<span data-ttu-id="aa1bd-179">" **性能** "窗格标识页面何时导致强制同步布局。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-179">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="aa1bd-180">`Layout`这些事件用红色条标记。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-180">These `Layout` events are marked with red bars.</span></span>  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="强制同步布局" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="aa1bd-182">强制同步布局</span><span class="sxs-lookup"><span data-stu-id="aa1bd-182">Forced synchronous layout</span></span>  
:::image-end:::  

<span data-ttu-id="aa1bd-183">"布局分隔"是强制同步布局条件的重复。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-183">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="aa1bd-184">当 JavaScript 重复写入和读取 DOM 时，会出现此情况，这会强制浏览器重新计算一次又一次布局。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-184">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="aa1bd-185">若要标识布局限制，请查找多个强制同步布局警告的模式。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-185">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="aa1bd-186">查看上图。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-186">Review the previous figure.</span></span>  

### <a name="layout-problems"></a><span data-ttu-id="aa1bd-187">布局：问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-187">Layout: Problems</span></span>  

<span data-ttu-id="aa1bd-188">下表介绍了一些常见的布局问题和潜在解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-188">The following table describes some common layout problems and potential solutions.</span></span>  

| <span data-ttu-id="aa1bd-189">问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-189">Problem</span></span> | <span data-ttu-id="aa1bd-190">示例</span><span class="sxs-lookup"><span data-stu-id="aa1bd-190">Example</span></span> | <span data-ttu-id="aa1bd-191">解决方案</span><span class="sxs-lookup"><span data-stu-id="aa1bd-191">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aa1bd-192">影响响应或动画的强制同步布局。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-192">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-193">强制浏览器在像素管道中更早地执行布局，从而在呈现过程中重复步骤。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-193">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="aa1bd-194">首先批量读取样式，然后执行任何写入操作。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-194">Batch your style reads first, then do any writes.</span></span>  <!--Navigate to [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="aa1bd-195">影响响应或动画的布局长线。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-195">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-196">使浏览器进入读写循环的循环，强制浏览器一次又一次地重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-196">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="aa1bd-197">使用 FastDom 库自动批处理 [读写操作][GitHubWilsonpageFastdom]。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-197">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <a name="paint-and-composite"></a><span data-ttu-id="aa1bd-198">画图和复合</span><span class="sxs-lookup"><span data-stu-id="aa1bd-198">Paint and composite</span></span>  

<span data-ttu-id="aa1bd-199">画图是填充像素的过程。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-199">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="aa1bd-200">它通常是呈现过程成本最大的部分。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-200">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="aa1bd-201">如果你注意到你的页面未以任何设计方式工作，很可能是有绘制问题。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-201">If you noticed that your page is not working as designed in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="aa1bd-202">合成是页面的绘制部分组合在一起以在屏幕上显示的地方。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-202">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="aa1bd-203">大多数情况下，如果你坚持使用仅合成器属性，并且完全避免绘制，你应该注意到性能有显著改进，但需要留意层数过多。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-203">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should notice a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--Navigate to [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <a name="paint-and-composite-tools"></a><span data-ttu-id="aa1bd-204">画图和复合：工具</span><span class="sxs-lookup"><span data-stu-id="aa1bd-204">Paint and composite: Tools</span></span>  

<span data-ttu-id="aa1bd-205">想知道绘制需要多久或多久发生一次画？</span><span class="sxs-lookup"><span data-stu-id="aa1bd-205">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="aa1bd-206">选中" [性能"面板][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] 中的" **启用高级画** 图检测"设置，然后录制。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-206">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="aa1bd-207">如果大多数呈现时间都用于绘制，则存在绘制问题。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-207">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <a name="paint-and-composite-problems"></a><span data-ttu-id="aa1bd-208">画图和复合：问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-208">Paint and composite: Problems</span></span>  

<span data-ttu-id="aa1bd-209">下表介绍了一些常见的绘制和复合问题以及潜在的解决方案。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-209">The following table describes some common paint and composite problems and potential solutions.</span></span>  

| <span data-ttu-id="aa1bd-210">问题</span><span class="sxs-lookup"><span data-stu-id="aa1bd-210">Problem</span></span> | <span data-ttu-id="aa1bd-211">示例</span><span class="sxs-lookup"><span data-stu-id="aa1bd-211">Example</span></span> | <span data-ttu-id="aa1bd-212">解决方案</span><span class="sxs-lookup"><span data-stu-id="aa1bd-212">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="aa1bd-213">画图响应或动画的风暴。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-213">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-214">影响响应或动画的大画区或昂贵的画图。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-214">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="aa1bd-215">避免绘制、升级要移动到其自己的图层的元素、使用转换和不透明度。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-215">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--Navigate to [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="aa1bd-216">影响动画的层爆炸。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-216">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="aa1bd-217">过多元素的过度提示会 `translateZ(0)` 大大影响动画性能。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-217">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="aa1bd-218">尽量少地提升至层，并且仅在你知道它提供切实改进时。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-218">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--Navigate to [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="aa1bd-219">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="aa1bd-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

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
> <span data-ttu-id="aa1bd-226">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-226">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="aa1bd-227">[此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index)可以找到原始页面，由 [Kayce Basques][KayceBasques] \（技术写作人员，Chrome DevTools \& Lighthouse\）和 [Meggin Kearney][MegginKearney] \（技术写作人员\）编写。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![知识共享许可协议][CCby4Image]][CCA4IL]  
<span data-ttu-id="aa1bd-229">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="aa1bd-229">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
