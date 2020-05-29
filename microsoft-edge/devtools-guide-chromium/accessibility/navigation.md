---
title: 导航 Microsoft Edge DevTools 与辅助技术
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 03/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、devtools
ms.openlocfilehash: 5de27e46d20957a1be79f72cf36074291566e6e5
ms.sourcegitcommit: 6860234c25a8be863b7f29a54838e78e120dbb62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "10562911"
---
<!-- Copyright Rob Dodson 

   Licensed under the Apache License, Version 2.0 (the "License");
   you may not use this file except in compliance with the License.
   You may obtain a copy of the License at

       https://www.apache.org/licenses/LICENSE-2.0

   Unless required by applicable law or agreed to in writing, software
   distributed under the License is distributed on an "AS IS" BASIS,
   WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
   See the License for the specific language governing permissions and
   limitations under the License.  -->





# 导航 Microsoft Edge DevTools 与辅助技术   



本指南旨在帮助主要依靠辅助技术（如屏幕阅读器）访问和使用 Microsoft Edge DevTools 的用户。  Microsoft Edge DevTools 是内置于 Microsoft Edge 浏览器中的一套 web 开发人员工具。  <!--See [Accessibility Reference][DevtoolsAccessibilityReference] if you are looking for DevTools features related to improving the accessibility of a web page.  -->

<!--todo: add edge devtools index section when available  -->  
<!--todo: add reference (Accessibility Reference) section when available  -->  

DevTools 的辅助功能是一个正在进行的工作。  某些面板和选项卡比其他面板和选项卡更适用于辅助技术。  本指南将指导你完成最易于访问和突出显示你可能遇到的特定问题的面板。  

## 概述   

在开始之前，它有助于获得有关 DevTools UI 的结构的心理模型。  DevTools 分为一系列的面板，这些面板组织成一个[ARIA `tablist` ][W3CWaiAriaTablist]。  

例如：  

*   可通过 "**元素**" 面板查看和更改 DOM 节点或 [CSS] [DevtoolsCssIndex]。  
*   [**控制台**面板] [DevtoolsConsoleIndex] 允许您读取 JavaScript 日志和实时编辑对象。  

<!--todo:  add dom nodes (dom nodes) section when available  -->  

在每个面板的内容区域内，有许多不同的工具，这些工具通常称为文档中的选项卡或窗格。  
例如，"**元素**" 面板包含用于检查事件侦听器、辅助功能树以及更多的其他选项卡。  选项卡和窗格之间的区别稍有不同。  你可能看到一个术语或另一个术语的唯一原因是与官方 DevTools 文档的其余部分保持一致。  

## 键盘快捷方式   

[DevTools 键盘快捷方式参考] [DevtoolsShortcuts] 是一个非常有用的 cheatsheet。  在浏览不同的面板时，请务必将其加入书签并重新引用它。  

## 打开 DevTools   

若要开始，请阅读 [打开 Microsoft Edge DevTools] [DevtoolsOpen]。  有多种方法可以打开 DevTools，方法是通过键盘快捷方式或菜单项打开。  

## 在面板之间导航   

### 通过键盘导航   

*   在 DevTools 打开的情况下，按 `Control` + `]` \ （Windows \）或 `Command` + `]` \ （macOS \）重点关注下一个面板。  
*   按 `Control` + `[` \ （Windows \）或 `Command` + `[` \ （macOS \）将焦点置于上一个面板。  
*   也可以使用将 `Shift` + `Tab` 焦点移动到面板的[ARIA `tablist` ][W3CWaiAriaTablist]中并使用箭头键更改面板，尽管使用前面提到的快捷方式可能会更快。  

#### 已知问题   

*   某些面板（如 "**控制台**" 和 "**性能**" 面板）可能会在激活后将焦点移动到其内容区域。  这可能导致很难通过箭头键进行导航。  
*   将宣布所选面板的名称，但仅在它已阅读面板中的焦点内容后才会。  这可能会使错过的事情变得非常容易。  

### 通过命令菜单导航   

若要聚焦特定面板，请使用 [**命令菜单**] [DevtoolsCommandMenuIndex]：  

1.  在 DevTools 打开的情况下，按 `Control` + `Shift` + `P` \ （Windows \）或 `Command` + `Shift` + `P` \ （macOS \）打开 "**命令" 菜单**。  
    **命令菜单**是模糊搜索记忆式键入 combobox。  
1.  键入要打开的面板的名称，然后使用键盘上的 " `Down Arrow` 导航到正确的" 选项。  
1.  按 `Enter` 运行命令。  

例如，若要打开 "**元素**" 面板，请执行以下操作：  

