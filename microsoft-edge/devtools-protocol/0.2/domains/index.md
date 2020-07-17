---
description: Microsoft Edge DevTools 协议版本0.2 中支持的域的引用列表。
title: DevTools 协议域-DevTools 协议版本0.2 （EdgeHTML）
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 07/16/2020
ms.topic: reference
ms.prod: microsoft-edge
ms.openlocfilehash: ba56b31bb750eb9c575c6d13ef296aae6604e99f
ms.sourcegitcommit: a06c86ef7c69e1e400a0be5938449f3c4ba6ec72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/16/2020
ms.locfileid: "10882749"
---
# DevTools 协议域-DevTools 协议版本0.2 （EdgeHTML）  

## [CSS](css.md)  

此域公开 CSS 读/写操作。 所有 CSS 对象（样式表、规则和样式）在 `id` 相关对象的后续操作中都有相关联的已使用。 每个对象类型都有一个特定的 `id` 结构，它们在不同类型的对象之间不能互换。 可以使用 `get*ForNode()` 调用（接受 DOM 节点 id）加载 CSS 对象。 客户端还可以通过事件跟踪样式表 `styleSheetAdded` / `styleSheetRemoved` ，随后使用这些方法加载所需的样式表内容 `getStyleSheet[Text]()` 。
## [DOM](dom.md)
此域公开了 DOM 读/写操作。 每个 DOM 节点都由其镜像对象表示，其镜像对象具有 `id` 。 这 `id` 可用于获取有关节点的其他信息、将其解析为 JavaScript 对象包装等。客户只能接收客户端已知节点的 DOM 事件，这一点非常重要。 后端将跟踪已发送到客户端的节点，并且不会两次发送相同的节点。 客户负责收集有关已发送到客户端的节点的信息。<p>请注意， `iframe` 所有者元素将返回对应的文档元素作为其子节点。</p>
## [DOMDebugger](domdebugger.md)
DOM 调试允许在特定的 DOM 操作和事件上设置断点。 由于设置了常规断点，JavaScript 执行将在这些操作上停止。
## [调试程序](debugger.md)
调试器域公开 JavaScript 调试功能。 它允许设置和删除断点、逐句通过执行、浏览堆栈跟踪等。
## [覆盖](overlay.md)
覆盖域公开视觉装饰和节点选择交互
## [Page](page.md)
与已检查页面相关的操作和事件属于页面域。
## [运行时](runtime.md)
运行时域通过远程计算和镜像对象公开 JavaScript 运行时。 计算结果以镜像对象的形式返回，该对象公开可用于进一步对象引用的对象类型、字符串表示形式和唯一标识符。 原始对象将保留在内存中，除非它们被显式释放。
## [架构](schema.md)
提供有关协议架构的信息。