---
description: 有关使用辅助技术（如屏幕阅读器）导航 Microsoft Edge 开发工具的指南。
title: 使用辅助技术导航 Microsoft Edge 开发工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 12/11/2020
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: d72c856e9136291e9255b3784aad7c6cd99f92fc
ms.sourcegitcommit: a35a6b5bbc21b7df61d08cbc6b074b5325ad4fef
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/17/2020
ms.locfileid: "11230808"
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

# 使用辅助技术导航 Microsoft Edge 开发工具  

以下文章旨在帮助主要依赖于辅助技术（如屏幕阅读器）的用户访问和使用 [Microsoft Edge 开发工具][MicrosoftEdgeDevtoolsMain]。  [Microsoft Edge 开发工具][MicrosoftEdgeDevtoolsMain] 是内置于 Microsoft Edge 浏览器的一套 Web 开发人员工具。  如果正在查找与改进网页辅助功能相关的开发工具功能，请导航到[辅助功能参考][DevtoolsAccessibilityReference]。  

开发工具的辅助功能是一项正在进行中的工作。  与其他面板和选项卡相比，某些面板和选项卡与辅助技术的配合工作效果更好。  本指南将引导你浏览最容易访问的面板，并重点介绍你在这一过程中可能遇到的特定问题。  

## 概述  

在开始之前，首先建立关于开发工具 UI 构建方式的思维模型，这一点对于下一步学习将很有帮助。  开发工具划分为一系列面板，这些面板组织为一个 [ARIA 选项卡列表][W3CWaiAriaTablist]。  

例如：  

*   “**元素**”面板允许你 [查看和更改 DOM 节点][DevtoolsDomIndexNavigateDomTreeKeyboard] 或 [CSS][DevtoolsCssIndex]。  
*   通过“[控制台面板][DevtoolsConsoleIndex]”可以读取 JavaScript 日志和实时编辑对象。  

每个面板的内容区域中有许多不同的工具，在文档中通常称为选项卡或窗格。  
例如，“**元素**”面板包含有其他选项卡，用于检查事件侦听器、辅助功能树和其他更多内容。  选项卡和窗格之间的区别在一定程度上是任意的。  可能审阅某一个术语的唯一原因只是为了与官方开发工具文档的其余部分保持一致。  

## 键盘快捷方式  

[DevTools 键盘快捷方式参考][DevtoolsShortcuts] 是一个有用的速查表。  请确保将其添加为书签，以便在浏览不同面板时进行参考。  

## 打开开发工具  

若要开始，请导航到 [打开 Microsoft Edge 开发工具] [DevtoolsOpen]。  开发工具有多种打开方式，可以通过键盘快捷方式，也可通过菜单项将其打开。  

## 在面板之间导航  

### 使用键盘导航  

*   开发工具打开后，选择 `Control`+`]` \(Windows, Linux\) 或 `Command`+`]` \(macOS\) 以聚焦下一个面板。  
*   选择 `Control`+`[` \(Windows, Linux\) 或 `Command`+`[` \(macOS\) 以聚焦上一个面板。  
*   还可使用 `Shift`+`Tab` 将焦点移动到面板的“[ARIA 选项卡列表][W3CWaiAriaTablist]”，并使用箭头键更改面板，不过使用前面提及的快捷方式可能更快。  

**已知问题**  

*   一些面板（例如“**控制台**”和“**性能**”面板）在激活每个面板后，可以立即将焦点移动到面板内容区域。  这可能使得使用箭头键导航更加困难。  
*   将会播报所选面板的名称，但仅在读取面板中的重点内容之后才会播报。  这种方式可能会让用户很容易忽略这一信息。  

### 按命令菜单导航  

若要聚焦于特定面板，请使用“[命令菜单][DevtoolsCommandMenuIndex]”：  

1.  打开开发工具，选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 以打开“**命令菜单**”。  
    “**命令菜单** 是一个模糊搜索自动完成的组合框。  
