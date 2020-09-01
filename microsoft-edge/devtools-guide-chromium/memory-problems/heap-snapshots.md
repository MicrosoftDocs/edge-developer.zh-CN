---
title: 如何录制堆快照
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bd46489d8a8a3fddbff60618b4997784294cccff
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985419"
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





# <span data-ttu-id="c989f-103">如何录制堆快照</span><span class="sxs-lookup"><span data-stu-id="c989f-103">How to record heap snapshots</span></span>   



<span data-ttu-id="c989f-104">了解如何将堆快照与 Microsoft Edge DevTools 堆探查器一起录制并查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="c989f-104">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="c989f-105">Microsoft Edge DevTools 堆探查器显示由页面的 JavaScript 对象和相关的 DOM 节点的内存分布。</span><span class="sxs-lookup"><span data-stu-id="c989f-105">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="c989f-106">使用它来获取 JavaScript 堆 \ (JS 堆 \ ) 快照、分析内存图、比较快照和查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="c989f-106">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="c989f-107">另请参阅 [对象保留树][DevtoolsMemoryProblems101ObjectsRetainingTree]。</span><span class="sxs-lookup"><span data-stu-id="c989f-107">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <span data-ttu-id="c989f-108">拍摄快照</span><span class="sxs-lookup"><span data-stu-id="c989f-108">Take a snapshot</span></span>  

<span data-ttu-id="c989f-109">在 " **内存** " 面板上，选择 " **拍摄快照**"，然后单击 " **开始**"。</span><span class="sxs-lookup"><span data-stu-id="c989f-109">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span></span>  <span data-ttu-id="c989f-110">您也可以按 `Ctrl` + `E` \ (Windows \ ) 或 `Cmd` + `E` \ (macOS \ ) 。</span><span class="sxs-lookup"><span data-stu-id="c989f-110">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="选择性能分析类型" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   <span data-ttu-id="c989f-112">选择性能分析类型</span><span class="sxs-lookup"><span data-stu-id="c989f-112">Select profiling type</span></span>  
:::image-end:::  

<span data-ttu-id="c989f-113">**快照** 最初存储在呈现器进程内存中。</span><span class="sxs-lookup"><span data-stu-id="c989f-113">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="c989f-114">当你单击 "快照" 图标进行查看时，快照将按需转到 DevTools。</span><span class="sxs-lookup"><span data-stu-id="c989f-114">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span></span>  

