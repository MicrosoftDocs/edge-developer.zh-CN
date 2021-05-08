---
description: 了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存不足和频繁垃圾回收。
title: 修复内存问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: afaea8ca561bd975490d9153cda40877786a0f08
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397830"
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

# <a name="fix-memory-problems"></a><span data-ttu-id="9e5a5-104">修复内存问题</span><span class="sxs-lookup"><span data-stu-id="9e5a5-104">Fix memory problems</span></span>  

<span data-ttu-id="9e5a5-105">了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存不足和频繁垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-105">Learn how to use Microsoft Edge and DevTools to find memory issues that affect page performance, including memory leaks, memory bloat, and frequent garbage collections.</span></span>  

### <a name="summary"></a><span data-ttu-id="9e5a5-106">摘要</span><span class="sxs-lookup"><span data-stu-id="9e5a5-106">Summary</span></span>  

*   <span data-ttu-id="9e5a5-107">了解你的页面当前与浏览器任务管理器Microsoft Edge的内存量。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-107">Find out how much memory your page is currently using with the Microsoft Edge Browser Task Manager.</span></span>  
*   <span data-ttu-id="9e5a5-108">使用内存面板直观呈现一段时间 **的内存** 使用情况。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-108">Visualize memory usage over time with the **Memory** panel.</span></span>  
*   <span data-ttu-id="9e5a5-109">使用堆快照 (分离的 DOM 树 \) 内存泄漏 **的常见原因**。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-109">Identify detached DOM trees \(a common cause of memory leaks\) with **Heap snapshot**.</span></span>  
*   <span data-ttu-id="9e5a5-110">在时间线上通过 Allocation instrumentation 了解 JavaScript 堆 \ (JS 堆\) **分配新内存的时间**。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-110">Find out when new memory is being allocated in your JavaScript heap \(JS heap\) with **Allocation instrumentation on timeline**.</span></span>  

## <a name="overview"></a><span data-ttu-id="9e5a5-111">概述</span><span class="sxs-lookup"><span data-stu-id="9e5a5-111">Overview</span></span>  

<span data-ttu-id="9e5a5-112">在 RAIL **性能模型** 方面，性能工作的重点应该是用户。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-112">In the spirit of the **RAIL** performance model, the focus of your performance efforts should be your users.</span></span>  

<!--todo: add RAIL section when available  -->  

<span data-ttu-id="9e5a5-113">内存问题非常重要，因为它们经常被用户感知。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-113">Memory issues are important because they are often perceivable by users.</span></span>  <span data-ttu-id="9e5a5-114">用户可能通过以下方式发现内存问题：</span><span class="sxs-lookup"><span data-stu-id="9e5a5-114">Users may perceive memory issues in the following ways:</span></span>  

*   <span data-ttu-id="9e5a5-115">**随着时间的推移，页面的性能逐渐变差**。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-115">**The performance of a page gets progressively worse over time**.</span></span>  <span data-ttu-id="9e5a5-116">这可能是内存泄漏症状。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-116">This is possibly a symptom of a memory leak.</span></span>  <span data-ttu-id="9e5a5-117">内存泄漏是页面中的 Bug 导致页面随着时间的推移逐渐使用更多内存。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-117">A memory leak is when a bug in the page causes the page to progressively use more and more memory over time.</span></span>  
*   <span data-ttu-id="9e5a5-118">**页面的性能一直不佳**。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-118">**The performance of a page is consistently bad**.</span></span>  <span data-ttu-id="9e5a5-119">这可能是内存不足现象。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-119">This is possibly a symptom of memory bloat.</span></span>  <span data-ttu-id="9e5a5-120">当页面使用的内存多于最佳页面速度所需的内存时，内存量会变大。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-120">Memory bloat is when a page uses more memory than is necessary for optimal page speed.</span></span>  
*   <span data-ttu-id="9e5a5-121">**页面的性能会延迟或看似频繁暂停**。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-121">**The performance of a page is delayed or appears to pause frequently**.</span></span>  <span data-ttu-id="9e5a5-122">这可能是频繁垃圾回收症状。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-122">This is possibly a symptom of frequent garbage collections.</span></span>  <span data-ttu-id="9e5a5-123">垃圾回收是在浏览器回收内存时进行。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-123">Garbage collection is when the browser reclaims memory.</span></span>  <span data-ttu-id="9e5a5-124">浏览器决定何时发生这种情况。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-124">The browser decides when this happens.</span></span>  <span data-ttu-id="9e5a5-125">在集合期间，所有正在运行的脚本将暂停。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-125">During collections, all script running is paused.</span></span>  <span data-ttu-id="9e5a5-126">因此，如果浏览器大量进行垃圾回收，脚本运行时将暂停很多。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-126">So if the browser is garbage collecting a lot, script runtime is going to get paused a lot.</span></span>  

