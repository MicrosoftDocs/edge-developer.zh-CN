---
description: 使用"问题"工具的"辅助功能"部分自动测试网页的辅助功能问题。
title: 自动测试网页中的辅助功能问题
author: MSEdgeTeam
ms.author: msedgedevrel
ms.date: 06/07/2021
ms.topic: article
ms.prod: microsoft-edge
keywords: microsoft edge, web 开发, f12 工具, devtools
ms.openlocfilehash: 1cba9db1744235dfbfd2a007e33d1101452aab31
ms.sourcegitcommit: e150d798161277fd3fc610838ef2611dc08f5cf6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "11624736"
---
# <a name="automatically-test-a-webpage-for-accessibility-issues"></a>自动测试网页中的辅助功能问题

问题**工具****包括辅助功能部分**，可自动报告图像上缺少可选文本、表单字段上缺少标签以及文本颜色对比度不足等问题。  问题**工具**位于 DevTools 底部的"箱"内。 ****  本文使用辅助功能测试演示网页逐步介绍了如何使用问题工具的**辅助功能****部分。**

有几种打开问题 **工具的方法** ，例如：
*  选择 DevTools ** (右上角** 的"问题") "问题" ![ 计数器 ](../media/issues-counter-icon.msft.png) \) 。
*  在" **元素** "工具的 DOM 树中 **，Shift+单击** 元素上的波浪下划线。
*  在"**命令"菜单中**，键入 `issues` ，然后选择"**显示问题"。**


## <a name="view-the-accessibility-section-of-the-issues-tool"></a>查看问题工具的辅助功能部分

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。  在右上角，"问题"计数器 **\ (** Issues 计数器 \) 显示为语音气泡图标以及自动检测到 ![ ](../media/issues-counter-icon.msft.png) 的问题数。  浏览器中可能会显示不同的数字，并且该数字可能会随着使用 DevTools 而更新。

    :::image type="complex" source="../media/a11y-testing-issues-tracker.msft.png" alt-text="DevTools 中的问题计数器，指示当前文档中的问题数" lightbox="../media/a11y-testing-issues-tracker.msft.png":::
        DevTools 中的"问题"计数器，指示当前文档中的问题数****
    :::image-end:::

1.  选择" **问题"计数器**。  "**问题**"工具将在 DevTools 底部的"箱"中打开。 ****

    :::image type="complex" source="../media/a11y-testing-accessibility-issues.msft.png" alt-text="问题工具中显示的辅助功能警告" lightbox="../media/a11y-testing-accessibility-issues.msft.png":::
        问题工具中显示的辅助功能警告
    :::image-end:::

1.  在" **问题"** 选项卡上，展开 **"辅助功能"** 部分。


## <a name="verify-that-input-fields-have-labels"></a>验证输入字段是否包含标签

若要检查输入字段是否连接了标签，请使用问题工具，**** 该工具会自动检查整个网页，并报告辅助功能**部分中的此问题**。

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  在右上角，选择问题 **计数器** \ (![ 问题计数器 ](../media/issues-counter-icon.msft.png) \) 。  "**问题**"工具将在 DevTools 底部的"箱"中打开。 ****

1.  在" **问题"** 选项卡上，展开 **"辅助功能"** 部分。

1.  展开 **警告** `Form elements must have labels: Element has no title attribute Element has no placeholder attribute` 。

1. 选择" **在元素中打开"** 链接。

    :::image type="complex" source="../media/a11y-testing-inspect-problematic-element.msft.png" alt-text="在问题工具中选择链接后显示有问题的 HTML 的元素工具" lightbox="../media/a11y-testing-inspect-problematic-element.msft.png":::
        在"问题"工具中选择链接后显示有问题的 HTML **的元素** 工具 :::image-end:::

    将 **打开"** 元素"工具，同时在 DOM 树中突出显示元素。  " **样式** "窗格显示元素应用的 CSS 规则。  现在将显示以下代码。

    ```html
    <label>Search</label>
    <input type="search">
    <input type="submit" value="go">
    ```

    在以上代码中，元素使用不正确，因为 元素和特定元素 `label` `label` 之间没有 `input` 连接。  若要将 `label` 元素连接到特定 `input` 元素，请使用以下任一选项。
    *   将 `input` 元素嵌套在 `label` 元素中。
    *   在 `label` 元素中，添加 `for` 与 元素的属性 `id` 匹配的 `input` 属性。

    还有另一种方法可以测试元素之间缺少连接。 在" **元素"** 工具中， `<label>Search</label>` 选择 DOM 树中的元素。  在网页上，请注意，焦点只出现在 **搜索** 标签上，而不是输入文本框上。  正确的实现将焦点放在输入 `search` 文本框和 **搜索标签** 上。

1.  作为正确连接的示例，选择"捐赠 **"表单** 上的"其他"标签。  焦点指示器框正确显示在"其他"标签旁边的输入文本框上，因为**** 存在匹配 `for` 值 `id` 和属性值。

