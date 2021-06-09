---
description: 使用 DevTools 开始测试辅助功能问题
title: 使用 DevTools 的辅助功能测试概述
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 50661f68c7b3269d003bdc25f6a8098ae0e3ec89
ms.sourcegitcommit: 34feec6ae6241c598911dac7b63c28d655691233
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "11597319"
---
# <a name="overview-of-accessibility-testing-using-devtools"></a>使用 DevTools 的辅助功能测试概述

本文介绍可在 DevTools 中用于测试辅助功能问题的一些功能。  我们将使用 DevTools 的不同功能检测演示页面中的辅助功能问题，并讨论如何解决这些问题。  打开 [新选项卡][DevToolsA11yErrorsDemopage] 中的演示页面，尝试一下自己，然后可以一起测试。

:::image type="complex" source="../media/a11y-testing-basics-demopage.msft.png" alt-text="本文中使用的演示页面具有一些辅助功能问题" lightbox="../media/a11y-testing-basics-demopage.msft.png":::
    本文中使用的演示页面具有一些辅助功能问题
:::image-end:::


## <a name="automated-testing-by-using-the-issues-tool"></a>使用问题工具自动测试

When you open the demo page in the browser and open DevTools， notice that some issues are automatically detected in the **Issues counter**.  Select the **Issues counter** \ (Issues ![ counter ](../media/issues-counter-icon.msft.png) \) to open the Issues [tool][DevToolsIssuesTool] to view the issues and more information.

:::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text=""问题"计数器显示当前网页中的问题个个，并打开"问题"工具" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
    "问题"计数器显示当前网页中的问题个个，并打开"问题"工具
:::image-end:::

对于本文，我们将重点介绍问题**工具**的**辅助功能部分。**

:::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="问题工具中显示的辅助功能警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
    问题工具中显示的辅助功能警告
:::image-end:::

有关详细演练步骤，请导航到查看 [问题工具的辅助功能部分][DevToolsAccessibilityTestIssuesToolViewAccSection]。


### <a name="automatically-checking-that-input-fields-have-labels"></a>自动检查输入字段是否包含标签

显示的第一个警告是 `Form elements must have labels: Element has no title attribute. Element has no placeholder attribute` 。  展开此部分并选择"在元素中打开****"链接时，将打开 **"** 元素"工具，同时在 DOM 树中突出显示元素。  " **样式** "选项卡显示应用于 元素的 CSS。

有关详细演练步骤，请导航到"[验证输入字段是否包含标签"。][DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]

:::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="在"问题"工具中选择链接后显示有问题的 HTML 的元素工具" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
    在"问题"工具中选择链接后显示有问题的 HTML 的元素工具
:::image-end:::

在这种情况下，HTML 具有 `label` 不起作用的元素。

```html
<label>Search</label>
<input type="search">
<input type="submit" value="go">
```

此处元素的使用有误，因为 元素和 元素之间 `label` `label` 没有 `input` 连接。  当您选择搜索标签时，有效的 HTML 标签将焦点放在搜索输入 **文本框** 上。 

可以通过将 元素嵌套在 元素中，或添加指向 元素属性的属性来 `input` `label` `for` `id` 解决此问题 `input` 。  若要查看正确的连接，请选择"捐赠 **"表单** 上的"其他"标签。

还可以选择问题工具中的说明 **性** 链接获取此信息。

:::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="问题工具中指向有关问题的更深入信息的链接" lightbox="../media/a11y-testing-more-information-links.msft.png":::
    问题 **工具中** 指向有关问题的更深入信息的链接
:::image-end:::


### <a name="automatically-checking-that-images-have-alt-text"></a>自动检查图像是否包含替换文字

另一个自动检测到的问题是，页面中的许多图像没有任何替代文本。  如果展开警告 `Images must have alternate text: Element has no title attribute` ，将获取具有此问题的四个图像实例。

:::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="问题工具，报告缺少可选文本的图像" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
    问题 **工具** ，报告缺少可选文本的图像
:::image-end:::

有关详细演练步骤，请导航到["验证图像是否具有替换文字"。][DevtoolsAccessibilityTestIssuesToolCheckAltText]


### <a name="automatically-checking-that-text-colors-have-enough-contrast"></a>自动检查文本颜色是否具有足够的对比度

" **问题** "工具还报告页面上的两个元素没有足够的对比度。

:::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="问题工具中报告的对比度问题" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
    问题工具中报告的 **对比度** 问题
:::image-end:::

问题 **工具** 提供警告的详细说明。  向下钻取时，将获取具有此问题的元素的列表。  在 **"问题** "工具中，选择指向某个元素的链接将在呈现的页面上突出显示该元素。

:::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="选择指向该页面的链接后突出显示的页面中的元素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
    选择指向该页面的链接后突出显示的页面中的元素
:::image-end:::

有关详细演练步骤，请导航到"[验证文本颜色是否具有足够的对比度"。][DevtoolsAccessibilityTestIssuesToolCheckContrast]


### <a name="verify-that-the-webpage-layout-is-usable-when-narrow"></a>验证网页布局在较窄时是否可用

<!-- by design, this section doesn't have a corresponding how-to article -->

