---
description: 本节介绍内存分析中使用的常见术语，适用于不同语言的各种内存分析工具。
title: 内存术语
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 58b3ecde157b1c551b6c0cd435049ce221555519
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564768"
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
   limitations under the License. -->
# <a name="memory-terminology"></a><span data-ttu-id="f6dfd-104">内存术语</span><span class="sxs-lookup"><span data-stu-id="f6dfd-104">Memory terminology</span></span>  

<span data-ttu-id="f6dfd-105">本文介绍内存分析中使用的常见术语，适用于不同语言的各种内存分析工具。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-105">This article describes common terms used in memory analysis, and is applicable to various memory profiling tools for different languages.</span></span>  

<span data-ttu-id="f6dfd-106">此处介绍的术语和概念是指内存 [面板][DevtoolsMemoryProblemsHeapSnapshots]。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-106">The terms and notions described here refer to the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="f6dfd-107">如果你曾经使用过 Java、.NET 或其他一些内存探查器，那么本文可能是一个刷新程序。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-107">If you have ever worked with either the Java, .NET, or some other memory profiler, then this article may be a refresher.</span></span>  

## <a name="object-sizes"></a><span data-ttu-id="f6dfd-108">对象大小</span><span class="sxs-lookup"><span data-stu-id="f6dfd-108">Object sizes</span></span>  

<span data-ttu-id="f6dfd-109">将内存视为包含基元类型 \ (如数字和字符串\) 和对象 \ (associative arrays\) 。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-109">Think of memory as a graph with primitive types \(like numbers and strings\) and objects \(associative arrays\).</span></span>  <span data-ttu-id="f6dfd-110">它可能会显示为具有许多互连点的图形，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-110">It may display as a graph with many interconnected points such as following figure.</span></span>  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="内存的视觉表示形式" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   <span data-ttu-id="f6dfd-112">内存的视觉表示形式</span><span class="sxs-lookup"><span data-stu-id="f6dfd-112">Visual representation of memory</span></span>  
:::image-end:::  

<span data-ttu-id="f6dfd-113">对象可能以两种方式保留内存：</span><span class="sxs-lookup"><span data-stu-id="f6dfd-113">An object may hold memory in two ways:</span></span>  

*   <span data-ttu-id="f6dfd-114">直接由 对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-114">Directly by the object.</span></span>  
*   <span data-ttu-id="f6dfd-115">隐式保留对其他对象的引用，从而阻止垃圾收集器自动释放这些对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-115">Implicitly by holding references to other objects, and therefore preventing those objects from being automatically disposed by a garbage collector.</span></span>  

<span data-ttu-id="f6dfd-116">当使用 DevTools \ (中的内存面板时，你可能会发现自己正在查看一些不同的信息列。使用该工具可调查 Memory \*\*\) \*\*下发现的内存问题。 [][DevtoolsMemoryProblemsHeapSnapshots]</span><span class="sxs-lookup"><span data-stu-id="f6dfd-116">When working with the [Memory][DevtoolsMemoryProblemsHeapSnapshots] panel in DevTools \(a tool for investigating memory issues found under **Memory**\), you may find yourself looking at a few different columns of information.</span></span>  <span data-ttu-id="f6dfd-117">两个突出的项是 **浅** 表大小和 **保留大小**，但这表示什么？</span><span class="sxs-lookup"><span data-stu-id="f6dfd-117">Two that stand out are **Shallow Size** and **Retained Size**, but what do these represent?</span></span>  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅表和保留大小" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   <span data-ttu-id="f6dfd-119">浅表和保留大小</span><span class="sxs-lookup"><span data-stu-id="f6dfd-119">Shallow and Retained Size</span></span>  
:::image-end:::  

### <a name="shallow-size"></a><span data-ttu-id="f6dfd-120">浅表大小</span><span class="sxs-lookup"><span data-stu-id="f6dfd-120">Shallow size</span></span>  

<span data-ttu-id="f6dfd-121">这是对象所持有的内存大小。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-121">This is the size of memory that is held by the object.</span></span>  

<span data-ttu-id="f6dfd-122">典型的 JavaScript 对象会保留一些内存以供其说明和存储即时值。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-122">Typical JavaScript objects have some memory reserved for their description and for storing immediate values.</span></span>  <span data-ttu-id="f6dfd-123">通常，只有数组和字符串才能具有明显的浅表大小。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-123">Usually, only arrays and strings are able to have a significant shallow size.</span></span>  <span data-ttu-id="f6dfd-124">但是，字符串和外部数组通常具有呈现器内存中的主存储，从而在 JavaScript 堆上只公开一个小包装对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-124">However, strings and external arrays often have their main storage in renderer memory, exposing only a small wrapper object on the JavaScript heap.</span></span>  

