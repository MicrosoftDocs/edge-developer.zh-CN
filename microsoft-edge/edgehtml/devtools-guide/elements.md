---
description: 使用"元素"面板检查页面的 HTML、CSS、DOM 和辅助功能。
title: DevTools - 元素
author: MSEdgeTeam
ms.author: msedgedevrel
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge， Web 开发， f12 工具， devtools， 元素， html， css， dom 断点， 事件， 辅助功能
ms.custom: seodec18
ms.date: 11/19/2020
ROBOTS: NOINDEX,NOFOLLOW
ms.openlocfilehash: 14052bc40b9f94e628f0b575ede6c1ca8ccf179a
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11232133"
---
# 元素

" **元素** "面板可帮助你：

* [标识和编辑当前页面的 HTML](#html-tree-view) 树中的元素
* [检查和修改页面上的 CSS，](./elements/styles.md) 包括伪状态和伪元素
* [了解页面上发生的 CSS](./elements/computed.md) 布局和样式级联
* [跟踪未授权事件处理程序](./elements/events.md) ，以便你可以调试它们
* [设置调试断点，以便意外的视觉更改](./elements/dom-breakpoints.md) 跳转到导致它们的代码
* [获取有关页面上使用的字体](./elements/fonts.md) 及其加载位置的详细信息
* [从屏幕阅读器的角度查看页面以](./elements/accessibility.md) 验证和测试辅助功能 
* [在调试页面 UI](./elements/changes.md) 时，查看 CSS 更改的运行差异

## HTML 树视图

![Microsoft Edge DevTools 元素面板](./media/elements.png)

1. 使用**Select 元素** () 在 HTML 树视图中通过单击该元素在页面中找到 `Ctrl+B` 该元素。 ****

2. 使用 **元素突出显示** () 工具，通过将鼠标悬停在 HTML 树视图中的某个元素，找到 `Ctrl+Shift+L` **页面上的元素**。

3. 打开 **颜色选取** 器 () 查看当前页面上 `Ctrl+K` 使用的颜色列表。 单击列表上的颜色将提供有关色调、饱和度 (亮度、Alpha 颜色、alpha) 。 当您*单击*"样式"窗格中的颜色值旁边的彩色正方形时，颜色选取器也会打开，从而**** 允许您编辑页面元素的颜色并立即查看结果。

4. "**** 辅助功能 () 按钮将打开"辅助功能"树窗格，显示页面的结构，就像它向辅助技术（如 `Ctrl+Shift+A` Windows[讲述](https://support.microsoft.com/help/22798/windows-10-narrator-get-started)[](./elements/accessibility.md)人屏幕阅读器）显示一样。

5. 您还可以 **通过** () 属性或文本内容，在 HTML 树视图中查找元素 `Ctrl+F` 的名称。

### 编辑元素

可以通过在 HTML 树视图中右键单击某个元素，然后从上下文菜单中选择"编辑 **为 HTML"** 来编辑元素。 上下文菜单还提供了删除、剪切、复制、粘贴、设置 CSS 伪类 (*：active*、 *：focus*、 *：hover*、 *：visited*) 和添加属性的选项。 编辑属性和/或其值的另一种方式是从 HTML 树视图中双击它。

![HTML 树视图上下文菜单](./media/elements_html_tree_context.png)

> [!NOTE]
> 编辑 HTML 树不会影响基础源标记。 刷新页面将还原更改，并仅呈现由页面源确定的布局。 如果希望整个 **页面** 打开上下文菜单 (，可以右键单击所需的元素 () 或全局元素，将修改后的 HTML 复制到剪贴板 `html` 中。  (**剪切****和粘贴**选项也可用) 。

在 ["样式](./elements/styles.md) "窗格中，还可以添加/删除/编辑 CSS 伪状态和伪元素。

## 工具窗格

选择感兴趣的页面元素后，可以使用工具窗格进一步检查其不同的样式和辅助功能属性、查看其事件侦听器和设置 DOM 破坏断点。

!["元素"面板上的"工具"窗格](./media/elements_toolpanes.png)

1. [**样式**](./elements/styles.md)：当前应用的样式由样式表组织

2. [**计算：**](./elements/computed.md)当前应用的样式由 CSS 属性组织

3. [**事件 ：**](./elements/events.md)在当前元素和上级元素上注册的事件侦听器

4. [**DOM 断点**](./elements/dom-breakpoints.md)：DOM 分解断点 

5. [**字体**](./elements/fonts.md)：当前为选定元素应用的字体

6. [**辅助功能**](./elements/accessibility.md)：辅助功能属性

7. [**更改**](./elements/changes.md)：诊断会话期间对 CSS 所做的更改  

## 快捷方式

| 操作               | 快捷方式               |
|:---------------------|:-----------------------|
| 元素面板       | `Ctrl` + `1`           |
| 元素突出显示 | `Ctrl` + `Shift` + `L` |
| Select 元素       | `Ctrl` + `B`           |
| 颜色选取器         | `Ctrl` + `K`           |
| 辅助功能树   | `Ctrl` + `Shift` + `A` |
