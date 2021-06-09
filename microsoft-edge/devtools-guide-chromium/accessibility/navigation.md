---
description: 有关使用辅助技术（如屏幕阅读器）导航 Microsoft Edge 开发工具的指南。
title: 使用辅助技术导航 Microsoft Edge 开发工具
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge、web 开发、f12 工具、开发工具
ms.openlocfilehash: 2cb57a8ea1ea34506b4698d80ae0981d8716f3d2
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597103"
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
# <a name="navigate-microsoft-edge-devtools-with-assistive-technology"></a>使用辅助技术导航 Microsoft Edge 开发工具  

本文可帮助主要依赖于辅助技术的用户（如屏幕阅读器）使用[Microsoft Edge DevTools。][MicrosoftEdgeDevtoolsMain]  DevTools 是内置于 Web 浏览器的一Microsoft Edge工具。  

有关改善网页辅助功能的 DevTools 功能，请参阅 [DevTools][DevtoolsAccessibilityReference] 中的辅助功能测试和使用 [DevTools](accessibility-testing-in-devtools.md)的辅助功能测试概述。

开发工具的辅助功能是一项正在进行中的工作。  某些工具和选项卡在辅助技术方面比使用其他工具和选项卡更好。  本指南将指导你完成最可访问的工具和选项卡，并重点说明你一直遇到的特定问题。  

## <a name="overview"></a>概述  

DevTools 分为一系列工具。   (在命令菜单中，**** 工具称为面板 。) 工具组织__ 到主工具栏和箱工具栏上的[ARIA][W3CWaiAriaTablist]选项卡列表中。

以下是工具示例：

*   元素 **工具** 允许你 [查看和更改 DOM 节点][DevtoolsDomIndexNavigateDomTreeKeyboard] 或 [CSS][DevtoolsCssIndex]。  
*   控制台 **工具** 允许你读取 JavaScript 日志和实时编辑对象。  有关详细信息，请导航到"[使用控制台"。][DevtoolsConsoleIndex]

在每个工具中，都有一组或多组选项卡。  例如， **元素** 工具包含一组选项卡，包括 **样式**、 **事件**侦听器 **和辅助功能**。

## <a name="keyboard-shortcuts"></a>键盘快捷方式  

[DevTools 键盘快捷方式参考][DevtoolsShortcuts]是一本有用的工作表。  请务必在浏览不同的工具时为它添加书签并引用回它。

## <a name="open-devtools"></a>打开开发工具  

若要开始，请导航到 [打开 Microsoft Edge 开发工具] [DevtoolsOpen]。  开发工具有多种打开方式，可以通过键盘快捷方式，也可通过菜单项将其打开。  

## <a name="navigate-between-tools"></a>在工具之间导航

### <a name="navigate-by-keyboard"></a>使用键盘导航  

*   打开 DevTools 后，选择 `Control` + `]` \ (Windows、Linux\) 或 `Command` + `]` \ (macOS\) 将焦点移到主工具栏上的下一个工具。
*   选择 `Control` + `[` \ (Windows、Linux\) 或 `Command` + \ (macOS\) 将焦点移到主工具栏上的上 `[` 一个工具。
*   选择 `Tab` 或 `Shift` + 重复选择，直到焦点移到主工具栏或箱工具栏的选项卡，然后使用箭头键在工具 `Tab` 之间移动。

**已知问题**  

*   一旦选择控制台**和性能**工具，某些**** 工具（如控制台和性能工具）可能会将焦点移到工具的内容区域中。  这可能使得使用箭头键导航更加困难。  
*   选定工具的名称将公布，但仅在宣布该工具中重点内容后公布。  此通知序列可能会轻松错过工具的名称。

### <a name="navigate-by-command-menu"></a>按命令菜单导航  

若要选择特定工具，请使用命令 [菜单][DevtoolsCommandMenuIndex]。  在命令菜单中，工具_称为面板。_

1.  打开开发工具，选择 `Control`+`Shift`+`P` \(Windows, Linux\) 或 `Command`+`Shift`+`P` \(macOS\) 以打开“**命令菜单**”。  
    命令 **菜单** 是一个模糊搜索自动完成组合框。  
1.  键入面板名称 (工具) ，然后使用键盘上的 导航 `Down Arrow` 到正确的选项。  
1.  选择 `Enter` 以运行命令。  

若要打开 **"元素"** 工具，请执行以下操作：

