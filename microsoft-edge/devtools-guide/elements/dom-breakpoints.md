---
description: 使用 DOM 断点直观地调试页面上的布局故障
title: DevTools-DOM 断点
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、元素、dom 断点、dom 转变
ms.custom: seodec18
ms.openlocfilehash: 4e9eab4727cf1c3ef74b69495dd972838985e589
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564280"
---
# DOM 断点

从此窗格管理 DOM 转变断点，包括禁用、删除和重新绑定。

当所选元素节点发生更改时，可以使用 DOM 转变断点中断调试器。 这有助于跟踪负责在你的 UI 中导致视觉故障的代码，而无需在 *EdgeHTML* 中的每个 450 + DOM api 上设置单个断点，从而触发此类更改。 

若要设置 DOM 断点，请右键单击 " **元素** " 面板中的任意元素 *HTML 树视图* 以打开上下文菜单。

![DOM 断点上下文菜单](../media/elements_dom_breakpoints_contextmenu.png)

你可以设置以下任意断点：

 - **删除节点上的中断**：在从文档 (DOM 树) 中删除所选元素时，中断到调试器。

 - **已修改的子树中断**：当所选元素的任何子代更改 (添加、删除或其子树被修改) 时，请中断调试程序。 修改属性时不会中断 (请参阅该) 的 "下一步" 选项。

 - **已修改的属性中断**：在值中添加、删除或更改所选元素的属性时，请中断调试程序。

然后，" **dom 断点** " 窗格将通过生成一个选择器来列出所选元素 (，该选择器描述其在 DOM) 中的位置以及已设置的断点类型 (*节点已被删除、子树已修改、属性已* 修改) 。 在此处，你还可以重新 *绑定*、 *禁用*或 *删除* 你的断点，从 rt 单击上下文菜单中单独 () 或同时使用 "按钮) " (。

![DOM 断点窗格](../media/elements_dom_breakpoints.png)

## 断点持久性

断点存储 (和范围内，其在) 中设置为 DevTools 设置的一部分的页面的 URL。 重新加载页面或关闭并重新打开工具后，DevTools 将尝试将断点重新绑定到其关联的元素。

无法自动 rebinded 的断点以断点圆圈上的警告图标表示。 对于这些内容，你可以等待手动重新绑定该元素 (使用 "重新 **绑定断点** " 按钮和/或上下文菜单选项) 只要相应元素出现在 (DOM 中，断点图标将不再显示警告指示器) ，或者完全 **删除** 断点。

![未绑定断点指示器](../media/elements_dom_breakpoint_unbound.png)

除了此*DOM 断点*窗格外，你还可以在**调试器**中管理你的[DOM 断点](../debugger.md#dom-breakpoints)。

## 当前限制

请注意在 Edge DevTools 中 DOM 断点调试的以下限制：

- Edge DevTools 目前不支持[ `<iframe>` s](https://developer.mozilla.org/docs/Web/HTML/Element/iframe)中的重新绑定断点。 如果在 iframe 中设置断点并关闭边缘 DevTools 或刷新页面，则断点将丢失。

- 如果你的脚本在 DOM 完成之前遇到同步执行的断点 [`readyState`](https://developer.mozilla.org/docs/Web/API/Document/readyState) ，则你将无法在调试器暂停时设置 DOM 断点。 你通常可以通过设置 [`defer`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 或脚本属性来解决此情况 [`async`](https://developer.mozilla.org/docs/Web/HTML/Element/script#Attributes) 。

- 对于同步脚本，我们会在调用事件时触发断点的自动重新绑定 [`window.onload`](https://developer.mozilla.org/docs/Web/API/GlobalEventHandlers/onload) 。 在这种情况下，我们可能会错过在 DOM 的初始脚本驱动内部版本期间将触发的绑定断点。 对于异步脚本，我们会在执行第一个脚本之前触发重新绑定尝试，因此你的断点可能会根据需要重新绑定和触发。
