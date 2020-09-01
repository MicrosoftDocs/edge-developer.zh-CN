---
title: 如何录制堆快照
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/28/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: bd46489d8a8a3fddbff60618b4997784294cccff
ms.sourcegitcommit: 1251c555c6b4db8ef8187ed94d8832fdb89d03b8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/31/2020
ms.locfileid: "10985419"
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





# 如何录制堆快照   



了解如何将堆快照与 Microsoft Edge DevTools 堆探查器一起录制并查找内存泄漏。  

Microsoft Edge DevTools 堆探查器显示由页面的 JavaScript 对象和相关的 DOM 节点的内存分布。  使用它来获取 JavaScript 堆 \ (JS 堆 \ ) 快照、分析内存图、比较快照和查找内存泄漏。  另请参阅 [对象保留树][DevtoolsMemoryProblems101ObjectsRetainingTree]。  

## 拍摄快照  

在 " **内存** " 面板上，选择 " **拍摄快照**"，然后单击 " **开始**"。  您也可以按 `Ctrl` + `E` \ (Windows \ ) 或 `Cmd` + `E` \ (macOS \ ) 。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png" alt-text="选择性能分析类型" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots.msft.png":::
   选择性能分析类型  
:::image-end:::  

**快照** 最初存储在呈现器进程内存中。  当你单击 "快照" 图标进行查看时，快照将按需转到 DevTools。  

将快照加载到 DevTools 并进行分析后，将显示快照标题下方的数字，并显示可 [访问的 JavaScript 对象的总大小][DevtoolsMemoryProblems101ObjectSizes]。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png" alt-text="可访问对象的总大小" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all.msft.png":::
   可访问对象的总大小  
:::image-end:::  

> [!NOTE]
> 快照中仅包含可访问的对象。  此外，拍摄快照始终从垃圾回收开始。  

## 清除快照  

单击 " **清除所有配置文件** " 图标以从 DevTools 中删除快照 \ (以及与呈现程序进程 \ ) 关联的任何内存。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png" alt-text="删除快照" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-all-hover-clear-all-profiles.msft.png":::
   删除快照  
:::image-end:::  

关闭 DevTools 窗口不会删除与呈现程序进程关联的内存中的配置文件。  重新打开 DevTools 时，以前拍摄的所有快照都会重新出现在快照列表中。  

> [!NOTE]
> 请试用 [分散对象][GlitchDevtoolsMemoryExample03] 的示例并使用堆探查器对其进行分析。  你应该会看到大量 (对象 \ ) 项分配。  

## 查看快照  

从不同的视角查看不同任务的快照。  

"**摘要" 视图**显示按构造函数名称分组的对象。  使用它来查寻对象 \ (和内存使用 \ ) 基于由构造函数名称分组的类型。  它对于 **跟踪 DOM 泄漏**非常有用。

<!--todo: add profile memory problems memory diagnosis (tracking down DOM leaks) section when available  -->  

**比较视图**。  显示两个快照之间的差异。  使用它比较操作前后的两个 \ (或多个 \ ) 内存快照。  检查已释放的内存和引用计数中的增量可让你确认内存泄漏的存在和原因。  

**包含视图**。  允许探索堆内容。  "**包容" 视图**提供了更好的对象结构视图，帮助分析全局命名空间 \ (窗口中引用的对象 \ ) ，以了解对象周围的保留对象。  使用它来分析闭包，并以较低的级别深入查看你的对象。  

若要在视图之间进行切换，请使用视图顶部的选择器。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png" alt-text="切换视图选择器" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-view-dropdown.msft.png":::
   切换视图选择器  
:::image-end:::  

> [!NOTE]
> 并非所有属性都存储在 JavaScript 堆上。  不捕获使用运行本机代码的 getter 实现的属性。  此外，不捕获数字等非字符串值。  

### 摘要视图  

最初，快照在 "摘要" 视图中打开，显示 "对象总数"，它们可能会展开以显示实例：  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png" alt-text="摘要视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-retainers.msft.png":::
   摘要视图  
:::image-end:::  

顶级条目是 "汇总" 行。  

| 顶级项 | 描述 |  
|:--- |:--- |  
| **构造函数** | 表示使用此构造函数创建的所有对象。  |  
| **距离** | 使用节点的最短简单路径显示到根的距离。  |  
| **浅大小** | 显示由特定构造函数创建的所有对象的平坦大小之和。  浅大小是对象所占用的内存大小 (通常情况下，数组和字符串具有较大的浅层大小 \ ) 。  另请参阅 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。  |  
| **保留大小** | 显示同一组对象中的最大保留大小。  在删除对象后，您可以释放的内存大小 \ (且无法再访问从属单元 ) 称为保留的大小。  另请参阅 [对象大小][DevtoolsMemoryProblems101ObjectSizes]。  |  

