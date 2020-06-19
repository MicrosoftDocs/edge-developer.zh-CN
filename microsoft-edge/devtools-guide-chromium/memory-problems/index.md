---
title: 修复内存问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/10/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: b9e6e2af333257f0cbe0a4a354dcd1d7b862af9c
ms.sourcegitcommit: 037a2d62333691104c9accb4862968f80a3465a2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/18/2020
ms.locfileid: "10751987"
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

# <span data-ttu-id="dad5a-103">修复内存问题</span><span class="sxs-lookup"><span data-stu-id="dad5a-103">Fix Memory Problems</span></span>  

<span data-ttu-id="dad5a-104">了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存膨胀和频繁垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="dad5a-104">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <span data-ttu-id="dad5a-105">摘要</span><span class="sxs-lookup"><span data-stu-id="dad5a-105">Summary</span></span>  

*   <span data-ttu-id="dad5a-106">使用 Microsoft Edge 浏览器任务管理器了解你的页面当前使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="dad5a-106">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="dad5a-107">使用 "**内存**" 面板在一段时间内可视化内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="dad5a-107">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="dad5a-108">使用**堆快照**标识分离的 DOM 树 \ （内存泄漏的常见原因 \）。</span><span class="sxs-lookup"><span data-stu-id="dad5a-108">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="dad5a-109">了解在你的 JavaScript 堆中分配新内存的时间（JS 堆 \）和**时间线上的分配检测**。</span><span class="sxs-lookup"><span data-stu-id="dad5a-109">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <span data-ttu-id="dad5a-110">概述</span><span class="sxs-lookup"><span data-stu-id="dad5a-110">Overview</span></span>  

