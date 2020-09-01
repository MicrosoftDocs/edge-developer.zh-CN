---
title: 分析运行时性能
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 5f1a4125cfea1c582a76469ae7c9cd1ca75f0b00
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10984922"
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





# <span data-ttu-id="8651b-103">分析运行时性能</span><span class="sxs-lookup"><span data-stu-id="8651b-103">Analyze runtime performance</span></span>   




<span data-ttu-id="8651b-104">用户需要交互式页面和平滑页面。</span><span class="sxs-lookup"><span data-stu-id="8651b-104">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="8651b-105">像素管道中的每个阶段都表示引入 jank 的商机。</span><span class="sxs-lookup"><span data-stu-id="8651b-105">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="8651b-106">了解用于识别和修复降低运行时性能的常见问题的工具和策略。</span><span class="sxs-lookup"><span data-stu-id="8651b-106">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <span data-ttu-id="8651b-107">摘要</span><span class="sxs-lookup"><span data-stu-id="8651b-107">Summary</span></span>  

*   <span data-ttu-id="8651b-108">不要编写强制浏览器重新计算布局的 JavaScript。</span><span class="sxs-lookup"><span data-stu-id="8651b-108">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="8651b-109">单独读取和写入函数，并首先执行读取操作。</span><span class="sxs-lookup"><span data-stu-id="8651b-109">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="8651b-110">不要过度复杂地处理您的 CSS。</span><span class="sxs-lookup"><span data-stu-id="8651b-110">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="8651b-111">使用较少的 CSS，让你的 CSS 选择器更简单。</span><span class="sxs-lookup"><span data-stu-id="8651b-111">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="8651b-112">尽可能避免布局。</span><span class="sxs-lookup"><span data-stu-id="8651b-112">Avoid layout as much as possible.</span></span>  <span data-ttu-id="8651b-113">选择根本不触发布局的 CSS。</span><span class="sxs-lookup"><span data-stu-id="8651b-113">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="8651b-114">绘制可能比任何其他呈现活动占用更多的时间。</span><span class="sxs-lookup"><span data-stu-id="8651b-114">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="8651b-115">注意绘制瓶颈。</span><span class="sxs-lookup"><span data-stu-id="8651b-115">Watch out for paint bottlenecks.</span></span>  
    
## <span data-ttu-id="8651b-116">JavaScript</span><span class="sxs-lookup"><span data-stu-id="8651b-116">JavaScript</span></span>  

<span data-ttu-id="8651b-117">JavaScript 计算（尤其是触发大量视觉变化的情况）可能会延迟应用程序性能。</span><span class="sxs-lookup"><span data-stu-id="8651b-117">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="8651b-118">不要让错误计时或长时间运行的 JavaScript 干扰用户交互。</span><span class="sxs-lookup"><span data-stu-id="8651b-118">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <span data-ttu-id="8651b-119">JavaScript：工具</span><span class="sxs-lookup"><span data-stu-id="8651b-119">JavaScript: Tools</span></span>  

<span data-ttu-id="8651b-120">在 " **性能** " 面板中记笔记，并查找可疑的长 `Evaluate Script` 事件。</span><span class="sxs-lookup"><span data-stu-id="8651b-120">Take a recording in the **Performance** panel and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="8651b-121">f 你注意到你的 JavaScript 中有很多 jank，你可能需要分析到下一级别并收集 JavaScript CPU 配置文件。</span><span class="sxs-lookup"><span data-stu-id="8651b-121">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="8651b-122">CPU 配置文件显示运行时在页面的功能中所用的位置。</span><span class="sxs-lookup"><span data-stu-id="8651b-122">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="8651b-123">了解如何在 [加速 JavaScript 运行时][DevtoolsRenderingToolsJavascriptRuntime]中创建 CPU 配置文件。</span><span class="sxs-lookup"><span data-stu-id="8651b-123">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <span data-ttu-id="8651b-124">JavaScript：问题</span><span class="sxs-lookup"><span data-stu-id="8651b-124">JavaScript: Problems</span></span>  

