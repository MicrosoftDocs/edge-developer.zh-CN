---
description: 了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存不足和频繁垃圾回收。
title: 修复内存问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: afaea8ca561bd975490d9153cda40877786a0f08
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397830"
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

*   了解你的页面当前使用 Microsoft Edge 浏览器任务管理器的内存量。  
*   使用"内存"面板直观显示 **一段时间的内存** 使用情况。  
*   使用堆快照 (分离的 DOM 树 \) 内存泄漏的 **常见原因**。  
*   了解何时在 JavaScript 堆 \ (JS 堆\) 分配检测 **中分配新内存**。  

## <a name="overview"></a>概述  

根据 **RAIL** 性能模型，您的性能工作的重点应该是用户。  

<!--todo: add RAIL section when available  -->  

内存问题非常重要，因为它们经常被用户感知。  用户可能会以以下方式发现内存问题：  

*   **随着时间的推移，页面的性能会逐渐变差**。  这可能是内存泄漏的一种症状。  内存泄漏是页面中的 Bug 导致页面随着时间的推移逐渐使用越来越多的内存。  
*   **页面的性能一直很差**。  这可能是内存不足的一种症状。  内存不足是页面使用的内存多于实现最佳页面速度所必需的内存时。  
*   **页面的性能会延迟或经常暂停**。  这可能是频繁进行垃圾回收的一种症状。  垃圾回收是浏览器回收内存时。  浏览器决定何时发生此情况。  在集合期间，所有正在运行的脚本将暂停。  因此，如果浏览器大量进行垃圾回收，脚本运行时将大量暂停。  

### <a name="memory-bloat-how-much-is-too-much"></a>内存不足："太多"多少？  

内存泄漏易于定义。  如果网站逐渐使用越来越多的内存，则有一个泄漏。  但是内存不足有点难以固定。  什么限定为"使用过多的内存"？  

此处没有硬数字，因为不同的设备和浏览器具有不同的功能。  在高端智能手机上流畅运行的同一页面可能在低端智能手机上崩溃。  

此处的关键是使用 RAIL 模型并关注用户。  了解哪些设备受用户欢迎，然后在这些设备上测试你的页面。  如果体验一直不佳，则页面可能会超出这些设备的内存功能。  

## <a name="monitor-memory-use-in-realtime-with-the-microsoft-edge-browser-task-manager"></a>使用 Microsoft Edge 浏览器任务管理器实时监视内存使用  

使用 Microsoft Edge 浏览器任务管理器作为内存问题调查的起点。  Microsoft Edge 浏览器任务管理器是一个实时监视器，可告知你页面当前使用的内存量。  

1.  选择 `Shift` + `Esc` 或导航到 Microsoft Edge 主菜单，然后选择 **"更多工具**  >  **浏览器任务管理器**"以打开 Microsoft Edge 浏览器任务管理器。  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       图 1：打开 Microsoft Edge 浏览器任务管理器  
    :::image-end:::  
    
1.  将鼠标悬停在 Microsoft Edge 浏览器任务管理器的表标题上，打开上下文菜单 \ (右键单击\) ，并启用 **JavaScript 内存**。  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="启用 JavaScript 内存" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       图 2：启用 JavaScript 内存  
    :::image-end:::  
    
这两列告诉你有关页面如何使用内存的不同内容。  

*   " **内存** "列表示本机内存。  DOM 节点存储在本机内存中。  如果此值增加，将创建 DOM 节点。  
*   **"JavaScript 内存"** 列表示 JS 堆。  此列包含两个值。  您感兴趣的值为活动号码 \ (括号\) 。  实时数表示页面上的可到达对象使用的内存量。  如果此数目增加，则要么正在创建新对象，要么现有对象正在增长。  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## <a name="visualize-memory-leaks-with-performance-panel"></a>使用"性能"面板可视化内存泄漏  

您还可以使用性能面板作为调查的另一个起点。  "性能"面板可帮助您直观地了解页面在一段时间的内存使用。  

1.  打开**** DevTools 上的"性能"面板。  
1.  启用 **"内存"** 复选框。  
1.  [进行录制][DevtoolsEvaluatePerformanceReferenceRecord]。  

> [!TIP]
> 最佳做法是使用强制垃圾回收开始和结束录制。  若要强制进行垃圾回收，请选择记录 **时收集垃圾回收** ![ ][ImageForceGarbageCollectionIcon] 强制垃圾回收按钮。  

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

每次选择代码中引用的按钮时，都会将一万个节点追加到文档正文，并且将一个包含一百万个字符的字符串推送到 `div` `x` `x` 数组中。  运行上一个代码示例将生成"性能 **"面板** 中的记录，如下图所示。  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="简单增长" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   图 3：简单增长  
:::image-end:::  