1.  键入想要打开的面板名称，然后使用键盘上的 `Down Arrow` 导航到正确选项。  
1.  选择 `Enter` 以运行命令。  

完成以下操作以打开“**元素**”面板。  

1.  打开“**命令菜单**”。  
1.  键入 `E` ，然后键入 `L`。  选择“**面板>显示元素**”选项。  
1.  选择 `Enter` 以运行命令打开面板。  

用这种方式打开一个面板会将焦点引导到面板的内容上。  在“**元素**”面板上，焦点将移动到“**DOM 树**”。  

## 元素面板  

### 检查页面上的元素  

1.  在屏幕阅读器中，使用光标导航到要检查的元素。  
1.  使用鼠标模拟右键单击元素以打开上下文菜单。  
1.  选择“**检查**”选项。  此操作将 [打开元素面板并聚焦于 DOM 树中的元素][DevtoolsDomIndexViewDomNodes]。  

“**DOM 树**”已布局为 [ARIA 树][W3CWaiAriaTree]。  例如，导航到 [使用键盘导航“**DOM Tree**”][DevtoolsDomIndexNavigateDomTreeKeyboard]。  

### 复制 DOM 树中元素的代码  

1.  将焦点放在“**DOM 树**”中的节点上，然后将鼠标悬停在节点上，并打开上下文菜单 \（右键单击\）。  
1.  展开“**复制**”选项。  
1.  选择“**复制 outerHTML**”。  

**已知问题**  

*   “**复制 outerHTML**”通常不会选择当前节点，而是选择父节点。  但是，该元素的内容应仍在复制的 outerHTML 中。  

### 修改 DOM 树中元素的属性  

*   将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。  
*   选择 `Tab` 以在属性值之间移动。  听到“空格”声音时，你已位于空白文本输入内，并且能够键入新的属性值。  
*   选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改并收听元素的全部内容。  

**已知问题**  

*   在键入文本输入时，无法获取任何反馈。  如果输入错误并使用箭头键来浏览输入，也将没有任何反馈。  检查工作最简单的方法是接受更改，然后收听要播报的整个元素。  

### 编辑 DOM 树中元素的 HTML  

*   将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。  
*   选择 `Tab` 以在属性值之间移动。  当听到该元素的名称（例如，`h2`）时，你会位于文本输入内，并且可以更改元素的类型。  
*   选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改。  

例如，键入 `h3` 并选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 时，`h3` 元素的开始和结尾标记都会更改。  

## 元素面板选项卡  

“**元素**”面板中包含其他选项卡，用于检查如应用于元素的 CSS 或辅助功能树中相关位置等内容。  

*   将焦点放在“**DOM 树**”中的节点上时，选择 `Tab` 直至听到已选择“**样式**”。  
*   使用 `Right Arrow` 浏览其他可用的选项卡。  

“**DOM 树**”将具有 `href` 属性的元素转换为可聚焦链接，因此可能需要多次选择 `Tab` 以访问“**样式**”窗格。  

**已知问题**  

不能通过键盘访问“**DOM 断点**”和“**属性**”选项卡。  

### 样式窗格  

在“**样式**”窗格查找控件筛选样式、切换元素状态 \（如 [:active][MDNActive] 和 [:focus][MDNFocus]\）、切换类别和添加新类别。   还有一个功能强大的样式检查工具，用于浏览和修改当前应用于“**DOM 树**”中处于焦点的元素的样式。  