<!--| **Number of object instances** | Displayed in the # column.  |  -->  

在上部视图中展开 "汇总" 行后，将显示所有实例。  对于每个实例，浅和保留大小都显示在相应的列中。  字符后的数字 `@` 是对象的唯一 ID，使你可以基于每个对象比较堆快照。  

请注意，黄色对象具有 JavaScript 引用，红色对象是从一个具有黄色背景的分离节点引用。  

**堆探查器中的各种构造函数 \ (组 \ ) 条目对应于什么？**  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png" alt-text="构造函数组" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-constructor-highlight.msft.png":::
   构造函数组  
:::image-end:::  

| 构造函数 \ (组 \ ) 条目 | 描述 |  
|:--- |:--- |  
| **\ (global 属性 \ ) ** | 全局对象 \ (（如 `window` \ ) 和它引用的对象）之间的中间对象。  如果使用构造函数创建对象 `Person` 并由全局对象持有，则保留路径将如下所示 `[global] > \(global property\) > Person` 。  这与标准进行对比，其中对象直接相互引用。  出于性能原因，存在中间对象。  全局会定期修改全局，并且属性访问优化对非全局对象执行良好的作业不适用于全局对象。  |  
| **\ (根 \ ) ** | "保留树" 视图中的根项是引用所选对象的实体。  这些条目也可能是引擎为特定于引擎的目的而创建的引用。  该引擎已缓存哪些引用对象，但所有此类引用都很弱，并且不会阻止收集对象，因为没有真正的强引用。  |  
| **\ (关闭 ) ** | 通过函数闭包对一组对象的引用的计数。  |  
| **\ (数组、string、number、regexp \ ) ** | 包含属性的对象类型列表，这些属性引用数组、字符串、数字或正则表达式。  |  
| **\ (已编译的代码 \ ) ** | 与编译的代码相关的所有内容。  脚本类似于函数，但对应于 `<script>` 主体。  SharedFunctionInfos \ (SFI \ ) 是位于函数和编译代码之间的对象。  函数通常具有上下文，而 SFIs 不是。  |  
| **HTMLDivElement**、 **HTMLAnchorElement**、 **DocumentFragment**等。  | 对你的代码引用的特定类型的元素或文档对象的引用。  |  

<!--todo: add heap profiling summary section when available -->  

### 比较视图  

通过相互比较多个快照来查找泄漏的对象。  若要验证特定应用程序操作是否不会产生泄漏 \ (例如，通常一对直接和反向操作（如打开文档，然后关闭它）不应退出任何垃圾 ) ，您可能需要遵循以下方案：  

1.  在执行操作之前，请拍摄堆快照。  
1.  执行操作 \ (以某种方式与页面交互，使你认为导致泄漏 \n ) 。  
1.  执行反向操作 \ (执行相反的交互操作，并多次重复 \ ) 。  
1.  获取第二个堆快照，并将此快照的视图更改为 **比较**，将其与 **快照 1**进行比较。  
    
在 " **比较** " 视图中，显示两个快照之间的差异。  展开总条目时，将显示添加和删除的对象实例。  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png" alt-text="比较视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-comparison-dropdown.msft.png":::
   **比较** 视图  
:::image-end:::  

<!--todo: add HeapProfilingComparison section when available  -->  

### 包含视图  

**包含**视图实质上是应用程序的对象结构的 "鸟瞰图"。  它允许你在函数闭包内进行查看，以观察虚拟机 \ (VM \ ) 共同构成 JavaScript 对象的内部对象，并了解应用程序在非常低的级别上使用的内存量。  

| 包容视图入口点 | 描述 |  
|:--- |:--- |  
| **DOMWindow 对象** | 适用于 JavaScript 代码的全局对象。  |  
| **GC 根** | 由 VM 的垃圾回收使用的实际 GC 根。  GC 根由内置的对象映射、符号表、VM 线程堆栈、编译缓存、处理作用域和全局句柄组成。  |  
| **本机对象** | 在 JavaScript 虚拟机 \ (JavaScript VM \ ) 中的浏览器对象 "推送" 以允许自动化（例如，DOM 节点、CSS 规则）。  |  

:::image type="complex" source="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png" alt-text="包含视图" lightbox="../media/memory-problems-gh-nodejs-benchmarks-run-memory-heap-snapshots-containment-dropdown.msft.png":::
   **包含** 视图  
:::image-end:::  

<!--todo: add heap profiling containment section when available  -->  

> [!TIP]
> 有关闭包的提示。  对函数进行命名，以便能够轻松地区分快照中的闭包。  例如，此示例不使用命名的函数。  
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
> Followingcode 代码段使用命名的函数。  
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
> > 试一试此示例， [原因 `eval` 是][GlitchDevtoolsMemoryExample07] 分析闭包对内存的影响。  你可能还会对此示例进行关注，让你完成记录 [堆分配][GlitchDevtoolsMemoryExample08]。  
> 

