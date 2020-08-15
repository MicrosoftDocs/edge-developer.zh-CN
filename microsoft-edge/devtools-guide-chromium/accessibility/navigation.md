---
title: 导航 Microsoft Edge DevTools 与辅助技术
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 08/14/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 4bd910fabaab02a632bdc51ade29c5ad6502432a
ms.sourcegitcommit: 054ad92f0b8f9a15da1e3aed32e8f4379b10860f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/15/2020
ms.locfileid: "10931194"
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

以下文章旨在帮助主要依靠辅助技术（如屏幕阅读器）访问和使用 [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain]的用户。  [Microsoft Edge DevTools][MicrosoftEdgeDevtoolsMain] 是内置于 Microsoft edge 浏览器中的一套 web 开发人员工具。  如果您要查找与改善网页辅助功能相关的 DevTools 功能，请参阅 [辅助功能参考][DevtoolsAccessibilityReference]。  

DevTools 的辅助功能是一个正在进行的工作。  某些面板和选项卡比其他面板和选项卡更适用于辅助技术。  本指南将指导你完成最易于访问和突出显示你可能遇到的特定问题的面板。  

## 概述  

在开始之前，它有助于获得有关 DevTools UI 的结构的心理模型。  DevTools 分为一系列的面板，这些面板分为一个 [ARIA tablist][W3CWaiAriaTablist]。  

例如：  

*   通过 " **元素** " 面板，你可以 [查看和更改 DOM 节点] [DevtoolsDomIndexNavigateDomTreeKeyboard] 或 [CSS][DevtoolsCssIndex]。  
*   [控制台面板][DevtoolsConsoleIndex]允许您读取 JavaScript 日志和实时编辑对象。  

在每个面板的内容区域内，有许多不同的工具，这些工具通常称为文档中的选项卡或窗格。  
例如，" **元素** " 面板包含用于检查事件侦听器、辅助功能树以及更多的其他选项卡。  选项卡和窗格之间的区别稍有不同。  你可能看到一个术语或另一个术语的唯一原因是与官方 DevTools 文档的其余部分保持一致。  

## 键盘快捷方式  

[DevTools 键盘快捷方式参考] [DevtoolsShortcuts] 是一个非常有用的 cheatsheet。  在浏览不同的面板时，请务必将其加入书签并重新引用它。  

## 打开开发工具  

若要开始使用，请参阅 [打开 Microsoft Edge DevTools] [DevtoolsOpen]。  有多种方法可以打开 DevTools，方法是通过键盘快捷方式或菜单项打开。  

## 在面板之间导航  

### 通过键盘导航  

*   在 DevTools 打开的情况下，选择 `Control` + `]` \ (Windows \ ) 或 `Command` + `]` \ (macOS \ ) 以重点关注下一个面板。  
*   选择 `Control` + `[` \ (Windows \ ) 或 `Command` + `[` \ (macOS \ ) 以重点介绍上一个面板。  
*   也可以使用将 `Shift` + `Tab` 焦点移动到面板的[ARIA tablist][W3CWaiAriaTablist]中并使用箭头键更改面板，但使用前面提到的快捷方式可能会更快。  

**已知问题**  

*   在每个面板激活后，某些面板（如 " **控制台** " 和 " **性能** " 面板）可能会将焦点移到 "面板内容" 区域。  这可能导致很难通过箭头键进行导航。  
*   将宣布所选面板的名称，但仅在它已阅读面板中的焦点内容后才会。  这可能会使错过的事情变得非常容易。  

### 通过命令菜单导航  

若要聚焦特定面板，请使用 " [命令" 菜单][DevtoolsCommandMenuIndex]：  

1.  在 DevTools 打开的情况下，选择 `Control` + `Shift` + `P` \ (Windows \ ) 或 `Command` + `Shift` + `P` \ (macOS \ ) 打开 "**命令" 菜单**。  
    **命令菜单**是模糊搜索记忆式键入 combobox。  
1.  键入要打开的面板的名称，然后使用键盘上的 " `Down Arrow` 导航到正确的" 选项。  
1.  选择 `Enter` 以运行命令。  

完成以下操作以打开 " **元素** " 面板。  

1.  打开 " **命令" 菜单**。  
1.  `E`然后键入 `L` 。  **"面板 > 显示元素**" 选项处于选中状态。  
1.  选择 `Enter` 以运行打开面板的命令。  

以这种方式打开面板，将焦点定向到面板的内容。  在 " **元素** " 面板的情况下，焦点移到 **DOM 树**中。  

