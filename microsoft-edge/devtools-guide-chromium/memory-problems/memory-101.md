---
description: 本节介绍在内存分析中使用的常用术语，适用于适用于不同语言的各种内存分析工具。
title: 内存术语
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 02/12/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 1579374be29f0f419ded3bf88f5dea284f0bbb1a
ms.sourcegitcommit: 6cf12643e9959873f8b5d785fd6158eeab74f424
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2021
ms.locfileid: "11397788"
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

# <a name="memory-terminology"></a>内存术语  

本文介绍在内存分析中使用的常用术语，适用于不同语言的各种内存分析工具。  

此处所述的术语和概念是指内存 [面板][DevtoolsMemoryProblemsHeapSnapshots]。  如果您曾经使用 Java、.NET 或其他一些内存探查器，则本文可能是一个刷新程序。  

## <a name="object-sizes"></a>对象大小  

将内存视为包含基元类型 \ (如数字和字符串\) 和对象 \ (关联数组\) 。  它可能显示为具有许多互连点的图形，如下图所示。  

:::image type="complex" source="../media/memory-problems-thinkgraph.msft.png" alt-text="内存的视觉表示形式" lightbox="../media/memory-problems-thinkgraph.msft.png":::
   内存的视觉表示形式  
:::image-end:::  

对象可能以两种方式保留内存：  

*   直接由对象。  
*   隐式保留对其他对象的引用，从而阻止垃圾回收器自动释放这些对象。  

使用 DevTools \ (中的"内存"面板时) **在"内存**"\) 下发现的内存问题的工具，你可能会发现自己正在查看一些不同的信息列。 [][DevtoolsMemoryProblemsHeapSnapshots]  其中两个突出的" **浅** 表大小和 **保留大小**"，但它们表示什么？  

:::image type="complex" source="../media/memory-problems-shallow-retained.msft.png" alt-text="浅表和保留大小" lightbox="../media/memory-problems-shallow-retained.msft.png":::
   浅表和保留大小  
:::image-end:::  

### <a name="shallow-size"></a>浅表大小  

这是对象所持有的内存大小。  

典型的 JavaScript 对象具有一些内存，用于描述和存储即时值。  通常，只有数组和字符串才能具有明显的浅表大小。  但是，字符串和外部数组通常具有呈现器内存中的主存储，从而在 JavaScript 堆上仅公开一个小包装对象。  

呈现器内存是呈现已检查页面的过程的所有内存：页面的本机内存 + JS 堆内存 + 页面启动的所有专用工作者的 JS 堆内存。  但是，即使是一个小对象，也能够通过防止自动垃圾回收过程释放其他对象，间接地保留大量内存。  

### <a name="retained-size"></a>保留大小  

这是删除对象后释放的内存大小，以及从垃圾回收器根目录无法访问的从属 **对象**。  

**垃圾回收器**根目录由在从**** 本机代码引用 V8 外部的 JavaScript 对象时创建 \ (本地或全局\) 的句柄所构建。  可以在 GC 根目录下的堆快照中找到所有**** 此类句柄 处理范围和  >  ******GC 根**  >  **全局句柄**。  在本文档中介绍句柄而不深入介绍浏览器实现的详细信息可能会令人困惑。  垃圾收集器根和句柄都不需要担心。  

有很多内部垃圾回收器根目录，其中大多数对用户没有兴趣。  从应用程序的角度来看，有以下类型的根。  

*   窗口全局对象 \ (每个 iframe\) 。  堆快照中的距离字段是窗口最短保留路径上的属性引用数。  
*   文档 DOM 树，由通过遍历文档可到达的所有本机 DOM 节点组成。  并非所有节点可能都有 JS 包装器，但如果节点有包装器，则文档处于活动状态时该节点是活动节点。  
*   有时，对象可能由"源"面板和**控制台**\ (中的调试器上下文保留，例如，在控制台评估\) 。 ****  使用清除的控制台面板创建**** 堆快照，在"源"面板的调试器中没有活动的**断**点。

>[!TIP]
> 在"**内存**"面板中拍摄堆快照之前，通过运行和停用"源"面板中的断点来 `clear()` 清除[控制台面板][DevtoolsMemoryProblemsHeapSnapshots]。 ****

内存图以根开头，根目录可能是浏览器的对象或Node.js `window` `Global` 对象。  您不控制如何垃圾回收此根对象。  

:::image type="complex" source="../media/memory-problems-dontcontrol.msft.png" alt-text="你无法控制如何垃圾回收根对象。" lightbox="../media/memory-problems-dontcontrol.msft.png":::
   你无法控制如何垃圾回收根对象。  
:::image-end:::  

从根目录无法到达的任何对象都会进行垃圾回收。  