<span data-ttu-id="f6dfd-125">呈现器内存是呈现已检查页面的过程的所有内存：页面的本机内存 + JS 堆内存 ， 页面启动的所有专用工作者的 JS 堆内存。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-125">Renderer memory is all memory of the process where an inspected page is rendered: native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page.</span></span>  <span data-ttu-id="f6dfd-126">但是，即使一个小对象，也能够间接地保留大量内存，防止自动垃圾回收过程释放其他对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-126">Nevertheless, even a small object is able to hold a large amount of memory indirectly, by preventing other objects from being disposed of by the automatic garbage collection process.</span></span>  

### <a name="retained-size"></a><span data-ttu-id="f6dfd-127">保留大小</span><span class="sxs-lookup"><span data-stu-id="f6dfd-127">Retained size</span></span>  

<span data-ttu-id="f6dfd-128">这是在对象删除后释放的内存大小，以及从垃圾回收器根目录无法访问的从属 **对象**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-128">This is the size of memory that is freed once the object is deleted along with the dependent objects that were made unreachable from **Garbage Collector roots**.</span></span>  

<span data-ttu-id="f6dfd-129">**垃圾回收器根**由在从本机\*\*\*\* 代码引用 V8 外部的 JavaScript 对象时创建的句柄（本地 (或 global\) ）创建。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-129">**Garbage Collector roots** are made up of **handles** that are created \(either local or global\) when making a reference from native code to a JavaScript object outside of V8.</span></span>  <span data-ttu-id="f6dfd-130">可以在 GC 根下的堆快照内找到所有此类\*\*\*\* 句柄  >  **处理范围**和**GC 根**  >  **全局句柄**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-130">All such handles may be found within a heap snapshot under **GC roots** > **Handle scope** and **GC roots** > **Global handles**.</span></span>  <span data-ttu-id="f6dfd-131">在本文档中介绍句柄而不深入介绍浏览器实现的详细信息可能会令人困惑。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-131">Describing the handles in this documentation without diving into details of the browser implementation may be confusing.</span></span>  <span data-ttu-id="f6dfd-132">垃圾回收器根和句柄都不需要担心。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-132">Both Garbage Collector roots and the handles are not something you need to worry about.</span></span>  

<span data-ttu-id="f6dfd-133">存在大量内部垃圾回收器根，其中大多数对用户不感兴趣。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-133">There are lots of internal Garbage Collector roots, most of which are not interesting for the users.</span></span>  <span data-ttu-id="f6dfd-134">从应用程序的角度来看，有以下类型的根。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-134">From the applications standpoint, there are the following kinds of roots.</span></span>  

*   <span data-ttu-id="f6dfd-135">窗口全局对象 \ (iframe\) 。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-135">Window global object \(in each iframe\).</span></span>  <span data-ttu-id="f6dfd-136">在堆快照中，字段指示窗口最短保留 `distance` 路径上的属性引用数。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-136">In the heap snapshots, the `distance` field indicates the number of property references on the shortest retaining path from the window.</span></span>  
*   <span data-ttu-id="f6dfd-137">文档 DOM 树，由通过遍历文档可到达的所有本机 DOM 节点组成。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-137">The document DOM tree, consisting of all native DOM nodes that are reachable by traversing the document.</span></span>  <span data-ttu-id="f6dfd-138">并非所有节点都有 JavaScript 包装器，但如果节点有包装器，则节点在文档处于活动状态时处于活动状态。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-138">Not all of the nodes have JavaScript wrappers, but if a node has a wrapper, the node is alive while the document is alive.</span></span>  
*   <span data-ttu-id="f6dfd-139">有时对象由源工具和控制台中的调试上下文保留，\*\*\*\* 例如控制台评估之后\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-139">Sometimes objects are retained by the debug context in the **Sources** tool and the **Console**, such as after Console evaluation.</span></span>  <span data-ttu-id="f6dfd-140">使用清除的控制台工具 **创建** 堆快照，在"源"工具的调试器中没有活动的 **断** 点。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-140">Create heap snapshots with a cleared **Console** tool and no active breakpoints in the debugger in the **Sources** tool.</span></span>

