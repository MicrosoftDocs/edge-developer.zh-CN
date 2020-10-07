---
description: This section describes common terms used in memory analysis, and is applicable to a variety of memory profiling tools for different languages.
title: Memory Terminology
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 3455b05cf19f3aa5a69de5571ab3a24d5654dfe4
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992748"
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

# <span data-ttu-id="84870-104">Memory Terminology</span><span class="sxs-lookup"><span data-stu-id="84870-104">Memory Terminology</span></span>  

<span data-ttu-id="84870-105">This section describes common terms used in memory analysis, and is applicable to a variety of memory profiling tools for different languages.</span><span class="sxs-lookup"><span data-stu-id="84870-105">This section describes common terms used in memory analysis, and is applicable to a variety of memory profiling tools for different languages.</span></span>  

<span data-ttu-id="84870-106">The terms and notions described here refer to the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span><span class="sxs-lookup"><span data-stu-id="84870-106">The terms and notions described here refer to the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="84870-107">If you have ever worked with either the Java, .NET, or some other memory profiler, then this may be a refresher.</span><span class="sxs-lookup"><span data-stu-id="84870-107">If you have ever worked with either the Java, .NET, or some other memory profiler, then this may be a refresher.</span></span>  

## <span data-ttu-id="84870-108">Object sizes</span><span class="sxs-lookup"><span data-stu-id="84870-108">Object sizes</span></span>  

<span data-ttu-id="84870-109">Think of memory as a graph with primitive types \(like numbers and strings\) and objects \(associative arrays\).</span><span class="sxs-lookup"><span data-stu-id="84870-109">Think of memory as a graph with primitive types \(like numbers and strings\) and objects \(associative arrays\).</span></span>  <span data-ttu-id="84870-110">It might visually be represented as a graph with a number of interconnected points as follows:</span><span class="sxs-lookup"><span data-stu-id="84870-110">It might visually be represented as a graph with a number of interconnected points as follows:</span></span>  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="Visual representation of memory" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   <span data-ttu-id="84870-112">Visual representation of memory</span><span class="sxs-lookup"><span data-stu-id="84870-112">Visual representation of memory</span></span>  
:::image-end:::  

<span data-ttu-id="84870-113">An object may hold memory in two ways:</span><span class="sxs-lookup"><span data-stu-id="84870-113">An object may hold memory in two ways:</span></span>  

*   <span data-ttu-id="84870-114">Directly by the object.</span><span class="sxs-lookup"><span data-stu-id="84870-114">Directly by the object.</span></span>  
*   <span data-ttu-id="84870-115">Implicitly by holding references to other objects, and therefore preventing those objects from being automatically disposed by a garbage collector \(**GC** for short\).</span><span class="sxs-lookup"><span data-stu-id="84870-115">Implicitly by holding references to other objects, and therefore preventing those objects from being automatically disposed by a garbage collector \(**GC** for short\).</span></span>  

<span data-ttu-id="84870-116">When working with the [Memory][DevtoolsMemoryProblemsHeapSnapshots] panel in DevTools \(a tool for investigating memory issues found under **Memory**\), you may find yourself looking at a few different columns of information.</span><span class="sxs-lookup"><span data-stu-id="84870-116">When working with the [Memory][DevtoolsMemoryProblemsHeapSnapshots] panel in DevTools \(a tool for investigating memory issues found under **Memory**\), you may find yourself looking at a few different columns of information.</span></span>  <span data-ttu-id="84870-117">Two that stand out are **Shallow Size** and **Retained Size**, but what do these represent?</span><span class="sxs-lookup"><span data-stu-id="84870-117">Two that stand out are **Shallow Size** and **Retained Size**, but what do these represent?</span></span>  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="Visual representation of memory" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   <span data-ttu-id="84870-119">Shallow and Retained Size</span><span class="sxs-lookup"><span data-stu-id="84870-119">Shallow and Retained Size</span></span>  
:::image-end:::  

### <span data-ttu-id="84870-120">Shallow size</span><span class="sxs-lookup"><span data-stu-id="84870-120">Shallow size</span></span>  

<span data-ttu-id="84870-121">This is the size of memory that is held by the object.</span><span class="sxs-lookup"><span data-stu-id="84870-121">This is the size of memory that is held by the object.</span></span>  

