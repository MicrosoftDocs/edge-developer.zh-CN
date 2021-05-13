---
description: 在日程表上使用分配检测来查找未正确进行垃圾回收的对象，并继续保留内存。
title: 如何在时间线上使用分配检测
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: a02249840256b1e5a2469a253d765eb888527662
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11564082"
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
# <a name="how-to-use-allocation-instrumentation-on-timeline"></a><span data-ttu-id="60c84-104">如何在时间线上使用分配检测</span><span class="sxs-lookup"><span data-stu-id="60c84-104">How to use Allocation instrumentation on Timeline</span></span>  

<span data-ttu-id="60c84-105">在 **日程表上使用分配** 检测来查找未正确进行垃圾回收的对象，并继续保留内存。</span><span class="sxs-lookup"><span data-stu-id="60c84-105">Use **Allocation instrumentation on timeline** to find objects that are not being properly garbage collected, and continue to retain memory.</span></span>  

## <a name="how-allocation-instrumentation-on-timeline-works"></a><span data-ttu-id="60c84-106">时间线上的分配检测的工作原理</span><span class="sxs-lookup"><span data-stu-id="60c84-106">How Allocation instrumentation on timeline works</span></span>  

<span data-ttu-id="60c84-107">**时间线上的分配检测**将堆探查器的详细快照信息与\*\*\*\* 性能面板的增量更新和**跟踪**相结合。</span><span class="sxs-lookup"><span data-stu-id="60c84-107">**Allocation instrumentation on timeline** combines the detailed snapshot information of the **heap profiler** with the incremental updating and tracking of the **Performance** panel.</span></span>  <span data-ttu-id="60c84-108">同样，跟踪对象的堆分配涉及启动记录、执行一系列操作以及停止记录进行分析。</span><span class="sxs-lookup"><span data-stu-id="60c84-108">Similarly, tracking heap allocation for objects involves starting a recording, performing a sequence of actions, and stopping the recording for analysis.</span></span>  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

<span data-ttu-id="60c84-109">**时间线上的分配检测** 在整个记录 \ (中定期获取堆快照，频率为每 50 ms\) ，最后一个快照位于录制末尾。</span><span class="sxs-lookup"><span data-stu-id="60c84-109">**Allocation instrumentation on timeline** takes heap snapshots periodically throughout the recording \(as frequently as every 50 ms\) and one final snapshot at the end of the recording.</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="日程表上的分配检测" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **<span data-ttu-id="60c84-111">日程表上的分配检测</span><span class="sxs-lookup"><span data-stu-id="60c84-111">Allocation instrumentation on timeline</span></span>**  
:::image-end:::  

> [!NOTE]
> <span data-ttu-id="60c84-112">后一 `@` 个数字是对象 ID，在录制会话期间获取的多个快照中保留。</span><span class="sxs-lookup"><span data-stu-id="60c84-112">The number after the `@` is an object ID that persists across the multiple snapshots taken during the recording session.</span></span>  <span data-ttu-id="60c84-113">通过永久性对象 ID，可以在堆状态之间进行精确比较。</span><span class="sxs-lookup"><span data-stu-id="60c84-113">The persistent object ID enables precise comparison between heap states.</span></span>  <span data-ttu-id="60c84-114">对象在垃圾回收期间移动，因此显示对象的地址没有任何意义。</span><span class="sxs-lookup"><span data-stu-id="60c84-114">Objects are moved during garbage collections, so displaying the address of an object makes no sense.</span></span>  

## <a name="enable-allocation-instrumentation-on-timeline"></a><span data-ttu-id="60c84-115">在时间线上启用分配检测</span><span class="sxs-lookup"><span data-stu-id="60c84-115">Enable Allocation Instrumentation on Timeline</span></span>  

<span data-ttu-id="60c84-116">完成以下操作以开始在时间线**上使用 Allocation instrumentation。**</span><span class="sxs-lookup"><span data-stu-id="60c84-116">Complete the following actions to begin using **Allocation instrumentation on timeline**.</span></span>  

1.  <span data-ttu-id="60c84-117">[打开 DevTools][DevtoolsOpenIndex]。</span><span class="sxs-lookup"><span data-stu-id="60c84-117">[Open the DevTools][DevtoolsOpenIndex].</span></span>  
1.  <span data-ttu-id="60c84-118">打开内存 **面板** ，选择时间线 **上的分配检测单选** 按钮。</span><span class="sxs-lookup"><span data-stu-id="60c84-118">Open the **Memory** panel, select the **Allocation instrumentation on timeline** radio button.</span></span>  
1.  <span data-ttu-id="60c84-119">开始录制。</span><span class="sxs-lookup"><span data-stu-id="60c84-119">Start recording.</span></span>  
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="记录堆分配探查器" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       <span data-ttu-id="60c84-121">记录堆分配探查器</span><span class="sxs-lookup"><span data-stu-id="60c84-121">Record heap allocations profiler</span></span>  
    :::image-end:::  
    
