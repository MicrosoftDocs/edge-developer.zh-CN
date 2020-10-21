---
description: 了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存膨胀和频繁垃圾回收。
title: 修复内存问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 1d8a24fc360dc307471be33544c9c707736be06d
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125452"
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

# <span data-ttu-id="b467e-104">修复内存问题</span><span class="sxs-lookup"><span data-stu-id="b467e-104">Fix Memory Problems</span></span>  

<span data-ttu-id="b467e-105">了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存膨胀和频繁垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b467e-105">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <span data-ttu-id="b467e-106">摘要</span><span class="sxs-lookup"><span data-stu-id="b467e-106">Summary</span></span>  

*   <span data-ttu-id="b467e-107">使用 Microsoft Edge 浏览器任务管理器了解你的页面当前使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="b467e-107">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="b467e-108">使用 " **内存** " 面板在一段时间内可视化内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="b467e-108">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="b467e-109">确定分离的 DOM 树 \ (使用 **堆快照**的内存泄漏的常见原因 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="b467e-109">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="b467e-110">了解在你的 JavaScript 堆 \ (JS 堆 \ ) 以及 **时间线上有分配检测**的情况中何时分配新内存。</span><span class="sxs-lookup"><span data-stu-id="b467e-110">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <span data-ttu-id="b467e-111">概述</span><span class="sxs-lookup"><span data-stu-id="b467e-111">Overview</span></span>  

<span data-ttu-id="b467e-112">在 **铁路** 性能模型的精神中，你的性能工作的重点应是你的用户。</span><span class="sxs-lookup"><span data-stu-id="b467e-112">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="b467e-113">内存问题很重要，因为它们通常由用户觉察。</span><span class="sxs-lookup"><span data-stu-id="b467e-113">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="b467e-114">用户可能会通过以下方式来感知内存问题：</span><span class="sxs-lookup"><span data-stu-id="b467e-114">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="b467e-115">**随着时间的推移，页面性能逐渐变得越来越严重**。</span><span class="sxs-lookup"><span data-stu-id="b467e-115">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="b467e-116">这可能是内存泄漏的症状。</span><span class="sxs-lookup"><span data-stu-id="b467e-116">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="b467e-117">当页面中的 bug 导致页面逐渐使用越来越多的内存时，会发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="b467e-117">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="b467e-118">**页面性能始终不正确**。</span><span class="sxs-lookup"><span data-stu-id="b467e-118">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="b467e-119">这可能是内存膨胀的症状。</span><span class="sxs-lookup"><span data-stu-id="b467e-119">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="b467e-120">内存膨胀是指页面使用的内存超过最佳页面速度所需的内存。</span><span class="sxs-lookup"><span data-stu-id="b467e-120">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="b467e-121">**页面性能延迟或显示为经常暂停**。</span><span class="sxs-lookup"><span data-stu-id="b467e-121">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="b467e-122">这可能是频繁垃圾回收的症状。</span><span class="sxs-lookup"><span data-stu-id="b467e-122">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="b467e-123">垃圾回收是浏览器回收内存的时候。</span><span class="sxs-lookup"><span data-stu-id="b467e-123">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="b467e-124">浏览器决定何时发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="b467e-124">The browser decides when this happens.</span></span>  <span data-ttu-id="b467e-125">在集合期间，将暂停运行的所有脚本。</span><span class="sxs-lookup"><span data-stu-id="b467e-125">During collections, all script running is paused.</span></span>  <span data-ttu-id="b467e-126">因此，如果浏览器对大量垃圾回收，脚本运行时将会暂停很多事情。</span><span class="sxs-lookup"><span data-stu-id="b467e-126">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <span data-ttu-id="b467e-127">内存膨胀： "过多" 是多少？</span><span class="sxs-lookup"><span data-stu-id="b467e-127">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="b467e-128">内存泄漏很容易定义。</span><span class="sxs-lookup"><span data-stu-id="b467e-128">A memory leak is easy to define.</span></span>  <span data-ttu-id="b467e-129">如果某个网站在使用更多内存的情况下逐渐增加，则你有泄漏。</span><span class="sxs-lookup"><span data-stu-id="b467e-129">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="b467e-130">但是内存膨胀比固定更难。</span><span class="sxs-lookup"><span data-stu-id="b467e-130">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="b467e-131">什么是 "使用过多的内存"？</span><span class="sxs-lookup"><span data-stu-id="b467e-131">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="b467e-132">此处没有任何硬编号，因为不同的设备和浏览器具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="b467e-132">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="b467e-133">在高端智能手机上正常运行的同一页面可能会在低端智能手机上崩溃。</span><span class="sxs-lookup"><span data-stu-id="b467e-133">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="b467e-134">此处的关键是使用滑轨模型，并关注您的用户。</span><span class="sxs-lookup"><span data-stu-id="b467e-134">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="b467e-135">了解你的用户最常用的设备，然后在这些设备上测试你的页面。</span><span class="sxs-lookup"><span data-stu-id="b467e-135">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="b467e-136">如果体验持续很差，则页面可能超出了这些设备的内存功能。</span><span class="sxs-lookup"><span data-stu-id="b467e-136">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <span data-ttu-id="b467e-137">使用 Microsoft Edge 浏览器任务管理器实时监视内存使用情况</span><span class="sxs-lookup"><span data-stu-id="b467e-137">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="b467e-138">使用 Microsoft Edge 浏览器任务管理器作为内存问题调查的起始点。</span><span class="sxs-lookup"><span data-stu-id="b467e-138">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="b467e-139">Microsoft Edge 浏览器任务管理器是一个实时监视器，可告诉你页面当前使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="b467e-139">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="b467e-140">选择 `Shift` + `Esc` 或转到 Microsoft edge 主菜单，然后选择 "**更多工具**  >  **浏览器任务管理**器" 以打开 microsoft Edge 浏览器任务管理器。</span><span class="sxs-lookup"><span data-stu-id="b467e-140">Select `Shift`+`Esc` or go to the Microsoft Edge main menu and choose **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       <span data-ttu-id="b467e-142">图1：打开 Microsoft Edge 浏览器任务管理器</span><span class="sxs-lookup"><span data-stu-id="b467e-142">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="b467e-143">将鼠标悬停在 Microsoft Edge 浏览器任务管理器的表标题上，打开上下文菜单 \ (右键单击 "\ ) "，然后启用 **JavaScript 内存**。</span><span class="sxs-lookup"><span data-stu-id="b467e-143">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       <span data-ttu-id="b467e-145">图2：启用 JavaScript 内存</span><span class="sxs-lookup"><span data-stu-id="b467e-145">Figure 2:  Enable JavaScript memory</span></span>  
    :::image-end:::  
    
<span data-ttu-id="b467e-146">这两个列告诉你有关页面如何使用内存的不同内容。</span><span class="sxs-lookup"><span data-stu-id="b467e-146">These two columns tell you different things about how your page is using memory.</span></span>  

*   <span data-ttu-id="b467e-147">" **内存** " 列表示本机内存。</span><span class="sxs-lookup"><span data-stu-id="b467e-147">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="b467e-148">DOM 节点存储在本机内存中。</span><span class="sxs-lookup"><span data-stu-id="b467e-148">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="b467e-149">如果此值增加，则会创建 DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="b467e-149">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="b467e-150">**JavaScript 内存**列表示 JS 堆栈。</span><span class="sxs-lookup"><span data-stu-id="b467e-150">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="b467e-151">此列包含两个值。</span><span class="sxs-lookup"><span data-stu-id="b467e-151">This column contains two values.</span></span>  <span data-ttu-id="b467e-152">您感兴趣的值是活动号码 \ (圆括号中的数字 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="b467e-152">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="b467e-153">活动号码表示页面上可访问对象所使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="b467e-153">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="b467e-154">如果此数字增加，则表示正在创建新对象，或者现有对象正在增长。</span><span class="sxs-lookup"><span data-stu-id="b467e-154">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <span data-ttu-id="b467e-155">利用性能面板可视化内存泄漏</span><span class="sxs-lookup"><span data-stu-id="b467e-155">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="b467e-156">您也可以将 "性能" 面板用作调查中的另一个起始点。</span><span class="sxs-lookup"><span data-stu-id="b467e-156">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="b467e-157">"性能" 面板可帮助你在一段时间内对页面的内存使用进行可视化处理。</span><span class="sxs-lookup"><span data-stu-id="b467e-157">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="b467e-158">在 DevTools 上打开 **性能** 面板。</span><span class="sxs-lookup"><span data-stu-id="b467e-158">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="b467e-159">启用 " **内存** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="b467e-159">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="b467e-160">[进行录制][DevtoolsEvaluatePerformanceReferenceRecord]。</span><span class="sxs-lookup"><span data-stu-id="b467e-160">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="b467e-161">使用强制垃圾回收开始和结束录制是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="b467e-161">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="b467e-162">在录制以强制垃圾回收时，选择 " **收集垃圾** ![ 强制垃圾回收" ][ImageForceGarbageCollectionIcon] 按钮。</span><span class="sxs-lookup"><span data-stu-id="b467e-162">Select the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording to force garbage collection.</span></span>  

<span data-ttu-id="b467e-163">若要演示内存录制，请考虑以下代码：</span><span class="sxs-lookup"><span data-stu-id="b467e-163">To demonstrate memory recordings, consider the code below:</span></span>  

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

<span data-ttu-id="b467e-164">每次按下代码中引用的按钮时，将 `div` 向文档正文追加10000节点，并将1000000字符的字符串 `x` 推送到 `x` 数组中。</span><span class="sxs-lookup"><span data-stu-id="b467e-164">Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="b467e-165">运行上面的代码示例将在 " **性能** " 面板中生成一条记录，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="b467e-165">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   <span data-ttu-id="b467e-167">图3：简单增长</span><span class="sxs-lookup"><span data-stu-id="b467e-167">Figure 3:  Simple growth</span></span>  
:::image-end:::  

<span data-ttu-id="b467e-168">首先是用户界面的说明。</span><span class="sxs-lookup"><span data-stu-id="b467e-168">First, an explanation of the user interface.</span></span>  <span data-ttu-id="b467e-169">"**概述**" 窗格中的**堆**图形 \ (下方的**NET**\ ) 表示 JS 堆栈。</span><span class="sxs-lookup"><span data-stu-id="b467e-169">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="b467e-170">" **概述** " 窗格下方是 **计数器** 窗格。</span><span class="sxs-lookup"><span data-stu-id="b467e-170">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="b467e-171">在这里，你可以在 "**概述**" 窗格中查看按 JS 堆栈 \ (和**堆**图相同的内存使用 \ ) 、文档、DOM 节点、侦听器和 GPU 内存。</span><span class="sxs-lookup"><span data-stu-id="b467e-171">Here you are able to see memory usage broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="b467e-172">禁用复选框会将其从图形中隐藏。</span><span class="sxs-lookup"><span data-stu-id="b467e-172">Disabling a checkbox hides it from the graph.</span></span>  

<span data-ttu-id="b467e-173">现在，与上图中的代码分析进行了比较。</span><span class="sxs-lookup"><span data-stu-id="b467e-173">Now, an analysis of the code compared with the previous figure.</span></span>  <span data-ttu-id="b467e-174">如果你查看节点计数器 \ (绿色图形 \ ) 你可以看到它与代码完全匹配。</span><span class="sxs-lookup"><span data-stu-id="b467e-174">If you look at the node counter \(the green graph\) you are able to see that it matches up cleanly with the code.</span></span>  <span data-ttu-id="b467e-175">节点计数在离散步骤中增加。</span><span class="sxs-lookup"><span data-stu-id="b467e-175">The node count increases in discrete steps.</span></span>  <span data-ttu-id="b467e-176">你可能会假定节点计数中的每个增加都是对的调用 `grow()` 。</span><span class="sxs-lookup"><span data-stu-id="b467e-176">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="b467e-177">JS 堆图形 \ (蓝色图形 \ ) 不是很简单。</span><span class="sxs-lookup"><span data-stu-id="b467e-177">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="b467e-178">根据最佳做法，第一个 dip 实际上是强制垃圾回收 \ (通过按 "  **收集垃圾** ![ 强制垃圾回收" ][ImageForceGarbageCollectionIcon] 按钮 \ ) 实现。</span><span class="sxs-lookup"><span data-stu-id="b467e-178">In keeping with best practices, the first dip is actually a forced garbage collection \(achieved by pressing the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="b467e-179">在录制过程中，你可以看到 JS 堆大小峰值。</span><span class="sxs-lookup"><span data-stu-id="b467e-179">As the recording progresses you are able to see that the JS heap size spikes.</span></span>  <span data-ttu-id="b467e-180">这是自然且预期的： JavaScript 代码在每个按钮上创建 DOM 节点，并在创建1000000个字符串时执行大量工作。</span><span class="sxs-lookup"><span data-stu-id="b467e-180">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button press and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="b467e-181">下面的关键内容是，JS 堆的结束时间比它的开始时间更高 \ ("开始" 是强制垃圾回收 \ ) 之后的点。</span><span class="sxs-lookup"><span data-stu-id="b467e-181">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="b467e-182">在现实世界中，如果你看到此模式增加了 JS 堆大小或节点大小，则可能会定义内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="b467e-182">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <span data-ttu-id="b467e-183">利用堆快照发现分离的 DOM 树内存泄漏</span><span class="sxs-lookup"><span data-stu-id="b467e-183">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="b467e-184">仅当在页面上运行的 DOM 树或 JavaScript 代码中没有对节点的引用时，才会对 DOM 节点进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b467e-184">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="b467e-185">当从 DOM 树中删除节点但某些 JavaScript 仍引用它时，称该节点已 "分离"。</span><span class="sxs-lookup"><span data-stu-id="b467e-185">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="b467e-186">分离的 DOM 节点是内存泄漏的常见原因。</span><span class="sxs-lookup"><span data-stu-id="b467e-186">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="b467e-187">本部分介绍如何使用 DevTools 中的堆探查器来标识已分离的节点。</span><span class="sxs-lookup"><span data-stu-id="b467e-187">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="b467e-188">下面是分离的 DOM 节点的简单示例。</span><span class="sxs-lookup"><span data-stu-id="b467e-188">Here is a simple example of detached DOM nodes.</span></span>  

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

<span data-ttu-id="b467e-189">选择代码中引用的按钮将创建一个 `ul` 具有十 `li` 个子元素的节点。</span><span class="sxs-lookup"><span data-stu-id="b467e-189">Selecting the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="b467e-190">节点由代码引用，但在 DOM 树中不存在，因此每个节点都是分离的。</span><span class="sxs-lookup"><span data-stu-id="b467e-190">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="b467e-191">堆快照是标识已分离节点的一种方法。</span><span class="sxs-lookup"><span data-stu-id="b467e-191">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="b467e-192">正如名称所示，堆快照显示了如何在该快照的时间点在 JS 对象和 DOM 节点之间分配内存。</span><span class="sxs-lookup"><span data-stu-id="b467e-192">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="b467e-193">若要创建快照，请打开 DevTools 并转到 " **内存** " 面板，选择 " **堆快照** " 单选按钮，然后按 " **拍摄快照** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="b467e-193">To create a snapshot, open DevTools and go to the **Memory** panel, select the **Heap snapshot** radio button, and then press the **Take snapshot** button.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   <span data-ttu-id="b467e-195">图4：采用堆快照</span><span class="sxs-lookup"><span data-stu-id="b467e-195">Figure 4:  Take heap snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="b467e-196">快照可能需要一些时间才能处理和加载。</span><span class="sxs-lookup"><span data-stu-id="b467e-196">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="b467e-197">完成后，从左侧面板 \ ("已命名的 **堆快照**\ ) " 中选择它。</span><span class="sxs-lookup"><span data-stu-id="b467e-197">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="b467e-198">`Detached`在 "**类筛选器**" 文本框中键入以搜索已分离的 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="b467e-198">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   <span data-ttu-id="b467e-200">图5：对已分离节点的筛选</span><span class="sxs-lookup"><span data-stu-id="b467e-200">Figure 5:  Filtering for detached nodes</span></span>  
:::image-end:::  

<span data-ttu-id="b467e-201">展开 carats 以调查已分离的树。</span><span class="sxs-lookup"><span data-stu-id="b467e-201">Expand the carats to investigate a detached tree.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   <span data-ttu-id="b467e-203">图6：调查分离树</span><span class="sxs-lookup"><span data-stu-id="b467e-203">Figure 6:  Investigating detached tree</span></span>  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="b467e-204">选择要进一步调查的节点。</span><span class="sxs-lookup"><span data-stu-id="b467e-204">Select a node to investigate it further.</span></span>  <span data-ttu-id="b467e-205">在 " **对象** " 窗格中，你可以查看有关引用它的代码的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b467e-205">In the **Objects** pane you are able to see more information about the code that is referencing it.</span></span>  <span data-ttu-id="b467e-206">例如，在下图中，你可以看到该 `detachedNodes` 变量正在引用该节点。</span><span class="sxs-lookup"><span data-stu-id="b467e-206">For example, in the following figure you are able to see that the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="b467e-207">若要修复此特定内存泄漏，应研究使用该变量的代码， `detachedUNode` 并确保删除不再需要的节点引用。</span><span class="sxs-lookup"><span data-stu-id="b467e-207">To fix this particular memory leak, you should study the code that uses the `detachedUNode` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   <span data-ttu-id="b467e-209">图7：调查节点</span><span class="sxs-lookup"><span data-stu-id="b467e-209">Figure 7:  Investigating a node</span></span>  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <span data-ttu-id="b467e-210">在日程表上通过分配检测识别 JS 堆内存泄漏</span><span class="sxs-lookup"><span data-stu-id="b467e-210">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="b467e-211">**时间线上的分配检测** 是另一个工具，可帮助你跟踪 JS 堆中的内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="b467e-211">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="b467e-212">使用以下代码 **在时间线上演示分配检测**  。</span><span class="sxs-lookup"><span data-stu-id="b467e-212">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="b467e-213">每次推送代码中引用的按钮时，将向数组中添加一个1000000字符的字符串 `x` 。</span><span class="sxs-lookup"><span data-stu-id="b467e-213">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="b467e-214">若要在日程表上记录分配检测，请打开 DevTools，转到 " **内存** " 面板，选择 " **时间线上的分配检测** " 单选按钮，按 " **开始** " 按钮，执行怀疑导致内存泄漏的操作，然后按 " **停止录制堆配置文件** ![ 停止录制" ][ImageStopRecordingIcon] 按钮。</span><span class="sxs-lookup"><span data-stu-id="b467e-214">To record an Allocation instrumentation on timeline, open DevTools, go to the **Memory** panel, select the **Allocation instrumentation on timeline** radio button, press the **Start** button, perform the action that you suspect is causing the memory leak, and then press the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="b467e-215">录制时，注意是否在时间线上显示分配检测上的任何蓝色条，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="b467e-215">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   <span data-ttu-id="b467e-217">图8：新分配</span><span class="sxs-lookup"><span data-stu-id="b467e-217">Figure 8:  New allocations</span></span>  
:::image-end:::  

<span data-ttu-id="b467e-218">这些蓝色条表示新的内存分配。</span><span class="sxs-lookup"><span data-stu-id="b467e-218">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="b467e-219">这些新的内存分配是内存泄漏的候选项。</span><span class="sxs-lookup"><span data-stu-id="b467e-219">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="b467e-220">你可以放大条形以筛选 " **构造函数** " 窗格，以便仅显示在指定时间范围内分配的对象。</span><span class="sxs-lookup"><span data-stu-id="b467e-220">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   <span data-ttu-id="b467e-222">图9：已缩放的分配日程表</span><span class="sxs-lookup"><span data-stu-id="b467e-222">Figure 9:  Zoomed allocation timeline</span></span>  
:::image-end:::  

<span data-ttu-id="b467e-223">展开对象并选择值以在 " **对象** " 窗格中查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="b467e-223">Expand the object and select the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="b467e-224">例如，在下图中，通过查看新分配的对象的详细信息，你应该能够看到它已分配给 `x` 作用域中的变量 `Window` 。</span><span class="sxs-lookup"><span data-stu-id="b467e-224">For example, in the following figure, by viewing the details of the object that was newly allocated, you should be able to see that it was allocated to the `x` variable in the `Window` scope.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   <span data-ttu-id="b467e-226">图10：对象详细信息</span><span class="sxs-lookup"><span data-stu-id="b467e-226">Figure 10:  Object details</span></span>  
:::image-end:::  

## <span data-ttu-id="b467e-227">调查按函数分配的内存</span><span class="sxs-lookup"><span data-stu-id="b467e-227">Investigate memory allocation by function</span></span>  

<span data-ttu-id="b467e-228">使用 **分配采样** 分析类型，查看由 JavaScript 函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="b467e-228">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   <span data-ttu-id="b467e-230">图11：记录分配抽样</span><span class="sxs-lookup"><span data-stu-id="b467e-230">Figure 11:  Record Allocation sampling</span></span>  
:::image-end:::  

1.  <span data-ttu-id="b467e-231">选择 " **分配采样** " 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="b467e-231">Select the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="b467e-232">如果页面上有工作人员，你可以使用 " **开始** " 按钮旁边的下拉菜单选择它作为分析目标。</span><span class="sxs-lookup"><span data-stu-id="b467e-232">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="b467e-233">按 " **开始** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="b467e-233">Press the **Start** button.</span></span>  
1.  <span data-ttu-id="b467e-234">在要调查的页面上执行操作。</span><span class="sxs-lookup"><span data-stu-id="b467e-234">Perform the actions on the page which you want to investigate.</span></span>  
1.  <span data-ttu-id="b467e-235">完成所有操作后，按 " **停止** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="b467e-235">Press the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="b467e-236">DevTools 显示按函数划分的内存分配。</span><span class="sxs-lookup"><span data-stu-id="b467e-236">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="b467e-237">默认视图为 \*\* (自下而上的 "下) \*\*"，显示分配了最高内存的函数。</span><span class="sxs-lookup"><span data-stu-id="b467e-237">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   <span data-ttu-id="b467e-239">图12：分配抽样</span><span class="sxs-lookup"><span data-stu-id="b467e-239">Figure 12:  Allocation sampling</span></span>  
:::image-end:::  

## <span data-ttu-id="b467e-240">经常发现垃圾回收</span><span class="sxs-lookup"><span data-stu-id="b467e-240">Spot frequent garbage collections</span></span>  

<span data-ttu-id="b467e-241">如果您的页面看起来经常暂停，则您可能遇到了垃圾回收问题。</span><span class="sxs-lookup"><span data-stu-id="b467e-241">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="b467e-242">你可以使用 Microsoft Edge 浏览器任务管理器或性能内存录制来发现频繁的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b467e-242">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="b467e-243">在 Microsoft Edge 浏览器任务管理器中，频繁上升和下降的 **内存** 或 **JavaScript 内存** 值表示频繁的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b467e-243">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="b467e-244">在性能录制中，频繁更改 \ (升高和下降 \ ) 到 JS 堆或节点计数图指示频繁的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="b467e-244">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="b467e-245">确定问题后，您可以 **在时间线录制上使用分配检测** 来查明内存的分配位置以及导致分配的函数。</span><span class="sxs-lookup"><span data-stu-id="b467e-245">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

## <span data-ttu-id="b467e-246">与 Microsoft Edge 开发人员工具团队联系</span><span class="sxs-lookup"><span data-stu-id="b467e-246">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "记录性能-性能分析参考"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="b467e-248">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="b467e-248">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="b467e-249">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="b467e-249">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="b467e-251">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="b467e-251">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
