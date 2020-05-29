---
title: 如何在日程表上使用分配检测
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 04/29/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: ab7a270e1d599e254aaaf4515b6898cb1d9782fc
ms.sourcegitcommit: 50991a04c18283a8890ae33fcc3491c0476c7684
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/30/2020
ms.locfileid: "10611732"
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





# <span data-ttu-id="466ac-103">如何在日程表上使用分配检测</span><span class="sxs-lookup"><span data-stu-id="466ac-103">How to Use Allocation Instrumentation on Timeline</span></span>  



<span data-ttu-id="466ac-104">使用**时间线上的分配检测**查找未正确进行垃圾回收的对象，并继续保留内存。</span><span class="sxs-lookup"><span data-stu-id="466ac-104">Use **Allocation instrumentation on timeline** to find objects that are not being properly garbage collected, and continue to retain memory.</span></span>  

## <span data-ttu-id="466ac-105">时间线上的分配规范的工作原理</span><span class="sxs-lookup"><span data-stu-id="466ac-105">How Allocation instrumentation on timeline works</span></span>  

<span data-ttu-id="466ac-106">**时间线上的分配规范**将**堆探查器**的详细快照信息与**性能**面板的增量更新和跟踪组合在一起。</span><span class="sxs-lookup"><span data-stu-id="466ac-106">**Allocation instrumentation on timeline** combines the detailed snapshot information of the **heap profiler** with the incremental updating and tracking of the **Performance** panel.</span></span>  <span data-ttu-id="466ac-107">同样，针对对象的跟踪堆分配涉及开始录制、执行操作序列和停止录制分析。</span><span class="sxs-lookup"><span data-stu-id="466ac-107">Similarly, tracking heap allocation for objects involves starting a recording, performing a sequence of actions, and stopping the recording for analysis.</span></span>  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

<span data-ttu-id="466ac-108">"**时间线上的分配规范" 在**整个录制过程中定期（每个 50 ms！ \）和最后一个快照（每个 ms！ \）和录制结束时定期执行堆快照。</span><span class="sxs-lookup"><span data-stu-id="466ac-108">**Allocation instrumentation on timeline** takes heap snapshots periodically throughout the recording \(as frequently as every 50 ms!\) and one final snapshot at the end of the recording.</span></span>  

> ##### <span data-ttu-id="466ac-109">图 1</span><span class="sxs-lookup"><span data-stu-id="466ac-109">Figure 1</span></span>  
> **<span data-ttu-id="466ac-110">日程表上的分配规范</span><span class="sxs-lookup"><span data-stu-id="466ac-110">Allocation instrumentation on timeline</span></span>**  
> ![日程表上的分配规范][ImageObjectTracker]  

> [!NOTE]
> <span data-ttu-id="466ac-112">后面的数字 `@` 是一个对象 ID，该对象 ID 持续于录制会话期间拍摄的多个快照中。</span><span class="sxs-lookup"><span data-stu-id="466ac-112">The number after the `@` is an object ID that persists across the multiple snapshots taken during the recording session.</span></span>  <span data-ttu-id="466ac-113">持久性对象 ID 支持堆状态之间的精确比较。</span><span class="sxs-lookup"><span data-stu-id="466ac-113">The persistent object ID enables precise comparison between heap states.</span></span>  <span data-ttu-id="466ac-114">在垃圾回收过程中移动对象，因此显示对象的地址毫无意义。</span><span class="sxs-lookup"><span data-stu-id="466ac-114">Objects are moved during garbage collections, so displaying the address of an object makes no sense.</span></span>  

## <span data-ttu-id="466ac-115">在日程表上启用分配检测</span><span class="sxs-lookup"><span data-stu-id="466ac-115">Enable Allocation Instrumentation on Timeline</span></span>  

<span data-ttu-id="466ac-116">请按照以下步骤开始**在日程表上使用分配检测**。</span><span class="sxs-lookup"><span data-stu-id="466ac-116">Follow these steps to begin using **Allocation instrumentation on timeline**.</span></span>  