<span data-ttu-id="dad5a-111">在**铁路**性能模型的精神中，你的性能工作的重点应是你的用户。</span><span class="sxs-lookup"><span data-stu-id="dad5a-111">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="dad5a-112">内存问题很重要，因为它们通常由用户觉察。</span><span class="sxs-lookup"><span data-stu-id="dad5a-112">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="dad5a-113">用户可能会通过以下方式来感知内存问题：</span><span class="sxs-lookup"><span data-stu-id="dad5a-113">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="dad5a-114">**随着时间的推移，页面性能逐渐变得越来越严重**。</span><span class="sxs-lookup"><span data-stu-id="dad5a-114">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="dad5a-115">这可能是内存泄漏的症状。</span><span class="sxs-lookup"><span data-stu-id="dad5a-115">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="dad5a-116">当页面中的 bug 导致页面逐渐使用越来越多的内存时，会发生内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="dad5a-116">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="dad5a-117">**页面性能始终不正确**。</span><span class="sxs-lookup"><span data-stu-id="dad5a-117">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="dad5a-118">这可能是内存膨胀的症状。</span><span class="sxs-lookup"><span data-stu-id="dad5a-118">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="dad5a-119">内存膨胀是指页面使用的内存超过最佳页面速度所需的内存。</span><span class="sxs-lookup"><span data-stu-id="dad5a-119">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="dad5a-120">**页面性能延迟或显示为经常暂停**。</span><span class="sxs-lookup"><span data-stu-id="dad5a-120">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="dad5a-121">这可能是频繁垃圾回收的症状。</span><span class="sxs-lookup"><span data-stu-id="dad5a-121">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="dad5a-122">垃圾回收是浏览器回收内存的时候。</span><span class="sxs-lookup"><span data-stu-id="dad5a-122">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="dad5a-123">浏览器决定何时发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="dad5a-123">The browser decides when this happens.</span></span>  <span data-ttu-id="dad5a-124">在集合期间，将暂停运行的所有脚本。</span><span class="sxs-lookup"><span data-stu-id="dad5a-124">During collections, all script running is paused.</span></span>  <span data-ttu-id="dad5a-125">因此，如果浏览器对大量垃圾回收，脚本运行时将会暂停很多事情。</span><span class="sxs-lookup"><span data-stu-id="dad5a-125">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <span data-ttu-id="dad5a-126">内存膨胀： "过多" 是多少？</span><span class="sxs-lookup"><span data-stu-id="dad5a-126">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="dad5a-127">内存泄漏很容易定义。</span><span class="sxs-lookup"><span data-stu-id="dad5a-127">A memory leak is easy to define.</span></span>  <span data-ttu-id="dad5a-128">如果某个网站在使用更多内存的情况下逐渐增加，则你有泄漏。</span><span class="sxs-lookup"><span data-stu-id="dad5a-128">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="dad5a-129">但是内存膨胀比固定更难。</span><span class="sxs-lookup"><span data-stu-id="dad5a-129">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="dad5a-130">什么是 "使用过多的内存"？</span><span class="sxs-lookup"><span data-stu-id="dad5a-130">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="dad5a-131">此处没有任何硬编号，因为不同的设备和浏览器具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="dad5a-131">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="dad5a-132">在高端智能手机上正常运行的同一页面可能会在低端智能手机上崩溃。</span><span class="sxs-lookup"><span data-stu-id="dad5a-132">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="dad5a-133">此处的关键是使用滑轨模型，并关注您的用户。</span><span class="sxs-lookup"><span data-stu-id="dad5a-133">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="dad5a-134">了解你的用户最常用的设备，然后在这些设备上测试你的页面。</span><span class="sxs-lookup"><span data-stu-id="dad5a-134">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="dad5a-135">如果体验持续很差，则页面可能超出了这些设备的内存功能。</span><span class="sxs-lookup"><span data-stu-id="dad5a-135">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <span data-ttu-id="dad5a-136">使用 Microsoft Edge 浏览器任务管理器实时监视内存使用情况</span><span class="sxs-lookup"><span data-stu-id="dad5a-136">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="dad5a-137">使用 Microsoft Edge 浏览器任务管理器作为内存问题调查的起始点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-137">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="dad5a-138">Microsoft Edge 浏览器任务管理器是一个实时监视器，可告诉你页面当前使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="dad5a-138">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="dad5a-139">按下 `Shift` + `Esc` 或转到 Microsoft edge 主菜单，然后选择 "**更多工具**  >  **浏览器任务管理**器" 以打开 Microsoft Edge 浏览器任务管理器。</span><span class="sxs-lookup"><span data-stu-id="dad5a-139">Press `Shift`+`Esc` or go to the Microsoft Edge main menu and select **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       <span data-ttu-id="dad5a-141">图1：打开 Microsoft Edge 浏览器任务管理器</span><span class="sxs-lookup"><span data-stu-id="dad5a-141">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="dad5a-142">将鼠标悬停在 Microsoft Edge 浏览器任务管理器的表标题上，打开上下文菜单 \ （右键单击 \），然后启用**JavaScript 内存**。</span><span class="sxs-lookup"><span data-stu-id="dad5a-142">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="启用 JavaScript 内存" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       <span data-ttu-id="dad5a-144">图2：启用 JavaScript 内存</span><span class="sxs-lookup"><span data-stu-id="dad5a-144">Figure 2:  Enable JavaScript memory</span></span>  
    :::image-end:::  
    
<span data-ttu-id="dad5a-145">这两个列告诉你有关页面如何使用内存的不同内容。</span><span class="sxs-lookup"><span data-stu-id="dad5a-145">These two columns tell you different things about how your page is using memory.</span></span>  

