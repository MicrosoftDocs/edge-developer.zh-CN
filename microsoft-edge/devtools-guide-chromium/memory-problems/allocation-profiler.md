---
description: 在日程表上使用分配检测来查找未正确进行垃圾回收的对象，并继续保留内存。
title: 如何在时间线上使用分配检测
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 374b7f0ad80b8975319b2b0ec5cecf42ce4bde82
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397816"
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

# <a name="how-to-use-allocation-instrumentation-on-timeline"></a>如何在时间线上使用分配检测  

在 **日程表上使用分配** 检测来查找未正确进行垃圾回收的对象，并继续保留内存。  

## <a name="how-allocation-instrumentation-on-timeline-works"></a>时间线上的分配检测的工作原理  

**时间线上的分配检测**将堆探查器的详细快照信息与**** 性能面板的增量更新和**跟踪**相结合。  同样，跟踪对象的堆分配涉及启动记录、执行一系列操作以及停止记录进行分析。  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

**时间线上的分配检测** 在整个记录 \ (中定期获取堆快照，频率为每 50 ms\) ，最后一个快照位于录制末尾。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="日程表上的分配检测" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **日程表上的分配检测**  
:::image-end:::  

> [!NOTE]
> 后一 `@` 个数字是对象 ID，在录制会话期间获取的多个快照中保留。  通过永久性对象 ID，可以在堆状态之间进行精确比较。  对象在垃圾回收期间移动，因此显示对象的地址没有任何意义。  

## <a name="enable-allocation-instrumentation-on-timeline"></a>在时间线上启用分配检测  

完成以下操作以开始在时间线**上使用 Allocation instrumentation。**  

1.  [打开 DevTools][DevtoolsOpenIndex]。  
1.  打开内存 **面板** ，选择时间线 **上的分配检测单选** 按钮。  
1.  开始录制。  
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="记录堆分配探查器" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       记录堆分配探查器  
    :::image-end:::  
    
## <a name="read-a-heap-allocation-timeline"></a>读取堆分配时间线  

堆分配时间线显示对象的创建位置，并标识保留路径。  在下图中，顶部的条形指示何时在堆中发现新对象。  

每个栏的高度对应于最近分配的对象的大小，而条形的颜色指示这些对象是否仍位于最终堆快照中。  蓝色条指示仍位于时间线末尾的对象，灰色条指示在时间线期间分配但之后已被垃圾回收的对象。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="时间线快照上的分配检测" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   **时间线快照上的分配** 检测  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple choose actions  -->  

你能够使用上述时间线中的滑块放大该特定快照并查看此时最近分配的对象：  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="放大快照" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   放大快照  
:::image-end:::  

选择堆中的特定对象将显示堆快照底部部分的保留树。  检查对象的保留路径应为您提供足够的信息来了解未收集对象的原因，并且应进行必要的代码更改以删除不必要的引用。  

## <a name="view-memory-allocation-by-function"></a>按功能查看内存分配  

你能够通过 JavaScript 函数查看内存分配。  有关详细信息，请导航到按 [函数 调查内存分配][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "在 DevTools (打开 Microsoft Edge) Chromium |Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "按功能调查内存分配 - 修复内存|Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 渠道"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) ，由 [Meggin Kearney][MegginKearney] \ (Technical Writer\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
