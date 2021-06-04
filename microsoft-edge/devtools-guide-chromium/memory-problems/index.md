---
description: 了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存不足和频繁垃圾回收。
title: 修复内存问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 3b2405d23dd6ee349484c9ba66d195e3ed12144b
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565027"
---
<!-- Copyright Kayce Basques 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->
# <a name="fix-memory-problems"></a>修复内存问题  

了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存不足和频繁垃圾回收。  

### <a name="summary"></a>摘要  

*   了解你的页面当前与浏览器任务管理器Microsoft Edge的内存量。  
*   使用内存面板直观呈现一段时间 **的内存** 使用情况。  
*   使用堆快照 (分离的 DOM 树 \) 内存泄漏 **的常见原因**。  
*   在时间线上通过 Allocation instrumentation 了解 JavaScript 堆 \(JS 堆\) **分配新内存的时间**。  

## <a name="overview"></a>概述  

在 RAIL **性能模型** 方面，性能工作的重点应该是用户。  

<!--todo: add RAIL section when available  -->  

内存问题非常重要，因为它们经常被用户感知。  用户可能通过以下方式发现内存问题：  

*   **随着时间的推移，页面的性能逐渐变差**。  这可能是内存泄漏症状。  内存泄漏是页面中的 Bug 导致页面随着时间的推移逐渐使用更多内存。  
*   **页面的性能一直不佳**。  这可能是内存不足现象。  当页面使用的内存多于最佳页面速度所需的内存时，内存量会变大。  
*   **页面的性能会延迟或看似频繁暂停**。  这可能是频繁垃圾回收症状。  垃圾回收是在浏览器回收内存时进行。  浏览器决定何时发生这种情况。  在集合期间，所有正在运行的脚本将暂停。  因此，如果浏览器大量进行垃圾回收，脚本运行时将暂停很多。  

### <a name="memory-bloat-how-much-is-too-much"></a>内存过多："太多"多少？  

内存泄漏易于定义。  如果网站逐渐使用更多内存，则有泄漏。  但是，内存不足有点难以固定。  什么限定为"使用过多的内存"？  

此处没有硬数，因为不同的设备和浏览器具有不同的功能。  在高端智能手机上流畅运行的同一页面可能在低端智能手机上崩溃。  

这里的关键是使用 RAIL 模型，并专注于你的用户。  了解哪些设备受你的用户欢迎，然后在这些设备上测试你的页面。  如果体验始终不佳，则页面可能会超出这些设备的内存功能。  

## <a name="monitor-memory-use-in-realtime-with-the-microsoft-edge-browser-task-manager"></a>使用浏览器任务管理器实时Microsoft Edge内存使用  

使用Microsoft Edge浏览器任务管理器作为内存问题调查的起点。  浏览器Microsoft Edge管理器是实时监视器，可告诉你页面当前使用的内存量。  

1.  选择 `Shift` + `Esc` 或导航到****"Microsoft Edge"主菜单，然后选择"更多工具""浏览器任务管理器"以Microsoft Edge  >  **** 浏览器任务管理器"。  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="打开Microsoft Edge浏览器任务管理器" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       图 1：打开Microsoft Edge浏览器任务管理器  
    :::image-end:::  
    
1.  将鼠标悬停在浏览器任务管理器Microsoft Edge表标题上，打开上下文菜单 \(右键单击\) ，并启用**JavaScript 内存**。  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="启用 JavaScript 内存" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       图 2：启用 JavaScript 内存  
    :::image-end:::  
    
这两列告诉您有关页面如何使用内存的不同内容。  

*   " **内存** "列表示本机内存。  DOM 节点存储在本机内存中。  如果此值增加，将创建 DOM 节点。  
*   **"JavaScript 内存"** 列表示 JS 堆。  此列包含两个值。  您感兴趣的值为活动号码 \(括号\) 。  实时数表示页面上的可访问对象使用的内存量。  如果此数目增加，则要么正在创建新对象，要么现有对象正在增长。  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <a name="visualize-memory-leaks-with-performance-panel"></a>使用性能面板可视化内存泄漏  