*   <span data-ttu-id="dad5a-146">"**内存**" 列表示本机内存。</span><span class="sxs-lookup"><span data-stu-id="dad5a-146">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="dad5a-147">DOM 节点存储在本机内存中。</span><span class="sxs-lookup"><span data-stu-id="dad5a-147">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="dad5a-148">如果此值增加，则会创建 DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-148">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="dad5a-149">**JavaScript 内存**列表示 JS 堆栈。</span><span class="sxs-lookup"><span data-stu-id="dad5a-149">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="dad5a-150">此列包含两个值。</span><span class="sxs-lookup"><span data-stu-id="dad5a-150">This column contains two values.</span></span>  <span data-ttu-id="dad5a-151">您感兴趣的值是活动号码 \ （圆括号中的数字 \）。</span><span class="sxs-lookup"><span data-stu-id="dad5a-151">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="dad5a-152">活动号码表示页面上可访问对象所使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="dad5a-152">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="dad5a-153">如果此数字增加，则表示正在创建新对象，或者现有对象正在增长。</span><span class="sxs-lookup"><span data-stu-id="dad5a-153">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <span data-ttu-id="dad5a-154">利用性能面板可视化内存泄漏</span><span class="sxs-lookup"><span data-stu-id="dad5a-154">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="dad5a-155">您也可以将 "性能" 面板用作调查中的另一个起始点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-155">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="dad5a-156">"性能" 面板可帮助你在一段时间内对页面的内存使用进行可视化处理。</span><span class="sxs-lookup"><span data-stu-id="dad5a-156">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="dad5a-157">在 DevTools 上打开**性能**面板。</span><span class="sxs-lookup"><span data-stu-id="dad5a-157">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="dad5a-158">启用 "**内存**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="dad5a-158">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="dad5a-159">[进行录制][DevtoolsEvaluatePerformanceReferenceRecord]。</span><span class="sxs-lookup"><span data-stu-id="dad5a-159">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="dad5a-160">使用强制垃圾回收开始和结束录制是一种很好的做法。</span><span class="sxs-lookup"><span data-stu-id="dad5a-160">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="dad5a-161">在录制以强制垃圾回收时，选择 "**收集垃圾** ![ 强制垃圾回收" ][ImageForceGarbageCollectionIcon] 按钮。</span><span class="sxs-lookup"><span data-stu-id="dad5a-161">Select the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording to force garbage collection.</span></span>  

<span data-ttu-id="dad5a-162">若要演示内存录制，请考虑以下代码：</span><span class="sxs-lookup"><span data-stu-id="dad5a-162">To demonstrate memory recordings, consider the code below:</span></span>  

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

<span data-ttu-id="dad5a-163">每次按下代码中引用的按钮时，将 `div` 向文档正文追加10000节点，并将1000000字符的字符串 `x` 推送到 `x` 数组中。</span><span class="sxs-lookup"><span data-stu-id="dad5a-163">Every time that the button referenced in the code is pressed, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="dad5a-164">运行上面的代码示例将在 "**性能**" 面板中生成一条记录，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="dad5a-164">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="简单增长" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   <span data-ttu-id="dad5a-166">图3：简单增长</span><span class="sxs-lookup"><span data-stu-id="dad5a-166">Figure 3:  Simple growth</span></span>  
:::image-end:::  

<span data-ttu-id="dad5a-167">首先是用户界面的说明。</span><span class="sxs-lookup"><span data-stu-id="dad5a-167">First, an explanation of the user interface.</span></span>  <span data-ttu-id="dad5a-168">"**概述**" 窗格中的**堆**图形 \ （在**NET**\）表示 JS 堆。</span><span class="sxs-lookup"><span data-stu-id="dad5a-168">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="dad5a-169">"**概述**" 窗格下方是**计数器**窗格。</span><span class="sxs-lookup"><span data-stu-id="dad5a-169">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="dad5a-170">在这里，你可以查看由 JS 堆栈 \ （与**概述**窗格中的**堆**图 \）、文档、DOM 节点、侦听器和 GPU 内存划分的内存使用情况。</span><span class="sxs-lookup"><span data-stu-id="dad5a-170">Here you are able to see memory usage broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="dad5a-171">禁用复选框会将其从图形中隐藏。</span><span class="sxs-lookup"><span data-stu-id="dad5a-171">Disabling a checkbox hides it from the graph.</span></span>  

<span data-ttu-id="dad5a-172">现在，与上图中的代码分析进行了比较。</span><span class="sxs-lookup"><span data-stu-id="dad5a-172">Now, an analysis of the code compared with the previous figure.</span></span>  <span data-ttu-id="dad5a-173">如果你查看节点计数器 \ （绿色图形 \），你可以看到它与代码完全匹配。</span><span class="sxs-lookup"><span data-stu-id="dad5a-173">If you look at the node counter \(the green graph\) you are able to see that it matches up cleanly with the code.</span></span>  <span data-ttu-id="dad5a-174">节点计数在离散步骤中增加。</span><span class="sxs-lookup"><span data-stu-id="dad5a-174">The node count increases in discrete steps.</span></span>  <span data-ttu-id="dad5a-175">你可能会假定节点计数中的每个增加都是对的调用 `grow()` 。</span><span class="sxs-lookup"><span data-stu-id="dad5a-175">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="dad5a-176">JS 堆图形 \ （蓝色图形 \）不十分简单。</span><span class="sxs-lookup"><span data-stu-id="dad5a-176">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="dad5a-177">根据最佳做法，第一个 dip 实际上是强制垃圾回收 \ （通过按 "**收集垃圾** ![ 强制垃圾回收" ][ImageForceGarbageCollectionIcon] 按钮实现）。</span><span class="sxs-lookup"><span data-stu-id="dad5a-177">In keeping with best practices, the first dip is actually a forced garbage collection \(achieved by pressing the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="dad5a-178">在录制过程中，你可以看到 JS 堆大小峰值。</span><span class="sxs-lookup"><span data-stu-id="dad5a-178">As the recording progresses you are able to see that the JS heap size spikes.</span></span>  <span data-ttu-id="dad5a-179">这是自然且预期的： JavaScript 代码在每个按钮上创建 DOM 节点，并在创建1000000个字符串时执行大量工作。</span><span class="sxs-lookup"><span data-stu-id="dad5a-179">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button press and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="dad5a-180">此处的关键内容是，JS 堆终止高于开始的位置 \ （"开始" 是强制垃圾回收之后的点）。</span><span class="sxs-lookup"><span data-stu-id="dad5a-180">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="dad5a-181">在现实世界中，如果你看到此模式增加了 JS 堆大小或节点大小，则可能会定义内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="dad5a-181">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <span data-ttu-id="dad5a-182">利用堆快照发现分离的 DOM 树内存泄漏</span><span class="sxs-lookup"><span data-stu-id="dad5a-182">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="dad5a-183">仅当在页面上运行的 DOM 树或 JavaScript 代码中没有对节点的引用时，才会对 DOM 节点进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="dad5a-183">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="dad5a-184">当从 DOM 树中删除节点但某些 JavaScript 仍引用它时，称该节点已 "分离"。</span><span class="sxs-lookup"><span data-stu-id="dad5a-184">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="dad5a-185">分离的 DOM 节点是内存泄漏的常见原因。</span><span class="sxs-lookup"><span data-stu-id="dad5a-185">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="dad5a-186">本部分介绍如何使用 DevTools 中的堆探查器来标识已分离的节点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-186">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="dad5a-187">下面是分离的 DOM 节点的简单示例。</span><span class="sxs-lookup"><span data-stu-id="dad5a-187">Here is a simple example of detached DOM nodes.</span></span>  

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

<span data-ttu-id="dad5a-188">选择代码中引用的按钮将创建一个 `ul` 具有十 `li` 个子元素的节点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-188">Selecting the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="dad5a-189">节点由代码引用，但在 DOM 树中不存在，因此每个节点都是分离的。</span><span class="sxs-lookup"><span data-stu-id="dad5a-189">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="dad5a-190">堆快照是标识已分离节点的一种方法。</span><span class="sxs-lookup"><span data-stu-id="dad5a-190">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="dad5a-191">正如名称所示，堆快照显示了如何在该快照的时间点在 JS 对象和 DOM 节点之间分配内存。</span><span class="sxs-lookup"><span data-stu-id="dad5a-191">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="dad5a-192">若要创建快照，请打开 DevTools 并转到 "**内存**" 面板，选择 "**堆快照**" 单选按钮，然后按 "**拍摄快照**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dad5a-192">To create a snapshot, open DevTools and go to the **Memory** panel, select the **Heap snapshot** radio button, and then press the **Take snapshot** button.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="获取堆快照" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   <span data-ttu-id="dad5a-194">图4：采用堆快照</span><span class="sxs-lookup"><span data-stu-id="dad5a-194">Figure 4:  Take heap snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="dad5a-195">快照可能需要一些时间才能处理和加载。</span><span class="sxs-lookup"><span data-stu-id="dad5a-195">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="dad5a-196">完成后，从左侧面板中选择它（命名**堆快照**\）。</span><span class="sxs-lookup"><span data-stu-id="dad5a-196">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="dad5a-197">`Detached`在 "**类筛选器**" 文本框中键入以搜索已分离的 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="dad5a-197">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="已分离节点的筛选" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   <span data-ttu-id="dad5a-199">图5：对已分离节点的筛选</span><span class="sxs-lookup"><span data-stu-id="dad5a-199">Figure 5:  Filtering for detached nodes</span></span>  
:::image-end:::  

<span data-ttu-id="dad5a-200">展开 carats 以调查已分离的树。</span><span class="sxs-lookup"><span data-stu-id="dad5a-200">Expand the carats to investigate a detached tree.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="调查分离树" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   <span data-ttu-id="dad5a-202">图6：调查分离树</span><span class="sxs-lookup"><span data-stu-id="dad5a-202">Figure 6:  Investigating detached tree</span></span>  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="dad5a-203">选择要进一步调查的节点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-203">Select a node to investigate it further.</span></span>  <span data-ttu-id="dad5a-204">在 "**对象**" 窗格中，你可以查看有关引用它的代码的详细信息。</span><span class="sxs-lookup"><span data-stu-id="dad5a-204">In the **Objects** pane you are able to see more information about the code that is referencing it.</span></span>  <span data-ttu-id="dad5a-205">例如，在下图中，你可以看到该 `detachedNodes` 变量正在引用该节点。</span><span class="sxs-lookup"><span data-stu-id="dad5a-205">For example, in the following figure you are able to see that the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="dad5a-206">若要修复此特定内存泄漏，应研究使用该变量的代码， `detachedNodes` 并确保删除不再需要的节点引用。</span><span class="sxs-lookup"><span data-stu-id="dad5a-206">To fix this particular memory leak, you should study the code that uses the `detachedNodes` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="调查节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   <span data-ttu-id="dad5a-208">图7：调查节点</span><span class="sxs-lookup"><span data-stu-id="dad5a-208">Figure 7:  Investigating a node</span></span>  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <span data-ttu-id="dad5a-209">在日程表上通过分配检测识别 JS 堆内存泄漏</span><span class="sxs-lookup"><span data-stu-id="dad5a-209">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="dad5a-210">**时间线上的分配检测**是另一个工具，可帮助你跟踪 JS 堆中的内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="dad5a-210">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="dad5a-211">使用以下代码**在时间线上演示分配检测**。</span><span class="sxs-lookup"><span data-stu-id="dad5a-211">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="dad5a-212">每次推送代码中引用的按钮时，将向数组中添加一个1000000字符的字符串 `x` 。</span><span class="sxs-lookup"><span data-stu-id="dad5a-212">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="dad5a-213">若要在日程表上记录分配检测，请打开 DevTools，转到 "**内存**" 面板，选择 "**时间线上的分配检测**" 单选按钮，按 "**开始**" 按钮，执行怀疑导致内存泄漏的操作，然后按 "**停止录制堆配置文件** ![ 停止录制" ][ImageStopRecordingIcon] 按钮。</span><span class="sxs-lookup"><span data-stu-id="dad5a-213">To record an Allocation instrumentation on timeline, open DevTools, go to the **Memory** panel, select the **Allocation instrumentation on timeline** radio button, press the **Start** button, perform the action that you suspect is causing the memory leak, and then press the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="dad5a-214">录制时，注意是否在时间线上显示分配检测上的任何蓝色条，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="dad5a-214">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新分配" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   <span data-ttu-id="dad5a-216">图8：新分配</span><span class="sxs-lookup"><span data-stu-id="dad5a-216">Figure 8:  New allocations</span></span>  
:::image-end:::  