1.  在" **问题"工具**中，选择"进一步 **阅读** "以了解有关问题有关详细信息。  若要打开新选项卡中的链接，请按**Ctrl**单击 Windows/Linux 上的链接，或单击 + ******** + **** macOS 上的链接的命令。

    :::image type="complex" source="../media/a11y-testing-more-information-links.msft.png" alt-text="指向有关问题的更深入信息的问题选项卡上的链接" lightbox="../media/a11y-testing-more-information-links.msft.png":::
        指向 **有关问题的** 更深入信息的"问题"选项卡上的链接
    :::image-end:::


## <a name="verify-that-images-have-alt-text"></a>验证图像是否包含替换文字

基本辅助功能测试要求确保为图像 (_可选_ 文字) 可选文字。

若要自动检查是否为图像提供了替换文字，请使用 **问题工具，** 该工具具有 **辅助功能** 部分。  问题**工具**位于 DevTools**** 底部的"箱"中。

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  若要打开 **"问题"** 工具，请选择**** DevTools 右上角的"问题"计数器。

1.  在" **问题"** 选项卡上，展开警告 `Images must have alternate text: Element has no title attribute` 。  有四种图像实例缺少替换文字。

    :::image type="complex" source="../media/a11y-testing-images-without-alt.msft.png" alt-text="问题工具报告缺少可选文本的图像" lightbox="../media/a11y-testing-images-without-alt.msft.png":::
        问题工具报告缺少可选文本的图像
    :::image-end:::

有关详细信息，导航到 [图像必须具有备用文本](https://dequeuniversity.com/rules/axe/4.1/image-alt)。


## <a name="verify-that-text-colors-have-enough-contrast"></a>验证文本颜色是否具有足够的对比度

若要自动检查文本颜色是否具有足够的对比度，请使用问题 **工具，** 该工具 **具有辅助功能部分** 。  问题**工具**位于 DevTools**** 底部的"箱"中。

1.  在 [浏览器的新选项卡中][DevToolsA11yErrorsDemopage] 打开辅助功能测试演示网页，然后选择 **F12** 以打开 DevTools。

1.  若要打开 **"问题"** 工具，请选择**** DevTools 右上角的"问题"计数器。  您可能会收到警告，指出演示网页上的两个元素的对比度不足。

    :::image type="complex" source="../media/a11y-testing-contrast-issues.msft.png" alt-text="问题工具中报告的对比度问题" lightbox="../media/a11y-testing-contrast-issues.msft.png":::
        问题工具中报告的对比度问题
    :::image-end:::

1.  根据您的设置，"问题"**** 选项卡可能会显示一条警告，如用户可能由于颜色对比度不足而难以**阅读文本内容**。   可以展开该警告，然后展开受影响的 **资源**。  将显示元素列表，其中具有对比度不足的元素列表。


1.  选择 `li.high` 元素。  在呈现的网页中，突出显示**了"小**动物****"部分中的"动物"链接，显示一个小的信息覆盖层。  这是当您将鼠标悬停在"元素"工具中 DOM 树中的某个元素上时出现的 **相同** 覆盖。

    :::image type="complex" source="../media/a11y-testing-element-with-contrast-issues.msft.png" alt-text="在受影响资源部分选择链接后突出显示的网页中的元素" lightbox="../media/a11y-testing-element-with-contrast-issues.msft.png":::
        在"受影响资源"部分选择链接后 **突出显示的网页中的** 元素
    :::image-end:::


### <a name="wavy-underlines-in-the-dom-tree-indicate-automatically-detected-issues"></a>DOM 树中的波浪下划线指示自动检测到的问题 

元素工具中的 DOM **树直接** 在 HTML 中用波浪下划线标记问题。  这些问题由问题**工具报告。**  当 **Shift+单击** 带波浪下划线的任何元素时，将显示 **"问题"** 工具。

1.  在" **元素** "工具的 DOM 树中 **，Shift+单击** 元素，其下 `<input type="search">` 有一条波浪线 `input` 。  将显示 **"** 问题"工具，并显示该元素的问题。

    :::image type="complex" source="../media/a11y-testing-wavy-underlines.msft.png" alt-text="DOM 视图中具有波浪下划线的元素有一个问题" lightbox="../media/a11y-testing-wavy-underlines.msft.png":::
        DOM 视图中具有波浪下划线的元素有一个问题
    :::image-end:::


## <a name="see-also"></a>另请参阅

*  [使用问题工具查找和修复问题][DevToolsIssuesTool]
*  [使用 DevTools 的辅助功能测试概述](accessibility-testing-in-devtools.md)


## <a name="getting-in-touch-with-the-microsoft-edge-devtools-team"></a>联系 Microsoft Edge DevTools 团队  

[!INCLUDE [contact DevTools team note](../includes/contact-devtools-team-note.md)]  


<!-- links -->
[DevToolsIssuesTool]: ../issues/index.md "使用问题工具查找并修复|Microsoft Docs"
[DevToolsA11yErrorsDemopage]: https://microsoftedge.github.io/DevToolsSamples/a11y-testing/page-with-errors.html "辅助功能测试演示网页|GitHub"
