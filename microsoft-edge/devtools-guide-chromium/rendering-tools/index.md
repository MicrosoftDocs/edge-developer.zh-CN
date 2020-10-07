---
description: Users expects interactive and smooth pages.  Each stage in the pixel pipeline represents an opportunity to introduce jank.  Learn about tools and strategies to identify and fix common problems that slow down runtime performance.
title: Analyze Runtime Performance
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
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

# <span data-ttu-id="b1975-106">Analyze runtime performance</span><span class="sxs-lookup"><span data-stu-id="b1975-106">Analyze runtime performance</span></span> 

<span data-ttu-id="b1975-107">Users expects interactive and smooth pages.</span><span class="sxs-lookup"><span data-stu-id="b1975-107">Users expects interactive and smooth pages.</span></span>  <span data-ttu-id="b1975-108">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span><span class="sxs-lookup"><span data-stu-id="b1975-108">Each stage in the pixel pipeline represents an opportunity to introduce jank.</span></span>  <span data-ttu-id="b1975-109">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span><span class="sxs-lookup"><span data-stu-id="b1975-109">Learn about tools and strategies to identify and fix common problems that slow down runtime performance.</span></span>  

### <span data-ttu-id="b1975-110">Summary</span><span class="sxs-lookup"><span data-stu-id="b1975-110">Summary</span></span>  

*   <span data-ttu-id="b1975-111">Do not write JavaScript that forces the browser to recalculate layout.</span><span class="sxs-lookup"><span data-stu-id="b1975-111">Do not write JavaScript that forces the browser to recalculate layout.</span></span>  <span data-ttu-id="b1975-112">Separate read and write functions, and perform reads first.</span><span class="sxs-lookup"><span data-stu-id="b1975-112">Separate read and write functions, and perform reads first.</span></span>  
*   <span data-ttu-id="b1975-113">Do not over-complicate your CSS.</span><span class="sxs-lookup"><span data-stu-id="b1975-113">Do not over-complicate your CSS.</span></span>  <span data-ttu-id="b1975-114">Use less CSS and keep your CSS selectors simple.</span><span class="sxs-lookup"><span data-stu-id="b1975-114">Use less CSS and keep your CSS selectors simple.</span></span>  
*   <span data-ttu-id="b1975-115">Avoid layout as much as possible.</span><span class="sxs-lookup"><span data-stu-id="b1975-115">Avoid layout as much as possible.</span></span>  <span data-ttu-id="b1975-116">Choose CSS that does not trigger layout at all.</span><span class="sxs-lookup"><span data-stu-id="b1975-116">Choose CSS that does not trigger layout at all.</span></span>  
*   <span data-ttu-id="b1975-117">Painting may take up more time than any other rendering activity.</span><span class="sxs-lookup"><span data-stu-id="b1975-117">Painting may take up more time than any other rendering activity.</span></span>  <span data-ttu-id="b1975-118">Watch out for paint bottlenecks.</span><span class="sxs-lookup"><span data-stu-id="b1975-118">Watch out for paint bottlenecks.</span></span>  
    
## <span data-ttu-id="b1975-119">JavaScript</span><span class="sxs-lookup"><span data-stu-id="b1975-119">JavaScript</span></span>  

<span data-ttu-id="b1975-120">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span><span class="sxs-lookup"><span data-stu-id="b1975-120">JavaScript calculations, especially ones that trigger extensive visual changes, may stall application performance.</span></span>  <span data-ttu-id="b1975-121">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span><span class="sxs-lookup"><span data-stu-id="b1975-121">Do not let badly-timed or long-running JavaScript interfere with user interactions.</span></span>  

### <span data-ttu-id="b1975-122">JavaScript: Tools</span><span class="sxs-lookup"><span data-stu-id="b1975-122">JavaScript: Tools</span></span>  