<span data-ttu-id="84870-122">Typical JavaScript objects have some memory reserved for their description and for storing immediate values.</span><span class="sxs-lookup"><span data-stu-id="84870-122">Typical JavaScript objects have some memory reserved for their description and for storing immediate values.</span></span>  <span data-ttu-id="84870-123">Usually, only arrays and strings are able to have a significant shallow size.</span><span class="sxs-lookup"><span data-stu-id="84870-123">Usually, only arrays and strings are able to have a significant shallow size.</span></span>  <span data-ttu-id="84870-124">However, strings and external arrays often have their main storage in renderer memory, exposing only a small wrapper object on the JavaScript heap.</span><span class="sxs-lookup"><span data-stu-id="84870-124">However, strings and external arrays often have their main storage in renderer memory, exposing only a small wrapper object on the JavaScript heap.</span></span>  

<span data-ttu-id="84870-125">Renderer memory is all memory of the process where an inspected page is rendered: native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page.</span><span class="sxs-lookup"><span data-stu-id="84870-125">Renderer memory is all memory of the process where an inspected page is rendered: native memory + JS heap memory of the page + JS heap memory of all dedicated workers started by the page.</span></span>  <span data-ttu-id="84870-126">Nevertheless, even a small object is able to hold a large amount of memory indirectly, by preventing other objects from being disposed of by the automatic garbage collection process.</span><span class="sxs-lookup"><span data-stu-id="84870-126">Nevertheless, even a small object is able to hold a large amount of memory indirectly, by preventing other objects from being disposed of by the automatic garbage collection process.</span></span>  

### <span data-ttu-id="84870-127">Retained size</span><span class="sxs-lookup"><span data-stu-id="84870-127">Retained size</span></span>  

<span data-ttu-id="84870-128">This is the size of memory that is freed once the object is deleted along with the dependent objects that were made unreachable from **Garbage Collector roots** \(GC roots\) .</span><span class="sxs-lookup"><span data-stu-id="84870-128">This is the size of memory that is freed once the object is deleted along with the dependent objects that were made unreachable from **Garbage Collector roots** \(GC roots\) .</span></span>  

<span data-ttu-id="84870-129">**Garbage Collector roots** \(GC roots\) are made up of **handles** that are created \(either local or global\) when making a reference from native code to a JavaScript object outside of V8.</span><span class="sxs-lookup"><span data-stu-id="84870-129">**Garbage Collector roots** \(GC roots\) are made up of **handles** that are created \(either local or global\) when making a reference from native code to a JavaScript object outside of V8.</span></span>  <span data-ttu-id="84870-130">All such handles may be found within a heap snapshot under **GC roots** > **Handle scope** and **GC roots** > **Global handles**.</span><span class="sxs-lookup"><span data-stu-id="84870-130">All such handles may be found within a heap snapshot under **GC roots** > **Handle scope** and **GC roots** > **Global handles**.</span></span>  <span data-ttu-id="84870-131">Describing the handles in this documentation without diving into details of the browser implementation may be confusing.</span><span class="sxs-lookup"><span data-stu-id="84870-131">Describing the handles in this documentation without diving into details of the browser implementation may be confusing.</span></span>  <span data-ttu-id="84870-132">Both Garbage Collector (GC) roots and the handles are not something you need to worry about.</span><span class="sxs-lookup"><span data-stu-id="84870-132">Both Garbage Collector (GC) roots and the handles are not something you need to worry about.</span></span>  

<span data-ttu-id="84870-133">There are lots of internal GC roots, most of which are not interesting for the users.</span><span class="sxs-lookup"><span data-stu-id="84870-133">There are lots of internal GC roots, most of which are not interesting for the users.</span></span>  <span data-ttu-id="84870-134">From the applications standpoint there are following kinds of roots.</span><span class="sxs-lookup"><span data-stu-id="84870-134">From the applications standpoint there are following kinds of roots.</span></span>  