### <a name="memory-bloat-how-much-is-too-much"></a><span data-ttu-id="9e5a5-127">内存过多："太多"多少？</span><span class="sxs-lookup"><span data-stu-id="9e5a5-127">Memory bloat: how much is "too much"?</span></span>  

<span data-ttu-id="9e5a5-128">内存泄漏易于定义。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-128">A memory leak is easy to define.</span></span>  <span data-ttu-id="9e5a5-129">如果网站逐渐使用更多内存，则有泄漏。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-129">If a site is progressively using more and more memory, then you have a leak.</span></span>  <span data-ttu-id="9e5a5-130">但是，内存不足有点难以固定。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-130">But memory bloat is a bit harder to pin down.</span></span>  <span data-ttu-id="9e5a5-131">什么限定为"使用过多的内存"？</span><span class="sxs-lookup"><span data-stu-id="9e5a5-131">What qualifies as "using too much memory"?</span></span>  

<span data-ttu-id="9e5a5-132">此处没有硬数，因为不同的设备和浏览器具有不同的功能。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-132">There are no hard numbers here, because different devices and browsers have different capabilities.</span></span>  <span data-ttu-id="9e5a5-133">在高端智能手机上流畅运行的同一页面可能在低端智能手机上崩溃。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-133">The same page that runs smoothly on a high-end smartphone may crash on a low-end smartphone.</span></span>  

<span data-ttu-id="9e5a5-134">这里的关键是使用 RAIL 模型，并专注于你的用户。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-134">The key here is to use the RAIL model and focus on your users.</span></span>  <span data-ttu-id="9e5a5-135">了解哪些设备受你的用户欢迎，然后在这些设备上测试你的页面。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-135">Find out what devices are popular with your users, and then test out your page on those devices.</span></span>  <span data-ttu-id="9e5a5-136">如果体验始终不佳，则页面可能会超出这些设备的内存功能。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-136">If the experience is consistently bad, the page may be exceeding the memory capabilities of those devices.</span></span>  

## <a name="monitor-memory-use-in-realtime-with-the-microsoft-edge-browser-task-manager"></a><span data-ttu-id="9e5a5-137">使用浏览器任务管理器实时Microsoft Edge内存使用</span><span class="sxs-lookup"><span data-stu-id="9e5a5-137">Monitor memory use in realtime with the Microsoft Edge Browser Task Manager</span></span>  

<span data-ttu-id="9e5a5-138">使用Microsoft Edge浏览器任务管理器作为内存问题调查的起点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-138">Use the Microsoft Edge Browser Task Manager as a starting point to your memory issue investigation.</span></span>  <span data-ttu-id="9e5a5-139">浏览器Microsoft Edge管理器是实时监视器，可告诉你页面当前使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-139">The Microsoft Edge Browser Task Manager is a realtime monitor that tells you how much memory a page is currently using.</span></span>  

1.  <span data-ttu-id="9e5a5-140">选择 `Shift` + `Esc` 或导航到\*\*\*\*"Microsoft Edge"主菜单，然后选择"更多工具""浏览器任务管理器"以Microsoft Edge  >  \*\*\*\* 浏览器任务管理器"。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-140">Select `Shift`+`Esc` or navigate to the Microsoft Edge main menu and choose **More tools** > **Browser Task Manager** to open the Microsoft Edge Browser Task Manager.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="打开Microsoft Edge浏览器任务管理器" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       <span data-ttu-id="9e5a5-142">图 1：打开Microsoft Edge浏览器任务管理器</span><span class="sxs-lookup"><span data-stu-id="9e5a5-142">Figure 1:  Opening the Microsoft Edge Browser Task Manager</span></span>  
    :::image-end:::  
    