## 查找颜色编码  

对象的属性和属性值具有不同的类型，并相应地着色。  每个属性都具有以下四种类型之一。  

| 属性类型 | 描述 |  
|:--- |:--- |  
| **a：属性** | 带有名称的常规属性，通过 `.` \ (点 \ ) 运算符或通过 `[` `]` \ (方括号 \ ) 表示法访问） `["foo bar"]` 。  |  
| **0：元素** | 带有数字索引的常规属性，通过 `[` `]` \ (方括号 \ ) 表示法访问。  |  
| **a：上下文 var** |  函数上下文中的一个变量，可通过函数闭中的变量名称进行访问。  |  
| **a：系统属性** | 由 JavaScript VM 添加的属性，无法从 JavaScript 代码访问。  |  

指定为 " `System` 不具有相应 JavaScript 类型的对象"。  每个都是 Javascript VM 的对象系统实现的一部分。  V8 将分配同一个堆中的大部分内部对象（用户的 JS 对象）。  因此，这些只是 V8 内部。  

## 查找特定对象  

若要查找所收集堆中的对象，您可以使用 `Ctrl` + `F` 进行搜索并提供对象 ID。  

## 发现 DOM 泄漏  

堆探查器能够反映浏览器本机对象 \ (DOM 节点、CSS 规则 \ ) 和 JavaScript 对象之间的双向依赖关系。
这有助于发现由于忘记分离的 DOM 子树而导致的不可见泄漏。  

DOM 泄漏可能比你想像的更大。  请考虑以下示例。  何时 #tree GC？  

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

`#leaf`维护对相关父代的引用 \ (parentNode \ ) 并向上递归 `#tree` ，因此仅当 leafRef 为 nullified 时，才是 GC 的候选项下的整个树 `#tree` 。  

:::image type="complex" source="../media/memory-problems-tree-gc.msft.png" alt-text="DOM 子树" lightbox="../media/memory-problems-tree-gc.msft.png":::
   DOM 子树  
:::image-end:::  

> [!NOTE]
> 示例：请尝试这种 [泄漏的 DOM 节点][GlitchDevtoolsMemoryExample06] 示例，了解它可能会泄漏的位置以及如何检测它。  你还可以查看此 [DOM 泄漏的示例比预期更大][GlitchDevtoolsMemoryExample09]。  

若要阅读有关 DOM 泄漏和内存分析基础知识的详细信息，请 [使用 Microsoft Edge DevTools Gonzalo Ruiz De Villa 查找和调试内存泄漏][GonzaloRuizdeVillaMemory] 。  

<!--  
> [!NOTE]
> Example: Try this **demo** to play with detached DOM trees.  
-->  

<!--todo: add heap profiling dom leaks section when available  -->  

<!--  
## Feedback   


-->  

<!-- links -->  

[DevtoolsMemoryProblems101ObjectSizes]: ./memory-101.md#object-sizes "对象大小-内存术语 |Microsoft 文档"  
[DevtoolsMemoryProblems101ObjectsRetainingTree]: ./memory-101.md#objects-retaining-tree "对象保留树内存术语 |Microsoft 文档"  

<!--[DevToolsHeapProfilingComparison]: https://developer.alphabet.com/devtools/docs/heap-profiling-comparison ""  -->  
<!--[DevToolsHeapProfilingContainment]: https://developer.alphabet.com/devtools/docs/heap-profiling-containment ""  -->  
<!--[DevtoolsHeapProfilingDomLeaks]: https://developer.alphabet.com/devtools/docs/heap-profiling-dom-leaks ""  -->  
<!--[DevToolsHeapProfilingSummary]: https://developer.alphabet.com/devtools/docs/heap-profiling-summary ""  -->  
<!--[DevtoolsProfileMemoryProblemsDiagnosisCausesMemoryLeaks]: ../profile/memory-problems/memory-diagnosis#narrow-down-causes-of-memory-leaks ""  -->  

[GlitchDevtoolsMemoryExample03]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-03.html "example-03.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample06]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-06.html "example-06.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample07]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-07.html "example-07.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample08]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-08.html "example-08.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample09]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-09.html "example-09.html-Microsoft Edge (Chromium) DevTools |故障"  
[GlitchDevtoolsMemoryExample10]: https://microsoft-edge-chromium-devtools.glitch.me/static/memory/example-10.html "example-10.html-Microsoft Edge (Chromium) DevTools |故障"  

[GonzaloRuizdeVillaMemory]: https://slid.es/gruizdevilla/memory "内存 |几"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/heap-snapshots) ，由 [Meggin Kearney][MegginKearney] (技术编写器 \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney  