## 元素面板  

### 检查页面上的元素  

1.  使用屏幕阅读器中的光标导航到要检查的元素。  
1.  在元素上使用鼠标进行右键单击以打开上下文菜单。  
1.  选择 " **检查** " 选项。  此 [打开元素面板并聚焦 DOM 树中的元素] [DevtoolsDomIndexViewDomNodes]。  

**DOM 树**布局为[ARIA 树][W3CWaiAriaTree]。  有关示例，请参阅 [使用键盘导航 **DOM 树** ] [DevtoolsDomIndexNavigateDomTreeKeyboard]。  

### 复制 DOM 树中元素的代码  

1.  当焦点位于 **DOM 树**中的某个节点上时，将鼠标悬停在节点上并打开上下文菜单 \ (右键单击 \ ) 。  
1.  展开 " **复制** " 选项。  
1.  选择 " **复制 outerHTML**"。  

**已知问题**  

*   **复制 outerHTML** 通常不选择当前节点，而是选择父节点。  但是，该元素的内容应仍在已复制的 outerHTML 中。  

### 在 DOM 树中修改元素的属性  

*   将焦点置于 **DOM 树**中的某个节点上，然后选择 `Enter` 以使其可编辑。  
*   选择 `Tab` 以在属性值之间移动。  当你听到 "space" 时，你位于空的文本输入中，并且能够键入新的属性值。  
*   选择 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) ，接受更改并收听该元素的所有内容。  

**已知问题**  

*   键入文本输入时，您不会收到任何反馈。  如果你进行了键入错误，并使用箭头键浏览你的输入，你也不会收到任何反馈。  检查工作的最简单方法是接受更改，然后侦听要宣布的整个元素。  

### 在 DOM 树中编辑元素的 HTML  

*   将焦点置于 **DOM 树**中的某个节点上，然后选择 `Enter` 以使其可编辑。  
*   选择 `Tab` 以在属性值之间移动。  例如，当听到元素的名称（例如，在 `h2` 文本输入中）时，可能会更改元素的类型。  
*   选择 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 以接受更改。  

例如，当你键入 `h3` 并选择 `Control` + `Enter` \ (Windows \ ) 或 `Command` + `Enter` \ (macOS \ ) 时，元素的开始和结束标记会 `h3` 发生更改。  

## "元素" 面板选项卡  

" **元素** " 面板包含用于检查内容的其他选项卡，例如应用于某个元素的 CSS 或 "辅助功能" 树中的相关位置。  

*   将焦点置于 **DOM 树**中的某个节点上，选择， `Tab` 直到听到 " **样式** " 窗格处于选中状态。  
*   使用 `Right Arrow` 浏览其他可用的选项卡。  

**DOM 树**将具有属性的元素 `href` 转换为可设定焦点的链接，因此你可能需要选择多次 `Tab` 才能到达 "**样式**" 窗格。  

**已知问题**  

" **DOM 断点** " 和 " **属性** " 选项卡不能通过键盘访问。  

### "样式" 窗格  