<span data-ttu-id="dad5a-217">这些蓝色条表示新的内存分配。</span><span class="sxs-lookup"><span data-stu-id="dad5a-217">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="dad5a-218">这些新的内存分配是内存泄漏的候选项。</span><span class="sxs-lookup"><span data-stu-id="dad5a-218">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="dad5a-219">你可以放大条形以筛选 "**构造函数**" 窗格，以便仅显示在指定时间范围内分配的对象。</span><span class="sxs-lookup"><span data-stu-id="dad5a-219">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="已缩放的分配日程表" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   <span data-ttu-id="dad5a-221">图9：已缩放的分配日程表</span><span class="sxs-lookup"><span data-stu-id="dad5a-221">Figure 9:  Zoomed allocation timeline</span></span>  
:::image-end:::  

<span data-ttu-id="dad5a-222">展开对象并选择值以在 "**对象**" 窗格中查看更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="dad5a-222">Expand the object and select the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="dad5a-223">例如，在下图中，通过查看新分配的对象的详细信息，你应该能够看到它已分配给 `x` 作用域中的变量 `Window` 。</span><span class="sxs-lookup"><span data-stu-id="dad5a-223">For example, in the following figure, by viewing the details of the object that was newly allocated, you should be able to see that it was allocated to the `x` variable in the `Window` scope.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="对象详细信息" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   <span data-ttu-id="dad5a-225">图10：对象详细信息</span><span class="sxs-lookup"><span data-stu-id="dad5a-225">Figure 10:  Object details</span></span>  
:::image-end:::  