*   <span data-ttu-id="84870-135">Window global object \(in each iframe\).</span><span class="sxs-lookup"><span data-stu-id="84870-135">Window global object \(in each iframe\).</span></span>  <span data-ttu-id="84870-136">There is a distance field in the heap snapshots which is the number of property references on the shortest retaining path from the window.</span><span class="sxs-lookup"><span data-stu-id="84870-136">There is a distance field in the heap snapshots which is the number of property references on the shortest retaining path from the window.</span></span>  
*   <span data-ttu-id="84870-137">Document DOM tree consisting of all native DOM nodes reachable by traversing the document.</span><span class="sxs-lookup"><span data-stu-id="84870-137">Document DOM tree consisting of all native DOM nodes reachable by traversing the document.</span></span>  <span data-ttu-id="84870-138">Not all of the nodes may have JS wrappers but if a node has a wrapper, it is alive while the document is alive.</span><span class="sxs-lookup"><span data-stu-id="84870-138">Not all of the nodes may have JS wrappers but if a node has a wrapper, it is alive while the document is alive.</span></span>  
*   <span data-ttu-id="84870-139">Sometimes objects may be retained by the debugger context in the **Sources** panel and the **Console** \(for example after Console evaluation\).</span><span class="sxs-lookup"><span data-stu-id="84870-139">Sometimes objects may be retained by the debugger context in the **Sources** panel and the **Console** \(for example after Console evaluation\).</span></span>  <span data-ttu-id="84870-140">Create heap snapshots with a cleared **Console** panel and no active breakpoints in the debugger in the **Sources** panel.</span><span class="sxs-lookup"><span data-stu-id="84870-140">Create heap snapshots with a cleared **Console** panel and no active breakpoints in the debugger in the **Sources** panel.</span></span>

>[!TIP]
> <span data-ttu-id="84870-141">Clear the **Console** panel by running `clear()` and deactivate breakpoints in the **Sources** panel before taking a heap snapshot in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span><span class="sxs-lookup"><span data-stu-id="84870-141">Clear the **Console** panel by running `clear()` and deactivate breakpoints in the **Sources** panel before taking a heap snapshot in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots].</span></span>

<span data-ttu-id="84870-142">The memory graph starts with a root, which may be the `window` object of the browser or the `Global` object of a Node.js module.</span><span class="sxs-lookup"><span data-stu-id="84870-142">The memory graph starts with a root, which may be the `window` object of the browser or the `Global` object of a Node.js module.</span></span>  <span data-ttu-id="84870-143">You do not control how this root object is garbage collected (GCd).</span><span class="sxs-lookup"><span data-stu-id="84870-143">You do not control how this root object is garbage collected (GCd).</span></span>  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="Visual representation of memory" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   <span data-ttu-id="84870-145">You are not able to control how the root object is garbage collected.</span><span class="sxs-lookup"><span data-stu-id="84870-145">You are not able to control how the root object is garbage collected.</span></span>  
:::image-end:::  

<span data-ttu-id="84870-146">Whatever is not reachable from the root gets garbage collected \(GCd\).</span><span class="sxs-lookup"><span data-stu-id="84870-146">Whatever is not reachable from the root gets garbage collected \(GCd\).</span></span>  

