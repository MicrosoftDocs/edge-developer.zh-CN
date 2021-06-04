---
description: 了解如何使用 DevTools 堆Microsoft Edge器记录堆快照并查找内存泄漏。
title: 如何记录堆快照
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 05/04/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 5f097cc45facc7f366a99a9564cf6f3d443f2058
ms.sourcegitcommit: 7945939c29dfdd414020f8b05936f605fa2b640e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/13/2021
ms.locfileid: "11565013"
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
# <a name="how-to-record-heap-snapshots"></a>如何记录堆快照  

了解如何使用 DevTools 堆Microsoft Edge器记录堆快照并查找内存泄漏。  

DevTools Microsoft Edge配置文件器中显示了 JavaScript 对象和页面的相关 DOM 节点的内存分布。  使用它获取 JavaScript 堆 \(JS 堆\) 快照、分析内存图形、比较快照和查找内存泄漏。  导航到 [对象保留树][DevtoolsMemoryProblems101ObjectsRetainingTree]。  

## <a name="take-a-snapshot"></a>拍摄快照  

在"**内存"面板**上，选择"**拍摄快照"，** 然后选择"**开始"。**  还可以选择 `Ctrl` + `E` \(Windows、Linux\) 或 `Cmd` + `E` \(macOS\) 。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="选择分析类型" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   选择分析类型  
:::image-end:::  

**快照** 最初存储在呈现器进程内存中。  当你选择快照图标进行查看时，快照将按需传输到 DevTools。  

将快照加载到 DevTools 并进行分析后，将显示快照标题下方的数字，并显示可到达 [的 JavaScript 对象的总大小][DevtoolsMemoryProblems101ObjectSizes]。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="可到达对象的总大小" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   可到达对象的总大小  
:::image-end:::  

> [!NOTE]
> 快照中仅包含可到达的对象。  此外，拍摄快照始终从垃圾回收开始。  

## <a name="clear-snapshots"></a>清除快照  

选择 **"清除所有配置文件** "图标，从 DevTools (删除快照和与呈现器进程关联的任何内存\) 。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="删除快照" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   删除快照  
:::image-end:::  

关闭 DevTools 窗口不会从与呈现器进程关联的内存中删除配置文件。  重新打开 DevTools 时，以前获取的所有快照将重新出现于快照列表中。  

> [!NOTE]
> 试用此散 [点对象示例，][GlitchDevtoolsMemoryExample03] 然后使用堆探查器进行配置文件。  将显示一个 \(对象\) 项分配。  

## <a name="view-snapshots"></a>查看快照  

从不同的角度查看不同任务的快照。  

