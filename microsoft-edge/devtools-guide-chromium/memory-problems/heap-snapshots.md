---
description: Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.
title: How to Record Heap Snapshots
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web development, f12 tools, devtools
ms.openlocfilehash: 15692b0258de6db66c0b58a2659348a6e849aaca
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10993469"
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

# <span data-ttu-id="62ebb-104">How to record heap snapshots</span><span class="sxs-lookup"><span data-stu-id="62ebb-104">How to record heap snapshots</span></span>  

<span data-ttu-id="62ebb-105">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span><span class="sxs-lookup"><span data-stu-id="62ebb-105">Learn how to record heap snapshots with the Microsoft Edge DevTools heap profiler and find memory leaks.</span></span>  

<span data-ttu-id="62ebb-106">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span><span class="sxs-lookup"><span data-stu-id="62ebb-106">The Microsoft Edge DevTools heap profiler shows memory distribution by the JavaScript objects and related DOM nodes of your page.</span></span>  <span data-ttu-id="62ebb-107">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span><span class="sxs-lookup"><span data-stu-id="62ebb-107">Use it to take JavaScript heap \(JS heap\) snapshots, analyze memory graphs, compare snapshots, and find memory leaks.</span></span>  <span data-ttu-id="62ebb-108">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span><span class="sxs-lookup"><span data-stu-id="62ebb-108">See also [Objects retaining tree][DevtoolsMemoryProblems101ObjectsRetainingTree].</span></span>  

## <span data-ttu-id="62ebb-109">Take a snapshot</span><span class="sxs-lookup"><span data-stu-id="62ebb-109">Take a snapshot</span></span>  