## <a name="read-a-heap-allocation-timeline"></a><span data-ttu-id="60c84-122">读取堆分配时间线</span><span class="sxs-lookup"><span data-stu-id="60c84-122">Read a heap allocation timeline</span></span>  

<span data-ttu-id="60c84-123">堆分配时间线显示对象的创建位置，并标识保留路径。</span><span class="sxs-lookup"><span data-stu-id="60c84-123">The heap allocation timeline shows where objects are being created and identifies the retaining path.</span></span>  <span data-ttu-id="60c84-124">在下图中，顶部的条形指示何时在堆中发现新对象。</span><span class="sxs-lookup"><span data-stu-id="60c84-124">In the following figure, the bars at the top indicate when new objects are found in the heap.</span></span>  

<span data-ttu-id="60c84-125">每个栏的高度对应于最近分配的对象的大小，而条形的颜色指示这些对象是否仍位于最终堆快照中。</span><span class="sxs-lookup"><span data-stu-id="60c84-125">The height of each bar corresponds to the size of the recently allocated objects, and the color of the bars indicate whether or not those objects are still live in the final heap snapshot.</span></span>  <span data-ttu-id="60c84-126">蓝色条指示仍位于时间线末尾的对象，灰色条指示在时间线期间分配但之后已被垃圾回收的对象。</span><span class="sxs-lookup"><span data-stu-id="60c84-126">Blue bars indicate objects that are still live at the end of the timeline, Gray bars indicate objects that were allocated during the timeline, but have since been garbage collected.</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="时间线快照上的分配检测" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   <span data-ttu-id="60c84-128">**时间线快照上的分配** 检测</span><span class="sxs-lookup"><span data-stu-id="60c84-128">**Allocation instrumentation on timeline** snapshot</span></span>  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple choose actions  -->  

<span data-ttu-id="60c84-129">你能够使用上述时间线中的滑块放大该特定快照并查看此时最近分配的对象：</span><span class="sxs-lookup"><span data-stu-id="60c84-129">You are able to use the sliders in the timeline above to zoom into that particular snapshot and review the objects that were recently allocated at that point:</span></span>  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="放大快照" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   <span data-ttu-id="60c84-131">放大快照</span><span class="sxs-lookup"><span data-stu-id="60c84-131">Zoom into snapshot</span></span>  
:::image-end:::  

<span data-ttu-id="60c84-132">选择堆中的特定对象将显示堆快照底部部分的保留树。</span><span class="sxs-lookup"><span data-stu-id="60c84-132">Choosing on a specific object in the heap shows the retaining tree in the bottom portion of the heap snapshot.</span></span>  <span data-ttu-id="60c84-133">检查对象的保留路径应为您提供足够的信息来了解未收集对象的原因，并且应进行必要的代码更改以删除不必要的引用。</span><span class="sxs-lookup"><span data-stu-id="60c84-133">Examining the retaining path to the object should give you enough information to understand why the object was not collected, and you should make the necessary code changes to remove the unnecessary reference.</span></span>  

## <a name="view-memory-allocation-by-function"></a><span data-ttu-id="60c84-134">按功能查看内存分配</span><span class="sxs-lookup"><span data-stu-id="60c84-134">View memory allocation by function</span></span>  

<span data-ttu-id="60c84-135">你能够通过 JavaScript 函数查看内存分配。</span><span class="sxs-lookup"><span data-stu-id="60c84-135">You are able to view memory allocation by JavaScript function.</span></span>  <span data-ttu-id="60c84-136">有关详细信息，请导航到按 [函数 调查内存分配][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。</span><span class="sxs-lookup"><span data-stu-id="60c84-136">For more information, navigate to [Investigate memory allocation by function][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction].</span></span>  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a><span data-ttu-id="60c84-137">联系 Microsoft Edge DevTools 团队</span><span class="sxs-lookup"><span data-stu-id="60c84-137">Getting in touch with the Microsoft Edge DevTools team</span></span>  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "打开Microsoft Edge (Chromium) DevTools |Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "按功能调查内存分配 - 修复内存|Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "下载Microsoft Edge频道"  

> [!NOTE]
> <span data-ttu-id="60c84-141">此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。</span><span class="sxs-lookup"><span data-stu-id="60c84-141">Portions of this page are modifications based on work created and [shared by Google][GoogleSitePolicies] and used according to terms described in the [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  
> <span data-ttu-id="60c84-142">原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) ，由 [Meggin Kearney][MegginKearney] \ (Technical Writer\) 。</span><span class="sxs-lookup"><span data-stu-id="60c84-142">The original page is found [here](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) and is authored by [Meggin Kearney][MegginKearney] \(Technical Writer\).</span></span>  

[![Creative Commons License][CCby4Image]][CCA4IL]  
<span data-ttu-id="60c84-144">本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。</span><span class="sxs-lookup"><span data-stu-id="60c84-144">This work is licensed under a [Creative Commons Attribution 4.0 International License][CCA4IL].</span></span>  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