> [!NOTE]
> <span data-ttu-id="84870-147">Both the [Shallow size](#shallow-size) and [Retained size](#retained-size) columns represent data in bytes.</span><span class="sxs-lookup"><span data-stu-id="84870-147">Both the [Shallow size](#shallow-size) and [Retained size](#retained-size) columns represent data in bytes.</span></span>  

## <span data-ttu-id="84870-148">Objects retaining tree</span><span class="sxs-lookup"><span data-stu-id="84870-148">Objects retaining tree</span></span>  

<span data-ttu-id="84870-149">The heap is a network of interconnected objects.</span><span class="sxs-lookup"><span data-stu-id="84870-149">The heap is a network of interconnected objects.</span></span>  <span data-ttu-id="84870-150">In the mathematical world, this structure is called a **graph** or memory graph.</span><span class="sxs-lookup"><span data-stu-id="84870-150">In the mathematical world, this structure is called a **graph** or memory graph.</span></span>  <span data-ttu-id="84870-151">A graph is constructed from **nodes** connected by means of **edges**, both of which are given labels.</span><span class="sxs-lookup"><span data-stu-id="84870-151">A graph is constructed from **nodes** connected by means of **edges**, both of which are given labels.</span></span>  

*   <span data-ttu-id="84870-152">**Nodes** \(or **objects**\) are labelled using the name of the **constructor** function that was used to build them.</span><span class="sxs-lookup"><span data-stu-id="84870-152">**Nodes** \(or **objects**\) are labelled using the name of the **constructor** function that was used to build them.</span></span>  
*   <span data-ttu-id="84870-153">**Edges** are labelled using the names of **properties**.</span><span class="sxs-lookup"><span data-stu-id="84870-153">**Edges** are labelled using the names of **properties**.</span></span>  

<span data-ttu-id="84870-154">Learn [how to record a profile using the Heap Profiler][DevtoolsMemoryProblemsHeapSnapshots].</span><span class="sxs-lookup"><span data-stu-id="84870-154">Learn [how to record a profile using the Heap Profiler][DevtoolsMemoryProblemsHeapSnapshots].</span></span>  <span data-ttu-id="84870-155">In the following figure, some of the eye-catching things that you may see in the Heap Snapshot recording in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots] include distance:  the distance from the Garbage Collector \(GC\) root.</span><span class="sxs-lookup"><span data-stu-id="84870-155">In the following figure, some of the eye-catching things that you may see in the Heap Snapshot recording in the [Memory panel][DevtoolsMemoryProblemsHeapSnapshots] include distance:  the distance from the Garbage Collector \(GC\) root.</span></span>  <span data-ttu-id="84870-156">If almost all the objects of the same type are at the same distance, and a few are at a bigger distance, that is something worth investigating.</span><span class="sxs-lookup"><span data-stu-id="84870-156">If almost all the objects of the same type are at the same distance, and a few are at a bigger distance, that is something worth investigating.</span></span>  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="Visual representation of memory" lightbox="../media/memory-problems-root.msft.png":::
   <span data-ttu-id="84870-158">Distance from root</span><span class="sxs-lookup"><span data-stu-id="84870-158">Distance from root</span></span>  
:::image-end:::  

## <span data-ttu-id="84870-159">Dominators</span><span class="sxs-lookup"><span data-stu-id="84870-159">Dominators</span></span>  

<span data-ttu-id="84870-160">Dominator objects are comprised of a tree structure because each object has exactly one dominator.</span><span class="sxs-lookup"><span data-stu-id="84870-160">Dominator objects are comprised of a tree structure because each object has exactly one dominator.</span></span>  <span data-ttu-id="84870-161">A dominator of an object may lack direct references to an object it dominates; that is, the tree of the dominator is not a spanning tree of the graph.</span><span class="sxs-lookup"><span data-stu-id="84870-161">A dominator of an object may lack direct references to an object it dominates; that is, the tree of the dominator is not a spanning tree of the graph.</span></span>  

<span data-ttu-id="84870-162">In the following figure, the following statement are true.</span><span class="sxs-lookup"><span data-stu-id="84870-162">In the following figure, the following statement are true.</span></span>  

*   <span data-ttu-id="84870-163">Node 1 dominates node 2</span><span class="sxs-lookup"><span data-stu-id="84870-163">Node 1 dominates node 2</span></span>  
*   <span data-ttu-id="84870-164">Node 2 dominates nodes 3, 4 and 6</span><span class="sxs-lookup"><span data-stu-id="84870-164">Node 2 dominates nodes 3, 4 and 6</span></span>  
*   <span data-ttu-id="84870-165">Node 3 dominates node 5</span><span class="sxs-lookup"><span data-stu-id="84870-165">Node 3 dominates node 5</span></span>  
*   <span data-ttu-id="84870-166">Node 5 dominates node 8</span><span class="sxs-lookup"><span data-stu-id="84870-166">Node 5 dominates node 8</span></span>  
*   <span data-ttu-id="84870-167">Node 6 dominates node 7</span><span class="sxs-lookup"><span data-stu-id="84870-167">Node 6 dominates node 7</span></span>  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="Visual representation of memory" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   <span data-ttu-id="84870-169">Dominator tree structure</span><span class="sxs-lookup"><span data-stu-id="84870-169">Dominator tree structure</span></span>  
:::image-end:::  