<span data-ttu-id="62ebb-110">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span><span class="sxs-lookup"><span data-stu-id="62ebb-110">On the **Memory** panel, choose **Take snapshot**, then click **Start**.</span></span>  <span data-ttu-id="62ebb-111">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span><span class="sxs-lookup"><span data-stu-id="62ebb-111">You may also press `Ctrl`+`E` \(Windows\) or `Cmd`+`E` \(macOS\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   <span data-ttu-id="62ebb-113">Select profiling type</span><span class="sxs-lookup"><span data-stu-id="62ebb-113">Select profiling type</span></span>  
:::image-end:::  

<span data-ttu-id="62ebb-114">**Snapshots** are initially stored in the renderer process memory.</span><span class="sxs-lookup"><span data-stu-id="62ebb-114">**Snapshots** are initially stored in the renderer process memory.</span></span>  <span data-ttu-id="62ebb-115">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span><span class="sxs-lookup"><span data-stu-id="62ebb-115">Snapshots are transferred to the DevTools on demand, when you click on the snapshot icon to view it.</span></span>  

<span data-ttu-id="62ebb-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span><span class="sxs-lookup"><span data-stu-id="62ebb-116">After the snapshot has been loaded into DevTools and has been parsed, the number below the snapshot title appears and shows the [total size of the reachable JavaScript objects][DevtoolsMemoryProblems101ObjectSizes].</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   <span data-ttu-id="62ebb-118">Total size of reachable objects</span><span class="sxs-lookup"><span data-stu-id="62ebb-118">Total size of reachable objects</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="62ebb-119">Only reachable objects are included in snapshots.</span><span class="sxs-lookup"><span data-stu-id="62ebb-119">Only reachable objects are included in snapshots.</span></span>  <span data-ttu-id="62ebb-120">Also, taking a snapshot always starts with a garbage collection.</span><span class="sxs-lookup"><span data-stu-id="62ebb-120">Also, taking a snapshot always starts with a garbage collection.</span></span>  

## <span data-ttu-id="62ebb-121">Clear snapshots</span><span class="sxs-lookup"><span data-stu-id="62ebb-121">Clear snapshots</span></span>  

<span data-ttu-id="62ebb-122">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span><span class="sxs-lookup"><span data-stu-id="62ebb-122">Click **Clear all profiles** icon to remove snapshots \(both from DevTools and any memory associated with the renderer process\).</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   <span data-ttu-id="62ebb-124">Remove snapshots</span><span class="sxs-lookup"><span data-stu-id="62ebb-124">Remove snapshots</span></span>  
:::image-end:::  

<span data-ttu-id="62ebb-125">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span><span class="sxs-lookup"><span data-stu-id="62ebb-125">Closing the DevTools window does not delete profiles from the memory associated with the renderer process.</span></span>  <span data-ttu-id="62ebb-126">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span><span class="sxs-lookup"><span data-stu-id="62ebb-126">When reopening DevTools, all previously taken snapshots reappear in the list of snapshots.</span></span>  

> [!NOTE]
> <span data-ttu-id="62ebb-127">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span><span class="sxs-lookup"><span data-stu-id="62ebb-127">Try out this example of [scattered objects][GlitchDevtoolsMemoryExample03] and profile it using the Heap Profiler.</span></span>  <span data-ttu-id="62ebb-128">You should see a number of \(object\) item allocations.</span><span class="sxs-lookup"><span data-stu-id="62ebb-128">You should see a number of \(object\) item allocations.</span></span>  

## <span data-ttu-id="62ebb-129">View snapshots</span><span class="sxs-lookup"><span data-stu-id="62ebb-129">View snapshots</span></span>  

<span data-ttu-id="62ebb-130">View snapshots from different perspectives for different tasks.</span><span class="sxs-lookup"><span data-stu-id="62ebb-130">View snapshots from different perspectives for different tasks.</span></span>  

<span data-ttu-id="62ebb-131">**Summary view** shows objects grouped by the constructor name.</span><span class="sxs-lookup"><span data-stu-id="62ebb-131">**Summary view** shows objects grouped by the constructor name.</span></span>  <span data-ttu-id="62ebb-132">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span><span class="sxs-lookup"><span data-stu-id="62ebb-132">Use it to hunt down objects \(and the memory use\) based on type grouped by constructor name.</span></span>  <span data-ttu-id="62ebb-133">It is particularly helpful for **tracking down DOM leaks**.</span><span class="sxs-lookup"><span data-stu-id="62ebb-133">It is particularly helpful for **tracking down DOM leaks**.</span></span>

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

<span data-ttu-id="62ebb-134">**Comparison view**.</span><span class="sxs-lookup"><span data-stu-id="62ebb-134">**Comparison view**.</span></span>  <span data-ttu-id="62ebb-135">Displays the difference between two snapshots.</span><span class="sxs-lookup"><span data-stu-id="62ebb-135">Displays the difference between two snapshots.</span></span>  <span data-ttu-id="62ebb-136">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span><span class="sxs-lookup"><span data-stu-id="62ebb-136">Use it to compare two \(or more\) memory snapshots from before and after an operation.</span></span>  <span data-ttu-id="62ebb-137">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span><span class="sxs-lookup"><span data-stu-id="62ebb-137">Inspecting the delta in freed memory and reference count lets you confirm the presence and cause of a memory leak.</span></span>  

<span data-ttu-id="62ebb-138">**Containment view**.</span><span class="sxs-lookup"><span data-stu-id="62ebb-138">**Containment view**.</span></span>  <span data-ttu-id="62ebb-139">Allows exploration of heap contents.</span><span class="sxs-lookup"><span data-stu-id="62ebb-139">Allows exploration of heap contents.</span></span>  <span data-ttu-id="62ebb-140">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span><span class="sxs-lookup"><span data-stu-id="62ebb-140">**Containment view** provides a better view of object structure, helping analyze objects referenced in the global namespace \(window\) to find out what is keeping objects around.</span></span>  <span data-ttu-id="62ebb-141">Use it to analyze closures and dive into your objects at a low level.</span><span class="sxs-lookup"><span data-stu-id="62ebb-141">Use it to analyze closures and dive into your objects at a low level.</span></span>  

<span data-ttu-id="62ebb-142">To switch between views, use the selector at the top of the view.</span><span class="sxs-lookup"><span data-stu-id="62ebb-142">To switch between views, use the selector at the top of the view.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   <span data-ttu-id="62ebb-144">Switch views selector</span><span class="sxs-lookup"><span data-stu-id="62ebb-144">Switch views selector</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="62ebb-145">Not all properties are stored on the JavaScript heap.</span><span class="sxs-lookup"><span data-stu-id="62ebb-145">Not all properties are stored on the JavaScript heap.</span></span>  <span data-ttu-id="62ebb-146">Properties implemented using getters that run native code are not captured.</span><span class="sxs-lookup"><span data-stu-id="62ebb-146">Properties implemented using getters that run native code are not captured.</span></span>  <span data-ttu-id="62ebb-147">Also, non-string values such as numbers are not captured.</span><span class="sxs-lookup"><span data-stu-id="62ebb-147">Also, non-string values such as numbers are not captured.</span></span>  

### <span data-ttu-id="62ebb-148">Summary view</span><span class="sxs-lookup"><span data-stu-id="62ebb-148">Summary view</span></span>  

<span data-ttu-id="62ebb-149">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span><span class="sxs-lookup"><span data-stu-id="62ebb-149">Initially, a snapshot opens in the Summary view, displaying object totals, which may be expanded to show instances:</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   <span data-ttu-id="62ebb-151">**Summary** view</span><span class="sxs-lookup"><span data-stu-id="62ebb-151">**Summary** view</span></span>  
:::image-end:::  

<span data-ttu-id="62ebb-152">Top-level entries are "total" lines.</span><span class="sxs-lookup"><span data-stu-id="62ebb-152">Top-level entries are "total" lines.</span></span>  

| <span data-ttu-id="62ebb-153">Top-level entries</span><span class="sxs-lookup"><span data-stu-id="62ebb-153">Top-level entries</span></span> | <span data-ttu-id="62ebb-154">Description</span><span class="sxs-lookup"><span data-stu-id="62ebb-154">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="62ebb-155">Constructor</span><span class="sxs-lookup"><span data-stu-id="62ebb-155">Constructor</span></span>** | <span data-ttu-id="62ebb-156">Represents all objects created using this constructor.</span><span class="sxs-lookup"><span data-stu-id="62ebb-156">Represents all objects created using this constructor.</span></span>  |  
| **<span data-ttu-id="62ebb-157">Distance</span><span class="sxs-lookup"><span data-stu-id="62ebb-157">Distance</span></span>** | <span data-ttu-id="62ebb-158">displays the distance to the root using the shortest simple path of nodes.</span><span class="sxs-lookup"><span data-stu-id="62ebb-158">displays the distance to the root using the shortest simple path of nodes.</span></span>  |  
| **<span data-ttu-id="62ebb-159">Shallow size</span><span class="sxs-lookup"><span data-stu-id="62ebb-159">Shallow size</span></span>** | <span data-ttu-id="62ebb-160">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span><span class="sxs-lookup"><span data-stu-id="62ebb-160">Displays the sum of shallow sizes of all objects created by a certain constructor function.</span></span>  <span data-ttu-id="62ebb-161">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span><span class="sxs-lookup"><span data-stu-id="62ebb-161">The shallow size is the size of memory held by an object \(generally, arrays and strings have larger shallow sizes\).</span></span>  <span data-ttu-id="62ebb-162">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span><span class="sxs-lookup"><span data-stu-id="62ebb-162">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  
| **<span data-ttu-id="62ebb-163">Retained size</span><span class="sxs-lookup"><span data-stu-id="62ebb-163">Retained size</span></span>** | <span data-ttu-id="62ebb-164">Displays the maximum retained size among the same set of objects.</span><span class="sxs-lookup"><span data-stu-id="62ebb-164">Displays the maximum retained size among the same set of objects.</span></span>  <span data-ttu-id="62ebb-165">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span><span class="sxs-lookup"><span data-stu-id="62ebb-165">The size of memory that you are able to free after an object is deleted \(and the dependents are made no longer reachable\) is called the retained size.</span></span>  <span data-ttu-id="62ebb-166">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span><span class="sxs-lookup"><span data-stu-id="62ebb-166">See also [Object sizes][DevtoolsMemoryProblems101ObjectSizes].</span></span>  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

<span data-ttu-id="62ebb-167">After expanding a total line in the upper view, all of the instances are displayed.</span><span class="sxs-lookup"><span data-stu-id="62ebb-167">After expanding a total line in the upper view, all of the instances are displayed.</span></span>  <span data-ttu-id="62ebb-168">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span><span class="sxs-lookup"><span data-stu-id="62ebb-168">For each instance, the shallow and retained sizes are displayed in the corresponding columns.</span></span>  <span data-ttu-id="62ebb-169">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span><span class="sxs-lookup"><span data-stu-id="62ebb-169">The number after the `@` character is the unique ID of the object, allowing you to compare heap snapshots on per-object basis.</span></span>  

<span data-ttu-id="62ebb-170">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span><span class="sxs-lookup"><span data-stu-id="62ebb-170">Remember that yellow objects have JavaScript references and red objects are detached nodes which are referenced from one with a yellow background.</span></span>  

**<span data-ttu-id="62ebb-171">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span><span class="sxs-lookup"><span data-stu-id="62ebb-171">What do the various constructor \(group\) entries in the Heap profiler correspond to?</span></span>**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   <span data-ttu-id="62ebb-173">**Constructor** groups</span><span class="sxs-lookup"><span data-stu-id="62ebb-173">**Constructor** groups</span></span>  
:::image-end:::  

| <span data-ttu-id="62ebb-174">Constructor \(group\) entry</span><span class="sxs-lookup"><span data-stu-id="62ebb-174">Constructor \(group\) entry</span></span> | <span data-ttu-id="62ebb-175">Description</span><span class="sxs-lookup"><span data-stu-id="62ebb-175">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="62ebb-176">\(global property\)</span><span class="sxs-lookup"><span data-stu-id="62ebb-176">\(global property\)</span></span>** | <span data-ttu-id="62ebb-177">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span><span class="sxs-lookup"><span data-stu-id="62ebb-177">The intermediate objects between a global object \(like `window`\) and an object referenced by it.</span></span>  <span data-ttu-id="62ebb-178">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span><span class="sxs-lookup"><span data-stu-id="62ebb-178">If an object is created using a constructor `Person` and is held by a global object, the retaining path would look like `[global] > \(global property\) > Person`.</span></span>  <span data-ttu-id="62ebb-179">This contrasts with the norm, where objects directly reference each other.</span><span class="sxs-lookup"><span data-stu-id="62ebb-179">This contrasts with the norm, where objects directly reference each other.</span></span>  <span data-ttu-id="62ebb-180">Intermediate objects exist for performance reasons.</span><span class="sxs-lookup"><span data-stu-id="62ebb-180">Intermediate objects exist for performance reasons.</span></span>  <span data-ttu-id="62ebb-181">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span><span class="sxs-lookup"><span data-stu-id="62ebb-181">Globals are modified regularly and property access optimizations do a good job for non-global objects are not applicable for globals.</span></span>  |  
| **<span data-ttu-id="62ebb-182">\(roots\)</span><span class="sxs-lookup"><span data-stu-id="62ebb-182">\(roots\)</span></span>** | <span data-ttu-id="62ebb-183">The root entries in the retaining tree view are the entities that have references to the selected object.</span><span class="sxs-lookup"><span data-stu-id="62ebb-183">The root entries in the retaining tree view are the entities that have references to the selected object.</span></span>  <span data-ttu-id="62ebb-184">The entries may also be references created by the engine for engine-specific purposes.</span><span class="sxs-lookup"><span data-stu-id="62ebb-184">The entries may also be references created by the engine for engine-specific purposes.</span></span>  <span data-ttu-id="62ebb-185">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span><span class="sxs-lookup"><span data-stu-id="62ebb-185">The engine has caches which reference objects, but all such references are weak and do not prevent an object from being collected given that there are no truly strong references.</span></span>  |  
| **<span data-ttu-id="62ebb-186">\(closure\)</span><span class="sxs-lookup"><span data-stu-id="62ebb-186">\(closure\)</span></span>** | <span data-ttu-id="62ebb-187">A count of references to a group of objects through function closures.</span><span class="sxs-lookup"><span data-stu-id="62ebb-187">A count of references to a group of objects through function closures.</span></span>  |  
| **<span data-ttu-id="62ebb-188">\(array, string, number, regexp\)</span><span class="sxs-lookup"><span data-stu-id="62ebb-188">\(array, string, number, regexp\)</span></span>** | <span data-ttu-id="62ebb-189">A list of object types with properties which reference an Array, String, Number, or regular expression.</span><span class="sxs-lookup"><span data-stu-id="62ebb-189">A list of object types with properties which reference an Array, String, Number, or regular expression.</span></span>  |  
| **<span data-ttu-id="62ebb-190">\(compiled code\)</span><span class="sxs-lookup"><span data-stu-id="62ebb-190">\(compiled code\)</span></span>** | <span data-ttu-id="62ebb-191">Everything related to compiled code.</span><span class="sxs-lookup"><span data-stu-id="62ebb-191">Everything related to compiled code.</span></span>  <span data-ttu-id="62ebb-192">Script is similar to a function, but corresponds to a `<script>` body.</span><span class="sxs-lookup"><span data-stu-id="62ebb-192">Script is similar to a function, but corresponds to a `<script>` body.</span></span>  <span data-ttu-id="62ebb-193">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span><span class="sxs-lookup"><span data-stu-id="62ebb-193">SharedFunctionInfos \(SFI\) are objects standing between functions and compiled code.</span></span>  <span data-ttu-id="62ebb-194">Functions usually have a context, while SFIs do not.</span><span class="sxs-lookup"><span data-stu-id="62ebb-194">Functions usually have a context, while SFIs do not.</span></span>  |  
| <span data-ttu-id="62ebb-195">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span><span class="sxs-lookup"><span data-stu-id="62ebb-195">**HTMLDivElement**, **HTMLAnchorElement**, **DocumentFragment**, and so on.</span></span>  | <span data-ttu-id="62ebb-196">References to elements or document objects of a particular type referenced by your code.</span><span class="sxs-lookup"><span data-stu-id="62ebb-196">References to elements or document objects of a particular type referenced by your code.</span></span>  |  

<!--todo: add heap profiling summary section when available -->  

### <span data-ttu-id="62ebb-197">Comparison view</span><span class="sxs-lookup"><span data-stu-id="62ebb-197">Comparison view</span></span>  

<span data-ttu-id="62ebb-198">Find leaked objects by comparing multiple snapshots to each other.</span><span class="sxs-lookup"><span data-stu-id="62ebb-198">Find leaked objects by comparing multiple snapshots to each other.</span></span>  <span data-ttu-id="62ebb-199">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span><span class="sxs-lookup"><span data-stu-id="62ebb-199">To verify that a certain application operation does not create leaks \(for example, usually a pair of direct and reverse operations, like opening a document, and then closing it, should not leave any garbage\), you may follow the scenario below:</span></span>  

1.  <span data-ttu-id="62ebb-200">Take a heap snapshot before performing an operation.</span><span class="sxs-lookup"><span data-stu-id="62ebb-200">Take a heap snapshot before performing an operation.</span></span>  
1.  <span data-ttu-id="62ebb-201">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span><span class="sxs-lookup"><span data-stu-id="62ebb-201">Perform an operation \(interact with a page in some way that you believe to be causing a leak\).</span></span>  
1.  <span data-ttu-id="62ebb-202">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span><span class="sxs-lookup"><span data-stu-id="62ebb-202">Perform a reverse operation \(do the opposite interaction and repeat it a few times\).</span></span>  
1.  <span data-ttu-id="62ebb-203">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span><span class="sxs-lookup"><span data-stu-id="62ebb-203">Take a second heap snapshot and change the view of this one to **Comparison**, comparing it to **Snapshot 1**.</span></span>  
    
<span data-ttu-id="62ebb-204">In the **Comparison** view, the difference between two snapshots is displayed.</span><span class="sxs-lookup"><span data-stu-id="62ebb-204">In the **Comparison** view, the difference between two snapshots is displayed.</span></span>  <span data-ttu-id="62ebb-205">When expanding a total entry, added and deleted object instances are shown.</span><span class="sxs-lookup"><span data-stu-id="62ebb-205">When expanding a total entry, added and deleted object instances are shown.</span></span>  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   <span data-ttu-id="62ebb-207">**Comparison** view</span><span class="sxs-lookup"><span data-stu-id="62ebb-207">**Comparison** view</span></span>  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <span data-ttu-id="62ebb-208">Containment view</span><span class="sxs-lookup"><span data-stu-id="62ebb-208">Containment view</span></span>  

<span data-ttu-id="62ebb-209">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span><span class="sxs-lookup"><span data-stu-id="62ebb-209">The **Containment** view is essentially a "bird's eye view" of the objects structure of your application.</span></span>  <span data-ttu-id="62ebb-210">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span><span class="sxs-lookup"><span data-stu-id="62ebb-210">It allows you to peek inside function closures, to observe virtual machine \(VM\) internal objects that together make up your JavaScript objects, and to understand how much memory your application uses at a very low level.</span></span>  

| <span data-ttu-id="62ebb-211">Containment view entry points</span><span class="sxs-lookup"><span data-stu-id="62ebb-211">Containment view entry points</span></span> | <span data-ttu-id="62ebb-212">Description</span><span class="sxs-lookup"><span data-stu-id="62ebb-212">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="62ebb-213">DOMWindow objects</span><span class="sxs-lookup"><span data-stu-id="62ebb-213">DOMWindow objects</span></span>** | <span data-ttu-id="62ebb-214">Global objects for JavaScript code.</span><span class="sxs-lookup"><span data-stu-id="62ebb-214">Global objects for JavaScript code.</span></span>  |  
| **<span data-ttu-id="62ebb-215">GC roots</span><span class="sxs-lookup"><span data-stu-id="62ebb-215">GC roots</span></span>** | <span data-ttu-id="62ebb-216">The actual GC roots used by the garbage of the VM.</span><span class="sxs-lookup"><span data-stu-id="62ebb-216">The actual GC roots used by the garbage of the VM.</span></span>  <span data-ttu-id="62ebb-217">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span><span class="sxs-lookup"><span data-stu-id="62ebb-217">GC roots are comprised of built-in object maps, symbol tables, VM thread stacks, compilation caches, handle scopes, and global handles.</span></span>  |  
| **<span data-ttu-id="62ebb-218">Native objects</span><span class="sxs-lookup"><span data-stu-id="62ebb-218">Native objects</span></span>** | <span data-ttu-id="62ebb-219">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span><span class="sxs-lookup"><span data-stu-id="62ebb-219">Browser objects "pushed" inside the JavaScript virtual machine \(JavaScript VM\) to allow automation, for example, DOM nodes, CSS rules.</span></span>  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   <span data-ttu-id="62ebb-221">**Containment** view</span><span class="sxs-lookup"><span data-stu-id="62ebb-221">**Containment** view</span></span>  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> <span data-ttu-id="62ebb-222">A tip about closures.</span><span class="sxs-lookup"><span data-stu-id="62ebb-222">A tip about closures.</span></span>  <span data-ttu-id="62ebb-223">Name the functions so you are able to easily distinguish between closures in the snapshot.</span><span class="sxs-lookup"><span data-stu-id="62ebb-223">Name the functions so you are able to easily distinguish between closures in the snapshot.</span></span>  <span data-ttu-id="62ebb-224">For example, this example does not use named functions.</span><span class="sxs-lookup"><span data-stu-id="62ebb-224">For example, this example does not use named functions.</span></span>  
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
> <span data-ttu-id="62ebb-225">The followingcode snippet uses named functions.</span><span class="sxs-lookup"><span data-stu-id="62ebb-225">The followingcode snippet uses named functions.</span></span>  
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
> :::image type="complex" source="../media/memory-problems-domleaks.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-domleaks.msft.png":::
>    Name functions to distinguish between closures  
> :::image-end:::  
> -->  
> 
> > [!NOTE]
> > <span data-ttu-id="62ebb-226">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span><span class="sxs-lookup"><span data-stu-id="62ebb-226">Try out this example of [why `eval` is evil][GlitchDevtoolsMemoryExample07] to analyze the impact of closures on memory.</span></span>  <span data-ttu-id="62ebb-227">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span><span class="sxs-lookup"><span data-stu-id="62ebb-227">You may also be interested in following it up with this example that takes you through recording [heap allocations][GlitchDevtoolsMemoryExample08].</span></span>  
> 

## <span data-ttu-id="62ebb-228">Look up color coding</span><span class="sxs-lookup"><span data-stu-id="62ebb-228">Look up color coding</span></span>  

<span data-ttu-id="62ebb-229">Properties and property values of objects have different types and are colored accordingly.</span><span class="sxs-lookup"><span data-stu-id="62ebb-229">Properties and property values of objects have different types and are colored accordingly.</span></span>  <span data-ttu-id="62ebb-230">Each property has one of four types.</span><span class="sxs-lookup"><span data-stu-id="62ebb-230">Each property has one of four types.</span></span>  

| <span data-ttu-id="62ebb-231">Property Type</span><span class="sxs-lookup"><span data-stu-id="62ebb-231">Property Type</span></span> | <span data-ttu-id="62ebb-232">Description</span><span class="sxs-lookup"><span data-stu-id="62ebb-232">Description</span></span> |  
|:--- |:--- |  
| **<span data-ttu-id="62ebb-233">a: property</span><span class="sxs-lookup"><span data-stu-id="62ebb-233">a: property</span></span>** | <span data-ttu-id="62ebb-234">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span><span class="sxs-lookup"><span data-stu-id="62ebb-234">A regular property with a name, accessed via the `.` \(dot\) operator, or via `[` `]` \(brackets\) notation, for example `["foo bar"]`.</span></span>  |  
| **<span data-ttu-id="62ebb-235">0: element</span><span class="sxs-lookup"><span data-stu-id="62ebb-235">0: element</span></span>** | <span data-ttu-id="62ebb-236">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span><span class="sxs-lookup"><span data-stu-id="62ebb-236">A regular property with a numeric index, accessed via `[` `]` \(brackets\) notation.</span></span>  |  
| **<span data-ttu-id="62ebb-237">a: context var</span><span class="sxs-lookup"><span data-stu-id="62ebb-237">a: context var</span></span>** |  <span data-ttu-id="62ebb-238">A variable in a function context, accessible by the variable name from inside a function closure.</span><span class="sxs-lookup"><span data-stu-id="62ebb-238">A variable in a function context, accessible by the variable name from inside a function closure.</span></span>  |  
| **<span data-ttu-id="62ebb-239">a: system prop</span><span class="sxs-lookup"><span data-stu-id="62ebb-239">a: system prop</span></span>** | <span data-ttu-id="62ebb-240">A property added by the JavaScript VM, not accessible from JavaScript code.</span><span class="sxs-lookup"><span data-stu-id="62ebb-240">A property added by the JavaScript VM, not accessible from JavaScript code.</span></span>  |  

<span data-ttu-id="62ebb-241">Objects designated as `System` do not have a corresponding JavaScript type.</span><span class="sxs-lookup"><span data-stu-id="62ebb-241">Objects designated as `System` do not have a corresponding JavaScript type.</span></span>  <span data-ttu-id="62ebb-242">Each is part of the object system implementation of the Javascript VM.</span><span class="sxs-lookup"><span data-stu-id="62ebb-242">Each is part of the object system implementation of the Javascript VM.</span></span>  <span data-ttu-id="62ebb-243">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span><span class="sxs-lookup"><span data-stu-id="62ebb-243">V8 allocates most of the internal objects in the same heap as the user's JS objects.</span></span>  <span data-ttu-id="62ebb-244">So these are just V8 internals.</span><span class="sxs-lookup"><span data-stu-id="62ebb-244">So these are just V8 internals.</span></span>  

## <span data-ttu-id="62ebb-245">Find a specific object</span><span class="sxs-lookup"><span data-stu-id="62ebb-245">Find a specific object</span></span>  

<span data-ttu-id="62ebb-246">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span><span class="sxs-lookup"><span data-stu-id="62ebb-246">To find an object in the collected heap you may search using `Ctrl`+`F` and give the object ID.</span></span>  

## <span data-ttu-id="62ebb-247">Uncover DOM leaks</span><span class="sxs-lookup"><span data-stu-id="62ebb-247">Uncover DOM leaks</span></span>  

<span data-ttu-id="62ebb-248">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span><span class="sxs-lookup"><span data-stu-id="62ebb-248">The heap profiler has the ability to reflect bidirectional dependencies between browser native objects \(DOM nodes, CSS rules\) and JavaScript objects.</span></span>
<span data-ttu-id="62ebb-249">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span><span class="sxs-lookup"><span data-stu-id="62ebb-249">This helps to discover otherwise invisible leaks happening due to forgotten detached DOM subtrees floating around.</span></span>  

<span data-ttu-id="62ebb-250">DOM leaks may be bigger than you think.</span><span class="sxs-lookup"><span data-stu-id="62ebb-250">DOM leaks may be bigger than you think.</span></span>  <span data-ttu-id="62ebb-251">Consider the following sample.</span><span class="sxs-lookup"><span data-stu-id="62ebb-251">Consider the following sample.</span></span>  <span data-ttu-id="62ebb-252">When is the #tree GC?</span><span class="sxs-lookup"><span data-stu-id="62ebb-252">When is the #tree GC?</span></span>  

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

<span data-ttu-id="62ebb-253">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span><span class="sxs-lookup"><span data-stu-id="62ebb-253">The `#leaf` maintains a reference to the relevant parent \(parentNode\) and recursively up to `#tree`, so only when leafRef is nullified is the WHOLE tree under `#tree` a candidate for GC.</span></span>  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="Select profiling type" lightbox="../media/memory-problems-tree-gc.msft.png":::
   <span data-ttu-id="62ebb-255">DOM subtrees</span><span class="sxs-lookup"><span data-stu-id="62ebb-255">DOM subtrees</span></span>  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="62ebb-256">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span><span class="sxs-lookup"><span data-stu-id="62ebb-256">Examples:  Try this example of a [leaking DOM node][GlitchDevtoolsMemoryExample06] to understand where it may leak and how to detect it.</span></span>  <span data-ttu-id="62ebb-257">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span><span class="sxs-lookup"><span data-stu-id="62ebb-257">You may also look at this example of [DOM leaks being bigger than expected][GlitchDevtoolsMemoryExample09].</span></span>  

<span data-ttu-id="62ebb-258">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span><span class="sxs-lookup"><span data-stu-id="62ebb-258">To read more about DOM leaks and memory analysis fundamentals checkout [Finding and debugging memory leaks with the Microsoft Edge DevTools][GonzaloRuizdeVillaMemory] by Gonzalo Ruiz de Villa.</span></span>  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <span data-ttu-id="62ebb-259">Getting in touch with the Microsoft Edge DevTools team</span><span class="sxs-lookup"><span data-stu-id="62ebb-259">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "Object sizes - Memory Terminology | Microsoft Docs"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "Objects retaining tree - Memory Terminology | Microsoft Docs"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html - Microsoft Edge (Chromium) DevTools | Glitch"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html - Microsoft Edge (Chromium) DevTools | Glitch"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html - Microsoft Edge (Chromium) DevTools | Glitch"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html - Microsoft Edge (Chromium) DevTools | Glitch"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html - Microsoft Edge (Chromium) DevTools | Glitch"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html - Microsoft Edge (Chromium) DevTools | Glitch"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "memory | Slides"  

> [!NOTE]
> <span data-ttu-id="62ebb-269">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="62ebb-269">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="62ebb-270">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span><span class="sxs-lookup"><span data-stu-id="62ebb-270">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="62ebb-272">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="62ebb-272">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