辅助功能的一个重要部分是确保 Web 产品在较窄的视口上良好工作。 许多用户需要缩放页面才能使用它，这意味着没有太多空间。 当空间不足时，多列布局应转换为单列布局，内容按可理解的顺序放置。 这意味着将最重要的内容放置在页面顶部，将其他内容放置在页面的更下一层。

通过缩小浏览器窗口范围，使用箭头键滚动页面，可以看到演示页面的顶部导航栏具有一些辅助功能问题。  顶部导航栏与 **"** 搜索"窗体重叠，如上图所示，需要修复该问题。

可以通过调整浏览器窗口的大小来模拟较窄的视区，但测试设计响应性更好的方法就是使用 **设备仿真** 工具。  以下是设备仿真 **工具的一** 些功能，可帮助你查找任何网站的辅助功能问题：

*  无需调整浏览器窗口的大小，即可调整页面大小并测试 CSS [媒体][DevToolsMediaQueries] 查询是否触发布局更改。
*  检查是否使用鼠标的依赖项。 默认情况下，设备仿真假定为触摸设备。 这意味着产品依赖于悬停交互的任何功能将不起作用。 
*  通过模拟不同的设备、缩放级别和像素比率执行视觉测试。
*  测试产品在不可靠连接或用户脱机时的行为方式。  在低速连接上向用户显示最重要的交互也是辅助功能注意事项。

若要了解有关设备仿真**工具**的信息，请导航到在[DevTools Microsoft Edge模拟移动设备][DevToolsDeviceModeIndex]。


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a>DOM 树中的波浪下划线指示自动检测到的问题

"元素"工具中的 DOM **树通过** 添加波浪下划线自动在 HTML 中直接标记问题。  If you `Shift` + `click` any element that has a wavy underline， the **Issues** tool opens.

:::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="在 DOM 树中以波浪下划线显示的元素有问题。  Shift+单击元素以直接解决问题" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
    在 DOM 树中以波浪下划线显示的元素有问题。  `Shift`+`click` 直接进入问题的 元素。
:::image-end:::

问题工具发现的 **这些问题是一** 些可以避免的相对明显的辅助功能问题。  使用 **问题** 工具及其指导性说明修复问题，可引导你实现可访问的产品。


## <a name="limits-of-automated-testing"></a>自动测试的限制

问题[工具][DevToolsIssuesTool][、Accessibility Insights][AccessibilityInsights]和[Lighthouse][Lighthouse]是自动生成网页的辅助功能报告的工具。  从此类工具获取自动报告只是辅助功能测试之旅的开始。

辅助功能与人员交互有关，即在不同的技术环境中使用产品时具有不同的需求的人。  此测试无法完全自动化，但需要用户验证产品。  在最佳方案中，你有权访问具有不同辅助功能需求的测试人员和使用各种环境的测试人员。  但是，通过使用键盘进行导航并检查页面的不同部分，你已可以自己执行很多操作。

在演示页面上，还有一些自动测试无法检测到的其他问题，包括： 

*  与页面交互后出现的问题。 
*  与显示更改相关的问题，例如使窗口变窄。

其中一个问题就是"捐赠"表单。  使用鼠标时，可以单击不同的选项来赚钱。  但是，当您尝试使用键盘访问该资金表单时，不会执行任何操作。 若要解决此问题，您需要使用 **Inspect** 工具。

:::image type="complex" source="../media/a11y-testing-basics-donation-form-issue.msft.png" alt-text="演示页面上的"资金"表单突出显示" lightbox="../media/a11y-testing-basics-donation-form-issue.msft.png":::
    演示页面上的"资金"表单突出显示
:::image-end:::


## <a name="using-the-inspect-tool-to-detect-accessibility-issues"></a>使用检查工具检测辅助功能问题

使用 **"检查** "工具通过将鼠标悬停在网页的某些部分来检测辅助功能问题。  Inspect **** \ (Inspect ![ \) 工具位于 ](../media/inspect-icon.msft.png) DevTools 的左上角。  通过选择"检查工具"按钮 **打开"检查** "工具。

:::image type="complex" source="../media/a11y-testing-basics-inspector.msft.png" alt-text="通过选择"检查工具"按钮打开"检查"工具" lightbox="../media/a11y-testing-basics-inspector.msft.png":::
    通过选择 **"检查** 工具"按钮 **打开"检查** "工具
:::image-end:::

选择" **检查工具"** 按钮后，可以将指针移动到呈现页面上的任何元素上。  Inspect 工具将元素的布局显示为多色弹性框覆盖，将元素详细信息作为类似于工具提示的信息覆盖显示。

:::image type="complex" source="../media/inspect-tool-flexbox-overlay.msft.png" alt-text="使用 Inspect 工具时的多色弹性框覆盖和信息覆盖" lightbox="../media/inspect-tool-flexbox-overlay.msft.png":::
    使用 Inspect 工具时的多色弹性框覆盖 **和信息** 覆盖
:::image-end:::

检查工具的辅助功能**部分包括****对比度线**（如果适用）。

:::image type="complex" source="../media/a11y-testing-basics-inspector-overlay.msft.png" alt-text="检查工具的辅助功能部分包括对比度行（如果适用）" lightbox="../media/a11y-testing-basics-inspector-overlay.msft.png":::
    检查工具的辅助功能**部分包括****对比度行**（如果适用）
