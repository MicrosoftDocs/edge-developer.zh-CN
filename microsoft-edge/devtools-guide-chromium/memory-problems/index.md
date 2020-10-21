---
description: 了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存膨胀和频繁垃圾回收。
title: 修复内存问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 10/19/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 1d8a24fc360dc307471be33544c9c707736be06d
ms.sourcegitcommit: 99eee78698dc95b2a3fa638a5b063ef449899cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/20/2020
ms.locfileid: "11125452"
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

# 修复内存问题  

了解如何使用 Microsoft Edge 和 DevTools 查找影响页面性能的内存问题，包括内存泄漏、内存膨胀和频繁垃圾回收。  

### 摘要  

*   使用 Microsoft Edge 浏览器任务管理器了解你的页面当前使用的内存量。  
*   使用 " **内存** " 面板在一段时间内可视化内存使用情况。  
*   确定分离的 DOM 树 \ (使用 **堆快照**的内存泄漏的常见原因 \ ) 。  
*   了解在你的 JavaScript 堆 \ (JS 堆 \ ) 以及 **时间线上有分配检测**的情况中何时分配新内存。  

## 概述  

在 **铁路** 性能模型的精神中，你的性能工作的重点应是你的用户。  

<!--todo: add RAIL section when available  -->  

内存问题很重要，因为它们通常由用户觉察。  用户可能会通过以下方式来感知内存问题：  

*   **随着时间的推移，页面性能逐渐变得越来越严重**。  这可能是内存泄漏的症状。  当页面中的 bug 导致页面逐渐使用越来越多的内存时，会发生内存泄漏。  
*   **页面性能始终不正确**。  这可能是内存膨胀的症状。  内存膨胀是指页面使用的内存超过最佳页面速度所需的内存。  
*   **页面性能延迟或显示为经常暂停**。  这可能是频繁垃圾回收的症状。  垃圾回收是浏览器回收内存的时候。  浏览器决定何时发生这种情况。  在集合期间，将暂停运行的所有脚本。  因此，如果浏览器对大量垃圾回收，脚本运行时将会暂停很多事情。  

### 内存膨胀： "过多" 是多少？  

内存泄漏很容易定义。  如果某个网站在使用更多内存的情况下逐渐增加，则你有泄漏。  但是内存膨胀比固定更难。  什么是 "使用过多的内存"？  

此处没有任何硬编号，因为不同的设备和浏览器具有不同的功能。  在高端智能手机上正常运行的同一页面可能会在低端智能手机上崩溃。  

此处的关键是使用滑轨模型，并关注您的用户。  了解你的用户最常用的设备，然后在这些设备上测试你的页面。  如果体验持续很差，则页面可能超出了这些设备的内存功能。  

## 使用 Microsoft Edge 浏览器任务管理器实时监视内存使用情况  

使用 Microsoft Edge 浏览器任务管理器作为内存问题调查的起始点。  Microsoft Edge 浏览器任务管理器是一个实时监视器，可告诉你页面当前使用的内存量。  

1.  选择 `Shift` + `Esc` 或转到 Microsoft edge 主菜单，然后选择 "**更多工具**  >  **浏览器任务管理**器" 以打开 microsoft Edge 浏览器任务管理器。  
    
    :::image type="complex" source="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-bing-settings-more-tools-browser-task-manager.msft.png":::
       图1：打开 Microsoft Edge 浏览器任务管理器  
    :::image-end:::  
    
1.  将鼠标悬停在 Microsoft Edge 浏览器任务管理器的表标题上，打开上下文菜单 \ (右键单击 "\ ) "，然后启用 **JavaScript 内存**。  
    
    :::image type="complex" source="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-bing-browser-task-manager-javascript-memory.msft.png":::
       图2：启用 JavaScript 内存  
    :::image-end:::  
    
这两个列告诉你有关页面如何使用内存的不同内容。  

*   " **内存** " 列表示本机内存。  DOM 节点存储在本机内存中。  如果此值增加，则会创建 DOM 节点。  
*   **JavaScript 内存**列表示 JS 堆栈。  此列包含两个值。  您感兴趣的值是活动号码 \ (圆括号中的数字 \ ) 。  活动号码表示页面上可访问对象所使用的内存量。  如果此数字增加，则表示正在创建新对象，或者现有对象正在增长。  

<!--*   live number reference: https://groups.google.com/d/msg/google-chrome-developer-tools/aTMVGoNM0VY/bLmf3l2CpJ8J  -->  

## 利用性能面板可视化内存泄漏  

您也可以将 "性能" 面板用作调查中的另一个起始点。  "性能" 面板可帮助你在一段时间内对页面的内存使用进行可视化处理。  

1.  在 DevTools 上打开 **性能** 面板。  
1.  启用 " **内存** " 复选框。  
1.  [进行录制][DevtoolsEvaluatePerformanceReferenceRecord]。  

> [!TIP]
> 使用强制垃圾回收开始和结束录制是一种很好的做法。  在录制以强制垃圾回收时，选择 " **收集垃圾** ![ 强制垃圾回收" ][ImageForceGarbageCollectionIcon] 按钮。  

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