<span data-ttu-id="84870-170">In the following figure, node `#3` is the dominator of `#10`, but `#7` also exists in every simple path from Garbage Collector \(GC\) to `#10`.</span><span class="sxs-lookup"><span data-stu-id="84870-170">In the following figure, node `#3` is the dominator of `#10`, but `#7` also exists in every simple path from Garbage Collector \(GC\) to `#10`.</span></span>  <span data-ttu-id="84870-171">Therefore, an object B is a dominator of an object A if B exists in every simple path from the root to the object A.</span><span class="sxs-lookup"><span data-stu-id="84870-171">Therefore, an object B is a dominator of an object A if B exists in every simple path from the root to the object A.</span></span>  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="Visual representation of memory" lightbox="../media/memory-problems-dominators.msft.gif":::
   <span data-ttu-id="84870-173">Animated dominator illustration</span><span class="sxs-lookup"><span data-stu-id="84870-173">Animated dominator illustration</span></span>  
:::image-end:::  

## <span data-ttu-id="84870-174">V8 specifics</span><span class="sxs-lookup"><span data-stu-id="84870-174">V8 specifics</span></span>  

<span data-ttu-id="84870-175">When profiling memory, it is helpful to understand why heap snapshots look a certain way.</span><span class="sxs-lookup"><span data-stu-id="84870-175">When profiling memory, it is helpful to understand why heap snapshots look a certain way.</span></span>  <span data-ttu-id="84870-176">This section describes some memory-related topics specifically corresponding to the **V8 JavaScript virtual machine** \(V8 VM or VM\).</span><span class="sxs-lookup"><span data-stu-id="84870-176">This section describes some memory-related topics specifically corresponding to the **V8 JavaScript virtual machine** \(V8 VM or VM\).</span></span>  

### <span data-ttu-id="84870-177">JavaScript object representation</span><span class="sxs-lookup"><span data-stu-id="84870-177">JavaScript object representation</span></span>  

<span data-ttu-id="84870-178">There are three primitive types:</span><span class="sxs-lookup"><span data-stu-id="84870-178">There are three primitive types:</span></span>  

*   <span data-ttu-id="84870-179">Numbers \(for example `3.14159...`\)</span><span class="sxs-lookup"><span data-stu-id="84870-179">Numbers \(for example `3.14159...`\)</span></span>  
*   <span data-ttu-id="84870-180">Booleans \(`true` or `false`\)</span><span class="sxs-lookup"><span data-stu-id="84870-180">Booleans \(`true` or `false`\)</span></span>  
*   <span data-ttu-id="84870-181">Strings \(for example `"Werner Heisenberg"`\)</span><span class="sxs-lookup"><span data-stu-id="84870-181">Strings \(for example `"Werner Heisenberg"`\)</span></span>  

<span data-ttu-id="84870-182">Primitives are not able to reference other values and are always leafs or terminating nodes.</span><span class="sxs-lookup"><span data-stu-id="84870-182">Primitives are not able to reference other values and are always leafs or terminating nodes.</span></span>  

<span data-ttu-id="84870-183">**Numbers** are able to be stored as either:</span><span class="sxs-lookup"><span data-stu-id="84870-183">**Numbers** are able to be stored as either:</span></span>  

*   <span data-ttu-id="84870-184">an immediate 31-bit integer values called **small integers** \(**SMI**s\), or</span><span class="sxs-lookup"><span data-stu-id="84870-184">an immediate 31-bit integer values called **small integers** \(**SMI**s\), or</span></span>  
*   <span data-ttu-id="84870-185">heap objects, referred to as **heap numbers**.</span><span class="sxs-lookup"><span data-stu-id="84870-185">heap objects, referred to as **heap numbers**.</span></span> <span data-ttu-id="84870-186">Heap numbers are used for storing values that do not fit into the SMI form, such as **doubles**, or when a value needs to be **boxed**, such as setting properties on it.</span><span class="sxs-lookup"><span data-stu-id="84870-186">Heap numbers are used for storing values that do not fit into the SMI form, such as **doubles**, or when a value needs to be **boxed**, such as setting properties on it.</span></span>  

<span data-ttu-id="84870-187">**Strings** are able to be stored in either:</span><span class="sxs-lookup"><span data-stu-id="84870-187">**Strings** are able to be stored in either:</span></span>  