>[!TIP]
> <span data-ttu-id="f6dfd-141">在"内存"工具中拍摄堆 [快照之前，][DevtoolsMemoryProblemsHeapSnapshots] 请清除 **"** 控制台"工具，并停用"源"工具中的 **断** 点。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-141">Before taking a heap snapshot in the [Memory][DevtoolsMemoryProblemsHeapSnapshots] tool, clear the **Console** tool and deactivate breakpoints in the **Sources** tool.</span></span>  <span data-ttu-id="f6dfd-142">若要清除 **控制台工具** ，请运行 `clear()` 方法。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-142">To clear the **Console** tool, run the `clear()` method.</span></span>  

<span data-ttu-id="f6dfd-143">内存图以根开头，该根可能是浏览器的对象或模块Node.js `window` `Global` 对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-143">The memory graph starts with a root, which may be the `window` object of the browser or the `Global` object of a Node.js module.</span></span>  <span data-ttu-id="f6dfd-144">您不控制如何对根对象进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-144">You do not control how the root object is garbage collected.</span></span>  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="你无法控制如何对根对象进行垃圾回收。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   <span data-ttu-id="f6dfd-146">你无法控制如何对根对象进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-146">You are not able to control how the root object is garbage collected.</span></span>  
:::image-end:::  

<span data-ttu-id="f6dfd-147">从根目录无法到达的任何对象都会进行垃圾回收。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-147">Whatever is not reachable from the root gets garbage collected.</span></span>  