1.  <span data-ttu-id="9e5a5-143">将鼠标悬停在浏览器任务管理器Microsoft Edge表标题上，打开上下文菜单 \ (右键单击\) ，并启用**JavaScript 内存**。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-143">Hover on the table header of the Microsoft Edge Browser Task Manager, open the contextual menu \(right-click\), and enable **JavaScript memory**.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="启用 JavaScript 内存" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       <span data-ttu-id="9e5a5-145">图 2：启用 JavaScript 内存</span><span class="sxs-lookup"><span data-stu-id="9e5a5-145">Figure 2:  Enable JavaScript memory</span></span>  
    :::image-end:::  
    
<span data-ttu-id="9e5a5-146">这两列告诉您有关页面如何使用内存的不同内容。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-146">These two columns tell you different things about how your page is using memory.</span></span>  

*   <span data-ttu-id="9e5a5-147">" **内存** "列表示本机内存。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-147">The **Memory** column represents native memory.</span></span>  <span data-ttu-id="9e5a5-148">DOM 节点存储在本机内存中。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-148">DOM nodes are stored in native memory.</span></span>  <span data-ttu-id="9e5a5-149">如果此值增加，将创建 DOM 节点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-149">If this value is increasing, DOM nodes are getting created.</span></span>  
*   <span data-ttu-id="9e5a5-150">**"JavaScript 内存"** 列表示 JS 堆。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-150">The **JavaScript Memory** column represents the JS heap.</span></span>  <span data-ttu-id="9e5a5-151">此列包含两个值。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-151">This column contains two values.</span></span>  <span data-ttu-id="9e5a5-152">您感兴趣的值为活动号码 \ (括号\) 。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-152">The value you are interested in is the live number \(the number in parentheses\).</span></span>  <span data-ttu-id="9e5a5-153">实时数表示页面上的可访问对象使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-153">The live number represents how much memory the reachable objects on your page are using.</span></span>  <span data-ttu-id="9e5a5-154">如果此数目增加，则要么正在创建新对象，要么现有对象正在增长。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-154">If this number is increasing, either new objects are being created, or the existing objects are growing.</span></span>  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <a name="visualize-memory-leaks-with-performance-panel"></a><span data-ttu-id="9e5a5-155">使用性能面板可视化内存泄漏</span><span class="sxs-lookup"><span data-stu-id="9e5a5-155">Visualize memory leaks with Performance panel</span></span>  

<span data-ttu-id="9e5a5-156">您还可以使用性能面板作为调查的另一个起点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-156">You may also use the Performance panel as another starting point in your investigation.</span></span>  <span data-ttu-id="9e5a5-157">"性能"面板可帮助您直观呈现页面在一段时间的内存使用。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-157">The Performance panel helps you visualize the memory use of a page over time.</span></span>  

1.  <span data-ttu-id="9e5a5-158">打开\*\*\*\* DevTools 上的"性能"面板。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-158">Open the **Performance** panel on DevTools.</span></span>  
1.  <span data-ttu-id="9e5a5-159">启用" **内存"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-159">Enable the **Memory** checkbox.</span></span>  
1.  <span data-ttu-id="9e5a5-160">[录制][DevtoolsEvaluatePerformanceReferenceRecord]。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-160">[Make a recording][DevtoolsEvaluatePerformanceReferenceRecord].</span></span>  

> [!TIP]
> <span data-ttu-id="9e5a5-161">最佳做法是使用强制垃圾回收开始和结束录制。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-161">It is a good practice to start and end your recording with a forced garbage collection.</span></span>  <span data-ttu-id="9e5a5-162">若要强制进行垃圾回收，请选择记录时 **收集垃圾回收** ![ ][ImageForceGarbageCollectionIcon] 强制垃圾回收按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-162">To force garbage collection, choose the **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button while recording.</span></span>  

<span data-ttu-id="9e5a5-163">若要演示内存录制，请考虑以下代码：</span><span class="sxs-lookup"><span data-stu-id="9e5a5-163">To demonstrate memory recordings, consider the code below:</span></span>  

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

<span data-ttu-id="9e5a5-164">每次选择代码中引用的按钮时，都会将一万个节点追加到文档正文，并且一个包含一百万个字符的字符串 `div` `x` 被推送到 `x` 数组。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-164">Every time that the button referenced in the code is chosen, ten thousand `div` nodes are appended to the document body, and a string of one million `x` characters is pushed onto the `x` array.</span></span>  <span data-ttu-id="9e5a5-165">运行前面的代码示例在性能面板中 **生成** 记录，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-165">Running the previous code sample produces a recording in the **Performance** panel like the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="简单增长" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   <span data-ttu-id="9e5a5-167">图 3：简单增长</span><span class="sxs-lookup"><span data-stu-id="9e5a5-167">Figure 3:  Simple growth</span></span>  
:::image-end:::  

