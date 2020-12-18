---
description: 使用"内存"面板
title: DevTools - 内存
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 内存， 堆， GC， 垃圾回收， 保留大小， 管理程序
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 5ad284f8072cc296743299ec9c4fb2037f8fd883
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232124"
---
# <span data-ttu-id="8a676-104">内存</span><span class="sxs-lookup"><span data-stu-id="8a676-104">Memory</span></span>

<span data-ttu-id="8a676-105">使用 **内存** 面板测量系统资源的使用，并比较代码执行的不同状态中的堆快照。</span><span class="sxs-lookup"><span data-stu-id="8a676-105">Use the **Memory** panel to measure your use of system resources and compare heap snapshots at different states of code execution.</span></span> <span data-ttu-id="8a676-106">通过它，你可以：</span><span class="sxs-lookup"><span data-stu-id="8a676-106">With it, you can:</span></span>

- <span data-ttu-id="8a676-107">[实时绘制页面的内存消耗并](#memory-usage-timeline) 获取堆的快照</span><span class="sxs-lookup"><span data-stu-id="8a676-107">[Graph the memory consumption of your page in real time](#memory-usage-timeline) and take snapshots of the heap</span></span>
- <span data-ttu-id="8a676-108">[确定代码中的潜在](#snapshot-summary) 内存问题，例如未附加到 DOM 的保留对象</span><span class="sxs-lookup"><span data-stu-id="8a676-108">[Identify potential memory issues](#snapshot-summary) in your code, such as retained objects not attached to the DOM</span></span>
- <span data-ttu-id="8a676-109">[按实例、](#snapshot-details) 实例对象类型大小和引用查看内存使用率数据，以帮助隔离问题</span><span class="sxs-lookup"><span data-stu-id="8a676-109">[Review memory usage data](#snapshot-details) by object type, instance count, size, and references to help isolate issues</span></span>
- <span data-ttu-id="8a676-110">[应用快照数据筛选器](#filters) 以减少不可操作信息的干扰</span><span class="sxs-lookup"><span data-stu-id="8a676-110">[Apply snapshot data filters](#filters) to reduce the noise of non-actionable information</span></span>
- <span data-ttu-id="8a676-111">[确定特定对象的内存](#object-references) 成本和使该对象保持活动状态的引用</span><span class="sxs-lookup"><span data-stu-id="8a676-111">[Identify the memory cost of a specific object](#object-references) and the references keeping it alive</span></span>
- <span data-ttu-id="8a676-112">[在调查的不同阶段](#snapshot-comparison) 对堆进行差异，以跟踪内存泄漏和其他问题的来源</span><span class="sxs-lookup"><span data-stu-id="8a676-112">[Diff the heap at different phases of your investigation](#snapshot-comparison) to track down the source of memory leaks and other problems</span></span>

![Microsoft Edge DevTools 内存面板](./media/memory.png)


## <span data-ttu-id="8a676-114">工具栏</span><span class="sxs-lookup"><span data-stu-id="8a676-114">Toolbar</span></span>

1. <span data-ttu-id="8a676-115">\*\*启动/停止分析会话 (Ctrl+E) ： \*\*打开探查器后，你可以跟踪内存使用情况并获取堆的快照。</span><span class="sxs-lookup"><span data-stu-id="8a676-115">**Start/Stop profiling session (Ctrl+E)**: Turning on the profiler enables you to track memory usage and take snapshots of the heap.</span></span>
2. <span data-ttu-id="8a676-116">\*\*将分析会话 (Ctrl+O) ： \*\*加载保存的 DevTools 内存诊断会话。</span><span class="sxs-lookup"><span data-stu-id="8a676-116">**Import profiling session (Ctrl+O)**: Load a saved  DevTools memory diagnostic session.</span></span>
3. <span data-ttu-id="8a676-117">\*\*将分析会话 (Ctrl+S) ： \*\*将当前诊断会话保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="8a676-117">**Export profiling session (Ctrl+S)**: Save the current diagnostic session to disk.</span></span>
4. <span data-ttu-id="8a676-118">\*\*使用 Ctrl (Shift+T) \*\*获取堆快照：记录给定时间点的当前内存分配。</span><span class="sxs-lookup"><span data-stu-id="8a676-118">**Take heap snapshot (Ctrl+Shift+T)**: Record current memory allocations for a given point of time.</span></span>


## <span data-ttu-id="8a676-119">内存使用时间线</span><span class="sxs-lookup"><span data-stu-id="8a676-119">Memory usage timeline</span></span>

<span data-ttu-id="8a676-120">内存问题可能是性能问题的主要原因，从而导致页面逐渐变得无响应和滞后。</span><span class="sxs-lookup"><span data-stu-id="8a676-120">Memory problems can be a major culprit of performance issues, causing your page to become increasingly unresponsive and laggy over time.</span></span>

<span data-ttu-id="8a676-121">分析页面的内存使用情况的第一步是启动分析会话，以在对导致[](#toolbar)内存不足或可疑内存泄漏的步骤进行重新说明时，获取堆的快照之前/之后。</span><span class="sxs-lookup"><span data-stu-id="8a676-121">The first step to analyzing the memory usage of your page is to [start a profiling session](#toolbar) in order to take before/after snapshots of the heap as you repro the steps causing memory bloat or a suspected memory leak.</span></span>

<span data-ttu-id="8a676-122">启动内存探查器时，你将看到一个进程内存图，它允许你观察整个专用工作集 (页面占用的内存量) 一段时间。</span><span class="sxs-lookup"><span data-stu-id="8a676-122">When you start the memory profiler, you will see a process memory graph that allows you to observe the overall private working set (the amount of memory consumed by the page) over time.</span></span> <span data-ttu-id="8a676-123">内存图显示选项卡的进程内存（包括专用字节、本机内存和 JavaScript 堆）实时视图。</span><span class="sxs-lookup"><span data-stu-id="8a676-123">The memory graph shows you a live view of the tab's process memory, which includes private bytes, native memory, and the JavaScript heap.</span></span> 

![内存使用时间线](./media/memory_timeline.png)

 <span data-ttu-id="8a676-125">此图指示页面的内存趋势，该趋势使你能够判断何时适合拍摄堆 [快照供以后](#toolbar) 比较，例如当你看到意外的内存保留期时。</span><span class="sxs-lookup"><span data-stu-id="8a676-125">The graph gives you an indication of the memory trend for the page which enables you to judge when it is appropriate to [take a heap snapshot](#toolbar) for later comparison, such as when you see periods of unexpected memory retention.</span></span>

### <span data-ttu-id="8a676-126">Performance.mark () </span><span class="sxs-lookup"><span data-stu-id="8a676-126">Performance.mark()</span></span>

<span data-ttu-id="8a676-127">你可以向时间线 **添加自定义用户** 标记，以帮助识别分析会话过程中的关键事件，方法是从代码或 [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) DevTools 控制台内调用 [**该方法**](./console.md)。</span><span class="sxs-lookup"><span data-stu-id="8a676-127">You can add custom **User marks** to the timeline to help identify  key events during the course of your analysis session by calling the [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span>

### <span data-ttu-id="8a676-128">Console.takeheapSnapshot () </span><span class="sxs-lookup"><span data-stu-id="8a676-128">Console.takeheapSnapshot()</span></span>

<span data-ttu-id="8a676-129">有时，你需要在非常具体的点获取快照，例如紧接 DOM 发生大规模更改之前。</span><span class="sxs-lookup"><span data-stu-id="8a676-129">Sometimes you need to take snapshots at very specific points in time, such as immediately before a large mutation of the DOM.</span></span> <span data-ttu-id="8a676-130">在这些情况下，可以通过编程方式获取快照 [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots) 。</span><span class="sxs-lookup"><span data-stu-id="8a676-130">In these cases,you can take snapshots programmatically with [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots).</span></span>

## <span data-ttu-id="8a676-131">快照摘要</span><span class="sxs-lookup"><span data-stu-id="8a676-131">Snapshot summary</span></span>

<span data-ttu-id="8a676-132">[拍摄快照](#toolbar) 将生成一个摘要磁贴，该磁贴指示拍摄快照时 JavaScript 堆的大小，以及分配的对象数和页面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="8a676-132">[Taking a snapshot](#toolbar) will generate a summary tile that indicates the size of the JavaScript heap at the time the snapshot was taken, along with the number of objects allocated and a screenshot of the page.</span></span> <span data-ttu-id="8a676-133">在需要分析的用户方案中运行时，你随时都可以继续获取快照。</span><span class="sxs-lookup"><span data-stu-id="8a676-133">You can continue to take snapshots at any time as you run through the user scenario requiring analysis.</span></span> <span data-ttu-id="8a676-134">快照生成其他磁贴，其中每个磁贴都指示 JavaScript 内存与上一个快照的区别。</span><span class="sxs-lookup"><span data-stu-id="8a676-134">The snapshots generate additional tiles, each of which indicates the difference in JavaScript memory from the previous snapshot.</span></span>

![堆快照](./media/memory_snapshot.png)

<span data-ttu-id="8a676-136">单击摘要磁贴中的值将切换到显示快照数据详细信息 [的窗格](#snapshot-details)。</span><span class="sxs-lookup"><span data-stu-id="8a676-136">Clicking on the values in the summary tile will switch to the pane showing [details of the snapshot data](#snapshot-details).</span></span> <span data-ttu-id="8a676-137">潜在的 [内存问题用](#snapshot-details) 蓝色信息图标 ("i") 图标。</span><span class="sxs-lookup"><span data-stu-id="8a676-137">Potential [memory issues are indicated](#snapshot-details) with a blue informational ("i") icon.</span></span>

## <span data-ttu-id="8a676-138">快照详细信息</span><span class="sxs-lookup"><span data-stu-id="8a676-138">Snapshot details</span></span>

<span data-ttu-id="8a676-139">"快照" *窗格中* 的数据显示页面创建的对象以及你可能使用 JavaScript 框架分配的任何内存。</span><span class="sxs-lookup"><span data-stu-id="8a676-139">The data in the *Snapshot* pane shows the objects created by your page along with any memory allocated by JavaScript frameworks you may be consuming.</span></span>

![快照详细信息表](./media/memory_details.png)

<span data-ttu-id="8a676-141">这三个选项卡表示数据的不同视图：</span><span class="sxs-lookup"><span data-stu-id="8a676-141">The three tabs represent different views of the data:</span></span>

#### <span data-ttu-id="8a676-142">类型</span><span class="sxs-lookup"><span data-stu-id="8a676-142">Types</span></span>

<span data-ttu-id="8a676-143">显示堆栈上对象的实例计数和总大小，对象类型。</span><span class="sxs-lookup"><span data-stu-id="8a676-143">Shows the instance count and total size of objects on the heap, grouped by object type.</span></span> <span data-ttu-id="8a676-144">默认情况下，这些实例按实例计数排序。</span><span class="sxs-lookup"><span data-stu-id="8a676-144">By default, these are sorted by instance count.</span></span>

<span data-ttu-id="8a676-145">选择上半部分"类型"窗格中\*\* 的对象时，下[](#object-references)窗格中的"对象引用"表将列出指向该对象的所有对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-145">When you select an object in the upper *Types* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

#### <span data-ttu-id="8a676-146">根</span><span class="sxs-lookup"><span data-stu-id="8a676-146">Roots</span></span>

<span data-ttu-id="8a676-147">显示子引用的分层视图，以描述对象如何作为全局对象的根，从而防止它们被垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="8a676-147">Shows a hierarchical view of child references to describe how objects are rooted to the global object, thus preventing them from being garbage-collected.</span></span>

<span data-ttu-id="8a676-148">默认情况下，子节点按保留大小列进行排序，最顶端为最大。</span><span class="sxs-lookup"><span data-stu-id="8a676-148">By default, the child nodes are sorted by the retained size column, with the largest at the top.</span></span>

#### <span data-ttu-id="8a676-149">Dominators</span><span class="sxs-lookup"><span data-stu-id="8a676-149">Dominators</span></span>

<span data-ttu-id="8a676-150">显示堆栈上具有对其他对象的独占引用的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="8a676-150">Shows a list of objects on the heap that have exclusive references to other objects.</span></span> <span data-ttu-id="8a676-151">管理程序按保留大小进行排序，以指示使用最可能最轻松释放的内存的对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-151">Dominators are sorted by retained size to indicate the objects consuming the most memory that are potentially easiest to free.</span></span>

<span data-ttu-id="8a676-152">下面是如何解释"类型"、"根"\*\* 和"管理程序"*视图中的列*：</span><span class="sxs-lookup"><span data-stu-id="8a676-152">Here's how to interpret the columns in the *Types, Roots* and *Dominators* views:</span></span>

<span data-ttu-id="8a676-153">列</span><span class="sxs-lookup"><span data-stu-id="8a676-153">Column</span></span> | <span data-ttu-id="8a676-154">描述</span><span class="sxs-lookup"><span data-stu-id="8a676-154">Description</span></span>
:------------ | :-------------
<span data-ttu-id="8a676-155">标识符 () </span><span class="sxs-lookup"><span data-stu-id="8a676-155">Identifier(s)</span></span> | <span data-ttu-id="8a676-156">最能够标识对象的名称。</span><span class="sxs-lookup"><span data-stu-id="8a676-156">Name that best identifies the object.</span></span> <span data-ttu-id="8a676-157">例如，对于 HTML 元素，快照详细信息会显示 ID 属性值（如果使用）。</span><span class="sxs-lookup"><span data-stu-id="8a676-157">For example, for HTML elements the snapshot details show the ID attribute value, if one is used.</span></span>
<span data-ttu-id="8a676-158">类型</span><span class="sxs-lookup"><span data-stu-id="8a676-158">Type</span></span> | <span data-ttu-id="8a676-159">对象类型 (例如 *，HTMLDivElement*) 。</span><span class="sxs-lookup"><span data-stu-id="8a676-159">Object type (for example, *HTMLDivElement*).</span></span>
<span data-ttu-id="8a676-160">大小</span><span class="sxs-lookup"><span data-stu-id="8a676-160">Size</span></span> | <span data-ttu-id="8a676-161">对象大小，不包括任何引用对象的大小。</span><span class="sxs-lookup"><span data-stu-id="8a676-161">Object size, not including the size of any referenced objects.</span></span>
<span data-ttu-id="8a676-162">保留大小</span><span class="sxs-lookup"><span data-stu-id="8a676-162">Retained size</span></span> | <span data-ttu-id="8a676-163">对象大小加上没有其他父对象的所有子对象的大小。</span><span class="sxs-lookup"><span data-stu-id="8a676-163">Object size plus the size of all child objects that have no other parents.</span></span> <span data-ttu-id="8a676-164">出于实用目的，这是对象保留的内存量，因此，如果删除对象，将回收指定内存量。</span><span class="sxs-lookup"><span data-stu-id="8a676-164">For practical purposes, this is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>
<span data-ttu-id="8a676-165">Count</span><span class="sxs-lookup"><span data-stu-id="8a676-165">Count</span></span> | <span data-ttu-id="8a676-166">对象实例的数量。</span><span class="sxs-lookup"><span data-stu-id="8a676-166">Number of object instances.</span></span> <span data-ttu-id="8a676-167">此值仅在"类型"视图中显示。</span><span class="sxs-lookup"><span data-stu-id="8a676-167">This value appears only in the Types view.</span></span>

<span data-ttu-id="8a676-168">选择上窗格中的对象时，下窗格中\*\* 的"对象引用"表将[](#object-references)列出指向该对象的所有对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-168">When you select an object in the upper *Dominators* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

### <span data-ttu-id="8a676-169">筛选器</span><span class="sxs-lookup"><span data-stu-id="8a676-169">Filters</span></span>

<span data-ttu-id="8a676-170">可以使用以下内容进一步调整表中的数据：</span><span class="sxs-lookup"><span data-stu-id="8a676-170">You can further adjust data in the table with the following:</span></span>

![内置和对象 ID 的筛选器](./media/memory_filter.png)

1. <span data-ttu-id="8a676-172">**标识符筛选器**：通过搜索特定对象标识符筛选出数据</span><span class="sxs-lookup"><span data-stu-id="8a676-172">**Identifier filter**: Filter out data by searching for a particular object identifier</span></span>
2. <span data-ttu-id="8a676-173">**按管理**程序分组：只有具有对其他对象的\*\* 独占引用的对象显示在对象的顶级视图中 (这是 *"Dominators"* 选项卡视图中的默认) 。</span><span class="sxs-lookup"><span data-stu-id="8a676-173">**Group by dominator**: Only objects with *exclusive* references to other objects are shown in the top-level view of objects (this is the default view in the *Dominators* tab).</span></span>
3. <span data-ttu-id="8a676-174">**内置 /ID 筛选器**：默认情况下 [，JavaScript](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) 内置对象包含在列表中。</span><span class="sxs-lookup"><span data-stu-id="8a676-174">**Built-ins / IDs filter**: By default, [JavaScript built-in objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) are included in the list.</span></span> <span data-ttu-id="8a676-175">如果有多个需要区分的匿名对象，则列出对象 ID 会很有用。</span><span class="sxs-lookup"><span data-stu-id="8a676-175">Listing object IDs can be useful if there are multiple anonymous objects which need to be differentiated.</span></span>

<span data-ttu-id="8a676-176">" *类型"* 视图、"根视图"和"管理 *程序* "视图各有其自己的筛选器，因此切换到其他视图时不会保留该筛选器。</span><span class="sxs-lookup"><span data-stu-id="8a676-176">The *Types, Roots* and *Dominators* views each has its own filter, so the filter isn't preserved when you switch to another view.</span></span>

### <span data-ttu-id="8a676-177">对象引用</span><span class="sxs-lookup"><span data-stu-id="8a676-177">Object references</span></span>

<span data-ttu-id="8a676-178">在[**"类型**](#types)"[**和"管理程序**](#dominators)"视图中，下窗格包含一\*\*\*\* 个显示共享引用的对象引用列表。</span><span class="sxs-lookup"><span data-stu-id="8a676-178">In the [**Types**](#types) and [**Dominators**](#dominators) views, the lower pane contains an **Object references** list that displays shared references.</span></span> <span data-ttu-id="8a676-179">在上窗格中选择一个对象时，此列表将显示指向该对象的所有对象，即使选定对象保持活动状态的对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-179">When you choose an object in the upper pane, this list displays all objects that point to that object--in other words, the objects that are keeping the selected object alive.</span></span>

<span data-ttu-id="8a676-180">循环引用使用星号 (\*) 和信息性工具提示显示，并且不能展开。</span><span class="sxs-lookup"><span data-stu-id="8a676-180">Circular references are shown with an asterisk (\*) and informational tooltip, and cannot be expanded.</span></span> <span data-ttu-id="8a676-181">否则，它们会阻止您向上移动引用树并标识保留内存的对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-181">Otherwise, they would prevent you from walking up the reference tree and identifying objects that are retaining memory.</span></span>

<span data-ttu-id="8a676-182">若要快速标识等效对象，请选中 [*"显示对象标识*](#filters) "筛选器选项，以显示"标识符"列 (对象名称 \*) 对象标识 \* 。</span><span class="sxs-lookup"><span data-stu-id="8a676-182">To quickly identify equivalent objects, tick the [*Display object IDs*](#filters) filter option to display object IDs next to object names in the *Identifier(s)* column.</span></span> <span data-ttu-id="8a676-183">具有相同的 ID 的对象是共享引用。</span><span class="sxs-lookup"><span data-stu-id="8a676-183">Objects that have the same ID are shared references.</span></span>

### <span data-ttu-id="8a676-184">快照比较</span><span class="sxs-lookup"><span data-stu-id="8a676-184">Snapshot comparison</span></span>

<span data-ttu-id="8a676-185">单击快照 [摘要磁贴上的快照比较](#snapshot-details) 选项卡或比较 [链接](#snapshot-summary)  将显示两个快照之间的信息差异。</span><span class="sxs-lookup"><span data-stu-id="8a676-185">Clicking on a [snapshot comparison tab](#snapshot-details) or comparison link on the [snapshot summary tile](#snapshot-summary)  will show a diff of information between the two snapshots.</span></span> <span data-ttu-id="8a676-186">在比较窗格中，"Dominators"视图、"\*\* 类型"视图和"[\*\*](#snapshot-details)根"视图提供与单个快照相同的快照详细信息，并包含以下附加值： \*\*</span><span class="sxs-lookup"><span data-stu-id="8a676-186">In the comparison pane, the *Dominators, Types* and *Roots* views provide the same [*snapshot details*](#snapshot-details) you would see for a single snapshots, with these additional values:</span></span>

<span data-ttu-id="8a676-187">列</span><span class="sxs-lookup"><span data-stu-id="8a676-187">Column</span></span> | <span data-ttu-id="8a676-188">描述</span><span class="sxs-lookup"><span data-stu-id="8a676-188">Description</span></span>
:------------ | :-------------
<span data-ttu-id="8a676-189">大小差。</span><span class="sxs-lookup"><span data-stu-id="8a676-189">Size diff.</span></span> | <span data-ttu-id="8a676-190">当前快照中对象的大小与上一快照中对象的大小之间的差，不包括任何引用对象的大小。</span><span class="sxs-lookup"><span data-stu-id="8a676-190">Difference between the size of the object in the current snapshot and its size in the previous snapshot, not including the size of any referenced objects.</span></span>
<span data-ttu-id="8a676-191">保留大小差异。</span><span class="sxs-lookup"><span data-stu-id="8a676-191">Retained size diff.</span></span> | <span data-ttu-id="8a676-192">当前快照中对象的保留大小与上一快照中对象的保留大小之间的差。</span><span class="sxs-lookup"><span data-stu-id="8a676-192">Difference between the retained size of the object in the current snapshot and its retained size in the previous snapshot.</span></span> <span data-ttu-id="8a676-193">保留的大小包括对象大小以及其所有没有其他父项的子对象的大小。</span><span class="sxs-lookup"><span data-stu-id="8a676-193">The retained size includes the object size plus the size of all its child objects that have no other parents.</span></span> <span data-ttu-id="8a676-194">出于实用目的，保留的大小是对象保留的内存量，因此，如果删除对象，将回收指定内存量。</span><span class="sxs-lookup"><span data-stu-id="8a676-194">For practical purposes, the retained size is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>

<span data-ttu-id="8a676-195">可以使用 **"范围"** 下拉列表筛选快照之间的差异信息：</span><span class="sxs-lookup"><span data-stu-id="8a676-195">You can use the **Scope** dropdown to filter differential info between snapshots:</span></span>

![快照比较的作用域筛选器](./media/memory_comparison_scope_filter.png)

- <strong><span data-ttu-id="8a676-197">从 Snapshot # 中保留的对象：显示添加到堆和从堆栈中删除的对象（从基线快照到上一个快照） <number></strong> 之间的差。</span><span class="sxs-lookup"><span data-stu-id="8a676-197">Objects left over from Snapshot #<number></strong>: Shows the diff between the objects added to the heap and removed from the heap from the baseline snapshot to the previous snapshot.</span></span> <span data-ttu-id="8a676-198">例如，如果快照摘要在对象计数中显示 <em> +205 / -195，则此筛选器将显示已添加但不删除的十 </em> 个对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-198">For example, if the snapshot summary shows <em>+205 / -195</em> in the object count, this filter will show you the ten objects that were added but not removed.</span></span>

- <strong><span data-ttu-id="8a676-199">在 Snapshot # 和 # 之间添加的对象：显示从上一个快照 <number> <number></strong> 添加到堆的所有对象。</span><span class="sxs-lookup"><span data-stu-id="8a676-199">Objects added between Snapshot #<number> and #<number></strong>: Shows all objects added to the heap from the previous snapshot.</span></span>

- <strong><span data-ttu-id="8a676-200">Snapshot # 中的所有对象：显示堆上 (对象，也就是说，未筛选的 <number></strong> <em> </em> 视图) 。</span><span class="sxs-lookup"><span data-stu-id="8a676-200">All objects in Snapshot #<number></strong>: Shows all objects on the heap (in other words, an <em>unfiltered</em> view).</span></span>

<span data-ttu-id="8a676-201">默认情况下 *，"显示不匹配* 的引用"筛选器应用于比较视图以指示与当前范围筛选器不匹配的对象引用。</span><span class="sxs-lookup"><span data-stu-id="8a676-201">By default, the *Show non-matching references* filter is applied to the comparison view to indicate object references that don't match the current Scope filter.</span></span> <span data-ttu-id="8a676-202">你可以从下拉菜单中关闭它：</span><span class="sxs-lookup"><span data-stu-id="8a676-202">You can turn it off from the dropdown menu:</span></span>

![快照比较的不匹配引用筛选器](./media/memory_comparison_matching_filter.png)


## <span data-ttu-id="8a676-204">快捷方式</span><span class="sxs-lookup"><span data-stu-id="8a676-204">Shortcuts</span></span>

 <span data-ttu-id="8a676-205">操作</span><span class="sxs-lookup"><span data-stu-id="8a676-205">Action</span></span> | <span data-ttu-id="8a676-206">快捷方式</span><span class="sxs-lookup"><span data-stu-id="8a676-206">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="8a676-207">启动/停止分析会话</span><span class="sxs-lookup"><span data-stu-id="8a676-207">Start / Stop profiling session</span></span>  | `Ctrl` + `E`
<span data-ttu-id="8a676-208">导入分析会话</span><span class="sxs-lookup"><span data-stu-id="8a676-208">Import profiling session</span></span> | `Ctrl` + `O`
<span data-ttu-id="8a676-209">导出分析会话</span><span class="sxs-lookup"><span data-stu-id="8a676-209">Export profiling session</span></span> | `Ctrl` + `S`
<span data-ttu-id="8a676-210">获取堆快照</span><span class="sxs-lookup"><span data-stu-id="8a676-210">Take heap snapshot</span></span> | `Ctrl` + `Shift` + `T`

## <span data-ttu-id="8a676-211">已知问题</span><span class="sxs-lookup"><span data-stu-id="8a676-211">Known Issues</span></span>

### <span data-ttu-id="8a676-212">启动分析会话时出错</span><span class="sxs-lookup"><span data-stu-id="8a676-212">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="8a676-213">如果看到以下错误消息：在"\*\*\*\* 内存"工具中启动分析会话时出错，请按照以下步骤操作以寻找解决方法。</span><span class="sxs-lookup"><span data-stu-id="8a676-213">If you see this error message: **An error occurred while starting the profiling session** in the Memory tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="8a676-214">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="8a676-214">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="8a676-215">在"运行"对话框中，输入**services.msc。**</span><span class="sxs-lookup"><span data-stu-id="8a676-215">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="8a676-217">找到 **Microsoft (R) 诊断中心标准收集器服务** 并右键单击它。</span><span class="sxs-lookup"><span data-stu-id="8a676-217">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="8a676-219">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="8a676-219">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="8a676-221">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="8a676-221">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="8a676-222">现在，你应该能够开始分析。</span><span class="sxs-lookup"><span data-stu-id="8a676-222">You should now be able to begin profiling.</span></span> 
![known-issues-4](./media/known_issues_4-memory.PNG)

<span data-ttu-id="8a676-224">是否仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="8a676-224">Still running into problems?</span></span> <span data-ttu-id="8a676-225">请使用"发送反馈"图标 **向我们发送反馈** ！</span><span class="sxs-lookup"><span data-stu-id="8a676-225">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)