首先，用户界面的说明。  "**概述**"窗格**** \ (下 **"堆**) 表示 JS 堆。  "概述 **"** 窗格下方是 **"计数器"** 窗格。  内存使用率由 JS 堆 \ (在**概述窗格**\) 、文档、DOM 节点、侦听器和 GPU 内存中与**HEAP**图形相同。  关闭复选框以将其从图形中隐藏。  

现在，对代码的分析与上图进行比较。  如果查看节点计数器 \ (绿色图形\) ，它将与代码完全匹配。  节点计数在离散步骤中增加。  您可能认为节点计数的每次增加都是对的调用 `grow()` 。  JS 堆图 \ (蓝色图\) 不是那么简单。  为了与最佳做法保持一样，第一个 dip 实际上是一个强制垃圾回收 \ (选择  **收集垃圾回收** ![ 强制垃圾回收按钮 ][ImageForceGarbageCollectionIcon] \) 。  在录制进行时，将显示 JS 堆大小峰值。  这是自然且预期的：JavaScript 代码将在你选择的每一个按钮上创建 DOM 节点，并创建一百万个字符的字符串时执行大量工作。  这里的关键一点是 JS 堆结束时间高于其开头\ (此处是强制垃圾回收\) 之后的起点。  在现实世界中，如果你看到这种增加 JS 堆大小或节点大小的模式，它可能会定义内存泄漏。  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## <a name="discover-detached-dom-tree-memory-leaks-with-heap-snapshots"></a>使用堆快照发现分离的 DOM 树内存泄漏  

DOM 节点仅在从页面上运行的 DOM 树或 JavaScript 代码中没有引用该节点时进行垃圾回收。  从 DOM 树中删除节点时，该节点被"分离"，但某些 JavaScript 仍引用它。  分离的 DOM 节点是内存泄漏的常见原因。  本部分指导你如何使用 DevTools 中的堆探查器来标识分离的节点。  

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

选择代码中引用的按钮将创建一个包含 `ul` 10 个子节点 `li` 的节点。  这些节点由代码引用，但 DOM 树中不存在，因此会分离每个节点。  

堆快照是标识分离节点的一种方法。  正如名称所示，堆快照显示如何在快照时在页面的 JS 对象和 DOM 节点之间分配内存。  

若要创建快照，请打开 DevTools 并导航**** 到"内存"面板****，选择"堆快照单选 **>"按钮**。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="拍摄堆快照" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   图 4：获取堆快照  
:::image-end:::  

快照可能需要一些时间处理和加载。  完成后，从左侧面板 \ (**命名为 HEAP SNAPSHOTS**\) 。  

键入 `Detached` 类 **筛选器** 文本框以搜索分离的 DOM 树。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="筛选分离的节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   图 5：筛选分离的节点  
:::image-end:::  

展开树形以调查分离的树。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="调查分离的树" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   图 6：调查分离的树  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

选择一个节点以进一步调查它。  在 **"对象** "窗格中，您可以查看有关引用它的代码的详细信息。  例如，在下图中，变量 `detachedNodes` 引用节点。  若要修复特定内存泄漏，应研究使用该变量的代码，并确保在不再需要节点时删除 `detachedUNode` 对节点的引用。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="正在调查节点" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   图 7：调查节点  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## <a name="identify-js-heap-memory-leaks-with-allocation-instrumentation-on-timeline"></a>通过时间线上的分配检测识别 JS 堆内存泄漏  

**时间线上的分配检测** 是另一个工具，可帮助你跟踪 JS 堆中的内存泄漏。  

使用 **以下代码演示**  时间线上的分配检测。  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

每次推送代码中引用的按钮时，都会向数组中添加一个包含 100 万个字符 `x` 的字符串。  

若要在时间线上记录分配检测，请打开 DevTools，导航到内存面板，选择**** 时间线单选按钮上的分配检测，选择****"开始"按钮，执行您怀疑导致内存泄漏的操作，然后在完成后选择"停止录制**** 堆配置文件停止录制"按钮。 **** ![ ][ImageStopRecordingIcon]  

在录制时，请注意是否日程表上的分配规范上显示任何蓝色条形，如下图所示。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="新分配" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   图 8：新分配  
:::image-end:::  

这些蓝色条代表新的内存分配。  这些新的内存分配是内存泄漏的候选项。  您可以缩放栏以筛选 **构造函数窗格，** 以只显示指定时间范围内分配的对象。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="缩放的分配时间线" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   图 9：已缩放的分配时间线  
:::image-end:::  

展开对象并选择值以查看"对象"窗格中 **的** 更多详细信息。  例如，下图中新分配的对象的详细信息指示该对象已分配给 `x` 范围中的 `Window` 变量。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="对象详细信息" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   图 10：对象详细信息  
:::image-end:::  

## <a name="investigate-memory-allocation-by-function"></a>按函数调查内存分配  

使用 **分配采样** 分析类型查看 JavaScript 函数的内存分配。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="记录分配采样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   图 11：记录分配采样  
:::image-end:::  

1.  选择 **"分配采样单** 选"按钮。  如果页面上有工作线程，可以使用"开始"按钮旁边的下拉菜单选择该工作线程作为 **分析** 目标。  
1.  选择 **"开始"** 按钮。  
1.  完成要调查的网页上的操作。  
1.  完成 **所有** 操作后，选择"停止"按钮。  

DevTools 显示按功能细分的内存分配。  默认视图为"重 (**从 **下向上) ，该视图在顶部显示分配了最多内存的函数。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="分配采样" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   图 12：分配采样  
:::image-end:::  

## <a name="spot-frequent-garbage-collections"></a>发现频繁垃圾回收  

如果页面经常暂停，则您可能有垃圾回收问题。  

可以使用 Microsoft Edge 浏览器任务管理器或性能内存记录来发现频繁的垃圾回收。  在 Microsoft Edge 浏览器任务管理器中，经常增加和下降 **的内存** 或 **JavaScript 内存** 值表示频繁的垃圾回收。  在性能记录中，频繁更改 \ (和下降\) JS 堆或节点计数图指示频繁垃圾回收。  

识别问题后，可以在时间线记录上使用 **分配** 检测来了解分配内存的所在位置以及导致分配的函数。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

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
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