在 " **样式** " 窗格中，查找用于筛选样式的控件，切换元素状态 \ (例如 [： "活动][MDNActive] " 和 [： "焦点][MDNFocus]\" ) 、切换类以及添加新类。  还有一个功能强大的样式检查工具，可用于浏览和修改当前应用于 **DOM 树**中焦点的元素的样式。  

了解 " **样式** " 窗格的关键概念是它仅显示 **DOM 树**中当前选定的节点的样式。  例如，假设你已检查完节点的样式 `<header>` ，现在想要查看节点的样式 `<footer>` 。  若要执行此操作，首先需要选择 `<footer>` **DOM 树**中的节点。  你可能会发现使用 " [检查](#inspect-an-element-on-the-page) 工作流" 来检查节点的常规邻近 `footer` 节点 \ (（如页脚中的链接 \ ) ，它侧重于 **DOM 树**），然后使用键盘导航到你感兴趣的确切节点。  

#### 导航 "样式" 窗格  

因为所有样式工具都以一种方式进行连接，而另一种方式是返回到 " **样式** " 窗格，所以在此工具中首先成为专家是有意义的。  

*   将焦点置于 " **样式** " 窗格上，选择 `Tab` 以将焦点移动到其中并浏览内容。  
*   选择 `Tab` ，直到第一个样式变为活动状态。  如果您使用的是屏幕阅读器，则第一个样式将宣布为 `element.style {}` 。  
*   选择 `Down Arrow` 以按升序顺序导航样式列表。  屏幕阅读器将从 CSS 文件的名称、出现样式的行号以及样式的名称开始宣布每个样式。  例如，`main.css:233 .card__img {}`。  
*   选择 `Enter` 以更详细地检查样式。  焦点从样式名称的可编辑版本开始。  
*   选择 `Tab` 以在每个 CSS 属性的可编辑版本和相应值之间移动。  每个样式块的结尾是一个空白的可编辑文本字段，可用于添加其他 CSS 属性。  
*   你可以继续选择在 `Tab` 样式列表中移动，或选择 `Escape` 退出模式并返回到通过箭头键导航。  

有关其他快捷方式，请参阅 [样式窗格键盘参考] [DevtoolsShortcutsStylesPaneKeyboard]。  

**已知问题**  

*   如果使用 " **筛选器** 可编辑文本" 字段，则无法再导航样式列表。  

#### 切换元素状态  

切换元素的状态，例如 `:active` 或 `:focus` ：  

1.  导航到 " **样式** " 窗格，然后选择 `Tab` " **切换元素状态** " 按钮获得焦点。  
1.  选择 `Enter` 以展开元素状态的集合。  元素状态显示为一组复选框。  
1.  选择 " `Tab` 直到第一个状态" `:active` ，"有焦点"。  
1.  选择 `Space` 以启用它。  如果 DOM 树中的当前选定元素具有 `:active` 样式，则现在将其应用。  
1.  "保持" `Tab` 以浏览所有可用状态。  

#### 添加现有类  

" **切换元素状态** " 按钮旁边是 " **元素类** " 按钮。  若要将焦点移动到该文件，请选择 `Tab` 并选择 `Enter` 。  焦点移到标记为 " **添加新类**" 的编辑文本字段中。  

**元素类**按钮主要用于将现有类添加到元素。  例如，如果你的样式表包含名为的帮助程序类，则 `.clearfix` 可以在 `.` "编辑文本" 字段中选择以查看类的建议列表，并使用 `Down Arrow` 查找 `.clearfix` 建议。  或者键入类名，然后选择 `Enter` 应用。  

#### 添加新样式规则  

" **元素类** " 按钮旁边是 " **新建样式规则** " 按钮。  若要将焦点移动到该文件，请选择 `Tab` 并选择 `Enter` 。  焦点移到 "样式" 检查器内的可编辑文本字段中。  字段的初始文本内容是 **DOM 树**中所选元素的标记名称。  
你可以在此字段中键入所需的任何类名称，然后选择 `Tab` 将 CSS 属性分配给该字段。  

### 计算选项卡  

将焦点置于 " **计算** " 选项卡上，选择 `Tab` 以将焦点移动到其中并浏览内容。  在 " **计算** " 选项卡中有一些控件，用于探索哪些 CSS 属性实际应用于某个元素的具体程度。  

<!--todo: add computed tab section when available  -->  

#### 浏览所有计算样式  

选择 `Tab` ，直到到达计算样式的集合。  它们显示为一个 [ARIA 树][W3CWaiAriaTree]。  展开 listbox 将显示哪些 CSS 选择器应用了计算样式。  这些选择程序按具体程度进行组织。  屏幕阅读器宣布计算值、当前匹配的 CSS 选择器、包含选择器的样式表的文件名以及选择器的行号。  

**已知问题**  

*   如果使用 " **筛选** 文本" 字段，则无法再检查样式。  

### 事件侦听器选项卡  

在 " **元素** " 面板中，你可以使用 " **事件侦听器** " 选项卡检查应用到元素的事件侦听器。 将焦点置于 " **样式** " 窗格上，选择 `Right Arrow` 导航到 " **事件侦听器** " 选项卡。  

#### 浏览事件侦听器  

事件侦听器以 [ARIA 树][W3CWaiAriaTree]的形式呈现。  你可以使用箭头键进行导航。  屏幕阅读器将宣布事件侦听器附加到的 DOM 对象的名称，以及定义事件侦听器和行号的文件名。  

### 辅助功能窗格  

焦点位于 " **辅助功能** " 窗格上，选择 `Tab` 以将焦点移动到其中并浏览内容。  在 " [辅助功能" 窗格][DevtoolsAccessibilityReference] 中，有用于浏览辅助功能树、应用于元素的 ARIA 属性和计算的辅助功能属性的控件。  

#### 辅助功能树  

**辅助功能树**显示为一个[ARIA 树][W3CWaiAriaTree]，其中每个树都 `treeitem` 对应于 DOM 中的一个元素。  树宣布所选节点的已计算角色。  类中的泛型元素（如 `div` 和 `span` ）在树中被宣布为 "GenericContainer"。  使用箭头键遍历树并浏览父子关系。  

**已知问题**  

*   **辅助功能**窗格使用的[ARIA 树][W3CWaiAriaTree]的类型可能无法在 Microsoft Edge 中正确地向 macOS 屏幕阅读器（如 VoiceOver）公开。  订阅 [Chromium 问题 #868480][ChromiumIssues868480] 将收到有关此问题的进度。  
*   每个 **ARIA 属性** 和 **计算属性** 部分均标记为一个 [ARIA 树][W3CWaiAriaTree]，但每个都不是焦点管理，并且不是键盘可操作。  

## 审核面板  

" **审核** " 面板你应该针对网站运行一系列测试，以检查与性能、辅助功能、SEO 以及许多其他类别相关的常见问题。  

### 配置和运行审核  

1.  首次打开 " **审核** " 面板时，焦点将放置在窗体末尾的 " **运行审核** " 按钮上。  默认情况下，该窗体配置为对模拟的3G 连接上的每个类别使用 "移动仿真" 运行审核。  
1.  `Shift` + `Tab` 在浏览模式下使用或向后导航以更改审核设置。  
1.  准备好运行审核时，请导航回 " **运行审核** " 按钮并选择 `Enter` 。  
1.  焦点将移动到带有 " **取消** " 按钮的模式窗口，使您可以退出审核。  当审核运行并多次刷新页面时，你可能会听到一系列 earcons。  

**已知问题**  

*   配置窗体的不同部分当前不与元素一起标记 `fieldset` 。  在浏览模式中导航以确定与每个部分关联的控件可能更容易。  
*   审核完成运行时，没有 earcon 或活动区域公告。  通常需要30秒，之后才能导航到结果。  使用浏览模式可能是达到结果的最简单方式。  

### 导航审核报告  

审核报告已组织为与每个审核类别对应的分区。  将打开报表，其中包含每个类别的分数列表。  这些分数也是可以用于跳转到相关部分的链接。  在每个部分中都是可扩展 `details` 元素，其中包含与已通过或失败的审核相关的信息。  默认情况下，仅显示失败的审核。  每个部分都以 `details` 包含所有已传递审核的最终元素结尾。  

若要运行新审核，请使用 `Shift` + `Tab` 退出报告并查找 "**执行审核**" 按钮。  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "辅助功能参考 |Microsoft 文档"  
<!--[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "The Accessibility pane - Accessibility Reference | Microsoft Docs"  -->  

[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium.md "Microsoft Edge (Chromium) 开发工具 |Microsoft 文档"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "通过 Microsoft Edge DevTools 命令菜单运行命令 |Microsoft 文档"  
[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 |Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "开始使用查看和更改 CSS |Microsoft 文档"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md # view-dom-节点 "查看 DOM 节点-开始查看和更改 DOM |Microsoft 文档 "  
[DevtoolsDomIndexNavigateDomTreeKeyboard]: ../dom/index.md # "导航"-dom 树-带键盘 "使用键盘浏览 DOM"-开始查看和更改 DOM |Microsoft 文档 "  
[DevtoolsOpen]: ../open.md "打开 Microsoft Edge DevTools |Microsoft 文档 "  
[DevtoolsShortcuts]: ../shortcuts.md "Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档 "  
[DevtoolsShortcutsStylesPaneKeyboard]: ../shortcuts.md # 样式-窗格-键盘快捷方式 "样式窗格" 键盘快捷方式-Microsoft Edge DevTools 键盘快捷方式 |Microsoft 文档 "  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "问题 868480-将 ARIA 树作为 Mac 辅助功能中的表公开"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新问题-MicrosoftDocs/edge-开发人员 |GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active "：活动 |MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus "：焦点 |MDN"  

[MonorailChromiumIssues]: https://crbug.com "问题-chromium-Monorail"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "tablist (角色) -易于访问的富 Internet 应用 (WAI-ARIA-ARIA) 1.1 |W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "树 (角色) -易于访问的富 Internet 应用程序 (WAI-ARIA) 1.1 |W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> 原始页面在[此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation)找到，并且由 "Dodson" （ ([Rob Dodson][RobDodson] ）投稿人、Google WebFundamentals \ ) 创作。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
