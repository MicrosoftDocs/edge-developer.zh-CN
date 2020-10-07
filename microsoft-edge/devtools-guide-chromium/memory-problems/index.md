---
description: Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.
title: Fix Memory Problems
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: ef820353f81eb3fd791433e9c53434dff3b10a60
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992776"
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

# <span data-ttu-id="82856-104">Fix Memory Problems</span><span class="sxs-lookup"><span data-stu-id="82856-104">Fix Memory Problems</span></span>  

<span data-ttu-id="82856-105">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span><span class="sxs-lookup"><span data-stu-id="82856-105">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <span data-ttu-id="82856-106">Summary</span><span class="sxs-lookup"><span data-stu-id="82856-106">Summary</span></span>  

*   <span data-ttu-id="82856-107">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span><span class="sxs-lookup"><span data-stu-id="82856-107">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="82856-108">Visualize memory usage over time with the **Memory** panel.</span><span class="sxs-lookup"><span data-stu-id="82856-108">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="82856-109">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span><span class="sxs-lookup"><span data-stu-id="82856-109">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="82856-110">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span><span class="sxs-lookup"><span data-stu-id="82856-110">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <span data-ttu-id="82856-111">Overview</span><span class="sxs-lookup"><span data-stu-id="82856-111">Overview</span></span>  

<span data-ttu-id="82856-112">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span><span class="sxs-lookup"><span data-stu-id="82856-112">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="82856-113">Memory issues are important because they are often perceivable by users.</span><span class="sxs-lookup"><span data-stu-id="82856-113">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="82856-114">Users may perceive memory issues in the following ways:</span><span class="sxs-lookup"><span data-stu-id="82856-114">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="82856-115">**The performance of a page gets progressively worse over time**.</span><span class="sxs-lookup"><span data-stu-id="82856-115">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="82856-116">This is possibly a symptom of a memory leak.</span><span class="sxs-lookup"><span data-stu-id="82856-116">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="82856-117">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span><span class="sxs-lookup"><span data-stu-id="82856-117">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="82856-118">**The performance of a page is consistently bad**.</span><span class="sxs-lookup"><span data-stu-id="82856-118">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="82856-119">This is possibly a symptom of memory bloat.</span><span class="sxs-lookup"><span data-stu-id="82856-119">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="82856-120">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span><span class="sxs-lookup"><span data-stu-id="82856-120">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="82856-121">**The performance of a page is delayed or appears to pause frequently**.</span><span class="sxs-lookup"><span data-stu-id="82856-121">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="82856-122">This is possibly a symptom of frequent garbage collections.</span><span class="sxs-lookup"><span data-stu-id="82856-122">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="82856-123">Garbage collection is when the browser reclaims memory.</span><span class="sxs-lookup"><span data-stu-id="82856-123">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="82856-124">The browser decides when this happens.</span><span class="sxs-lookup"><span data-stu-id="82856-124">The browser decides when this happens.</span></span>  <span data-ttu-id="82856-125">During collections, all script running is paused.</span><span class="sxs-lookup"><span data-stu-id="82856-125">During collections, all script running is paused.</span></span>  <span data-ttu-id="82856-126">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span><span class="sxs-lookup"><span data-stu-id="82856-126">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <span data-ttu-id="82856-127">Memory bloat: how much is "too much"?</span><span class="sxs-lookup"><span data-stu-id="82856-127">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="82856-128">A memory leak is easy to define.</span><span class="sxs-lookup"><span data-stu-id="82856-128">A memory leak is easy to define.</span></span>  <span data-ttu-id="82856-129">If a site is progressively using more and more memory, then you have a leak.</span><span class="sxs-lookup"><span data-stu-id="82856-129">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="82856-130">But memory bloat is a bit harder to pin down.</span><span class="sxs-lookup"><span data-stu-id="82856-130">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="82856-131">What qualifies as "using too much memory"?</span><span class="sxs-lookup"><span data-stu-id="82856-131">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="82856-132">There are no hard numbers here, because different devices and browsers have different capabilities.</span><span class="sxs-lookup"><span data-stu-id="82856-132">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="82856-133">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span><span class="sxs-lookup"><span data-stu-id="82856-133">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="82856-134">The key here is to use the RAIL model and focus on your users.</span><span class="sxs-lookup"><span data-stu-id="82856-134">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="82856-135">Find out what devices are popular with your users, and then test out your page on those devices.</span><span class="sxs-lookup"><span data-stu-id="82856-135">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="82856-136">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span><span class="sxs-lookup"><span data-stu-id="82856-136">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <span data-ttu-id="82856-137">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span><span class="sxs-lookup"><span data-stu-id="82856-137">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="82856-138">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span><span class="sxs-lookup"><span data-stu-id="82856-138">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="82856-139">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span><span class="sxs-lookup"><span data-stu-id="82856-139">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="82856-140">Press `Shift`+`Esc` or go to the Microsoft Edge main menu and select **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span><span class="sxs-lookup"><span data-stu-id="82856-140">Press `Shift`+`Esc` or go to the Microsoft Edge main menu and select **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       <span data-ttu-id="82856-142">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span><span class="sxs-lookup"><span data-stu-id="82856-142">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="82856-143">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span><span class="sxs-lookup"><span data-stu-id="82856-143">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       <span data-ttu-id="82856-145">Figure 2:  Enable JavaScript memory</span><span class="sxs-lookup"><span data-stu-id="82856-145">Figure 2:  Enable JavaScript memory</span></span>  
    :::image-end:::  
    