<span data-ttu-id="8651b-125">下表介绍了一些常见的 JavaScript 问题和可能的解决方案：</span><span class="sxs-lookup"><span data-stu-id="8651b-125">The following table describes some common JavaScript problems and potential solutions:</span></span>  

| <span data-ttu-id="8651b-126">问题</span><span class="sxs-lookup"><span data-stu-id="8651b-126">Problem</span></span> | <span data-ttu-id="8651b-127">示例</span><span class="sxs-lookup"><span data-stu-id="8651b-127">Example</span></span> | <span data-ttu-id="8651b-128">解决方案</span><span class="sxs-lookup"><span data-stu-id="8651b-128">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="8651b-129">影响响应或动画的昂贵输入处理程序。</span><span class="sxs-lookup"><span data-stu-id="8651b-129">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="8651b-130">触摸，视差滚动。</span><span class="sxs-lookup"><span data-stu-id="8651b-130">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="8651b-131">让浏览器处理触摸并滚动，或者尽可能晚地绑定侦听器。</span><span class="sxs-lookup"><span data-stu-id="8651b-131">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="8651b-132">查看 [Paul Lewis "运行时性能清单" 中的昂贵输入处理程序][WebPerformanceCalendarRuntimeChecklist]。</span><span class="sxs-lookup"><span data-stu-id="8651b-132">See [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="8651b-133">影响响应、动画和加载的 JavaScript 计时错误。</span><span class="sxs-lookup"><span data-stu-id="8651b-133">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="8651b-134">用户在页面加载、setTimeout/setInterval 后立即滚动。</span><span class="sxs-lookup"><span data-stu-id="8651b-134">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="8651b-135">优化 JavaScript 运行时：使用 `requestAnimationFrame` ，在整个框架上分配 DOM 操作，使用 [Web 工作人员][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="8651b-135">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="8651b-136">长时间运行的 JavaScript 会影响响应。</span><span class="sxs-lookup"><span data-stu-id="8651b-136">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="8651b-137">[DOMContentLoaded 事件][MDNUsingWebWorkers]将在使用 JS 工作塞满时停止。</span><span class="sxs-lookup"><span data-stu-id="8651b-137">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="8651b-138">将纯计算工作移动到 [Web 工作人员][MDNUsingWebWorkers]。</span><span class="sxs-lookup"><span data-stu-id="8651b-138">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="8651b-139">如果需要 DOM 访问权限，请使用 `requestAnimationFrame` 。</span><span class="sxs-lookup"><span data-stu-id="8651b-139">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="8651b-140">影响响应或动画的垃圾 y 脚本。</span><span class="sxs-lookup"><span data-stu-id="8651b-140">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="8651b-141">垃圾回收可能发生在任何位置。</span><span class="sxs-lookup"><span data-stu-id="8651b-141">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="8651b-142">编写较少的垃圾脚本。</span><span class="sxs-lookup"><span data-stu-id="8651b-142">Write less garbage-y scripts.</span></span>  <span data-ttu-id="8651b-143">请参阅 [Paul Lewis "运行时性能清单"][WebPerformanceCalendarRuntimeChecklist]中的动画中的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="8651b-143">See [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <span data-ttu-id="8651b-144">样式</span><span class="sxs-lookup"><span data-stu-id="8651b-144">Style</span></span>  

<span data-ttu-id="8651b-145">样式更改成本很高，尤其是当这些更改影响 DOM 中的多个元素时。</span><span class="sxs-lookup"><span data-stu-id="8651b-145">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="8651b-146">无论何时对元素应用样式，浏览器都将计算出对所有相关元素的影响，重新计算布局，然后重新绘制。</span><span class="sxs-lookup"><span data-stu-id="8651b-146">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <span data-ttu-id="8651b-147">样式：工具</span><span class="sxs-lookup"><span data-stu-id="8651b-147">Style: Tools</span></span>  

<span data-ttu-id="8651b-148">在 " **性能** " 面板中记笔记。</span><span class="sxs-lookup"><span data-stu-id="8651b-148">Take a recording in the **Performance** panel.</span></span>  <span data-ttu-id="8651b-149">检查录制中是否有较大 `Recalculate Style` 的事件 \ (显示为紫色 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="8651b-149">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="8651b-150">单击 `Recalculate Style` 事件可在 **详细** 信息窗格中查看有关它的详细信息。</span><span class="sxs-lookup"><span data-stu-id="8651b-150">Click on a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="8651b-151">如果样式更改花费很长时间，则会影响性能。</span><span class="sxs-lookup"><span data-stu-id="8651b-151">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="8651b-152">如果样式计算影响大量元素，这是一个具有空间以改进的另一个区域。</span><span class="sxs-lookup"><span data-stu-id="8651b-152">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="较长的重新计算样式" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="8651b-154">较长的重新计算样式</span><span class="sxs-lookup"><span data-stu-id="8651b-154">Long recalculate style</span></span>  
:::image-end:::  

<span data-ttu-id="8651b-155">要减少事件的影响，请 `Recalculate Style` 执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="8651b-155">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="8651b-156">使用 [CSS 触发器][CssTriggers] 了解哪些 CSS 属性会触发布局、画图和复合。</span><span class="sxs-lookup"><span data-stu-id="8651b-156">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="8651b-157">这些属性对呈现性能有最严重的影响。</span><span class="sxs-lookup"><span data-stu-id="8651b-157">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="8651b-158">切换到影响较少的属性。</span><span class="sxs-lookup"><span data-stu-id="8651b-158">Switch to properties that have less impact.</span></span>  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <span data-ttu-id="8651b-159">样式：问题</span><span class="sxs-lookup"><span data-stu-id="8651b-159">Style: Problems</span></span>  

<span data-ttu-id="8651b-160">下表介绍了一些常见的样式问题和可能的解决方案：</span><span class="sxs-lookup"><span data-stu-id="8651b-160">The following table describes some common style problems and potential solutions:</span></span>  

| <span data-ttu-id="8651b-161">问题</span><span class="sxs-lookup"><span data-stu-id="8651b-161">Problem</span></span> | <span data-ttu-id="8651b-162">示例</span><span class="sxs-lookup"><span data-stu-id="8651b-162">Example</span></span> | <span data-ttu-id="8651b-163">解决方案</span><span class="sxs-lookup"><span data-stu-id="8651b-163">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="8651b-164">影响响应或动画的昂贵的样式计算。</span><span class="sxs-lookup"><span data-stu-id="8651b-164">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="8651b-165">更改元素的几何图形（如宽度、高度或位置）的任何 CSS 属性;浏览器检查所有其他元素并重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="8651b-165">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="8651b-166">避免触发布局的 CSS</span><span class="sxs-lookup"><span data-stu-id="8651b-166">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="8651b-167">影响响应或动画的复杂选择器。</span><span class="sxs-lookup"><span data-stu-id="8651b-167">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="8651b-168">嵌套的选择器强制浏览器了解所有其他元素（包括父级和子级）的所有内容。</span><span class="sxs-lookup"><span data-stu-id="8651b-168">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="8651b-169">仅使用类引用 CSS 中的元素。</span><span class="sxs-lookup"><span data-stu-id="8651b-169">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <span data-ttu-id="8651b-170">布局</span><span class="sxs-lookup"><span data-stu-id="8651b-170">Layout</span></span>  

<span data-ttu-id="8651b-171">在 Firefox) 中 (或重排布局是浏览器计算页面上所有元素的位置和大小的过程。</span><span class="sxs-lookup"><span data-stu-id="8651b-171">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="8651b-172">Web 布局模型意味着一个元素可能会影响其他元素;例如，元素的宽度 `<body>` 通常影响任何子元素的宽度，依此类推，在树中向上和向下。</span><span class="sxs-lookup"><span data-stu-id="8651b-172">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="8651b-173">该过程可能会非常适用于浏览器。</span><span class="sxs-lookup"><span data-stu-id="8651b-173">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="8651b-174">作为一般经验法则，如果你在帧完成之前要求从 DOM 返回几何值，你将发现你有 "强制同步布局"，如果频繁地重复或执行大型 DOM 树，则可能会产生大性能瓶颈。</span><span class="sxs-lookup"><span data-stu-id="8651b-174">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <span data-ttu-id="8651b-175">布局：工具</span><span class="sxs-lookup"><span data-stu-id="8651b-175">Layout: Tools</span></span>  

<span data-ttu-id="8651b-176">" **性能** " 窗格标识页面何时导致强制同步布局。</span><span class="sxs-lookup"><span data-stu-id="8651b-176">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="8651b-177">这些 `Layout` 事件标有红条。</span><span class="sxs-lookup"><span data-stu-id="8651b-177">These `Layout` events are marked with red bars.</span></span>  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="强制同步布局" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="8651b-179">强制同步布局</span><span class="sxs-lookup"><span data-stu-id="8651b-179">Forced synchronous layout</span></span>  
:::image-end:::  

<span data-ttu-id="8651b-180">"布局失效" 是强制执行同步布局条件的重复。</span><span class="sxs-lookup"><span data-stu-id="8651b-180">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="8651b-181">这会在 JavaScript 重复写入和读取 DOM 时发生，从而强制浏览器重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="8651b-181">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="8651b-182">若要识别布局失效，请查看多个强制同步布局警告的模式。</span><span class="sxs-lookup"><span data-stu-id="8651b-182">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="8651b-183">请参阅上图。</span><span class="sxs-lookup"><span data-stu-id="8651b-183">See the previous figure.</span></span>  

### <span data-ttu-id="8651b-184">布局：问题</span><span class="sxs-lookup"><span data-stu-id="8651b-184">Layout: Problems</span></span>  

<span data-ttu-id="8651b-185">下表介绍了一些常见布局问题和可能的解决方案：</span><span class="sxs-lookup"><span data-stu-id="8651b-185">The following table describes some common layout problems and potential solutions:</span></span>  

| <span data-ttu-id="8651b-186">问题</span><span class="sxs-lookup"><span data-stu-id="8651b-186">Problem</span></span> | <span data-ttu-id="8651b-187">示例</span><span class="sxs-lookup"><span data-stu-id="8651b-187">Example</span></span> | <span data-ttu-id="8651b-188">解决方案</span><span class="sxs-lookup"><span data-stu-id="8651b-188">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="8651b-189">影响响应或动画的强制同步布局。</span><span class="sxs-lookup"><span data-stu-id="8651b-189">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="8651b-190">强制浏览器在像素管道前面执行布局，从而在呈现过程中产生重复步骤。</span><span class="sxs-lookup"><span data-stu-id="8651b-190">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="8651b-191">将首先读取样式，然后执行任何写操作。</span><span class="sxs-lookup"><span data-stu-id="8651b-191">Batch your style reads first, then do any writes.</span></span>  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="8651b-192">影响响应或动画的布局失效。</span><span class="sxs-lookup"><span data-stu-id="8651b-192">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="8651b-193">将浏览器置于读写读写循环中的循环，强制浏览器重新计算布局。</span><span class="sxs-lookup"><span data-stu-id="8651b-193">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="8651b-194">使用 [FastDom 库][GitHubWilsonpageFastdom]自动批处理读写操作。</span><span class="sxs-lookup"><span data-stu-id="8651b-194">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <span data-ttu-id="8651b-195">画图和复合</span><span class="sxs-lookup"><span data-stu-id="8651b-195">Paint and composite</span></span>  

<span data-ttu-id="8651b-196">"画图" 是填充像素的过程。</span><span class="sxs-lookup"><span data-stu-id="8651b-196">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="8651b-197">它通常是呈现过程中最昂贵的部分。</span><span class="sxs-lookup"><span data-stu-id="8651b-197">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="8651b-198">如果你注意到你的页面是以任何方式 janky 的，则可能是你遇到了画图问题。</span><span class="sxs-lookup"><span data-stu-id="8651b-198">If you noticed that your page is janky in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="8651b-199">合成是指将页面的绘制部分放置在屏幕上以显示在屏幕上的位置。</span><span class="sxs-lookup"><span data-stu-id="8651b-199">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="8651b-200">在大多数情况下，如果您仅坚持使用组合器的属性并避免画图，您应该可以看到性能的显著改进，但需要注意大量的层计数。</span><span class="sxs-lookup"><span data-stu-id="8651b-200">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should see a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <span data-ttu-id="8651b-201">画图和复合：工具</span><span class="sxs-lookup"><span data-stu-id="8651b-201">Paint and composite: Tools</span></span>  

<span data-ttu-id="8651b-202">想要了解绘制所需的时间或绘图的频率是多少？</span><span class="sxs-lookup"><span data-stu-id="8651b-202">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="8651b-203">选中 "**性能**" 面板中的 "[启用高级画图检测][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]" 设置，然后进行录制。</span><span class="sxs-lookup"><span data-stu-id="8651b-203">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="8651b-204">如果大多数渲染时间都花在绘图上，则您遇到了画图问题。</span><span class="sxs-lookup"><span data-stu-id="8651b-204">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long paint times in timeline recording" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <span data-ttu-id="8651b-205">画图和复合：问题</span><span class="sxs-lookup"><span data-stu-id="8651b-205">Paint and composite: Problems</span></span>  

<span data-ttu-id="8651b-206">下表介绍了一些常见的画图和复合问题以及可能的解决方案：</span><span class="sxs-lookup"><span data-stu-id="8651b-206">The following table describes some common paint and composite problems and potential solutions:</span></span>  

| <span data-ttu-id="8651b-207">问题</span><span class="sxs-lookup"><span data-stu-id="8651b-207">Problem</span></span> | <span data-ttu-id="8651b-208">示例</span><span class="sxs-lookup"><span data-stu-id="8651b-208">Example</span></span> | <span data-ttu-id="8651b-209">解决方案</span><span class="sxs-lookup"><span data-stu-id="8651b-209">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="8651b-210">绘制影响响应或动画的风暴。</span><span class="sxs-lookup"><span data-stu-id="8651b-210">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="8651b-211">大型油漆区域或影响响应或动画的昂贵油漆。</span><span class="sxs-lookup"><span data-stu-id="8651b-211">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="8651b-212">避免使用 "画图"，提升移动到自己的图层的元素，使用转换和不透明度。</span><span class="sxs-lookup"><span data-stu-id="8651b-212">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="8651b-213">影响动画的图层爆发。</span><span class="sxs-lookup"><span data-stu-id="8651b-213">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="8651b-214">Overpromotion `translateZ(0)` 严重影响动画性能的元素太多。</span><span class="sxs-lookup"><span data-stu-id="8651b-214">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="8651b-215">谨慎地推广图层，仅当您知道它可以提供有形改进时。</span><span class="sxs-lookup"><span data-stu-id="8651b-215">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

<!--  
## Feedback   


-->  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "加速 JavaScript 运行时 |Microsoft 文档"  

[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#enable-advanced-paint-instrumentation "启用高级画图检测-性能分析参考 |Microsoft 文档"

<!--[DevtoolsRenderingToolsForcedSynchronousLayouts]: ./forced-synchronous-layouts.md "Diagnose Forced Synchronous Layouts | Microsoft Docs"  -->  

<!-- The Timeline Tool page is deprecated  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfileJavascript]: ../evaluate-performance/timeline-tool.md#profile-javascript "Profile JavaScript - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolProfilePainting]: ../evaluate-performance/timeline-tool.md#profile-painting "Profile painting - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRecording]: ../evaluate-performance/timeline-tool.md#make-a-recording "Make a recording - How to Use the Timeline Tool | Microsoft Docs"  -->  
<!--[DevtoolsEvaluatePerformanceTimelineToolRenderingSettings]: ../evaluate-performance/timeline-tool.md#rendering-settings "Rendering settings - How to Use the Timeline Tool | Microsoft Docs"  -->  

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
> <span data-ttu-id="8651b-222">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="8651b-222">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="8651b-223">原始页面可在 [此处](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) 找到，并由 [Kayce Basques][KayceBasques] (技术作者、Chrome DevTools \ & Lighthouse \ ) 和 [Meggin Kearney][MegginKearney] \ (技术作者 \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="8651b-223">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="8651b-225">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="8651b-225">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