每次按下代码中引用的按钮时，将 `div` 向文档正文追加10000节点，并将1000000字符的字符串 `x` 推送到 `x` 数组中。  运行上面的代码示例将在 " **性能** " 面板中生成一条记录，如下图所示。  

:::image type="complex" source="../media/memory-problems-glitch-example-1-performance-memory.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-1-performance-memory.msft.png":::
   图3：简单增长  
:::image-end:::  

首先是用户界面的说明。  "**概述**" 窗格中的**堆**图形 \ (下方的**NET**\ ) 表示 JS 堆栈。  " **概述** " 窗格下方是 **计数器** 窗格。  在这里，你可以在 "**概述**" 窗格中查看按 JS 堆栈 \ (和**堆**图相同的内存使用 \ ) 、文档、DOM 节点、侦听器和 GPU 内存。  禁用复选框会将其从图形中隐藏。  

现在，与上图中的代码分析进行了比较。  如果你查看节点计数器 \ (绿色图形 \ ) 你可以看到它与代码完全匹配。  节点计数在离散步骤中增加。  你可能会假定节点计数中的每个增加都是对的调用 `grow()` 。  JS 堆图形 \ (蓝色图形 \ ) 不是很简单。  根据最佳做法，第一个 dip 实际上是强制垃圾回收 \ (通过按 "  **收集垃圾** ![ 强制垃圾回收" ][ImageForceGarbageCollectionIcon] 按钮 \ ) 实现。  在录制过程中，你可以看到 JS 堆大小峰值。  这是自然且预期的： JavaScript 代码在每个按钮上创建 DOM 节点，并在创建1000000个字符串时执行大量工作。  下面的关键内容是，JS 堆的结束时间比它的开始时间更高 \ ("开始" 是强制垃圾回收 \ ) 之后的点。  在现实世界中，如果你看到此模式增加了 JS 堆大小或节点大小，则可能会定义内存泄漏。  

<!--todo: the Heap snapshots and Profiles panel are not found in Edge  -->  

## 利用堆快照发现分离的 DOM 树内存泄漏  

仅当在页面上运行的 DOM 树或 JavaScript 代码中没有对节点的引用时，才会对 DOM 节点进行垃圾回收。  当从 DOM 树中删除节点但某些 JavaScript 仍引用它时，称该节点已 "分离"。  分离的 DOM 节点是内存泄漏的常见原因。  本部分介绍如何使用 DevTools 中的堆探查器来标识已分离的节点。  

下面是分离的 DOM 节点的简单示例。  

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

选择代码中引用的按钮将创建一个 `ul` 具有十 `li` 个子元素的节点。  节点由代码引用，但在 DOM 树中不存在，因此每个节点都是分离的。  

堆快照是标识已分离节点的一种方法。  正如名称所示，堆快照显示了如何在该快照的时间点在 JS 对象和 DOM 节点之间分配内存。  

若要创建快照，请打开 DevTools 并转到 " **内存** " 面板，选择 " **堆快照** " 单选按钮，然后按 " **拍摄快照** " 按钮。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot.msft.png":::
   图4：采用堆快照  
:::image-end:::  