<span data-ttu-id="82856-146">These two columns tell you different things about how your page is using memory.</span><span class="sxs-lookup"><span data-stu-id="82856-146">These two columns tell you different things about how your page is using memory.</span></span>  

*   <span data-ttu-id="82856-147">The **Memory** column represents native memory.</span><span class="sxs-lookup"><span data-stu-id="82856-147">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="82856-148">DOM nodes are stored in native memory.</span><span class="sxs-lookup"><span data-stu-id="82856-148">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="82856-149">If this value is increasing, DOM nodes are getting created.</span><span class="sxs-lookup"><span data-stu-id="82856-149">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="82856-150">The **JavaScript Memory** column represents the JS heap.</span><span class="sxs-lookup"><span data-stu-id="82856-150">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="82856-151">This column contains two values.</span><span class="sxs-lookup"><span data-stu-id="82856-151">This column contains two values.</span></span>  <span data-ttu-id="82856-152">The value you are interested in is the live number \(the number in parentheses\).</span><span class="sxs-lookup"><span data-stu-id="82856-152">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="82856-153">The live number represents how much memory the reachable objects on your page are using.</span><span class="sxs-lookup"><span data-stu-id="82856-153">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="82856-154">If this number is increasing, either new objects are being created, or the existing objects are growing.</span><span class="sxs-lookup"><span data-stu-id="82856-154">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <span data-ttu-id="82856-155">Visualize memory leaks with Performance panel</span><span class="sxs-lookup"><span data-stu-id="82856-155">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="82856-156">You may also use the Performance panel as another starting point in your investigation.</span><span class="sxs-lookup"><span data-stu-id="82856-156">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="82856-157">The Performance panel helps you visualize the memory use of a page over time.</span><span class="sxs-lookup"><span data-stu-id="82856-157">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="82856-158">Open the **Performance** panel on DevTools.</span><span class="sxs-lookup"><span data-stu-id="82856-158">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="82856-159">Enable the **Memory** checkbox.</span><span class="sxs-lookup"><span data-stu-id="82856-159">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="82856-160">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span><span class="sxs-lookup"><span data-stu-id="82856-160">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="82856-161">It is a good practice to start and end your recording with a forced garbage collection.</span><span class="sxs-lookup"><span data-stu-id="82856-161">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="82856-162">Select the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording to force garbage collection.</span><span class="sxs-lookup"><span data-stu-id="82856-162">Select the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording to force garbage collection.</span></span>  

<span data-ttu-id="82856-163">To demonstrate memory recordings, consider the code below:</span><span class="sxs-lookup"><span data-stu-id="82856-163">To demonstrate memory recordings, consider the code below:</span></span>  