> [!NOTE]
> 浅[表大小和](#shallow-size)[保留大小](#retained-size)列都表示数据（以字节为单位）。  

## <a name="objects-retaining-tree"></a>保留树的对象  

堆是互连对象的网络。  在数学世界，此结构称为 **图形或** 内存图。  图形由通过边缘连接的节点**** 构造，这两个**** 节点都提供标签。  

*   **节点**\ (**或对象**\) 使用用于生成节点的构造函数函数的名称进行**** 标记。  
*   **边缘** 使用属性名称 **进行标记**。  

了解如何 [使用堆探查器记录配置文件][DevtoolsMemoryProblemsHeapSnapshots]。  下图中，内存工具中堆快照记录中的一些值得注意的事项包括距离：[][DevtoolsMemoryProblemsHeapSnapshots]垃圾回收器根之间的距离。  如果几乎所有相同类型的对象都位于同一距离，而一些对象距离较大，则值得调查。  

:::image type="complex" source="../media/memory-problems-root.msft.png" alt-text="与根之间的距离" lightbox="../media/memory-problems-root.msft.png":::
   与根之间的距离  
:::image-end:::  

## <a name="dominators"></a>Dominators  

管理程序对象由树结构组成，因为每个对象只有一个管理程序。  对象的管理者可能缺少对它所控制对象的直接引用;也就是说，管理者树不是图形的跨树。  

下图中，以下语句为 true。  

*   节点 1 控制节点 2  
*   节点 2 控制节点 3、4 和 6  
*   节点 3 与节点 5  
*   节点 5 控制节点 8  
*   节点 6 与节点 7  

:::image type="complex" source="../media/memory-problems-dominatorsspanning.msft.png" alt-text="管理程序树结构" lightbox="../media/memory-problems-dominatorsspanning.msft.png":::
   管理程序树结构  
:::image-end:::  

下图中，节点是管理者，但也存在于从垃圾回收器到的每个 `#3` `#10` `#7` 简单路径 `#10` 中。  因此，如果 B 存在于从根到对象 A 的每一个简单路径中，则对象 B 是对象 A 的管理者。  

:::image type="complex" source="../media/memory-problems-dominators.msft.gif" alt-text="动画管理者图示" lightbox="../media/memory-problems-dominators.msft.gif":::
   动画管理者图示  
:::image-end:::  

## <a name="v8-specifics"></a>V8 特定内容  

分析内存时，了解堆快照为何以特定方式显示非常有用。  本节介绍一些与内存相关的主题，这些主题专门对应于 **V8 JavaScript** 虚拟机 \ (V8 VM 或 VM\) 。  

### <a name="javascript-object-representation"></a>JavaScript 对象表示形式  

有三种基元类型：  

*   数字 \ (例如 `3.14159...` \)   
*   布尔值 \ (`true` 或 `false` \)   
*   字符串 \ (例如 `"Werner Heisenberg"` \)   

基元无法引用其他值，并且始终为叶或终止节点。  

**数字** 可以存储为：  

*   称为小整数 **\ (** **SMI\) **的 31 位整数值，或  
*   堆对象，称为 **堆数**。 堆编号用于存储不适合 SMI 表单的值（如双精度数）或需要对**** 值进行装箱时（如设置其属性）。 ****  

**字符串** 可以在两者之一中存储：  

*   **VM 堆**，或
*   在呈现 **器的内存中**。  创建 **包装** 对象并用于访问外部存储，例如，从 Web 接收的脚本源和其他内容存储，而不是复制到 VM 堆。

新 JavaScript 对象的内存从专用 JavaScript 堆 \ (**或 VM 堆**\) 。  这些对象由 V8 中的垃圾回收器管理，因此，只要至少有一个对对象的强引用，它们就保持活动状态。  

不在 JavaScript 堆中任何内容都称为 **本机对象**。  与堆对象相反，本机对象在生命周期内不由 V8 垃圾回收器管理，并且只能使用 JavaScript 包装对象从 JavaScript 访问。  

**Cons 字符串** 是一个对象，由存储并随后联接的字符串对组成，它是连接的结果。  仅根据需要 **联接 cons 字符串** 内容。  例如，当需要构造联接字符串的子字符串时。

例如，如果连接和 ，则得到一个字符串，该字符串表示 `a` `b` `(a, b)` 连接的结果。  如果稍后与该结果连接 `d` ，则得到另一个 **cons 字符串**： `((a, b, d)` .  

**数组** 是一个包含数字键的对象。 **数组** 在 V8 VM 中广泛使用，用于存储大量数据。 键值对集（如字典）由数组 **进行备份**。  

典型的 JavaScript 对象仅存储为两种数组类型 **之一** ：  

*   命名属性，以及  
*   数值元素  

当有少量属性时，这些属性将存储在 JavaScript 对象内部。  

**Map** 是描述对象种类和布局的对象。 例如，地图用于描述隐式对象层次结构，以 [快速访问属性][V8FastProperties]。  

### <a name="object-groups"></a>对象组  

每个 **本机对象** 组由相互引用的对象所共同决定。  例如，考虑一个 DOM 子树，其中每个节点都有一个指向相对父元素的链接和指向下一个子级和下一个同级元素的链接，因此形成一个连接的图形。  

> [!NOTE]
> 本机对象不表示在 JavaScript 堆中。  缺少表示形式是本机对象的大小为零的原因。 而是创建包装对象。  

每个包装对象保留对相应本机对象的引用，以将命令重定向到该对象。  反过来，对象组保留包装对象。  但是，这不会创建一个无法收集的循环，因为垃圾回收器足够智能，可以释放不再引用其包装的对象组。  但忘记释放单个包装器会保留整个组和关联的包装器。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsMemoryProblemsHeapSnapshots]: ./heap-snapshots.md "如何记录堆快照|Microsoft Docs"  

[V8FastProperties]: https://v8.dev/blog/fast-properties "V8 属性中的快速|V8"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面位于 [此处，](https://developers.google.com/web/tools/chrome-devtools/memory-problems/memory-101) 由 [Meggin Kearney][MegginKearney] \ (Technical Writer\) 。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[MegginKearney]: https://developers.google.com/web/resources/contributors/megginkearney