**摘要视图** 显示按构造函数名称分组的对象。  使用它来根据按构造函数名称 (类型来搜寻对象 \(和内存 use\) 。  它尤其有助于跟踪 **DOM 泄露**。

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

**比较视图**。  显示两个快照之间的差值。  使用它来比较两个 \(或更多\) 操作之前和之后的内存快照。  通过检查释放的内存和引用计数中的增量，你可以确认内存泄漏的存在和原因。  

**包含视图**。  允许浏览堆内容。  **包含视图** 提供更好的对象结构视图，帮助分析全局命名空间 \(window\) 中引用的对象，以找出对象周围的内容。  使用它来分析关闭，并深入到较低级别的对象中。  

若要在视图之间切换，请使用视图顶部的选择器。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="切换视图选择器" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   切换视图选择器  
:::image-end:::  

> [!NOTE]
> 并非所有属性都存储在 JavaScript 堆上。  不会捕获使用运行本机代码的 getter 实现的属性。  此外，不会捕获数字等非字符串值。  

### <a name="summary-view"></a>摘要视图  

最初，快照在"摘要"视图中打开，并显示对象总数，可以展开该对象汇总以显示实例：  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="摘要视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   **摘要** 视图  
:::image-end:::  

顶级条目是"total"行。  

| 顶级条目 | 说明 |  
|:--- |:--- |  
| **构造函数** | 表示使用此构造函数创建的所有对象。  |  
| **距离** | 使用节点的最短简单路径显示到根之间的距离。  |  
| **浅表大小** | 显示由特定构造函数函数创建的所有对象的浅表大小的总和。  浅表大小是由对象 \(通常，数组和字符串具有较大的浅表大小\) 。  导航到 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。  |  
| **保留大小** | 显示同一组对象中保留的最大大小。  在删除对象 \(并且使从属项不再可用后可以释放的内存大小) 称为保留大小。  导航到 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

展开上视图中的总行后，将显示所有实例。  对于每个实例，浅表和保留的大小显示在相应的列中。  字符后的编号是对象的唯一 ID，使你可以基于每个对象比较堆 `@` 快照。  

请记住，黄色对象具有 JavaScript 引用，红色对象是从具有黄色背景的节点引用的分离节点。  

**堆配置文件器中的各种构造函数 \(group\) 条目对应于什么？**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="构造函数组" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   **构造函数** 组  
:::image-end:::  

| 构造函数 \(group\) 条目 | 说明 |  
|:--- |:--- |  
| **\(global 属性\) ** | 全局对象 \(\) 和它所引用的对象 `window` 之间的中间对象。  如果对象是使用构造函数创建的，并且由全局对象保留，则保留路径可以 `Person` 表示为 `[global] > \(global property\) > Person` 。  这与标准相反，其中对象直接相互引用。  中间对象存在是出于性能原因。  会定期修改全局设置，并且属性访问优化对于非全局对象则不适用于全局对象。  |  
| **\(根\) ** | 保留树视图中的根条目是引用所选对象的实体。  这些条目还可以是引擎创建的用于引擎特定用途的引用。  引擎具有缓存哪些引用对象，但所有此类引用都是弱引用，并且不会在不存在真正强大的引用时阻止收集对象。  |  
| **\(关闭\) ** | 通过函数关闭对一组对象的引用计数。  |  
| **\(array， string， number， regexp\) ** | 具有引用 Array、String、Number 或正则表达式的属性的对象类型列表。  |  
| **\(编译的代码\) ** | 与已编译代码相关的所有内容。  脚本类似于函数，但对应于 `<script>` 正文。  SharedFunctionInfos \(SFI\) 是位于函数和已编译代码之间的对象。  函数通常具有上下文，而 SFIs 没有上下文。  |  
| **** HTMLDivElement、HTMLAnchorElement、DocumentFragment 等。 **** ****  | 对代码引用的特定类型元素或文档对象的引用。  |  

<!--todo: add heap profiling summary section when available -->  

### <a name="comparison-view"></a>比较视图  

通过将多个快照相互比较来查找泄露的对象。  若要验证特定应用程序操作不会创建泄漏 \(例如，通常一对直接和反向操作（如打开文档，然后关闭文档）不应留下任何垃圾回收\) ，您可以遵循以下方案：  

1.  在操作之前拍摄堆快照。  
1.  执行 \(以你认为会导致泄露的方式与页面交互) 。  
1.  执行反向操作 \(执行相反的交互并重复几次\) 。  
1.  拍摄第二个堆快照，将此快照的视图更改为**Comparison，** 比较快照**1。**  
    
在 **"比较** "视图中，将显示两个快照之间的差值。  展开总条目时，将显示添加和删除的对象实例。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比较视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   **比较** 视图  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### <a name="containment-view"></a>包含视图  

" **包含** "视图实质上是应用程序的对象结构的"鸟眼视图"。  它允许你查看函数关闭，观察共同组合 JavaScript 对象的虚拟机 \(VM\) 内部对象，以及了解应用程序在非常低级别使用的内存量。  

| 包含视图入口点 | 说明 |  
|:--- |:--- |  
| **DOMWindow 对象** | JavaScript 代码的全局对象。  |  
| **GC 根** | VM 的垃圾回收使用的实际 GC 根。  GC 根由内置对象映射、符号表、VM 线程堆栈、编译缓存、处理范围和全局句柄组成。  |  
| **本机对象** | 浏览器对象在 JavaScript 虚拟机 \(JavaScript VM\) 内"推送"，以允许自动化，例如 DOM 节点、CSS 规则。  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="包含视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   **包含** 视图  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> 有关关闭的提示。  命名函数，以便可以轻松地区分快照中的关闭。  例如，此示例不使用命名函数。  
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
> 以下代码段使用命名函数。  
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
> :::image type="complex" source="../media/memory-problems-domleaks.msft.png" alt-text="Name functions to distinguish between closures" lightbox="../media/memory-problems-domleaks.msft.png":::
>    Name functions to distinguish between closures  
> :::image-end:::  
> -->  
> 
> > [!NOTE]
> > 请试用此示例 [，了解为何 `eval` ][GlitchDevtoolsMemoryExample07] 需要分析关闭对内存的影响。  你可能还有兴趣通过此示例跟踪它，该示例将你完成记录 [堆分配][GlitchDevtoolsMemoryExample08]。  
> 

## <a name="look-up-color-coding"></a>查找颜色编码  

对象的属性和属性值具有不同的类型，并相应地进行着色。  每个属性有四种类型之一。  

| 属性类型 | 说明 |  
|:--- |:--- |  
| **a： property** | 具有名称的常规属性，可通过 `.` \(dot\) 运算符或通过 `[` `]` \(brackets\) 表示法访问，例如 `["foo bar"]` 。  |  
| **0：元素** | 具有数值索引的常规属性，可通过 `[` `]` \(brackets\) 表示法访问。  |  
| **a： context var** |  函数上下文中的变量，可通过函数关闭内部的变量名称访问。  |  
| **a： system prop** | JavaScript VM 添加的属性，无法通过 JavaScript 代码访问。  |  

指定为 的对象 `System` 没有相应的 JavaScript 类型。  每个组件都是 Javascript VM 的对象系统实现一部分。  V8 在用户 JS 对象相同的堆中分配大部分内部对象。  因此，这些只是 V8 内部。  

## <a name="find-a-specific-object"></a>查找特定对象  

若要在收集的堆中查找对象，可以使用 搜索 并 `Ctrl` + `F` 给出对象 ID。  

## <a name="uncover-dom-leaks"></a>发现 DOM 泄漏  

堆探查器能够反映浏览器本机对象 \(DOM 节点、CSS 规则\) 和 JavaScript 对象之间的双向依赖关系。
这有助于发现由于忘记了分离的 DOM 子树而发生的不可见泄露。  

DOM 泄露可能大于您想象中。  请考虑以下示例。  何时将#tree GC？  

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

保留对相关父级 `#leaf` \(parentNode\) 的引用，并递归到 ，因此仅在 leafRef 为 nullified 时，作为 GC 候选项下的 `#tree` WHOLE 树。 `#tree`  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM 子树" lightbox="../media/memory-problems-tree-gc.msft.png":::
   DOM 子树  
:::image-end:::  

> [!NOTE]
> 示例：尝试此示例的泄露 [DOM 节点][GlitchDevtoolsMemoryExample06] ，了解它可能会泄露在哪里以及如何检测它。  您还可以查看此 DOM 泄漏 [大于预期的示例][GlitchDevtoolsMemoryExample09]。  

若要了解有关 DOM 泄漏和内存分析基础的更多信息，请参阅查找和调试由 Gonzalo Ruiz de 的[Microsoft Edge DevTools][GonzaloRuizdeVillaMemory]的内存泄漏。  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "对象大小 - 内存术语|Microsoft Docs"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "保留树的对象 - 内存术语|Microsoft Docs"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html - Microsoft Edge (Chromium) DevTools |小故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html - Microsoft Edge (Chromium) DevTools |小故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "内存|幻灯片"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) ，由 [Meggin Kearney][MegginKearney] \(Technical Writer\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[MegginKearney]: https://developers.google.com/web/resources/contributors#meggin-kearney  