> [!NOTE]
> <span data-ttu-id="f6dfd-148">"[浅表大小"](#shallow-size)[和"保留大小"](#retained-size)列均表示以字节为单位的数据。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-148">Both the [Shallow size](#shallow-size) and [Retained size](#retained-size) columns represent data in bytes.</span></span>  

## <a name="objects-retaining-tree"></a><span data-ttu-id="f6dfd-149">保留树的对象</span><span class="sxs-lookup"><span data-stu-id="f6dfd-149">Objects retaining tree</span></span>  

<span data-ttu-id="f6dfd-150">堆是互连对象的网络。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-150">The heap is a network of interconnected objects.</span></span>  <span data-ttu-id="f6dfd-151">在数学世界，此结构称为 **图形或** 内存图。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-151">In the mathematical world, this structure is called a **graph** or memory graph.</span></span>  <span data-ttu-id="f6dfd-152">图形由**通过边缘连接的**节点构造，两者都是\*\*\*\* 给定的标签。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-152">A graph is constructed from **nodes** connected by means of **edges**, both of which are given labels.</span></span>  

*   <span data-ttu-id="f6dfd-153">**节点**\ (**或对象**\) 标有用于生成节点的构造函数函数的名称\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-153">**Nodes** \(or **objects**\) are labelled using the name of the **constructor** function that was used to build them.</span></span>  
*   <span data-ttu-id="f6dfd-154">**边缘** 使用属性 的名称 **标记**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-154">**Edges** are labelled using the names of **properties**.</span></span>  

<span data-ttu-id="f6dfd-155">了解如何 [使用堆配置文件器记录配置文件][DevtoolsMemoryProblemsHeapSnapshots]。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-155">Learn [how to record a profile using the Heap Profiler][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="f6dfd-156">在下图中，内存工具中堆快照记录中的一些 [值得注意的事项包括][DevtoolsMemoryProblemsHeapSnapshots] 距离：垃圾回收器根之间的距离。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-156">In the following figure, some of the notable things in the Heap Snapshot recording in the [Memory][DevtoolsMemoryProblemsHeapSnapshots] tool include distance:  the distance from the Garbage Collector root.</span></span>  <span data-ttu-id="f6dfd-157">如果几乎同一类型的所有对象都位于同一距离，而其中一些对象距离较大，则值得调查。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-157">If almost all the objects of the same type are at the same distance, and a few are at a bigger distance, that is something worth investigating.</span></span>  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="与根之间的距离" lightbox="../media/memory-problems-root.msft.png":::
   <span data-ttu-id="f6dfd-159">与根之间的距离</span><span class="sxs-lookup"><span data-stu-id="f6dfd-159">Distance from root</span></span>  
:::image-end:::  

## <a name="dominators"></a><span data-ttu-id="f6dfd-160">Dominators</span><span class="sxs-lookup"><span data-stu-id="f6dfd-160">Dominators</span></span>  

<span data-ttu-id="f6dfd-161">Dominator 对象由树结构组成，因为每个对象只有一个管理程序。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-161">Dominator objects are comprised of a tree structure because each object has exactly one dominator.</span></span>  <span data-ttu-id="f6dfd-162">对象的管理者可能缺少对它所控制的对象的直接引用;也就是说，管理器的树不是图形的跨越树。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-162">A dominator of an object may lack direct references to an object it dominates; that is, the tree of the dominator is not a spanning tree of the graph.</span></span>  

<span data-ttu-id="f6dfd-163">在下图中，以下语句为 true。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-163">In the following figure, the following statement are true.</span></span>  

*   <span data-ttu-id="f6dfd-164">节点 1 控制节点 2</span><span class="sxs-lookup"><span data-stu-id="f6dfd-164">Node 1 dominates node 2</span></span>  
*   <span data-ttu-id="f6dfd-165">节点 2 控制节点 3、4 和 6</span><span class="sxs-lookup"><span data-stu-id="f6dfd-165">Node 2 dominates nodes 3, 4 and 6</span></span>  
*   <span data-ttu-id="f6dfd-166">节点 3 与节点 5</span><span class="sxs-lookup"><span data-stu-id="f6dfd-166">Node 3 dominates node 5</span></span>  
*   <span data-ttu-id="f6dfd-167">节点 5 控制节点 8</span><span class="sxs-lookup"><span data-stu-id="f6dfd-167">Node 5 dominates node 8</span></span>  
*   <span data-ttu-id="f6dfd-168">节点 6 与节点 7</span><span class="sxs-lookup"><span data-stu-id="f6dfd-168">Node 6 dominates node 7</span></span>  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="Dominator 树结构" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   <span data-ttu-id="f6dfd-170">Dominator 树结构</span><span class="sxs-lookup"><span data-stu-id="f6dfd-170">Dominator tree structure</span></span>  
:::image-end:::  

<span data-ttu-id="f6dfd-171">在下图中，node 是 的管理程序，但也存在于从垃圾回收器到 `#3` `#10` `#7` 的每个简单路径 `#10` 中。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-171">In the following figure, node `#3` is the dominator of `#10`, but `#7` also exists in every simple path from Garbage Collector to `#10`.</span></span>  <span data-ttu-id="f6dfd-172">因此，如果 B 存在于从根到对象 A 的每一个简单路径中，则对象 B 是对象 A 的管理者。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-172">Therefore, an object B is a dominator of an object A if B exists in every simple path from the root to the object A.</span></span>  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="动画管理程序图示" lightbox="../media/memory-problems-dominators.msft.gif":::
   <span data-ttu-id="f6dfd-174">动画管理程序图示</span><span class="sxs-lookup"><span data-stu-id="f6dfd-174">Animated dominator illustration</span></span>  
:::image-end:::  

## <a name="v8-specifics"></a><span data-ttu-id="f6dfd-175">V8 特定内容</span><span class="sxs-lookup"><span data-stu-id="f6dfd-175">V8 specifics</span></span>  

<span data-ttu-id="f6dfd-176">分析内存时，了解堆快照为何以特定方式显示非常有用。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-176">When profiling memory, it is helpful to understand why heap snapshots look a certain way.</span></span>  <span data-ttu-id="f6dfd-177">本节介绍一些与内存相关的主题，这些主题专门与 **V8 JavaScript** 虚拟机 \ (V8 VM 或 VM\) 。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-177">This section describes some memory-related topics specifically corresponding to the **V8 JavaScript virtual machine** \(V8 VM or VM\).</span></span>  

### <a name="javascript-object-representation"></a><span data-ttu-id="f6dfd-178">JavaScript 对象表示形式</span><span class="sxs-lookup"><span data-stu-id="f6dfd-178">JavaScript object representation</span></span>  

<span data-ttu-id="f6dfd-179">有三种基元类型：</span><span class="sxs-lookup"><span data-stu-id="f6dfd-179">There are three primitive types:</span></span>  

*   <span data-ttu-id="f6dfd-180">数字 \ (例如 `3.14159...` \) </span><span class="sxs-lookup"><span data-stu-id="f6dfd-180">Numbers \(for example `3.14159...`\)</span></span>  
*   <span data-ttu-id="f6dfd-181">布尔值 \ (`true` `false` 或 \) </span><span class="sxs-lookup"><span data-stu-id="f6dfd-181">Booleans \(`true` or `false`\)</span></span>  
*   <span data-ttu-id="f6dfd-182">字符串 \ (例如 `"Werner Heisenberg"` \) </span><span class="sxs-lookup"><span data-stu-id="f6dfd-182">Strings \(for example `"Werner Heisenberg"`\)</span></span>  

<span data-ttu-id="f6dfd-183">基元无法引用其他值，并且始终是叶节点或终止节点。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-183">Primitives are not able to reference other values and are always leafs or terminating nodes.</span></span>  

<span data-ttu-id="f6dfd-184">**数字** 可以存储为：</span><span class="sxs-lookup"><span data-stu-id="f6dfd-184">**Numbers** are able to be stored as either:</span></span>  

*   <span data-ttu-id="f6dfd-185">称为小整数 **\ (** **SMI**s\) 的直接 31 位整数值，或</span><span class="sxs-lookup"><span data-stu-id="f6dfd-185">an immediate 31-bit integer values called **small integers** \(**SMI**s\), or</span></span>  
*   <span data-ttu-id="f6dfd-186">堆对象，称为 **堆数**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-186">heap objects, referred to as **heap numbers**.</span></span> <span data-ttu-id="f6dfd-187">堆编号用于存储不适合 SMI 表单的值（如双精度数）或需要对\*\*\*\* 值进行装箱时（例如设置其属性）。 \*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="f6dfd-187">Heap numbers are used for storing values that do not fit into the SMI form, such as **doubles**, or when a value needs to be **boxed**, such as setting properties on it.</span></span>  

<span data-ttu-id="f6dfd-188">**字符串** 可以存储在：</span><span class="sxs-lookup"><span data-stu-id="f6dfd-188">**Strings** are able to be stored in either:</span></span>  

*   <span data-ttu-id="f6dfd-189">**VM 堆**， 或</span><span class="sxs-lookup"><span data-stu-id="f6dfd-189">the **VM heap**, or</span></span>
*   <span data-ttu-id="f6dfd-190">在呈现 **器的内存外部**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-190">externally in the **memory of the renderer**.</span></span>  <span data-ttu-id="f6dfd-191">创建 **包装** 对象并用于访问外部存储，例如，存储从 Web 接收的脚本源和其他内容，而不是复制到 VM 堆。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-191">A **wrapper object** is created and used for accessing external storage where, for example, script sources and other content that is received from the Web is stored, rather than copied onto the VM heap.</span></span>

<span data-ttu-id="f6dfd-192">新 JavaScript 对象的内存从专用 JavaScript 堆 \ (**或 VM 堆**\) 。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-192">Memory for new JavaScript objects is allocated from a dedicated JavaScript heap \(or **VM heap**\).</span></span>  <span data-ttu-id="f6dfd-193">这些对象由 V8 中的垃圾回收器管理，因此，只要至少有一个强引用，它们就保持活动状态。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-193">These objects are managed by the garbage collector in V8 and therefore, stay alive as long as there is at least one strong reference to them.</span></span>  

<span data-ttu-id="f6dfd-194">不在 JavaScript 堆中任何内容都称为 **本机对象**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-194">Anything not in the JavaScript heap is called a **native object**.</span></span>  <span data-ttu-id="f6dfd-195">与堆对象相反，本机对象在生命周期内不由 V8 垃圾回收器管理，并且只能使用 JavaScript 包装对象从 JavaScript 访问。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-195">Native objects, in contrast to heap objects, are not managed by the V8 garbage collector throughout their lifetime, and may only be accessed from JavaScript using the JavaScript wrapper object.</span></span>  

<span data-ttu-id="f6dfd-196">**Cons string** 是一个包含存储然后联接的字符串对的对象，它是连接的结果。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-196">**Cons string** is an object that consists of pairs of strings stored and then joined, and is a result of concatenation.</span></span>  <span data-ttu-id="f6dfd-197">仅根据需要 **联接 cons 字符串** 内容。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-197">The joining of the **cons string** contents occurs only as needed.</span></span>  <span data-ttu-id="f6dfd-198">例如，需要构造联接字符串的子字符串时。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-198">For example, when a substring of a joined string needs to be constructed.</span></span>

<span data-ttu-id="f6dfd-199">例如，如果连接 和 `a` ，则 `b` 得到一个表示连接结果 `(a, b)` 的字符串。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-199">For example, if you concatenate `a` and `b`, you get a string `(a, b)` which represents the result of concatenation.</span></span>  <span data-ttu-id="f6dfd-200">如果稍后连接了该 `d` 结果，则得到另一个 **cons 字符串**： `((a, b, d)` 。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-200">If you later concatenated `d` with that result, you get another **cons string**: `((a, b, d)`.</span></span>  

<span data-ttu-id="f6dfd-201">**Array** 是一个包含数字键的对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-201">**Array** is an object with numeric keys.</span></span> <span data-ttu-id="f6dfd-202">**数组** 在 V8 VM 中广泛使用，用于存储大量数据。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-202">**Arrays** are used extensively in the V8 VM for storing large amounts of data.</span></span> <span data-ttu-id="f6dfd-203">键值对集（如字典）由数组 **进行备份**。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-203">Sets of key-value pairs, like dictionaries, are backed up by **arrays**.</span></span>  

<span data-ttu-id="f6dfd-204">典型的 JavaScript 对象仅存储为两种数组类型 **之** 一：</span><span class="sxs-lookup"><span data-stu-id="f6dfd-204">A typical JavaScript object is stored as only one of two **array** types:</span></span>  

*   <span data-ttu-id="f6dfd-205">命名属性和</span><span class="sxs-lookup"><span data-stu-id="f6dfd-205">named properties, and</span></span>  
*   <span data-ttu-id="f6dfd-206">数值元素</span><span class="sxs-lookup"><span data-stu-id="f6dfd-206">numeric elements</span></span>  

<span data-ttu-id="f6dfd-207">当有少量属性时，这些属性将内部存储在 JavaScript 对象中。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-207">When there are a small number of properties, the properties are stored internally in the JavaScript object.</span></span>  

<span data-ttu-id="f6dfd-208">**Map** 是描述对象种类和布局的对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-208">**Map** is an object that describes both the kind of object it is and the layout.</span></span> <span data-ttu-id="f6dfd-209">例如，映射用于描述用于快速属性访问的隐式 [对象层次结构][V8FastProperties]。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-209">For example, maps are used to describe implicit object hierarchies for [fast property access][V8FastProperties].</span></span>  

### <a name="object-groups"></a><span data-ttu-id="f6dfd-210">对象组</span><span class="sxs-lookup"><span data-stu-id="f6dfd-210">Object groups</span></span>  

<span data-ttu-id="f6dfd-211">每个 **本机对象** 组由相互引用的对象所共同决定。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-211">Each **native objects** group is made up of objects that hold mutual references to each other.</span></span>  <span data-ttu-id="f6dfd-212">例如，请考虑一个 DOM 子树，其中每个节点都有一个指向相对父级的链接以及指向下一个子级和下一个同级元素的链接，因此形成一个连接的图形。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-212">Consider, for example, a DOM subtree where every node has a link to the relative parent and links to the next child and next sibling, therefore forming a connected graph.</span></span>  

> [!NOTE]
> <span data-ttu-id="f6dfd-213">本机对象不表示在 JavaScript 堆中。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-213">Native objects are not represented in the JavaScript heap.</span></span>  <span data-ttu-id="f6dfd-214">缺少表示是本机对象的大小为零的原因。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-214">The lack of representation is why native objects have zero size.</span></span> <span data-ttu-id="f6dfd-215">相反，会创建包装对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-215">Instead, wrapper objects are created.</span></span>  

<span data-ttu-id="f6dfd-216">每个包装对象保存对相应本机对象的引用，用于将命令重定向到该对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-216">Each wrapper object holds a reference to the corresponding native object, for redirecting commands to it.</span></span>  <span data-ttu-id="f6dfd-217">反过来，对象组会保留包装对象。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-217">In turn, an object group holds wrapper objects.</span></span>  <span data-ttu-id="f6dfd-218">但是，这不会创建一个不可存储的循环，因为垃圾回收器足够智能，可以释放不再引用其包装器的对象组。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-218">However, this does not create an uncollectable cycle, as Garbage Collector is smart enough to release object groups whose wrappers are no longer referenced.</span></span>  <span data-ttu-id="f6dfd-219">但忘记释放单个包装会保留整个组和关联的包装器。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-219">But forgetting to release a single wrapper holds the whole group and associated wrappers.</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="f6dfd-220">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="f6dfd-220">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "如何记录堆快照|Microsoft Docs"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 中的快速|V8"  

> [!NOTE]
> <span data-ttu-id="f6dfd-223">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-223">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="f6dfd-224">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) ，由 [Meggin Kearney][MegginKearney] \ (Technical Writer\) 。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-224">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="f6dfd-226">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="f6dfd-226">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney
