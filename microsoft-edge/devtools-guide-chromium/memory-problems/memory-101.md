---
description: 本部分介绍内存分析中使用的常见术语，并适用于不同语言的各种内存分析工具。
title: 内存术语
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 09/01/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 3455b05cf19f3aa5a69de5571ab3a24d5654dfe4
ms.sourcegitcommit: 63e6d34ff483f3b419a0e271a3513874e6ce6c79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/02/2020
ms.locfileid: "10992748"
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

# 内存术语  

本部分介绍内存分析中使用的常见术语，并适用于不同语言的各种内存分析工具。  

此处所述的条款和概念指的是 [内存面板][DevtoolsMemoryProblemsHeapSnapshots]。  如果您曾经使用过 Java、.NET 或其他一些内存探查器，则这可能是复习。  

## 对象大小  

将内存视为具有基元类型 \ (的图形，例如数字和字符串 \ ) 和对象 \ (关联数组 \ ) 。  它可能以图形形式表示为具有许多互连点的图形，如下所示：  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="内存的可视化表示形式" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   内存的可视化表示形式  
:::image-end:::  

对象可以通过两种方式保留内存：  

*   直接由对象。  
*   通过保留对其他对象的引用来进行隐式处理，从而阻止这些对象被垃圾回收器 \ (**GC** 的短 \ ) 自动释放。  

在 DevTools 中使用 [内存][DevtoolsMemoryProblemsHeapSnapshots] 面板 \ (用于调查在 **内存**) 下找到的内存问题的工具时，您可能会发现自己的信息有几个不同列。  有两个是 **浅大小** 和 **保留大小**，但它们代表什么？  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅和保留大小" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   浅和保留大小  
:::image-end:::  

### 浅大小  

这是对象占用的内存大小。  

典型的 JavaScript 对象为其描述保留了一些内存，并用于存储即时值。  通常，只有数组和字符串能够具有显著的浅规格。  但是，字符串和外部数组在呈现器内存中通常具有主存储，仅在 JavaScript 堆上公开一个小型包装对象。  

呈现器内存是已检查页面呈现的进程的所有内存：页面上启动的页面 + JS 堆内存的本机内存 + JS 堆内存。  尽管如此，即使是小对象也可以通过自动垃圾回收进程来处理其他对象，从而间接容纳大量内存。  

### 保留大小  

这是在删除对象后释放的内存大小，以及从 **垃圾回收器根** \ (GC 根 \ ) 中无法访问的依赖对象。  

**垃圾回收器根** \ (GC 根 \ ) 是由创建的句柄组成的，当从本机代码引用 V8 之外的 JavaScript 对象时，将创建一个 **句柄** \ (本地或全局 \ ) 。  所有此类句柄都可以在 " **gc 根**" 下的堆快照中找到  >  ，它**处理作用域**和**GC 根**  >  **全局句柄**。  在此文档中描述句柄，而无需深入了解浏览器实现的详细信息可能会令人困惑。  垃圾回收器 (GC) 根和句柄不是你需要担心的事情。  

有许多内部 GC 根，其中大多数不会对用户感兴趣。  从应用程序角度看，有以下类型的根。  

*   每个 iframe 中的 Window 全局对象 \ () 。  堆快照中有一个距离字段，这是窗口的最短保留路径上的属性引用数。  
*   文档 DOM 树，其中包含通过遍历文档可访问的所有本地 DOM 节点。  并非所有节点都可以具有 JS 包装，但如果节点具有包装器，则在文档处于活动状态时，它处于活动状态。  
*   有时，" **源** " 面板中的调试器上下文和 **控制台** 的 (中的对象可能会保留，例如在 console 评估 \ ) 之后。  在 "**源**" 面板中，使用已清除的**控制台**面板和调试器中没有活动断点创建堆快照。

>[!TIP]
> 在 " **Console** `clear()` [内存" 面板][DevtoolsMemoryProblemsHeapSnapshots]中获取堆快照之前，通过运行和停用 "**源**" 面板中的断点来清除控制台面板。

内存图从根开始，它可能是 `window` 浏览器的对象或 `Global` Node.js 模块的对象。  你不会控制此根对象 (GCd) 进行垃圾回收的方式。  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="你无法控制如何对根对象进行垃圾回收。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   你无法控制如何对根对象进行垃圾回收。  
:::image-end:::  

从根中无法访问的任何内容都会获得垃圾回收 \ (GCd \ ) 。  

> [!NOTE]
> " [浅层大小](#shallow-size) " 和 " [保留大小](#retained-size) " 列均表示数据，以字节为单位。  

## 对象保留树  

堆是互连对象的网络。  在数学世界中，此结构称为 **图形** 或内存图。  图形由通过**边缘**连接的节点构造，这两个**节点**都具有标签。  

*   **节点** \ (或 **对象**\ ) 使用用于生成它们的 **构造** 函数的名称进行标记。  
*   使用**属性**名称对**边缘**进行标记。  