:::image-end:::

有关详细演练步骤，请导航到使用颜色 [突出显示标识嵌套区域][DevtoolsAccessibilityTestInspectToolColorHighlighting]。
<!-- = test-inspect-tool.md##identify-nested-regions-using-color-highlighting -->

检查工具的信息覆盖的**** 上半部分显示以下信息：

* 布局类型;如果元素是使用弹性框或网格定位的，则会看到相应的图标 \ (![网格布局图标](../media/grid-icon.msft.png)\).
* 元素的名称，如 、 **h1**或**div**。 ****
* 元素的尺寸（以像素为单位）。
* 颜色作为颜色样本， (较小的彩色方形) 和格式化值 (如 `#336699`) 。
* 字体信息 (大小和字体系列) 。
* 边距和填充（以像素为单位）。

检查 **覆盖** 的辅助功能 **部分** 如下一节所述。


### <a name="checking-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support"></a>检查各个元素的文本对比度、屏幕阅读器文本和键盘支持

Inspect **覆盖** 的"辅助功能 **"** 部分包含以下行：

*   **对比度** 定义弱视用户能否理解元素。
    *   [WCAG][WCAG]准则定义的对比率指示文本和背景颜色之间的对比度是否足够。 [][W3CContrastRatio]  绿色选中标记图标表示没有足够的对比度，橙色感叹号图标表示对比度不足。

*   **名称和****角色**指示哪些信息辅助技术（如屏幕阅读器）将报告有关元素的信息。
    *   **Name**是元素的文本 `a` 内容。  对于 元素 `<a href="/">About Us</a>` **，Inspect** 工具中显示的 Name 为"关于我们"。
    *   **元素**的角色。  **Role**通常是元素名称，如 、 `article` 、 `img` 或 `link` `heading` 。  `div`和 `span` 元素表示为 `generic` 。

*   **键盘可聚焦** 指示用户是否可以使用除鼠标外的其他输入设备访问元素。
    *   绿色选中标记图标指示元素是键盘可聚焦的。
    *   带对角线的灰色圆圈表示元素不可通过键盘聚焦。

有关详细演练步骤，请导航到检查各个元素的文本 [对比度、屏幕阅读器文本和键盘支持][DevtoolsAccessibilityTestInspectToolIndivElems]。
<!-- = test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support -->


### <a name="using-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css"></a>使用 Inspect 工具将鼠标悬停在网页上方以突出显示 DOM 和 CSS

使用 **Inspect 工具** 时，选择呈现页上的元素将打开 **Elements** 工具。  DOM 树显示元素的 **HTML，Styles** 显示应用于元素的 CSS 属性。

:::image type="complex" source="../media/a11y-testing-basics-inspector-selected-element.msft.png" alt-text="有关"元素"工具中显示的选定元素的详细信息" lightbox="../media/a11y-testing-basics-inspector-selected-element.msft.png":::
    有关"元素"工具中显示的选定元素的详细信息
:::image-end:::

使用 **Inspect 工具** 时，将鼠标悬停在打开 **Elements** 的呈现页面的不同部分时，你会注意到 DOM 树会自动刷新。

有关详细演练步骤，请导航到"使用检查工具将鼠标悬停在网页上方"以突出显示[DOM 和 CSS。][DevtoolsAccessibilityTestInspectToolDomCss]
<!-- = test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css -->


## <a name="verify-keyboard-support-by-using-the-tab-and-enter-keys"></a>使用 Tab 键和 Enter 键验证键盘支持

并非所有用户都使用指针或触摸设备，并且某些用户可能有低视力。 若要适应这些方案，请确保 IS 与键盘一起工作。

通过使用 或 从元素跳到元素，可以使用键盘来 `Tab` 导航 `Shift+Tab` 页面。  如果按下演示页面，则获得焦点的第一件事 `Tab` 是页面页眉中的 **搜索** 窗体。  即使使用"问题"工具之前发现的标签问题，通过按"甚至"还可以提交表单，这样 `Enter` **操作仍然** 有效。

有关详细演练步骤，请导航到使用 Tab 键和 Enter 键检查 [键盘支持](test-tab-enter-keys.md)。

当按下 而不是 时，下一个获得焦点的元素是页面内容部分的第一个"更多"链接， `Tab` `Enter` 如大纲所指示。 ****

:::image type="complex" source="../media/a11y-testing-keyboard-focus-on-element.msft.png" alt-text="使用 Tab 键导航页面。  焦点显示在页面中的"更多"链接上。" lightbox="../media/a11y-testing-keyboard-focus-on-element.msft.png":::
    使用 键导航 `Tab` 页面。  焦点显示在页面中的 **"更多** "链接上。
:::image-end:::

在通过最后一个 **"更多** "链接后，页面将向上滚动，并且不清楚哪个元素具有焦点。

如果你查看屏幕左下角或使用屏幕阅读器，你可以判断边栏导航菜单中的蓝色 **"猫** "链接具有焦点，因为浏览器显示 URL `#cats` 。

:::image type="complex" source="../media/a11y-testing-lack-of-focus-style.msft.png" alt-text="缺少焦点样式使无法知道你当前在页面中的什么位置。  唯一的提示是在窗口左下角显示链接目标。" lightbox="../media/a11y-testing-lack-of-focus-style.msft.png":::
    缺少焦点样式使无法知道你当前在页面中的什么位置。  唯一的提示是在窗口左下角显示链接目标。