1.  <span data-ttu-id="466ac-117">[打开 DevTools][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="466ac-117">[Open the DevTools][DevtoolsOpenIndex].</span></span>  
1.  <span data-ttu-id="466ac-118">打开 "**内存**" 面板，选择 "**时间线上的分配规范**" 单选按钮。</span><span class="sxs-lookup"><span data-stu-id="466ac-118">Open the **Memory** panel, select the **Allocation instrumentation on timeline** radio button.</span></span>  
1.  <span data-ttu-id="466ac-119">开始录制。</span><span class="sxs-lookup"><span data-stu-id="466ac-119">Start recording.</span></span>  

> ##### <span data-ttu-id="466ac-120">图 2</span><span class="sxs-lookup"><span data-stu-id="466ac-120">Figure 2</span></span>  
> <span data-ttu-id="466ac-121">记录堆分配探查器</span><span class="sxs-lookup"><span data-stu-id="466ac-121">Record heap allocations profiler</span></span>  
> ![记录堆分配探查器][ImageRecordHeap]  

## <span data-ttu-id="466ac-123">读取堆分配日程表</span><span class="sxs-lookup"><span data-stu-id="466ac-123">Read a heap allocation timeline</span></span>  

<span data-ttu-id="466ac-124">堆分配时间线显示创建对象的位置并标识保留路径。</span><span class="sxs-lookup"><span data-stu-id="466ac-124">The heap allocation timeline shows where objects are being created and identifies the retaining path.</span></span>  <span data-ttu-id="466ac-125">在[图 3](#figure-3)中，顶部的条指示何时在堆中找到新对象。</span><span class="sxs-lookup"><span data-stu-id="466ac-125">In [Figure 3](#figure-3), the bars at the top indicate when new objects are found in the heap.</span></span>  

<span data-ttu-id="466ac-126">每个条形的高度对应于最近分配的对象的大小，条形图的颜色指示这些对象是否仍在最终堆快照中。</span><span class="sxs-lookup"><span data-stu-id="466ac-126">The height of each bar corresponds to the size of the recently allocated objects, and the color of the bars indicate whether or not those objects are still live in the final heap snapshot.</span></span>  <span data-ttu-id="466ac-127">蓝色条表示在时间线结束时仍处于活动位置的对象，灰色条指示在时间线期间分配但已被垃圾回收的对象。</span><span class="sxs-lookup"><span data-stu-id="466ac-127">Blue bars indicate objects that are still live at the end of the timeline, Gray bars indicate objects that were allocated during the timeline, but have since been garbage collected.</span></span>  

> ##### <span data-ttu-id="466ac-128">图 3</span><span class="sxs-lookup"><span data-stu-id="466ac-128">Figure 3</span></span>  
> <span data-ttu-id="466ac-129">**日程表快照上的分配规范**</span><span class="sxs-lookup"><span data-stu-id="466ac-129">**Allocation instrumentation on timeline** snapshot</span></span>  
> ![日程表快照上的分配规范][ImageCollected]  

<!--In [Figure 4](#figure-4), an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

<span data-ttu-id="466ac-131">你可以使用上面时间线中的滑块缩放到该特定快照，并查看该位置最近分配的对象：</span><span class="sxs-lookup"><span data-stu-id="466ac-131">You are able to use the sliders in the timeline above to zoom into that particular snapshot and see the objects that were recently allocated at that point:</span></span>  

> ##### <span data-ttu-id="466ac-132">图 4</span><span class="sxs-lookup"><span data-stu-id="466ac-132">Figure 4</span></span>  
> <span data-ttu-id="466ac-133">放大到快照</span><span class="sxs-lookup"><span data-stu-id="466ac-133">Zoom into snapshot</span></span>  
> ![放大到快照][ImageSliders]  

<span data-ttu-id="466ac-135">单击堆中的特定对象时，将显示堆快照底部的保留树。</span><span class="sxs-lookup"><span data-stu-id="466ac-135">Clicking on a specific object in the heap shows the retaining tree in the bottom portion of the heap snapshot.</span></span>  <span data-ttu-id="466ac-136">检查对象的保留路径应为你提供足够的信息，以了解未收集对象的原因，你应该更改必要的代码以删除不必要的引用。</span><span class="sxs-lookup"><span data-stu-id="466ac-136">Examining the retaining path to the object should give you enough information to understand why the object was not collected, and you should make the necessary code changes to remove the unnecessary reference.</span></span>  

## <span data-ttu-id="466ac-137">按函数查看内存分配</span><span class="sxs-lookup"><span data-stu-id="466ac-137">View memory allocation by function</span></span>   

<span data-ttu-id="466ac-138">你可以通过 JavaScript 函数查看内存分配。</span><span class="sxs-lookup"><span data-stu-id="466ac-138">You are able to view memory allocation by JavaScript function.</span></span>  <span data-ttu-id="466ac-139">有关详细信息，请参阅[按函数调查内存分配][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。</span><span class="sxs-lookup"><span data-stu-id="466ac-139">See [Investigate memory allocation by function][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction] for more information.</span></span>  

<!--## Feedback   -->  



<!-- image links -->  

[ImageObjectTracker]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png "图1：日程表上的分配规范"  
[ImageRecordHeap]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png "图2：记录堆分配探查器"  
[ImageCollected]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-timelines-snapshot.msft.png "图3：日程表快照上的分配规范"  
[ImageSliders]: /microsoft-edge/devtools-guide-chromium/media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png "图4：放大到快照"  

<!-- links -->  

[DevToolsOpenIndex]: /microsoft-edge/devtools-guide-chromium/open "打开 Microsoft Edge （Chromium） DevTools"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: /microsoft-edge/devtools-guide-chromium/memory-problems/index#investigate-memory-allocation-by-function "通过函数调查内存分配-修复内存问题"  

<!--[HeapProfiler]: ../profile/memory-problems/heap-snapshots ""  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 频道"  

> [!NOTE]
> <span data-ttu-id="466ac-147">此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="466ac-147">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="466ac-148">原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler)，由[Meggin Kearney][MegginKearney] \ （技术作者 \）创作。</span><span class="sxs-lookup"><span data-stu-id="466ac-148">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
<span data-ttu-id="466ac-150">此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="466ac-150">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