快照可能需要一些时间才能处理和加载。  完成后，从左侧面板 \ ("已命名的 **堆快照**\ ) " 中选择它。  

`Detached`在 "**类筛选器**" 文本框中键入以搜索已分离的 DOM 树。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached.msft.png":::
   图5：对已分离节点的筛选  
:::image-end:::  

展开 carats 以调查已分离的树。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded.msft.png":::
   图6：调查分离树  
:::image-end:::  

<!--Nodes highlighted yellow have direct references to them from the JavaScript code.  Nodes highlighted red do not have direct references.  They are only alive because they are part of the tree for the yellow node.  In general, you want to focus on the yellow nodes.  Fix your code so that the yellow node is not alive for longer than it needs to be, and you also get rid of the red nodes that are part of the tree for the yellow node.  -->

选择要进一步调查的节点。  在 " **对象** " 窗格中，你可以查看有关引用它的代码的详细信息。  例如，在下图中，你可以看到该 `detachedNodes` 变量正在引用该节点。  若要修复此特定内存泄漏，应研究使用该变量的代码， `detachedUNode` 并确保删除不再需要的节点引用。  

:::image type="complex" source="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-12-memory-heap-snapshot-filter-detached-expanded-selected.msft.png":::
   图7：调查节点  
:::image-end:::  

<!--todo: the allocation timeline does not appear in the DevTools in Edge  -->  

## 在日程表上通过分配检测识别 JS 堆内存泄漏  

**时间线上的分配检测** 是另一个工具，可帮助你跟踪 JS 堆中的内存泄漏。  

使用以下代码 **在时间线上演示分配检测**  。  

```javascript
var x = [];
function grow() {
    x.push(new Array(1000000).join('x'));
}
document.getElementById('grow').addEventListener('click', grow);
```  

每次推送代码中引用的按钮时，将向数组中添加一个1000000字符的字符串 `x` 。  

若要在日程表上记录分配检测，请打开 DevTools，转到 " **内存** " 面板，选择 " **时间线上的分配检测** " 单选按钮，按 " **开始** " 按钮，执行怀疑导致内存泄漏的操作，然后按 " **停止录制堆配置文件** ![ 停止录制" ][ImageStopRecordingIcon] 按钮。  

录制时，注意是否在时间线上显示分配检测上的任何蓝色条，如下图所示。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-all.msft.png":::
   图8：新分配  
:::image-end:::  

这些蓝色条表示新的内存分配。  这些新的内存分配是内存泄漏的候选项。  你可以放大条形以筛选 " **构造函数** " 窗格，以便仅显示在指定时间范围内分配的对象。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused.msft.png":::
   图9：已缩放的分配日程表  
:::image-end:::  

展开对象并选择值以在 " **对象** " 窗格中查看更多详细信息。  例如，在下图中，通过查看新分配的对象的详细信息，你应该能够看到它已分配给 `x` 作用域中的变量 `Window` 。  

:::image type="complex" source="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-13-allocation-timeline-snapshot-focused-constructor-expanded.msft.png":::
   图10：对象详细信息  
:::image-end:::  

## 调查按函数分配的内存  

使用 **分配采样** 分析类型，查看由 JavaScript 函数分配的内存。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling.msft.png":::
   图11：记录分配抽样  
:::image-end:::  

1.  选择 " **分配采样** " 单选按钮。  如果页面上有工作人员，你可以使用 " **开始** " 按钮旁边的下拉菜单选择它作为分析目标。  
1.  按 " **开始** " 按钮。  
1.  在要调查的页面上执行操作。  
1.  完成所有操作后，按 " **停止** " 按钮。  

DevTools 显示按函数划分的内存分配。  默认视图为 ** (自下而上的 "下) **"，显示分配了最高内存的函数。  

:::image type="complex" source="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png" alt-text="打开 Microsoft Edge 浏览器任务管理器" lightbox="../media/memory-problems-glitch-example-05-memory-allocation-sampling-heavy-bottom-up.msft.png":::
   图12：分配抽样  
:::image-end:::  

## 经常发现垃圾回收  

如果您的页面看起来经常暂停，则您可能遇到了垃圾回收问题。  

你可以使用 Microsoft Edge 浏览器任务管理器或性能内存录制来发现频繁的垃圾回收。  在 Microsoft Edge 浏览器任务管理器中，频繁上升和下降的 **内存** 或 **JavaScript 内存** 值表示频繁的垃圾回收。  在性能录制中，频繁更改 \ (升高和下降 \ ) 到 JS 堆或节点计数图指示频繁的垃圾回收。  

确定问题后，您可以 **在时间线录制上使用分配检测** 来查明内存的分配位置以及导致分配的函数。  

## 与 Microsoft Edge 开发人员工具团队联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- image links -->  

[ImageForceGarbageCollectionIcon]: ../media/collect-garbage-icon.msft.png  
[ImageStopRecordingIcon]: ../media/stop-recording-icon.msft.png  

<!-- links -->  

[DevtoolsEvaluatePerformanceReferenceRecord]: /microsoft-edge/devtools-guide-chromium/evaluate-performance/reference#record-performance "记录性能-性能分析参考"  

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