了解“**样式**”窗格的关键概念是它只显示“**DOM 树**”窗格中当前选中节点的样式。  例如，假设已完成对 `<header>` 节点样式的检查，并且现在希望查看 `<footer>` 节点的样式。  若要执行该操作，首先需要在“**DOM 树**”中选择 `<footer>` 节点。  如果使用 [检查](#inspect-an-element-on-the-page) 工作流检查位于 `footer` 节点 \（如页脚内的链接）邻近区域中的节点（该节点焦点为“**DOM 树**”），然后使用键盘导航到您感兴趣的确切节点，可能发现这一操作更为快速。  

#### 导航“样式”窗格  

由于所有样式工具都以某种方式连接到“**样式**”窗格中，因此首先掌握此工具的使用具有重要意义。  

*   在焦点位于“**样式**”窗格时 ，选择 `Tab` 以将焦点移到内部并浏览内容。  
*   选择 `Tab` 直到第一个样式处于活动状态。  如果使用屏幕阅读器，则第一个样式将播报为 `element.style {}`。  
*   选择 `Down Arrow` 以按特定性顺序导航样式列表。  屏幕阅读器将读出每个样式，播报以 CSS 文件名开头，再依次报出样式所在的行号以及样式的名称。  例如，`main.css:233 .card__img {}`。  
*   选择 `Enter` 以更详细地检查样式。  焦点从样式名称的可编辑版本开始。  
*   选择 `Tab` 以在每个 CSS 属性的可编辑版本和相应的值之间移动。  每个样式块的结尾处是一个空白的可编辑文本字段，可将其用于添加其他 CSS 属性。  
*   可以继续选择 `Tab` 以在样式列表中移动，或选择 `Escape` 以退出模式并返回到使用箭头键导航。  

有关其他快捷方式，请导航到 [样式窗格键盘参考][DevtoolsShortcutsStylesPaneKeyboard]。  

**已知问题**  

*   如果你使用“**筛选器**”可编辑文本字段，则将不能再导航样式列表。  

#### 切换元素状态  

若要切换元素的状态，如 `:active` 或 `:focus`：  

1.  导航到“**样式**”窗格并选择 `Tab`，直到“**切换元素状态**”按钮获得焦点。  
1.  选择 `Enter` 以展开元素状态的集合。  元素状态将显示为一组复选框。  
1.  选择 `Tab`，直到第一个状态 `:active` 获得焦点。  
1.  选择 `Space` 以将其启用。  如果 DOM 树中当前选定的元素具有 `:active` 样式，则现在应用该样式。  
1.  按住 `Tab` 以浏览所有可用状态。  

#### 添加现有类别  

“**元素类别**”按钮与“**切换元素状态**”按钮相邻。  若要将焦点移动到此按钮上，请选择 `Tab`，然后选择 `Enter`。  焦点将移至一个标记为“**添加新类别**”的编辑文本字段。  

“**元素类别**”按钮主要用于向元素添加现有类别。  例如，如果样式表包含名为 `.clearfix` 的帮助程序类别，可选择编辑文本字段中的 `.` 以显示类别建议列表，并使用 `Down Arrow` 查找 `.clearfix` 建议。  或者自行键入类别名称，然后选择 `Enter` 以应用类别。  

#### 添加新的样式规则  

“**新样式规则**”按钮与“**元素类别**”按钮相邻。  若要将焦点移动到此按钮上，请选择 `Tab`，然后选择 `Enter`。  焦点将移到样式检查器内的可编辑文本字段中。  该字段的初始文本内容是在“**DOM 树**”中所选元素的标记名称。  
可以在此字段中键入希望键入的任何类别名称，然后选择 `Tab` 以向其分配 CSS 属性。  

### 已计算选项卡  

在焦点位于“**已计算**”选项卡上时，选择 `Tab` 以将焦点移到内部并浏览内容。  在“**已计算**”选项卡中，有一些控件用于浏览哪些 CSS 属性实际上是按特定性顺序应用于元素的。  

<!--todo: add computed tab section when available  -->  

#### 浏览所有已计算的样式  

选择 `Tab`，直至到达已计算样式的集合。  这些内容将显示为“[ARIA 树][W3CWaiAriaTree]。  展开列表框会显示哪些 CSS 选择器正在应用已计算样式。  这些选择器按特定性进行整理。  屏幕阅读器将播报已计算的值、当前哪个 CSS 选择器正在匹配、包含该选择器的样式表文件名以及选择器行号。  

**已知问题**  

*   如果使用“**筛选**”文本字段，则不再能够检查样式。  

### 事件侦听器选项卡  

在“**元素**”面板中，可以使用“**事件侦听器**”选项卡检查应用于元素的事件侦听器。 在焦点位于“**样式**”窗格上时，选择 `Right Arrow` 以导航到“**事件侦听器**”选项卡。  

#### 浏览事件侦听器  

事件侦听器将显示为 [ARIA 树][W3CWaiAriaTree]。  可以使用箭头键导航。  屏幕阅读器将播报事件侦听器所附加到的 DOM 对象名称，以及定义事件侦听器的文件名和行号。  

### 辅助功能窗格  

在焦点位于“**辅助功能**”窗格时，选择 `Tab` 以将焦点移到内部并浏览内容。  在“[辅助功能窗格][DevtoolsAccessibilityReference] 上，有用于浏览辅助功能树、应用于元素的 ARIA 属性和已计算辅助功能属性的控件。  

#### 辅助功能树  

**辅助功能树** 显示为 [ARIA 树][W3CWaiAriaTree]，其中每个 `treeitem` 对应 DOM 中的一个元素。  树将播报选定节点的已计算角色。  通用元素（如 `div` 和 `span`）将在树中播报为 “GenericContainer”。  使用箭头键来遍历树并浏览父子级关系。  

**已知问题**  

*   “**辅助功能**” 窗格使用的 [ARIA 树][W3CWaiAriaTree] 类型可能未在 Microsoft Edge for macOS 屏幕阅读器（如 VoiceOver）中正确公开。   订阅 [Chromium 问题 #868480][ChromiumIssues868480] 以获取有关此问题进展的通知。  
*   每个 **ARIA 属性** 和 **已计算属性** 部分都标记为 [ARIA 树][W3CWaiAriaTree]，但当前每个部分都不具有焦点管理且不可通过键盘操作。  

## “审核”面板  

应使用“**审核**”面板针对网站运行一系列测试，以检查与性能、辅助功能、SEO 和其他许多类别相关的常见问题。  

### 配置和运行审核  

1.  首次打开“**审核**”面板时，焦点位于窗体末尾的“**运行审核**”按钮上。  默认情况下，窗体配置为使用模拟 3G 连接上的移动仿真对每个类别运行审核。  
1.  使用`Shift`+`Tab`或导航回到浏览模式以更改审核设置。  
1.  准备好运行审核时，请导航回到“**运行审核**”按钮并选择 `Enter`。  
1.  焦点将移动到使用具有“**取消**”按钮的模式窗口，该按钮允许退出审核。  审核运行并多次刷新页面时，可能会听到一系列有声提示。  

**已知问题**  

*   配置窗体的不同部分当前未标记有 `fieldset` 元素。  在浏览模式下导航它们可能会更方便地了解与每个部分关联的控件。  
*   审核结束运行后，不会发布任何有声提示或实时区域公告。  此过程通常需要大约 30 秒，然后你将能够导航到结果。  使用浏览模式可能是获取结果的最简单方法。  

### 导航审核报告  

审核报告将组织成各个章节，对应每个审核类别。  报告打开时显示每个类别的分数列表。  这些分数也是可用于跳转到相关章节的链接。  每个章节内有可展开的 `details`元素，这些元素包含与审核通过或失败有关的信息。  默认情况下，仅显示失败的审核。  每节以最后一个 `details` 元素结尾，该元素包含所有通过的审核。  

若要运行新的审核，请使用 `Shift`+`Tab` 以退出报告并查找“**执行审核**”按钮。  

## 联系 Microsoft Edge 开发工具团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  

[DevtoolsAccessibilityReference]: ./reference.md "辅助功能参考 | Microsoft 文档"  
[DevtoolsAccessibilityReferencePane]: reference.md#the-accessibility-pane "辅助功能窗格 - 辅助功能参考 | Microsoft 文档"  
[MicrosoftEdgeDevtoolsMain]: ../../devtools-guide-chromium/index.md "Microsoft Edge (Chromium) 开发人员工具 | Microsoft 文档"  
[DevtoolsCommandMenuIndex]: ../command-menu/index.md "使用 Microsoft Edge 开发工具命令菜单运行命令"  
[DevtoolsConsoleIndex]: ../console/index.md "控制台概述 | Microsoft 文档"  
[DevtoolsCssIndex]: ../css/index.md "查看和更改 CSS 入门 | Microsoft 文档"  
<!--[DevtoolsCssReferenceViewAppliedElement]: ../css/reference.md#view-only-the-css-that-is-actually-applied-to-an-element "CSS Reference - View only the CSS that is actually applied to an element | Microsoft Docs"  -->  
<!--[DevtoolsDomIndex]: ../dom/index.md "Get started with viewing and changing the DOM | Microsoft Docs"  -->  
[DevtoolsDomIndexViewDomNodes]: ../dom/index.md#view-dom-nodes“查看 DOM 节点 - 查看和更改 DOM 入门 | Microsoft 文档”  
[DevtoolsDomindexexNaviDomGateKeyboard]： .。/dom/index.md#navigate-dom-tree-with-dom-tree-with-a-keyboard“使用键盘导航 DOM 树 - 查看和更改 DOM 入门 | Microsoft 文档”  
[DevtoolsOpen]：./open/index.md“打开 Microsoft Edge 开发工具 | Microsoft 文档”  
[DevtoolsShortcuts]：.。/shortcuts/index.md“Microsoft Edge 开发工具键盘快捷方式 | Microsoft 文档”  
[DevtoolsShortcutsStylesPaneKeyboard]：./shortcuts/index.md#styles-pane-keyboard-shortcuts“样式窗格键盘快捷方式 - Microsoft Edge 开发工具键盘快捷方式 | Microsoft 文档”  

[ChromiumIssues868480]: https://bugs.chromium.org/p/chromium/issues/detail?id=868480 "问题 868480 - 在 Mac 辅助功能中以表的形式公开 ARIA 树"  

[GithubEdgeDeveloperNewIssue]: https://github.com/MicrosoftDocs/edge-developer/issues/new?title=%5BDevTools%20Docs%20Feedback%5D "新问题 - MicrosoftDocs/edge-developer - GitHub"  

[MDNActive]: https://developer.mozilla.org/docs/Web/CSS/:active ":active | MDN"  
[MDNFocus]: https://developer.mozilla.org/docs/Web/CSS/:focus ":focus | MDN"  

[MonorailChromiumIssues]: https://crbug.com "问题 - chromium - Monorail"  

[W3CWaiAriaTablist]: https://www.w3.org/TR/wai-aria-1.1/#tablist "选项卡列表（角色） - 可访问的富 Internet 应用程序(WAI-ARIA) 1.1 | W3C"  
[W3CWaiAriaTree]: https://www.w3.org/TR/wai-aria-1.1/#tree "树（角色） - 可访问的富 Internet 应用程序 (WAI-ARIA) 1.1 | W3C"  

> [!NOTE]
> 此页面的某些部分是根据 [Google 创建和共享的][GoogleSitePolicies]作品所做的修改，并根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]中描述的条款使用。  
> [此处](https://developers.google.com/web/tools/chrome-devtools/accessibility/navigation) 可查找原始页面，其作者为 [Rob Dodson][RobDodson] \（参与者，Google WebFoundamentals\）。  

[![Creative Commons License][CCby4Image]][CCA4IL]  
本作品根据[ Creative Commons Attribution 4.0 International License ][CCA4IL]获得许可。  

[CCA4IL]: https://creativecommons.org/licenses/by/4.0  
[CCby4Image]: https://i.creativecommons.org/l/by/4.0/88x31.png  
[GoogleSitePolicies]: https://developers.google.com/terms/site-policies  
[KayceBasques]: https://developers.google.com/web/resources/contributors/kaycebasques  
[RobDodson]: https://developers.google.com/web/resources/contributors/robdodson  
