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





# 如何在日程表上使用分配检测  



使用**时间线上的分配检测**查找未正确进行垃圾回收的对象，并继续保留内存。  

## 时间线上的分配规范的工作原理  

**时间线上的分配规范**将**堆探查器**的详细快照信息与**性能**面板的增量更新和跟踪组合在一起。  同样，针对对象的跟踪堆分配涉及开始录制、执行操作序列和停止录制分析。  

<!--todo: add profile memory problems (heap profiler) section when available  -->  
<!--todo: add profile evaluate performance (Performance panel) section when available  -->  

"**时间线上的分配规范" 在**整个录制过程中定期（每个 50 ms！ \）和最后一个快照（每个 ms！ \）和录制结束时定期执行堆快照。  

> ##### 图 1  
> **日程表上的分配规范**  
> ![日程表上的分配规范][ImageObjectTracker]  

> [!NOTE]
> 后面的数字 `@` 是一个对象 ID，该对象 ID 持续于录制会话期间拍摄的多个快照中。  持久性对象 ID 支持堆状态之间的精确比较。  在垃圾回收过程中移动对象，因此显示对象的地址毫无意义。  

## 在日程表上启用分配检测  

请按照以下步骤开始**在日程表上使用分配检测**。  

1.  [打开 DevTools][DevtoolsOpenIndex]。  
1.  打开 "**内存**" 面板，选择 "**时间线上的分配规范**" 单选按钮。  
1.  开始录制。  

> ##### 图 2  
> 记录堆分配探查器  
> ![记录堆分配探查器][ImageRecordHeap]  

## 读取堆分配日程表  

堆分配时间线显示创建对象的位置并标识保留路径。  在[图 3](#figure-3)中，顶部的条指示何时在堆中找到新对象。  

每个条形的高度对应于最近分配的对象的大小，条形图的颜色指示这些对象是否仍在最终堆快照中。  蓝色条表示在时间线结束时仍处于活动位置的对象，灰色条指示在时间线期间分配但已被垃圾回收的对象。  

> ##### 图 3  
> **日程表快照上的分配规范**  
> ![日程表快照上的分配规范][ImageCollected]  

<!--In [Figure 4](#figure-4), an action was performed 3 times.  The sample program caches five objects, so the last five blue bars are expected.  But the left-most blue bar indicates a potential problem.  -->  
<!--todo: redo figure 4 with multiple click actions  -->  

你可以使用上面时间线中的滑块缩放到该特定快照，并查看该位置最近分配的对象：  

> ##### 图 4  
> 放大到快照  
> ![放大到快照][ImageSliders]  

单击堆中的特定对象时，将显示堆快照底部的保留树。  检查对象的保留路径应为你提供足够的信息，以了解未收集对象的原因，你应该更改必要的代码以删除不必要的引用。  

## 按函数查看内存分配   

你可以通过 JavaScript 函数查看内存分配。  有关详细信息，请参阅[按函数调查内存分配][DevtoolsMemoryProblemsIndexInvestigateMemoryAllocationFunction]。  

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
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/allocation-profiler)，由[Meggin Kearney][MegginKearney] \ （技术作者 \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  