:::image-end:::

再次 `Tab` 选择，将你带至"发送"表单的输入文本框。  但是，你无法到达输入文本框上方**的 50、100**或**200**个按钮。 ****  此外，当焦点位于该输入文本框上时，选择 `Enter` 不会提交表单。

:::image type="complex" source="../media/a11y-testing-form-field-with-outline.msft.png" alt-text="在资金表单中，唯一一个可通过键盘访问的元素是输入文本字段" lightbox="../media/a11y-testing-form-field-with-outline.msft.png":::
    在捐赠窗体中，唯一一个可通过键盘访问的元素是文本字段
:::image-end:::

再次选择会将焦点放在顶部导航栏上，您可以选择转到页面的不同部分或网站的不同 `Tab` `Enter` 页面。  你知道自己位于哪个元素上，因为有焦点轮廓。  若要选择顶部导航栏中的链接，请使用 或 将焦点放在链接上， `Tab` `Shift+Tab` 然后选择 `Enter` 。

:::image type="complex" source="../media/a11y-testing-menu-with-outline.msft.png" alt-text="顶部导航栏具有突出显示和焦点轮廓，因此键盘可访问" lightbox="../media/a11y-testing-menu-with-outline.msft.png":::
    顶部导航栏具有突出显示和焦点轮廓，因此键盘可访问
:::image-end:::

我们发现了一些要修复的问题：

* 使用键盘在页面上四处移动时，边栏导航菜单不会向用户显示 `Tab` 焦点位置。
* 在使用键盘时，在"捐赠"表单上 **，**50、100、** 和 200** 个按钮和表单提交功能不起作用。
* 键盘 Tab 键顺序不正确。 键 `Tab` 在边栏导航菜单前**** 浏览页面上的所有"更多"链接。  此顺序没有帮助，因为边栏导航旨在将你导航到该 `Tab` 页面的不同部分。 

让我们使用 DevTools 分析这些问题。


## <a name="analyze-keyboard-accessibility-issues-using-devtools"></a>使用 DevTools 分析键盘辅助功能问题


### <a name="analyzing-the-lack-of-indication-of-keyboard-focus-in-the-sidebar-menu"></a>分析边栏菜单中缺少键盘焦点的指示

若要了解为什么边栏导航未按预期优化以用于键盘，请首先使用**Inspect**工具突出显示边栏导航菜单中的链接，然后在 DOM 树中向下钻取到 元素。 `a` 

:::image type="complex" source="../media/a11y-testing-menu-link.msft.png" alt-text="检查边栏导航菜单中的链接的源代码和应用样式" lightbox="../media/a11y-testing-menu-link.msft.png":::
    检查边栏导航菜单中的链接的源代码和应用样式
:::image-end:::

在 **"样式** "选项卡中，可以看到应用于链接的 CSS，如果选择指向 的链接，文件将在"源" `styles.css` 工具 **中** 打开。

:::image type="complex" source="../media/a11y-testing-menu-link-styles.msft.png" alt-text="应用于链接的样式，如"源"工具中所示" lightbox="../media/a11y-testing-menu-link-styles.msft.png":::
    应用于链接的样式，如"源"工具中所示
:::image-end:::

在以上示例中，当您使用鼠标时，页面的样式包含菜单项上的状态，但键盘用户的 `hover` `focus` CSS 中没有任何状态。  

此外，此示例中的链接使用 `outline: none` 。 此样式用于删除浏览器在具有焦点和使用键盘时自动添加到元素中的轮廓。  若要避免此问题，请勿使用 `outline: none` 。

有关详细演练步骤，请导航到分析边栏菜单中缺少 [键盘焦点的指示](test-analyze-no-focus-indicator.md)。


### <a name="analyzing-the-lack-of-keyboard-support-in-the-donation-form"></a>分析在资金表单中缺少键盘支持

使用 元素实现"支持"表单上的按钮，而自动测试工具无法将元素识别 `div` 为表单上的控件。

若要调查这一点，可以使用 **"检查** "工具将鼠标悬停在"捐赠"表单的按钮上。  结果是它们都不是键盘可访问的，如信息覆盖的 **键盘** 可聚焦行上的灰色圈所指示。  如信息覆盖的****"名称****"和"角色"行所示，"捐赠"表单的按钮也没有任何名称，其角色为 (表示或元素 `generic` `div` `span`) ，这意味着它们不能通过辅助技术访问。

:::image type="complex" source="../media/a11y-testing-donation-button-info.msft.png" alt-text="检查表单的按钮时，会显示它们无法通过键盘访问" lightbox="../media/a11y-testing-donation-button-info.msft.png":::
    检查表单的按钮时，会显示它们无法通过键盘访问
:::image-end:::

有关详细演练步骤，请导航到分析表单中 [缺少键盘支持](test-analyze-no-keyboard-support.md)。

如果选择" **打开"按钮** ，" **检查** "工具将您导航到 **"元素** "工具，然后显示表单的 HTML。