```javascript
var x = [];
function grow() {
    for (var i = 0; i < 10000; i++) {
        document.body.appendChild(document.createElement('div'));
    }
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="82856-164">Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span><span class="sxs-lookup"><span data-stu-id="82856-164">Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="82856-165">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span><span class="sxs-lookup"><span data-stu-id="82856-165">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   <span data-ttu-id="82856-167">Figure 3:  Simple growth</span><span class="sxs-lookup"><span data-stu-id="82856-167">Figure 3:  Simple growth</span></span>  
:::image-end:::  

<span data-ttu-id="82856-168">First, an explanation of the user interface.</span><span class="sxs-lookup"><span data-stu-id="82856-168">First, an explanation of the user interface.</span></span>  <span data-ttu-id="82856-169">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span><span class="sxs-lookup"><span data-stu-id="82856-169">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="82856-170">Below the **Overview** pane is the **Counter** pane.</span><span class="sxs-lookup"><span data-stu-id="82856-170">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="82856-171">Here you are able to see memory usage broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span><span class="sxs-lookup"><span data-stu-id="82856-171">Here you are able to see memory usage broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="82856-172">Disabling a checkbox hides it from the graph.</span><span class="sxs-lookup"><span data-stu-id="82856-172">Disabling a checkbox hides it from the graph.</span></span>  

<span data-ttu-id="82856-173">Now, an analysis of the code compared with the previous figure.</span><span class="sxs-lookup"><span data-stu-id="82856-173">Now, an analysis of the code compared with the previous figure.</span></span>  <span data-ttu-id="82856-174">If you look at the node counter \(the green graph\) you are able to see that it matches up cleanly with the code.</span><span class="sxs-lookup"><span data-stu-id="82856-174">If you look at the node counter \(the green graph\) you are able to see that it matches up cleanly with the code.</span></span>  <span data-ttu-id="82856-175">The node count increases in discrete steps.</span><span class="sxs-lookup"><span data-stu-id="82856-175">The node count increases in discrete steps.</span></span>  <span data-ttu-id="82856-176">You may presume that each increase in the node count is a call to `grow()`.</span><span class="sxs-lookup"><span data-stu-id="82856-176">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="82856-177">The JS heap graph \(the blue graph\) is not as straightforward.</span><span class="sxs-lookup"><span data-stu-id="82856-177">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="82856-178">In keeping with best practices, the first dip is actually a forced garbage collection \(achieved by pressing the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span><span class="sxs-lookup"><span data-stu-id="82856-178">In keeping with best practices, the first dip is actually a forced garbage collection \(achieved by pressing the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="82856-179">As the recording progresses you are able to see that the JS heap size spikes.</span><span class="sxs-lookup"><span data-stu-id="82856-179">As the recording progresses you are able to see that the JS heap size spikes.</span></span>  <span data-ttu-id="82856-180">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button press and doing a lot of work when it creates the string of one million characters.</span><span class="sxs-lookup"><span data-stu-id="82856-180">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button press and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="82856-181">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span><span class="sxs-lookup"><span data-stu-id="82856-181">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="82856-182">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span><span class="sxs-lookup"><span data-stu-id="82856-182">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <span data-ttu-id="82856-183">Discover detached DOM tree memory leaks with Heap Snapshots</span><span class="sxs-lookup"><span data-stu-id="82856-183">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="82856-184">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span><span class="sxs-lookup"><span data-stu-id="82856-184">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="82856-185">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span><span class="sxs-lookup"><span data-stu-id="82856-185">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="82856-186">Detached DOM nodes are a common cause of memory leaks.</span><span class="sxs-lookup"><span data-stu-id="82856-186">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="82856-187">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span><span class="sxs-lookup"><span data-stu-id="82856-187">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="82856-188">Here is a simple example of detached DOM nodes.</span><span class="sxs-lookup"><span data-stu-id="82856-188">Here is a simple example of detached DOM nodes.</span></span>  

```javascript
var detachedTree;