## <span data-ttu-id="dad5a-226">调查按函数分配的内存</span><span class="sxs-lookup"><span data-stu-id="dad5a-226">Investigate memory allocation by function</span></span>  

<span data-ttu-id="dad5a-227">使用**分配采样**分析类型，查看由 JavaScript 函数分配的内存。</span><span class="sxs-lookup"><span data-stu-id="dad5a-227">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="记录分配抽样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   <span data-ttu-id="dad5a-229">图11：记录分配抽样</span><span class="sxs-lookup"><span data-stu-id="dad5a-229">Figure 11:  Record Allocation sampling</span></span>  
:::image-end:::  

1.  <span data-ttu-id="dad5a-230">选择 "**分配采样**" 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="dad5a-230">Select the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="dad5a-231">如果页面上有工作人员，你可以使用 "**开始**" 按钮旁边的下拉菜单选择它作为分析目标。</span><span class="sxs-lookup"><span data-stu-id="dad5a-231">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="dad5a-232">按 "**开始**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dad5a-232">Press the **Start** button.</span></span>  
1.  <span data-ttu-id="dad5a-233">在要调查的页面上执行操作。</span><span class="sxs-lookup"><span data-stu-id="dad5a-233">Perform the actions on the page which you want to investigate.</span></span>  
1.  <span data-ttu-id="dad5a-234">完成所有操作后，按 "**停止**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dad5a-234">Press the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="dad5a-235">DevTools 显示按函数划分的内存分配。</span><span class="sxs-lookup"><span data-stu-id="dad5a-235">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="dad5a-236">默认视图为 "**粗" （下）**，显示分配了最高内存的函数。</span><span class="sxs-lookup"><span data-stu-id="dad5a-236">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="分配抽样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   <span data-ttu-id="dad5a-238">图12：分配抽样</span><span class="sxs-lookup"><span data-stu-id="dad5a-238">Figure 12:  Allocation sampling</span></span>  
:::image-end:::  

