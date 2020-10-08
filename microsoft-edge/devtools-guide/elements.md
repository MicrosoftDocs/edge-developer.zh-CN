---
description: 使用 "元素" 面板检查页面的 HTML、CSS、DOM 和辅助功能。
title: DevTools-元素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/05/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools、元素、html、css、dom 断点、事件、辅助功能
ms.custom: seodec18
ms.openlocfilehash: 8948ddb3291bd122521e0b0800c0113a576d49e4
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10564293"
---
# 元素

" **元素** " 面板可帮助你：

* 在当前页的[HTML 树中标识和编辑元素](#html-tree-view)
* 在页面上[检查和修改 CSS](./elements/styles.md) ，包括伪状态和伪元素
* 了解页面上发生[的 CSS 布局和样式级联](./elements/computed.md)
* [跟踪无管理事件处理程序](./elements/events.md) ，以便你可以调试它们
* [设置调试断点以使意外的可视更改](./elements/dom-breakpoints.md) 跳转到引起它们的代码
* [获取有关页面上使用的字体](./elements/fonts.md) 以及加载位置的详细信息
* [通过屏幕阅读器的查看点查看页面](./elements/accessibility.md) ，验证和测试辅助功能 
* 查看你在调试页面 UI 时所做[的 CSS 更改的运行差异](./elements/changes.md)

## HTML 树视图

![Microsoft Edge DevTools 元素面板](./media/elements.png)

1. 使用 **Select 元素** (`Ctrl+B`) 工具在页面中单击元素以在 " **HTML" 树视图** 中找到该元素。

2. 使用 **元素突出显示** (`Ctrl+Shift+L`) 工具通过将元素悬停在 **HTML 树视图**中，在页面上查找元素。

3. 打开 " **颜色选取器** " (`Ctrl+K`) 工具 "以查看当前页面上使用的颜色列表。 单击列表上的颜色将提供更多详细信息 (色调、饱和度、亮度、Alpha) 。 在 "**样式**" 窗格中单击颜色值旁边的彩色方块时，*颜色选取器*也会打开，允许编辑页面元素的颜色并立即查看结果。

4. " **辅助功能树** (`Ctrl+Shift+A`) " 按钮将打开 " [辅助功能树](./elements/accessibility.md) " 窗格，其中显示页面的结构，其外观与辅助技术（如 [Windows 讲述人](https://support.microsoft.com/help/22798/windows-10-narrator-get-started) screenreader）的结构相同。

5. 还可以**Find** `Ctrl+F` 通过搜索 HTML 树视图中的标记名称、属性或文本内容来查找 () 元素。

### 编辑元素

你可以通过右键单击 HTML 树视图中的元素，然后从上下文菜单中选择 " **编辑为 HTML** " 来编辑该元素。 上下文菜单还提供用于删除、剪切、复制、粘贴、设置 CSS 伪类 (的选项： " *活动*"、 *： "焦点*" *： "悬停*"、"已 *访问* ") 和 "添加属性"。 编辑属性和/或其值的另一种方法是在 HTML 树视图中双击它。

![HTML 树视图上下文菜单](./media/elements_html_tree_context.png)

> [!NOTE]
> 编辑 HTML 树不会影响基础源标记。 刷新页面将还原所做的更改，并仅呈现由页面源确定的布局。 若要 **将** 修改后的 HTML 复制到剪贴板，请右键单击所需的元素 (或全局 `html` 元素（如果希望整个页面) 打开上下文菜单）。  (" **剪切** " 和 " **粘贴** " 选项也可) 。

从 " [样式](./elements/styles.md) " 窗格中，你还可以添加/删除/编辑 CSS 伪状态和伪元素。

## 工具窗格

选择了感兴趣的页面元素后，你可以使用工具窗格来进一步检查其不同的样式和辅助功能属性，查看其事件侦听器，并设置 DOM 转变断点。

!["元素" 面板上的工具窗格](./media/elements_toolpanes.png)

1. [**样式**](./elements/styles.md)：当前应用的样式，按样式表组织

2. 已[**计算**](./elements/computed.md)：当前应用的按 CSS 属性组织的样式

3. [**事件**](./elements/events.md)：在当前元素和上级元素上注册的事件侦听器

4. [**Dom 断点**](./elements/dom-breakpoints.md)： Dom 转变断点 

5. [**字体**](./elements/fonts.md)：当前对选定元素应用的字体

6. [**辅助功能**](./elements/accessibility.md)：辅助功能属性

7. [**更改**](./elements/changes.md)：在诊断会话期间进行的 CSS 更改  

## 快捷方式

| 操作               | 快捷方式               |
|:---------------------|:-----------------------|
| 元素面板       | `Ctrl` + `1`           |
| 元素突出显示 | `Ctrl` + `Shift` + `L` |
| 选择元素       | `Ctrl` + `B`           |
| 颜色选取器         | `Ctrl` + `K`           |
| 辅助功能树   | `Ctrl` + `Shift` + `A` |