1.  打开 "**命令" 菜单**。  
1.  `E`然后键入 `L` 。  **"面板 > 显示元素**" 选项处于选中状态。  
1.  按 `Enter` 运行打开面板的命令。  

通过这种方式打开面板，可将焦点定向到面板的内容。  在 "**元素**" 面板的情况下，焦点移到**DOM 树**中。  

## 元素面板   

### 检查页面上的元素   

1.  使用屏幕阅读器中的光标导航到要检查的元素。  
1.  模拟鼠标右键单击元素以打开上下文菜单。  
1.  选择 "**检查**" 选项。  这将打开 "**元素**" 面板，焦点在**DOM 树**中的元素。  

<!--todo:  add dom nodes (elements pane) section when available  -->  

**DOM 树**布局为[ARIA `tree` ][W3CWaiAriaTree]。  <!--See [Navigate the **DOM Tree** with a keyboard][DevtoolsDomIndexNavigateDomTreeKeyboard] for an example.  -->  

<!--todo: add dom index navigation tree section then available  -->

### 复制 DOM 树中元素的代码   

1.  将焦点置于**DOM 树**中的某个节点上，打开右键单击上下文菜单。  
1.  展开 "**复制**" 选项。  
1.  选择 "**复制 outerHTML**"。  

#### 已知问题   

*   **复制 outerHTML**通常不选择当前节点，而是选择父节点。  但是，该元素的内容应仍在已复制的 outerHTML 中。  

### 在 DOM 树中修改元素的属性   

*   将焦点放在**DOM 树**中的节点上时，按 `Enter` 以使其可编辑。  
*   按下 `Tab` 以在属性值之间移动。  当你听到 "space" 时，你位于空的文本输入中，并且能够键入新的属性值。  
*   按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）接受更改并收听元素的所有内容。  

#### 已知问题   

*   键入文本输入时，您不会收到任何反馈。  如果你进行了键入错误，并使用箭头键浏览你的输入，你也不会收到任何反馈。  检查工作的最简单方法是接受更改，然后侦听要宣布的整个元素。  

### 在 DOM 树中编辑元素的 HTML   

*   将焦点放在**DOM 树**中的节点上时，按 `Enter` 以使其可编辑。  
*   按下 `Tab` 以在属性值之间移动。  当你听到元素的名称（例如，"h2"）时，你位于文本输入内，并且可能会更改元素的类型。  
*   按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）接受更改。  

例如，键入 `h3` 并按 `Control` + `Enter` \ （Windows \）或 `Command` + `Enter` \ （macOS \）将元素的开始和结束标记更改为 `h3` 。  

## "元素" 面板选项卡   

"**元素**" 面板包含用于检查内容的其他选项卡，例如应用于某个元素的 CSS 或 "辅助功能" 树中的相关位置。  

*   将焦点置于**DOM 树**中的某个节点上时，按， `Tab` 直到听到 "**样式**" 窗格处于选中状态。  
*   使用 `Right Arrow` 浏览其他可用的选项卡。  

**DOM 树**将具有属性的元素 `href` 转换为可设定焦点的链接，因此你可能需要按多次 `Tab` 才能到达 "**样式**" 窗格。  

### 已知问题   

" **DOM 断点**" 和 "**属性**" 选项卡不能通过键盘访问。  

### "样式" 窗格   

在 "**样式**" 窗格中，查找用于筛选样式、切换元素状态 \ （如 [`:active`][MDNActive] 和 [`:focus`][MDNFocus] \）、切换类以及添加新类的控件。  还有一个功能强大的样式检查工具，可用于浏览和修改当前应用于**DOM 树**中焦点的元素的样式。  

了解 "**样式**" 窗格的关键概念是它仅显示**DOM 树**中当前选定的节点的样式。  例如，假设你已检查完节点的样式 `<header>` ，现在想要查看节点的样式 `<footer>` 。  若要执行此操作，首先需要选择 `<footer>` **DOM 树**中的节点。  你可以更快地使用 "[检查](#inspect-an-element-on-the-page)工作流" 检查节点的常规邻近节点 `footer` \ （如页脚中的链接 \）的节点 \ （如页脚中的链接 \）， **DOM Tree**然后使用键盘导航到你感兴趣的确切节点。  

#### 导航 "样式" 窗格   

因为所有样式工具都以一种方式进行连接，而另一种方式是返回到 "**样式**" 窗格，所以先掌握此工具才有意义。  