1.  打开“**命令菜单**”。  
1.  键入 `E` ，然后键入 `L`。  选择“**面板>显示元素**”选项。  
1.  选择 `Enter`。  

这样打开工具会将焦点放在工具的内容区域中。  对于" **元素"工具** ，焦点将移动到 **DOM 树中**。

## <a name="elements-tool"></a>元素工具

### <a name="inspect-an-element-on-the-page"></a>检查页面上的元素  

1.  使用屏幕阅读器中的光标导航到要检查的元素。  
1.  模拟右键单击元素以打开上下文菜单。  
1.  选择“**检查**”选项。  这将 [打开 Elements 工具并聚焦 DOM 树中的元素][DevtoolsDomIndexViewDomNodes]。  

“**DOM 树**”已布局为 [ARIA 树][W3CWaiAriaTree]。  例如，导航到 [使用键盘导航“**DOM Tree**”][DevtoolsDomIndexNavigateDomTreeKeyboard]。  

### <a name="copy-the-code-for-an-element-in-the-dom-tree"></a>复制 DOM 树中元素的代码  

1.  将焦点放在“**DOM 树**”中的节点上，然后将鼠标悬停在节点上，并打开上下文菜单 \（右键单击\）。  
1.  展开“**复制**”选项。  
1.  选择“**复制 outerHTML**”。  

**已知问题**  

*   “**复制 outerHTML**”通常不会选择当前节点，而是选择父节点。  但是，该元素的内容应仍在复制的 outerHTML 中。  

### <a name="modify-the-attributes-of-an-element-in-the-dom-tree"></a>修改 DOM 树中元素的属性  

*   将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。  
*   选择 `Tab` 以在属性值之间移动。  听到“空格”声音时，你已位于空白文本输入内，并且能够键入新的属性值。  
*   选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改并收听元素的全部内容。  

**已知问题**  

*   当你键入文本输入时，你未收到任何反馈。  如果你输入了拼写错误并使用箭头键来浏览你的输入，你同样不会收到反馈。  检查工作最简单的方法是接受更改，然后收听要播报的整个元素。  

### <a name="edit-the-html-of-an-element-in-the-dom-tree"></a>编辑 DOM 树中元素的 HTML  

*   将焦点放在“**DOM 树**”中的节点上时，选择 `Enter` 以使其可以编辑。  
*   选择 `Tab` 以在属性值之间移动。  当听到该元素的名称（例如，`h2`）时，你会位于文本输入内，并且可以更改元素的类型。  
*   选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 以接受更改。  

例如，键入 `h3` 并选择 `Control`+`Enter` \(Windows, Linux\) 或 `Command`+`Enter` \(macOS\) 时，`h3` 元素的开始和结尾标记都会更改。  

## <a name="tabs-in-the-elements-tool"></a>元素工具中的选项卡

元素 **工具** 包含用于检查应用于元素的 CSS 或辅助功能树中相关位置等内容的其他选项卡。  

*   焦点在**DOM**树中的节点上时，选择直到 `Tab` 您听到已**** 选择样式选项卡。  
*   使用 `Right Arrow` 浏览其他可用的选项卡。

“**DOM 树**”将具有 `href` 属性的元素转换为可聚焦链接，因此可能需要多次选择 `Tab` 以访问“**样式**”窗格。  

**已知问题**  

DOM **断点** 和 **属性** 选项卡不可通过键盘访问。  

### <a name="styles-pane"></a>样式窗格  

在“**样式**”窗格查找控件筛选样式、切换元素状态 \（如 [:active][MDNActive] 和 [:focus][MDNFocus]\）、切换类别和添加新类别。   还有一个功能强大的样式检查工具，用于浏览和修改当前应用于“**DOM 树**”中处于焦点的元素的样式。  

