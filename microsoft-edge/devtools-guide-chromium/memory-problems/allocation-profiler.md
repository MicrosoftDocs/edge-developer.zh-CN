---
description: 使用时间线上的分配检测查找未正确垃圾回收的对象，并继续保留内存。
title: 如何在日程表上使用分配检测
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 946c2d8b45f316b491a604c16c37bb2467983222
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230913"
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

# 如何在时间线上使用分配检测  

使用 **时间线上的分配检测** 查找未正确垃圾回收的对象，并继续保留内存。  

## 日程表上的分配检测的工作原理  

**时间线上的分配检测** 将堆配置文件 **器** 的详细快照信息与性能面板的增量更新和 **跟踪** 相结合。  同样，跟踪对象的堆分配涉及启动记录、执行一系列操作以及停止记录进行分析。  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

**时间线上的分配检测** 在整个录制 \ (定期获取堆快照，频率与记录末尾每 50 毫秒) 一次快照的频率一样。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png" alt-text="时间线上的分配检测" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted.msft.png":::
   **时间线上的分配检测**  
:::image-end:::  

> [!NOTE]
> The number after `@` is an object ID that persists across the multiple snapshots taken during the recording session.  持久对象 ID 支持堆栈状态之间的精确比较。  对象在垃圾回收过程中移动，因此显示对象的地址没有任何意义。  

## 在时间线上启用分配检测  

完成以下操作以在时间线 **上开始使用分配检测**。  

1.  [打开 DevTools][DevtoolsOpenIndex]。  
1.  打开内存 **面板** ，选择日程表 **单选按钮上的分配** 检测。  
1.  开始录制。  
    
    :::image type="complex" source="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png" alt-text="记录堆分配探查器" lightbox="../media/memory-problems-memory-allocation-instrumentation-on-timeline-selected.msft.png":::
       记录堆分配探查器  
    :::image-end:::  
    
## 读取堆分配时间线  

堆分配时间线显示对象的创建位置，并标识保留路径。  在下图中，顶部的条形指示在堆中何时找到新对象。  

每个栏的高度对应于最近分配的对象的大小，而条形的颜色指示这些对象是否仍位于最终堆快照中。  蓝色条指示仍位于时间线末尾的对象，灰色条指示在时间线期间分配但之后已被垃圾回收的对象。  

:::image type="complex" source="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png" alt-text="时间线快照上的分配检测" lightbox="../media/memory-problems-memory-allocation-timelines-snapshot.msft.png":::
   **时间线快照上的分配** 检测  
:::image-end:::  

<!--In the following figure, an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

可以使用上述时间线中的滑块放大该特定快照，并查看此时最近分配的对象：  

:::image type="complex" source="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png" alt-text="放大快照" lightbox="../media/memory-problems-memory-allocation-timeline-snapshot-highlighted-annotated.msft.png":::
   放大快照  
:::image-end:::  

单击堆中的特定对象将显示堆快照底部部分的保留树。  检查对象的保留路径应为您提供足够的信息，以理解为何未收集该对象，并且应进行必要的代码更改以删除不必要的引用。  

## 按功能查看内存分配  

你能够通过 JavaScript 函数查看内存分配。  有关详细信息，请导航到按 [函数调查内存分配][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。  

## 联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevToolsOpenIndex]: ../open/index.md "打开 Microsoft Edge (Chromium) DevTools |Microsoft Docs"
[DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]: ./index.md#investigate-memory-allocation-by-function "按功能调查内存分配 - 修复内存问题 |Microsoft Docs"  

<!--[HeapProfiler]: ./heap-snapshots.md "How to Record Heap Snapshots"  -->  
<!--[PerformancePanel]: ../profile/evaluate-performance/timeline-tool ""  -->  

[MicrosoftEdgeChannel]: https://www.microsoftedgeinsider.com/download "下载 Microsoft Edge 渠道"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler) 由 [Meggin Kearney][MegginKearney] \ (Technical Writer\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