<span data-ttu-id="c989f-115">将快照加载到 DevTools 并进行分析后，将显示快照标题下方的数字，并显示可 [访问的 JavaScript 对象的总大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="c989f-115">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="可访问对象的总大小" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   <span data-ttu-id="c989f-117">可访问对象的总大小</span><span class="sxs-lookup"><span data-stu-id="c989f-117">Total size of reachable objects</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c989f-118">快照中仅包含可访问的对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-118">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="c989f-119">此外，拍摄快照始终从垃圾回收开始。</span><span class="sxs-lookup"><span data-stu-id="c989f-119">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <span data-ttu-id="c989f-120">清除快照</span><span class="sxs-lookup"><span data-stu-id="c989f-120">Clear snapshots</span></span>  

<span data-ttu-id="c989f-121">单击 " **清除所有配置文件** " 图标以从 DevTools 中删除快照 \ (以及与呈现程序进程 \ ) 关联的任何内存。</span><span class="sxs-lookup"><span data-stu-id="c989f-121">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="删除快照" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   <span data-ttu-id="c989f-123">删除快照</span><span class="sxs-lookup"><span data-stu-id="c989f-123">Remove snapshots</span></span>  
:::image-end:::  

<span data-ttu-id="c989f-124">关闭 DevTools 窗口不会删除与呈现程序进程关联的内存中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="c989f-124">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="c989f-125">重新打开 DevTools 时，以前拍摄的所有快照都会重新出现在快照列表中。</span><span class="sxs-lookup"><span data-stu-id="c989f-125">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="c989f-126">请试用 [分散对象][GlitchDevtoolsMemoryExample03] 的示例并使用堆探查器对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="c989f-126">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="c989f-127">你应该会看到大量 (对象 \ ) 项分配。</span><span class="sxs-lookup"><span data-stu-id="c989f-127">You should see a number of \(object\) item allocations.</span></span>  

## <span data-ttu-id="c989f-128">查看快照</span><span class="sxs-lookup"><span data-stu-id="c989f-128">View snapshots</span></span>  

<span data-ttu-id="c989f-129">从不同的视角查看不同任务的快照。</span><span class="sxs-lookup"><span data-stu-id="c989f-129">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="c989f-130">"**摘要" 视图**显示按构造函数名称分组的对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-130">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="c989f-131">使用它来查寻对象 \ (和内存使用 \ ) 基于由构造函数名称分组的类型。</span><span class="sxs-lookup"><span data-stu-id="c989f-131">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="c989f-132">它对于 **跟踪 DOM 泄漏**非常有用。</span><span class="sxs-lookup"><span data-stu-id="c989f-132">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="c989f-133">**比较视图**。</span><span class="sxs-lookup"><span data-stu-id="c989f-133">**Comparison view**.</span></span>  <span data-ttu-id="c989f-134">显示两个快照之间的差异。</span><span class="sxs-lookup"><span data-stu-id="c989f-134">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="c989f-135">使用它比较操作前后的两个 \ (或多个 \ ) 内存快照。</span><span class="sxs-lookup"><span data-stu-id="c989f-135">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="c989f-136">检查已释放的内存和引用计数中的增量可让你确认内存泄漏的存在和原因。</span><span class="sxs-lookup"><span data-stu-id="c989f-136">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="c989f-137">**包含视图**。</span><span class="sxs-lookup"><span data-stu-id="c989f-137">**Containment view**.</span></span>  <span data-ttu-id="c989f-138">允许探索堆内容。</span><span class="sxs-lookup"><span data-stu-id="c989f-138">Allows exploration of heap contents.</span></span>  <span data-ttu-id="c989f-139">"**包容" 视图**提供了更好的对象结构视图，帮助分析全局命名空间 \ (窗口中引用的对象 \ ) ，以了解对象周围的保留对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-139">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="c989f-140">使用它来分析闭包，并以较低的级别深入查看你的对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-140">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="c989f-141">若要在视图之间进行切换，请使用视图顶部的选择器。</span><span class="sxs-lookup"><span data-stu-id="c989f-141">To switch between views, use the selector at the top of the view.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="切换视图选择器" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   <span data-ttu-id="c989f-143">切换视图选择器</span><span class="sxs-lookup"><span data-stu-id="c989f-143">Switch views selector</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c989f-144">并非所有属性都存储在 JavaScript 堆上。</span><span class="sxs-lookup"><span data-stu-id="c989f-144">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="c989f-145">不捕获使用运行本机代码的 getter 实现的属性。</span><span class="sxs-lookup"><span data-stu-id="c989f-145">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="c989f-146">此外，不捕获数字等非字符串值。</span><span class="sxs-lookup"><span data-stu-id="c989f-146">Also, non-string values such as numbers are not captured.</span></span>  

### <span data-ttu-id="c989f-147">摘要视图</span><span class="sxs-lookup"><span data-stu-id="c989f-147">Summary view</span></span>  

<span data-ttu-id="c989f-148">最初，快照在 "摘要" 视图中打开，显示 "对象总数"，它们可能会展开以显示实例：</span><span class="sxs-lookup"><span data-stu-id="c989f-148">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="摘要视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   <span data-ttu-id="c989f-150">摘要视图</span><span class="sxs-lookup"><span data-stu-id="c989f-150">Summary view</span></span>  
:::image-end:::  

<span data-ttu-id="c989f-151">顶级条目是 "汇总" 行。</span><span class="sxs-lookup"><span data-stu-id="c989f-151">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="c989f-152">顶级项</span><span class="sxs-lookup"><span data-stu-id="c989f-152">Top-level entries</span></span> | <span data-ttu-id="c989f-153">描述</span><span class="sxs-lookup"><span data-stu-id="c989f-153">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="c989f-154">构造函数</span><span class="sxs-lookup"><span data-stu-id="c989f-154">Constructor</span></span>** | <span data-ttu-id="c989f-155">表示使用此构造函数创建的所有对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-155">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="c989f-156">距离</span><span class="sxs-lookup"><span data-stu-id="c989f-156">Distance</span></span>** | <span data-ttu-id="c989f-157">使用节点的最短简单路径显示到根的距离。</span><span class="sxs-lookup"><span data-stu-id="c989f-157">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="c989f-158">浅大小</span><span class="sxs-lookup"><span data-stu-id="c989f-158">Shallow size</span></span>** | <span data-ttu-id="c989f-159">显示由特定构造函数创建的所有对象的平坦大小之和。</span><span class="sxs-lookup"><span data-stu-id="c989f-159">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="c989f-160">浅大小是对象所占用的内存大小 (通常情况下，数组和字符串具有较大的浅层大小 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="c989f-160">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="c989f-161">另请参阅 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="c989f-161">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="c989f-162">保留大小</span><span class="sxs-lookup"><span data-stu-id="c989f-162">Retained size</span></span>** | <span data-ttu-id="c989f-163">显示同一组对象中的最大保留大小。</span><span class="sxs-lookup"><span data-stu-id="c989f-163">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="c989f-164">在删除对象后，您可以释放的内存大小 \ (且无法再访问从属单元 ) 称为保留的大小。</span><span class="sxs-lookup"><span data-stu-id="c989f-164">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="c989f-165">另请参阅 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="c989f-165">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="c989f-166">在上部视图中展开 "汇总" 行后，将显示所有实例。</span><span class="sxs-lookup"><span data-stu-id="c989f-166">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="c989f-167">对于每个实例，浅和保留大小都显示在相应的列中。</span><span class="sxs-lookup"><span data-stu-id="c989f-167">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="c989f-168">字符后的数字 `@` 是对象的唯一 ID，使你可以基于每个对象比较堆快照。</span><span class="sxs-lookup"><span data-stu-id="c989f-168">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="c989f-169">请注意，黄色对象具有 JavaScript 引用，红色对象是从一个具有黄色背景的分离节点引用。</span><span class="sxs-lookup"><span data-stu-id="c989f-169">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="c989f-170">堆探查器中的各种构造函数 \ (组 \ ) 条目对应于什么？</span><span class="sxs-lookup"><span data-stu-id="c989f-170">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="构造函数组" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   <span data-ttu-id="c989f-172">构造函数组</span><span class="sxs-lookup"><span data-stu-id="c989f-172">Constructor groups</span></span>  
:::image-end:::  

| <span data-ttu-id="c989f-173">构造函数 \ (组 \ ) 条目</span><span class="sxs-lookup"><span data-stu-id="c989f-173">Constructor \(group\) entry</span></span> | <span data-ttu-id="c989f-174">描述</span><span class="sxs-lookup"><span data-stu-id="c989f-174">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="c989f-175">\ (global 属性 \ ) </span><span class="sxs-lookup"><span data-stu-id="c989f-175">\(global property\)</span></span>** | <span data-ttu-id="c989f-176">全局对象 \ (（如 `window` \ ) 和它引用的对象）之间的中间对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-176">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="c989f-177">如果使用构造函数创建对象 `Person` 并由全局对象持有，则保留路径将如下所示 `[global] > \(global property\) > Person` 。</span><span class="sxs-lookup"><span data-stu-id="c989f-177">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="c989f-178">这与标准进行对比，其中对象直接相互引用。</span><span class="sxs-lookup"><span data-stu-id="c989f-178">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="c989f-179">出于性能原因，存在中间对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-179">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="c989f-180">全局会定期修改全局，并且属性访问优化对非全局对象执行良好的作业不适用于全局对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-180">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="c989f-181">\ (根 \ ) </span><span class="sxs-lookup"><span data-stu-id="c989f-181">\(roots\)</span></span>** | <span data-ttu-id="c989f-182">"保留树" 视图中的根项是引用所选对象的实体。</span><span class="sxs-lookup"><span data-stu-id="c989f-182">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="c989f-183">这些条目也可能是引擎为特定于引擎的目的而创建的引用。</span><span class="sxs-lookup"><span data-stu-id="c989f-183">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="c989f-184">该引擎已缓存哪些引用对象，但所有此类引用都很弱，并且不会阻止收集对象，因为没有真正的强引用。</span><span class="sxs-lookup"><span data-stu-id="c989f-184">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="c989f-185">\ (关闭 ) </span><span class="sxs-lookup"><span data-stu-id="c989f-185">\(closure\)</span></span>** | <span data-ttu-id="c989f-186">通过函数闭包对一组对象的引用的计数。</span><span class="sxs-lookup"><span data-stu-id="c989f-186">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="c989f-187">\ (数组、string、number、regexp \ ) </span><span class="sxs-lookup"><span data-stu-id="c989f-187">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="c989f-188">包含属性的对象类型列表，这些属性引用数组、字符串、数字或正则表达式。</span><span class="sxs-lookup"><span data-stu-id="c989f-188">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="c989f-189">\ (已编译的代码 \ ) </span><span class="sxs-lookup"><span data-stu-id="c989f-189">\(compiled code\)</span></span>** | <span data-ttu-id="c989f-190">与编译的代码相关的所有内容。</span><span class="sxs-lookup"><span data-stu-id="c989f-190">Everything related to compiled code.</span></span>  <span data-ttu-id="c989f-191">脚本类似于函数，但对应于 `<script>` 主体。</span><span class="sxs-lookup"><span data-stu-id="c989f-191">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="c989f-192">SharedFunctionInfos \ (SFI \ ) 是位于函数和编译代码之间的对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-192">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="c989f-193">函数通常具有上下文，而 SFIs 不是。</span><span class="sxs-lookup"><span data-stu-id="c989f-193">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="c989f-194">**HTMLDivElement**、 **HTMLAnchorElement**、 **DocumentFragment**等。</span><span class="sxs-lookup"><span data-stu-id="c989f-194">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="c989f-195">对你的代码引用的特定类型的元素或文档对象的引用。</span><span class="sxs-lookup"><span data-stu-id="c989f-195">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <span data-ttu-id="c989f-196">比较视图</span><span class="sxs-lookup"><span data-stu-id="c989f-196">Comparison view</span></span>  

<span data-ttu-id="c989f-197">通过相互比较多个快照来查找泄漏的对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-197">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="c989f-198">若要验证特定应用程序操作是否不会产生泄漏 \ (例如，通常一对直接和反向操作（如打开文档，然后关闭它）不应退出任何垃圾 ) ，您可能需要遵循以下方案：</span><span class="sxs-lookup"><span data-stu-id="c989f-198">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="c989f-199">在执行操作之前，请拍摄堆快照。</span><span class="sxs-lookup"><span data-stu-id="c989f-199">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="c989f-200">执行操作 \ (以某种方式与页面交互，使你认为导致泄漏 \n ) 。</span><span class="sxs-lookup"><span data-stu-id="c989f-200">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="c989f-201">执行反向操作 \ (执行相反的交互操作，并多次重复 \ ) 。</span><span class="sxs-lookup"><span data-stu-id="c989f-201">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="c989f-202">获取第二个堆快照，并将此快照的视图更改为 **比较**，将其与 **快照 1**进行比较。</span><span class="sxs-lookup"><span data-stu-id="c989f-202">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  
    
<span data-ttu-id="c989f-203">在 " **比较** " 视图中，显示两个快照之间的差异。</span><span class="sxs-lookup"><span data-stu-id="c989f-203">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="c989f-204">展开总条目时，将显示添加和删除的对象实例。</span><span class="sxs-lookup"><span data-stu-id="c989f-204">When expanding a total entry, added and deleted object instances are shown.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比较视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   <span data-ttu-id="c989f-206">**比较** 视图</span><span class="sxs-lookup"><span data-stu-id="c989f-206">**Comparison** view</span></span>  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <span data-ttu-id="c989f-207">包含视图</span><span class="sxs-lookup"><span data-stu-id="c989f-207">Containment view</span></span>  

<span data-ttu-id="c989f-208">**包含**视图实质上是应用程序的对象结构的 "鸟瞰图"。</span><span class="sxs-lookup"><span data-stu-id="c989f-208">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="c989f-209">它允许你在函数闭包内进行查看，以观察虚拟机 \ (VM \ ) 共同构成 JavaScript 对象的内部对象，并了解应用程序在非常低的级别上使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="c989f-209">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="c989f-210">包容视图入口点</span><span class="sxs-lookup"><span data-stu-id="c989f-210">Containment view entry points</span></span> | <span data-ttu-id="c989f-211">描述</span><span class="sxs-lookup"><span data-stu-id="c989f-211">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="c989f-212">DOMWindow 对象</span><span class="sxs-lookup"><span data-stu-id="c989f-212">DOMWindow objects</span></span>** | <span data-ttu-id="c989f-213">适用于 JavaScript 代码的全局对象。</span><span class="sxs-lookup"><span data-stu-id="c989f-213">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="c989f-214">GC 根</span><span class="sxs-lookup"><span data-stu-id="c989f-214">GC roots</span></span>** | <span data-ttu-id="c989f-215">由 VM 的垃圾回收使用的实际 GC 根。</span><span class="sxs-lookup"><span data-stu-id="c989f-215">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="c989f-216">GC 根由内置的对象映射、符号表、VM 线程堆栈、编译缓存、处理作用域和全局句柄组成。</span><span class="sxs-lookup"><span data-stu-id="c989f-216">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="c989f-217">本机对象</span><span class="sxs-lookup"><span data-stu-id="c989f-217">Native objects</span></span>** | <span data-ttu-id="c989f-218">在 JavaScript 虚拟机 \ (JavaScript VM \ ) 中的浏览器对象 "推送" 以允许自动化（例如，DOM 节点、CSS 规则）。</span><span class="sxs-lookup"><span data-stu-id="c989f-218">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="包含视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   <span data-ttu-id="c989f-220">**包含** 视图</span><span class="sxs-lookup"><span data-stu-id="c989f-220">**Containment** view</span></span>  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="c989f-221">有关闭包的提示。</span><span class="sxs-lookup"><span data-stu-id="c989f-221">A tip about closures.</span></span>  <span data-ttu-id="c989f-222">对函数进行命名，以便能够轻松地区分快照中的闭包。</span><span class="sxs-lookup"><span data-stu-id="c989f-222">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="c989f-223">例如，此示例不使用命名的函数。</span><span class="sxs-lookup"><span data-stu-id="c989f-223">For example, this example does not use named functions.</span></span>  
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
> <span data-ttu-id="c989f-224">Followingcode 代码段使用命名的函数。</span><span class="sxs-lookup"><span data-stu-id="c989f-224">The followingcode snippet uses named functions.</span></span>  
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
> > <span data-ttu-id="c989f-225">试一试此示例， [原因 `eval` 是][GlitchDevtoolsMemoryExample07] 分析闭包对内存的影响。</span><span class="sxs-lookup"><span data-stu-id="c989f-225">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="c989f-226">你可能还会对此示例进行关注，让你完成记录 [堆分配][GlitchDevtoolsMemoryExample08]。</span><span class="sxs-lookup"><span data-stu-id="c989f-226">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <span data-ttu-id="c989f-227">查找颜色编码</span><span class="sxs-lookup"><span data-stu-id="c989f-227">Look up color coding</span></span>  

<span data-ttu-id="c989f-228">对象的属性和属性值具有不同的类型，并相应地着色。</span><span class="sxs-lookup"><span data-stu-id="c989f-228">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="c989f-229">每个属性都具有以下四种类型之一。</span><span class="sxs-lookup"><span data-stu-id="c989f-229">Each property has one of four types.</span></span>  

| <span data-ttu-id="c989f-230">属性类型</span><span class="sxs-lookup"><span data-stu-id="c989f-230">Property Type</span></span> | <span data-ttu-id="c989f-231">描述</span><span class="sxs-lookup"><span data-stu-id="c989f-231">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="c989f-232">a：属性</span><span class="sxs-lookup"><span data-stu-id="c989f-232">a: property</span></span>** | <span data-ttu-id="c989f-233">带有名称的常规属性，通过 `.` \ (点 \ ) 运算符或通过 `[` `]` \ (方括号 \ ) 表示法访问） `["foo bar"]` 。</span><span class="sxs-lookup"><span data-stu-id="c989f-233">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="c989f-234">0：元素</span><span class="sxs-lookup"><span data-stu-id="c989f-234">0: element</span></span>** | <span data-ttu-id="c989f-235">带有数字索引的常规属性，通过 `[` `]` \ (方括号 \ ) 表示法访问。</span><span class="sxs-lookup"><span data-stu-id="c989f-235">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="c989f-236">a：上下文 var</span><span class="sxs-lookup"><span data-stu-id="c989f-236">a: context var</span></span>** |  <span data-ttu-id="c989f-237">函数上下文中的一个变量，可通过函数闭中的变量名称进行访问。</span><span class="sxs-lookup"><span data-stu-id="c989f-237">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="c989f-238">a：系统属性</span><span class="sxs-lookup"><span data-stu-id="c989f-238">a: system prop</span></span>** | <span data-ttu-id="c989f-239">由 JavaScript VM 添加的属性，无法从 JavaScript 代码访问。</span><span class="sxs-lookup"><span data-stu-id="c989f-239">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="c989f-240">指定为 " `System` 不具有相应 JavaScript 类型的对象"。</span><span class="sxs-lookup"><span data-stu-id="c989f-240">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="c989f-241">每个都是 Javascript VM 的对象系统实现的一部分。</span><span class="sxs-lookup"><span data-stu-id="c989f-241">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="c989f-242">V8 将分配同一个堆中的大部分内部对象（用户的 JS 对象）。</span><span class="sxs-lookup"><span data-stu-id="c989f-242">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="c989f-243">因此，这些只是 V8 内部。</span><span class="sxs-lookup"><span data-stu-id="c989f-243">So these are just V8 internals.</span></span>  

## <span data-ttu-id="c989f-244">查找特定对象</span><span class="sxs-lookup"><span data-stu-id="c989f-244">Find a specific object</span></span>  

<span data-ttu-id="c989f-245">若要查找所收集堆中的对象，您可以使用 `Ctrl` + `F` 进行搜索并提供对象 ID。</span><span class="sxs-lookup"><span data-stu-id="c989f-245">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <span data-ttu-id="c989f-246">发现 DOM 泄漏</span><span class="sxs-lookup"><span data-stu-id="c989f-246">Uncover DOM leaks</span></span>  

<span data-ttu-id="c989f-247">堆探查器能够反映浏览器本机对象 \ (DOM 节点、CSS 规则 \ ) 和 JavaScript 对象之间的双向依赖关系。</span><span class="sxs-lookup"><span data-stu-id="c989f-247">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="c989f-248">这有助于发现由于忘记分离的 DOM 子树而导致的不可见泄漏。</span><span class="sxs-lookup"><span data-stu-id="c989f-248">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="c989f-249">DOM 泄漏可能比你想像的更大。</span><span class="sxs-lookup"><span data-stu-id="c989f-249">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="c989f-250">请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="c989f-250">Consider the following sample.</span></span>  <span data-ttu-id="c989f-251">何时 #tree GC？</span><span class="sxs-lookup"><span data-stu-id="c989f-251">When is the #tree GC?</span></span>  

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

<span data-ttu-id="c989f-252">`#leaf`维护对相关父代的引用 \ (parentNode \ ) 并向上递归 `#tree` ，因此仅当 leafRef 为 nullified 时，才是 GC 的候选项下的整个树 `#tree` 。</span><span class="sxs-lookup"><span data-stu-id="c989f-252">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM 子树" lightbox="../media/memory-problems-tree-gc.msft.png":::
   <span data-ttu-id="c989f-254">DOM 子树</span><span class="sxs-lookup"><span data-stu-id="c989f-254">DOM subtrees</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="c989f-255">示例：请尝试这种 [泄漏的 DOM 节点][GlitchDevtoolsMemoryExample06] 示例，了解它可能会泄漏的位置以及如何检测它。</span><span class="sxs-lookup"><span data-stu-id="c989f-255">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="c989f-256">你还可以查看此 [DOM 泄漏的示例比预期更大][GlitchDevtoolsMemoryExample09]。</span><span class="sxs-lookup"><span data-stu-id="c989f-256">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="c989f-257">若要阅读有关 DOM 泄漏和内存分析基础知识的详细信息，请 [使用 Microsoft Edge DevTools Gonzalo Ruiz De Villa 查找和调试内存泄漏][GonzaloRuizdeVillaMemory] 。</span><span class="sxs-lookup"><span data-stu-id="c989f-257">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

<!--  
## Feedback   


-->  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "对象大小-内存术语 |Microsoft 文档"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "对象保留树内存术语 |Microsoft 文档"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html-Microsoft Edge (Chromium) DevTools |故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "内存 |几"  

> [!NOTE]
> <span data-ttu-id="c989f-267">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="c989f-267">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="c989f-268">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) ，由 [Meggin Kearney][MegginKearney] (技术编写器 \ ) 创作。</span><span class="sxs-lookup"><span data-stu-id="c989f-268">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="c989f-270">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="c989f-270">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
