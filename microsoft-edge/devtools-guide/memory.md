---
description: 使用 "内存" 面板
title: DevTools-内存
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、内存、堆、GC、垃圾回收、保留的大小、dominators
ms.custom: seodec18
ms.openlocfilehash: 416ba144f7e22bd50f5d2a3437bc21d9d31a9035
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563476"
---
# <span data-ttu-id="35187-104">内存</span><span class="sxs-lookup"><span data-stu-id="35187-104">Memory</span></span>

<span data-ttu-id="35187-105">使用 " **内存** " 面板测量系统资源的使用情况，并在不同的代码执行状态中比较堆快照。</span><span class="sxs-lookup"><span data-stu-id="35187-105">Use the **Memory** panel to measure your use of system resources and compare heap snapshots at different states of code execution.</span></span> <span data-ttu-id="35187-106">有了它，您可以：</span><span class="sxs-lookup"><span data-stu-id="35187-106">With it, you can:</span></span>

- <span data-ttu-id="35187-107">[实时绘制页面的内存占用情况](#memory-usage-timeline) 并拍摄堆的快照</span><span class="sxs-lookup"><span data-stu-id="35187-107">[Graph the memory consumption of your page in real time](#memory-usage-timeline) and take snapshots of the heap</span></span>
- <span data-ttu-id="35187-108">[确定代码中可能存在的内存问题](#snapshot-summary) ，例如未附加到 DOM 的保留对象</span><span class="sxs-lookup"><span data-stu-id="35187-108">[Identify potential memory issues](#snapshot-summary) in your code, such as retained objects not attached to the DOM</span></span>
- <span data-ttu-id="35187-109">按对象类型、实例计数、大小和引用[查看内存使用数据](#snapshot-details)以帮助隔离问题</span><span class="sxs-lookup"><span data-stu-id="35187-109">[Review memory usage data](#snapshot-details) by object type, instance count, size, and references to help isolate issues</span></span>
- <span data-ttu-id="35187-110">[应用快照数据筛选器](#filters) 以减少不可操作的信息的干扰</span><span class="sxs-lookup"><span data-stu-id="35187-110">[Apply snapshot data filters](#filters) to reduce the noise of non-actionable information</span></span>
- <span data-ttu-id="35187-111">[确定特定对象的内存开销](#object-references) ，并且引用保持活动状态</span><span class="sxs-lookup"><span data-stu-id="35187-111">[Identify the memory cost of a specific object](#object-references) and the references keeping it alive</span></span>
- <span data-ttu-id="35187-112">[在调查的不同阶段比较堆](#snapshot-comparison) 以跟踪内存泄漏和其他问题的来源</span><span class="sxs-lookup"><span data-stu-id="35187-112">[Diff the heap at different phases of your investigation](#snapshot-comparison) to track down the source of memory leaks and other problems</span></span>

![Microsoft Edge DevTools 内存面板](./media/memory.png)


## <span data-ttu-id="35187-114">工具栏</span><span class="sxs-lookup"><span data-stu-id="35187-114">Toolbar</span></span>

1. <span data-ttu-id="35187-115">\*\*开始/停止分析会话 (Ctrl + E) \*\*：打开探查器可让你跟踪内存使用情况并拍摄堆的快照。</span><span class="sxs-lookup"><span data-stu-id="35187-115">**Start/Stop profiling session (Ctrl+E)**: Turning on the profiler enables you to track memory usage and take snapshots of the heap.</span></span>
2. <span data-ttu-id="35187-116">\*\* (Ctrl + O) 导入性能分析会话 \*\*：加载已保存的 DevTools 内存诊断会话。</span><span class="sxs-lookup"><span data-stu-id="35187-116">**Import profiling session (Ctrl+O)**: Load a saved  DevTools memory diagnostic session.</span></span>
3. <span data-ttu-id="35187-117">\*\* (Ctrl + S) 导出性能分析会话 \*\*：将当前的诊断会话保存到磁盘。</span><span class="sxs-lookup"><span data-stu-id="35187-117">**Export profiling session (Ctrl+S)**: Save the current diagnostic session to disk.</span></span>
4. <span data-ttu-id="35187-118">\*\*采用堆快照 (Ctrl + Shift + T) \*\*：记录给定时间点的当前内存分配。</span><span class="sxs-lookup"><span data-stu-id="35187-118">**Take heap snapshot (Ctrl+Shift+T)**: Record current memory allocations for a given point of time.</span></span>


## <span data-ttu-id="35187-119">内存使用日程表</span><span class="sxs-lookup"><span data-stu-id="35187-119">Memory usage timeline</span></span>

<span data-ttu-id="35187-120">内存问题可能是性能问题的主要原因，导致你的页面在一段时间内变得越来越慢和 laggy。</span><span class="sxs-lookup"><span data-stu-id="35187-120">Memory problems can be a major culprit of performance issues, causing your page to become increasingly unresponsive and laggy over time.</span></span>

<span data-ttu-id="35187-121">分析页面的内存使用的第一步是 [启动性能分析会话](#toolbar) ，以便在你重现导致内存膨胀或可疑内存泄漏的步骤之前和之后执行堆栈快照。</span><span class="sxs-lookup"><span data-stu-id="35187-121">The first step to analyzing the memory usage of your page is to [start a profiling session](#toolbar) in order to take before/after snapshots of the heap as you repro the steps causing memory bloat or a suspected memory leak.</span></span>

<span data-ttu-id="35187-122">启动内存探查器时，你将看到一个进程内存图，使你能够观察整个专用工作集， (页面随时间推移) 占用的内存量。</span><span class="sxs-lookup"><span data-stu-id="35187-122">When you start the memory profiler, you will see a process memory graph that allows you to observe the overall private working set (the amount of memory consumed by the page) over time.</span></span> <span data-ttu-id="35187-123">"内存" 图显示了选项卡的进程内存的实时视图，其中包括专用字节、本机内存和 JavaScript 堆。</span><span class="sxs-lookup"><span data-stu-id="35187-123">The memory graph shows you a live view of the tab's process memory, which includes private bytes, native memory, and the JavaScript heap.</span></span> 

![内存使用日程表](./media/memory_timeline.png)

 <span data-ttu-id="35187-125">该图提供了页面的内存趋势的指示，使你能够判断何时适合将 [堆快照](#toolbar) 用作后续比较，例如当你看到意外内存保留期间。</span><span class="sxs-lookup"><span data-stu-id="35187-125">The graph gives you an indication of the memory trend for the page which enables you to judge when it is appropriate to [take a heap snapshot](#toolbar) for later comparison, such as when you see periods of unexpected memory retention.</span></span>

### <span data-ttu-id="35187-126">性能。标记 ( # A1</span><span class="sxs-lookup"><span data-stu-id="35187-126">Performance.mark()</span></span>

<span data-ttu-id="35187-127">你可以将自定义 **用户标记** 添加到日程表，以通过 [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) 从你的代码或 DevTools [**控制台**](./console.md)调用该方法来帮助标识分析会话期间的关键事件。</span><span class="sxs-lookup"><span data-stu-id="35187-127">You can add custom **User marks** to the timeline to help identify  key events during the course of your analysis session by calling the [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span>

### <span data-ttu-id="35187-128">TakeheapSnapshot ( # A1</span><span class="sxs-lookup"><span data-stu-id="35187-128">Console.takeheapSnapshot()</span></span>

<span data-ttu-id="35187-129">有时，你需要在非常具体的时间点拍摄快照，例如在 DOM 的较大变化之前。</span><span class="sxs-lookup"><span data-stu-id="35187-129">Sometimes you need to take snapshots at very specific points in time, such as immediately before a large mutation of the DOM.</span></span> <span data-ttu-id="35187-130">在这些情况下，你可以采用编程方式获取快照 [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots) 。</span><span class="sxs-lookup"><span data-stu-id="35187-130">In these cases,you can take snapshots programmatically with [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots).</span></span>

## <span data-ttu-id="35187-131">快照摘要</span><span class="sxs-lookup"><span data-stu-id="35187-131">Snapshot summary</span></span>

<span data-ttu-id="35187-132">[拍摄快照](#toolbar) 将生成一个摘要磁贴，该图块指示拍摄快照时 JavaScript 堆的大小以及所分配的对象数和页面的屏幕截图。</span><span class="sxs-lookup"><span data-stu-id="35187-132">[Taking a snapshot](#toolbar) will generate a summary tile that indicates the size of the JavaScript heap at the time the snapshot was taken, along with the number of objects allocated and a screenshot of the page.</span></span> <span data-ttu-id="35187-133">在运行需要分析的用户方案时，你可以随时继续拍摄快照。</span><span class="sxs-lookup"><span data-stu-id="35187-133">You can continue to take snapshots at any time as you run through the user scenario requiring analysis.</span></span> <span data-ttu-id="35187-134">快照会生成其他磁贴，每个磁贴指示 JavaScript 内存中来自上一个快照的差异。</span><span class="sxs-lookup"><span data-stu-id="35187-134">The snapshots generate additional tiles, each of which indicates the difference in JavaScript memory from the previous snapshot.</span></span>

![堆快照](./media/memory_snapshot.png)

<span data-ttu-id="35187-136">单击摘要磁贴中的值将切换到显示 [快照数据详细信息](#snapshot-details)的窗格。</span><span class="sxs-lookup"><span data-stu-id="35187-136">Clicking on the values in the summary tile will switch to the pane showing [details of the snapshot data](#snapshot-details).</span></span> <span data-ttu-id="35187-137">使用蓝色信息 ( "i" ) 图标表示潜在的 [内存问题](#snapshot-details) 。</span><span class="sxs-lookup"><span data-stu-id="35187-137">Potential [memory issues are indicated](#snapshot-details) with a blue informational ("i") icon.</span></span>

## <span data-ttu-id="35187-138">快照详细信息</span><span class="sxs-lookup"><span data-stu-id="35187-138">Snapshot details</span></span>

<span data-ttu-id="35187-139">" *快照* " 窗格中的数据显示由您的页面创建的对象以及你可能需要使用的 JavaScript 框架分配的任何内存。</span><span class="sxs-lookup"><span data-stu-id="35187-139">The data in the *Snapshot* pane shows the objects created by your page along with any memory allocated by JavaScript frameworks you may be consuming.</span></span>

![快照详细信息表](./media/memory_details.png)

<span data-ttu-id="35187-141">这三个选项卡代表数据的不同视图：</span><span class="sxs-lookup"><span data-stu-id="35187-141">The three tabs represent different views of the data:</span></span>

#### <span data-ttu-id="35187-142">类型</span><span class="sxs-lookup"><span data-stu-id="35187-142">Types</span></span>

<span data-ttu-id="35187-143">显示堆上的对象的实例计数和总大小，按对象类型分组。</span><span class="sxs-lookup"><span data-stu-id="35187-143">Shows the instance count and total size of objects on the heap, grouped by object type.</span></span> <span data-ttu-id="35187-144">默认情况下，这些按实例计数进行排序。</span><span class="sxs-lookup"><span data-stu-id="35187-144">By default, these are sorted by instance count.</span></span>

<span data-ttu-id="35187-145">在 "上部 *类型* " 窗格中选择对象时，下方窗格中的 " [对象引用](#object-references) " 表将列出指向该对象的所有对象。</span><span class="sxs-lookup"><span data-stu-id="35187-145">When you select an object in the upper *Types* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

#### <span data-ttu-id="35187-146">方根</span><span class="sxs-lookup"><span data-stu-id="35187-146">Roots</span></span>

<span data-ttu-id="35187-147">显示子引用的分层视图，以描述对象如何成为全局对象的根，从而阻止它们被垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="35187-147">Shows a hierarchical view of child references to describe how objects are rooted to the global object, thus preventing them from being garbage-collected.</span></span>

<span data-ttu-id="35187-148">默认情况下，子节点按 "保留的大小" 列进行排序，最大的值位于顶部。</span><span class="sxs-lookup"><span data-stu-id="35187-148">By default, the child nodes are sorted by the retained size column, with the largest at the top.</span></span>

#### <span data-ttu-id="35187-149">Dominators</span><span class="sxs-lookup"><span data-stu-id="35187-149">Dominators</span></span>

<span data-ttu-id="35187-150">显示堆上具有对其他对象的独占引用的对象的列表。</span><span class="sxs-lookup"><span data-stu-id="35187-150">Shows a list of objects on the heap that have exclusive references to other objects.</span></span> <span data-ttu-id="35187-151">Dominators 按保留大小排序，以指示占用最容易自由的内存的对象。</span><span class="sxs-lookup"><span data-stu-id="35187-151">Dominators are sorted by retained size to indicate the objects consuming the most memory that are potentially easiest to free.</span></span>

<span data-ttu-id="35187-152">下面介绍了如何解释 *类型、根* 和 *Dominators* 视图中的列：</span><span class="sxs-lookup"><span data-stu-id="35187-152">Here's how to interpret the columns in the *Types, Roots* and *Dominators* views:</span></span>

<span data-ttu-id="35187-153">列</span><span class="sxs-lookup"><span data-stu-id="35187-153">Column</span></span> | <span data-ttu-id="35187-154">描述</span><span class="sxs-lookup"><span data-stu-id="35187-154">Description</span></span>
:------------ | :-------------
<span data-ttu-id="35187-155"> (s 的标识符) </span><span class="sxs-lookup"><span data-stu-id="35187-155">Identifier(s)</span></span> | <span data-ttu-id="35187-156">最能识别对象的名称。</span><span class="sxs-lookup"><span data-stu-id="35187-156">Name that best identifies the object.</span></span> <span data-ttu-id="35187-157">例如，对于 HTML 元素，快照详细信息显示 ID 属性值（如果使用了一个）。</span><span class="sxs-lookup"><span data-stu-id="35187-157">For example, for HTML elements the snapshot details show the ID attribute value, if one is used.</span></span>
<span data-ttu-id="35187-158">类型</span><span class="sxs-lookup"><span data-stu-id="35187-158">Type</span></span> | <span data-ttu-id="35187-159">对象类型 (例如， *HTMLDivElement*) 。</span><span class="sxs-lookup"><span data-stu-id="35187-159">Object type (for example, *HTMLDivElement*).</span></span>
<span data-ttu-id="35187-160">大小</span><span class="sxs-lookup"><span data-stu-id="35187-160">Size</span></span> | <span data-ttu-id="35187-161">对象大小，不包括任何引用对象的大小。</span><span class="sxs-lookup"><span data-stu-id="35187-161">Object size, not including the size of any referenced objects.</span></span>
<span data-ttu-id="35187-162">保留大小</span><span class="sxs-lookup"><span data-stu-id="35187-162">Retained size</span></span> | <span data-ttu-id="35187-163">对象大小加上没有其他父对象的所有子对象的大小。</span><span class="sxs-lookup"><span data-stu-id="35187-163">Object size plus the size of all child objects that have no other parents.</span></span> <span data-ttu-id="35187-164">为了便于使用，这是由对象保留的内存量，因此，如果你删除了指定的内存量，则会删除该对象。</span><span class="sxs-lookup"><span data-stu-id="35187-164">For practical purposes, this is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>
<span data-ttu-id="35187-165">Count</span><span class="sxs-lookup"><span data-stu-id="35187-165">Count</span></span> | <span data-ttu-id="35187-166">对象实例数。</span><span class="sxs-lookup"><span data-stu-id="35187-166">Number of object instances.</span></span> <span data-ttu-id="35187-167">此值仅在 "类型" 视图中显示。</span><span class="sxs-lookup"><span data-stu-id="35187-167">This value appears only in the Types view.</span></span>

<span data-ttu-id="35187-168">在上方的 *Dominators* 窗格中选择对象时，下方窗格中的 " [对象引用](#object-references) " 表将列出指向该对象的所有对象。</span><span class="sxs-lookup"><span data-stu-id="35187-168">When you select an object in the upper *Dominators* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

### <span data-ttu-id="35187-169">筛选器</span><span class="sxs-lookup"><span data-stu-id="35187-169">Filters</span></span>

<span data-ttu-id="35187-170">你可以通过以下方式进一步调整表中的数据：</span><span class="sxs-lookup"><span data-stu-id="35187-170">You can further adjust data in the table with the following:</span></span>

![筛选内置和对象 Id](./media/memory_filter.png)

1. <span data-ttu-id="35187-172">**标识符筛选器**：通过搜索特定对象标识符来筛选数据</span><span class="sxs-lookup"><span data-stu-id="35187-172">**Identifier filter**: Filter out data by searching for a particular object identifier</span></span>
2. <span data-ttu-id="35187-173">**按 Dominator 分组**：只有对其他对象具有 *独占* 引用的对象才会显示在对象的顶级视图中， (这是 *Dominators* 选项卡中的默认视图) 。</span><span class="sxs-lookup"><span data-stu-id="35187-173">**Group by dominator**: Only objects with *exclusive* references to other objects are shown in the top-level view of objects (this is the default view in the *Dominators* tab).</span></span>
3. <span data-ttu-id="35187-174">**内置/IDs 筛选器**：默认情况下，列表中包含 [JavaScript 内置对象](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) 。</span><span class="sxs-lookup"><span data-stu-id="35187-174">**Built-ins / IDs filter**: By default, [JavaScript built-in objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) are included in the list.</span></span> <span data-ttu-id="35187-175">如果存在多个需要区分的匿名对象，则列出对象 Id 可能很有用。</span><span class="sxs-lookup"><span data-stu-id="35187-175">Listing object IDs can be useful if there are multiple anonymous objects which need to be differentiated.</span></span>

<span data-ttu-id="35187-176">每个 *类型、根* 和 *Dominators* 视图都有其自己的筛选器，因此切换到另一个视图时不会保留筛选器。</span><span class="sxs-lookup"><span data-stu-id="35187-176">The *Types, Roots* and *Dominators* views each has its own filter, so the filter isn't preserved when you switch to another view.</span></span>

### <span data-ttu-id="35187-177">对象引用</span><span class="sxs-lookup"><span data-stu-id="35187-177">Object references</span></span>

<span data-ttu-id="35187-178">在 " [**类型**](#types) " 和 " [**Dominators**](#dominators) " 视图中，下方窗格包含显示共享引用的 " **对象引用** " 列表。</span><span class="sxs-lookup"><span data-stu-id="35187-178">In the [**Types**](#types) and [**Dominators**](#dominators) views, the lower pane contains an **Object references** list that displays shared references.</span></span> <span data-ttu-id="35187-179">当您在上部窗格中选择一个对象时，此列表将显示指向该对象的所有对象，换句话说，是使所选对象保持活动状态的对象。</span><span class="sxs-lookup"><span data-stu-id="35187-179">When you choose an object in the upper pane, this list displays all objects that point to that object--in other words, the objects that are keeping the selected object alive.</span></span>

<span data-ttu-id="35187-180">循环引用以星号 ( \* ) 和信息工具提示显示，并且不能展开。</span><span class="sxs-lookup"><span data-stu-id="35187-180">Circular references are shown with an asterisk (\*) and informational tooltip, and cannot be expanded.</span></span> <span data-ttu-id="35187-181">否则，它们将阻止你向上遍历引用树和标识保留内存的对象。</span><span class="sxs-lookup"><span data-stu-id="35187-181">Otherwise, they would prevent you from walking up the reference tree and identifying objects that are retaining memory.</span></span>

<span data-ttu-id="35187-182">若要快速识别等效对象，请勾选 " [*显示对象 id*](#filters) " 筛选器选项，以便在 " \*标识符 (s) \* " 列中的对象名称旁显示对象 id。</span><span class="sxs-lookup"><span data-stu-id="35187-182">To quickly identify equivalent objects, tick the [*Display object IDs*](#filters) filter option to display object IDs next to object names in the *Identifier(s)* column.</span></span> <span data-ttu-id="35187-183">具有相同 ID 的对象为共享引用。</span><span class="sxs-lookup"><span data-stu-id="35187-183">Objects that have the same ID are shared references.</span></span>

### <span data-ttu-id="35187-184">快照比较</span><span class="sxs-lookup"><span data-stu-id="35187-184">Snapshot comparison</span></span>

<span data-ttu-id="35187-185">单击 "[快照摘要" 图块](#snapshot-summary)上的 "[快照比较" 选项卡](#snapshot-details)或比较链接将显示两个快照之间的信息的比较。</span><span class="sxs-lookup"><span data-stu-id="35187-185">Clicking on a [snapshot comparison tab](#snapshot-details) or comparison link on the [snapshot summary tile](#snapshot-summary)  will show a diff of information between the two snapshots.</span></span> <span data-ttu-id="35187-186">在 "比较" 窗格中，" *Dominators"、"类型* " 和 " *根* " 视图提供了相同的 [*快照详细信息*](#snapshot-details) ，你可以看到一个快照的详细信息，包括以下其他值：</span><span class="sxs-lookup"><span data-stu-id="35187-186">In the comparison pane, the *Dominators, Types* and *Roots* views provide the same [*snapshot details*](#snapshot-details) you would see for a single snapshots, with these additional values:</span></span>

<span data-ttu-id="35187-187">列</span><span class="sxs-lookup"><span data-stu-id="35187-187">Column</span></span> | <span data-ttu-id="35187-188">描述</span><span class="sxs-lookup"><span data-stu-id="35187-188">Description</span></span>
:------------ | :-------------
<span data-ttu-id="35187-189">大小差异。</span><span class="sxs-lookup"><span data-stu-id="35187-189">Size diff.</span></span> | <span data-ttu-id="35187-190">当前快照中对象的大小与上一快照中的对象大小之间的差异，不包括任何引用对象的大小。</span><span class="sxs-lookup"><span data-stu-id="35187-190">Difference between the size of the object in the current snapshot and its size in the previous snapshot, not including the size of any referenced objects.</span></span>
<span data-ttu-id="35187-191">保留大小差异。</span><span class="sxs-lookup"><span data-stu-id="35187-191">Retained size diff.</span></span> | <span data-ttu-id="35187-192">当前快照中对象的保留大小与上一快照中的保留大小之间的差异。</span><span class="sxs-lookup"><span data-stu-id="35187-192">Difference between the retained size of the object in the current snapshot and its retained size in the previous snapshot.</span></span> <span data-ttu-id="35187-193">保留的大小包括对象大小加上没有其他父对象的所有子对象的大小。</span><span class="sxs-lookup"><span data-stu-id="35187-193">The retained size includes the object size plus the size of all its child objects that have no other parents.</span></span> <span data-ttu-id="35187-194">为了实用，保留大小是指由对象保留的内存量，因此，如果你删除了指定的内存量，则会删除该对象。</span><span class="sxs-lookup"><span data-stu-id="35187-194">For practical purposes, the retained size is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>

<span data-ttu-id="35187-195">你可以使用 **范围** 下拉列表来筛选快照之间的差异信息：</span><span class="sxs-lookup"><span data-stu-id="35187-195">You can use the **Scope** dropdown to filter differential info between snapshots:</span></span>

![快照 comparisions 的作用域筛选器](./media/memory_comparison_scope_filter.png)

- <strong><span data-ttu-id="35187-197">从快照 # 中留下的对象 # <number></strong> ：显示添加到堆中的对象与从基线快照到上一个快照的堆栈之间的比较。</span><span class="sxs-lookup"><span data-stu-id="35187-197">Objects left over from Snapshot #<number></strong>: Shows the diff between the objects added to the heap and removed from the heap from the baseline snapshot to the previous snapshot.</span></span> <span data-ttu-id="35187-198">例如，如果 "快照摘要" <em> 在对象计数中显示 + 205/-195 </em> ，此筛选器将显示已添加但未删除的十个对象。</span><span class="sxs-lookup"><span data-stu-id="35187-198">For example, if the snapshot summary shows <em>+205 / -195</em> in the object count, this filter will show you the ten objects that were added but not removed.</span></span>

- <strong><span data-ttu-id="35187-199">在快照 # <number> 和 #：之间添加 <number></strong> 的对象显示从以前的快照添加到堆的所有对象。</span><span class="sxs-lookup"><span data-stu-id="35187-199">Objects added between Snapshot #<number> and #<number></strong>: Shows all objects added to the heap from the previous snapshot.</span></span>

- <strong><span data-ttu-id="35187-200">快照 #：中的所有对象都 <number></strong> 显示堆上的所有对象 (换言之，"未 <em> 筛选的视图" </em>) 。</span><span class="sxs-lookup"><span data-stu-id="35187-200">All objects in Snapshot #<number></strong>: Shows all objects on the heap (in other words, an <em>unfiltered</em> view).</span></span>

<span data-ttu-id="35187-201">默认情况下，" *显示不匹配的引用* " 筛选器将应用于 "比较" 视图，以指示与当前范围筛选器不匹配的对象引用。</span><span class="sxs-lookup"><span data-stu-id="35187-201">By default, the *Show non-matching references* filter is applied to the comparison view to indicate object references that don't match the current Scope filter.</span></span> <span data-ttu-id="35187-202">您可以从下拉菜单中将其关闭：</span><span class="sxs-lookup"><span data-stu-id="35187-202">You can turn it off from the dropdown menu:</span></span>

![不匹配的引用筛选快照比较](./media/memory_comparison_matching_filter.png)


## <span data-ttu-id="35187-204">快捷方式</span><span class="sxs-lookup"><span data-stu-id="35187-204">Shortcuts</span></span>

 <span data-ttu-id="35187-205">操作</span><span class="sxs-lookup"><span data-stu-id="35187-205">Action</span></span> | <span data-ttu-id="35187-206">快捷方式</span><span class="sxs-lookup"><span data-stu-id="35187-206">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="35187-207">开始/停止分析会话</span><span class="sxs-lookup"><span data-stu-id="35187-207">Start / Stop profiling session</span></span>  | `Ctrl` + `E`
<span data-ttu-id="35187-208">导入性能分析会话</span><span class="sxs-lookup"><span data-stu-id="35187-208">Import profiling session</span></span> | `Ctrl` + `O`
<span data-ttu-id="35187-209">导出分析会话</span><span class="sxs-lookup"><span data-stu-id="35187-209">Export profiling session</span></span> | `Ctrl` + `S`
<span data-ttu-id="35187-210">获取堆快照</span><span class="sxs-lookup"><span data-stu-id="35187-210">Take heap snapshot</span></span> | `Ctrl` + `Shift` + `T`

## <span data-ttu-id="35187-211">已知问题</span><span class="sxs-lookup"><span data-stu-id="35187-211">Known Issues</span></span>

### <span data-ttu-id="35187-212">启动分析会话时出错</span><span class="sxs-lookup"><span data-stu-id="35187-212">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="35187-213">如果你看到此错误消息：在内存工具中 **启动分析会话时出错** ，请按照以下步骤进行解决。</span><span class="sxs-lookup"><span data-stu-id="35187-213">If you see this error message: **An error occurred while starting the profiling session** in the Memory tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="35187-214">按 `Windows Key`  +  `R` 。</span><span class="sxs-lookup"><span data-stu-id="35187-214">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="35187-215">在 "运行" 对话框中，输入 **services.msc**。</span><span class="sxs-lookup"><span data-stu-id="35187-215">In the Run dialog, enter **services.msc**.</span></span>
![已知问题-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="35187-217">找到 **Microsoft (R) 诊断中心标准收集器服务** ，然后右键单击它。</span><span class="sxs-lookup"><span data-stu-id="35187-217">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![已知问题-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="35187-219">重新启动 **Microsoft (R) 诊断中心标准收集器服务**。</span><span class="sxs-lookup"><span data-stu-id="35187-219">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![已知问题-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="35187-221">关闭 Microsoft Edge 开发人员工具和选项卡。打开新选项卡，导航到您的页面，然后按 `F12` 。</span><span class="sxs-lookup"><span data-stu-id="35187-221">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="35187-222">现在，你应该能够开始分析。</span><span class="sxs-lookup"><span data-stu-id="35187-222">You should now be able to begin profiling.</span></span> 
![已知问题-4](./media/known_issues_4-memory.PNG)

<span data-ttu-id="35187-224">仍遇到问题？</span><span class="sxs-lookup"><span data-stu-id="35187-224">Still running into problems?</span></span> <span data-ttu-id="35187-225">请使用 " **发送反馈** " 图标向我们发送您的反馈！</span><span class="sxs-lookup"><span data-stu-id="35187-225">Please send us your feedback using the **Send feedback** icon!</span></span> 

![已知问题-5](./media/known_issues_5.PNG)
