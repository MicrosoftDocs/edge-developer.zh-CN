---
description: 使用 DOM 断点直观调试页面上的布局故障
title: DevTools - 元素 - DOM 断点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 元素， dom 断点， dom 检测
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: cb60fa0497c98c152ca2c5adf28e9dee5d7c9f98
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232298"
---
# DOM 断点

管理此窗格中的 DOM 分解断点，包括禁用、删除和重新绑定它们。

只要选定元素节点发生更改，就可以使用 DOM 破坏断点来中断调试程序。 这有助于跟踪导致 UI 出现视觉故障的代码，而无需在 *EdgeHTML* 中可触发此类更改的 450 多个 DOM API 上设置单独的断点。 

若要设置 DOM 断点，请右键单击"元素"**** 面板*HTML 树视图中*的任何元素以打开上下文菜单。

![DOM 断点上下文菜单](../media/elements_dom_breakpoints_contextmenu.png)

可以设置以下任何断点：

 - **在已删除的节点上**中断：从 DOM 树文档中删除所选元素时， (调试) 。

 - **修改了子**树上的中断：当所选元素的任何后代发生更改时， (、删除或修改其子树时中断) 。 当属性被修改时，这不会中断 (查看下一个选项) 。

 - **修改属性时中断**：在值中添加、删除或更改选定元素的属性时，中断调试程序。

**然后，DOM**断点窗格将列出所选元素 (，具体操作是生成一个选择器，该选择器描述其在 DOM) 中的位置，以及已设置删除 (*节点*、修改了子树、修改了属性的断点) 。 在此处，您还可以使用 (按钮** 从 rt-click 上下文** 菜单) 或一次重新绑定、禁用或删除断点 (断点) 。 **

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## 断点持久性

断点存储在 (范围设置为在开发人员工具设置) 中设置的页面的 URL。 重新加载页面或关闭并重新打开工具时，DevTools 将尝试将断点重新绑定到其关联元素。

无法自动重新绑定的断点在断点圆圈上用警告图标指示。 对于这些元素，你可以等待在 DOM ( (中出现相应元素后****，使用重新绑定断点按钮和/或上下文菜单选项) 手动重新绑定元素) ，或者完全删除断点。 ****

![未绑定断点指示器](../media/elements_dom_breakpoint_unbound.png)

除了此 *DOM 断* 点窗格，您还可以从调试器中管理 [DOM](../debugger.md#dom-breakpoints) **断点**。

## 当前限制

请注意边缘开发人员工具中 DOM 断点调试的以下限制：

- Edge DevTools 当前不支持重新绑定内部[ `<iframe>` 断点](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)。 如果在 iframe 中设置断点并关闭 Edge DevTools 或刷新页面，断点将丢失。

- 如果脚本在 DOM 完成之前遇到同步执行的断点，将无法在调试程序暂停时设置 [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) DOM 断点。 通常可以通过设置或脚本属性 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 来 [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 补救这种情况。

- 对于同步脚本，在调用事件时触发断点的 [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) 自动重新绑定。 在这种情况下，我们可能会错过绑定断点，这些断点将在 DOM 的初始脚本驱动构建过程中触发。 对于异步脚本，我们在执行第一个脚本之前触发重新绑定尝试，以便断点可以按需要重新绑定和触发。
