---
description: Microsoft Edge DevTools 协议版本 0.2 中受支持域的引用列表。
title: 'DevTools 协议域 - DevTools 协议版本 0.2 (EdgeHTML) '
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: reference
ms.prod: microsoft-edge
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 03688ff2a1757205cc1c83d23a13d205e38011c7
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232460"
---
# DevTools 协议域 - DevTools 协议版本 0.2 (EdgeHTML)   

## [CSS](css.md)  

此域公开 CSS 读/写操作。 样式表 (规则的所有 CSS 对象) 在相关对象的后续操作中使用的 `id` 关联。 每个对象类型都有一个特定的结构，并且这些结构在不同类型的对象之间 `id` 不可互换。 CSS 对象可以使用接受 DOM 节点 id `get*ForNode()` 的 (加载) 。 客户端还可以通过事件跟踪样式表，然后使用这些方法加载所需的 `styleSheetAdded` / `styleSheetRemoved` 样式表 `getStyleSheet[Text]()` 内容。
## [DOM](dom.md)
此域公开 DOM 读/写操作。 每个 DOM 节点都用其镜像对象表示，该对象具有一个 `id` 。 这可用于获取有关节点的其他信息、将节点解析 `id` 为 JavaScript 对象包装器等。客户端仅接收客户端已知的节点的 DOM 事件很重要。 后端跟踪发送到客户端的节点，从不发送同一节点两次。 客户端负责收集有关发送到客户端的节点的信息。<p>请注意， `iframe` 所有者元素将返回相应的文档元素作为其子节点。</p>
## [DOMDebugger](domdebugger.md)
DOM 调试允许设置特定 DOM 操作和事件的断点。 JavaScript 执行将在这些操作上停止，就像有常规断点集一样。
## [调试程序](debugger.md)
调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐步执行、探索堆栈跟踪等。
## [覆盖](overlay.md)
覆盖域公开视觉修饰和节点选择交互
## [页面](page.md)
与检查的页面相关的操作和事件属于页面域。
## [运行时](runtime.md)
运行时域通过远程评估和镜像对象公开 JavaScript 运行时。 评估结果作为镜像对象返回，该对象公开对象类型、字符串表示形式和唯一标识符，可用于进一步的对象引用。 原始对象将保留于内存中，除非显式释放它们。
## [架构](schema.md)
提供有关协议架构的信息。
