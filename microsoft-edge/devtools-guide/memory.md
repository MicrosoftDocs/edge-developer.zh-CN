---
description: Use the Memory panel to
title: DevTools - Memory
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools, memory, heap, GC, garbage collection, retained size, dominators
ms.custom: seodec18
ms.openlocfilehash: 416ba144f7e22bd50f5d2a3437bc21d9d31a9035
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10563476"
---
# <span data-ttu-id="810cb-104">Memory</span><span class="sxs-lookup"><span data-stu-id="810cb-104">Memory</span></span>

<span data-ttu-id="810cb-105">Use the **Memory** panel to measure your use of system resources and compare heap snapshots at different states of code execution.</span><span class="sxs-lookup"><span data-stu-id="810cb-105">Use the **Memory** panel to measure your use of system resources and compare heap snapshots at different states of code execution.</span></span> <span data-ttu-id="810cb-106">With it, you can:</span><span class="sxs-lookup"><span data-stu-id="810cb-106">With it, you can:</span></span>

- <span data-ttu-id="810cb-107">[Graph the memory consumption of your page in real time](#memory-usage-timeline) and take snapshots of the heap</span><span class="sxs-lookup"><span data-stu-id="810cb-107">[Graph the memory consumption of your page in real time](#memory-usage-timeline) and take snapshots of the heap</span></span>
- <span data-ttu-id="810cb-108">[Identify potential memory issues](#snapshot-summary) in your code, such as retained objects not attached to the DOM</span><span class="sxs-lookup"><span data-stu-id="810cb-108">[Identify potential memory issues](#snapshot-summary) in your code, such as retained objects not attached to the DOM</span></span>
- <span data-ttu-id="810cb-109">[Review memory usage data](#snapshot-details) by object type, instance count, size, and references to help isolate issues</span><span class="sxs-lookup"><span data-stu-id="810cb-109">[Review memory usage data](#snapshot-details) by object type, instance count, size, and references to help isolate issues</span></span>
- <span data-ttu-id="810cb-110">[Apply snapshot data filters](#filters) to reduce the noise of non-actionable information</span><span class="sxs-lookup"><span data-stu-id="810cb-110">[Apply snapshot data filters](#filters) to reduce the noise of non-actionable information</span></span>
- <span data-ttu-id="810cb-111">[Identify the memory cost of a specific object](#object-references) and the references keeping it alive</span><span class="sxs-lookup"><span data-stu-id="810cb-111">[Identify the memory cost of a specific object](#object-references) and the references keeping it alive</span></span>
- <span data-ttu-id="810cb-112">[Diff the heap at different phases of your investigation](#snapshot-comparison) to track down the source of memory leaks and other problems</span><span class="sxs-lookup"><span data-stu-id="810cb-112">[Diff the heap at different phases of your investigation](#snapshot-comparison) to track down the source of memory leaks and other problems</span></span>

![The Microsoft Edge  DevTools Memory panel](./media/memory.png)


## <span data-ttu-id="810cb-114">Toolbar</span><span class="sxs-lookup"><span data-stu-id="810cb-114">Toolbar</span></span>

1. <span data-ttu-id="810cb-115">**Start/Stop profiling session (Ctrl+E)**: Turning on the profiler enables you to track memory usage and take snapshots of the heap.</span><span class="sxs-lookup"><span data-stu-id="810cb-115">**Start/Stop profiling session (Ctrl+E)**: Turning on the profiler enables you to track memory usage and take snapshots of the heap.</span></span>
2. <span data-ttu-id="810cb-116">**Import profiling session (Ctrl+O)**: Load a saved  DevTools memory diagnostic session.</span><span class="sxs-lookup"><span data-stu-id="810cb-116">**Import profiling session (Ctrl+O)**: Load a saved  DevTools memory diagnostic session.</span></span>
3. <span data-ttu-id="810cb-117">**Export profiling session (Ctrl+S)**: Save the current diagnostic session to disk.</span><span class="sxs-lookup"><span data-stu-id="810cb-117">**Export profiling session (Ctrl+S)**: Save the current diagnostic session to disk.</span></span>
4. <span data-ttu-id="810cb-118">**Take heap snapshot (Ctrl+Shift+T)**: Record current memory allocations for a given point of time.</span><span class="sxs-lookup"><span data-stu-id="810cb-118">**Take heap snapshot (Ctrl+Shift+T)**: Record current memory allocations for a given point of time.</span></span>


## <span data-ttu-id="810cb-119">Memory usage timeline</span><span class="sxs-lookup"><span data-stu-id="810cb-119">Memory usage timeline</span></span>

<span data-ttu-id="810cb-120">Memory problems can be a major culprit of performance issues, causing your page to become increasingly unresponsive and laggy over time.</span><span class="sxs-lookup"><span data-stu-id="810cb-120">Memory problems can be a major culprit of performance issues, causing your page to become increasingly unresponsive and laggy over time.</span></span>

<span data-ttu-id="810cb-121">The first step to analyzing the memory usage of your page is to [start a profiling session](#toolbar) in order to take before/after snapshots of the heap as you repro the steps causing memory bloat or a suspected memory leak.</span><span class="sxs-lookup"><span data-stu-id="810cb-121">The first step to analyzing the memory usage of your page is to [start a profiling session](#toolbar) in order to take before/after snapshots of the heap as you repro the steps causing memory bloat or a suspected memory leak.</span></span>

<span data-ttu-id="810cb-122">When you start the memory profiler, you will see a process memory graph that allows you to observe the overall private working set (the amount of memory consumed by the page) over time.</span><span class="sxs-lookup"><span data-stu-id="810cb-122">When you start the memory profiler, you will see a process memory graph that allows you to observe the overall private working set (the amount of memory consumed by the page) over time.</span></span> <span data-ttu-id="810cb-123">The memory graph shows you a live view of the tab's process memory, which includes private bytes, native memory, and the JavaScript heap.</span><span class="sxs-lookup"><span data-stu-id="810cb-123">The memory graph shows you a live view of the tab's process memory, which includes private bytes, native memory, and the JavaScript heap.</span></span> 

![Memory usage timeline](./media/memory_timeline.png)

 <span data-ttu-id="810cb-125">The graph gives you an indication of the memory trend for the page which enables you to judge when it is appropriate to [take a heap snapshot](#toolbar) for later comparison, such as when you see periods of unexpected memory retention.</span><span class="sxs-lookup"><span data-stu-id="810cb-125">The graph gives you an indication of the memory trend for the page which enables you to judge when it is appropriate to [take a heap snapshot](#toolbar) for later comparison, such as when you see periods of unexpected memory retention.</span></span>

### <span data-ttu-id="810cb-126">Performance.mark()</span><span class="sxs-lookup"><span data-stu-id="810cb-126">Performance.mark()</span></span>

<span data-ttu-id="810cb-127">You can add custom **User marks** to the timeline to help identify  key events during the course of your analysis session by calling the [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span><span class="sxs-lookup"><span data-stu-id="810cb-127">You can add custom **User marks** to the timeline to help identify  key events during the course of your analysis session by calling the [`Performance.mark()`](https://developer.mozilla.org/docs/Web/API/Performance/mark) method from within your code or the  DevTools [**Console**](./console.md).</span></span>

### <span data-ttu-id="810cb-128">Console.takeheapSnapshot()</span><span class="sxs-lookup"><span data-stu-id="810cb-128">Console.takeheapSnapshot()</span></span>

<span data-ttu-id="810cb-129">Sometimes you need to take snapshots at very specific points in time, such as immediately before a large mutation of the DOM.</span><span class="sxs-lookup"><span data-stu-id="810cb-129">Sometimes you need to take snapshots at very specific points in time, such as immediately before a large mutation of the DOM.</span></span> <span data-ttu-id="810cb-130">In these cases,you can take snapshots programmatically with [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots).</span><span class="sxs-lookup"><span data-stu-id="810cb-130">In these cases,you can take snapshots programmatically with [`Console.takeHeapSnapshot()`](./console/console-api.md#taking-heap-snapshots).</span></span>

## <span data-ttu-id="810cb-131">Snapshot summary</span><span class="sxs-lookup"><span data-stu-id="810cb-131">Snapshot summary</span></span>

<span data-ttu-id="810cb-132">[Taking a snapshot](#toolbar) will generate a summary tile that indicates the size of the JavaScript heap at the time the snapshot was taken, along with the number of objects allocated and a screenshot of the page.</span><span class="sxs-lookup"><span data-stu-id="810cb-132">[Taking a snapshot](#toolbar) will generate a summary tile that indicates the size of the JavaScript heap at the time the snapshot was taken, along with the number of objects allocated and a screenshot of the page.</span></span> <span data-ttu-id="810cb-133">You can continue to take snapshots at any time as you run through the user scenario requiring analysis.</span><span class="sxs-lookup"><span data-stu-id="810cb-133">You can continue to take snapshots at any time as you run through the user scenario requiring analysis.</span></span> <span data-ttu-id="810cb-134">The snapshots generate additional tiles, each of which indicates the difference in JavaScript memory from the previous snapshot.</span><span class="sxs-lookup"><span data-stu-id="810cb-134">The snapshots generate additional tiles, each of which indicates the difference in JavaScript memory from the previous snapshot.</span></span>

![Heap snapshot](./media/memory_snapshot.png)

<span data-ttu-id="810cb-136">Clicking on the values in the summary tile will switch to the pane showing [details of the snapshot data](#snapshot-details).</span><span class="sxs-lookup"><span data-stu-id="810cb-136">Clicking on the values in the summary tile will switch to the pane showing [details of the snapshot data](#snapshot-details).</span></span> <span data-ttu-id="810cb-137">Potential [memory issues are indicated](#snapshot-details) with a blue informational ("i") icon.</span><span class="sxs-lookup"><span data-stu-id="810cb-137">Potential [memory issues are indicated](#snapshot-details) with a blue informational ("i") icon.</span></span>

## <span data-ttu-id="810cb-138">Snapshot details</span><span class="sxs-lookup"><span data-stu-id="810cb-138">Snapshot details</span></span>

<span data-ttu-id="810cb-139">The data in the *Snapshot* pane shows the objects created by your page along with any memory allocated by JavaScript frameworks you may be consuming.</span><span class="sxs-lookup"><span data-stu-id="810cb-139">The data in the *Snapshot* pane shows the objects created by your page along with any memory allocated by JavaScript frameworks you may be consuming.</span></span>

![Snapshot details table](./media/memory_details.png)

<span data-ttu-id="810cb-141">The three tabs represent different views of the data:</span><span class="sxs-lookup"><span data-stu-id="810cb-141">The three tabs represent different views of the data:</span></span>

#### <span data-ttu-id="810cb-142">Types</span><span class="sxs-lookup"><span data-stu-id="810cb-142">Types</span></span>

<span data-ttu-id="810cb-143">Shows the instance count and total size of objects on the heap, grouped by object type.</span><span class="sxs-lookup"><span data-stu-id="810cb-143">Shows the instance count and total size of objects on the heap, grouped by object type.</span></span> <span data-ttu-id="810cb-144">By default, these are sorted by instance count.</span><span class="sxs-lookup"><span data-stu-id="810cb-144">By default, these are sorted by instance count.</span></span>

<span data-ttu-id="810cb-145">When you select an object in the upper *Types* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span><span class="sxs-lookup"><span data-stu-id="810cb-145">When you select an object in the upper *Types* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

#### <span data-ttu-id="810cb-146">Roots</span><span class="sxs-lookup"><span data-stu-id="810cb-146">Roots</span></span>

<span data-ttu-id="810cb-147">Shows a hierarchical view of child references to describe how objects are rooted to the global object, thus preventing them from being garbage-collected.</span><span class="sxs-lookup"><span data-stu-id="810cb-147">Shows a hierarchical view of child references to describe how objects are rooted to the global object, thus preventing them from being garbage-collected.</span></span>

<span data-ttu-id="810cb-148">By default, the child nodes are sorted by the retained size column, with the largest at the top.</span><span class="sxs-lookup"><span data-stu-id="810cb-148">By default, the child nodes are sorted by the retained size column, with the largest at the top.</span></span>

#### <span data-ttu-id="810cb-149">Dominators</span><span class="sxs-lookup"><span data-stu-id="810cb-149">Dominators</span></span>

<span data-ttu-id="810cb-150">Shows a list of objects on the heap that have exclusive references to other objects.</span><span class="sxs-lookup"><span data-stu-id="810cb-150">Shows a list of objects on the heap that have exclusive references to other objects.</span></span> <span data-ttu-id="810cb-151">Dominators are sorted by retained size to indicate the objects consuming the most memory that are potentially easiest to free.</span><span class="sxs-lookup"><span data-stu-id="810cb-151">Dominators are sorted by retained size to indicate the objects consuming the most memory that are potentially easiest to free.</span></span>

<span data-ttu-id="810cb-152">Here's how to interpret the columns in the *Types, Roots* and *Dominators* views:</span><span class="sxs-lookup"><span data-stu-id="810cb-152">Here's how to interpret the columns in the *Types, Roots* and *Dominators* views:</span></span>

<span data-ttu-id="810cb-153">Column</span><span class="sxs-lookup"><span data-stu-id="810cb-153">Column</span></span> | <span data-ttu-id="810cb-154">Description</span><span class="sxs-lookup"><span data-stu-id="810cb-154">Description</span></span>
:------------ | :-------------
<span data-ttu-id="810cb-155">Identifier(s)</span><span class="sxs-lookup"><span data-stu-id="810cb-155">Identifier(s)</span></span> | <span data-ttu-id="810cb-156">Name that best identifies the object.</span><span class="sxs-lookup"><span data-stu-id="810cb-156">Name that best identifies the object.</span></span> <span data-ttu-id="810cb-157">For example, for HTML elements the snapshot details show the ID attribute value, if one is used.</span><span class="sxs-lookup"><span data-stu-id="810cb-157">For example, for HTML elements the snapshot details show the ID attribute value, if one is used.</span></span>
<span data-ttu-id="810cb-158">Type</span><span class="sxs-lookup"><span data-stu-id="810cb-158">Type</span></span> | <span data-ttu-id="810cb-159">Object type (for example, *HTMLDivElement*).</span><span class="sxs-lookup"><span data-stu-id="810cb-159">Object type (for example, *HTMLDivElement*).</span></span>
<span data-ttu-id="810cb-160">Size</span><span class="sxs-lookup"><span data-stu-id="810cb-160">Size</span></span> | <span data-ttu-id="810cb-161">Object size, not including the size of any referenced objects.</span><span class="sxs-lookup"><span data-stu-id="810cb-161">Object size, not including the size of any referenced objects.</span></span>
<span data-ttu-id="810cb-162">Retained size</span><span class="sxs-lookup"><span data-stu-id="810cb-162">Retained size</span></span> | <span data-ttu-id="810cb-163">Object size plus the size of all child objects that have no other parents.</span><span class="sxs-lookup"><span data-stu-id="810cb-163">Object size plus the size of all child objects that have no other parents.</span></span> <span data-ttu-id="810cb-164">For practical purposes, this is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span><span class="sxs-lookup"><span data-stu-id="810cb-164">For practical purposes, this is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>
<span data-ttu-id="810cb-165">Count</span><span class="sxs-lookup"><span data-stu-id="810cb-165">Count</span></span> | <span data-ttu-id="810cb-166">Number of object instances.</span><span class="sxs-lookup"><span data-stu-id="810cb-166">Number of object instances.</span></span> <span data-ttu-id="810cb-167">This value appears only in the Types view.</span><span class="sxs-lookup"><span data-stu-id="810cb-167">This value appears only in the Types view.</span></span>

<span data-ttu-id="810cb-168">When you select an object in the upper *Dominators* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span><span class="sxs-lookup"><span data-stu-id="810cb-168">When you select an object in the upper *Dominators* pane, the [Object references](#object-references) table in the lower pane will list all the objects that point to that object.</span></span>

### <span data-ttu-id="810cb-169">Filters</span><span class="sxs-lookup"><span data-stu-id="810cb-169">Filters</span></span>

<span data-ttu-id="810cb-170">You can further adjust data in the table with the following:</span><span class="sxs-lookup"><span data-stu-id="810cb-170">You can further adjust data in the table with the following:</span></span>

![Filter for built-ins and object IDs](./media/memory_filter.png)

1. <span data-ttu-id="810cb-172">**Identifier filter**: Filter out data by searching for a particular object identifier</span><span class="sxs-lookup"><span data-stu-id="810cb-172">**Identifier filter**: Filter out data by searching for a particular object identifier</span></span>
2. <span data-ttu-id="810cb-173">**Group by dominator**: Only objects with *exclusive* references to other objects are shown in the top-level view of objects (this is the default view in the *Dominators* tab).</span><span class="sxs-lookup"><span data-stu-id="810cb-173">**Group by dominator**: Only objects with *exclusive* references to other objects are shown in the top-level view of objects (this is the default view in the *Dominators* tab).</span></span>
3. <span data-ttu-id="810cb-174">**Built-ins / IDs filter**: By default, [JavaScript built-in objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) are included in the list.</span><span class="sxs-lookup"><span data-stu-id="810cb-174">**Built-ins / IDs filter**: By default, [JavaScript built-in objects](https://developer.mozilla.org/docs/Web/JavaScript/Reference/Global_Objects) are included in the list.</span></span> <span data-ttu-id="810cb-175">Listing object IDs can be useful if there are multiple anonymous objects which need to be differentiated.</span><span class="sxs-lookup"><span data-stu-id="810cb-175">Listing object IDs can be useful if there are multiple anonymous objects which need to be differentiated.</span></span>

<span data-ttu-id="810cb-176">The *Types, Roots* and *Dominators* views each has its own filter, so the filter isn't preserved when you switch to another view.</span><span class="sxs-lookup"><span data-stu-id="810cb-176">The *Types, Roots* and *Dominators* views each has its own filter, so the filter isn't preserved when you switch to another view.</span></span>

### <span data-ttu-id="810cb-177">Object references</span><span class="sxs-lookup"><span data-stu-id="810cb-177">Object references</span></span>

<span data-ttu-id="810cb-178">In the [**Types**](#types) and [**Dominators**](#dominators) views, the lower pane contains an **Object references** list that displays shared references.</span><span class="sxs-lookup"><span data-stu-id="810cb-178">In the [**Types**](#types) and [**Dominators**](#dominators) views, the lower pane contains an **Object references** list that displays shared references.</span></span> <span data-ttu-id="810cb-179">When you choose an object in the upper pane, this list displays all objects that point to that object--in other words, the objects that are keeping the selected object alive.</span><span class="sxs-lookup"><span data-stu-id="810cb-179">When you choose an object in the upper pane, this list displays all objects that point to that object--in other words, the objects that are keeping the selected object alive.</span></span>

<span data-ttu-id="810cb-180">Circular references are shown with an asterisk (\*) and informational tooltip, and cannot be expanded.</span><span class="sxs-lookup"><span data-stu-id="810cb-180">Circular references are shown with an asterisk (\*) and informational tooltip, and cannot be expanded.</span></span> <span data-ttu-id="810cb-181">Otherwise, they would prevent you from walking up the reference tree and identifying objects that are retaining memory.</span><span class="sxs-lookup"><span data-stu-id="810cb-181">Otherwise, they would prevent you from walking up the reference tree and identifying objects that are retaining memory.</span></span>

<span data-ttu-id="810cb-182">To quickly identify equivalent objects, tick the [*Display object IDs*](#filters) filter option to display object IDs next to object names in the *Identifier(s)* column.</span><span class="sxs-lookup"><span data-stu-id="810cb-182">To quickly identify equivalent objects, tick the [*Display object IDs*](#filters) filter option to display object IDs next to object names in the *Identifier(s)* column.</span></span> <span data-ttu-id="810cb-183">Objects that have the same ID are shared references.</span><span class="sxs-lookup"><span data-stu-id="810cb-183">Objects that have the same ID are shared references.</span></span>

### <span data-ttu-id="810cb-184">Snapshot comparison</span><span class="sxs-lookup"><span data-stu-id="810cb-184">Snapshot comparison</span></span>

<span data-ttu-id="810cb-185">Clicking on a [snapshot comparison tab](#snapshot-details) or comparison link on the [snapshot summary tile](#snapshot-summary)  will show a diff of information between the two snapshots.</span><span class="sxs-lookup"><span data-stu-id="810cb-185">Clicking on a [snapshot comparison tab](#snapshot-details) or comparison link on the [snapshot summary tile](#snapshot-summary)  will show a diff of information between the two snapshots.</span></span> <span data-ttu-id="810cb-186">In the comparison pane, the *Dominators, Types* and *Roots* views provide the same [*snapshot details*](#snapshot-details) you would see for a single snapshots, with these additional values:</span><span class="sxs-lookup"><span data-stu-id="810cb-186">In the comparison pane, the *Dominators, Types* and *Roots* views provide the same [*snapshot details*](#snapshot-details) you would see for a single snapshots, with these additional values:</span></span>

<span data-ttu-id="810cb-187">Column</span><span class="sxs-lookup"><span data-stu-id="810cb-187">Column</span></span> | <span data-ttu-id="810cb-188">Description</span><span class="sxs-lookup"><span data-stu-id="810cb-188">Description</span></span>
:------------ | :-------------
<span data-ttu-id="810cb-189">Size diff.</span><span class="sxs-lookup"><span data-stu-id="810cb-189">Size diff.</span></span> | <span data-ttu-id="810cb-190">Difference between the size of the object in the current snapshot and its size in the previous snapshot, not including the size of any referenced objects.</span><span class="sxs-lookup"><span data-stu-id="810cb-190">Difference between the size of the object in the current snapshot and its size in the previous snapshot, not including the size of any referenced objects.</span></span>
<span data-ttu-id="810cb-191">Retained size diff.</span><span class="sxs-lookup"><span data-stu-id="810cb-191">Retained size diff.</span></span> | <span data-ttu-id="810cb-192">Difference between the retained size of the object in the current snapshot and its retained size in the previous snapshot.</span><span class="sxs-lookup"><span data-stu-id="810cb-192">Difference between the retained size of the object in the current snapshot and its retained size in the previous snapshot.</span></span> <span data-ttu-id="810cb-193">The retained size includes the object size plus the size of all its child objects that have no other parents.</span><span class="sxs-lookup"><span data-stu-id="810cb-193">The retained size includes the object size plus the size of all its child objects that have no other parents.</span></span> <span data-ttu-id="810cb-194">For practical purposes, the retained size is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span><span class="sxs-lookup"><span data-stu-id="810cb-194">For practical purposes, the retained size is the amount of memory retained by the object, so if you delete the object you reclaim the specified amount of memory.</span></span>

<span data-ttu-id="810cb-195">You can use the **Scope** dropdown to filter differential info between snapshots:</span><span class="sxs-lookup"><span data-stu-id="810cb-195">You can use the **Scope** dropdown to filter differential info between snapshots:</span></span>

![Scoping filter for snapshot comparisions](./media/memory_comparison_scope_filter.png)

- <strong><span data-ttu-id="810cb-197">Objects left over from Snapshot #<number></strong>: Shows the diff between the objects added to the heap and removed from the heap from the baseline snapshot to the previous snapshot.</span><span class="sxs-lookup"><span data-stu-id="810cb-197">Objects left over from Snapshot #<number></strong>: Shows the diff between the objects added to the heap and removed from the heap from the baseline snapshot to the previous snapshot.</span></span> <span data-ttu-id="810cb-198">For example, if the snapshot summary shows <em>+205 / -195</em> in the object count, this filter will show you the ten objects that were added but not removed.</span><span class="sxs-lookup"><span data-stu-id="810cb-198">For example, if the snapshot summary shows <em>+205 / -195</em> in the object count, this filter will show you the ten objects that were added but not removed.</span></span>

- <strong><span data-ttu-id="810cb-199">Objects added between Snapshot #<number> and #<number></strong>: Shows all objects added to the heap from the previous snapshot.</span><span class="sxs-lookup"><span data-stu-id="810cb-199">Objects added between Snapshot #<number> and #<number></strong>: Shows all objects added to the heap from the previous snapshot.</span></span>

- <strong><span data-ttu-id="810cb-200">All objects in Snapshot #<number></strong>: Shows all objects on the heap (in other words, an <em>unfiltered</em> view).</span><span class="sxs-lookup"><span data-stu-id="810cb-200">All objects in Snapshot #<number></strong>: Shows all objects on the heap (in other words, an <em>unfiltered</em> view).</span></span>

<span data-ttu-id="810cb-201">By default, the *Show non-matching references* filter is applied to the comparison view to indicate object references that don't match the current Scope filter.</span><span class="sxs-lookup"><span data-stu-id="810cb-201">By default, the *Show non-matching references* filter is applied to the comparison view to indicate object references that don't match the current Scope filter.</span></span> <span data-ttu-id="810cb-202">You can turn it off from the dropdown menu:</span><span class="sxs-lookup"><span data-stu-id="810cb-202">You can turn it off from the dropdown menu:</span></span>

![Non-matching references filter for snapshot comparisons](./media/memory_comparison_matching_filter.png)


## <span data-ttu-id="810cb-204">Shortcuts</span><span class="sxs-lookup"><span data-stu-id="810cb-204">Shortcuts</span></span>

 <span data-ttu-id="810cb-205">Action</span><span class="sxs-lookup"><span data-stu-id="810cb-205">Action</span></span> | <span data-ttu-id="810cb-206">Shortcut</span><span class="sxs-lookup"><span data-stu-id="810cb-206">Shortcut</span></span>
:------------ | :-------------
<span data-ttu-id="810cb-207">Start / Stop profiling session</span><span class="sxs-lookup"><span data-stu-id="810cb-207">Start / Stop profiling session</span></span>  | `Ctrl` + `E`
<span data-ttu-id="810cb-208">Import profiling session</span><span class="sxs-lookup"><span data-stu-id="810cb-208">Import profiling session</span></span> | `Ctrl` + `O`
<span data-ttu-id="810cb-209">Export profiling session</span><span class="sxs-lookup"><span data-stu-id="810cb-209">Export profiling session</span></span> | `Ctrl` + `S`
<span data-ttu-id="810cb-210">Take heap snapshot</span><span class="sxs-lookup"><span data-stu-id="810cb-210">Take heap snapshot</span></span> | `Ctrl` + `Shift` + `T`

## <span data-ttu-id="810cb-211">Known Issues</span><span class="sxs-lookup"><span data-stu-id="810cb-211">Known Issues</span></span>

### <span data-ttu-id="810cb-212">An error occurred while starting the profiling session</span><span class="sxs-lookup"><span data-stu-id="810cb-212">An error occurred while starting the profiling session</span></span>

<span data-ttu-id="810cb-213">If you see this error message: **An error occurred while starting the profiling session** in the Memory tool, follow these steps for a workaround.</span><span class="sxs-lookup"><span data-stu-id="810cb-213">If you see this error message: **An error occurred while starting the profiling session** in the Memory tool, follow these steps for a workaround.</span></span>

1. <span data-ttu-id="810cb-214">Press `Windows Key` + `R`.</span><span class="sxs-lookup"><span data-stu-id="810cb-214">Press `Windows Key` + `R`.</span></span>

2. <span data-ttu-id="810cb-215">In the Run dialog, enter **services.msc**.</span><span class="sxs-lookup"><span data-stu-id="810cb-215">In the Run dialog, enter **services.msc**.</span></span>
![known-issues-1](./media/known_issues_1.PNG)

3. <span data-ttu-id="810cb-217">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span><span class="sxs-lookup"><span data-stu-id="810cb-217">Locate the **Microsoft (R) Diagnostics Hub Standard Collector Service** and right-click it.</span></span>
![known-issues-2](./media/known_issues_2.PNG)

4. <span data-ttu-id="810cb-219">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span><span class="sxs-lookup"><span data-stu-id="810cb-219">Restart the **Microsoft (R) Diagnostics Hub Standard Collector Service**.</span></span>
![known-issues-3](./media/known_issues_3.PNG)

5. <span data-ttu-id="810cb-221">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span><span class="sxs-lookup"><span data-stu-id="810cb-221">Close the Microsoft Edge Developer Tools and the tab. Open a new tab, navigate to your page, and press `F12`.</span></span>

6. <span data-ttu-id="810cb-222">You should now be able to begin profiling.</span><span class="sxs-lookup"><span data-stu-id="810cb-222">You should now be able to begin profiling.</span></span> 
![known-issues-4](./media/known_issues_4-memory.PNG)

<span data-ttu-id="810cb-224">Still running into problems?</span><span class="sxs-lookup"><span data-stu-id="810cb-224">Still running into problems?</span></span> <span data-ttu-id="810cb-225">Please send us your feedback using the **Send feedback** icon!</span><span class="sxs-lookup"><span data-stu-id="810cb-225">Please send us your feedback using the **Send feedback** icon!</span></span> 

![known-issues-5](./media/known_issues_5.PNG)