```HTML
<div class="donationrow">
    <div class="donationbutton">50</div>
    <div class="donationbutton">100</div>
    <div class="donationbutton">200</div>
</div>
<div class="donationrow">
    <label for="freedonation">Other</label>
    <input id="freedonation" class="smallinput">
</div>
<div class="donationrow">
    <div class="submitbutton">Donate</div>
</div>
```

使用 和 元素是有效的，这导致标签能够正常使用，并且 `label` `input` `input` 文本框是键盘可访问的。  表单的其余部分使用 `div` 元素，这些元素易于设置样式，但没有任何语义含义。

接下来，我们分析表单的 JavaScript 功能。 在 **"元素**"中，选择" **事件** 侦听器"选项卡以分析表单的 JavaScript。

:::image type="complex" source="../media/a11y-testing-event-handlers-on-button.msft.png" alt-text=""事件侦听器"选项卡，包含指向表单的 JavaScript 的链接" lightbox="../media/a11y-testing-event-handlers-on-button.msft.png":::
    " **事件侦听器"** 选项卡，包含指向表单的 JavaScript 的链接
:::image-end:::

在 **"事件侦听器**"选项卡上，选择链接以打开"源"工具，然后检查负责表单 `buttons.js:18` 功能的**** JavaScript。

:::image type="complex" source="../media/a11y-testing-form-handling-javascript.msft.png" alt-text="负责"接收"表单功能的 JavaScript，显示在"源"工具中" lightbox="../media/a11y-testing-form-handling-javascript.msft.png":::
    负责"接收"表单功能的 JavaScript，显示在" **源"工具** 中
:::image-end:::

`click`建议将事件与按钮一同使用，因为事件同时用于 `click` 鼠标指针和键盘。  但是，由于元素不可通过键盘访问，并且"完成"按钮作为元素实现，因此此 JavaScript 仅在使用鼠标 `div` **** `div` 时运行。

使用 `div` 作为按钮是一个经典示例，其中需要额外 JavaScript 才能创建元素 `button` 提供的功能。 因此，这会导致无法访问体验。


### <a name="checking-the-accessibility-tree-for-keyboard-and-screen-reader-support"></a>检查辅助功能树是否支持键盘和屏幕阅读器

使用 **Inspect** 工具单独检查页面上的每个元素非常耗时。  相反，使用 **"辅助功能"** 选项卡导航页面的 **"辅助功能树"。**  辅助功能树指示页面向辅助技术（如屏幕阅读器）提供哪些信息。

:::image type="complex" source="../media/a11y-testing-accessibility-tree.msft.png" alt-text="辅助功能树中的"资金"表单按钮" lightbox="../media/a11y-testing-accessibility-tree.msft.png":::
    辅助功能树中的"资金 **"表单按钮**
:::image-end:::

树中没有名称或角色为 的任何元素都是问题，因为该元素对键盘用户或使用辅助技术的用户 `generic` 不可用。

有关详细演练步骤，请导航到检查 [辅助功能树，获取键盘和屏幕阅读器支持](test-accessibility-tree.md)。


### <a name="analyzing-the-order-of-keyboard-access-to-sections-of-the-page"></a>分析键盘访问页面部分的顺序

另一个问题就是页面上的 Tab 键顺序不明确。  键盘用户只有在按 Tab 键浏览整个页面的所有"更多"链接后 **才能到达边** 栏导航菜单。  本示例中，边栏导航菜单旨在作为该页面不同分区的快捷方式。  此 Tab 键顺序会导致用户体验不佳。 

混乱顺序的原因是它 `Tab` 由文档的源顺序确定。  也可通过使用元素上的 属性来修改 Tab 键顺序，该元素使该元素 `tabindex` 退出默认源顺序。

在文档的源代码中，边栏导航菜单显示在页面主要内容之后。  边栏导航菜单显示在页面主要内容的上方，仅仅是因为边栏导航菜单已使用 CSS 定位。

文档的源顺序对于辅助技术非常重要，并且可能不同于元素在呈现页面上的显示顺序。  使用 CSS，您可以直观地对页面元素进行重新排序，但这并不意味着屏幕阅读器等辅助技术将按与 CSS 相同的顺序表示页面元素。

可以使用"辅助功能"选项卡中的"源 **顺序** 查看器"测试 **页面元素** 的顺序。 一直向下滚动，然后选中" **显示源订单"** 复选框。  现在，当您在 **"** 元素"工具中导航 DOM 树（如选择元素）时，数值覆盖显示在呈现的页面的表示源顺序的各个 `header` 部分。 

:::image type="complex" source="../media/a11y-testing-source-order-viewer.msft.png" alt-text="打开"源订单查看器"将显示源代码中元素在页面上作为数字覆盖的顺序" lightbox="../media/a11y-testing-source-order-viewer.msft.png":::
    打开" **源订单** 查看器"将显示源代码中元素在页面上作为数字覆盖的顺序
:::image-end:::

有关详细演练步骤，请导航到使用源顺序 [查看器测试键盘支持](test-tab-key-source-order-viewer.md)。


## <a name="testing-contrast-of-text-colors-in-various-states"></a>测试不同状态的文本颜色的对比度

检查 **工具** 一次报告一个状态辅助功能问题。  首先，我们将介绍使用 Inspect 工具仅查看页面元素的静态状态的限制。  然后，我们将介绍如何检查页面元素的其他状态，通过在"样式"选项卡上选择"切换元素状态 (**\：hov **) 切换 **元素状态** "。

