---
title: 如何录制堆快照
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/03/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: e6f64b219bc2b28d01780c28cc605d56a07cb491
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611676"
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





# <span data-ttu-id="e9c75-103">如何录制堆快照</span><span class="sxs-lookup"><span data-stu-id="e9c75-103">How to Record Heap Snapshots</span></span>   



<span data-ttu-id="e9c75-104">了解如何将堆快照与 Microsoft Edge DevTools 堆探查器一起录制并查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="e9c75-104">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="e9c75-105">Microsoft Edge DevTools 堆探查器显示由页面的 JavaScript 对象和相关的 DOM 节点的内存分布。</span><span class="sxs-lookup"><span data-stu-id="e9c75-105">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="e9c75-106">使用它来获取 JavaScript 堆 \ （JS 堆 \）快照、分析内存图、比较快照和查找内存泄漏。</span><span class="sxs-lookup"><span data-stu-id="e9c75-106">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="e9c75-107">另请参阅[对象保留树][DevtoolsMemoryProblems101ObjectsRetainingTree]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-107">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <span data-ttu-id="e9c75-108">拍摄快照</span><span class="sxs-lookup"><span data-stu-id="e9c75-108">Take a snapshot</span></span>  

<span data-ttu-id="e9c75-109">在 "**内存**" 面板上，选择 "**拍摄快照**"，然后单击 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="e9c75-109">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span></span>  <span data-ttu-id="e9c75-110">您也可以按 `Ctrl` + `E` \ （Windows \）或 `Cmd` + `E` \ （macOS \）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-110">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span></span>  

> ##### <span data-ttu-id="e9c75-111">图 1</span><span class="sxs-lookup"><span data-stu-id="e9c75-111">Figure 1</span></span>  
> <span data-ttu-id="e9c75-112">选择性能分析类型</span><span class="sxs-lookup"><span data-stu-id="e9c75-112">Select profiling type</span></span>  
> ![选择性能分析类型][ImageProfilingType]  

<span data-ttu-id="e9c75-114">**快照**最初存储在呈现器进程内存中。</span><span class="sxs-lookup"><span data-stu-id="e9c75-114">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="e9c75-115">当你单击 "快照" 图标进行查看时，快照将按需转到 DevTools。</span><span class="sxs-lookup"><span data-stu-id="e9c75-115">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span></span>  