您还可以使用性能面板作为调查的另一个起点。  "性能"面板可帮助您直观呈现页面在一段时间的内存使用。  

1.  打开**** DevTools 上的"性能"面板。  
1.  启用" **内存"** 复选框。  
1.  [录制][DevtoolsEvaluatePerformanceReferenceRecord]。  

> [!TIP]
> 最佳做法是使用强制垃圾回收开始和结束录制。  若要强制进行垃圾回收，请选择记录时 **收集垃圾回收** ![ ][ImageForceGarbageCollectionIcon] 强制垃圾回收按钮。  

若要演示内存录制，请考虑以下代码：  

```javascript
var x = [];
function grow() {
    for (var i = 0; i < 10000; i++) {
        document.body.appendChild(document.createElement('div'));
    }
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

每次选择代码中引用的按钮时，都会将一万个节点追加到文档正文，并且一个包含一百万个字符的字符串 `div` `x` 被推送到 `x` 数组。  运行前面的代码示例在性能面板中 **生成** 记录，如下图所示。  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="简单增长" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   图 3：简单增长  
:::image-end:::  

首先，用户界面的说明。  "**概述**"窗格**** \(中的 HEAP 图) **表示**JS 堆。  "概述 **"窗格** 下方是" **计数器"** 窗格。  内存使用率由 JS 堆 \(与概述窗格\) 、文档、DOM**** 节点、侦听器和 GPU 内存中的**HEAP**图形相同。  关闭复选框以在图形中隐藏它。  

现在，代码分析与上图比较。  如果查看节点计数器 \(绿色图形\) ，它将与代码完全匹配。  节点计数在离散步骤中增加。  您可能认为每次增加的节点数都是对 的调用 `grow()` 。  JS 堆图 \(蓝图\) 不是那么简单。  为了与最佳做法保持一样，第一个下降实际上是强制垃圾回收 \(选择  **收集垃圾回收** ![ 强制垃圾回收按钮 ][ImageForceGarbageCollectionIcon] \) 。  在记录进行时，将显示 JS 堆大小峰值。  这是自然且预期的：JavaScript 代码将在你选择的每一个按钮上创建 DOM 节点，并创建一百万个字符的字符串时执行大量工作。  此处的关键点是 JS 堆结束时间高于其开头 \("开头"是强制垃圾回收\) 。  在现实世界中，如果你看到这种增加 JS 堆大小或节点大小的模式，它可能会定义内存泄漏。  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <a name="discover-detached-dom-tree-memory-leaks-with-heap-snapshots"></a>使用堆快照发现分离的 DOM 树内存泄漏  

DOM 节点仅在没有从页面上运行的 DOM 树或 JavaScript 代码引用该节点时进行垃圾回收。  当从 DOM 树中删除节点时，该节点将被"分离"，但某些 JavaScript 仍引用它。  分离的 DOM 节点是内存泄漏的常见原因。  本部分指导你如何使用 DevTools 中的堆探查器来确定分离的节点。  

下面是分离 DOM 节点的简单示例。  

```javascript
var detachedTree;