*   <span data-ttu-id="84870-188">the **VM heap**, or</span><span class="sxs-lookup"><span data-stu-id="84870-188">the **VM heap**, or</span></span>
*   <span data-ttu-id="84870-189">externally in the **memory of the renderer**.</span><span class="sxs-lookup"><span data-stu-id="84870-189">externally in the **memory of the renderer**.</span></span>  <span data-ttu-id="84870-190">A **wrapper object** is created and used for accessing external storage where, for example, script sources and other content that is received from the Web is stored, rather than copied onto the VM heap.</span><span class="sxs-lookup"><span data-stu-id="84870-190">A **wrapper object** is created and used for accessing external storage where, for example, script sources and other content that is received from the Web is stored, rather than copied onto the VM heap.</span></span>

<span data-ttu-id="84870-191">Memory for new JavaScript objects is allocated from a dedicated JavaScript heap \(or **VM heap**\).</span><span class="sxs-lookup"><span data-stu-id="84870-191">Memory for new JavaScript objects is allocated from a dedicated JavaScript heap \(or **VM heap**\).</span></span>  <span data-ttu-id="84870-192">These objects are managed by the garbage collector in V8 and therefore, stay alive as long as there is at least one strong reference to them.</span><span class="sxs-lookup"><span data-stu-id="84870-192">These objects are managed by the garbage collector in V8 and therefore, stay alive as long as there is at least one strong reference to them.</span></span>  

<span data-ttu-id="84870-193">Anything not in the JavaScript heap is called a **native object**.</span><span class="sxs-lookup"><span data-stu-id="84870-193">Anything not in the JavaScript heap is called a **native object**.</span></span>  <span data-ttu-id="84870-194">Native objects, in contrast to heap objects, are not managed by the V8 garbage collector throughout their lifetime, and may only be accessed from JavaScript using the JavaScript wrapper object.</span><span class="sxs-lookup"><span data-stu-id="84870-194">Native objects, in contrast to heap objects, are not managed by the V8 garbage collector throughout their lifetime, and may only be accessed from JavaScript using the JavaScript wrapper object.</span></span>  

<span data-ttu-id="84870-195">**Cons string** is an object that consists of pairs of strings stored and then joined, and is a result of concatenation.</span><span class="sxs-lookup"><span data-stu-id="84870-195">**Cons string** is an object that consists of pairs of strings stored and then joined, and is a result of concatenation.</span></span>  <span data-ttu-id="84870-196">The joining of the **cons string** contents occurs only as needed.</span><span class="sxs-lookup"><span data-stu-id="84870-196">The joining of the **cons string** contents occurs only as needed.</span></span> <span data-ttu-id="84870-197">An example would be when a substring of a joined string needs to be constructed.</span><span class="sxs-lookup"><span data-stu-id="84870-197">An example would be when a substring of a joined string needs to be constructed.</span></span>

<span data-ttu-id="84870-198">For example, if you concatenate `a` and `b`, you get a string `(a, b)` which represents the result of concatenation.</span><span class="sxs-lookup"><span data-stu-id="84870-198">For example, if you concatenate `a` and `b`, you get a string `(a, b)` which represents the result of concatenation.</span></span>  <span data-ttu-id="84870-199">If you later concatenated `d` with that result, you get another **cons string**: `((a, b, d)`.</span><span class="sxs-lookup"><span data-stu-id="84870-199">If you later concatenated `d` with that result, you get another **cons string**: `((a, b, d)`.</span></span>  

<span data-ttu-id="84870-200">**Array** is an object with numeric keys.</span><span class="sxs-lookup"><span data-stu-id="84870-200">**Array** is an object with numeric keys.</span></span> <span data-ttu-id="84870-201">**Arrays** are used extensively in the V8 VM for storing large amounts of data.</span><span class="sxs-lookup"><span data-stu-id="84870-201">**Arrays** are used extensively in the V8 VM for storing large amounts of data.</span></span> <span data-ttu-id="84870-202">Sets of key-value pairs, like dictionaries, are backed up by **arrays**.</span><span class="sxs-lookup"><span data-stu-id="84870-202">Sets of key-value pairs, like dictionaries, are backed up by **arrays**.</span></span>  