<span data-ttu-id="e9c75-116">将快照加载到 DevTools 并进行分析后，将显示快照标题下方的数字，并显示可[访问的 JavaScript 对象的总大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

> ##### <span data-ttu-id="e9c75-117">图 2</span><span class="sxs-lookup"><span data-stu-id="e9c75-117">Figure 2</span></span>  
> <span data-ttu-id="e9c75-118">可访问对象的总大小</span><span class="sxs-lookup"><span data-stu-id="e9c75-118">Total size of reachable objects</span></span>  
> ![可访问对象的总大小][ImageTotalSize]  

> [!NOTE]
> <span data-ttu-id="e9c75-120">快照中仅包含可访问的对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-120">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="e9c75-121">此外，拍摄快照始终从垃圾回收开始。</span><span class="sxs-lookup"><span data-stu-id="e9c75-121">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <span data-ttu-id="e9c75-122">清除快照</span><span class="sxs-lookup"><span data-stu-id="e9c75-122">Clear snapshots</span></span>  

<span data-ttu-id="e9c75-123">单击 "**清除所有配置文件**" 图标以删除快照 \ （从 DevTools 和与呈现程序进程关联的任何内存 \）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-123">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

> ##### <span data-ttu-id="e9c75-124">图 3</span><span class="sxs-lookup"><span data-stu-id="e9c75-124">Figure 3</span></span>  
> <span data-ttu-id="e9c75-125">删除快照</span><span class="sxs-lookup"><span data-stu-id="e9c75-125">Remove snapshots</span></span>  
> ![删除快照][ImageRemoveSnapshots]  

<span data-ttu-id="e9c75-127">关闭 DevTools 窗口不会删除与呈现程序进程关联的内存中的配置文件。</span><span class="sxs-lookup"><span data-stu-id="e9c75-127">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="e9c75-128">重新打开 DevTools 时，以前拍摄的所有快照都会重新出现在快照列表中。</span><span class="sxs-lookup"><span data-stu-id="e9c75-128">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="e9c75-129">请试用[分散对象][GlitchDevtoolsMemoryExample03]的示例并使用堆探查器对其进行分析。</span><span class="sxs-lookup"><span data-stu-id="e9c75-129">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="e9c75-130">你应该会看到大量的 \ （对象 \）项目分配。</span><span class="sxs-lookup"><span data-stu-id="e9c75-130">You should see a number of \(object\) item allocations.</span></span>  

## <span data-ttu-id="e9c75-131">查看快照</span><span class="sxs-lookup"><span data-stu-id="e9c75-131">View snapshots</span></span>  

<span data-ttu-id="e9c75-132">从不同的视角查看不同任务的快照。</span><span class="sxs-lookup"><span data-stu-id="e9c75-132">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="e9c75-133">"**摘要" 视图**显示按构造函数名称分组的对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-133">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="e9c75-134">使用它基于按构造函数名称分组的类型来查寻对象 \ （和内存使用 \）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-134">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="e9c75-135">它对于**跟踪 DOM 泄漏**非常有用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-135">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="e9c75-136">**比较视图**。</span><span class="sxs-lookup"><span data-stu-id="e9c75-136">**Comparison view**.</span></span>  <span data-ttu-id="e9c75-137">显示两个快照之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e9c75-137">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="e9c75-138">使用它比较操作前后的两个 \ （或多个 \）内存快照。</span><span class="sxs-lookup"><span data-stu-id="e9c75-138">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="e9c75-139">检查已释放的内存和引用计数中的增量可让你确认内存泄漏的存在和原因。</span><span class="sxs-lookup"><span data-stu-id="e9c75-139">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="e9c75-140">**包含视图**。</span><span class="sxs-lookup"><span data-stu-id="e9c75-140">**Containment view**.</span></span>  <span data-ttu-id="e9c75-141">允许探索堆内容。</span><span class="sxs-lookup"><span data-stu-id="e9c75-141">Allows exploration of heap contents.</span></span>  <span data-ttu-id="e9c75-142">"**包容" 视图**提供了更好的对象结构视图，帮助分析全局命名空间 \ （窗口 \）中引用的对象，以查明对象的保留对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-142">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="e9c75-143">使用它来分析闭包，并以较低的级别深入查看你的对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-143">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="e9c75-144">若要在视图之间进行切换，请使用视图顶部的选择器。</span><span class="sxs-lookup"><span data-stu-id="e9c75-144">To switch between views, use the selector at the top of the view.</span></span>  

> ##### <span data-ttu-id="e9c75-145">图 4</span><span class="sxs-lookup"><span data-stu-id="e9c75-145">Figure 4</span></span>  
> <span data-ttu-id="e9c75-146">切换视图选择器</span><span class="sxs-lookup"><span data-stu-id="e9c75-146">Switch views selector</span></span>  
> ![切换视图选择器][ImageSwitchViews]  

> [!NOTE]
> <span data-ttu-id="e9c75-148">并非所有属性都存储在 JavaScript 堆上。</span><span class="sxs-lookup"><span data-stu-id="e9c75-148">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="e9c75-149">不捕获使用运行本机代码的 getter 实现的属性。</span><span class="sxs-lookup"><span data-stu-id="e9c75-149">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="e9c75-150">此外，不捕获数字等非字符串值。</span><span class="sxs-lookup"><span data-stu-id="e9c75-150">Also, non-string values such as numbers are not captured.</span></span>  

### <span data-ttu-id="e9c75-151">摘要视图</span><span class="sxs-lookup"><span data-stu-id="e9c75-151">Summary view</span></span>  

<span data-ttu-id="e9c75-152">最初，快照在 "摘要" 视图中打开，显示 "对象总数"，它们可能会展开以显示实例：</span><span class="sxs-lookup"><span data-stu-id="e9c75-152">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

> ##### <span data-ttu-id="e9c75-153">图 5</span><span class="sxs-lookup"><span data-stu-id="e9c75-153">Figure 5</span></span>  
> <span data-ttu-id="e9c75-154">摘要视图</span><span class="sxs-lookup"><span data-stu-id="e9c75-154">Summary view</span></span>  
> ![摘要视图][ImageSummaryView]  

<span data-ttu-id="e9c75-156">顶级条目是 "汇总" 行。</span><span class="sxs-lookup"><span data-stu-id="e9c75-156">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="e9c75-157">顶级项</span><span class="sxs-lookup"><span data-stu-id="e9c75-157">Top-level entries</span></span> | <span data-ttu-id="e9c75-158">描述</span><span class="sxs-lookup"><span data-stu-id="e9c75-158">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="e9c75-159">构造函数</span><span class="sxs-lookup"><span data-stu-id="e9c75-159">Constructor</span></span>** | <span data-ttu-id="e9c75-160">表示使用此构造函数创建的所有对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-160">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="e9c75-161">距离</span><span class="sxs-lookup"><span data-stu-id="e9c75-161">Distance</span></span>** | <span data-ttu-id="e9c75-162">使用节点的最短简单路径显示到根的距离。</span><span class="sxs-lookup"><span data-stu-id="e9c75-162">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="e9c75-163">浅大小</span><span class="sxs-lookup"><span data-stu-id="e9c75-163">Shallow size</span></span>** | <span data-ttu-id="e9c75-164">显示由特定构造函数创建的所有对象的平坦大小之和。</span><span class="sxs-lookup"><span data-stu-id="e9c75-164">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="e9c75-165">浅大小是对象所占用的内存大小 \ （通常情况下，数组和字符串具有较大的浅层大小 \）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-165">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="e9c75-166">另请参阅[对象大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-166">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="e9c75-167">保留大小</span><span class="sxs-lookup"><span data-stu-id="e9c75-167">Retained size</span></span>** | <span data-ttu-id="e9c75-168">显示同一组对象中的最大保留大小。</span><span class="sxs-lookup"><span data-stu-id="e9c75-168">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="e9c75-169">在删除对象后，您能够释放的内存大小 \ （并且无法再访问从属单元）称为保留大小。</span><span class="sxs-lookup"><span data-stu-id="e9c75-169">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="e9c75-170">另请参阅[对象大小][DevtoolsMemoryProblems101ObjectSizes]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-170">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="e9c75-171">在上部视图中展开 "汇总" 行后，将显示所有实例。</span><span class="sxs-lookup"><span data-stu-id="e9c75-171">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="e9c75-172">对于每个实例，浅和保留大小都显示在相应的列中。</span><span class="sxs-lookup"><span data-stu-id="e9c75-172">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="e9c75-173">字符后的数字 `@` 是对象的唯一 ID，使你可以基于每个对象比较堆快照。</span><span class="sxs-lookup"><span data-stu-id="e9c75-173">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="e9c75-174">请注意，黄色对象具有 JavaScript 引用，红色对象是从一个具有黄色背景的分离节点引用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-174">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="e9c75-175">堆探查器中的各种构造函数 \ （group）条目对应于什么？</span><span class="sxs-lookup"><span data-stu-id="e9c75-175">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

> ##### <span data-ttu-id="e9c75-176">图 6</span><span class="sxs-lookup"><span data-stu-id="e9c75-176">Figure 6</span></span>  
> <span data-ttu-id="e9c75-177">构造函数组</span><span class="sxs-lookup"><span data-stu-id="e9c75-177">Constructor groups</span></span>  
> ![构造函数组][ImageConstructorGroups]  

| <span data-ttu-id="e9c75-179">构造函数 \ （group \）条目</span><span class="sxs-lookup"><span data-stu-id="e9c75-179">Constructor \(group\) entry</span></span> | <span data-ttu-id="e9c75-180">描述</span><span class="sxs-lookup"><span data-stu-id="e9c75-180">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="e9c75-181">\ （全局属性 \）</span><span class="sxs-lookup"><span data-stu-id="e9c75-181">\(global property\)</span></span>** | <span data-ttu-id="e9c75-182">全局对象 \ （如 `window` \）和它引用的对象之间的中间对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-182">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="e9c75-183">如果使用构造函数创建对象 `Person` 并由全局对象持有，则保留路径将如下所示 `[global] > \(global property\) > Person` 。</span><span class="sxs-lookup"><span data-stu-id="e9c75-183">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="e9c75-184">这与标准进行对比，其中对象直接相互引用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-184">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="e9c75-185">出于性能原因，存在中间对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-185">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="e9c75-186">全局会定期修改全局，并且属性访问优化对非全局对象执行良好的作业不适用于全局对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-186">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="e9c75-187">\ （根目录 \）</span><span class="sxs-lookup"><span data-stu-id="e9c75-187">\(roots\)</span></span>** | <span data-ttu-id="e9c75-188">"保留树" 视图中的根项是引用所选对象的实体。</span><span class="sxs-lookup"><span data-stu-id="e9c75-188">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="e9c75-189">这些条目也可能是引擎为特定于引擎的目的而创建的引用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-189">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="e9c75-190">该引擎已缓存哪些引用对象，但所有此类引用都很弱，并且不会阻止收集对象，因为没有真正的强引用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-190">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="e9c75-191">\ （关闭 \）</span><span class="sxs-lookup"><span data-stu-id="e9c75-191">\(closure\)</span></span>** | <span data-ttu-id="e9c75-192">通过函数闭包对一组对象的引用的计数。</span><span class="sxs-lookup"><span data-stu-id="e9c75-192">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="e9c75-193">\ （数组，字符串，数字，regexp \）</span><span class="sxs-lookup"><span data-stu-id="e9c75-193">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="e9c75-194">包含属性的对象类型列表，这些属性引用数组、字符串、数字或正则表达式。</span><span class="sxs-lookup"><span data-stu-id="e9c75-194">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="e9c75-195">\ （已编译的代码 \）</span><span class="sxs-lookup"><span data-stu-id="e9c75-195">\(compiled code\)</span></span>** | <span data-ttu-id="e9c75-196">与编译的代码相关的所有内容。</span><span class="sxs-lookup"><span data-stu-id="e9c75-196">Everything related to compiled code.</span></span>  <span data-ttu-id="e9c75-197">脚本类似于函数，但对应于 `<script>` 主体。</span><span class="sxs-lookup"><span data-stu-id="e9c75-197">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="e9c75-198">SharedFunctionInfos \ （SFI \）是位于函数和编译代码之间的对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-198">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="e9c75-199">函数通常具有上下文，而 SFIs 不是。</span><span class="sxs-lookup"><span data-stu-id="e9c75-199">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="e9c75-200">**HTMLDivElement**、 **HTMLAnchorElement**、 **DocumentFragment**等。</span><span class="sxs-lookup"><span data-stu-id="e9c75-200">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="e9c75-201">对你的代码引用的特定类型的元素或文档对象的引用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-201">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <span data-ttu-id="e9c75-202">比较视图</span><span class="sxs-lookup"><span data-stu-id="e9c75-202">Comparison view</span></span>  

<span data-ttu-id="e9c75-203">通过相互比较多个快照来查找泄漏的对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-203">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="e9c75-204">若要验证特定应用程序操作是否不会产生泄漏 \ （例如，通常一对直接和反向操作，例如打开文档，然后关闭它，不应退出任何垃圾 \），你可以按照以下方案进行操作：</span><span class="sxs-lookup"><span data-stu-id="e9c75-204">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="e9c75-205">在执行操作之前，请拍摄堆快照。</span><span class="sxs-lookup"><span data-stu-id="e9c75-205">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="e9c75-206">执行操作 \ （以某种方式与页面交互，以你认为导致泄漏的方式 \）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-206">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="e9c75-207">执行反向操作 \ （执行相反的交互，并多次重复 \）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-207">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="e9c75-208">获取第二个堆快照，并将此快照的视图更改为**比较**，将其与**快照 1**进行比较。</span><span class="sxs-lookup"><span data-stu-id="e9c75-208">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  

<span data-ttu-id="e9c75-209">在 "**比较**" 视图中，显示两个快照之间的差异。</span><span class="sxs-lookup"><span data-stu-id="e9c75-209">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="e9c75-210">展开总条目时，将显示添加和删除的对象实例。</span><span class="sxs-lookup"><span data-stu-id="e9c75-210">When expanding a total entry, added and deleted object instances are shown.</span></span>  

> ##### <span data-ttu-id="e9c75-211">图 7</span><span class="sxs-lookup"><span data-stu-id="e9c75-211">Figure 7</span></span>  
> <span data-ttu-id="e9c75-212">比较视图</span><span class="sxs-lookup"><span data-stu-id="e9c75-212">Comparison view</span></span>  
> ![比较视图][ImageComparisonView]  

<!--todo: add HeapProfilingComparison section when available  -->  

### <span data-ttu-id="e9c75-214">包含视图</span><span class="sxs-lookup"><span data-stu-id="e9c75-214">Containment view</span></span>  

<span data-ttu-id="e9c75-215">**包含**视图实质上是应用程序的对象结构的 "鸟瞰图"。</span><span class="sxs-lookup"><span data-stu-id="e9c75-215">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="e9c75-216">它允许你在函数闭包内进行查看，以观察虚拟机 \ （VM \）内部对象，这些对象共同构成 JavaScript 对象，并了解应用程序在非常低的级别上使用的内存量。</span><span class="sxs-lookup"><span data-stu-id="e9c75-216">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="e9c75-217">包容视图入口点</span><span class="sxs-lookup"><span data-stu-id="e9c75-217">Containment view entry points</span></span> | <span data-ttu-id="e9c75-218">描述</span><span class="sxs-lookup"><span data-stu-id="e9c75-218">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="e9c75-219">DOMWindow 对象</span><span class="sxs-lookup"><span data-stu-id="e9c75-219">DOMWindow objects</span></span>** | <span data-ttu-id="e9c75-220">适用于 JavaScript 代码的全局对象。</span><span class="sxs-lookup"><span data-stu-id="e9c75-220">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="e9c75-221">GC 根</span><span class="sxs-lookup"><span data-stu-id="e9c75-221">GC roots</span></span>** | <span data-ttu-id="e9c75-222">由 VM 的垃圾回收使用的实际 GC 根。</span><span class="sxs-lookup"><span data-stu-id="e9c75-222">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="e9c75-223">GC 根由内置的对象映射、符号表、VM 线程堆栈、编译缓存、处理作用域和全局句柄组成。</span><span class="sxs-lookup"><span data-stu-id="e9c75-223">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="e9c75-224">本机对象</span><span class="sxs-lookup"><span data-stu-id="e9c75-224">Native objects</span></span>** | <span data-ttu-id="e9c75-225">位于 JavaScript 虚拟机 \ （JavaScript VM \）内的浏览器对象 "已推送" 以允许自动化，例如，DOM 节点、CSS 规则。</span><span class="sxs-lookup"><span data-stu-id="e9c75-225">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

> ##### <span data-ttu-id="e9c75-226">图 8</span><span class="sxs-lookup"><span data-stu-id="e9c75-226">Figure 8</span></span>  
> <span data-ttu-id="e9c75-227">包含视图</span><span class="sxs-lookup"><span data-stu-id="e9c75-227">Containment view</span></span>  
> ![包含视图][ImageContainmentView]  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="e9c75-229">有关闭包的提示。</span><span class="sxs-lookup"><span data-stu-id="e9c75-229">A tip about closures.</span></span>  <span data-ttu-id="e9c75-230">对函数进行命名，以便能够轻松地区分快照中的闭包。</span><span class="sxs-lookup"><span data-stu-id="e9c75-230">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="e9c75-231">例如，此示例不使用命名的函数。</span><span class="sxs-lookup"><span data-stu-id="e9c75-231">For example, this example does not use named functions.</span></span>  
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
> <span data-ttu-id="e9c75-232">此示例使用命名函数：</span><span class="sxs-lookup"><span data-stu-id="e9c75-232">This example uses named functions:</span></span>  
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
> > ##### old Figure 9  
> > Name functions to distinguish between closures  
> > ![Name functions to distinguish between closures][ImageDomLeaks]  
> -->  
> 
> > [!NOTE]
> > <span data-ttu-id="e9c75-233">试一试此示例，[原因 `eval` 是][GlitchDevtoolsMemoryExample07]分析闭包对内存的影响。</span><span class="sxs-lookup"><span data-stu-id="e9c75-233">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="e9c75-234">你可能还会对此示例进行关注，让你完成记录[堆分配][GlitchDevtoolsMemoryExample08]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-234">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <span data-ttu-id="e9c75-235">查找颜色编码</span><span class="sxs-lookup"><span data-stu-id="e9c75-235">Look up color coding</span></span>  

<span data-ttu-id="e9c75-236">对象的属性和属性值具有不同的类型，并相应地着色。</span><span class="sxs-lookup"><span data-stu-id="e9c75-236">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="e9c75-237">每个属性都具有以下四种类型之一。</span><span class="sxs-lookup"><span data-stu-id="e9c75-237">Each property has one of four types.</span></span>  

| <span data-ttu-id="e9c75-238">属性类型</span><span class="sxs-lookup"><span data-stu-id="e9c75-238">Property Type</span></span> | <span data-ttu-id="e9c75-239">描述</span><span class="sxs-lookup"><span data-stu-id="e9c75-239">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="e9c75-240">a：属性</span><span class="sxs-lookup"><span data-stu-id="e9c75-240">a: property</span></span>** | <span data-ttu-id="e9c75-241">带有名称的常规属性，通过 `.` \ （点 \）运算符访问，或通过 `[` `]` \ （括弧 \）表示法访问 `["foo bar"]` 。</span><span class="sxs-lookup"><span data-stu-id="e9c75-241">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="e9c75-242">0：元素</span><span class="sxs-lookup"><span data-stu-id="e9c75-242">0: element</span></span>** | <span data-ttu-id="e9c75-243">带有数字索引的常规属性，通过 `[` `]` \ （括号 \）表示符进行访问。</span><span class="sxs-lookup"><span data-stu-id="e9c75-243">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="e9c75-244">a：上下文 var</span><span class="sxs-lookup"><span data-stu-id="e9c75-244">a: context var</span></span>** |  <span data-ttu-id="e9c75-245">函数上下文中的一个变量，可通过函数闭中的变量名称进行访问。</span><span class="sxs-lookup"><span data-stu-id="e9c75-245">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="e9c75-246">a：系统属性</span><span class="sxs-lookup"><span data-stu-id="e9c75-246">a: system prop</span></span>** | <span data-ttu-id="e9c75-247">由 JavaScript VM 添加的属性，无法从 JavaScript 代码访问。</span><span class="sxs-lookup"><span data-stu-id="e9c75-247">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="e9c75-248">指定为 " `System` 不具有相应 JavaScript 类型的对象"。</span><span class="sxs-lookup"><span data-stu-id="e9c75-248">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="e9c75-249">每个都是 Javascript VM 的对象系统实现的一部分。</span><span class="sxs-lookup"><span data-stu-id="e9c75-249">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="e9c75-250">V8 将分配同一个堆中的大部分内部对象（用户的 JS 对象）。</span><span class="sxs-lookup"><span data-stu-id="e9c75-250">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="e9c75-251">因此，这些只是 V8 内部。</span><span class="sxs-lookup"><span data-stu-id="e9c75-251">So these are just V8 internals.</span></span>  

## <span data-ttu-id="e9c75-252">查找特定对象</span><span class="sxs-lookup"><span data-stu-id="e9c75-252">Find a specific object</span></span>  

<span data-ttu-id="e9c75-253">若要查找所收集堆中的对象，您可以使用 `Ctrl` + `F` 进行搜索并提供对象 ID。</span><span class="sxs-lookup"><span data-stu-id="e9c75-253">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <span data-ttu-id="e9c75-254">发现 DOM 泄漏</span><span class="sxs-lookup"><span data-stu-id="e9c75-254">Uncover DOM leaks</span></span>  

<span data-ttu-id="e9c75-255">堆探查器能够反映浏览器本机对象 \ （DOM 节点、CSS 规则 \）和 JavaScript 对象之间的双向依赖关系。</span><span class="sxs-lookup"><span data-stu-id="e9c75-255">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="e9c75-256">这有助于发现由于忘记分离的 DOM 子树而导致的不可见泄漏。</span><span class="sxs-lookup"><span data-stu-id="e9c75-256">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="e9c75-257">DOM 泄漏可能比你想像的更大。</span><span class="sxs-lookup"><span data-stu-id="e9c75-257">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="e9c75-258">请考虑以下示例。</span><span class="sxs-lookup"><span data-stu-id="e9c75-258">Consider the following sample.</span></span>  <span data-ttu-id="e9c75-259">何时 #tree GC？</span><span class="sxs-lookup"><span data-stu-id="e9c75-259">When is the #tree GC?</span></span>  

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

<span data-ttu-id="e9c75-260">`#leaf`保持对相关父代的引用 \ （parentNode \）和向上递归 `#tree` ，因此仅当 leafRef 为 nullified 时，才为 GC 的候选项下的整个树 `#tree` 。</span><span class="sxs-lookup"><span data-stu-id="e9c75-260">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

> ##### <span data-ttu-id="e9c75-261">图 9</span><span class="sxs-lookup"><span data-stu-id="e9c75-261">Figure 9</span></span>  
> <span data-ttu-id="e9c75-262">DOM 子树</span><span class="sxs-lookup"><span data-stu-id="e9c75-262">DOM subtrees</span></span>  
> <span data-ttu-id="e9c75-263">![DOM 子树][ImageTreeGc]</span><span class="sxs-lookup"><span data-stu-id="e9c75-263">![DOM subtrees][ImageTreeGc]</span></span>  

> [!NOTE]
> <span data-ttu-id="e9c75-264">示例：请尝试这种[泄漏的 DOM 节点][GlitchDevtoolsMemoryExample06]示例，了解它可能会泄漏的位置以及如何检测它。</span><span class="sxs-lookup"><span data-stu-id="e9c75-264">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="e9c75-265">你还可以查看此[DOM 泄漏的示例比预期更大][GlitchDevtoolsMemoryExample09]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-265">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="e9c75-266">若要阅读有关 DOM 泄漏和内存分析基础知识的详细信息，请[使用 Microsoft Edge DevTools Gonzalo Ruiz De Villa 查找和调试内存泄漏][GonzaloRuizdeVillaMemory]。</span><span class="sxs-lookup"><span data-stu-id="e9c75-266">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

<!--## Feedback   -->  



<!-- image links -->  

[ImageProfilingType]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png "图1：选择性能分析类型"  
[ImageTotalSize]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png "图2：可访问对象的总大小"  
[ImageRemoveSnapshots]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png "图3：删除快照"  
[ImageSwitchViews]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png "图4：切换视图选择器"  
[ImageSummaryView]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png "图5：摘要视图"  
[ImageConstructorGroups]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png "图6：构造函数组"  
[ImageComparisonView]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png "图7：比较视图"  
[ImageContainmentView]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png "图8：包容视图"  
<!--[ImageDomLeaks]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-domleaks.msft.png "old Figure 9: Name functions to distinguish between closures"  -->  
<span data-ttu-id="e9c75-275">[ImageTreeGc]：/microsoft-edge/devtools-guide-chromium/media/memory-problems-tree-gc.msft.png "图9： DOM 子树"</span><span class="sxs-lookup"><span data-stu-id="e9c75-275">[ImageTreeGc]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-tree-gc.msft.png "Figure 9: DOM subtrees"</span></span>  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: /microsoft-edge/devtools-guide-chromium/memory-problems/memory-101#object-sizes "对象大小-内存术语"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: /microsoft-edge/devtools-guide-chromium/memory-problems/memory-101#objects-retaining-tree "对象保留树内存术语"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03-Microsoft Edge （Chromium） DevTools |故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06-Microsoft Edge （Chromium） DevTools |故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07-Microsoft Edge （Chromium） DevTools |故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08-Microsoft Edge （Chromium） DevTools |故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09-Microsoft Edge （Chromium） DevTools |故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10-Microsoft Edge （Chromium） DevTools |故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "内存 |几"  

> [!NOTE]
> <span data-ttu-id="e9c75-285">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="e9c75-285">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="e9c75-286">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots)，由[Meggin Kearney][MegginKearney] \ （技术作者 \）创作。</span><span class="sxs-lookup"><span data-stu-id="e9c75-286">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="e9c75-288">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="e9c75-288">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