<span data-ttu-id="b1975-123">Take a recording in the **Performance** panel and look for suspiciously long `Evaluate Script` events.</span><span class="sxs-lookup"><span data-stu-id="b1975-123">Take a recording in the **Performance** panel and look for suspiciously long `Evaluate Script` events.</span></span>  <!--If you find any, you are able to enable the **JS Profiler** and re-do your recording to get more detailed information about exactly which JavaScript functions were used and how long each took.  -->  

<!--todo: add Recording section when available  -->  
<!--todo: add Profile JavaScript (JS Profiler) section when available  -->  

<span data-ttu-id="b1975-124">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span><span class="sxs-lookup"><span data-stu-id="b1975-124">f you noticing quite a bit of jank in your JavaScript, you may need to take your analysis to the next level and collect a JavaScript CPU profile.</span></span>  <span data-ttu-id="b1975-125">CPU profiles show where runtime is spent within the functions of your page.</span><span class="sxs-lookup"><span data-stu-id="b1975-125">CPU profiles show where runtime is spent within the functions of your page.</span></span>  <span data-ttu-id="b1975-126">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span><span class="sxs-lookup"><span data-stu-id="b1975-126">Learn how to create CPU profiles in [Speed Up JavaScript Runtime][DevtoolsRenderingToolsJavascriptRuntime].</span></span>

### <span data-ttu-id="b1975-127">JavaScript: Problems</span><span class="sxs-lookup"><span data-stu-id="b1975-127">JavaScript: Problems</span></span>  

<span data-ttu-id="b1975-128">The following table describes some common JavaScript problems and potential solutions:</span><span class="sxs-lookup"><span data-stu-id="b1975-128">The following table describes some common JavaScript problems and potential solutions:</span></span>  