<span data-ttu-id="84870-203">A typical JavaScript object is stored as only one of two **array** types:</span><span class="sxs-lookup"><span data-stu-id="84870-203">A typical JavaScript object is stored as only one of two **array** types:</span></span>  

*   <span data-ttu-id="84870-204">named properties, and</span><span class="sxs-lookup"><span data-stu-id="84870-204">named properties, and</span></span>  
*   <span data-ttu-id="84870-205">numeric elements</span><span class="sxs-lookup"><span data-stu-id="84870-205">numeric elements</span></span>  

<span data-ttu-id="84870-206">When there are a small number of properties, the properties are stored internally in the JavaScript object.</span><span class="sxs-lookup"><span data-stu-id="84870-206">When there are a small number of properties, the properties are stored internally in the JavaScript object.</span></span>  

<span data-ttu-id="84870-207">**Map** is an object that describes both the kind of object it is and the layout.</span><span class="sxs-lookup"><span data-stu-id="84870-207">**Map** is an object that describes both the kind of object it is and the layout.</span></span> <span data-ttu-id="84870-208">For example, maps are used to describe implicit object hierarchies for [fast property access][V8FastProperties].</span><span class="sxs-lookup"><span data-stu-id="84870-208">For example, maps are used to describe implicit object hierarchies for [fast property access][V8FastProperties].</span></span>  

### <span data-ttu-id="84870-209">Object groups</span><span class="sxs-lookup"><span data-stu-id="84870-209">Object groups</span></span>  

<span data-ttu-id="84870-210">Each **native objects** group is made up of objects that hold mutual references to each other.</span><span class="sxs-lookup"><span data-stu-id="84870-210">Each **native objects** group is made up of objects that hold mutual references to each other.</span></span>  <span data-ttu-id="84870-211">Consider, for example, a DOM subtree where every node has a link to the relative parent and links to the next child and next sibling, therefore forming a connected graph.</span><span class="sxs-lookup"><span data-stu-id="84870-211">Consider, for example, a DOM subtree where every node has a link to the relative parent and links to the next child and next sibling, therefore forming a connected graph.</span></span>  

> [!NOTE]
> <span data-ttu-id="84870-212">Native objects are not represented in the JavaScript heap.</span><span class="sxs-lookup"><span data-stu-id="84870-212">Native objects are not represented in the JavaScript heap.</span></span>  <span data-ttu-id="84870-213">The lack of representation is why native objects have zero size.</span><span class="sxs-lookup"><span data-stu-id="84870-213">The lack of representation is why native objects have zero size.</span></span> <span data-ttu-id="84870-214">Instead, wrapper objects are created.</span><span class="sxs-lookup"><span data-stu-id="84870-214">Instead, wrapper objects are created.</span></span>  

<span data-ttu-id="84870-215">Each wrapper object holds a reference to the corresponding native object, for redirecting commands to it.</span><span class="sxs-lookup"><span data-stu-id="84870-215">Each wrapper object holds a reference to the corresponding native object, for redirecting commands to it.</span></span>  <span data-ttu-id="84870-216">In turn, an object group holds wrapper objects.</span><span class="sxs-lookup"><span data-stu-id="84870-216">In turn, an object group holds wrapper objects.</span></span>  <span data-ttu-id="84870-217">However, this does not create an uncollectable cycle, as Garbage Collector \(GC\) is smart enough to release object groups whose wrappers are no longer referenced.</span><span class="sxs-lookup"><span data-stu-id="84870-217">However, this does not create an uncollectable cycle, as Garbage Collector \(GC\) is smart enough to release object groups whose wrappers are no longer referenced.</span></span> <span data-ttu-id="84870-218">But forgetting to release a single wrapper holds the whole group and associated wrappers.</span><span class="sxs-lookup"><span data-stu-id="84870-218">But forgetting to release a single wrapper holds the whole group and associated wrappers.</span></span>  

## <span data-ttu-id="84870-219">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="84870-219">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "How to Record Heap Snapshots | Microsoft Docs"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "Fast properties in V8 | V8"  

> [!NOTE]
> <span data-ttu-id="84870-222">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="84870-222">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="84870-223">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span><span class="sxs-lookup"><span data-stu-id="84870-223">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="84870-225">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="84870-225">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