了解“**样式**”窗格的关键概念是它只显示“**DOM 树**”窗格中当前选中节点的样式。  例如，假设已完成对 `<header>` 节点样式的检查，并且现在希望查看 `<footer>` 节点的样式。  若要执行该操作，首先需要在“**DOM 树**”中选择 `<footer>` 节点。  如果使用 [检查](#inspect-an-element-on-the-page) 工作流检查位于 `footer` 节点 \（如页脚内的链接）邻近区域中的节点（该节点焦点为“**DOM 树**”），然后使用键盘导航到您感兴趣的确切节点，可能发现这一操作更为快速。  

#### <a name="navigate-the-styles-pane"></a>导航“样式”窗格  

由于所有样式工具都以某种方式连接到“**样式**”窗格中，因此首先掌握此工具的使用具有重要意义。  

*   在焦点位于“**样式**”窗格时 ，选择 `Tab` 以将焦点移到内部并浏览内容。  
*   选择 `Tab` 直到第一个样式处于活动状态。  如果使用屏幕阅读器，则第一个样式将播报为 `element.style {}`。  
*   选择 `Down Arrow` 以按特定性顺序导航样式列表。  屏幕阅读器将读出每个样式，播报以 CSS 文件名开头，再依次报出样式所在的行号以及样式的名称。  例如，`main.css:233 .card__img {}`。  
*   选择 `Enter` 以更详细地检查样式。  焦点从样式名称的可编辑版本开始。  
*   选择 `Tab` 以在每个 CSS 属性的可编辑版本和相应的值之间移动。  每个样式块的末尾都是一个空白的可编辑文本字段，可用于添加其他 CSS 属性。  
*   你可以继续选择在样式列表中移动，或者选择退出模式 `Tab` 并返回通过 `Escape` 箭头键导航。  

有关其他快捷方式，请导航到 [样式窗格键盘参考][DevtoolsShortcutsStylesPaneKeyboard]。  

**已知问题**  

*   如果你使用“**筛选器**”可编辑文本字段，则将不能再导航样式列表。  

#### <a name="toggle-element-state"></a>切换元素状态  

若要切换元素的状态，如 `:active` 或 `:focus`：  

1.  导航到“**样式**”窗格并选择 `Tab`，直到“**切换元素状态**”按钮获得焦点。  
1.  选择 `Enter` 以展开元素状态的集合。  元素状态将显示为一组复选框。  
1.  选择 `Tab`，直到第一个状态 `:active` 获得焦点。  
1.  选择 `Space` 以将其启用。  如果 DOM 树中当前选定的元素具有 `:active` 样式，则现在应用该样式。  
1.  按住 `Tab` 以浏览所有可用状态。  

#### <a name="add-an-existing-class"></a>添加现有类别  

“**元素类别**”按钮与“**切换元素状态**”按钮相邻。  若要将焦点移到它，请选择 `Tab` ，然后选择 `Enter` 。  焦点移到标记为添加新类的 **编辑文本字段**。  

“**元素类别**”按钮主要用于向元素添加现有类别。  例如，如果您的样式表包含一个名为 的帮助程序类，您可以在编辑文本字段内选择 以显示类的建议列表，并使用 查找 `.clearfix` `.` `Down Arrow` `.clearfix` 建议。  或者自行键入类别名称，然后选择 `Enter` 以应用类别。  

#### <a name="add-a-new-style-rule"></a>添加新的样式规则  

“**新样式规则**”按钮与“**元素类别**”按钮相邻。  若要将焦点移到它，请选择 `Tab` ，然后选择 `Enter` 。  焦点将移到样式检查器内的可编辑文本字段中。  该字段的初始文本内容是在“**DOM 树**”中所选元素的标记名称。  
您可以在此字段中键入您希望的任何类名称，然后选择为其分配 `Tab` CSS 属性。  

### <a name="computed-tab"></a>已计算选项卡  

在焦点位于“**已计算**”选项卡上时，选择 `Tab` 以将焦点移到内部并浏览内容。  在“**已计算**”选项卡中，有一些控件用于浏览哪些 CSS 属性实际上是按特定性顺序应用于元素的。  

<!--todo: add Computed tab section when available  -->  

#### <a name="explore-all-computed-styles"></a>浏览所有已计算的样式  

选择 `Tab`，直至到达已计算样式的集合。  这些内容将显示为“[ARIA 树][W3CWaiAriaTree]。  展开列表框会显示哪些 CSS 选择器正在应用已计算样式。  这些选择器按特定性进行整理。  屏幕阅读器将播报已计算的值、当前哪个 CSS 选择器正在匹配、包含该选择器的样式表文件名以及选择器行号。  

**已知问题**  

*   如果使用“**筛选**”文本字段，则不再能够检查样式。  

### <a name="event-listeners-tab"></a>"事件侦听器"选项卡  

若要检查应用于元素的事件侦听器，请选择"元素"工具，然后选择"**** 事件侦听器"选项卡 ("**** 样式"选项卡) 。 ****

#### <a name="explore-event-listeners"></a>浏览事件侦听器  

事件侦听器将显示为 [ARIA 树][W3CWaiAriaTree]。  可以使用箭头键导航它们。  屏幕阅读器将播报事件侦听器所附加到的 DOM 对象名称，以及定义事件侦听器的文件名和行号。  

### <a name="accessibility-tab"></a>"辅助功能"选项卡

在 `Tab` "元素"工具的"辅助功能 **"** 选项卡内选择要四 **处移动的** 键。

" **辅助功能"** 选项卡位于"样式" **选项卡** 附近。在"辅助功能"选项卡上，有一些控件用于探索辅助功能树、应用于元素的 ARIA 属性以及计算出的辅助功能属性。  有关详细信息，请导航到使用 [辅助功能选项卡测试辅助功能][DevtoolsAccessibilityTab]。

#### <a name="accessibility-tree"></a>辅助功能树  

**辅助功能树** 显示为 [ARIA 树][W3CWaiAriaTree]，其中每个 `treeitem` 对应 DOM 中的一个元素。  树将播报选定节点的已计算角色。  通用元素（如 `div` 和 `span`）将在树中播报为 “GenericContainer”。  使用箭头键来遍历树并浏览父子级关系。  

**已知问题**  

*   对于 MacOS 屏幕阅读器（如**** VoiceOver）来说，"辅助功能"选项卡Microsoft Edge [ARIA][W3CWaiAriaTree]树的类型可能未正确公开。  订阅 [Chromium 问题 #868480][ChromiumIssues868480] 以获取有关此问题进展的通知。  
*   每个 **ARIA 属性** 和 **已计算属性** 部分都标记为 [ARIA 树][W3CWaiAriaTree]，但当前每个部分都不具有焦点管理且不可通过键盘操作。  

## <a name="lighthouse-tool"></a>Lighthouse 工具

**Lighthouse** 对网站运行一系列测试，以检查与性能、辅助功能、SEO 和大量其他类别相关的常见问题。  

### <a name="configure-and-generate-a-report"></a>配置和生成报告

1.  在 DevTools 中首次打开 **Lighthouse** 工具时，焦点将放置在"生成报告 **"按钮** 上。  默认情况下，表单配置为在模拟 3G 连接上使用移动模拟来运行每个类别的报告。  
1.  若要更改报告设置，请使用 将焦点放在 `Shift` + `Tab` **Lighthouse 设置上**，或导航回浏览模式。  
1.  准备好运行报告后，导航回"生成 **报告"** 按钮并选择 `Enter` 。  
1.  焦点将移动到使用具有“**取消**”按钮的模式窗口，该按钮允许退出审核。  审核运行并多次刷新页面时，可能会听到一系列有声提示。  

**已知问题**  

*   配置窗体的不同部分当前未标记有 `fieldset` 元素。  在浏览模式下导航它们可能会更方便地了解与每个部分关联的控件。  
*   审核结束运行后，不会发布任何有声提示或实时区域公告。  通常，审核需要大约 30 秒，在此之后，你将能够导航到结果。  使用浏览模式可能是获取结果的最简单方法。  

### <a name="navigate-the-lighthouse-report"></a>导航"浅楼"报表  

Lighthouse 报告分为与每个审核类别对应的部分。  报告打开时显示每个类别的分数列表。  这些分数也是可用于跳到相关部分的链接。  每个章节内有可展开的 `details`元素，这些元素包含与审核通过或失败有关的信息。  默认情况下，仅显示失败的审核。  每节以最后一个 `details` 元素结尾，该元素包含所有通过的审核。  

若要运行新审核，请使用 `Shift` + `Tab` 退出报告并选择"生成**报告"** 按钮。  

## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  

<!-- links -->  
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"  
[DevtoolsAccessibilityTab]: accessibility-tab.md "使用&quot;辅助功能&quot;选项卡工具测试|Microsoft Docs"  
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
[DevtoolsShortcutsStylesPaneKeyboard]： ../shortcuts/index.md#styles-panel-keyboard-shortcuts "Styles panel keyboard shortcuts - Microsoft Edge DevTools Keyboard Shortcuts |Microsoft Docs"  

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
[KayceBasques]: https://developers.google.com/web/resources/contributors#kayce-basques  
[RobDodson]: https://developers.google.com/web/resources/contributors#rob-dodson  