function create() {
    var ul = document.createElement('ul');
    for (var i = 0; i < 10; i++) {
        var li = document.createElement('li');
        ul.appendChild(li);
    }
    detachedTree = ul;
}
document.getElementById('create').addEventListener('click', create);
```  

<span data-ttu-id="82856-189">Selecting the button referenced in the code creates a `ul` node with ten `li` children.</span><span class="sxs-lookup"><span data-stu-id="82856-189">Selecting the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="82856-190">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span><span class="sxs-lookup"><span data-stu-id="82856-190">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="82856-191">Heap snapshots are one way to identify detached nodes.</span><span class="sxs-lookup"><span data-stu-id="82856-191">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="82856-192">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span><span class="sxs-lookup"><span data-stu-id="82856-192">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="82856-193">To create a snapshot, open DevTools and go to the **Memory** panel, select the **Heap snapshot** radio button, and then press the **Take snapshot** button.</span><span class="sxs-lookup"><span data-stu-id="82856-193">To create a snapshot, open DevTools and go to the **Memory** panel, select the **Heap snapshot** radio button, and then press the **Take snapshot** button.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   <span data-ttu-id="82856-195">Figure 4:  Take heap snapshot</span><span class="sxs-lookup"><span data-stu-id="82856-195">Figure 4:  Take heap snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="82856-196">The snapshot may take some time to process and load.</span><span class="sxs-lookup"><span data-stu-id="82856-196">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="82856-197">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span><span class="sxs-lookup"><span data-stu-id="82856-197">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="82856-198">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span><span class="sxs-lookup"><span data-stu-id="82856-198">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   <span data-ttu-id="82856-200">Figure 5:  Filtering for detached nodes</span><span class="sxs-lookup"><span data-stu-id="82856-200">Figure 5:  Filtering for detached nodes</span></span>  
:::image-end:::  

<span data-ttu-id="82856-201">Expand the carats to investigate a detached tree.</span><span class="sxs-lookup"><span data-stu-id="82856-201">Expand the carats to investigate a detached tree.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   <span data-ttu-id="82856-203">Figure 6:  Investigating detached tree</span><span class="sxs-lookup"><span data-stu-id="82856-203">Figure 6:  Investigating detached tree</span></span>  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="82856-204">Select a node to investigate it further.</span><span class="sxs-lookup"><span data-stu-id="82856-204">Select a node to investigate it further.</span></span>  <span data-ttu-id="82856-205">In the **Objects** pane you are able to see more information about the code that is referencing it.</span><span class="sxs-lookup"><span data-stu-id="82856-205">In the **Objects** pane you are able to see more information about the code that is referencing it.</span></span>  <span data-ttu-id="82856-206">For example, in the following figure you are able to see that the `detachedNodes` variable is referencing the node.</span><span class="sxs-lookup"><span data-stu-id="82856-206">For example, in the following figure you are able to see that the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="82856-207">To fix this particular memory leak, you should study the code that uses the `detachedUNode` variable and ensure that the reference to the node is removed when it is no longer needed.</span><span class="sxs-lookup"><span data-stu-id="82856-207">To fix this particular memory leak, you should study the code that uses the `detachedUNode` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   <span data-ttu-id="82856-209">Figure 7:  Investigating a node</span><span class="sxs-lookup"><span data-stu-id="82856-209">Figure 7:  Investigating a node</span></span>  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <span data-ttu-id="82856-210">Identify JS heap memory leaks with Allocation instrumentation on timeline</span><span class="sxs-lookup"><span data-stu-id="82856-210">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="82856-211">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span><span class="sxs-lookup"><span data-stu-id="82856-211">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="82856-212">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span><span class="sxs-lookup"><span data-stu-id="82856-212">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="82856-213">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span><span class="sxs-lookup"><span data-stu-id="82856-213">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="82856-214">To record an Allocation instrumentation on timeline, open DevTools, go to the **Memory** panel, select the **Allocation instrumentation on timeline** radio button, press the **Start** button, perform the action that you suspect is causing the memory leak, and then press the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span><span class="sxs-lookup"><span data-stu-id="82856-214">To record an Allocation instrumentation on timeline, open DevTools, go to the **Memory** panel, select the **Allocation instrumentation on timeline** radio button, press the **Start** button, perform the action that you suspect is causing the memory leak, and then press the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="82856-215">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span><span class="sxs-lookup"><span data-stu-id="82856-215">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   <span data-ttu-id="82856-217">Figure 8:  New allocations</span><span class="sxs-lookup"><span data-stu-id="82856-217">Figure 8:  New allocations</span></span>  
:::image-end:::  

<span data-ttu-id="82856-218">Those blue bars represent new memory allocations.</span><span class="sxs-lookup"><span data-stu-id="82856-218">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="82856-219">Those new memory allocations are your candidates for memory leaks.</span><span class="sxs-lookup"><span data-stu-id="82856-219">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="82856-220">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span><span class="sxs-lookup"><span data-stu-id="82856-220">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   <span data-ttu-id="82856-222">Figure 9:  Zoomed allocation timeline</span><span class="sxs-lookup"><span data-stu-id="82856-222">Figure 9:  Zoomed allocation timeline</span></span>  
:::image-end:::  

<span data-ttu-id="82856-223">Expand the object and select the value to view more details in the **Object** pane.</span><span class="sxs-lookup"><span data-stu-id="82856-223">Expand the object and select the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="82856-224">For example, in the following figure, by viewing the details of the object that was newly allocated, you should be able to see that it was allocated to the `x` variable in the `Window` scope.</span><span class="sxs-lookup"><span data-stu-id="82856-224">For example, in the following figure, by viewing the details of the object that was newly allocated, you should be able to see that it was allocated to the `x` variable in the `Window` scope.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   <span data-ttu-id="82856-226">Figure 10:  Object details</span><span class="sxs-lookup"><span data-stu-id="82856-226">Figure 10:  Object details</span></span>  
:::image-end:::  

## <span data-ttu-id="82856-227">Investigate memory allocation by function</span><span class="sxs-lookup"><span data-stu-id="82856-227">Investigate memory allocation by function</span></span>  

<span data-ttu-id="82856-228">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span><span class="sxs-lookup"><span data-stu-id="82856-228">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   <span data-ttu-id="82856-230">Figure 11:  Record Allocation sampling</span><span class="sxs-lookup"><span data-stu-id="82856-230">Figure 11:  Record Allocation sampling</span></span>  
:::image-end:::  

1.  <span data-ttu-id="82856-231">Select the **Allocation sampling** radio button.</span><span class="sxs-lookup"><span data-stu-id="82856-231">Select the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="82856-232">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span><span class="sxs-lookup"><span data-stu-id="82856-232">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="82856-233">Press the **Start** button.</span><span class="sxs-lookup"><span data-stu-id="82856-233">Press the **Start** button.</span></span>  
1.  <span data-ttu-id="82856-234">Perform the actions on the page which you want to investigate.</span><span class="sxs-lookup"><span data-stu-id="82856-234">Perform the actions on the page which you want to investigate.</span></span>  
1.  <span data-ttu-id="82856-235">Press the **Stop** button when you have finished all of your actions.</span><span class="sxs-lookup"><span data-stu-id="82856-235">Press the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="82856-236">DevTools shows you a breakdown of memory allocation by function.</span><span class="sxs-lookup"><span data-stu-id="82856-236">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="82856-237">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span><span class="sxs-lookup"><span data-stu-id="82856-237">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="Opening the Microsoft Edge Browser Task Manager" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   <span data-ttu-id="82856-239">Figure 12:  Allocation sampling</span><span class="sxs-lookup"><span data-stu-id="82856-239">Figure 12:  Allocation sampling</span></span>  
:::image-end:::  

## <span data-ttu-id="82856-240">Spot frequent garbage collections</span><span class="sxs-lookup"><span data-stu-id="82856-240">Spot frequent garbage collections</span></span>  

<span data-ttu-id="82856-241">If your page appears to pause frequently, then you may have garbage collection issues.</span><span class="sxs-lookup"><span data-stu-id="82856-241">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="82856-242">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="82856-242">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="82856-243">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="82856-243">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="82856-244">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span><span class="sxs-lookup"><span data-stu-id="82856-244">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="82856-245">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span><span class="sxs-lookup"><span data-stu-id="82856-245">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "Record performance - Performance Analysis Reference"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="82856-247">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="82856-247">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="82856-248">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="82856-248">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="82856-250">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="82856-250">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