<span data-ttu-id="9e5a5-168">首先，用户界面的说明。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-168">First, an explanation of the user interface.</span></span>  <span data-ttu-id="9e5a5-169">"**概述**"窗格\*\*\*\* \ (中的 HEAP 图) **表示**JS 堆。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-169">The **HEAP** graph in the **Overview** pane \(below **NET**\) represents the JS heap.</span></span>  <span data-ttu-id="9e5a5-170">"概述 **"窗格** 下方是" **计数器"** 窗格。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-170">Below the **Overview** pane is the **Counter** pane.</span></span>  <span data-ttu-id="9e5a5-171">内存使用率由 JS 堆 \ (与概述窗格\) 、文档、DOM\*\*\*\* 节点、侦听器和 GPU 内存中的**HEAP**图形相同。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-171">The memory usage is broken down by JS heap \(same as **HEAP** graph in the **Overview** pane\), documents, DOM nodes, listeners, and GPU memory.</span></span>  <span data-ttu-id="9e5a5-172">关闭复选框以在图形中隐藏它。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-172">Turn off a checkbox to hide it from the graph.</span></span>  

<span data-ttu-id="9e5a5-173">现在，代码分析与上图比较。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-173">Now, an analysis of the code compared with the previous figure.</span></span>  <span data-ttu-id="9e5a5-174">如果查看节点计数器 \ (绿色图形\) ，它将与代码完全匹配。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-174">If you review the node counter \(the green graph\), it matches up cleanly with the code.</span></span>  <span data-ttu-id="9e5a5-175">节点计数在离散步骤中增加。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-175">The node count increases in discrete steps.</span></span>  <span data-ttu-id="9e5a5-176">您可能认为每次增加的节点数都是对 的调用 `grow()` 。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-176">You may presume that each increase in the node count is a call to `grow()`.</span></span>  <span data-ttu-id="9e5a5-177">JS 堆图 \ (蓝图\) 不是那么简单。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-177">The JS heap graph \(the blue graph\) is not as straightforward.</span></span>  <span data-ttu-id="9e5a5-178">为了与最佳做法保持一样，第一个下降实际上是强制垃圾回收 \ (选择  **收集垃圾回收** ![ 强制垃圾回收按钮 ][ImageForceGarbageCollectionIcon] \) 。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-178">In keeping with best practices, the first dip is actually a forced garbage collection \(choose the  **collect garbage** ![force garbage collection][ImageForceGarbageCollectionIcon] button\).</span></span>  <span data-ttu-id="9e5a5-179">在记录进行时，将显示 JS 堆大小峰值。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-179">As the recording progresses, the JS heap size spikes are displayed.</span></span>  <span data-ttu-id="9e5a5-180">这是自然且预期的：JavaScript 代码将在你选择的每一个按钮上创建 DOM 节点，并创建一百万个字符的字符串时执行大量工作。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-180">This is natural and expected:  the JavaScript code is creating the DOM nodes on every button you choose and doing a lot of work when it creates the string of one million characters.</span></span>  <span data-ttu-id="9e5a5-181">此处的关键点是 JS 堆结束时间高于其开头 \ ("开头"是强制垃圾回收\) 。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-181">The key thing here is the fact that the JS heap ends higher than it began \(the "beginning" here being the point after the forced garbage collection\).</span></span>  <span data-ttu-id="9e5a5-182">在现实世界中，如果你看到这种增加 JS 堆大小或节点大小的模式，它可能会定义内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-182">In the real world, if you saw this pattern of increasing JS heap size or node size, it may potentially define a memory leak.</span></span>  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <a name="discover-detached-dom-tree-memory-leaks-with-heap-snapshots"></a><span data-ttu-id="9e5a5-183">使用堆快照发现分离的 DOM 树内存泄漏</span><span class="sxs-lookup"><span data-stu-id="9e5a5-183">Discover detached DOM tree memory leaks with Heap Snapshots</span></span>  

