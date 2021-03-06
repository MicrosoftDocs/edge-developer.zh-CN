---
description: 了解如何使用 Microsoft Edge DevTools 堆探查器记录堆快照并查找内存泄漏。
title: 如何记录堆快照
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: ce7a6f972bed386f96312808428bd74f1241668f
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397802"
---
<!-- Copyright Meggin Kearney 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->

# <a name="how-to-record-heap-snapshots"></a><span data-ttu-id="940c6-104">如何记录堆快照</span><span class="sxs-lookup"><span data-stu-id="940c6-104">How to record heap snapshots</span></span>  

<span data-ttu-id="940c6-105">了解如何使用 Microsoft Edge DevTools 堆探查器记录堆快照并查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="940c6-105">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="940c6-106">Microsoft Edge DevTools 堆探查器显示页面的 JavaScript 对象和相关 DOM 节点的内存分布。</span><span class="sxs-lookup"><span data-stu-id="940c6-106">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="940c6-107">使用它获取 JavaScript 堆 \ (JS 堆\) 快照、分析内存图、比较快照和查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="940c6-107">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="940c6-108">导航到 [对象保留树][DevtoolsMemoryProblems101ObjectsRetainingTree]。</span><span class="sxs-lookup"><span data-stu-id="940c6-108">Navigate to [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <a name="take-a-snapshot"></a><span data-ttu-id="940c6-109">拍摄快照</span><span class="sxs-lookup"><span data-stu-id="940c6-109">Take a snapshot</span></span>  

<span data-ttu-id="940c6-110">在"**内存"** 面板上，选择 **"拍摄快照"，** 然后选择"**开始"。**</span><span class="sxs-lookup"><span data-stu-id="940c6-110">On the **Memory** panel, choose **Take snapshot**, then choose **Start**.</span></span>  <span data-ttu-id="940c6-111">还可以选择 `Ctrl` + `E` \ (Windows、Linux\) `Cmd` + `E` 或 \ (macOS\) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-111">You may also select `Ctrl`+`E` \(Windows, Linux\) or `Cmd`+`E` \(macOS\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="选择分析类型" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   <span data-ttu-id="940c6-113">选择分析类型</span><span class="sxs-lookup"><span data-stu-id="940c6-113">Choose profiling type</span></span>  
:::image-end:::  

<span data-ttu-id="940c6-114">**快照** 最初存储在呈现器进程内存中。</span><span class="sxs-lookup"><span data-stu-id="940c6-114">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="940c6-115">当你选择在快照图标上查看快照时，快照会按需传输到 DevTools。</span><span class="sxs-lookup"><span data-stu-id="940c6-115">Snapshots are transferred to the DevTools on demand, when you choose on the snapshot icon to view it.</span></span>  

<span data-ttu-id="940c6-116">将快照加载到 DevTools 中并进行分析后，将显示快照标题下方的数字，并显示可到达 [的 JavaScript 对象的总大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="940c6-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="可到达对象的总大小" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   <span data-ttu-id="940c6-118">可到达对象的总大小</span><span class="sxs-lookup"><span data-stu-id="940c6-118">Total size of reachable objects</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="940c6-119">快照中仅包含可到达的对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-119">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="940c6-120">此外，拍摄快照始终从垃圾回收开始。</span><span class="sxs-lookup"><span data-stu-id="940c6-120">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <a name="clear-snapshots"></a><span data-ttu-id="940c6-121">清除快照</span><span class="sxs-lookup"><span data-stu-id="940c6-121">Clear snapshots</span></span>  

<span data-ttu-id="940c6-122">选择 **"清除所有配置文件** "图标 (从 DevTools 和与呈现器进程关联的任何内存中删除快照 \) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-122">Choose **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="删除快照" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   <span data-ttu-id="940c6-124">删除快照</span><span class="sxs-lookup"><span data-stu-id="940c6-124">Remove snapshots</span></span>  
:::image-end:::  

<span data-ttu-id="940c6-125">关闭 DevTools 窗口不会从与呈现器进程关联的内存中删除配置文件。</span><span class="sxs-lookup"><span data-stu-id="940c6-125">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="940c6-126">重新打开 DevTools 时，以前拍摄的所有快照都重新出现于快照列表中。</span><span class="sxs-lookup"><span data-stu-id="940c6-126">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="940c6-127">试用该散 [点对象示例，][GlitchDevtoolsMemoryExample03] 然后使用堆配置文件器进行配置文件。</span><span class="sxs-lookup"><span data-stu-id="940c6-127">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="940c6-128">将显示许多 \ (对象\) 项分配。</span><span class="sxs-lookup"><span data-stu-id="940c6-128">A number of \(object\) item allocations are displayed.</span></span>  

## <a name="view-snapshots"></a><span data-ttu-id="940c6-129">查看快照</span><span class="sxs-lookup"><span data-stu-id="940c6-129">View snapshots</span></span>  

<span data-ttu-id="940c6-130">从不同的角度查看不同任务的快照。</span><span class="sxs-lookup"><span data-stu-id="940c6-130">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="940c6-131">**摘要视图** 显示按构造函数名称分组的对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-131">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="940c6-132">使用它根据按构造函数名称 (类型来搜寻对象 \ (和内存使用\) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-132">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="940c6-133">它对于跟踪 **DOM 泄露尤其有用**。</span><span class="sxs-lookup"><span data-stu-id="940c6-133">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="940c6-134">**比较视图**。</span><span class="sxs-lookup"><span data-stu-id="940c6-134">**Comparison view**.</span></span>  <span data-ttu-id="940c6-135">显示两个快照的区别。</span><span class="sxs-lookup"><span data-stu-id="940c6-135">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="940c6-136">使用它来比较两个 \ (或多个\) 操作之前和之后的内存快照。</span><span class="sxs-lookup"><span data-stu-id="940c6-136">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="940c6-137">通过检查释放的内存和引用计数中的增量，可以确认内存泄漏的存在和原因。</span><span class="sxs-lookup"><span data-stu-id="940c6-137">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="940c6-138">**包含视图**。</span><span class="sxs-lookup"><span data-stu-id="940c6-138">**Containment view**.</span></span>  <span data-ttu-id="940c6-139">允许浏览堆内容。</span><span class="sxs-lookup"><span data-stu-id="940c6-139">Allows exploration of heap contents.</span></span>  <span data-ttu-id="940c6-140">**包含视图** 提供更好的对象结构视图，帮助分析全局命名空间 \ (window\) 中引用的对象，以找出对象周围的内容。</span><span class="sxs-lookup"><span data-stu-id="940c6-140">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="940c6-141">使用它来分析关闭，并深入到较低级别的对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-141">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="940c6-142">若要在视图之间切换，请使用视图顶部的选择器。</span><span class="sxs-lookup"><span data-stu-id="940c6-142">To switch between views, use the selector at the top of the view.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="切换视图选择器" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   <span data-ttu-id="940c6-144">切换视图选择器</span><span class="sxs-lookup"><span data-stu-id="940c6-144">Switch views selector</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="940c6-145">并非所有属性都存储在 JavaScript 堆上。</span><span class="sxs-lookup"><span data-stu-id="940c6-145">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="940c6-146">不会捕获使用运行本机代码的 getter 实现的属性。</span><span class="sxs-lookup"><span data-stu-id="940c6-146">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="940c6-147">此外，不会捕获数字等非字符串值。</span><span class="sxs-lookup"><span data-stu-id="940c6-147">Also, non-string values such as numbers are not captured.</span></span>  

### <a name="summary-view"></a><span data-ttu-id="940c6-148">摘要视图</span><span class="sxs-lookup"><span data-stu-id="940c6-148">Summary view</span></span>  

<span data-ttu-id="940c6-149">最初，快照在"摘要"视图中打开，并显示对象总数，可以展开此快照以显示实例：</span><span class="sxs-lookup"><span data-stu-id="940c6-149">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="摘要视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   <span data-ttu-id="940c6-151">**摘要** 视图</span><span class="sxs-lookup"><span data-stu-id="940c6-151">**Summary** view</span></span>  
:::image-end:::  

<span data-ttu-id="940c6-152">顶级条目是"total"行。</span><span class="sxs-lookup"><span data-stu-id="940c6-152">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="940c6-153">顶级条目</span><span class="sxs-lookup"><span data-stu-id="940c6-153">Top-level entries</span></span> | <span data-ttu-id="940c6-154">说明</span><span class="sxs-lookup"><span data-stu-id="940c6-154">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="940c6-155">构造函数</span><span class="sxs-lookup"><span data-stu-id="940c6-155">Constructor</span></span>** | <span data-ttu-id="940c6-156">表示使用此构造函数创建的所有对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-156">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="940c6-157">距离</span><span class="sxs-lookup"><span data-stu-id="940c6-157">Distance</span></span>** | <span data-ttu-id="940c6-158">使用节点的最短简单路径显示与根之间的距离。</span><span class="sxs-lookup"><span data-stu-id="940c6-158">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="940c6-159">浅表大小</span><span class="sxs-lookup"><span data-stu-id="940c6-159">Shallow size</span></span>** | <span data-ttu-id="940c6-160">显示由特定构造函数函数创建的所有对象的浅表大小的总和。</span><span class="sxs-lookup"><span data-stu-id="940c6-160">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="940c6-161">浅表大小是对象 \ (通常具有较大的浅表大小\) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-161">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="940c6-162">导航到 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="940c6-162">Navigate to [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="940c6-163">保留大小</span><span class="sxs-lookup"><span data-stu-id="940c6-163">Retained size</span></span>** | <span data-ttu-id="940c6-164">显示同一组对象中保留的最大大小。</span><span class="sxs-lookup"><span data-stu-id="940c6-164">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="940c6-165">删除对象 \ (且从属项不再可用\) 后可以释放的内存大小称为保留大小。</span><span class="sxs-lookup"><span data-stu-id="940c6-165">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="940c6-166">导航到 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="940c6-166">Navigate to [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="940c6-167">展开上视图中的总行后，将显示所有实例。</span><span class="sxs-lookup"><span data-stu-id="940c6-167">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="940c6-168">对于每个实例，浅表和保留的大小显示在相应的列中。</span><span class="sxs-lookup"><span data-stu-id="940c6-168">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="940c6-169">字符后的编号是对象的唯一 ID，允许您基于每个对象比较堆 `@` 快照。</span><span class="sxs-lookup"><span data-stu-id="940c6-169">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="940c6-170">请记住，黄色对象具有 JavaScript 引用，红色对象是从具有黄色背景的节点引用的分离节点。</span><span class="sxs-lookup"><span data-stu-id="940c6-170">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="940c6-171">堆配置文件器中的各种构造函数 \ (group\) 条目对应什么？</span><span class="sxs-lookup"><span data-stu-id="940c6-171">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="构造函数组" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   <span data-ttu-id="940c6-173">**构造函数** 组</span><span class="sxs-lookup"><span data-stu-id="940c6-173">**Constructor** groups</span></span>  
:::image-end:::  

| <span data-ttu-id="940c6-174">构造函数 \ (group\) 条目</span><span class="sxs-lookup"><span data-stu-id="940c6-174">Constructor \(group\) entry</span></span> | <span data-ttu-id="940c6-175">说明</span><span class="sxs-lookup"><span data-stu-id="940c6-175">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="940c6-176">\ (global 属性\) </span><span class="sxs-lookup"><span data-stu-id="940c6-176">\(global property\)</span></span>** | <span data-ttu-id="940c6-177">全局对象 \ (\) 和它引用的对象之间的中间 `window` 对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-177">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="940c6-178">如果使用构造函数创建对象并且由全局对象保留，则保留路径可以 `Person` 表示为 `[global] > \(global property\) > Person` 。</span><span class="sxs-lookup"><span data-stu-id="940c6-178">If an object is created using a constructor `Person` and is held by a global object, the retaining path may be represented as `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="940c6-179">这与对象直接相互引用的规范相反。</span><span class="sxs-lookup"><span data-stu-id="940c6-179">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="940c6-180">中间对象出于性能原因存在。</span><span class="sxs-lookup"><span data-stu-id="940c6-180">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="940c6-181">会定期修改全局设置，并且属性访问优化对非全局对象来说效果良好，而不适用于全局对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-181">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="940c6-182">\ (根\) </span><span class="sxs-lookup"><span data-stu-id="940c6-182">\(roots\)</span></span>** | <span data-ttu-id="940c6-183">保留树视图中的根条目是引用所选对象的实体。</span><span class="sxs-lookup"><span data-stu-id="940c6-183">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="940c6-184">这些条目可能也是引擎为特定于引擎而创建的引用。</span><span class="sxs-lookup"><span data-stu-id="940c6-184">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="940c6-185">引擎具有缓存哪些引用对象，但所有此类引用都是弱引用，并且不会阻止在不存在真正强大的引用时收集对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-185">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="940c6-186">\ (关闭\) </span><span class="sxs-lookup"><span data-stu-id="940c6-186">\(closure\)</span></span>** | <span data-ttu-id="940c6-187">通过函数关闭对一组对象的引用计数。</span><span class="sxs-lookup"><span data-stu-id="940c6-187">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="940c6-188">\ (数组、字符串、数字、regexp\) </span><span class="sxs-lookup"><span data-stu-id="940c6-188">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="940c6-189">具有引用数组、字符串、数字或正则表达式的属性的对象类型列表。</span><span class="sxs-lookup"><span data-stu-id="940c6-189">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="940c6-190">\ (编译的代码\) </span><span class="sxs-lookup"><span data-stu-id="940c6-190">\(compiled code\)</span></span>** | <span data-ttu-id="940c6-191">与已编译代码相关的一切内容。</span><span class="sxs-lookup"><span data-stu-id="940c6-191">Everything related to compiled code.</span></span>  <span data-ttu-id="940c6-192">脚本类似于函数，但对应于 `<script>` 正文。</span><span class="sxs-lookup"><span data-stu-id="940c6-192">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="940c6-193">SharedFunctionInfos \ (SFI\) 是位于函数和已编译代码之间的对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-193">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="940c6-194">函数通常具有上下文，而 SFIS 则没有上下文。</span><span class="sxs-lookup"><span data-stu-id="940c6-194">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="940c6-195">\*\*\*\* HTMLDivElement、HTMLAnchorElement、DocumentFragment 等。 \*\*\*\* \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="940c6-195">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="940c6-196">对代码引用的某一特定类型元素或文档对象的引用。</span><span class="sxs-lookup"><span data-stu-id="940c6-196">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <a name="comparison-view"></a><span data-ttu-id="940c6-197">比较视图</span><span class="sxs-lookup"><span data-stu-id="940c6-197">Comparison view</span></span>  

<span data-ttu-id="940c6-198">通过将多个快照相互比较来查找泄漏的对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-198">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="940c6-199">若要验证特定应用程序操作不会创建泄漏 \ (例如，通常一对直接和反向操作（如打开文档，然后关闭文档）不应留下任何垃圾\) ，您可以遵循以下方案：</span><span class="sxs-lookup"><span data-stu-id="940c6-199">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="940c6-200">在操作之前拍摄堆快照。</span><span class="sxs-lookup"><span data-stu-id="940c6-200">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="940c6-201">执行一个操作 \ (以你认为会导致泄露的方式与页面交互) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-201">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="940c6-202">执行反向操作 \ (执行相反的交互并重复几次\) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-202">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="940c6-203">拍摄第二个堆快照，将此堆栈的视图更改为 **"比较**"，将它与快照 **1 进行比较**。</span><span class="sxs-lookup"><span data-stu-id="940c6-203">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  
    
<span data-ttu-id="940c6-204">在 **"比较** "视图中，将显示两个快照之间的差值。</span><span class="sxs-lookup"><span data-stu-id="940c6-204">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="940c6-205">展开总条目时，将显示添加和删除的对象实例。</span><span class="sxs-lookup"><span data-stu-id="940c6-205">When expanding a total entry, added and deleted object instances are shown.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比较视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   <span data-ttu-id="940c6-207">**比较** 视图</span><span class="sxs-lookup"><span data-stu-id="940c6-207">**Comparison** view</span></span>  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <a name="containment-view"></a><span data-ttu-id="940c6-208">包含视图</span><span class="sxs-lookup"><span data-stu-id="940c6-208">Containment view</span></span>  

<span data-ttu-id="940c6-209">包含 **视图** 实质上是应用程序的对象结构的"鸟瞰图"。</span><span class="sxs-lookup"><span data-stu-id="940c6-209">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="940c6-210">它允许你查看函数关闭，观察虚拟机 \ (VM\) 内部对象，这些内部对象共同组合 JavaScript 对象，并了解应用程序在非常低的级别使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="940c6-210">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="940c6-211">包含视图入口点</span><span class="sxs-lookup"><span data-stu-id="940c6-211">Containment view entry points</span></span> | <span data-ttu-id="940c6-212">说明</span><span class="sxs-lookup"><span data-stu-id="940c6-212">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="940c6-213">DOMWindow 对象</span><span class="sxs-lookup"><span data-stu-id="940c6-213">DOMWindow objects</span></span>** | <span data-ttu-id="940c6-214">JavaScript 代码的全局对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-214">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="940c6-215">GC 根目录</span><span class="sxs-lookup"><span data-stu-id="940c6-215">GC roots</span></span>** | <span data-ttu-id="940c6-216">VM 的垃圾回收使用的实际 GC 根。</span><span class="sxs-lookup"><span data-stu-id="940c6-216">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="940c6-217">GC 根由内置对象映射、符号表、VM 线程堆栈、编译缓存、处理范围和全局句柄组成。</span><span class="sxs-lookup"><span data-stu-id="940c6-217">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="940c6-218">本机对象</span><span class="sxs-lookup"><span data-stu-id="940c6-218">Native objects</span></span>** | <span data-ttu-id="940c6-219">JavaScript 虚拟机 \ (JavaScript VM\) 内"推送"的浏览器对象允许自动化，例如 DOM 节点、CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="940c6-219">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="包含视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   <span data-ttu-id="940c6-221">**包含** 视图</span><span class="sxs-lookup"><span data-stu-id="940c6-221">**Containment** view</span></span>  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="940c6-222">有关关闭的提示。</span><span class="sxs-lookup"><span data-stu-id="940c6-222">A tip about closures.</span></span>  <span data-ttu-id="940c6-223">命名函数，以便你可以轻松区分快照中的关闭。</span><span class="sxs-lookup"><span data-stu-id="940c6-223">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="940c6-224">例如，此示例不使用命名函数。</span><span class="sxs-lookup"><span data-stu-id="940c6-224">For example, this example does not use named functions.</span></span>  
> 
> ```javascript
> function createLargeClosure() {
>     var largeStr = new Array(1000000).join('x');
>     var lC = function() { // this is NOT a named function
>         return largeStr;
>     };
>     return lC;
> }
> ```  
> 
> <span data-ttu-id="940c6-225">以下代码段使用命名函数。</span><span class="sxs-lookup"><span data-stu-id="940c6-225">The followingcode snippet uses named functions.</span></span>  
> 
> ```javascript
> function createLargeClosure() {
>     var largeStr = new Array(1000000).join('x');
>     var lC = function lC() { // this IS a named function
>         return largeStr;
>     };
>     return lC;
> }
> ```  
> 
> <!--  
> :::image type="complex" source="../media/memory-problems-domleaks.msft.png" alt-text="Name functions to distinguish between closures" lightbox="../media/memory-problems-domleaks.msft.png":::
>    Name functions to distinguish between closures  
> :::image-end:::  
> -->  
> 
> > [!NOTE]
> > <span data-ttu-id="940c6-226">尝试此示例， [了解 `eval` ][GlitchDevtoolsMemoryExample07] 为什么分析关闭对内存的影响是一种尝试。</span><span class="sxs-lookup"><span data-stu-id="940c6-226">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="940c6-227">你可能还有兴趣通过此示例跟踪它，该示例将记录 [堆分配][GlitchDevtoolsMemoryExample08]。</span><span class="sxs-lookup"><span data-stu-id="940c6-227">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <a name="look-up-color-coding"></a><span data-ttu-id="940c6-228">查找颜色编码</span><span class="sxs-lookup"><span data-stu-id="940c6-228">Look up color coding</span></span>  

<span data-ttu-id="940c6-229">对象的属性和属性值具有不同的类型，并相应地着色。</span><span class="sxs-lookup"><span data-stu-id="940c6-229">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="940c6-230">每个属性有四种类型之一。</span><span class="sxs-lookup"><span data-stu-id="940c6-230">Each property has one of four types.</span></span>  

| <span data-ttu-id="940c6-231">属性类型</span><span class="sxs-lookup"><span data-stu-id="940c6-231">Property Type</span></span> | <span data-ttu-id="940c6-232">说明</span><span class="sxs-lookup"><span data-stu-id="940c6-232">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="940c6-233">a： 属性</span><span class="sxs-lookup"><span data-stu-id="940c6-233">a: property</span></span>** | <span data-ttu-id="940c6-234">具有名称的常规属性，可通过 `.` \ (dot\) 运算符或通过 `[` `]` \ (brackets\) 表示 `["foo bar"]` 法访问。</span><span class="sxs-lookup"><span data-stu-id="940c6-234">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="940c6-235">0：元素</span><span class="sxs-lookup"><span data-stu-id="940c6-235">0: element</span></span>** | <span data-ttu-id="940c6-236">具有数值索引的常规属性， `[` `]` 可通过 \ (方括号\) 表示法访问。</span><span class="sxs-lookup"><span data-stu-id="940c6-236">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="940c6-237">a： context var</span><span class="sxs-lookup"><span data-stu-id="940c6-237">a: context var</span></span>** |  <span data-ttu-id="940c6-238">函数上下文中的一个变量，可通过函数关闭内部的变量名称访问。</span><span class="sxs-lookup"><span data-stu-id="940c6-238">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="940c6-239">a：系统属性</span><span class="sxs-lookup"><span data-stu-id="940c6-239">a: system prop</span></span>** | <span data-ttu-id="940c6-240">JavaScript VM 添加的属性，无法通过 JavaScript 代码访问。</span><span class="sxs-lookup"><span data-stu-id="940c6-240">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="940c6-241">指定为对象 `System` 的对象没有相应的 JavaScript 类型。</span><span class="sxs-lookup"><span data-stu-id="940c6-241">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="940c6-242">每个虚拟机都是 Javascript VM 的对象系统实现一部分。</span><span class="sxs-lookup"><span data-stu-id="940c6-242">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="940c6-243">V8 分配与用户的 JS 对象相同的堆中的大多数内部对象。</span><span class="sxs-lookup"><span data-stu-id="940c6-243">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="940c6-244">因此，这些只是 V8 内部。</span><span class="sxs-lookup"><span data-stu-id="940c6-244">So these are just V8 internals.</span></span>  

## <a name="find-a-specific-object"></a><span data-ttu-id="940c6-245">查找特定对象</span><span class="sxs-lookup"><span data-stu-id="940c6-245">Find a specific object</span></span>  

<span data-ttu-id="940c6-246">若要在收集的堆中查找对象，可以使用搜索并 `Ctrl` + `F` 给出对象 ID。</span><span class="sxs-lookup"><span data-stu-id="940c6-246">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <a name="uncover-dom-leaks"></a><span data-ttu-id="940c6-247">发现 DOM 泄露</span><span class="sxs-lookup"><span data-stu-id="940c6-247">Uncover DOM leaks</span></span>  

<span data-ttu-id="940c6-248">堆探查器能够反映浏览器本机对象 \ (DOM 节点、CSS 规则\) 和 JavaScript 对象之间的双向依赖关系。</span><span class="sxs-lookup"><span data-stu-id="940c6-248">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="940c6-249">这有助于发现因忘记分离的 DOM 子树四处浮动而发生的不可见泄露。</span><span class="sxs-lookup"><span data-stu-id="940c6-249">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="940c6-250">DOM 泄露可能大于您想象中。</span><span class="sxs-lookup"><span data-stu-id="940c6-250">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="940c6-251">请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="940c6-251">Consider the following sample.</span></span>  <span data-ttu-id="940c6-252">何时是#tree GC？</span><span class="sxs-lookup"><span data-stu-id="940c6-252">When is the #tree GC?</span></span>  

```javascript
var select = document.querySelector;
var treeRef = select("#tree");
var leafRef = select("#leaf");
var body = select("body");
body.removeChild(treeRef);
//#tree in not GC yet due to treeRef
treeRef = null;
//#tree is not GC yet due to indirect
//reference from leafRef
leafRef = null;
//#NOW able to be #tree GC
```  

<span data-ttu-id="940c6-253">保留对相关父 `#leaf` \ (parentNode\) 的引用，并递归到 ，因此仅在 leafRef 为 `#tree` null 时，GC 候选项下的整个树。 `#tree`</span><span class="sxs-lookup"><span data-stu-id="940c6-253">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM 子树" lightbox="../media/memory-problems-tree-gc.msft.png":::
   <span data-ttu-id="940c6-255">DOM 子树</span><span class="sxs-lookup"><span data-stu-id="940c6-255">DOM subtrees</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="940c6-256">示例：尝试该泄露 [DOM][GlitchDevtoolsMemoryExample06] 节点的示例，以了解其可能泄漏在何处以及如何检测它。</span><span class="sxs-lookup"><span data-stu-id="940c6-256">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="940c6-257">您还可以查看 [DOM 泄漏大于预期的示例][GlitchDevtoolsMemoryExample09]。</span><span class="sxs-lookup"><span data-stu-id="940c6-257">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="940c6-258">若要了解有关 DOM 泄漏和内存分析基础内容，请通过 Gonzalo Ruiz de Checkout 查找和调试 [Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] 的内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="940c6-258">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="940c6-259">联系 Microsoft Edge 开发工具团队</span><span class="sxs-lookup"><span data-stu-id="940c6-259">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "对象大小 - 内存术语|Microsoft Docs"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "保留树的对象 - 内存术语|Microsoft Docs"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html - Microsoft Edge (Chromium) DevTools |小故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "内存|幻灯片"  

> [!NOTE]
> <span data-ttu-id="940c6-269">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="940c6-269">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="940c6-270">原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) 由 [Meggin Kearney][MegginKearney] \ (Technical Writer\) 。</span><span class="sxs-lookup"><span data-stu-id="940c6-270">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="940c6-272">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="940c6-272">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