### <a name="checking-text-color-contrast-in-the-default-state"></a>检查默认状态下的文本颜色对比度

除了问题工具中的自动颜色对比度测试之外，您还可以**** 使用**Inspect**工具检查各个页面元素是否具有足够的对比度。  如果对比度信息可用，" **检查** "覆盖层将显示对比率和复选框项。  绿色选中标记图标表示对比度足够高，黄色警报图标表示对比度不足。

例如，边栏导航菜单中的链接具有足够的对比度，但"参与状态"部分中的**** 绿色"动物"列表**** 项没有。  "检查"覆盖层中的警告标记了对比度 **不足** 的元素。

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-enough-contrast.msft.png" alt-text="边栏导航菜单中的链接具有足够的对比度，如检查覆盖中所示" lightbox="../media/a11y-testing-enough-contrast.msft.png":::
            边栏导航菜单中的链接具有足够的对比度，如检查**覆盖中所示** :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-not-enough-contrast.msft.png" alt-text=""检查"覆盖层中的警告标记了对比度不足的元素" lightbox="../media/a11y-testing-not-enough-contrast.msft.png":::
            "检查"覆盖层中的警告标记了对比度 **不足** 的元素 :::image-end:::
    :::column-end:::
:::row-end:::

这样 **使用 Inspect** 工具并不能完全测试元素。 页面上的元素可能具有不同的状态，所有这些状态都需要进行测试。 例如，如果将鼠标悬停在边栏导航菜单上，请注意更改链接颜色动画。

:::image type="complex" source="../media/a11y-testing-hover.msft.png" alt-text="鼠标指针悬停在不同的菜单项上时显示不同的颜色" lightbox="../media/a11y-testing-hover.msft.png":::
    鼠标指针悬停在不同的菜单项上时显示不同的颜色
:::image-end:::

### <a name="verify-accessibility-of-all-states-of-elements-such-as-the-contrast-on-hover"></a>验证元素的所有状态（如悬停时对比度）的辅助功能

使用 DevTools 时，你需要模拟元素的所有状态，因为 **Inspect** 工具不会同时显示所有状态的信息。 本示例中，使用**Inspect**工具时，你无法到达边栏导航菜单上的"猫"链接的状态来分析状态中的对比率，因为样式中的状态 `hover` **** `hover` `hover` 不会触发。  相反，你需要使用"样式"选项卡中的状态模拟来模拟 **"猫**"**菜单项的状态。**

有关详细演练步骤，请导航到验证元素 [的所有状态是否可访问](test-inspect-states.md)。

打开检查 **工具** ，然后在呈现的页面中，选择边栏导航菜单中的蓝色 **"猫** "链接。  将 **打开"** 元素"工具， `a` 同时在 DOM 树中选择元素。  如果需要，在 DOM 树中，导航到 CSS 中 `hover` 具有状态的元素。  在这种情况下，元素 `a` 具有 `hover` 状态。

:::image type="complex" source="../media/a11y-testing-inspecting-link-to-hover.msft.png" alt-text="检查元素工具中具有悬停状态的元素" lightbox="../media/a11y-testing-inspecting-link-to-hover.msft.png":::
    检查元素工具中具有悬停状态的元素
:::image-end:::

在" **样式"** 选项卡上，选择 **"\：hov (切换元素状态) ** 按钮。  然后使用 **"Force 元素状态** "复选框选择要模拟的状态。

:::image type="complex" source="../media/a11y-testing-state-simulation.msft.png" alt-text="显示所有选项的状态模拟功能" lightbox="../media/a11y-testing-state-simulation.msft.png":::
    显示所有选项的状态模拟功能
:::image-end:::

选中 **\：hover** 复选框。  现在 DOM 元素旁边将出现一个黄色点，指示 DOM 元素具有模拟状态。  此外，边栏导航菜单中的 **"猫** "链接现在在页面中突出显示，就像鼠标指针悬停在它上方一样。

:::image type="complex" source="../media/a11y-testing-hover-simulated.msft.png" alt-text="模拟悬停状态的开发工具" lightbox="../media/a11y-testing-hover-simulated.msft.png":::
    模拟悬停状态的开发工具
:::image-end:::

应用模拟状态后，可以再次使用 **Inspect** 工具在用户将鼠标悬停在元素上时检查元素的对比度。  在这种情况下，对比度不够高。

:::image type="complex" source="../media/a11y-testing-hover-contrast-testing.msft.png" alt-text="在模拟悬停状态中测试元素的对比度" lightbox="../media/a11y-testing-hover-contrast-testing.msft.png":::
    在模拟悬停状态中测试元素的对比度
:::image-end:::

状态模拟也是检查你是否认为不同的用户需求的一个好方法。  对于边栏导航菜单，你可以检测 `:focus` 状态是否具有对比度问题。


## <a name="use-the-rendering-tool-to-test-accessibility-for-visual-impairment"></a>使用呈现工具测试辅助功能视觉障碍

### <a name="check-contrast-issues-with-dark-theme-and-light-themes"></a>检查深色主题和浅色主题的对比度问题