function create() {
    var ul = document.createElement('ul');
    for (var i = 0; i < 10; i++) {
        var li = document.createElement('li');
        ul.appendChild(li);
    }
    detachedTree = ul;
}
document.getElementById('create').addEventListener('click', create);
```  

选择代码中引用的按钮将创建一 `ul` 个包含 10 个子节点 `li` 的节点。  节点由代码引用，但在 DOM 树中不存在，因此会分离每个节点。  

堆快照是标识分离节点的一种方法。  正如该名称所示，堆快照显示了在快照时间点如何在页面的 JS 对象和 DOM 节点之间分配内存。  

若要创建快照，请打开 DevTools 并导航**** 到内存面板，选择**** 堆快照单选按钮>**拍摄快照**按钮。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="拍摄堆快照" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   图 4：拍摄堆快照  
:::image-end:::  

可能需要一些时间处理和加载快照。  完成后，从名为 **HEAP SNAPSHOTS**\(的左侧面板 \) 。  

在 `Detached` 类 **筛选器文本框中** 键入以搜索分离的 DOM 树。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="筛选分离的节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   图 5：筛选分离的节点  
:::image-end:::  

展开树状以调查分离的树。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="调查分离的树" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   图 6：调查分离的树  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

选择一个节点以进一步调查它。  在 **"对象** "窗格中，您可以查看有关引用它的代码的详细信息。  例如，在下图中， `detachedNodes` 变量引用节点。  若要修复特定内存泄漏，应研究使用 变量的代码，并确保在不再需要节点时删除 `detachedUNode` 对节点的引用。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="调查节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   图 7：调查节点  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <a name="identify-js-heap-memory-leaks-with-allocation-instrumentation-on-timeline"></a>在时间线上通过 Allocation instrumentation 识别 JS 堆内存泄漏  

**时间线上的分配检测** 是另一个可以帮助你跟踪 JS 堆中的内存泄漏的工具。  

使用 **下面的代码演示时间线**  上的分配检测。  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

每次推送代码中引用的按钮时，都会向数组中添加一个包含一百万个字符 `x` 的字符串。  

若要在时间线上记录分配检测，请打开 DevTools，导航**** 到内存面板，选择时间线上的分配检测单选按钮，选择****"开始"按钮，执行你怀疑导致内存泄漏的操作，然后在完成后选择停止**录制**堆配置文件停止录制**** ![ ][ImageStopRecordingIcon] 按钮。  

在录制时，请注意时间线上的 Allocation instrumentation 上是否显示任何蓝色条，如下图所示。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新分配" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   图 8：新分配  
:::image-end:::  

这些蓝色条代表新的内存分配。  这些新的内存分配是内存泄漏的候选项。  可以缩放栏以筛选"构造函数"窗格，以**** 只显示指定时间范围内分配的对象。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="已缩放的分配时间线" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   图 9：已缩放的分配时间线  
:::image-end:::  

展开对象并选择值以查看"对象"窗格中的 **更多详细信息** 。  例如，下图中新分配的对象的详细信息指示已分配给范围 `x` 中的 `Window` 变量。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="对象详细信息" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   图 10：对象详细信息  
:::image-end:::  

## <a name="investigate-memory-allocation-by-function"></a>按功能调查内存分配  

使用 **分配采样** 分析类型查看 JavaScript 函数的内存分配。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="记录分配采样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   图 11：记录分配采样  
:::image-end:::  

1.  选择“**分配采样**”按钮。  如果页面上有工作线程，可以使用"开始"按钮旁边的下拉菜单选择该工作 **线程作为分析** 目标。  
1.  选择" **开始"** 按钮。  
1.  完成要调查的网页上的操作。  
1.  完成 **所有操作** 后，选择"停止"按钮。  

DevTools 显示按功能分配内存的细目。  默认视图为 **"高 (从 **下) "，它显示在顶部分配了大部分内存的函数。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="分配采样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   图 12：分配采样  
:::image-end:::  

## <a name="spot-frequent-garbage-collections"></a>专色频繁垃圾回收  

如果页面似乎频繁暂停，则可能有垃圾回收问题。  

您可以使用浏览器任务管理器或性能Microsoft Edge记录来发现频繁垃圾回收。  在浏览器Microsoft Edge管理器中，经常出现和下降**的内存**或**JavaScript 内存**值表示频繁的垃圾回收。  在性能记录中，频繁更改 \(和下降\) JS 堆或节点计数图指示频繁进行垃圾回收。  

确定问题后，可以在时间线记录上使用 **Allocation instrumentation** 来查明内存的分配位置以及导致分配的函数。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "记录性能 - 性能分析参考"  

<!--[RAIL]: /profile/evaluate-performance/rail  -->
<!--[recording]: /profile/evaluate-performance/timeline-tool#make-a-recording ""  -->  

<!--[hngd]: https://jsfiddle.net/kaycebasques/tmtbw8ef/  -->  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/index)，由 [Kayce Basques][KayceBasques]\（Chrome DevTools \& Lighthouse 的技术作家\）撰写。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