| <span data-ttu-id="b1975-129">Problem</span><span class="sxs-lookup"><span data-stu-id="b1975-129">Problem</span></span> | <span data-ttu-id="b1975-130">Example</span><span class="sxs-lookup"><span data-stu-id="b1975-130">Example</span></span> | <span data-ttu-id="b1975-131">Solution</span><span class="sxs-lookup"><span data-stu-id="b1975-131">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b1975-132">Expensive input handlers affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-132">Expensive input handlers affecting response or animation.</span></span>  | <span data-ttu-id="b1975-133">Touch, parallax scrolling.</span><span class="sxs-lookup"><span data-stu-id="b1975-133">Touch, parallax scrolling.</span></span>  | <span data-ttu-id="b1975-134">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span><span class="sxs-lookup"><span data-stu-id="b1975-134">Let the browser handle touch and scrolls, or bind the listener as late as possible.</span></span>  <span data-ttu-id="b1975-135">See [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span><span class="sxs-lookup"><span data-stu-id="b1975-135">See [Expensive Input Handlers in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  
| <span data-ttu-id="b1975-136">Badly-timed JavaScript affecting response, animation, load.</span><span class="sxs-lookup"><span data-stu-id="b1975-136">Badly-timed JavaScript affecting response, animation, load.</span></span>  | <span data-ttu-id="b1975-137">User scrolls right after page load, setTimeout / setInterval.</span><span class="sxs-lookup"><span data-stu-id="b1975-137">User scrolls right after page load, setTimeout / setInterval.</span></span>  | <span data-ttu-id="b1975-138">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span><span class="sxs-lookup"><span data-stu-id="b1975-138">Optimize JavaScript runtime: use `requestAnimationFrame`, spread DOM manipulation over frames, use [Web Workers][MDNUsingWebWorkers].</span></span>  |  
| <span data-ttu-id="b1975-139">Long-running JavaScript affecting response.</span><span class="sxs-lookup"><span data-stu-id="b1975-139">Long-running JavaScript affecting response.</span></span>  | <span data-ttu-id="b1975-140">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span><span class="sxs-lookup"><span data-stu-id="b1975-140">The [DOMContentLoaded event][MDNUsingWebWorkers] stalls as it is swamped with JS work.</span></span>  | <span data-ttu-id="b1975-141">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span><span class="sxs-lookup"><span data-stu-id="b1975-141">Move pure computational work to [Web Workers][MDNUsingWebWorkers].</span></span>  <span data-ttu-id="b1975-142">If you need DOM access, use `requestAnimationFrame`.</span><span class="sxs-lookup"><span data-stu-id="b1975-142">If you need DOM access, use `requestAnimationFrame`.</span></span>  <!--See also [Optimize JavaScript Execution][WebFundamentalsPerformanceRenderingOptimizeJavascriptRuntime].  -->  |  
| <span data-ttu-id="b1975-143">Garbage-y scripts affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-143">Garbage-y scripts affecting response or animation.</span></span>  | <span data-ttu-id="b1975-144">Garbage collection may happen anywhere.</span><span class="sxs-lookup"><span data-stu-id="b1975-144">Garbage collection may happen anywhere.</span></span>  | <span data-ttu-id="b1975-145">Write less garbage-y scripts.</span><span class="sxs-lookup"><span data-stu-id="b1975-145">Write less garbage-y scripts.</span></span>  <span data-ttu-id="b1975-146">See [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span><span class="sxs-lookup"><span data-stu-id="b1975-146">See [Garbage Collection in Animation in Paul Lewis' runtime performance checklist][WebPerformanceCalendarRuntimeChecklist].</span></span>  |  

<!--todo: add Optimize JavaScript runtime section when available  -->  

## <span data-ttu-id="b1975-147">Style</span><span class="sxs-lookup"><span data-stu-id="b1975-147">Style</span></span>  

<span data-ttu-id="b1975-148">Style changes are costly, especially if those changes affect more than one element in the DOM.</span><span class="sxs-lookup"><span data-stu-id="b1975-148">Style changes are costly, especially if those changes affect more than one element in the DOM.</span></span>  <span data-ttu-id="b1975-149">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span><span class="sxs-lookup"><span data-stu-id="b1975-149">Any time you apply styles to an element, the browser figures out the impact on all related elements, recalculates the layout, and repaints.</span></span>  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  
-->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

### <span data-ttu-id="b1975-150">Style: Tools</span><span class="sxs-lookup"><span data-stu-id="b1975-150">Style: Tools</span></span>  

<span data-ttu-id="b1975-151">Take a recording in the **Performance** panel.</span><span class="sxs-lookup"><span data-stu-id="b1975-151">Take a recording in the **Performance** panel.</span></span>  <span data-ttu-id="b1975-152">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span><span class="sxs-lookup"><span data-stu-id="b1975-152">Check the recording for large `Recalculate Style` events \(displayed in purple\).</span></span>  

<!--todo: add Recording section when available  -->  

<span data-ttu-id="b1975-153">Click on a `Recalculate Style` event to view more information about it in the **Details** pane.</span><span class="sxs-lookup"><span data-stu-id="b1975-153">Click on a `Recalculate Style` event to view more information about it in the **Details** pane.</span></span>  <span data-ttu-id="b1975-154">If the style changes are taking a long time, that is a performance hit.</span><span class="sxs-lookup"><span data-stu-id="b1975-154">If the style changes are taking a long time, that is a performance hit.</span></span>  <span data-ttu-id="b1975-155">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span><span class="sxs-lookup"><span data-stu-id="b1975-155">If the style calculations are affecting a large number of elements, that is another area with room for improvement.</span></span>  

:::image type="complex" source="../media/rendering-tools-performance-recalculate-style-summary.msft.png" alt-text="Long recalculate style" lightbox="../media/rendering-tools-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="b1975-157">Long recalculate style</span><span class="sxs-lookup"><span data-stu-id="b1975-157">Long recalculate style</span></span>  
:::image-end:::  

<span data-ttu-id="b1975-158">To reduce the impact of `Recalculate Style` events:</span><span class="sxs-lookup"><span data-stu-id="b1975-158">To reduce the impact of `Recalculate Style` events:</span></span>  

*   <span data-ttu-id="b1975-159">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span><span class="sxs-lookup"><span data-stu-id="b1975-159">Use the [CSS Triggers][CssTriggers] to learn which CSS properties trigger layout, paint, and composite.</span></span>  <span data-ttu-id="b1975-160">These properties have the worst impact on rendering performance.</span><span class="sxs-lookup"><span data-stu-id="b1975-160">These properties have the worst impact on rendering performance.</span></span>  
*   <span data-ttu-id="b1975-161">Switch to properties that have less impact.</span><span class="sxs-lookup"><span data-stu-id="b1975-161">Switch to properties that have less impact.</span></span>  <!--See [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties] for more guidance.  -->  
    
<!--todo: add Stick to compositor-only properties and manage layer count section when available -->  

### <span data-ttu-id="b1975-162">Style: Problems</span><span class="sxs-lookup"><span data-stu-id="b1975-162">Style: Problems</span></span>  

<span data-ttu-id="b1975-163">The following table describes some common style problems and potential solutions:</span><span class="sxs-lookup"><span data-stu-id="b1975-163">The following table describes some common style problems and potential solutions:</span></span>  

| <span data-ttu-id="b1975-164">Problem</span><span class="sxs-lookup"><span data-stu-id="b1975-164">Problem</span></span> | <span data-ttu-id="b1975-165">Example</span><span class="sxs-lookup"><span data-stu-id="b1975-165">Example</span></span> | <span data-ttu-id="b1975-166">Solution</span><span class="sxs-lookup"><span data-stu-id="b1975-166">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b1975-167">Expensive style calculations affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-167">Expensive style calculations affecting response or animation.</span></span>  | <span data-ttu-id="b1975-168">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span><span class="sxs-lookup"><span data-stu-id="b1975-168">Any CSS property that changes the geometry of an element, like the width, height, or position; the browser checks all other elements and recalculates the layout.</span></span>  | <span data-ttu-id="b1975-169">Avoid CSS that triggers layouts</span><span class="sxs-lookup"><span data-stu-id="b1975-169">Avoid CSS that triggers layouts</span></span> |  
| <span data-ttu-id="b1975-170">Complex selectors affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-170">Complex selectors affecting response or animation.</span></span>  | <span data-ttu-id="b1975-171">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span><span class="sxs-lookup"><span data-stu-id="b1975-171">Nested selectors force the browser to know everything about all the other elements, including parents and children.</span></span>  | <span data-ttu-id="b1975-172">Reference an element in your CSS with just a class.</span><span class="sxs-lookup"><span data-stu-id="b1975-172">Reference an element in your CSS with just a class.</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts section when available -->  
<!--todo: add Reduce the Scope and Complexity of Styles Calculations (Reference an element in your CSS with just a class) section when available -->  

<!--Related Guides:  

*   [Reduce the Scope and Complexity of Styles Calculations][WebFundamentalsPerformanceRenderingReduceScope]  -->  

<!--todo: add Reduce the Scope and Complexity of Styles Calculations section when available -->  

## <span data-ttu-id="b1975-173">Layout</span><span class="sxs-lookup"><span data-stu-id="b1975-173">Layout</span></span>  

<span data-ttu-id="b1975-174">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span><span class="sxs-lookup"><span data-stu-id="b1975-174">Layout (or reflow in Firefox) is the process by which the browser calculates the positions and sizes of all the elements on a page.</span></span>  <span data-ttu-id="b1975-175">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span><span class="sxs-lookup"><span data-stu-id="b1975-175">The layout model of the web means that one element may affect others; for example, the width of the `<body>` element typically affects the widths of any child elements, and so on, all the way up and down the tree.</span></span>  <span data-ttu-id="b1975-176">The process may be quite involved for the browser.</span><span class="sxs-lookup"><span data-stu-id="b1975-176">The process may be quite involved for the browser.</span></span>  

<span data-ttu-id="b1975-177">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span><span class="sxs-lookup"><span data-stu-id="b1975-177">As a general rule of thumb, if you ask for a geometric value back from the DOM before a frame is complete, you are going to find yourself with "forced synchronous layouts", which may be a big performance bottleneck if repeated frequently or performed for a large DOM tree.</span></span>  

<!--Related Guides:  

*   [Avoid Layout Thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts]  
*   [Diagnose Forced Synchronous Layouts][DevtoolsRenderingToolsForcedSynchronousLayouts]  -->  

<!--todo: add Avoid CSS that triggers layouts (Avoid Layout Thrashing) section when available -->  
<!--todo: add Diagnose Forced Synchronous Layouts section when available  -->  

### <span data-ttu-id="b1975-178">Layout: Tools</span><span class="sxs-lookup"><span data-stu-id="b1975-178">Layout: Tools</span></span>  

<span data-ttu-id="b1975-179">The **Performance** pane identifies when a page causes forced synchronous layouts.</span><span class="sxs-lookup"><span data-stu-id="b1975-179">The **Performance** pane identifies when a page causes forced synchronous layouts.</span></span>  <span data-ttu-id="b1975-180">These `Layout` events are marked with red bars.</span><span class="sxs-lookup"><span data-stu-id="b1975-180">These `Layout` events are marked with red bars.</span></span>  

:::image type="complex" source="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png" alt-text="Long recalculate style" lightbox="../media/rendering-tools-jank-performance-recalculate-style-summary.msft.png":::
   <span data-ttu-id="b1975-182">Forced synchronous layout</span><span class="sxs-lookup"><span data-stu-id="b1975-182">Forced synchronous layout</span></span>  
:::image-end:::  

<span data-ttu-id="b1975-183">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span><span class="sxs-lookup"><span data-stu-id="b1975-183">"Layout thrashing" is a repetition of forced synchronous layout conditions.</span></span>  <span data-ttu-id="b1975-184">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span><span class="sxs-lookup"><span data-stu-id="b1975-184">This occurs when JavaScript writes and reads from the DOM repeatedly, which forces the browser to recalculate the layout over and over.</span></span>  <span data-ttu-id="b1975-185">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span><span class="sxs-lookup"><span data-stu-id="b1975-185">To identify layout thrashing, look for a pattern of multiple forced synchronous layout warnings.</span></span>  <span data-ttu-id="b1975-186">See the previous figure.</span><span class="sxs-lookup"><span data-stu-id="b1975-186">See the previous figure.</span></span>  

### <span data-ttu-id="b1975-187">Layout: Problems</span><span class="sxs-lookup"><span data-stu-id="b1975-187">Layout: Problems</span></span>  

<span data-ttu-id="b1975-188">The following table describes some common layout problems and potential solutions:</span><span class="sxs-lookup"><span data-stu-id="b1975-188">The following table describes some common layout problems and potential solutions:</span></span>  

| <span data-ttu-id="b1975-189">Problem</span><span class="sxs-lookup"><span data-stu-id="b1975-189">Problem</span></span> | <span data-ttu-id="b1975-190">Example</span><span class="sxs-lookup"><span data-stu-id="b1975-190">Example</span></span> | <span data-ttu-id="b1975-191">Solution</span><span class="sxs-lookup"><span data-stu-id="b1975-191">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b1975-192">Forced synchronous layout affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-192">Forced synchronous layout affecting response or animation.</span></span>  | <span data-ttu-id="b1975-193">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span><span class="sxs-lookup"><span data-stu-id="b1975-193">Forcing the browser to perform layout earlier in the pixel pipeline, resulting in repeating steps in the rendering process.</span></span>  | <span data-ttu-id="b1975-194">Batch your style reads first, then do any writes.</span><span class="sxs-lookup"><span data-stu-id="b1975-194">Batch your style reads first, then do any writes.</span></span>  <!--See also [Avoid large, complex layouts and layout thrashing][WebFundamentalsPerformanceRenderingAvoidLargeComplexLayouts].  -->  |  
| <span data-ttu-id="b1975-195">Layout thrashing affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-195">Layout thrashing affecting response or animation.</span></span>  | <span data-ttu-id="b1975-196">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span><span class="sxs-lookup"><span data-stu-id="b1975-196">A loop that puts the browser into a read-write-read-write cycle, forcing the browser to recalculate layout over and over again.</span></span>  | <span data-ttu-id="b1975-197">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span><span class="sxs-lookup"><span data-stu-id="b1975-197">Automatically batch read-write operations using [FastDom library][GitHubWilsonpageFastdom].</span></span>  |  

<!--todo: add Avoid CSS that triggers layouts (Avoid large, complex layouts and layout thrashing) section when available -->  

## <span data-ttu-id="b1975-198">Paint and composite</span><span class="sxs-lookup"><span data-stu-id="b1975-198">Paint and composite</span></span>  

<span data-ttu-id="b1975-199">Paint is the process of filling in pixels.</span><span class="sxs-lookup"><span data-stu-id="b1975-199">Paint is the process of filling in pixels.</span></span>  <span data-ttu-id="b1975-200">It is often the most costly part of the rendering process.</span><span class="sxs-lookup"><span data-stu-id="b1975-200">It is often the most costly part of the rendering process.</span></span>  <span data-ttu-id="b1975-201">If you noticed that your page is janky in any way, it is likely that you have paint problems.</span><span class="sxs-lookup"><span data-stu-id="b1975-201">If you noticed that your page is janky in any way, it is likely that you have paint problems.</span></span>  

<span data-ttu-id="b1975-202">Compositing is where the painted parts of the page are put together for displaying on screen.</span><span class="sxs-lookup"><span data-stu-id="b1975-202">Compositing is where the painted parts of the page are put together for displaying on screen.</span></span>  <span data-ttu-id="b1975-203">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should see a major improvement in performance, but you need to watch out for excessive layer counts.</span><span class="sxs-lookup"><span data-stu-id="b1975-203">For the most part, if you stick to compositor-only properties and avoid paint altogether, you should see a major improvement in performance, but you need to watch out for excessive layer counts.</span></span>  <!--See also [Stick to compositor-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  

<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

### <span data-ttu-id="b1975-204">Paint and composite: Tools</span><span class="sxs-lookup"><span data-stu-id="b1975-204">Paint and composite: Tools</span></span>  

<span data-ttu-id="b1975-205">Want to know how long painting takes or how often painting occurs?</span><span class="sxs-lookup"><span data-stu-id="b1975-205">Want to know how long painting takes or how often painting occurs?</span></span>  <span data-ttu-id="b1975-206">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span><span class="sxs-lookup"><span data-stu-id="b1975-206">Check the [Enable advanced paint instrumentation][DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation] setting in the **Performance** panel and then take a recording.</span></span>  <span data-ttu-id="b1975-207">If most of your rendering time is spent painting, you have paint problems.</span><span class="sxs-lookup"><span data-stu-id="b1975-207">If most of your rendering time is spent painting, you have paint problems.</span></span>  

<!--
:::image type="complex" source="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png" alt-text="Long recalculate style" lightbox="../media/rendering-tools-jank-performance-advanced-paint-instrumentation-summary.msft.png":::
   Long paint times in timeline recording  
:::image-end:::  
-->  

<!--
Check out the **Rendering** panel for further configurations that are able to help you diagnose paint problems.  -->  

<!--todo: link Rendering panel in ../evaluate-performance/timeline-tool  sub-section when live  -->  

### <span data-ttu-id="b1975-208">Paint and composite: Problems</span><span class="sxs-lookup"><span data-stu-id="b1975-208">Paint and composite: Problems</span></span>  

<span data-ttu-id="b1975-209">The following table describes some common paint and composite problems and potential solutions:</span><span class="sxs-lookup"><span data-stu-id="b1975-209">The following table describes some common paint and composite problems and potential solutions:</span></span>  

| <span data-ttu-id="b1975-210">Problem</span><span class="sxs-lookup"><span data-stu-id="b1975-210">Problem</span></span> | <span data-ttu-id="b1975-211">Example</span><span class="sxs-lookup"><span data-stu-id="b1975-211">Example</span></span> | <span data-ttu-id="b1975-212">Solution</span><span class="sxs-lookup"><span data-stu-id="b1975-212">Solution</span></span> |  
|:--- |:--- |:--- |  
| <span data-ttu-id="b1975-213">Paint storms affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-213">Paint storms affecting response or animation.</span></span>  | <span data-ttu-id="b1975-214">Big paint areas or expensive paints affecting response or animation.</span><span class="sxs-lookup"><span data-stu-id="b1975-214">Big paint areas or expensive paints affecting response or animation.</span></span>  | <span data-ttu-id="b1975-215">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span><span class="sxs-lookup"><span data-stu-id="b1975-215">Avoid paint, promote elements that are moving to their own layer, use transforms and opacity.</span></span>  <!--See [Simplify paint complexity and reduce paint areas][WebFundamentalsPerformanceRenderingSimplifyPaintComplexity].  -->  |  
| <span data-ttu-id="b1975-216">Layer explosions affecting animations.</span><span class="sxs-lookup"><span data-stu-id="b1975-216">Layer explosions affecting animations.</span></span>  | <span data-ttu-id="b1975-217">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span><span class="sxs-lookup"><span data-stu-id="b1975-217">Overpromotion of too many elements with `translateZ(0)` greatly affects animation performance.</span></span>  | <span data-ttu-id="b1975-218">Promote to layers sparingly, and only when you know it offers tangible improvements.</span><span class="sxs-lookup"><span data-stu-id="b1975-218">Promote to layers sparingly, and only when you know it offers tangible improvements.</span></span>  <!--See [Stick to composite-only properties and manage layer count][WebFundamentalsPerformanceRenderingCompositorOnlyProperties].  -->  |  

<!--todo: add Simplify paint complexity and reduce paint areas section when available  -->  
<!--todo: add Stick to compositor-only properties and manage layer count section when available  -->  

## <span data-ttu-id="b1975-219">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="b1975-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsRenderingToolsJavascriptRuntime]: ./js-runtime.md "Speed up JavaScript runtime | Microsoft Docs"  
[DevtoolsChromiumEvaluatePerformanceReferenceEnableadvancedpaintinstrumentation]: ../evaluate-performance/reference.md#enable-advanced-paint-instrumentation "Enable advanced paint instrumentation - Performance analysis reference | Microsoft Docs"

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

[CssTriggers]: https://csstriggers.com "CSS Triggers"  

[MDNUsingWebWorkers]: https://developer.mozilla.org/docs/Web/API/Web_Workers_API/Using_web_workers "Using Web Workers | MDN"  

[WebPerformanceCalendarRuntimeChecklist]: https://calendar.perfplanet.com/2013/the-runtime-performance-checklist/ "The Runtime Performance Checklist - Web Performance Calendar"  

[GitHubWilsonpageFastdom]: https://github.com/wilsonpage/fastdom "wilsonpage/fastdom | GitHub"  

> [!NOTE]
> <span data-ttu-id="b1975-226">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b1975-226">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b1975-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span><span class="sxs-lookup"><span data-stu-id="b1975-227">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/rendering-tools/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\) and [Meggin Kearney][MegginKearney] \(Tech Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b1975-229">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b1975-229">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