了解 [如何使用堆探查器录制配置文件][DevtoolsMemoryProblemsHeapSnapshots]。  下图中，你可能在 " [内存" 面板][DevtoolsMemoryProblemsHeapSnapshots] 的堆快照记录中看到的一些引人注目的内容包括距离：垃圾回收器 \ (GC \ ) root 的距离。  如果几乎所有相同类型的对象都在同一距离上，并且有几个更远的距离，这就是值得研究的事情。  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="与根的距离" lightbox="../media/memory-problems-root.msft.png":::
   与根的距离  
:::image-end:::  

## Dominators  

Dominator 对象由树形结构组成，因为每个对象都有一个 Dominator。  对象的 dominator 可能缺少直接引用它 dominates 的对象;也就是说，dominator 的树不是图形的生成树。  

在下图中，以下语句为 true。  

*   节点 1 dominates 节点2  
*   节点 2 dominates 节点3、4和6  
*   节点 3 dominates 节点5  
*   节点 5 dominates 节点8  
*   节点 6 dominates 节点7  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="Dominator 树结构" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   Dominator 树结构  
:::image-end:::  

在下图中，node `#3` 是的 dominator `#10` ，但 `#7` 也存在于来自垃圾回收器 \ (GC \ ) 的每个简单路径中 `#10` 。  因此，对象 B 是对象 A 的 dominator，即 B 存在于从根到对象 A 的每个简单路径中的 a。  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="动画 dominator 图" lightbox="../media/memory-problems-dominators.msft.gif":::
   动画 dominator 图  
:::image-end:::  

## V8 详细信息  

分析内存时，了解堆快照的外观很有帮助。  本部分介绍了一些内存相关主题，特别是与 **V8 JavaScript virtual machine** \ (V8 VM 或 vm \ ) 相关联。  

### JavaScript 对象表示形式  

有三种基元类型：  

*   数字 \ (例如 `3.14159...` \ )   
*   布尔值 \ (`true` 或 `false` \ )   
*   字符串 \ (例如 `"Werner Heisenberg"` \ )   

基元不能引用其他值，并且始终 leafs 或终止节点。  

**数字** 可以存储为：  

*   名为 **小整数** 的直接31位整数值 \ (**SMI**s \ ) ，或者  
*   堆对象，称为 **堆编号**。 堆编号用于存储不适合 SMI 形式的值（如 **双精度或双精度**型），或者需要对值进行 **装箱**时（如在其上设置属性）。  

**字符串** 能够存储在以下其中一种：  

*   **VM 堆**或
*   在呈现器的 **内存**中外部。  创建一个 **包装对象** ，并使用它来访问外部存储，例如，存储从 Web 接收的脚本源和其他内容，而不是将其复制到 VM 堆。

新 JavaScript 对象的内存是从专用的 JavaScript 堆 \ (或 **VM 堆**\ ) 分配的。  这些对象由 V8 中的垃圾回收器管理，因此只要存在至少一个强引用，就保持活动。  

任何不在 JavaScript 堆中的内容称为 **本机对象**。  与堆对象相比，本机对象不会在其整个生存期内由 V8 垃圾回收器管理，并且只能通过 javascript 包装对象从 JavaScript 中访问。  

**缺点字符串** 是包含存储和联接的字符串对，并且是连接的结果的对象。  仅在需要时，才会出现操作 **字符串** 内容的联接。 当需要构造联接的字符串的子字符串时，就会出现一个示例。

例如，如果你连接， `a` `b` 则会收到一个 `(a, b)` 表示连接结果的字符串。  如果稍后 `d` 与该结果连接，将获得另一个 **缺点字符串**： `((a, b, d)` 。  

**Array** 是带有数字键的对象。 **数组** 在 V8 VM 中广泛用于存储大量数据。 键/值对的集（如字典）由 **数组**进行备份。  

典型的 JavaScript 对象被存储为两种 **数组** 类型中的一种：  

*   命名属性和  
*   数字元素  

当存在少量属性时，属性在内部存储在 JavaScript 对象中。  

**Map** 是描述对象类型和布局的对象。 例如，映射用于描述用于 [快速属性访问][V8FastProperties]的隐式对象层次结构。  

### 对象组  

每个 **本机对象** 组都由相互保持相互引用的对象组成。  例如，请考虑一个 DOM 子树，其中每个节点都有指向相对父级的链接和指向下一个子元素和下一个同级元素的链接，从而形成连接的图表。  

> [!NOTE]
> 在 JavaScript 堆中不表示本机对象。  缺少表示是为什么本机对象的大小为零的原因。 而是创建包装对象。  

每个包装对象都包含对相应本机对象的引用，用于将命令重定向到该对象。  反过来，对象组保留包装对象。  但是，这不会创建 uncollectable 循环，因为垃圾回收器 \ (GC \ ) 非常智能，足以释放其包装不再被引用的对象组。 但忘记发布单个包装器会保留整个组和关联的包装。  

## 与 Microsoft Edge DevTools 团队取得联系  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "如何录制堆快照 |Microsoft 文档"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 | 中的快速属性V8"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) ，由 [Meggin Kearney][MegginKearney] (技术编写器 \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