<span data-ttu-id="9e5a5-184">DOM 节点仅在没有从页面上运行的 DOM 树或 JavaScript 代码引用该节点时进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-184">A DOM node is only garbage collected when there are no references to the node from either the DOM tree or JavaScript code running on the page.</span></span>  <span data-ttu-id="9e5a5-185">当从 DOM 树中删除节点时，该节点将被"分离"，但某些 JavaScript 仍引用它。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-185">A node is said to be "detached" when it is removed from the DOM tree but some JavaScript still references it.</span></span>  <span data-ttu-id="9e5a5-186">分离的 DOM 节点是内存泄漏的常见原因。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-186">Detached DOM nodes are a common cause of memory leaks.</span></span>  <span data-ttu-id="9e5a5-187">本部分指导你如何使用 DevTools 中的堆探查器来确定分离的节点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-187">This section teaches you how to use the heap profilers in DevTools to identify detached nodes.</span></span>  

<span data-ttu-id="9e5a5-188">下面是分离 DOM 节点的简单示例。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-188">Here is a simple example of detached DOM nodes.</span></span>  

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

<span data-ttu-id="9e5a5-189">选择代码中引用的按钮将创建一 `ul` 个包含 10 个子节点 `li` 的节点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-189">Choosing the button referenced in the code creates a `ul` node with ten `li` children.</span></span>  <span data-ttu-id="9e5a5-190">节点由代码引用，但在 DOM 树中不存在，因此会分离每个节点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-190">The nodes are referenced by the code but do not exist in the DOM tree, so each is detached.</span></span>  

<span data-ttu-id="9e5a5-191">堆快照是标识分离节点的一种方法。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-191">Heap snapshots are one way to identify detached nodes.</span></span>  <span data-ttu-id="9e5a5-192">正如该名称所示，堆快照显示了在快照时间点如何在页面的 JS 对象和 DOM 节点之间分配内存。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-192">As the name implies, heap snapshots show you how memory is distributed among the JS objects and DOM nodes for your page at the point of time of the snapshot.</span></span>  

<span data-ttu-id="9e5a5-193">若要创建快照，请打开 DevTools 并导航\*\*\*\* 到内存面板，选择\*\*\*\* 堆快照单选按钮>**拍摄快照**按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-193">To create a snapshot, open DevTools and navigate to the **Memory** panel, choose the **Heap snapshot** radio button > **Take snapshot** button.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="拍摄堆快照" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   <span data-ttu-id="9e5a5-195">图 4：拍摄堆快照</span><span class="sxs-lookup"><span data-stu-id="9e5a5-195">Figure 4:  Take heap snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="9e5a5-196">可能需要一些时间处理和加载快照。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-196">The snapshot may take some time to process and load.</span></span>  <span data-ttu-id="9e5a5-197">完成后，从名为 **HEAP SNAPSHOTS**\ (的左侧面板 \) 。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-197">After it is finished, select it from the left-hand panel \(named **HEAP SNAPSHOTS**\).</span></span>  

<span data-ttu-id="9e5a5-198">在 `Detached` 类 **筛选器文本框中** 键入以搜索分离的 DOM 树。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-198">Type `Detached` in the **Class filter** textbox to search for detached DOM trees.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="筛选分离的节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   <span data-ttu-id="9e5a5-200">图 5：筛选分离的节点</span><span class="sxs-lookup"><span data-stu-id="9e5a5-200">Figure 5:  Filtering for detached nodes</span></span>  
:::image-end:::  

<span data-ttu-id="9e5a5-201">展开树状以调查分离的树。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-201">Expand the carats to investigate a detached tree.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="调查分离的树" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   <span data-ttu-id="9e5a5-203">图 6：调查分离的树</span><span class="sxs-lookup"><span data-stu-id="9e5a5-203">Figure 6:  Investigating detached tree</span></span>  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