在颜色辅助功能方面的另一个注意事项是，可能需要测试不同的主题，以检查对比度问题。  大多数操作系统具有深色模式和浅色模式。  网页可以使用 CSS 媒体查询对这些不同的设置做出反应。

此演示页面具有浅色和深色主题。  通过使用呈现工具中的深色或浅色配色方案模拟，无需更改操作系统 [即可][DevToolsColorSchemeSimulation] 测试这两 **个主题** 。  到目前为止，本文查看了使用深色主题设置的操作系统的演示页面。  如果我们改为模拟光线方案，然后刷新页面，问题工具将显示六**** 个颜色对比度问题，而不是两个。

有关详细演练步骤，请导航到检查深色主题和浅色主题 [的对比度问题](test-dark-mode.md)。


在呈现工具中 **切换到浅色** 主题时，请注意以下项目。

*  由于浅色主题更改，检测到新的对比度问题。
*  页面 **的整个"接收状态** "部分在浅色模式下不可读取。

:::row:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png" alt-text="由于浅色主题更改而检测到的新对比度问题" lightbox="../media/a11y-testing-new-contrast-issues-in-light-mode.msft.png":::
            由于浅色主题更改而检测到的新对比度问题 :::image-end:::
    :::column-end:::
    :::column:::
        :::image type="complex" source="../media/a11y-testing-donation-state-light-contrast.msft.png" alt-text="在浅色模式下标记为对比度问题的接收状态项目" lightbox="../media/a11y-testing-donation-state-light-contrast.msft.png":::
            在浅色模式下标记为对比度问题的接收状态项目 :::image-end:::
    :::column-end:::
:::row-end:::


### <a name="verify-that-the-webpage-is-usable-by-people-with-color-blindness"></a>验证网页是否对色盲者可用

不同的接收状态使用红色 (绿色、黄色) 颜色作为区分资金状态的唯一方式。  但是，你无法预期所有用户都体验这些颜色。  如果你使用 DevTools 的视觉缺陷模拟功能，则通过模拟不同视觉的人如何理解你的设计，你可以发现这不够好。 [][DevToolsVisionDeficiencies]
有关详细演练步骤，请导航到验证页面是否适用于色 [盲用户](test-color-blindness.md)。
:::image type="complex" source="../media/a11y-testing-simulating-protanopia.msft.png" alt-text="将页面显示为具有亚特 <9> <9>色 (色盲) 可以看到页面" lightbox="../media/a11y-testing-simulating-protanopia.msft.png":::
    显示页面，就像有亚特 <9>色 (色盲) 会看到页面
:::image-end:::



### <a name="verify-that-the-webpage-is-usable-with-blurred-vision"></a>验证网页是否具有模糊视觉

呈现工具的另一 **个** 有趣功能是，你可以模拟模糊的视觉。  如果我们从"模拟**** 视觉缺陷"下拉列表中选择"**** 模糊视觉"选项，可以看到上菜单中文本上的投影使阅读菜单项变得困难。
有关详细的演练步骤，请导航到验证 [页面是否可用模糊的视觉](test-blurred-vision.md)。

:::image type="complex" source="../media/a11y-testing-simulating-blur.msft.png" alt-text="模拟模糊的页面可能会发现辅助功能问题" lightbox="../media/a11y-testing-simulating-blur.msft.png":::
    模拟模糊的页面可能会发现辅助功能问题
:::image-end:::


### <a name="verify-that-the-page-is-usable-with-ui-animation-turned-off-reduced-motion"></a>验证页面是否可用，并关闭 UI 动画， (运动) 

这些天操作系统提供的另一个设置是关闭动画的方法。  动画可以帮助产品的可用性，但它们也会导致许多问题，包括混淆和混乱。 这就是产品不应向在操作系统中关闭动画的用户显示动画的原因。  通过使用 CSS 媒体查询，您可以检查用户是否希望查看动画，并相应地将其关闭。  而且，与深色和浅色模式很类似，有一种方法可以模拟使用 [DevTools 的减少运动][DevToolsReducedMotion]。

在此处的演示页中，当你选择边栏导航菜单的不同部分时，关闭动画将停止页面的平滑滚动。  这可以通过在媒体查询中将平滑滚动设置包装在 CSS 中实现：

:::image type="complex" source="../media/a11y-testing-simulating-reduced-motion.msft.png" alt-text="模拟减少运动和 CSS，以确保仅在用户需要时发生平滑滚动" lightbox="../media/a11y-testing-simulating-reduced-motion.msft.png":::
    模拟减少运动和 CSS，以确保仅在用户需要时发生平滑滚动
:::image-end:::

```css
@media (prefers-reduced-motion: no-preference) {
  html {
    scroll-behavior: smooth;
  }
}
```

此 CSS 媒体查询有条件地运行"平滑滚动"动画。  但是顶部导航栏、边栏导航菜单和更多链接的动画仍然**** 运行，即使用户不想看到动画。 这些其他动画需要有条件地运行，例如通过添加其他媒体查询。

有关详细的演练步骤，请导航到验证页面是否可用，并关闭 [UI 动画](test-reduced-ui-motion.md)。


## <a name="what-to-do-next"></a>下一步该怎么办？