*   焦点位于 "**样式**" 窗格上时，按 `Tab` 以将焦点移动到其中并浏览内容。  
*   按下 `Tab` 第一个样式变为活动状态。  如果您使用的是屏幕阅读器，则第一种样式将宣布为 "element. style {} "。  
*   按下 `Down Arrow` 以按升序顺序导航样式列表。  屏幕阅读器将从 CSS 文件的名称、出现样式的行号以及样式的名称开始宣布每个样式。  例如： "main .css： 233 card__img {} "  
*   按 `Enter` 以更详细地检查样式。  焦点从样式名称的可编辑版本开始。  
*   按下 `Tab` 以在每个 CSS 属性的可编辑版本及其相应值之间移动。  每个样式块的结尾是一个空白的可编辑文本字段，可用于添加其他 CSS 属性。  
*   你可以继续按下 `Tab` 以在样式列表中移动，或者按 `Escape` 退出此模式并返回到通过箭头键导航。  

请务必阅读 [样式窗格键盘参考] [DevtoolsShortcutsStylesPaneKeyboard] 以了解其他快捷方式。  

##### 已知问题   

*   如果使用 "**筛选器**可编辑文本" 字段，则无法再导航样式列表。  

#### 切换元素状态   

切换元素的状态，例如 `:active` 或 `:focus` ：  

1.  导航到 "**样式**" 窗格，然后按， `Tab` 直到 "**切换元素状态**" 按钮获得焦点。  
1.  按 `Enter` 以展开元素状态的集合。  元素状态显示为一组复选框。  
1.  按下 `Tab` 第一个状态， `:active` 即 "有焦点"。  
1.  按 `Space` 以启用它。  如果 DOM 树中的当前选定元素具有 `:active` 样式，则现在将其应用。  
1.  继续按 `Tab` 以浏览所有可用状态。  

#### 添加现有类   

"**切换元素状态**" 按钮旁边是 "**元素类**" 按钮。  按 "then" 将焦点移动到该文件 `Tab` `Enter` 。  焦点移到标记为 "**添加新类**" 的编辑文本字段中。  

**元素类**按钮主要用于将现有类添加到元素。  例如，如果你的样式表包含名为的帮助程序类， `.clearfix` 你可以 `.` 在 "编辑文本" 字段内按下以查看建议的类列表，并使用 `Down Arrow` 查找 `.clearfix` 建议。  或者键入类名称，然后按 `Enter` 以应用它。  

#### 添加新样式规则   

"**元素类**" 按钮旁边是 "**新建样式规则**" 按钮。  通过按键将焦点移动到该 `Tab` 按钮 `Enter` 。  焦点移到 "样式" 检查器内的可编辑文本字段中。  字段的初始文本内容是**DOM 树**中所选元素的标记名称。  
你可以在此字段中键入所需的任何类名称，然后按 `Tab` 向其分配 CSS 属性。  

### 计算选项卡   

将焦点放在 "**计算**" 选项卡上，按下 `Tab` 以将焦点移动到其中并浏览内容。  在 "**计算**" 选项卡中有一些控件，用于探索哪些 CSS 属性实际应用于某个元素的具体程度。  

<!--todo: add computed tab section when available  -->  

#### 浏览所有计算样式   

按 `Tab` ，直到到达计算样式的集合。  这些将作为[ARIA `tree` ][W3CWaiAriaTree]呈现。  展开 listbox 将显示哪些 CSS 选择器应用了计算样式。  这些选择程序按具体程度进行组织。  屏幕阅读器宣布计算值、当前匹配的 CSS 选择器、包含选择器的样式表的文件名以及选择器的行号。  

#### 已知问题   

*   如果使用 "**筛选**文本" 字段，则无法再检查样式。  

### 事件侦听器选项卡   

在 "**元素**" 面板中，你可以使用 "**事件侦听器**" 选项卡检查应用到元素的事件侦听器。 将焦点置于 "**样式**" 窗格上，按 `Right Arrow` 以导航到 "**事件侦听器**" 选项卡。  

#### 浏览事件侦听器   

事件侦听器以[ARIA `tree` ][W3CWaiAriaTree]的形式呈现。  你可以使用箭头键进行导航。  屏幕阅读器将宣布事件侦听器附加到的 DOM 对象的名称，以及定义事件侦听器和行号的文件名。  

### 辅助功能窗格   

焦点位于 "**辅助功能**" 窗格上时，按 `Tab` 以将焦点移动到其中并浏览内容。  在 "**辅助功能**" 窗格中，有用于浏览辅助功能树、应用于元素的 ARIA 属性和计算的辅助功能属性的控件。  

<!--todo: add reference (Accessibility pane) section when available  -->  

#### 辅助功能树   

**辅助功能树**显示为一个[ `tree` ARIA][W3CWaiAriaTree] ，其中每个元素都 `treeitem` 对应于 DOM 中的一个元素。  树宣布所选节点的已计算角色。  类中的泛型元素（如 `div` 和 `span` ）在树中被宣布为 "GenericContainer"。  使用箭头键遍历树并浏览父子关系。  