<span data-ttu-id="9e5a5-204">选择一个节点以进一步调查它。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-204">Choose a node to investigate it further.</span></span>  <span data-ttu-id="9e5a5-205">在 **"对象** "窗格中，您可以查看有关引用它的代码的详细信息。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-205">In the **Objects** pane, you may review more information about the code that is referencing it.</span></span>  <span data-ttu-id="9e5a5-206">例如，在下图中， `detachedNodes` 变量引用节点。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-206">For example, in the following figure, the `detachedNodes` variable is referencing the node.</span></span>  <span data-ttu-id="9e5a5-207">若要修复特定内存泄漏，应研究使用 变量的代码，并确保在不再需要节点时删除 `detachedUNode` 对节点的引用。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-207">To fix the particular memory leak, you should study the code that uses the `detachedUNode` variable and ensure that the reference to the node is removed when it is no longer needed.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="调查节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   <span data-ttu-id="9e5a5-209">图 7：调查节点</span><span class="sxs-lookup"><span data-stu-id="9e5a5-209">Figure 7:  Investigating a node</span></span>  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <a name="identify-js-heap-memory-leaks-with-allocation-instrumentation-on-timeline"></a><span data-ttu-id="9e5a5-210">在时间线上通过 Allocation instrumentation 识别 JS 堆内存泄漏</span><span class="sxs-lookup"><span data-stu-id="9e5a5-210">Identify JS heap memory leaks with Allocation instrumentation on timeline</span></span>  

<span data-ttu-id="9e5a5-211">**时间线上的分配检测** 是另一个可以帮助你跟踪 JS 堆中的内存泄漏的工具。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-211">**Allocation instrumentation on timeline** is another tool that may help you track down memory leaks in your JS heap.</span></span>  

<span data-ttu-id="9e5a5-212">使用 **下面的代码演示时间线**  上的分配检测。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-212">Demonstrate **Allocation instrumentation on timeline**  using the following code.</span></span>  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

<span data-ttu-id="9e5a5-213">每次推送代码中引用的按钮时，都会向数组中添加一个包含一百万个字符 `x` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-213">Every time that the button referenced in the code is pushed, a string of one million characters is added to the `x` array.</span></span>  

<span data-ttu-id="9e5a5-214">若要在时间线上记录分配检测，请打开 DevTools，导航\*\*\*\* 到内存面板，选择时间线上的分配检测单选按钮，选择\*\*\*\*"开始"按钮，执行你怀疑导致内存泄漏的操作，然后在完成后选择停止**录制**堆配置文件停止录制\*\*\*\* ![ ][ImageStopRecordingIcon] 按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-214">To record an Allocation instrumentation on timeline, open DevTools, navigate to the **Memory** panel, choose the **Allocation instrumentation on timeline** radio button, choose the **Start** button, perform the action that you suspect is causing the memory leak, and then choose the **Stop recording heap profile** ![stop recording][ImageStopRecordingIcon] button when you are done.</span></span>  

<span data-ttu-id="9e5a5-215">在录制时，请注意时间线上的 Allocation instrumentation 上是否显示任何蓝色条，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-215">As you are recording, notice if any blue bars show up on the Allocation instrumentation on timeline, like in the following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新分配" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   <span data-ttu-id="9e5a5-217">图 8：新分配</span><span class="sxs-lookup"><span data-stu-id="9e5a5-217">Figure 8:  New allocations</span></span>  
:::image-end:::  

<span data-ttu-id="9e5a5-218">这些蓝色条代表新的内存分配。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-218">Those blue bars represent new memory allocations.</span></span>  <span data-ttu-id="9e5a5-219">这些新的内存分配是内存泄漏的候选项。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-219">Those new memory allocations are your candidates for memory leaks.</span></span>  <span data-ttu-id="9e5a5-220">可以缩放栏以筛选"构造函数"窗格，以\*\*\*\* 只显示指定时间范围内分配的对象。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-220">You are able to zoom on a bar to filter the **Constructor** pane to only show objects that were allocated during the specified timeframe.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="已缩放的分配时间线" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   <span data-ttu-id="9e5a5-222">图 9：已缩放的分配时间线</span><span class="sxs-lookup"><span data-stu-id="9e5a5-222">Figure 9:  Zoomed allocation timeline</span></span>  
:::image-end:::  

<span data-ttu-id="9e5a5-223">展开对象并选择值以查看"对象"窗格中的 **更多详细信息** 。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-223">Expand the object and select the value to view more details in the **Object** pane.</span></span>  <span data-ttu-id="9e5a5-224">例如，下图中新分配的对象的详细信息指示已分配给范围 `x` 中的 `Window` 变量。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-224">For example, in the following figure, in the details of the newly allocated object indicates that it was allocated to the `x` variable in the `Window` scope.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="对象详细信息" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   <span data-ttu-id="9e5a5-226">图 10：对象详细信息</span><span class="sxs-lookup"><span data-stu-id="9e5a5-226">Figure 10:  Object details</span></span>  
:::image-end:::  