## <span data-ttu-id="dad5a-239">经常发现垃圾回收</span><span class="sxs-lookup"><span data-stu-id="dad5a-239">Spot frequent garbage collections</span></span>  

<span data-ttu-id="dad5a-240">如果您的页面看起来经常暂停，则您可能遇到了垃圾回收问题。</span><span class="sxs-lookup"><span data-stu-id="dad5a-240">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="dad5a-241">你可以使用 Microsoft Edge 浏览器任务管理器或性能内存录制来发现频繁的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="dad5a-241">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="dad5a-242">在 Microsoft Edge 浏览器任务管理器中，频繁上升和下降的**内存**或**JavaScript 内存**值表示频繁的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="dad5a-242">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="dad5a-243">在性能录制中，经常更改 \ （上升和下降 \）到 JS 堆或节点计数图表指示频繁的垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="dad5a-243">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="dad5a-244">确定问题后，您可以**在时间线录制上使用分配检测**来查明内存的分配位置以及导致分配的函数。</span><span class="sxs-lookup"><span data-stu-id="dad5a-244">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "记录性能-性能分析参考"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="dad5a-246">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="dad5a-246">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="dad5a-247">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)，由[Kayce Basques][KayceBasques] \ （技术作者、Chrome DevTools \ & Lighthouse \）创作。</span><span class="sxs-lookup"><span data-stu-id="dad5a-247">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="dad5a-249">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="dad5a-249">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