#### 已知问题   

*   **辅助功能**窗格使用的[ARIA `tree` ][W3CWaiAriaTree]类型可能无法在 Microsoft Edge 中针对 MacOS 屏幕阅读器（如 VoiceOver）正确公开。  订阅[Chromium 问题 #868480][ChromiumIssues868480]将收到有关此问题的进度。  
*   每个**ARIA 属性**和**计算属性**部分均标记为[ `tree` ARIA ][W3CWaiAriaTree]，但每个都不是焦点管理，并且不是键盘可操作。  

## 审核面板   

"**审核**" 面板你应该针对网站运行一系列测试，以检查与性能、辅助功能、SEO 以及许多其他类别相关的常见问题。  

### 配置和运行审核   

1.  首次打开 "**审核**" 面板时，焦点将放置在窗体末尾的 "**运行审核**" 按钮上。  默认情况下，该窗体配置为对模拟的3G 连接上的每个类别使用 "移动仿真" 运行审核。  
1.  `Shift` + `Tab` 在浏览模式下使用或向后导航以更改审核设置。  
1.  准备好运行审核时，请导航回 "**运行审核**" 按钮，然后按 `Enter` 。  
1.  焦点将移动到带有 "**取消**" 按钮的模式窗口，使您可以退出审核。  当审核运行并多次刷新页面时，你可能会听到一系列 earcons。  

#### 已知问题   

*   配置窗体的不同部分当前不与元素一起标记 `fieldset` 。  在浏览模式中导航以确定与每个部分关联的控件可能更容易。  
*   审核完成运行时，没有 earcon 或活动区域公告。  通常需要30秒，之后才能导航到结果。  使用浏览模式可能是达到结果的最简单方式。  

### 导航审核报告   

审核报告已组织为与每个审核类别对应的分区。  将打开报表，其中包含每个类别的分数列表。  这些分数也是可以用于跳转到相关部分的链接。  在每个部分中都是可扩展 `details` 元素，其中包含与已通过或失败的审核相关的信息。  默认情况下，仅显示失败的审核。  每个部分都以 `details` 包含所有已传递审核的最终元素结尾。  

若要运行新审核，请使用 `Shift` + `Tab` 退出报告并查找 "**执行审核**" 按钮。  

## 反馈   

*   将 DevTools bug 报告或功能请求发送到[Chromium Issue 跟踪][MonorailChromiumIssues]器。  
*   将与此文档相关的任何反馈发送到[GitHub][GithubEdgeDeveloperNewIssue]。  

<!-- image links -->  

<!-- links -->  

<!--[DevtoolsAccessibilityReference]: reference.md "Accessibility Reference"  -->  
<!--[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "The Accessibility pane - Accessibility Reference"  -->  

<!--[MicrosoftEdgeDevtoolsIndex]: ../index.md "Microsoft Edge DevTools"  -->  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令"  
[DevtoolsConsoleIndex]: ../console/index.md "控制台概述"  
[DevtoolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get Started With Viewing And Changing The DOM"  -->  
<!--[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md#navigate-the-dom-tree-with-a-keyboard "Navigate the DOM Tree with a keyboard - Get Started With Viewing And Changing The DOM"  -->
[DevtoolsOpen]: ../open.md "打开 Microsoft Edge DevTools"  
[DevtoolsShortcuts]: ../shortcuts.md "Microsoft Edge DevTools 键盘快捷方式"  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # 样式-窗格-键盘快捷方式 "样式窗格键盘快捷方式-Microsoft Edge DevTools 键盘快捷方式"  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "问题 868480-将 ARIA 树作为 Mac 辅助功能中的表公开"  
[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新问题-MicrosoftDocs/edge-开发人员 |GitHub"  
[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active "：活动 |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus "：焦点 |MDN"  
[MonorailChromiumIssues]: https://crbug.com "问题-chromium-Monorail"  
[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist （角色）-易于访问的富互联网应用程序（WAI-ARIA-ARIA） 1.1 |W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "树（角色）-易于访问的富互联网应用程序（WAI-ARIA） 1.1 |W3C"  

> [!NOTE]
> 此页面的某些部分是基于[由 Google][GoogleSitePolicies]创建和共享的工作的修改，并根据 "[创造性 Commons 归属4.0 国际许可证][CCA4IL]" 中所述的条款使用。  
> 原始页面位于[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation)，并且由 " [Dodson][RobDodson] " （参与者、Google WebFundamentals \）创作。  

[![创造性 Commons 许可证][CCby4Image]][CCA4IL]  
此作品通过 [Creative Commons Attribution 4.0 国际许可证][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