## <a name="investigate-memory-allocation-by-function"></a><span data-ttu-id="9e5a5-227">按功能调查内存分配</span><span class="sxs-lookup"><span data-stu-id="9e5a5-227">Investigate memory allocation by function</span></span>  

<span data-ttu-id="9e5a5-228">使用 **分配采样** 分析类型查看 JavaScript 函数的内存分配。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-228">Use the **Allocation sampling** profiling type to view memory allocation by JavaScript function.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="记录分配采样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   <span data-ttu-id="9e5a5-230">图 11：记录分配采样</span><span class="sxs-lookup"><span data-stu-id="9e5a5-230">Figure 11:  Record Allocation sampling</span></span>  
:::image-end:::  

1.  <span data-ttu-id="9e5a5-231">选择“**分配采样**”按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-231">Choose the **Allocation sampling** radio button.</span></span>  <span data-ttu-id="9e5a5-232">如果页面上有工作线程，可以使用"开始"按钮旁边的下拉菜单选择该工作 **线程作为分析** 目标。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-232">If there is a worker on the page, you are able to select that as the profiling target using the dropdown menu next to the **Start** button.</span></span>  
1.  <span data-ttu-id="9e5a5-233">选择" **开始"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-233">Choose the **Start** button.</span></span>  
1.  <span data-ttu-id="9e5a5-234">完成要调查的网页上的操作。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-234">Complete the actions on the webpage which you want to investigate.</span></span>  
1.  <span data-ttu-id="9e5a5-235">完成 **所有操作** 后，选择"停止"按钮。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-235">Choose the **Stop** button when you have finished all of your actions.</span></span>  

<span data-ttu-id="9e5a5-236">DevTools 显示按功能分配内存的细目。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-236">DevTools shows you a breakdown of memory allocation by function.</span></span>  <span data-ttu-id="9e5a5-237">默认视图为 \*\*"高 (从 \*\*下) "，它显示在顶部分配了大部分内存的函数。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-237">The default view is **Heavy (Bottom Up)**, which displays the functions that allocated the most memory at the top.</span></span>  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="分配采样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   <span data-ttu-id="9e5a5-239">图 12：分配采样</span><span class="sxs-lookup"><span data-stu-id="9e5a5-239">Figure 12:  Allocation sampling</span></span>  
:::image-end:::  

## <a name="spot-frequent-garbage-collections"></a><span data-ttu-id="9e5a5-240">专色频繁垃圾回收</span><span class="sxs-lookup"><span data-stu-id="9e5a5-240">Spot frequent garbage collections</span></span>  

<span data-ttu-id="9e5a5-241">如果页面似乎频繁暂停，则可能有垃圾回收问题。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-241">If your page appears to pause frequently, then you may have garbage collection issues.</span></span>  

<span data-ttu-id="9e5a5-242">可以使用 Microsoft Edge 浏览器任务管理器或性能内存记录来发现频繁垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-242">You are able to use either the Microsoft Edge Browser Task Manager or Performance memory recordings to spot frequent garbage collection.</span></span>  <span data-ttu-id="9e5a5-243">在 Microsoft Edge 浏览器任务管理器中，经常出现和下降 **的内存** 或 **JavaScript 内存** 值表示频繁垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-243">In the Microsoft Edge Browser Task Manager, frequently rising and falling **Memory** or **JavaScript Memory** values represent frequent garbage collection.</span></span>  <span data-ttu-id="9e5a5-244">在性能记录中，频繁更改 \ (和下降\) JS 堆或节点计数图指示频繁进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-244">In Performance recordings, frequent changes \(rising and falling\) to the JS heap or node count graphs indicate frequent garbage collection.</span></span>  

<span data-ttu-id="9e5a5-245">确定问题后，可以在时间线记录上使用 **Allocation instrumentation** 来查明内存的分配位置以及导致分配的函数。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-245">After you have identified the problem, you are able to use an **Allocation instrumentation on timeline** recording to find out where memory is being allocated and which functions are causing the allocations.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="9e5a5-246">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="9e5a5-246">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "记录性能 - 性能分析参考"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> <span data-ttu-id="9e5a5-248">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-248">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="9e5a5-249">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-249">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index) and is authored by [Kayce Basques][KayceBasques] \(Technical Writer, Chrome DevTools \& Lighthouse\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="9e5a5-251">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="9e5a5-251">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