我们介绍了许多可用于确保捕获产品中的辅助功能问题的工具。  这些工具的范围从自动检查和手动详细检查到不同状态和环境的模拟。  这些工具汇总在 [DevTools 中的辅助功能测试功能中](reference.md)。  自动化工具无法找到产品的所有问题，因为许多辅助功能障碍仅在交互式使用期间出现。

这些工具均无法将正确的一轮产品测试替换为使用辅助技术并遵循检查所有所需测试的计划。 您还可以使用[辅助功能见解][AccessibilityInsightsAssessment][的评估功能][AccessibilityInsights]。  您可能需要执行其他检查，例如：

* 放大时进行测试。
* 使用屏幕阅读器进行测试。
* 使用语音识别进行测试。
* 在高对比度模式下进行测试。

了解改进 Web 产品的方法的另一个方法为使用[webhint 扩展Visual Studio Code。][WebhintForCode]  此扩展标记源代码中易检测到的辅助功能问题，并提供了如何修复这些问题的见解。

:::image type="complex" source="../media/a11y-testing-webhint-in-vs-code.msft.png" alt-text="Webhint in Visual Studio Code， showing an accessibility issue by underlining the HTML element and showing an explanation of the problem" lightbox="../media/a11y-testing-webhint-in-vs-code.msft.png":::
    Webhint in Visual Studio Code， showing an accessibility issue by underlining the HTML element and showing an explanation of the problem
:::image-end:::

We're constantly working on new accessibility features for DevTools.  如果缺少任何内容，请给我们发送消息，并告诉我们我们可以做什么。


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]


<!-- links -->
[DevToolsMediaQueries]: ../device-mode/index.md#show-media-queries "显示媒体查询 - 在 DevTools Microsoft Edge中模拟移动设备|Microsoft Docs"
[DevToolsDeviceModeIndex]: ../device-mode/index.md "在 Microsoft Edge 开发人员工具中模拟移动设备 | Microsoft Docs"
[DevtoolsAccessibilityReference]: reference.md "DevTools |Microsoft Docs"
[DevToolsColorSchemeSimulation]: ./preferred-color-scheme-simulation.md "深色或浅色配色方案模拟|Microsoft Docs"
[DevToolsIssuesTool]: ../issues/index.md "查找并修复 Microsoft Edge DevTools 问题工具的问题 | Microsoft Docs"
[DevToolsReducedMotion]: ./reduced-motion-simulation.md "减少运动模拟|Microsoft Docs"
[DevToolsVisionDeficiencies]: ./emulate-vision-deficiencies.md "模拟视觉缺陷|Microsoft Docs"
<!-- links into test-issues-tool.md -->
[DevToolsAccessibilityTestIssuesToolViewAccSection]: test-issues-tool.md#view-the-accessibility-section-of-the-issues-tool "查看问题工具的辅助功能部分 - 自动测试网页的辅助功能问题|Microsoft Docs"
[DevtoolsAccessibilityTestIssuesToolCheckFieldsLabels]: test-issues-tool.md#verify-that-input-fields-have-labels "验证输入字段是否包含标签 - 自动测试网页的辅助功能|Microsoft Docs" 
[DevtoolsAccessibilityTestIssuesToolCheckAltText]: test-issues-tool.md#verify-that-images-have-alt-text "验证图像是否包含替换文字 - 自动测试网页的辅助功能|Microsoft Docs "
[DevtoolsAccessibilityTestIssuesToolCheckContrast]: test-issues-tool.md#verify-that-text-colors-have-enough-contrast "验证文本颜色是否具有足够的对比度 - 自动测试网页的辅助功能问题|Microsoft Docs"
<!-- links into test-inspect-tool.md -->
[DevtoolsAccessibilityTestInspectToolColorHighlighting]: test-inspect-tool.md#identify-nested-regions-using-color-highlighting "使用颜色突出显示标识嵌套区域 - 使用&quot;检查&quot;工具通过将鼠标悬停在网页上方来检测|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolIndivElems]: test-inspect-tool.md#check-individual-elements-for-text-contrast-screen-reader-text-and-keyboard-support "检查各个元素的文本对比度、屏幕阅读器文本和键盘支持 - 使用 Inspect 工具通过将鼠标悬停在网页页面上方来检测|Microsoft Docs"
[DevtoolsAccessibilityTestInspectToolDomCss]: test-inspect-tool.md#use-the-inspect-tool-to-hover-over-the-webpage-to-highlight-the-dom-and-css "使用&quot;检查&quot;工具将鼠标悬停在网页上方以突出显示 DOM 和 CSS - 使用&quot;检查&quot;工具通过将鼠标悬停在网页上方来检测|Microsoft Docs"
<!-- external links -->
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
[W3CContrastRatio]: https://www.w3.org/TR/WCAG21/#dfn-contrast-ratio "对比率|W3C"
[WCAG]: https://www.w3.org/TR/WCAG21/ "Web 内容辅助功能指南|W3C"
[AccessibilityInsightsAssessment]: https://accessibilityinsights.io/docs/en/web/getstarted/assessment/ "Accessibility Insights for Web |辅助功能见解"
[AccessibilityInsights]: https://accessibilityinsights.io "辅助功能见解"
[Lighthouse]: https://developers.google.com/web/tools/lighthouse/ "浅|Google"
[WebhintForCode]:https://aka.ms/webhint4code "webhint |Visual StudioMarketplace"
